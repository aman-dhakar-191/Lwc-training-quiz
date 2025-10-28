# Quiz Set 1: Answers - JSON Data Handling from APIs in LWC

---

## JSON Fundamentals (Answers 1-10)

**A1.** JavaScript Object Notation

**A2.** b) String
(JSON supports: strings, numbers, booleans, null, objects, and arrays. Functions, undefined, and Date objects are not valid JSON data types.)

**A3.** b) {"key": "value"}
(JSON requires double quotes around both keys and string values.)

**A4.** b) []
(Square brackets denote arrays in JSON.)

**A5.** No, this JSON is invalid. JSON does not allow trailing commas after the last property.

**A6.** JSON does not support `undefined`. If a value is absent or empty, it should be represented as `null` in JSON. `undefined` is a JavaScript concept and will cause JSON parsing errors.

**A7.**
```json
{"name": "Alice", "age": 25}
```

**A8.**
```json
{
  "name": "John",
  "address": {
    "city": "New York",
    "zipCode": "10001"
  }
}
```

**A9.** c) NaN
(NaN is not a valid JSON value. JSON supports true, false, and null.)

**A10.** Yes, JSON property names can contain spaces, but they must be enclosed in double quotes, like `{"first name": "John"}`. However, it's best practice to avoid spaces in property names.

---

## Basic HTTP Callout in Apex (Answers 11-16)

**A11.** b) Http

**A12.** `setEndpoint()`

**A13.**
```apex
HttpRequest req = new HttpRequest();
```

**A14.** The valid HTTP methods include: GET, POST, PUT, PATCH, DELETE, HEAD. Common ones are GET and POST.

**A15.** `Http.send(HttpRequest)` method sends the request and returns an HttpResponse object.

**A16.** `getBody()` to retrieve the response body as a string, and `getStatusCode()` to get the HTTP status code.

---

## JSON Parsing in Apex (Answers 17-24)

**A17.** `JSON.deserialize()`

**A18.** `JSON.serialize()`

**A19.**
```apex
Map<String, Object> result = (Map<String, Object>) JSON.deserializeUntyped('{"name":"John"}');
```

**A20.** A wrapper class is an Apex class that mirrors the structure of a JSON response, with properties matching the JSON fields. It's used to deserialize JSON into a strongly-typed Apex object.

**A21.**
```apex
public class ResponseWrapper {
    public String id;
    public String name;
}
```

**A22.** First deserialize the JSON to a List, then access elements by index: `List<Object> items = (List<Object>) result.get('arrayField'); Object firstItem = items[0];`

**A23.** A JSONException will be thrown if you try to deserialize invalid JSON. This should be caught in a try-catch block.

**A24.** Yes, you can deserialize a JSON array directly into a List of wrapper objects:
```apex
List<ResponseWrapper> items = (List<ResponseWrapper>) JSON.deserialize(jsonString, List<ResponseWrapper>.class);
```

---

## Apex Method Setup for LWC (Answers 25-30)

**A25.** `@AuraEnabled`

**A26.** Yes, for LWC, @AuraEnabled methods must be static.

**A27.**
```apex
@AuraEnabled
public static String getDataString() {
    return 'Hello';
}
```

**A28.** `cacheable=true` allows the LWC framework to cache the method results, improving performance. It should only be used for read-only operations that don't modify data.

**A29.** Primitive types (String, Integer, Boolean, etc.), Lists, Maps, and custom Apex classes (which are automatically serialized to JSON).

**A30.** No, for LWC, @AuraEnabled methods must be static. Instance methods are not supported.

---

## Calling Apex from LWC (Answers 31-37)

**A31.** `import`

**A32.**
```javascript
import getAccountData from '@salesforce/apex/AccountController.getAccountData';
```

**A33.** 1) Imperative calls using import and then calling the method programmatically, 2) Wire service using @wire decorator.

**A34.** The `.then()` block handles the successful resolution of a promise, processing the returned data.

**A35.** The `.catch()` block handles errors or rejections from the promise.

**A36.**
```javascript
getData()
    .then(result => {
        this.data = result;
    })
    .catch(error => {
        console.error(error);
    });
```

**A37.** Both handle asynchronous operations. `async/await` provides a more synchronous-looking syntax and is generally easier to read. `.then()/.catch()` uses promise chaining. `async/await` uses try-catch for error handling.

---

## Processing JSON Data in LWC JavaScript (Answers 38-44)

**A38.** Using dot notation: `object.firstName` or bracket notation: `object['firstName']`

**A39.** `map()`

**A40.** `forEach()` iterates over elements without returning anything, used for side effects. `map()` creates and returns a new array with transformed elements.

**A41.**
```javascript
const activeData = data.filter(item => item.status === 'active');
```

**A42.** Simply assign the value to the property: `this.propertyName = receivedData;` The LWC framework automatically tracks changes to component properties.

**A43.** The UI automatically re-renders to reflect the new data values when a reactive property is updated.

**A44.**
```javascript
const names = arrayOfObjects.map(obj => obj.name);
```

---

## Displaying Data in LWC (Answers 45-50)

**A45.** `for:each`

**A46.** `for:each` requires two attributes: the array to iterate (`for:each={array}`) and a unique key for each item (`for:key={item.id}` or similar).

**A47.**
```html
<template for:each={items} for:item="item" for:key={item.id}>
    <li>{item.name}</li>
</template>
```

**A48.** `if:true` renders the element when the condition is truthy, while `if:false` renders the element when the condition is falsy.

**A49.** Use curly braces in the template: `{propertyName}` or `{object.property}`

**A50.** Yes, you can nest `for:each` loops, but you need different item names (for:item) for each level to avoid conflicts.

---

## Error Handling (Answers 51-54)

**A51.** `catch` (as part of try-catch blocks)

**A52.**
```apex
try {
    HttpResponse res = http.send(req);
} catch (CalloutException e) {
    System.debug('Callout error: ' + e.getMessage());
}
```

**A53.** HTTP status code 200 (OK) indicates success. Codes in the 200-299 range generally indicate success.

**A54.** You can store the error in a component property and display it in the template:
```javascript
.catch(error => {
    this.errorMessage = error.body.message;
})
```

---

## Reactive Properties (Answers 55-57)

**A55.** `@api`

**A56.** In modern LWC (API version 40+), you rarely need @track. Use it only if you need to track changes to specific properties of objects or elements of arrays.

**A57.** No, modern LWC automatically tracks changes to objects and arrays. @track is generally not needed unless you have specific use cases.

---

## Practical Application (Answers 58-59)

**A58.** Complete flow:
1. External API provides JSON data at an endpoint
2. Apex method makes HTTP callout using Http and HttpRequest classes
3. Apex receives HttpResponse and extracts JSON using getBody()
4. Apex parses JSON using JSON.deserialize() into Apex objects
5. @AuraEnabled Apex method returns data to LWC
6. LWC JavaScript calls Apex method (imperative or wire)
7. LWC receives data in .then() block and assigns to reactive property
8. LWC template uses data binding and for:each to display data
9. UI automatically updates when reactive property changes

**A59.** Create a button with an onclick handler that calls the Apex method:
```javascript
handleRefresh() {
    getData()
        .then(result => {
            this.data = result;
        })
        .catch(error => {
            this.error = error;
        });
}
```
