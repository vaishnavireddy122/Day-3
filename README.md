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
<h3>MAP:</h3>
<h5>What is a Map?</h5>
A Map is like a container that stores things in pairs:<br>
🔑 a key and <br>
📦 a value. <br>
You use a key to find its value, just like a label on a storage box.<br>
<h5>🧠 Why not just use an Object {}?</h5>
You can — but Map is better when:<br>
You want to use any type of key (not just strings).<br>
You need to keep the order of items.<br>
You need better performance when adding/removing items often.<br>
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
🔹 Adding Data<br>
   myMap.set("color", "blue");<br>
🔹 Getting Data<br>
   console.log(myMap.get("color")); // "blue"<br>
🔹 Checking if a Key Exists<br>
   console.log(myMap.has("color")); // true<br>
🔹 Removing a Key<br>
   myMap.delete("color");<br>
🔹 Checking How Many Items Are Inside<br>
   console.log(myMap.size); // 2 (if two items are added)<br>
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
🆚 Map vs Object Summary (Very Simple)<br>
<pre>
  Feature	             Object	                    Map
Keys can be	           Strings only	                Any type (even objects!)
Keeps order?	          No guarantee	               Yes
Easy size check?	     No (Object.keys().length)	 Yes (map.size)
</pre>

<h3>FILTER:</h3>
<h4>✅ What is filter()?</h4>
filter() is a built-in method for arrays in JavaScript.<br>
It creates a new array with only the items that pass a test (the test is a function you give it).<br>
📦 Basic Syntax:<br>
<pre>
  array.filter(function(item) {
  return condition;
});
</pre>
item is each element in the array<br>
condition is a test that returns true (keep the item) or false (remove it)<br>
🔍 Simple Example: Filter Numbers<br>
<pre>
  const numbers = [1, 2, 3, 4, 5];

// Keep only numbers greater than 3
const result = numbers.filter(num => num > 3);

console.log(result); // ➡️ [4, 5]
</pre>
⚠️ Important Notes
filter() does not change the original array.
It returns a new array.
It's very useful when combined with .map() and .reduce() in real apps.

<h3>REDUCE:</h3>
<h4>✅ What is reduce()?</h4>
reduce() is used to combine all values in an array into a single value — like a sum, product, object, or anything you want.<br>
You give it a function, and it applies that function to each item in the array, building up a final result
📦 Basic Syntax:<br>
 <pre>array.reduce((accumulator, currentValue) => {
  return newValue;
}, initialValue);
</pre>
<br>
accumulator	::: The running total or result so far<br>
currentValue :::	The current item in the array<br>
initialValue :::	The starting value for the accumulator (can be number, object, etc.)<br>
Example ::const numbers = [1, 2, 3];<br>
You want to add all the numbers together.<br>
✅ Without reduce():<br>
<pre>
  let total = 0;
for (let i = 0; i < numbers.length; i++) {
  total = total + numbers[i];
}
console.log(total); // 6
</pre>
✅ Now with reduce():
<pre>
  const total = numbers.reduce((sum, num) => {
  return sum + num;
}, 0);

console.log(total); // 6
</pre>

<h3>find(), some(), and every()</h3>
<h4>1. find()</h4> <br>
🔹 What it does: <br>
Finds the first item in an array that matches a condition and returns it.
If no item matches, returns undefined. <br>
🔹 Example:<br>
<pre>const numbers = [5, 12, 8, 130, 44];
// Find the first number greater than 10
const found = numbers.find(num => num > 10);
console.log(found); // 12
</pre>
<h4>2. some()</h4>
🔹 What it does:<br>
Checks if at least one item in the array passes the test.<br>
Returns true or false.<br>
<pre>
  const ages = [3, 10, 18, 20];
// Is there at least one adult (age >= 18)?
const hasAdult = ages.some(age => age >= 18);
console.log(hasAdult); // true
</pre>
<h4>3. every()
🔹 What it does:</h4>
Checks if all items in the array pass the test.<br>
Returns true or false.<br>
<pre>
  const ages = [12, 17, 20, 25];

// Are all people adults (age >= 18)?
const allAdults = ages.every(age => age >= 18);

console.log(allAdults); // false (because 12 and 17 are not adults)

</pre>
