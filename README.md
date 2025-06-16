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
