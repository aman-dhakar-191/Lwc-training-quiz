# Quiz Set 3: JSON Data Handling from APIs in LWC

## Instructions
- Total Questions: 60 (50 Multiple Choice + 10 Coding)
- Difficulty Distribution: Easy (60%), Medium (35%), Hard (<5%)
- For multiple choice questions, select the best answer(s)
- For coding questions, write concise, production-ready code

---

## Section A: Multiple Choice Questions (1-50)

### JSON Fundamentals

**Q1.** [Easy] What is the root element of a JSON document?
a) Must be an object
b) Must be an array
c) Can be either object or array
d) Must be a string

**Q2.** [Easy] Which character is used to separate a key from its value in JSON?
a) Comma
b) Colon
c) Semicolon
d) Equals

**Q3.** [Medium] How do you represent an empty array in JSON?
a) null
b) []
c) {}
d) ""

**Q4.** [Easy] Is `{"name": null}` valid JSON?
a) No, null not allowed
b) Yes, null is valid
c) Only in JavaScript
d) Depends on parser

**Q5.** [Medium] What's wrong with this JSON: `{name: "John", "age": 30}`?
a) Nothing wrong
b) Key 'name' needs quotes
c) Age should be string
d) Missing brackets

**Q6.** [Easy] Can you have a JSON array of arrays?
a) No, not allowed
b) Yes, nested arrays are valid
c) Only two levels deep
d) Only with objects

**Q7.** [Medium] Which JSON value represents "no data"?
a) empty string ""
b) null
c) undefined
d) void

**Q8.** [Easy] What is the maximum nesting depth for JSON?
a) 10 levels
b) 100 levels
c) No fixed limit (implementation dependent)
d) 5 levels

**Q9.** [Medium] Are JSON property names case-sensitive?
a) No
b) Yes
c) Depends on language
d) Only for strings

**Q10.** [Easy] Which is correct JSON syntax for a string with newline?
a) "line1\nline2"
b) "line1
line2"
c) 'line1\nline2'
d) "line1\\nline2"

### Basic HTTP Callout in Apex

**Q11.** [Medium] What HTTP status code indicates "Not Found"?
a) 400
b) 401
c) 404
d) 500

**Q12.** [Easy] What HTTP status code indicates success?
a) 100
b) 200
c) 300
d) 400

**Q13.** [Medium] What's the difference between GET and POST HTTP methods?
a) No difference
b) GET retrieves data, POST sends/creates data
c) GET is faster
d) POST is deprecated

**Q14.** [Easy] Can you set custom headers in HttpRequest?
a) No
b) Yes, using setHeader()
c) Only Content-Type
d) Only Authorization

**Q15.** [Medium] What happens if callout endpoint is not in Remote Site Settings?
a) Works fine
b) Unauthorized endpoint error
c) Timeout
d) Returns null

**Q16.** [Easy] Which method sends the actual HTTP request?
a) HttpRequest.send()
b) Http.send(HttpRequest)
c) HttpRequest.execute()
d) Http.call()

### JSON Parsing in Apex

**Q17.** [Medium] How do you handle a JSON array at the root level?
a) Cannot be done
b) Deserialize to List<WrapperClass>
c) Only with Map
d) Convert to object first

**Q18.** [Medium] What happens to extra JSON properties not in wrapper class?
a) Error thrown
b) Ignored by default (unless using deserializeStrict)
c) Stored separately
d) Must be removed

**Q19.** [Easy] Can JSON.serialize() handle Salesforce SObjects?
a) No, not supported
b) Yes, automatically serializes
c) Only standard objects
d) Only custom objects

**Q20.** [Medium] How do you serialize only specific fields of an object?
a) Cannot do it
b) Use @JsonAccess or create specific wrapper
c) Use JSON.filter()
d) Modify object first

**Q21.** [Hard] How do you handle polymorphic JSON where a field can be string or object?
a) Not possible
b) Use Object type and check instanceof
c) Always use String
d) Create two wrapper classes

**Q22.** [Medium] What's the use of transient keyword with JSON serialization?
a) Makes it faster
b) Excludes field from serialization
c) Includes field
d) No effect

**Q23.** [Easy] Does JSON.serialize() handle List and Map types?
a) No
b) Yes, both automatically
c) Only List
d) Only Map

**Q24.** [Medium] How do you parse nested arrays in JSON?
a) Flatten first
b) Use nested List in wrapper class
c) Not possible
d) Use Map only

### Apex Method Setup for LWC

**Q25.** [Easy] What's the syntax for cacheable @AuraEnabled method?
a) @AuraEnabled public
b) @AuraEnabled(cacheable=true)
c) @AuraEnabled(cache=true)
d) @Cache @AuraEnabled

**Q26.** [Medium] Can cacheable methods modify data (DML)?
a) Yes, no restrictions
b) No, read-only operations only
c) Only inserts
d) Only updates

