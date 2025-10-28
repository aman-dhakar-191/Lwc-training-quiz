# Quiz Set 2: Answers - JSON Data Handling from APIs in LWC

---

## Section A: Multiple Choice Answers (1-50)

### JSON Fundamentals

**A1.** b) .json

**A2.** c) Technically yes, but last value overwrites
(While parsers handle duplicates differently, the last occurrence typically overwrites. It's not recommended.)

**A3.** b) 3.14
(JSON supports decimal numbers. Hexadecimal, Infinity, and special formats are invalid.)

**A4.** b) false
(Lowercase, no quotes: `{"isActive": false}`)

**A5.** b) No, ignored by parsers
(Whitespace is not significant in JSON, only used for readability.)

**A6.** b) No, keys must be strings in quotes
(Even numbers must be in quotes: `{"123": "value"}`)

**A7.** b) UTF-8
(JSON is typically encoded in UTF-8.)

**A8.** c) No, comments not supported
(JSON specification does not support comments.)

**A9.** b) {} is an object with no properties, null is absence of value
(They serve different purposes.)

**A10.** b) Yes, mixed types allowed
```json
[1, "text", true, null, {"key": "value"}]
```

### Basic HTTP Callout in Apex

**A11.** c) Remote Site Settings configuration
(Remote Site Settings must whitelist the endpoint URL.)

**A12.** b) Stores endpoint URL and authentication in metadata
(Benefits: secure storage, no Remote Site Settings needed, easier management.)

**A13.** b) 6 MB for synchronous
(Maximum is 6 MB for synchronous callouts, 12 MB for asynchronous.)

**A14.** b) Debug logs in Developer Console
(Use System.debug() and check logs in Developer Console or Setup.)

**A15.** b) No, must use @future or Queueable
(Triggers run synchronously and cannot make callouts directly.)

**A16.** c) setTimeout(milliseconds)
```apex
req.setTimeout(60000); // 60 seconds
```

### JSON Parsing in Apex

**A17.** b) JSON.serialize()

**A18.** b) Parse as strings then convert to DateTime
(JSON represents dates as ISO 8601 strings that must be parsed.)

**A19.** b) Controls JSON serialization access for properties
(@JsonAccess controls whether properties are serialized, deserialized, both, or neither.)

**A20.** a) Use JSON.deserialize() (default behavior)
(`JSON.deserialize()` ignores unknown properties by default, unlike `deserializeStrict()`.)

**A21.** b) Use JSON.deserializeUntyped() and iterate through keys
```apex
Map<String, Object> jsonMap = (Map<String, Object>) JSON.deserializeUntyped(jsonString);
for (String key : jsonMap.keySet()) {
    Object value = jsonMap.get(key);
}
```

**A22.** b) Pretty-printing adds whitespace for readability
```apex
String pretty = JSON.serializePretty(obj);
```

**A23.** b) Yes, using JSON.deserializeUntyped()
```apex
List<Object> items = (List<Object>) JSON.deserializeUntyped('["a","b","c"]');
```

**A24.** b) Throws exception if JSON has extra properties
(Strict mode enforces exact match with Apex class structure.)

### Apex Method Setup for LWC

**A25.** b) Yes, unlimited
(You can have as many @AuraEnabled methods as needed.)

**A26.** b) Use try-catch and throw AuraHandledException
```apex
try {
    // logic
} catch (Exception e) {
    throw new AuraHandledException(e.getMessage());
}
```

**A27.** b) Yes, can use Platform Cache
(@AuraEnabled methods can use both org cache and session cache.)

**A28.** b) No, can be void
(Methods can have void return type if they don't return data.)

**A29.** b) Throws exception if exceeds governor limits
(CPU time, heap size, and other limits apply.)

**A30.** b) Yes, subject to governor limits
(All governor limits apply including CPU time, SOQL, DML, heap size.)

### Calling Apex from LWC

**A31.** c) No fixed limit
(Import as many as needed from one or multiple controllers.)

**A32.** b) Promise is rejected, control passes to .catch()
(Exception details are available in the error object.)

**A33.** b) Yes, automatically serialized to JSON
(Objects are serialized to JSON and deserialized to Apex objects.)

**A34.** b) Use boolean property to track loading state
```javascript
this.isLoading = true;
getData()
    .then(result => { this.data = result; })
    .finally(() => { this.isLoading = false; });
```

**A35.** b) Provides reactive data binding
(@wire automatically calls Apex when parameters change.)

**A36.** b) Yes, parameters must be reactive properties
```javascript
@wire(getDataWithParam, { paramName: '$propertyName' })
```

**A37.** b) Cacheable are read-only and can be reused, non-cacheable fetch fresh data
(Cacheable methods allow framework caching, non-cacheable can perform DML.)

**A38.** b) Cannot directly cancel once initiated
(Track component state and ignore results if needed.)

### Processing JSON Data in LWC JavaScript

**A39.** c) JSON.stringify()

**A40.** b) hasOwnProperty() or 'prop' in obj
```javascript
obj.hasOwnProperty('propName')
'propName' in obj
obj?.propName !== undefined
```

**A41.** b) Tests if at least one element passes condition
```javascript
const hasActive = items.some(item => item.active === true);
```

**A42.** d) Both b and c
(Optional chaining `obj?.nested?.property` or manual checking both work.)

**A43.** b) null is explicit "no value", undefined is unassigned
(`null` is deliberately assigned, `undefined` means never assigned.)

**A44.** c) includes()
```javascript
const exists = array.includes(searchValue);
```

**A45.** b) Reduces to single value by applying function
```javascript
const sum = numbers.reduce((acc, curr) => acc + curr, 0);
```

### Displaying Data in LWC

**A46.** b) iterator:it
```html
<template iterator:it={items}>
    <div key={it.value.id}>{it.index} - {it.value.name}</div>
</template>
```

**A47.** b) Use computed property that returns class name
```javascript
get computedClass() {
    return this.isActive ? 'active' : 'inactive';
}
```

**A48.** b) No, use nested template
```html
<template if:true={hasData}>
    <template for:each={items} for:item="item" for:key={item.id}>
        ...
    </template>
</template>
```

**A49.** b) Use data attributes to store item info
```html
<button onclick={handleClick} data-id={item.id}>Click</button>
```
```javascript
handleClick(event) {
    const itemId = event.target.dataset.id;
}
```

**A50.** b) Format in JavaScript getter first
```javascript
get formattedDate() {
    return this.dateObj.toLocaleDateString();
}
```

---

## Section B: Coding Answers (51-60)

**A51.**
```json
[1, 2, 3]
```

**A52.**
```apex
req.setHeader('Authorization', 'Bearer token123');
```

**A53.**
```apex
List<String> items = new List<String>{'a', 'b', 'c'};
String jsonString = JSON.serialize(items);
```

**A54.**
```apex
public class ApiResponse {
    public Boolean success;
    public List<Integer> data;
}
```

**A55.**
```apex
@AuraEnabled
public static Integer getLength(String input) {
    return input.length();
}
```

**A56.**
```javascript
async handleLoad() {
    try {
        const result = await getData();
        this.data = result;
    } catch (error) {
        this.error = error;
    }
}
```

**A57.**
```javascript
const sum = numbers.reduce((acc, curr) => acc + curr, 0);
```

**A58.**
```javascript
const unique = [...new Set(numbers)];
```

**A59.**
```html
<div if:true={hasData}>Content here</div>
```

**A60.**
```apex
HttpResponse res = http.send(req);
if (res.getStatusCode() != 200) {
    throw new AuraHandledException('HTTP Error: ' + res.getStatus());
}
```
