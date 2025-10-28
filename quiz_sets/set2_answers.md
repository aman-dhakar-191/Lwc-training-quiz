# Quiz Set 2: Answers - JSON Data Handling from APIs in LWC

---

## JSON Fundamentals (Answers 1-10)

**A1.** .json

**A2.** b) Comma (,)
(Commas separate multiple key-value pairs within an object.)

**A3.** While JSON supports unlimited nesting, it's recommended to keep nesting to 5-10 levels for maintainability and performance. Deeply nested structures are harder to work with and can cause performance issues.

**A4.** Technically yes, but it's not recommended. If duplicate keys exist, the last occurrence typically overwrites previous values. JSON parsers handle this differently, so it should be avoided.

**A5.** b) 3.14
(JSON supports decimal numbers. Hexadecimal, Infinity, and special number formats are not valid.)

**A6.**
```json
[1, 2, 3]
```

**A7.** Simply as `false` (lowercase, no quotes): `{"isActive": false}`

**A8.** No, whitespace (spaces, tabs, newlines) is not significant in JSON. It's ignored by parsers and is only used for human readability.

**A9.** No, JSON keys must be strings. Even if they look like numbers, they must be enclosed in double quotes: `{"123": "value"}`

**A10.** An empty object `{}` is a valid object with no properties, while `null` represents the absence of an object/value. They serve different purposes.

---

## Basic HTTP Callout in Apex (Answers 11-16)

**A11.** Remote Site Settings must be configured in Salesforce Setup to whitelist the external endpoint URL before making callouts.

**A12.**
```apex
req.setMethod('GET');
```

**A13.** The default timeout is 120 seconds (120,000 milliseconds).

**A14.** Use `req.setTimeout(milliseconds)` method. For example: `req.setTimeout(60000);` for 60 seconds.

**A15.** No HTTP request is made. The request is only prepared but not executed. You must call `Http.send(req)` to actually make the callout.

**A16.** No, HTTP callouts cannot be made directly from triggers because triggers run synchronously. You must use @future methods or Queueable Apex to make callouts from triggers.

---

## JSON Parsing in Apex (Answers 17-24)

**A17.** `JSON.deserializeUntyped()` returns an Object that can be cast to `Map<String, Object>` for JSON objects or `List<Object>` for JSON arrays.

**A18.**
```apex
List<String> items = new List<String>{'a', 'b', 'c'};
String jsonString = JSON.serialize(items);
```

**A19.** Null values in JSON are automatically handled and mapped to null in Apex. You can check for null using standard null checks: `if (obj.property != null) { ... }`

**A20.** `JSON.deserialize()` requires a specific Apex type to deserialize into, providing type safety. `JSON.deserializeUntyped()` returns generic Object types (Map/List) and is more flexible for dynamic JSON structures.

**A21.**
```apex
public class UserWrapper {
    public UserDetail user;
    
    public class UserDetail {
        public Integer id;
        public String name;
    }
}
```

**A22.**
```apex
List<Object> items = (List<Object>) JSON.deserializeUntyped('["apple", "banana", "orange"]');
```

**A23.** `JSON.deserializeStrict()` enforces strict mode, which means it will throw an exception if the JSON contains extra properties not defined in the Apex class.

**A24.** Use `JSON.deserializeUntyped()` to get a `Map<String, Object>`, then iterate through the keys:
```apex
Map<String, Object> jsonMap = (Map<String, Object>) JSON.deserializeUntyped(jsonString);
for (String key : jsonMap.keySet()) {
    Object value = jsonMap.get(key);
}
```

---

## Apex Method Setup for LWC (Answers 25-30)

**A25.** Yes, @AuraEnabled methods can have parameters. Parameters are automatically deserialized from the JavaScript call.

**A26.**
```apex
@AuraEnabled
public static Integer getLength(String input) {
    return input.length();
}
```

**A27.** `@AuraEnabled` methods are called fresh each time. `@AuraEnabled(cacheable=true)` allows LWC to cache results for improved performance, but should only be used for read-only operations that don't modify data.

**A28.** No, @AuraEnabled methods must be public or global. Private methods cannot be accessed from LWC.

**A29.** AuraHandledException for controlled error messages to LWC, or any standard exceptions (DmlException, QueryException, etc.). AuraHandledException provides better error messaging to the client.

**A30.** Yes, @AuraEnabled methods are subject to Apex governor limits including CPU time, heap size, SOQL queries, and DML statements.

---

## Calling Apex from LWC (Answers 31-37)

**A31.** `@salesforce/apex`

**A32.** Yes, you can call multiple Apex methods simultaneously using Promise.all():
```javascript
Promise.all([method1(), method2()]).then(results => { ... })
```

**A33.**
```apex
async handleLoad() {
    try {
        const result = await getData();
        this.data = result;
    } catch (error) {
        this.error = error;
    }
}
```

