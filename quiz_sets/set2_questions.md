# Quiz Set 2: JSON Data Handling from APIs in LWC

## Instructions
- Total Questions: 59
- Difficulty Distribution: Easy (60%), Medium (35%), Hard (<5%)
- Answer all questions to the best of your ability
- For code questions, write concise, production-ready code

---

## JSON Fundamentals (Questions 1-10)

**Q1.** [Easy] What is the file extension for JSON files?

**Q2.** [Easy] Which character separates key-value pairs in a JSON object?
a) Semicolon (;)
b) Comma (,)
c) Pipe (|)
d) Colon (:)

**Q3.** [Medium] What is the maximum nesting depth recommended for JSON objects?

**Q4.** [Easy] Can a JSON object have duplicate keys?

**Q5.** [Easy] Which of these is a valid JSON number?
a) 0xFF
b) 3.14
c) Infinity
d) 0x10

**Q6.** [Code] [Easy] Write a JSON array containing three numbers: 1, 2, and 3.

**Q7.** [Medium] How do you represent a boolean false value in JSON?

**Q8.** [Medium] Is whitespace significant in JSON?

**Q9.** [Easy] Can JSON keys be numbers?

**Q10.** [Medium] What's the difference between an empty object `{}` and null in JSON?

---

## Basic HTTP Callout in Apex (Questions 11-16)

**Q11.** [Easy] What Salesforce setting must be configured before making HTTP callouts?

**Q12.** [Code] [Easy] Write code to set an HTTP method to GET.

**Q13.** [Medium] What is the default timeout for HTTP callouts in Salesforce?

**Q14.** [Medium] How do you set a custom timeout for an HTTP request?

**Q15.** [Easy] What happens if you don't call Http.send()?

**Q16.** [Medium] Can you make HTTP callouts from triggers directly?

---

## JSON Parsing in Apex (Questions 17-24)

**Q17.** [Easy] What does JSON.deserializeUntyped() return?

**Q18.** [Code] [Easy] Write code to serialize a List of Strings to JSON.

**Q19.** [Medium] How do you handle null values in JSON deserialization?

**Q20.** [Medium] What's the difference between JSON.deserialize() and JSON.deserializeUntyped()?

**Q21.** [Code] [Medium] Write a wrapper class for JSON with nested object: `{"user": {"id": 1, "name": "John"}}`.

**Q22.** [Medium] How do you parse a JSON array of strings in Apex?

**Q23.** [Medium] What is JSON.deserializeStrict() used for?

**Q24.** [Hard] How do you handle dynamic JSON keys that you don't know in advance?

---

## Apex Method Setup for LWC (Questions 25-30)

**Q25.** [Easy] Can @AuraEnabled methods have parameters?

**Q26.** [Code] [Medium] Write an @AuraEnabled method that accepts a String parameter and returns an Integer.

**Q27.** [Medium] What's the difference between @AuraEnabled and @AuraEnabled(cacheable=true)?

**Q28.** [Easy] Can you use @AuraEnabled on private methods?

**Q29.** [Medium] What types of exceptions can be thrown from @AuraEnabled methods?

**Q30.** [Medium] Do @AuraEnabled methods count against Apex CPU time limits?

---

## Calling Apex from LWC (Questions 31-37)

**Q31.** [Easy] What namespace is used to import Apex methods in LWC?

**Q32.** [Medium] Can you call multiple Apex methods simultaneously from LWC?

**Q33.** [Code] [Medium] Write code to call an Apex method using async/await pattern with error handling.

**Q34.** [Medium] What is the advantage of using @wire over imperative calls?

**Q35.** [Easy] What happens when an Apex method throws an exception?

**Q36.** [Medium] Can you pass complex objects as parameters to Apex methods from LWC?

**Q37.** [Medium] How do you handle loading states while waiting for Apex response?

---

## Processing JSON Data in LWC JavaScript (Questions 38-44)

**Q38.** [Easy] Which method adds an element to the end of an array?

**Q39.** [Code] [Easy] Write code to check if an array contains a specific value.

**Q40.** [Medium] What's the difference between `find()` and `filter()` methods?

**Q41.** [Medium] How do you sort an array of objects by a specific property?

**Q42.** [Code] [Medium] Write code to sum all values in an array of numbers using reduce().

**Q43.** [Medium] How do you create a shallow copy of an array in JavaScript?

**Q44.** [Medium] What is destructuring and how is it useful with JSON data?

---

## Displaying Data in LWC (Questions 45-50)

**Q45.** [Easy] What attribute is used for unique identification in for:each?

**Q46.** [Code] [Easy] Write template code to conditionally show a div when `hasData` is true.

**Q47.** [Medium] How do you display a formatted date from a JavaScript Date object in template?

**Q48.** [Medium] Can you use JavaScript expressions directly in LWC templates?

**Q49.** [Easy] What happens if you don't provide a for:key in for:each?

**Q50.** [Medium] How do you handle empty arrays in templates?

---

## Error Handling (Questions 51-54)

**Q51.** [Code] [Medium] Write Apex code to return a custom error message to LWC.

**Q52.** [Medium] What information is available in the error object in LWC .catch() block?

**Q53.** [Easy] What HTTP status code indicates "Not Found"?

**Q54.** [Medium] How do you differentiate between different types of errors in LWC?

---

## Reactive Properties (Questions 55-57)

**Q55.** [Easy] Are primitive properties (String, Number, Boolean) automatically tracked in LWC?

**Q56.** [Medium] How do you force a component to re-render when data changes?

**Q57.** [Code] [Easy] Write code to declare a public property named 'recordId'.

---

## Practical Application (Questions 58-59)

**Q58.** [Hard] Design a complete LWC component that fetches weather data from an API and displays temperature, handling errors appropriately.

**Q59.** [Medium] How would you implement pagination for API results in LWC?
