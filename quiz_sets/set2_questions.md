# Quiz Set 2: JSON Data Handling from APIs in LWC

## Instructions
- Total Questions: 60 (50 Multiple Choice + 10 Coding)
- For multiple choice questions, select the best answer(s)
- For coding questions, write concise, production-ready code

---

## Section A: Multiple Choice Questions (1-50)

### JSON Fundamentals

**Q1.** What is the file extension for JSON files?  
a) .js  
b) .json  
c) .txt  
d) .data

**Q2.** Can a JSON object have duplicate keys?  
a) Yes, recommended  
b) No, never allowed  
c) Technically yes, but last value overwrites  
d) Only in arrays

**Q3.** Which of these is a valid JSON number?  
a) 0xFF  
b) 3.14  
c) Infinity  
d) 0x10

**Q4.** How do you represent a boolean false value in JSON?  
a) "false"  
b) false  
c) FALSE  
d) 0

**Q5.** Is whitespace significant in JSON?  
a) Yes, very important  
b) No, ignored by parsers  
c) Only in strings  
d) Only for formatting

**Q6.** Can JSON keys be numbers?  
a) Yes, numbers are fine  
b) No, keys must be strings in quotes  
c) Only in arrays  
d) Only positive integers

**Q7.** What encoding is JSON typically based on?  
a) ASCII  
b) UTF-8  
c) UTF-16  
d) ISO-8859-1

**Q8.** Can JSON contain comments?  
a) Yes, using //  
b) Yes, using /* */  
c) No, comments not supported  
d) Yes, using #

**Q9.** What's the difference between an empty object `{}` and null in JSON?  
a) They are the same  
b) {} is an object with no properties, null is absence of value  
c) null is invalid  
d) {} cannot be used

**Q10.** Can a JSON array contain different data types?  
a) No, must be homogeneous  
b) Yes, mixed types allowed  
c) Only primitives  
d) Only objects

### Basic HTTP Callout in Apex

**Q11.** What permission is needed to make HTTP callouts in Salesforce?  
a) System Administrator  
b) API Enabled permission  
c) Remote Site Settings configuration  
d) Custom permission set

**Q12.** What is a Named Credential in Salesforce?  
a) A type of user credential  
b) Stores endpoint URL and authentication in metadata  
c) A custom object  
d) A report type

**Q13.** What's the maximum size of an HTTP response body in Salesforce?  
a) 3 MB  
b) 6 MB for synchronous  
c) 10 MB  
d) Unlimited

**Q14.** How can you debug HTTP callout requests and responses?  
a) System.debug() only  
b) Debug logs in Developer Console  
c) Cannot debug callouts  
d) Email notifications

**Q15.** Can you make HTTP callouts from triggers directly?  
a) Yes, always  
b) No, must use @future or Queueable  
c) Only for GET requests  
d) Only in test methods

**Q16.** How do you set a custom timeout for an HTTP request?  
a) setTimeout()  
b) setTimeoutLimit()  
c) setTimeout(milliseconds)  
d) setMaxWait()

### JSON Parsing in Apex

**Q17.** What method converts a simple Map to JSON string?  
a) JSON.parse()  
b) JSON.serialize()  
c) JSON.encode()  
d) toString()

**Q18.** How do you handle date/datetime values in JSON responses?  
a) They convert automatically  
b) Parse as strings then convert to DateTime  
c) Use Date JSON type  
d) Not possible

**Q19.** What's the purpose of the @JsonAccess annotation in Apex?  
a) Controls method access  
b) Controls JSON serialization access for properties  
c) Enables JSON parsing  
d) Validates JSON

**Q20.** How do you ignore unknown JSON properties during deserialization?  
a) Use JSON.deserialize() (default behavior)  
b) Use JSON.deserializeStrict()  
c) Not possible  
d) Use try-catch

**Q21.** How do you handle dynamic JSON keys that you don't know in advance?  
a) Cannot be done  
b) Use JSON.deserializeUntyped() and iterate through keys  
c) Use wrapper classes  
d) Use JSON.parse()

**Q22.** What's the difference between serializing and pretty-printing JSON?  
a) No difference  
b) Pretty-printing adds whitespace for readability  
c) Pretty-printing is faster  
d) Serializing is deprecated

**Q23.** Can you parse a JSON array of strings in Apex?  
a) No, only objects  
b) Yes, using JSON.deserializeUntyped()  
c) Only with wrapper classes  
d) Not supported

**Q24.** What does JSON.deserializeStrict() do?  
a) Faster parsing  
b) Throws exception if JSON has extra properties  
c) Validates JSON syntax  
d) Same as deserialize()

### Apex Method Setup for LWC

**Q25.** Can you have multiple @AuraEnabled methods in one Apex class?  
a) No, only one  
b) Yes, unlimited  
c) Maximum of 10  
d) Only in controllers

**Q26.** What's the best practice for handling exceptions in @AuraEnabled methods?  
a) Let them throw naturally  
b) Use try-catch and throw AuraHandledException  
c) Return null  
d) Log and ignore

