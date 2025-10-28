# JSON Data Handling from APIs in LWC - Quiz Sets

This repository contains three comprehensive quiz sets focused on JSON Data Handling from APIs in Lightning Web Components (LWC).

## Overview

- **Total Sets**: 3
- **Questions per Set**: 60 (50 Multiple Choice + 10 Coding)
- **Total Questions**: 180
- **Difficulty Distribution**: Easy (60%), Medium (35%), Hard (<5%)
- **Format**: Multiple choice/select for non-coding questions, concise code answers (1-5 lines)

## Structure

Each set contains:
- **50 Multiple Choice Questions**: Testing conceptual understanding with clear answer options
- **10 Coding Questions**: Practical coding exercises with concise, production-ready answers

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
├── set1_questions.md    # Quiz Set 1: 60 Questions (50 MC + 10 Code)
├── set1_answers.md      # Quiz Set 1: Complete Answers
├── set2_questions.md    # Quiz Set 2: 60 Questions (50 MC + 10 Code)
├── set2_answers.md      # Quiz Set 2: Complete Answers
├── set3_questions.md    # Quiz Set 3: 60 Questions (50 MC + 10 Code)
└── set3_answers.md      # Quiz Set 3: Complete Answers
```

## Question Format

### Multiple Choice Questions
Each multiple choice question provides 4 options (a, b, c, d) with a single best answer or multiple correct answers where specified.

Example:
```
Q: Which Apex class is used to make HTTP callouts?
a) HTTPClient
b) Http
c) WebService
d) RestClient

Answer: b) Http
```

### Coding Questions
Coding questions require concise, production-ready code answers (1-5 lines).

Example:
```
Q: Write code to filter an array to get only items where status === 'active'.

Answer:
const activeData = data.filter(item => item.status === 'active');
```

## How to Use

1. **For Self-Study**: Answer questions in Section A (Multiple Choice) first, then tackle Section B (Coding)
2. **For Training**: Use sets sequentially, reviewing answers after each attempt
3. **For Assessment**: Mix questions from different sets to create custom quizzes
4. **For Interview Prep**: Focus on coding questions and medium/hard difficulty questions

## Question Difficulty Breakdown

Each set contains approximately:
- **Easy Questions**: ~36 questions (60%) - Fundamental concepts, basic syntax
- **Medium Questions**: ~21 questions (35%) - Application, analysis, integration
- **Hard Questions**: ~3 questions (<5%) - Complex scenarios, architecture, best practices

## Features

- ✅ All non-coding questions are multiple choice/select format
- ✅ Clear separation between conceptual (MC) and practical (Coding) questions
- ✅ Comprehensive coverage of JSON and API integration in LWC
- ✅ Separate answer files for better learning experience
- ✅ Real-world scenarios and best practices
- ✅ Progressive difficulty within each topic
- ✅ Production-ready code examples

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
