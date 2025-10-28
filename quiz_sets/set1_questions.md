# Quiz Set 1: JSON Data Handling from APIs in LWC

## Instructions
- Total Questions: 60 (50 Multiple Choice + 10 Coding)
- Difficulty Distribution: Easy (60%), Medium (35%), Hard (<5%)
- For multiple choice questions, select the best answer(s)
- For coding questions, write concise, production-ready code

---

## Section A: Multiple Choice Questions (1-50)

### JSON Fundamentals

**Q1.** [Easy] What does JSON stand for?
a) Java Standard Object Notation
b) JavaScript Object Notation
c) Java Serialized Object Notation
d) JavaScript Ordered Notation

**Q2.** [Easy] Which of the following is a valid JSON data type?
a) Function
b) String
c) Undefined
d) Date

**Q3.** [Easy] What is the correct syntax for a JSON object?
a) {key: value}
b) {"key": "value"}
c) [key: value]
d) <key>value</key>

**Q4.** [Easy] In JSON, which symbol is used to represent an array?
a) {}
b) []
c) ()
d) <>

**Q5.** [Easy] Which of the following values is NOT allowed in JSON?
a) true
b) false
c) NaN
d) null

**Q6.** [Easy] What character separates key-value pairs in a JSON object?
a) Semicolon (;)
b) Comma (,)
c) Pipe (|)
d) Colon (:) for key-value, comma (,) for pairs

**Q7.** [Medium] Is the following JSON valid? `{"name": "John", "age": 30,}`
a) Yes, it's valid
b) No, trailing commas are not allowed
c) Yes, but only in JavaScript
d) No, the age should be a string

**Q8.** [Medium] What is the difference between `null` and `undefined` in JSON context?
a) They are the same
b) JSON supports both equally
c) JSON only supports null, not undefined
d) JSON only supports undefined, not null

**Q9.** [Medium] Can JSON property names contain spaces?
a) No, never
b) Yes, but they must be in double quotes
c) Yes, without quotes
d) Only in arrays

**Q10.** [Easy] How do you escape a double quote inside a JSON string value?
a) \'
b) \"
c) ""
d) //

### Basic HTTP Callout in Apex

**Q11.** [Easy] Which Apex class is used to make HTTP callouts?
a) HTTPClient
b) Http
c) WebService
d) RestClient

**Q12.** [Easy] What method is used to set the endpoint URL in an HttpRequest?
a) setURL()
b) setEndpoint()
c) setDestination()
d) setTarget()

**Q13.** [Easy] What class represents the HTTP response in Apex?
a) Response
b) HttpResponse
c) CalloutResponse
d) RestResponse

**Q14.** [Medium] What Salesforce setting must be configured before making HTTP callouts?
a) Remote Site Settings
b) CORS Settings
c) API Settings
d) Security Settings

**Q15.** [Medium] What is the default timeout for HTTP callouts in Salesforce?
a) 60 seconds
b) 90 seconds
c) 120 seconds
d) 180 seconds

**Q16.** [Easy] What two methods are commonly used to read data from an HttpResponse? (Select 2)
a) getBody()
b) getData()
c) getStatusCode()
d) getContent()

### JSON Parsing in Apex

**Q17.** [Easy] Which method is used to convert a JSON string to an Apex object?
a) JSON.parse()
b) JSON.deserialize()
c) JSON.decode()
d) JSON.convert()

**Q18.** [Easy] Which method converts an Apex object to a JSON string?
a) JSON.stringify()
b) JSON.serialize()
c) JSON.encode()
d) JSON.convert()

**Q19.** [Medium] What does JSON.deserializeUntyped() return?
a) A String
b) An Object that can be cast to Map or List
c) A specific Apex class instance
d) null

**Q20.** [Medium] What is a wrapper class in the context of JSON parsing?
a) A class that wraps HTTP requests
b) An Apex class that mirrors JSON structure
c) A class that handles errors
d) A class that validates JSON

**Q21.** [Medium] What's the difference between JSON.deserialize() and JSON.deserializeUntyped()?
a) They are the same
b) deserialize() requires a specific type, deserializeUntyped() returns Object
c) deserializeUntyped() is faster
d) deserialize() only works with arrays

**Q22.** [Medium] What happens if you try to deserialize invalid JSON using JSON.deserialize()?
a) Returns null
b) Returns empty object
c) Throws JSONException
d) Silently fails

**Q23.** [Easy] Can you deserialize a JSON array directly into a List of wrapper objects?
a) No, not possible
b) Yes, using JSON.deserialize()
c) Only with JSON.deserializeUntyped()
d) Only for primitive types

**Q24.** [Medium] How do you handle null values in JSON deserialization?
a) They cause errors
b) They are automatically mapped to null in Apex
c) They must be removed first
d) Convert them to empty strings

### Apex Method Setup for LWC

**Q25.** [Easy] What annotation makes an Apex method accessible from LWC?
a) @AuraEnabled
b) @LWCEnabled
c) @RemoteAction
d) @WebService

**Q26.** [Easy] Must @AuraEnabled methods be static for LWC?
a) No, they can be instance methods
b) Yes, they must be static
c) Only for cacheable methods
d) Depends on the context

