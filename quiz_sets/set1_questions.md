# Quiz Set 1: JSON Data Handling from APIs in LWC

## Instructions
- Total Questions: 59
- Difficulty Distribution: Easy (60%), Medium (35%), Hard (<5%)
- Answer all questions to the best of your ability
- For code questions, write concise, production-ready code

---

## JSON Fundamentals (Questions 1-10)

**Q1.** [Easy] What does JSON stand for?

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

**Q5.** [Medium] Is the following JSON valid? `{"name": "John", "age": 30,}`

**Q6.** [Medium] What is the difference between `null` and `undefined` in JSON context?

**Q7.** [Code] [Easy] Write a valid JSON object representing a person with name "Alice" and age 25.

**Q8.** [Medium] How do you represent a nested JSON object with a person having an address object containing city and zip code?

**Q9.** [Easy] Which of the following values is NOT allowed in JSON?
a) true
b) false
c) NaN
d) null

**Q10.** [Medium] Can JSON property names contain spaces?

---

## Basic HTTP Callout in Apex (Questions 11-16)

**Q11.** [Easy] Which Apex class is used to make HTTP callouts?
a) HTTPClient
b) Http
c) WebService
d) RestClient

**Q12.** [Easy] What method is used to set the endpoint URL in an HttpRequest?

**Q13.** [Code] [Easy] Write a single line to create an HttpRequest object in Apex.

**Q14.** [Medium] What are the valid HTTP methods you can set using setMethod()?

**Q15.** [Medium] Which method actually sends the HTTP request and returns a response?

**Q16.** [Easy] What two methods are commonly used to read data from an HttpResponse?

---

## JSON Parsing in Apex (Questions 17-24)

**Q17.** [Easy] Which method is used to convert a JSON string to an Apex object?

**Q18.** [Easy] Which method converts an Apex object to a JSON string?

**Q19.** [Code] [Medium] Write code to deserialize a JSON string `{"name":"John"}` into a Map<String, Object>.

**Q20.** [Medium] What is a wrapper class in the context of JSON parsing?

**Q21.** [Code] [Medium] Write a simple wrapper class for a JSON response containing "id" and "name" fields.

**Q22.** [Medium] How do you access an array element from a deserialized JSON object?

**Q23.** [Hard] What happens if you try to deserialize invalid JSON using JSON.deserialize()?

**Q24.** [Medium] Can you deserialize a JSON array directly into a List of wrapper objects?

---

## Apex Method Setup for LWC (Questions 25-30)

**Q25.** [Easy] What annotation makes an Apex method accessible from LWC?

**Q26.** [Easy] Must @AuraEnabled methods be static?

**Q27.** [Code] [Easy] Write the signature of a basic @AuraEnabled method that returns a String.

**Q28.** [Medium] What does the `cacheable=true` parameter do in @AuraEnabled methods?

**Q29.** [Medium] What data types can be returned from @AuraEnabled methods to LWC?

**Q30.** [Medium] Can you use instance methods with @AuraEnabled for LWC?

---

## Calling Apex from LWC (Questions 31-37)

**Q31.** [Easy] What keyword is used to import an Apex method in LWC JavaScript?

**Q32.** [Code] [Medium] Write an import statement to import a method named `getAccountData` from `AccountController` class.

**Q33.** [Easy] What are the two ways to call Apex methods from LWC?

**Q34.** [Medium] What does a promise `.then()` block handle?

**Q35.** [Medium] What does a promise `.catch()` block handle?

**Q36.** [Code] [Medium] Write a basic imperative Apex call using .then() and .catch() for a method `getData()`.

**Q37.** [Medium] What is the difference between `async/await` and `.then()/.catch()` patterns?

---

## Processing JSON Data in LWC JavaScript (Questions 38-44)

**Q38.** [Easy] How do you access a property named "firstName" from a JavaScript object?

**Q39.** [Easy] Which array method creates a new array with transformed elements?

**Q40.** [Medium] What is the difference between `forEach()` and `map()` array methods?

**Q41.** [Code] [Easy] Write code to filter an array `data` to get only items where `status === 'active'`.

**Q42.** [Medium] How do you assign data received from Apex to a reactive property in LWC?

**Q43.** [Medium] What happens to the UI when you update a reactive property?

**Q44.** [Code] [Medium] Write code to extract just the "name" field from an array of objects using map().

---

## Displaying Data in LWC (Questions 45-50)

**Q45.** [Easy] Which directive is used to iterate over an array in LWC template?

**Q46.** [Easy] What attribute must be specified when using `for:each`?

**Q47.** [Code] [Easy] Write template syntax to display a list item's `name` property in a for:each loop.

**Q48.** [Medium] What's the difference between `if:true` and `if:false` directives?

**Q49.** [Medium] How do you bind a JavaScript property to display in the HTML template?

**Q50.** [Medium] Can you use nested `for:each` loops in LWC templates?

---

## Error Handling (Questions 51-54)

**Q51.** [Easy] Which Apex statement is used to catch exceptions?

**Q52.** [Code] [Medium] Write a try-catch block in Apex to handle a callout exception.

**Q53.** [Medium] What HTTP status code indicates a successful request?

**Q54.** [Medium] How do you display an error message from a .catch() block in LWC?

---

## Reactive Properties (Questions 55-57)

**Q55.** [Easy] What decorator is used to make a property public in LWC?

**Q56.** [Medium] When should you use the @track decorator in modern LWC?

**Q57.** [Medium] Do you need @track for objects and arrays in modern LWC?

---

## Practical Application (Questions 58-59)

**Q58.** [Hard] Describe the complete flow of data from an external API to displaying it in an LWC component.

**Q59.** [Medium] How would you implement a refresh button that fetches new data from an API?
