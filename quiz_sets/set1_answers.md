# Quiz Set 1: Answers - JSON Data Handling from APIs in LWC

---

## Section A: Multiple Choice Answers (1-50)

### JSON Fundamentals

**A1.** b) JavaScript Object Notation

**A2.** b) String
(JSON supports: strings, numbers, booleans, null, objects, and arrays. Functions, undefined, and Date objects are not valid JSON data types.)

**A3.** b) {"key": "value"}
(JSON requires double quotes around both keys and string values.)

**A4.** b) []
(Square brackets denote arrays in JSON.)

**A5.** c) NaN
(NaN is not a valid JSON value. JSON supports true, false, and null.)

**A6.** d) Colon (:) for key-value, comma (,) for pairs
(Colons separate keys from values, commas separate key-value pairs.)

**A7.** b) No, trailing commas are not allowed
(JSON does not allow trailing commas after the last property.)

**A8.** c) JSON only supports null, not undefined
(`undefined` is a JavaScript concept and will cause JSON parsing errors.)

**A9.** b) Yes, but they must be in double quotes
(Property names with spaces must be enclosed in double quotes, like `{"first name": "John"}`.)

**A10.** b) \"
(Backslash followed by double quote escapes it: `"He said \"Hello\""`)

### Basic HTTP Callout in Apex

**A11.** b) Http

**A12.** b) setEndpoint()

**A13.** b) HttpResponse

**A14.** a) Remote Site Settings
(Remote Site Settings must be configured to whitelist external endpoint URLs.)

**A15.** c) 120 seconds
(The default timeout is 120 seconds or 120,000 milliseconds.)

**A16.** a) getBody() and c) getStatusCode()
(These two methods are most commonly used to retrieve response data and status.)

### JSON Parsing in Apex

**A17.** b) JSON.deserialize()

**A18.** b) JSON.serialize()

**A19.** b) An Object that can be cast to Map or List
(Returns Object that can be cast to `Map<String, Object>` for JSON objects or `List<Object>` for JSON arrays.)

**A20.** b) An Apex class that mirrors JSON structure
(Wrapper classes have properties matching JSON fields for strongly-typed deserialization.)

**A21.** b) deserialize() requires a specific type, deserializeUntyped() returns Object
(`JSON.deserialize()` needs a target type for type safety, while `deserializeUntyped()` returns generic Objects.)

**A22.** c) Throws JSONException
(Invalid JSON causes a JSONException that should be caught in a try-catch block.)

**A23.** b) Yes, using JSON.deserialize()
```apex
List<WrapperClass> items = (List<WrapperClass>) JSON.deserialize(jsonString, List<WrapperClass>.class);
```

**A24.** b) They are automatically mapped to null in Apex
(Null values in JSON are automatically handled and mapped to null in Apex properties.)

### Apex Method Setup for LWC

**A25.** a) @AuraEnabled

**A26.** b) Yes, they must be static
(For LWC, @AuraEnabled methods must be static.)

**A27.** b) Allows LWC to cache results for performance
(`cacheable=true` allows the framework to cache method results. Should only be used for read-only operations.)

**A28.** c) Primitives, Lists, Maps, and custom classes
(All these types can be returned and are automatically serialized to JSON.)

**A29.** b) Yes, parameters are automatically deserialized
(Parameters are automatically deserialized from the JavaScript call.)

**A30.** b) No, they must be public or global
(@AuraEnabled methods must be public or global to be accessible from LWC.)

### Calling Apex from LWC

**A31.** c) import

**A32.** a) @salesforce/apex

**A33.** b) Imperative and wire
(Imperative calls for programmatic control, @wire for reactive data binding.)

**A34.** b) Successful resolution and data
(The `.then()` block handles successful promise resolution and processes returned data.)

**A35.** b) Errors or rejections
(The `.catch()` block handles errors or promise rejections.)

**A36.** b) Always a Promise
(All imported Apex methods return Promises in JavaScript, regardless of their Apex return type.)

**A37.** b) Automatic reactive parameter handling and caching
(@wire automatically updates when parameters change and caches data efficiently.)

**A38.** b) Yes, using Promise.all()
```javascript
Promise.all([method1(), method2()]).then(results => { ... })
```

### Processing JSON Data in LWC JavaScript

**A39.** b) object.firstName or object['firstName']
(Both dot notation and bracket notation work for property access.)

**A40.** c) map()
(`map()` transforms each element and returns a new array.)

**A41.** b) forEach() doesn't return, map() returns new array
(`forEach()` is used for side effects, `map()` creates and returns a new transformed array.)

**A42.** c) push()

**A43.** b) Return elements matching a condition
(`filter()` returns a new array with elements that pass the test condition.)

**A44.** b) Extracting values from objects/arrays into variables
```javascript
const {name, age} = person;
const [first, second] = array;
```

### Displaying Data in LWC

**A45.** b) for:each

**A46.** b) for:key
(`for:each` requires both the array (`for:each={array}`) and a unique key (`for:key={item.id}`).)

**A47.** b) if:true renders when truthy, if:false when falsy
(`if:true` shows element when condition is truthy, `if:false` shows when falsy.)

**A48.** b) {propertyName}
(Curly braces are used for data binding in LWC templates.)

**A49.** b) Yes, with different item names
(Nested loops are supported but require different item names for each level.)

**A50.** b) Warning and potential rendering issues
(LWC will show a console warning and may have rendering/performance issues without unique keys.)

---

## Section B: Coding Answers (51-60)

**A51.**
```json
{"name": "Alice", "age": 25}
```

**A52.**
```apex
HttpRequest req = new HttpRequest();
```

**A53.**
```apex
req.setMethod('GET');
```

**A54.**
```apex
Map<String, Object> result = (Map<String, Object>) JSON.deserializeUntyped('{"name":"John"}');
```

**A55.**
```apex
@AuraEnabled
public static String getDataString() {
    return 'Hello';
}
```

**A56.**
```javascript
import getAccountData from '@salesforce/apex/AccountController.getAccountData';
```

**A57.**
```javascript
const activeData = data.filter(item => item.status === 'active');
```

**A58.**
```javascript
const names = arrayOfObjects.map(obj => obj.name);
```

**A59.**
```html
<p>{userName}</p>
```

**A60.**
```apex
try {
    HttpResponse res = http.send(req);
} catch (CalloutException e) {
    System.debug('Callout error: ' + e.getMessage());
}
```
