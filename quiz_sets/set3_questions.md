# Quiz Set 3: JSON Data Handling from APIs in LWC

## Instructions
- Total Questions: 59
- Difficulty Distribution: Easy (60%), Medium (35%), Hard (<5%)
- Answer all questions to the best of your ability
- For code questions, write concise, production-ready code

---

## JSON Fundamentals (Questions 1-10)

**Q1.** [Easy] What encoding is JSON always based on?
a) ASCII
b) UTF-8
c) UTF-16
d) ISO-8859-1

**Q2.** [Easy] Can JSON contain comments?

**Q3.** [Code] [Easy] Write a JSON object with two properties: `active` (boolean true) and `count` (number 5).

**Q4.** [Medium] How do you represent an empty array in JSON?

**Q5.** [Easy] Which character is used to separate a key from its value in JSON?

**Q6.** [Medium] Is `{"name": null}` valid JSON?

**Q7.** [Easy] What is the root element of a JSON document?
a) Must be an object
b) Must be an array
c) Can be either object or array
d) Must be a string

**Q8.** [Medium] Can you have a JSON array containing different data types?

**Q9.** [Medium] What's wrong with this JSON: `{name: "John", "age": 30}`?

**Q10.** [Easy] How do you escape a double quote inside a JSON string value?

---

## Basic HTTP Callout in Apex (Questions 11-16)

**Q11.** [Easy] What permission is required in a profile to make HTTP callouts?

**Q12.** [Medium] What is a Named Credential and why is it useful?

**Q13.** [Code] [Medium] Write code to set a request header "Authorization" with value "Bearer token123".

**Q14.** [Medium] What's the maximum size of an HTTP response body in Salesforce?

**Q15.** [Easy] Which class represents the HTTP response in Apex?

**Q16.** [Medium] How can you debug HTTP callout requests and responses?

---

## JSON Parsing in Apex (Questions 17-24)

**Q17.** [Easy] What method converts JSON string containing an array to Apex List?

**Q18.** [Medium] How do you handle date/datetime values in JSON responses?

**Q19.** [Code] [Easy] Write code to convert a simple Map to JSON string.

**Q20.** [Medium] What's the purpose of the @JsonAccess annotation in Apex?

**Q21.** [Medium] How do you ignore unknown JSON properties during deserialization?

**Q22.** [Code] [Medium] Write a wrapper class for: `{"success": true, "data": [1, 2, 3]}`.

**Q23.** [Hard] How do you handle polymorphic JSON (different structures for same field)?

**Q24.** [Medium] What's the difference between serializing and pretty-printing JSON?

---

## Apex Method Setup for LWC (Questions 25-30)

**Q25.** [Easy] Can you have multiple @AuraEnabled methods in one Apex class?

**Q26.** [Medium] What's the best practice for handling exceptions in @AuraEnabled methods?

**Q27.** [Code] [Easy] Write an @AuraEnabled method that returns a List of Strings.

**Q28.** [Medium] Can @AuraEnabled methods use platform caching?

**Q29.** [Medium] What happens if an @AuraEnabled method takes too long to execute?

**Q30.** [Easy] Must @AuraEnabled methods have a return value?

---

## Calling Apex from LWC (Questions 31-37)

**Q31.** [Easy] How many Apex methods can you import in a single LWC component?

**Q32.** [Medium] What is the return type of an imported Apex method in JavaScript?

**Q33.** [Code] [Medium] Write code to call an Apex method with two parameters: name and age.

**Q34.** [Medium] Can you use @wire with methods that have parameters?

**Q35.** [Medium] How do you cancel an in-flight Apex call?

**Q36.** [Easy] What does the @wire decorator do?

**Q37.** [Medium] What's the difference between cacheable and non-cacheable Apex methods for LWC?

---

## Processing JSON Data in LWC JavaScript (Questions 38-44)

**Q38.** [Code] [Easy] Write code to get the length of an array.

**Q39.** [Medium] How do you check if a property exists in an object?

**Q40.** [Medium] What's the purpose of the `some()` array method?

**Q41.** [Code] [Medium] Write code to get unique values from an array of numbers.

**Q42.** [Medium] How do you safely access nested properties that might not exist?

**Q43.** [Medium] What's the difference between `null` and `undefined` in JavaScript?

**Q44.** [Easy] Which method converts a JavaScript object to a JSON string?

---

## Displaying Data in LWC (Questions 45-50)

**Q45.** [Code] [Easy] Write template code to display a property named `userName`.

**Q46.** [Medium] How do you add CSS classes conditionally in LWC templates?

**Q47.** [Medium] Can you use template if:true and for:each on the same element?

**Q48.** [Easy] What iterator directive can be used as an alternative to for:each?

**Q49.** [Medium] How do you handle click events on dynamically rendered items?

**Q50.** [Code] [Medium] Write a getter that returns a computed value from two properties.

---

## Error Handling (Questions 51-54)

**Q51.** [Easy] What HTTP status codes indicate client errors?

**Q52.** [Medium] How do you log errors in LWC for debugging?

**Q53.** [Code] [Medium] Write Apex code to check HTTP response status and throw error if not 200.

**Q54.** [Medium] What's the best way to display user-friendly error messages in LWC?

---

## Reactive Properties (Questions 55-57)

**Q55.** [Code] [Easy] Write code to declare a tracked array property.

**Q56.** [Medium] What happens when you modify an array element directly?

**Q57.** [Medium] How do you make a property reactive to changes from parent component?

---

## Practical Application (Questions 58-59)

**Q58.** [Hard] Design a solution to handle API rate limiting when making multiple callouts from LWC.

**Q59.** [Medium] How would you implement a search-as-you-type feature that calls an API endpoint?