**Q27.** Can @AuraEnabled methods use platform caching?  
a) No, not compatible  
b) Yes, can use Platform Cache  
c) Only session cache  
d) Only org cache

**Q28.** Must @AuraEnabled methods have a return value?  
a) Yes, always  
b) No, can be void  
c) Only primitives  
d) Only objects

**Q29.** What happens if an @AuraEnabled method takes too long?  
a) Continues indefinitely  
b) Throws exception if exceeds governor limits  
c) Automatically caches  
d) Queues for later

**Q30.** Do @AuraEnabled methods count against Apex CPU time limits?  
a) No, exempt  
b) Yes, subject to governor limits  
c) Only synchronous ones  
d) Only cacheable ones

### Calling Apex from LWC

**Q31.** How many Apex methods can you import in a single LWC component?  
a) Only one  
b) Maximum 10  
c) No fixed limit  
d) Only from one class

**Q32.** What happens when an Apex method throws an exception in LWC?  
a) Component crashes  
b) Promise is rejected, control passes to .catch()  
c) Returns null  
d) Page reloads

**Q33.** Can you pass complex objects as parameters to Apex methods from LWC?  
a) No, only primitives  
b) Yes, automatically serialized to JSON  
c) Only arrays  
d) Only strings

**Q34.** How do you handle loading states while waiting for Apex response?  
a) Cannot track  
b) Use boolean property to track loading state  
c) Automatic  
d) Use @track only

**Q35.** What does the @wire decorator do?  
a) Makes methods asynchronous  
b) Provides reactive data binding  
c) Validates data  
d) Caches permanently

**Q36.** Can you use @wire with methods that have parameters?  
a) No, not supported  
b) Yes, parameters must be reactive properties  
c) Only one parameter  
d) Only string parameters

**Q37.** What's the difference between cacheable and non-cacheable Apex methods?  
a) No difference  
b) Cacheable are read-only and can be reused, non-cacheable fetch fresh data  
c) Cacheable are slower  
d) Non-cacheable cannot have parameters

**Q38.** How do you cancel an in-flight Apex call?  
a) Use cancel() method  
b) Cannot directly cancel once initiated  
c) Use stop()  
d) Close component

### Processing JSON Data in LWC JavaScript

**Q39.** Which method converts a JavaScript object to a JSON string?  
a) toString()  
b) JSON.parse()  
c) JSON.stringify()  
d) serialize()

**Q40.** How do you check if a property exists in an object?  
a) obj.prop === undefined  
b) hasOwnProperty() or 'prop' in obj  
c) typeof obj.prop  
d) Object.exists()

**Q41.** What's the purpose of the `some()` array method?  
a) Returns sum  
b) Tests if at least one element passes condition  
c) Returns some elements  
d) Sorts array

**Q42.** How do you safely access nested properties that might not exist?  
a) Try-catch  
b) Optional chaining (obj?.nested?.property)  
c) Check each level manually  
d) Both b and c

**Q43.** What's the difference between `null` and `undefined` in JavaScript?  
a) Same thing  
b) null is explicit "no value", undefined is unassigned  
c) null is faster  
d) undefined is deprecated

**Q44.** Which method checks if an array contains a specific value?  
a) contains()  
b) has()  
c) includes()  
d) find()

**Q45.** What does the `reduce()` array method do?  
a) Shrinks array  
b) Reduces to single value by applying function  
c) Filters elements  
d) Sorts array

### Displaying Data in LWC

**Q46.** What iterator directive can be used as alternative to for:each?  
a) for:loop  
b) iterator:it  
c) repeat  
d) while

**Q47.** How do you add CSS classes conditionally in LWC templates?  
a) Cannot do conditionally  
b) Use computed property that returns class name  
c) Use if:class  
d) Only with JavaScript

**Q48.** Can you use template if:true and for:each on the same element?  
a) Yes  
b) No, use nested template  
c) Only with iterator  
d) Only in production

**Q49.** How do you handle click events on dynamically rendered items?  
a) Cannot handle  
b) Use data attributes to store item info  
c) Use index only  
d) Separate handlers for each

**Q50.** How do you display a formatted date in LWC template?  
a) Use <date> tag  
b) Format in JavaScript getter first  
c) Automatic formatting  
d) Use date filter

---

## Section B: Coding Questions (51-60)

**Q51.** Write a JSON array containing three numbers: 1, 2, and 3.

**Q52.** Write code to set a request header "Authorization" with value "Bearer token123".

**Q53.** Write code to serialize a List of Strings to JSON.

**Q54.** Write a simple wrapper class for JSON: `{"success": true, "data": [1, 2, 3]}`.

**Q55.** Write an @AuraEnabled method that accepts a String parameter and returns an Integer.

**Q56.** Write code to call an Apex method using async/await pattern with try-catch.

**Q57.** Write code to sum all values in an array of numbers using reduce().

**Q58.** Write code to get unique values from an array of numbers.

**Q59.** Write template code to conditionally show a div when `hasData` is true.

**Q60.** Write Apex code to check HTTP response status and throw error if not 200.