**Q27.** [Easy] What's required for @AuraEnabled method with parameters?
a) Nothing special
b) Parameters automatically deserialized from LWC
c) Must use @Param annotation
d) Parameters must be strings

**Q28.** [Medium] How do you return an error message from Apex to LWC?
a) Return null
b) Throw AuraHandledException
c) Use System.debug()
d) Cannot return errors

**Q29.** [Medium] Can @AuraEnabled methods call other methods?
a) No
b) Yes, can call any method
c) Only static methods
d) Only public methods

**Q30.** [Easy] What return type should be used for no return data?
a) null
b) void
c) String
d) Object

### Calling Apex from LWC

**Q31.** [Easy] What's the pattern for imperative Apex call error handling?
a) if-else
b) .then().catch()
c) try-catch only
d) No error handling needed

**Q32.** [Medium] When should you use @wire vs imperative calls?
a) Always use @wire
b) @wire for reactive data, imperative for user actions
c) Always use imperative
d) No difference

**Q33.** [Medium] Can you call cacheable methods imperatively?
a) No, only with @wire
b) Yes, both ways work
c) Only in production
d) Deprecated approach

**Q34.** [Easy] What does importing an Apex method return?
a) The actual method
b) A function that returns Promise
c) A Promise directly
d) An Observable

**Q35.** [Medium] How do you pass an array as parameter to Apex?
a) Cannot pass arrays
b) Pass as JavaScript array, auto-converts to List
c) Convert to string first
d) Only individual elements

**Q36.** [Medium] What's the advantage of cacheable Apex methods?
a) Faster execution
b) Results can be shared across components
c) No governor limits
d) Can modify data

**Q37.** [Easy] Can LWC call Apex methods from different classes?
a) No, only one class
b) Yes, import from multiple classes
c) Maximum two classes
d) Only same namespace

**Q38.** [Medium] How do you refresh wired data?
a) Cannot refresh
b) Use refreshApex() function
c) Reload page
d) Call again imperatively

### Processing JSON Data in LWC JavaScript

**Q39.** [Easy] What method removes last element from array?
a) removeLast()
b) delete()
c) pop()
d) splice()

**Q40.** [Medium] What's the difference between `find()` and `filter()`?
a) Same thing
b) find() returns first match, filter() returns all matches
c) filter() is faster
d) find() modifies array

**Q41.** [Easy] How do you get array length?
a) array.size
b) array.length
c) array.count()
d) array.size()

**Q42.** [Medium] What does `every()` array method test?
a) If any element passes
b) If all elements pass condition
c) If no elements pass
d) Count of passing elements

**Q43.** [Medium] How do you create a shallow copy of an object?
a) object.copy()
b) {...object} or Object.assign()
c) object.clone()
d) JSON.parse(JSON.stringify())

**Q44.** [Medium] What's the purpose of Array.from()?
a) Deletes array
b) Creates array from array-like or iterable
c) Converts to string
d) Validates array

**Q45.** [Easy] How do you sort an array of numbers?
a) array.sort()
b) array.sort((a, b) => a - b)
c) Array.sort(array)
d) array.sortNumbers()

### Displaying Data in LWC

**Q46.** [Easy] What's the syntax for accessing nested property in template?
a) {object.nested.property}
b) {object[nested][property]}
c) {object->nested->property}
d) {object::nested::property}

**Q47.** [Medium] How do you pass data to a child component?
a) Cannot pass data
b) Use @api property on child
c) Use event only
d) Use state management

**Q48.** [Medium] Can you use JavaScript expressions in templates?
a) No
b) Yes, limited expressions like ternary
c) Yes, any expression
d) Only variables

**Q49.** [Easy] How do you handle empty data in templates?
a) Always shows error
b) Use if:true/if:false to check
c) Automatic handling
d) Not possible

**Q50.** [Medium] What's the purpose of lwc:if directive?
a) Deprecated
b) Conditional rendering (newer syntax)
c) Loop directive
d) Event handler

---

## Section B: Coding Questions (51-60)

**Q51.** [Code] [Easy] Write a JSON object with two properties: `active` (boolean true) and `count` (number 5).

**Q52.** [Code] [Easy] Write code to create an HttpRequest and set endpoint to 'https://api.example.com/data'.

**Q53.** [Code] [Easy] Write code to convert a Map to JSON string in Apex.

**Q54.** [Code] [Medium] Write a wrapper class for: `{"user": {"id": 1, "name": "John"}}`.

**Q55.** [Code] [Easy] Write an @AuraEnabled method that returns a List of Strings.

**Q56.** [Code] [Medium] Write code to call an Apex method with parameters name='John' and age=30.

**Q57.** [Code] [Easy] Write code to check if an array includes the value 'test'.

**Q58.** [Code] [Medium] Write a getter that returns full name from firstName and lastName properties.

**Q59.** [Code] [Easy] Write template code to display a list item's `name` property in a for:each loop.

**Q60.** [Code] [Medium] Write code to handle error from Apex call and store error message.
