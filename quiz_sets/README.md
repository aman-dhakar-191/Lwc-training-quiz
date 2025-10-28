# JSON Data Handling from APIs in LWC - Quiz Sets

This repository contains three comprehensive quiz sets focused on JSON Data Handling from APIs in Lightning Web Components (LWC).

## Overview

- **Total Sets**: 3
- **Questions per Set**: 59
- **Total Questions**: 177
- **Difficulty Distribution**: Easy (60%), Medium (35%), Hard (<5%)
- **Code Questions per Set**: 10 (with answers being one-liner or less than 5 lines)

## Topics Covered

Each quiz set comprehensively covers the following topics:

1. **JSON Fundamentals**
   - JSON syntax and structure
   - Data types in JSON
   - Valid vs invalid JSON format
   - Nested JSON objects and arrays

2. **Basic HTTP Callout in Apex**
   - HttpRequest and HttpResponse classes
   - Setting endpoint URL and HTTP methods
   - Making callouts with Http.send()
   - Reading responses

3. **JSON Parsing in Apex**
   - JSON.deserialize() and JSON.serialize() methods
   - Creating wrapper classes
   - Handling arrays in JSON
   - Working with dynamic JSON

4. **Apex Method Setup for LWC**
   - @AuraEnabled methods
   - Static methods and cacheable options
   - Return types from Apex to LWC
   - Error handling

5. **Calling Apex from LWC**
   - Importing Apex methods
   - Imperative calls and @wire decorator
   - Promise handling with .then() and .catch()
   - Async/await patterns

6. **Processing JSON Data in LWC JavaScript**
   - Receiving data from Apex
   - Array methods (map, filter, forEach, reduce)
   - Object property access
   - Reactive properties

7. **Displaying Data in LWC**
   - Data binding in templates
   - for:each iteration
   - Conditional rendering with if:true/if:false
   - Displaying JSON fields

8. **Error Handling**
   - Try-catch in Apex
   - Error handling in LWC .catch() blocks
   - HTTP status code checking
   - User-friendly error messages

9. **Reactive Properties**
   - @track and @api decorators
   - Updating UI when data changes
   - Modern LWC reactivity

10. **Practical Application**
    - Complete API-to-UI data flow
    - Refreshing data
    - Search and pagination implementations
    - Real-world scenarios

## File Structure

```
quiz_sets/
├── set1_questions.md    # Quiz Set 1 Questions
├── set1_answers.md      # Quiz Set 1 Answers
├── set2_questions.md    # Quiz Set 2 Questions
├── set2_answers.md      # Quiz Set 2 Answers
├── set3_questions.md    # Quiz Set 3 Questions
└── set3_answers.md      # Quiz Set 3 Answers
```

## How to Use

1. **For Self-Study**: Start with any set, answer questions without looking at answers first
2. **For Training**: Use sets sequentially, reviewing answers after each attempt
3. **For Assessment**: Mix questions from different sets to create custom quizzes
4. **For Interview Prep**: Focus on Hard and Medium difficulty questions

## Question Difficulty Breakdown

Each set contains:
- **Easy Questions**: ~35 questions (60%) - Fundamental concepts, basic syntax
- **Medium Questions**: ~21 questions (35%) - Application, analysis, integration
- **Hard Questions**: ~3 questions (<5%) - Complex scenarios, architecture, best practices
- **Code Questions**: 10 questions - Practical coding with concise answers

## Features

- ✅ Comprehensive coverage of JSON and API integration in LWC
- ✅ Separate answer files for better learning experience
- ✅ Mix of theoretical and practical questions
- ✅ Code examples with production-ready snippets
- ✅ Real-world scenarios and best practices
- ✅ Progressive difficulty within each topic

## Best Practices Covered

- Secure API callout implementations
- Proper error handling patterns
- Efficient JSON parsing techniques
- LWC component reactivity
- Code reusability and maintainability
- Governor limit considerations

## Contributing

Feel free to suggest improvements or additional questions through pull requests.

## License

This quiz content is provided for educational purposes.