**Q27.** [Medium] What does the `cacheable=true` parameter do in @AuraEnabled methods?
a) Caches data on the server permanently
b) Allows LWC to cache results for performance
c) Prevents multiple calls
d) Stores data in browser localStorage

**Q28.** [Medium] What data types can be returned from @AuraEnabled methods to LWC?
a) Only primitives
b) Only custom objects
c) Primitives, Lists, Maps, and custom classes
d) Only strings and integers

**Q29.** [Easy] Can @AuraEnabled methods have parameters?
a) No
b) Yes, parameters are automatically deserialized
c) Only primitive parameters
d) Only one parameter allowed

**Q30.** [Medium] Can you use @AuraEnabled on private methods?
a) Yes, privacy doesn't matter
b) No, they must be public or global
c) Only for cacheable methods
d) Only in test classes

### Calling Apex from LWC

**Q31.** [Easy] What keyword is used to import an Apex method in LWC JavaScript?
a) require
b) include
c) import
d) use

**Q32.** [Easy] What namespace is used to import Apex methods in LWC?
a) @salesforce/apex
b) @apex
c) @salesforce/controller
d) @lwc/apex

**Q33.** [Easy] What are the two ways to call Apex methods from LWC?
a) Sync and async
b) Imperative and wire
c) Direct and indirect
d) Static and dynamic

**Q34.** [Medium] What does a promise `.then()` block handle?
a) Errors
b) Successful resolution and data
c) Loading state
d) Timeout

**Q35.** [Medium] What does a promise `.catch()` block handle?
a) Success
b) Errors or rejections
c) Loading state
d) Caching

**Q36.** [Medium] What is the return type of an imported Apex method in JavaScript?
a) The actual Apex return type
b) Always a Promise
c) Always a String
d) An Observable

**Q37.** [Medium] What is the advantage of using @wire over imperative calls?
a) It's faster
b) Automatic reactive parameter handling and caching
c) Allows DML operations
d) Works offline

**Q38.** [Medium] Can you call multiple Apex methods simultaneously from LWC?
a) No, only sequential
b) Yes, using Promise.all()
c) Only with @wire
d) Not recommended

### Processing JSON Data in LWC JavaScript

**Q39.** [Easy] How do you access a property named "firstName" from a JavaScript object?
a) object->firstName
b) object.firstName or object['firstName']
c) object::firstName
d) object#firstName

**Q40.** [Easy] Which array method creates a new array with transformed elements?
a) forEach()
b) filter()
c) map()
d) reduce()

**Q41.** [Medium] What's the difference between `forEach()` and `map()` array methods?
a) They are identical
b) forEach() doesn't return, map() returns new array
c) map() is slower
d) forEach() can modify the array

**Q42.** [Easy] Which method adds an element to the end of an array?
a) append()
b) add()
c) push()
d) insert()

**Q43.** [Medium] What's the purpose of the `filter()` array method?
a) Clean the array
b) Return elements matching a condition
c) Sort the array
d) Remove duplicates

**Q44.** [Medium] What is destructuring in JavaScript?
a) Deleting objects
b) Extracting values from objects/arrays into variables
c) Breaking loops
d) Error handling

### Displaying Data in LWC

**Q45.** [Easy] Which directive is used to iterate over an array in LWC template?
a) for:loop
b) for:each
c) repeat
d) iterate

**Q46.** [Easy] What attribute must be specified when using `for:each`?
a) for:id
b) for:key
c) for:index
d) for:item only

**Q47.** [Medium] What's the difference between `if:true` and `if:false` directives?
a) No difference
b) if:true renders when truthy, if:false when falsy
c) if:false is deprecated
d) They can't be used together

**Q48.** [Easy] How do you bind a JavaScript property to display in the HTML template?
a) ${propertyName}
b) {propertyName}
c) {{propertyName}}
d) [propertyName]

**Q49.** [Medium] Can you use nested `for:each` loops in LWC templates?
a) No, not supported
b) Yes, with different item names
c) Only two levels
d) Only with arrays

**Q50.** [Medium] What happens if you don't provide a for:key in for:each?
a) It works fine
b) Warning and potential rendering issues
c) Compilation error
d) Runtime error

---

## Section B: Coding Questions (51-60)

**Q51.** [Code] [Easy] Write a valid JSON object representing a person with name "Alice" and age 25.

**Q52.** [Code] [Easy] Write a single line to create an HttpRequest object in Apex.

**Q53.** [Code] [Easy] Write code to set an HTTP method to GET for a request object named `req`.

**Q54.** [Code] [Medium] Write code to deserialize a JSON string `{"name":"John"}` into a Map<String, Object>.

**Q55.** [Code] [Easy] Write the signature of a basic @AuraEnabled method that returns a String.

**Q56.** [Code] [Medium] Write an import statement to import a method named `getAccountData` from `AccountController` class.

**Q57.** [Code] [Easy] Write code to filter an array `data` to get only items where `status === 'active'`.

**Q58.** [Code] [Medium] Write code to extract just the "name" field from an array of objects using map().

**Q59.** [Code] [Easy] Write template syntax to display a property named `userName`.

**Q60.** [Code] [Medium] Write a try-catch block in Apex to handle a callout exception.
