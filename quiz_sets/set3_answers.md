# Quiz Set 3: Answers - JSON Data Handling from APIs in LWC

---

## JSON Fundamentals (Answers 1-10)

**A1.** b) UTF-8
(JSON is always encoded in UTF-8, UTF-16, or UTF-32, but UTF-8 is the standard.)

**A2.** No, JSON does not support comments. Comments are not part of the JSON specification. If you need to add notes, you must use a property like "_comment" in the JSON itself.

**A3.**
```json
{"active": true, "count": 5}
```

**A4.** An empty array is represented as: `[]`

**A5.** Colon (:)

**A6.** Yes, this is valid JSON. `null` is a valid JSON value for any property.

**A7.** c) Can be either object or array
(A JSON document can have an object or array as its root element.)

**A8.** Yes, a JSON array can contain mixed data types:
```json
[1, "text", true, null, {"key": "value"}, [1, 2]]
```

**A9.** The key `name` is not enclosed in double quotes. All JSON keys must be strings enclosed in double quotes: `{"name": "John", "age": 30}`

**A10.** Use a backslash: `\"` 
Example: `{"message": "He said \"Hello\""}`

---

## Basic HTTP Callout in Apex (Answers 11-16)

**A11.** No special permission is required at the profile level for making callouts, but the user must have access to the Apex class making the callout.

**A12.** A Named Credential stores endpoint URL and authentication details in Salesforce metadata. Benefits: secure credential storage, no need to add Remote Site Settings, easier credential management, and supports various authentication protocols.

**A13.**
```apex
req.setHeader('Authorization', 'Bearer token123');
```

**A14.** The maximum size of an HTTP response body is 6 MB for synchronous callouts and 12 MB for asynchronous callouts (in continuation context).

**A15.** `HttpResponse` class

**A16.** Use `System.debug()` to log the request and response:
```apex
System.debug('Request: ' + req.getEndpoint());
System.debug('Response Body: ' + res.getBody());
System.debug('Status Code: ' + res.getStatusCode());
```
Also check debug logs in Developer Console or Setup.

---

## JSON Parsing in Apex (Answers 17-24)

**A17.** Use `JSON.deserialize()` with a List type:
```apex
List<MyClass> items = (List<MyClass>) JSON.deserialize(jsonString, List<MyClass>.class);
```

**A18.** JSON typically represents dates as ISO 8601 strings. Parse them as strings first, then convert:
```apex
String dateStr = '2024-01-15T10:30:00Z';
Datetime dt = Datetime.valueOf(dateStr.replace('T', ' ').replace('Z', ''));
```
Or use JSON.deserialize with a wrapper class having DateTime properties.

**A19.**
```apex
Map<String, Object> dataMap = new Map<String, Object>{'key' => 'value'};
String json = JSON.serialize(dataMap);
```

**A20.** `@JsonAccess` controls JSON serialization access for Apex properties. It can restrict whether a property is serialized (serializable), deserialized (deserializable), both, or neither.

**A21.** Use `JSON.deserialize()` (not deserializeStrict). It ignores unknown properties by default. Or use `JSON.deserializeUntyped()` for dynamic handling.

**A22.**
```apex
public class ApiResponse {
    public Boolean success;
    public List<Integer> data;
}
```

**A23.** Use `JSON.deserializeUntyped()` to get generic Object, then check structure and cast accordingly:
```apex
Map<String, Object> jsonMap = (Map<String, Object>) JSON.deserializeUntyped(jsonString);
Object dataField = jsonMap.get('data');
if (dataField instanceof List<Object>) {
    // Handle as array
} else if (dataField instanceof Map<String, Object>) {
    // Handle as object
}
```

**A24.** Serializing produces compact JSON (no formatting). Pretty-printing adds whitespace and indentation for readability:
```apex
String pretty = JSON.serializePretty(obj);
```

---

## Apex Method Setup for LWC (Answers 25-30)

**A25.** Yes, you can have as many @AuraEnabled methods as needed in a single Apex class.

**A26.** Best practice: Use try-catch blocks and throw `AuraHandledException` with user-friendly messages:
```apex
@AuraEnabled
public static String getData() {
    try {
        // logic
        return result;
    } catch (Exception e) {
        throw new AuraHandledException('Error: ' + e.getMessage());
    }
}
```

**A27.**
```apex
@AuraEnabled
public static List<String> getNames() {
    return new List<String>{'Alice', 'Bob', 'Charlie'};
}
```

**A28.** Yes, @AuraEnabled methods can use Platform Cache (org cache or session cache) to store and retrieve data, improving performance.

**A29.** If an @AuraEnabled method exceeds governor limits (CPU time, heap size), it will throw an exception which is passed to the LWC component's error handler.

**A30.** No, @AuraEnabled methods can have void return type if they don't need to return data to LWC.

---

## Calling Apex from LWC (Answers 31-37)

**A31.** There's no fixed limit. You can import as many Apex methods as needed from one or multiple controllers.

**A32.** All imported Apex methods return Promises in JavaScript, regardless of their actual Apex return type.

**A33.**
```javascript
import processData from '@salesforce/apex/MyController.processData';

processData({ name: 'John', age: 30 })
    .then(result => { console.log(result); })
    .catch(error => { console.error(error); });
```

**A34.** Yes, @wire can use methods with parameters. Parameters must be reactive properties decorated with @api or tracked:
```javascript
@wire(getDataWithParam, { paramName: '$propertyName' })
```

