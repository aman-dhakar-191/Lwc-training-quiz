# Quiz Set 3: Answers - JSON Data Handling from APIs in LWC

---

## Section A: Multiple Choice Answers (1-50)

### JSON Fundamentals

**A1.** c) Can be either object or array
(A JSON document can have an object `{}` or array `[]` as root.)

**A2.** b) Colon

**A3.** b) []

**A4.** b) Yes, null is valid
(`null` is a valid JSON value for any property.)

**A5.** b) Key 'name' needs quotes
(All JSON keys must be strings in double quotes: `{"name": "John", "age": 30}`)

**A6.** b) Yes, nested arrays are valid
```json
[[1, 2], [3, 4], [5, 6]]
```

**A7.** b) null
(`null` is the JSON representation of "no data".)

**A8.** c) No fixed limit (implementation dependent)
(JSON specification has no depth limit, but implementations may have practical limits.)

**A9.** b) Yes
(`"Name"` and `"name"` are different properties.)

**A10.** a) "line1\nline2"
(Use `\n` for newline in JSON strings.)

### Basic HTTP Callout in Apex

**A11.** c) 404

**A12.** b) 200
(Status code 200 OK indicates success.)

**A13.** b) GET retrieves data, POST sends/creates data
(GET is for reading, POST for creating/sending data.)

**A14.** b) Yes, using setHeader()
```apex
req.setHeader('Authorization', 'Bearer token');
```

**A15.** b) Unauthorized endpoint error
(Callout will fail with unauthorized endpoint exception.)

**A16.** b) Http.send(HttpRequest)
```apex
Http http = new Http();
HttpResponse res = http.send(req);
```

### JSON Parsing in Apex

**A17.** b) Deserialize to List<WrapperClass>
```apex
List<MyClass> items = (List<MyClass>) JSON.deserialize(jsonString, List<MyClass>.class);
```

**A18.** b) Ignored by default (unless using deserializeStrict)
(`JSON.deserialize()` ignores extra properties by default.)

**A19.** b) Yes, automatically serializes
(SObjects can be serialized, though it includes all fields.)

**A20.** b) Use @JsonAccess or create specific wrapper
(@JsonAccess controls which fields are serialized.)

**A21.** b) Use Object type and check instanceof
```apex
Object dataField = jsonMap.get('data');
if (dataField instanceof String) {
    // Handle as string
} else if (dataField instanceof Map<String, Object>) {
    // Handle as object
}
```

**A22.** b) Excludes field from serialization
(`transient` keyword prevents field from being serialized.)

**A23.** b) Yes, both automatically
(Both List and Map types are handled automatically.)

**A24.** b) Use nested List in wrapper class
```apex
public class Wrapper {
    public List<List<Integer>> nestedArray;
}
```

### Apex Method Setup for LWC

**A25.** b) @AuraEnabled(cacheable=true)

**A26.** b) No, read-only operations only
(Cacheable methods cannot perform DML or other data modifications.)

**A27.** b) Parameters automatically deserialized from LWC
(No special annotation needed, automatic deserialization from JavaScript.)

**A28.** b) Throw AuraHandledException
```apex
throw new AuraHandledException('Error message');
```

**A29.** b) Yes, can call any method
(@AuraEnabled methods can call other methods internally.)

**A30.** b) void

### Calling Apex from LWC

**A31.** b) .then().catch()
(Standard promise pattern for handling success and errors.)

**A32.** b) @wire for reactive data, imperative for user actions
(@wire for automatic updates, imperative for button clicks and user-triggered actions.)

**A33.** b) Yes, both ways work
(Cacheable methods can be called with @wire or imperatively.)

**A34.** b) A function that returns Promise
(Import returns a function that when called returns a Promise.)

**A35.** b) Pass as JavaScript array, auto-converts to List
(JavaScript arrays automatically convert to Apex Lists.)

**A36.** b) Results can be shared across components
(Framework can cache and reuse results across component instances.)

**A37.** b) Yes, import from multiple classes
```javascript
import method1 from '@salesforce/apex/Class1.method1';
import method2 from '@salesforce/apex/Class2.method2';
```

**A38.** b) Use refreshApex() function
```javascript
import { refreshApex } from '@salesforce/apex';
refreshApex(this.wiredResult);
```

### Processing JSON Data in LWC JavaScript

**A39.** c) pop()

**A40.** b) find() returns first match, filter() returns all matches
(`find()` returns single element or undefined, `filter()` returns array.)

**A41.** b) array.length

**A42.** b) If all elements pass condition
```javascript
const allActive = items.every(item => item.active === true);
```

**A43.** b) {...object} or Object.assign()
```javascript
const copy1 = {...originalObject};
const copy2 = Object.assign({}, originalObject);
```

**A44.** b) Creates array from array-like or iterable
```javascript
const arr = Array.from('hello'); // ['h','e','l','l','o']
```

**A45.** b) array.sort((a, b) => a - b)
(Plain `sort()` treats numbers as strings; comparator needed for numeric sort.)

### Displaying Data in LWC

**A46.** a) {object.nested.property}

**A47.** b) Use @api property on child
```javascript
// Child: @api recordId;
// Parent: <c-child record-id={parentRecordId}></c-child>
```

**A48.** b) Yes, limited expressions like ternary
```html
<div>{isActive ? 'Active' : 'Inactive'}</div>
```

**A49.** b) Use if:true/if:false to check
```html
<template if:true={data}>...</template>
<template if:false={data}>No data</template>
```

**A50.** b) Conditional rendering (newer syntax)
(`lwc:if`, `lwc:elseif`, `lwc:else` are newer conditional directives.)

---

## Section B: Coding Answers (51-60)

**A51.**
```json
{"active": true, "count": 5}
```

**A52.**
```apex
HttpRequest req = new HttpRequest();
req.setEndpoint('https://api.example.com/data');
```

**A53.**
```apex
Map<String, Object> dataMap = new Map<String, Object>{'key' => 'value'};
String json = JSON.serialize(dataMap);
```

**A54.**
```apex
public class UserWrapper {
    public UserDetail user;
    
    public class UserDetail {
        public Integer id;
        public String name;
    }
}
```

**A55.**
```apex
@AuraEnabled
public static List<String> getNames() {
    return new List<String>{'Alice', 'Bob', 'Charlie'};
}
```

**A56.**
```javascript
processData({ name: 'John', age: 30 })
    .then(result => { this.result = result; })
    .catch(error => { this.error = error; });
```

**A57.**
```javascript
const exists = array.includes('test');
```

**A58.**
```javascript
get fullName() {
    return `${this.firstName} ${this.lastName}`;
}
```

**A59.**
```html
<template for:each={items} for:item="item" for:key={item.id}>
    <li>{item.name}</li>
</template>
```

**A60.**
```javascript
getData()
    .then(result => {
        this.data = result;
        this.error = undefined;
    })
    .catch(error => {
        this.error = error.body.message;
        this.data = undefined;
    });
```