**A34.** @wire automatically handles reactive parameters, caches data, and updates the UI when wired data changes. It's better for data that updates automatically. Imperative calls give more control over when data is fetched.

**A35.** The promise is rejected and control passes to the .catch() block (or catch in try-catch for async/await). The error object contains details about the exception.

**A36.** Yes, you can pass JavaScript objects which are automatically serialized to JSON and deserialized to Apex objects. The structure should match what the Apex method expects.

**A37.** Use a boolean property to track loading state:
```javascript
this.isLoading = true;
getData()
    .then(result => { this.data = result; })
    .finally(() => { this.isLoading = false; });
```

---

## Processing JSON Data in LWC JavaScript (Answers 38-44)

**A38.** `push()` method

**A39.**
```javascript
const exists = array.includes(searchValue);
```

**A40.** `find()` returns the first element that matches the condition (or undefined). `filter()` returns an array of all elements that match the condition.

**A41.**
```javascript
array.sort((a, b) => a.propertyName - b.propertyName);
```

**A42.**
```javascript
const sum = numbers.reduce((acc, curr) => acc + curr, 0);
```

**A43.** Use spread operator `[...array]` or `Array.from(array)` or `array.slice()`.

**A44.** Destructuring extracts values from objects/arrays into variables:
```javascript
const {name, age} = person;
const [first, second] = array;
```
It makes code cleaner when working with JSON data.

---

## Displaying Data in LWC (Answers 45-50)

**A45.** `for:key` attribute

**A46.**
```html
<div if:true={hasData}>Content here</div>
```

**A47.** Use a getter or format the date in JavaScript first, then bind to template:
```javascript
get formattedDate() {
    return this.dateObj.toLocaleDateString();
}
```

**A48.** Limited expressions are allowed. You can use property access, ternary operators, and some methods, but not complex expressions or statements.

**A49.** LWC will show a warning in the console and may have rendering issues. Each item in for:each must have a unique key for proper rendering and performance.

**A50.** Use conditional rendering with if:true/if:false to check array length:
```html
<template if:true={hasData}>
    <template for:each={items} for:item="item" for:key={item.id}>
        ...
    </template>
</template>
<template if:false={hasData}>
    <p>No data available</p>
</template>
```

---

## Error Handling (Answers 51-54)

**A51.**
```apex
@AuraEnabled
public static String getData() {
    throw new AuraHandledException('Custom error message');
}
```

**A52.** The error object typically contains: `error.body.message`, `error.body.stackTrace`, `error.status`, and `error.statusText`.

**A53.** HTTP status code 404

**A54.** Check the error structure and properties:
```javascript
if (error.body && error.body.message) {
    // AuraHandledException
} else if (error.status) {
    // Network error
}
```

---

## Reactive Properties (Answers 55-57)

**A55.** Yes, primitive properties are automatically reactive in LWC. Changes to them automatically trigger UI updates.

**A56.** In modern LWC, you typically don't need to force re-rendering. If necessary, you can reassign the property: `this.data = [...this.data]` for arrays or `this.obj = {...this.obj}` for objects.

**A57.**
```javascript
@api recordId;
```

---

## Practical Application (Answers 58-59)

**A58.** Complete component design:

**Apex Controller:**
```apex
public with sharing class WeatherController {
    @AuraEnabled(cacheable=true)
    public static Map<String, Object> getWeather(String city) {
        HttpRequest req = new HttpRequest();
        req.setEndpoint('callout:WeatherAPI/weather?q=' + city);
        req.setMethod('GET');
        try {
            Http http = new Http();
            HttpResponse res = http.send(req);
            if (res.getStatusCode() == 200) {
                return (Map<String, Object>) JSON.deserializeUntyped(res.getBody());
            }
            throw new AuraHandledException('Error: ' + res.getStatus());
        } catch (Exception e) {
            throw new AuraHandledException(e.getMessage());
        }
    }
}
```

**LWC JavaScript:**
```javascript
import { LightningElement } from 'lwc';
import getWeather from '@salesforce/apex/WeatherController.getWeather';

export default class Weather extends LightningElement {
    temperature;
    error;
    city = 'London';

    handleFetch() {
        getWeather({ city: this.city })
            .then(result => {
                this.temperature = result.main.temp;
                this.error = undefined;
            })
            .catch(error => {
                this.error = error.body.message;
                this.temperature = undefined;
            });
    }
}
```

**A59.** Implement pagination with page tracking:
```javascript
export default class PaginatedList extends LightningElement {
    pageNumber = 1;
    pageSize = 10;
    totalRecords = 0;
    
    get offset() {
        return (this.pageNumber - 1) * this.pageSize;
    }
    
    handleNext() {
        if (this.pageNumber < this.totalPages) {
            this.pageNumber++;
            this.fetchData();
        }
    }
    
    handlePrevious() {
        if (this.pageNumber > 1) {
            this.pageNumber--;
            this.fetchData();
        }
    }
}
```