**A35.** You cannot directly cancel an Apex call once initiated. Best practice: track component state and ignore results if component unmounts or state changes.

**A36.** The @wire decorator provides reactive data binding. It automatically calls the Apex method when parameters change and updates the component when data is available.

**A37.** Cacheable methods (`cacheable=true`) allow the framework to cache results across component instances and reuse data. Non-cacheable methods always fetch fresh data and can perform DML operations. Cacheable methods are read-only.

---

## Processing JSON Data in LWC JavaScript (Answers 38-44)

**A38.**
```javascript
const len = array.length;
```

**A39.** Use `hasOwnProperty()`, `in` operator, or optional chaining:
```javascript
obj.hasOwnProperty('propName')
'propName' in obj
obj?.propName !== undefined
```

**A40.** `some()` tests whether at least one element passes a condition. Returns true/false:
```javascript
const hasActive = items.some(item => item.active === true);
```

**A41.**
```javascript
const unique = [...new Set(numbers)];
```

**A42.** Use optional chaining:
```javascript
const value = obj?.nested?.property?.deepProperty;
```
Or check each level:
```javascript
const value = obj && obj.nested && obj.nested.property;
```

**A43.** `null` is an explicitly assigned value meaning "no value". `undefined` means a variable/property has been declared but not assigned a value. In JSON, only `null` is valid.

**A44.** `JSON.stringify()`

---

## Displaying Data in LWC (Answers 45-50)

**A45.**
```html
<p>{userName}</p>
```

**A46.** Use template expressions with class attribute:
```html
<div class={computedClass}></div>
```
Or in JavaScript:
```javascript
get computedClass() {
    return this.isActive ? 'active-class' : 'inactive-class';
}
```

**A47.** No, you cannot use both on the same element. Use a nested template:
```html
<template if:true={hasData}>
    <template for:each={items} for:item="item" for:key={item.id}>
        ...
    </template>
</template>
```

**A48.** `iterator:it` directive provides more control with `first`, `last`, and `index` properties:
```html
<template iterator:it={items}>
    <div key={it.value.id}>
        {it.index} - {it.value.name}
    </div>
</template>
```

**A49.** Use data attributes to store item information and retrieve in event handler:
```html
<button onclick={handleClick} data-id={item.id}>Click</button>
```
```javascript
handleClick(event) {
    const itemId = event.target.dataset.id;
}
```

**A50.**
```javascript
get fullName() {
    return `${this.firstName} ${this.lastName}`;
}
```

---

## Error Handling (Answers 51-54)

**A51.** HTTP status codes 400-499 indicate client errors (400 Bad Request, 401 Unauthorized, 404 Not Found, etc.).

**A52.** Use `console.error()`, `console.log()`, or `console.warn()`:
```javascript
console.error('Error details:', error);
```
Check browser Developer Console to view logs.

**A53.**
```apex
HttpResponse res = http.send(req);
if (res.getStatusCode() != 200) {
    throw new AuraHandledException('HTTP Error: ' + res.getStatus());
}
```

**A54.** Store error messages in a component property and display using conditional rendering:
```html
<template if:true={error}>
    <div class="error-message">{error}</div>
</template>
```
Use `reduceErrors()` utility to format error objects into user-friendly messages.

---

## Reactive Properties (Answers 55-57)

**A55.**
```javascript
items = [];
```
(In modern LWC, explicit @track is not needed for arrays.)

**A56.** In modern LWC, directly modifying array elements triggers reactivity. The UI updates automatically. In older versions, you might need reassignment: `this.items = [...this.items]`.

**A57.** Use `@api` decorator to make the property public and reactive to parent changes:
```javascript
@api propertyName;
```

---

## Practical Application (Answers 58-59)

**A58.** Solution for API rate limiting:

**Apex with retry logic:**
```apex
@AuraEnabled
public static Object fetchData() {
    Integer retries = 3;
    while (retries > 0) {
        try {
            HttpResponse res = http.send(req);
            if (res.getStatusCode() == 429) {
                retries--;
                Integer delay = Integer.valueOf(res.getHeader('Retry-After'));
                // Log and continue
            } else if (res.getStatusCode() == 200) {
                return JSON.deserializeUntyped(res.getBody());
            }
        } catch (Exception e) {
            throw new AuraHandledException(e.getMessage());
        }
    }
    throw new AuraHandledException('Rate limit exceeded');
}
```

**LWC with exponential backoff:**
```javascript
async fetchWithRetry(retries = 3, delay = 1000) {
    try {
        return await getData();
    } catch (error) {
        if (retries > 0) {
            await new Promise(resolve => setTimeout(resolve, delay));
            return this.fetchWithRetry(retries - 1, delay * 2);
        }
        throw error;
    }
}
```

**A59.** Implement debouncing to avoid excessive API calls:
```javascript
export default class SearchComponent extends LightningElement {
    searchTerm = '';
    searchTimeout;
    
    handleSearch(event) {
        this.searchTerm = event.target.value;
        clearTimeout(this.searchTimeout);
        
        this.searchTimeout = setTimeout(() => {
            this.performSearch();
        }, 300); // Wait 300ms after user stops typing
    }
    
    performSearch() {
        if (this.searchTerm.length >= 3) {
            searchAPI({ term: this.searchTerm })
                .then(results => { this.results = results; })
                .catch(error => { this.error = error; });
        }
    }
}
```
