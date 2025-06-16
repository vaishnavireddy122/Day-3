# Day-3

<h3>JS OBJECTS :</h3>
<p>
A JavaScript object is a collection of key-value pairs. Each key (also called a property name) is a string, and its value can be any data type.
</p>
<pre>
  const person = {
  name: "Alice",
  age: 30,
  isStudent: false,
  hobbies: ["reading", "cycling"],
  greet: function () {
    console.log("Hello!");
  }
};
</pre>
<h5>Accessing Properties:</h5>
You can access object properties using dot notation or bracket notation:
console.log(person.name);      // Alice
console.log(person["age"]);    // 30

<h5> Modifying Properties</h5>
You can update or add properties like this:
<pre>
  person.age = 31;
  person.city = "New York";
</pre>
<h5>Deleting Properties</h5>
 Use the delete operator:
 <pre>
   delete person.isStudent;
 </pre>
 <h5>Methods in Objects</h5>
 When a function is a property of an object, it’s called a method:
 <pre>
   person.sayHello = function () {
  console.log(`Hi, I'm ${this.name}`);
};
person.sayHello();  // Hi, I'm Alice

 </pre>
 <h5>Nested Objects</h5>
Objects can contain other objects:
<pre>
  const car = {
  make: "Toyota",
  model: "Camry",
  owner: {
    name: "Bob",
    age: 40
  }
 };
 console.log(car.owner.name);  // Bob
</pre>
<h3>MAP</h3>
<h5>What is a Map?</h5>
A Map is like a container that stores things in pairs:
🔑 a key and
📦 a value.
You use a key to find its value, just like a label on a storage box.
<h5>🧠 Why not just use an Object {}?</h5>
You can — but Map is better when:
You want to use any type of key (not just strings).
You need to keep the order of items.
You need better performance when adding/removing items often.
<pre>
 const myMap = new Map();
// Add items
myMap.set("name", "Alice");
myMap.set("age", 25);

// Get items
console.log(myMap.get("name")); // ➡️ "Alice"
console.log(myMap.get("age"));  // ➡️ 25
</pre>
<h4>📌 Important Things to Remember</h4>
🔹 Adding Data
   myMap.set("color", "blue");
🔹 Getting Data
   console.log(myMap.get("color")); // "blue"
🔹 Checking if a Key Exists
   console.log(myMap.has("color")); // true
🔹 Removing a Key
   myMap.delete("color");
🔹 Checking How Many Items Are Inside
   console.log(myMap.size); // 2 (if two items are added)
<h5>🌀 Looping Through a Map</h5>
<pre>const map = new Map();
map.set("a", 1);
map.set("b", 2);

for (let [key, value] of map) {
  console.log(`${key} = ${value}`);
}
// Output:
// a = 1
// b = 2
</pre>

<pre>
  Feature	             Object	                    Map
Keys can be	           Strings only	              Any type (even objects!)
Keeps order?	         No guarantee	              Yes
Easy size check?	     No (Object.keys().length)	Yes (map.size)
</pre>
