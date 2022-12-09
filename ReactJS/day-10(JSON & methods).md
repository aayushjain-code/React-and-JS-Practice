### Day-10 JSON its uses and Methods

👉 JSON its uses and Methods 🔆

⚙️ What is JSON?
JavaScript Object Notation
JSON is a lightweight data-interchange format
JSON is language independent
JSON is "self-describing" and easy to understand


⚙️ Where it is used?
Used for data interchange 🛣️ through various forms of technology.

The most common use of JSON data and files is to read 🤓 data from a server 🖥️ for a website or web application 📲 to display — and change data given the correct permissions.

Computer applications, programs, mobile apps, and much more all use JSON files.

⚙️ Methods:
JSON.stringify():- to convert objects into JSON.
JSON.parse():- to convert JSON back into an object.

Code Example: 

```
let student = {
  name: 'John',
  age: 30,
  isAdmin: false,
  courses: ['html', 'css', 'js'],
  spouse: null
};

let json = JSON.stringify(student);
console.log(typeof json); // string
console.log(json);
// JSON-encoded object:
// {
//  "name": "John",
//  "age": 30,
//  "isAdmin": false,
//  "courses": ["html", "css", "js"],
//  "spouse": null
// }
-------------------------------------------------------------

var json = '{"name": "Peter", "age": 22, "country": "United States"}';

// Converting JSON-encoded string to JS object
var obj = JSON.parse(json);

// Accessing individual value from JS object
console.log(obj.name); // Peter
console.log(obj.age); //  22
console.log(obj.country); // United States
```
