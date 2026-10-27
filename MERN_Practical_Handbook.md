# MERN Stack Practical Exam Handbook
## Simple code, VS Code steps, and run commands

This is a single Markdown file. Open it directly in VS Code and copy each practical's code.

## Before starting

- **JavaScript:** Install Node.js. Run a saved file with `node filename.js`.
- **React:** Create a Vite React project once, then replace `src/App.jsx` for each React practical.
- **Express:** Install Node.js, then install Express inside a project using `npm install express`.
- **Axios:** Inside a React project, run `npm install axios`.
- **React Router:** Inside a React project, run `npm install react-router-dom`.
- **MongoDB:** MongoDB Community Server and `mongosh` must be installed separately. A VS Code terminal command cannot install the database without an installer/package manager. Use the official MongoDB Community Server and Shell installers if needed.

### Create a React project

Run in VS Code Terminal:
```bash
npm create vite@latest my-practical -- --template react
cd my-practical
npm install
npm run dev
```
For a different practical, you can reuse the same project and replace `src/App.jsx`. Stop the running server with `Ctrl+C` before starting another terminal task if needed.

---

# Q.1 — JavaScript, React, Router and API

## A. JavaScript programs

For each program, create a `.js` file, paste the code, then run `node filename.js`.

### 1. Demonstrate operators and control statements
```javascript
let a = 10;
let b = 5;
console.log("Sum:", a + b);
console.log("Greater:", a > b);
if (a > b) {
    console.log("a is greater");
} else {
    console.log("b is greater");
}
```

### 2. Print even numbers from 1 to 50
```javascript
for (let i = 1; i <= 50; i++) {
    if (i % 2 === 0) console.log(i);
}
```

### 3. Declare variables and calculate sum using a function
```javascript
let a = 10;
let b = 20;
function sum(x, y) {
    return x + y;
}
console.log("Sum:", sum(a, b));
```

### 4. Find the largest of three numbers
```javascript
let a = 10, b = 25, c = 15;
if (a >= b && a >= c) console.log(a);
else if (b >= a && b >= c) console.log(b);
else console.log(c);
```

### 5. Factorial using a loop and template literals
```javascript
let n = 5;
let fact = 1;
for (let i = 1; i <= n; i++) fact *= i;
console.log(`Factorial of ${n} is ${fact}`);
```

### 6. Reverse a number
```javascript
let n = 1234;
let reverse = 0;
while (n > 0) {
    reverse = reverse * 10 + n % 10;
    n = Math.floor(n / 10);
}
console.log(reverse);
```

### 7. Implement arrays in JavaScript
```javascript
let fruits = ["Apple", "Banana", "Mango"];
console.log(fruits);
console.log(fruits[0]);
fruits.push("Orange");
console.log(fruits);
```

### 8. Demonstrate arrow functions
```javascript
const greet = () => "Hello JavaScript";
console.log(greet());
```

### 9. Add two numbers using an arrow function
```javascript
const sum = (a, b) => a + b;
console.log(sum(10, 20));
```

### 10. Multiplication table using a loop and template literals
```javascript
let n = 5;
for (let i = 1; i <= 10; i++) {
    console.log(`${n} x ${i} = ${n * i}`);
}
```

### 11. Check even or odd using an arrow function
```javascript
const check = n => n % 2 === 0 ? "Even" : "Odd";
console.log(check(7));
```

### 12. Demonstrate arrays and objects
```javascript
let fruits = ["Apple", "Mango"];
let student = { name: "Ravi", age: 20 };
console.log(fruits);
console.log(student.name, student.age);
```

### 13. Use map(), filter() and reduce()
```javascript
let numbers = [10, 20, 30, 40, 50];
console.log(numbers.map(n => n * 2));
console.log(numbers.filter(n => n > 25));
console.log(numbers.reduce((sum, n) => sum + n, 0));
```

### 14. Create a student object and display properties
```javascript
let student = { name: "Ravi", rollNo: 12, course: "BSc IT" };
console.log(student.name);
console.log(student.rollNo);
console.log(student.course);
```

### 15. Store student details in an array of objects
```javascript
let students = [
    { name: "Ravi", rollNo: 1 },
    { name: "Priya", rollNo: 2 },
    { name: "Aman", rollNo: 3 }
];
students.forEach(s => console.log(s.name, s.rollNo));
```

### 16. Store student marks in an array of objects
```javascript
let students = [
    { name: "Ravi", marks: 85 },
    { name: "Priya", marks: 72 },
    { name: "Aman", marks: 91 }
];
students.forEach(s => console.log(s.name, s.marks));
```

### 17. Calculate percentage, grade, pass and distinction
```javascript
let marks = [80, 75, 90, 85, 70];
let total = marks.reduce((sum, mark) => sum + mark, 0);
let percentage = total / marks.length;
let status = marks.some(mark => mark < 35) ? "Fail" : "Pass";
let grade = percentage >= 75 ? "Distinction" : percentage >= 60 ? "First Class" : percentage >= 35 ? "Pass Class" : "Fail";
console.log(`Percentage: ${percentage}%`);
console.log(`Status: ${status}`);
console.log(`Grade: ${grade}`);
```

### 18. Calculate simple interest
```javascript
function simpleInterest(principal, rate, time) {
    return principal * rate * time / 100;
}
console.log("Simple Interest:", simpleInterest(1000, 5, 2));
```

### 19. Array of five products and array methods
```javascript
let products = ["Pen", "Book", "Bag", "Pencil", "Ruler"];
products.push("Bottle");
console.log(products);
products.pop();
console.log(products);
products.shift();
console.log(products);
products.unshift("Eraser");
console.log(products);
```

### 20. Functions for square, cube and even/odd
```javascript
const square = n => n * n;
const cube = n => n * n * n;
const evenOdd = n => n % 2 === 0 ? "Even" : "Odd";
console.log(square(4));
console.log(cube(4));
console.log(evenOdd(4));
```

### 21. Increase salaries by 10% and filter salaries
```javascript
let salaries = [20000, 30000, 40000, 50000];
let increased = salaries.map(s => s * 1.10);
let filtered = increased.filter(s => s > 35000);
console.log(increased);
console.log(filtered);
```

### 22. Library program: add, search and list books
```javascript
let books = [];
function addBook(title) {
    books.push({ title, available: true });
}
function searchBook(title) {
    return books.find(book => book.title.toLowerCase() === title.toLowerCase());
}
function listBooks() {
    console.log(books.filter(book => book.available));
}
addBook("Wings of Fire");
addBook("The Alchemist");
console.log(searchBook("The Alchemist"));
listBooks();
```

### 23. Switch for day name and ternary for leap year
```javascript
let day = 3;
switch (day) {
    case 1: console.log("Monday"); break;
    case 2: console.log("Tuesday"); break;
    case 3: console.log("Wednesday"); break;
    case 4: console.log("Thursday"); break;
    case 5: console.log("Friday"); break;
    case 6: console.log("Saturday"); break;
    case 7: console.log("Sunday"); break;
    default: console.log("Invalid day");
}
let year = 2024;
console.log(year % 400 === 0 || (year % 4 === 0 && year % 100 !== 0) ? "Leap year" : "Not a leap year");
```

### 24. Star triangle and Fibonacci series
```javascript
for (let i = 1; i <= 5; i++) {
    let row = "";
    for (let j = 1; j <= i; j++) row += "* ";
    console.log(row);
}
let a = 0, b = 1;
for (let i = 1; i <= 10; i++) {
    console.log(a);
    let next = a + b;
    a = b;
    b = next;
}
```

### 25. Celsius/Fahrenheit conversion using let and const
```javascript
const celsiusToFahrenheit = c => c * 9 / 5 + 32;
const fahrenheitToCelsius = f => (f - 32) * 5 / 9;
let c = 25;
let f = 77;
console.log(celsiusToFahrenheit(c));
console.log(fahrenheitToCelsius(f));
```

### 26. Default parameter and electricity bill
```javascript
function bill(units = 0) {
    if (units <= 100) return units * 2;
    if (units <= 200) return 100 * 2 + (units - 100) * 3;
    return 100 * 2 + 100 * 3 + (units - 200) * 5;
}
console.log(`Electricity bill: Rs. ${bill(250)}`);
```

---

## B. React components, state and forms

For each practical below, paste the code into `src/App.jsx` of a Vite React project, then run `npm run dev`. Unless stated otherwise, no extra package is needed.

### 27. Create a simple functional component
```jsx
function App() {
    return <h1>Hello React</h1>;
}
export default App;
```

### 28. Heading and paragraph component
```jsx
function App() {
    return <div><h1>Welcome</h1><p>This is a React paragraph.</p></div>;
}
export default App;
```

### 29. Display a welcome message
```jsx
function App() {
    return <h1>Welcome to MERN Stack</h1>;
}
export default App;
```

### 30. Render multiple functional components
```jsx
function Header() { return <h1>My Website</h1>; }
function Content() { return <p>Welcome to React.</p>; }
function Footer() { return <footer>Thank you</footer>; }
function App() { return <><Header /><Content /><Footer /></>; }
export default App;
```

### 31. Welcome and Footer components with name and college
```jsx
function Welcome() { return <h1>Welcome, Ankit</h1>; }
function Footer() { return <p>RD & SH National College</p>; }
function App() { return <><Welcome /><Footer /></>; }
export default App;
```

### 32. Apply external CSS styling
`src/App.jsx`
```jsx
import './App.css';
function App() { return <h1 className="heading">Hello React</h1>; }
export default App;
```
`src/App.css`
```css
.heading {
    color: blue;
    text-align: center;
}
```

### 33. React component to calculate sum of two numbers
```jsx
function App() {
    let a = 10;
    let b = 20;
    return <h2>Sum: {a + b}</h2>;
}
export default App;
```

### 34. Show current date and time, update every second
```jsx
import { useEffect, useState } from 'react';
function App() {
    const [time, setTime] = useState(new Date());
    useEffect(() => {
        const id = setInterval(() => setTime(new Date()), 1000);
        return () => clearInterval(id);
    }, []);
    return <h2>{time.toLocaleString()}</h2>;
}
export default App;
```

### 35. Pass student details using props
```jsx
function Student(props) {
    return <p>{props.name} - {props.roll} - {props.course}</p>;
}
function App() {
    return <Student name="Ankit" roll="12" course="BSc IT" />;
}
export default App;
```

### 36. Product component using props
```jsx
function Product({ name, price }) {
    return <p>{name}: Rs. {price}</p>;
}
function App() {
    return <Product name="Notebook" price={50} />;
}
export default App;
```

### 37. Manage and update data using useState
```jsx
import { useState } from 'react';
function App() {
    const [count, setCount] = useState(0);
    return <div><h2>{count}</h2><button onClick={() => setCount(count + 1)}>Increase</button></div>;
}
export default App;
```

### 38. Display and update a user's name
```jsx
import { useState } from 'react';
function App() {
    const [name, setName] = useState("Ankit");
    return <div><input value={name} onChange={e => setName(e.target.value)} /><h2>{name}</h2></div>;
}
export default App;
```

### 39. Counter with increment, decrement and reset
```jsx
import { useState } from 'react';
function App() {
    const [count, setCount] = useState(0);
    return <div><h2>{count}</h2><button onClick={() => setCount(count + 1)}>+</button><button onClick={() => setCount(count - 1)}>-</button><button onClick={() => setCount(0)}>Reset</button></div>;
}
export default App;
```

### 40. Store a list in state and display with map()
```jsx
import { useState } from 'react';
function App() {
    const [items] = useState(["Apple", "Banana", "Mango"]);
    return <ul>{items.map((item, i) => <li key={i}>{item}</li>)}</ul>;
}
export default App;
```

### 41. Display names using map()
```jsx
function App() {
    const names = ["Ankit", "Ravi", "Priya"];
    return <ul>{names.map((name, i) => <li key={i}>{name}</li>)}</ul>;
}
export default App;
```

### 42. Display student details dynamically using JSX
```jsx
function App() {
    const student = { name: "Ankit", roll: 12, course: "BSc IT" };
    return <div><h2>{student.name}</h2><p>Roll: {student.roll}</p><p>Course: {student.course}</p></div>;
}
export default App;
```

### 43. Calculate square and cube
```jsx
import { useState } from 'react';
function App() {
    const [n, setN] = useState(2);
    return <div><input type="number" value={n} onChange={e => setN(Number(e.target.value))} /><p>Square: {n * n}</p><p>Cube: {n * n * n}</p></div>;
}
export default App;
```

### 44. To-do list with add and delete
```jsx
import { useState } from 'react';
function App() {
    const [task, setTask] = useState("");
    const [tasks, setTasks] = useState([]);
    function addTask(e) {
        e.preventDefault();
        if (task.trim()) {
            setTasks([...tasks, task]);
            setTask("");
        }
    }
    return <div><form onSubmit={addTask}><input value={task} onChange={e => setTask(e.target.value)} /><button>Add</button></form>{tasks.map((t, i) => <p key={i}>{t} <button onClick={() => setTasks(tasks.filter((_, j) => j !== i))}>Delete</button></p>)}</div>;
}
export default App;
```

### 45. Form input displayed dynamically
```jsx
import { useState } from 'react';
function App() {
    const [name, setName] = useState("");
    return <div><input placeholder="Enter name" value={name} onChange={e => setName(e.target.value)} /><h2>Your name: {name}</h2></div>;
}
export default App;
```

### 46. Registration form with basic validation
```jsx
import { useState } from 'react';
function App() {
    const [form, setForm] = useState({ name: "", email: "", phone: "", password: "" });
    const [message, setMessage] = useState("");
    function change(e) {
        setForm({ ...form, [e.target.name]: e.target.value });
    }
    function submit(e) {
        e.preventDefault();
        if (!form.name || !form.email.includes("@") || !/^\d{10}$/.test(form.phone) || form.password.length < 6) {
            setMessage("Enter valid details. Password must be 6+ characters.");
        } else {
            setMessage("Registration successful");
        }
    }
    return <form onSubmit={submit}><input name="name" placeholder="Name" value={form.name} onChange={change} /><input name="email" placeholder="Email" value={form.email} onChange={change} /><input name="phone" placeholder="10-digit phone" value={form.phone} onChange={change} /><input name="password" type="password" placeholder="Password" value={form.password} onChange={change} /><button>Register</button><p>{message}</p></form>;
}
export default App;
```

### 47. Vite/CRA app with Header component
```jsx
function Header() {
    return <h1>Welcome to MERN Stack Development</h1>;
}
function App() {
    return <Header />;
}
export default App;
```

---

## C. React Router and API integration

For Router practicals, run `npm install react-router-dom`. For Axios practicals, run `npm install axios`. Paste each code into `src/App.jsx`.

### 51. Install Router and create Home, About and Contact pages
Create `src/pages/Home.jsx`:
```jsx
export default function Home() { return <h2>Home Page</h2>; }
```
Create `src/pages/About.jsx`:
```jsx
export default function About() { return <h2>About Page</h2>; }
```
Create `src/pages/Contact.jsx`:
```jsx
export default function Contact() { return <h2>Contact Page</h2>; }
```
`src/App.jsx`:
```jsx
import { BrowserRouter, Routes, Route, Link } from 'react-router-dom';
import Home from './pages/Home';
import About from './pages/About';
import Contact from './pages/Contact';
function App() {
    return <BrowserRouter><nav><Link to="/">Home</Link> | <Link to="/about">About</Link> | <Link to="/contact">Contact</Link></nav><Routes><Route path="/" element={<Home />} /><Route path="/about" element={<About />} /><Route path="/contact" element={<Contact />} /></Routes></BrowserRouter>;
}
export default App;
```

### 52. Use Link and Routes to navigate between pages
Use the same `App.jsx` code from Practical 51. It already uses `Link`, `Routes`, and `Route`.

### 53. Bookstore pages and Page Not Found
```jsx
import { BrowserRouter, Routes, Route, Link } from 'react-router-dom';
function Home() { return <h2>Home Page</h2>; }
function Books() { return <h2>Books Page</h2>; }
function Cart() { return <h2>Cart Page</h2>; }
function NotFound() { return <h2>Page Not Found</h2>; }
function App() {
    return <BrowserRouter><nav><Link to="/">Home</Link> | <Link to="/books">Books</Link> | <Link to="/cart">Cart</Link></nav><Routes><Route path="/" element={<Home />} /><Route path="/books" element={<Books />} /><Route path="/cart" element={<Cart />} /><Route path="*" element={<NotFound />} /></Routes></BrowserRouter>;
}
export default App;
```

### 54. Fetch data from public API using Axios and display results
```jsx
import axios from 'axios';
import { useEffect, useState } from 'react';
function App() {
    const [users, setUsers] = useState([]);
    useEffect(() => {
        axios.get('https://jsonplaceholder.typicode.com/users').then(res => setUsers(res.data));
    }, []);
    return <div><h2>Users</h2>{users.map(u => <p key={u.id}>{u.name}</p>)}</div>;
}
export default App;
```

### 55. Fetch users and search by name
```jsx
import axios from 'axios';
import { useEffect, useState } from 'react';
function App() {
    const [users, setUsers] = useState([]);
    const [search, setSearch] = useState("");
    useEffect(() => {
        axios.get('https://jsonplaceholder.typicode.com/users').then(res => setUsers(res.data));
    }, []);
    const filtered = users.filter(u => u.name.toLowerCase().includes(search.toLowerCase()));
    return <div><input placeholder="Search name" value={search} onChange={e => setSearch(e.target.value)} />{filtered.map(u => <p key={u.id}>{u.name}</p>)}</div>;
}
export default App;
```

### 56. Fetch sample data and display filtered results dynamically
```jsx
import axios from 'axios';
import { useEffect, useState } from 'react';
function App() {
    const [posts, setPosts] = useState([]);
    const [search, setSearch] = useState("");
    useEffect(() => {
        axios.get('https://jsonplaceholder.typicode.com/posts').then(res => setPosts(res.data.slice(0, 20)));
    }, []);
    return <div><input placeholder="Search title" value={search} onChange={e => setSearch(e.target.value)} />{posts.filter(p => p.title.includes(search.toLowerCase())).map(p => <p key={p.id}>{p.title}</p>)}</div>;
}
export default App;
```

### 57. Fetch student data from an Express API using Axios
First run the backend server from Q.2 Practical 13, then install Axios in the React project.
```jsx
import axios from 'axios';
import { useEffect, useState } from 'react';
function App() {
    const [students, setStudents] = useState([]);
    useEffect(() => {
        axios.get('http://localhost:3000/students').then(res => setStudents(res.data));
    }, []);
    return <div>{students.map(s => <p key={s.id}>{s.name} - {s.roll}</p>)}</div>;
}
export default App;
```

### 58. Display fetched data in a table
```jsx
import axios from 'axios';
import { useEffect, useState } from 'react';
function App() {
    const [users, setUsers] = useState([]);
    useEffect(() => {
        axios.get('https://jsonplaceholder.typicode.com/users').then(res => setUsers(res.data));
    }, []);
    return <table border="1"><thead><tr><th>ID</th><th>Name</th><th>Email</th></tr></thead><tbody>{users.map(u => <tr key={u.id}><td>{u.id}</td><td>{u.name}</td><td>{u.email}</td></tr>)}</tbody></table>;
}
export default App;
```

### 59. Filter displayed data
```jsx
import axios from 'axios';
import { useEffect, useState } from 'react';
function App() {
    const [users, setUsers] = useState([]);
    const [search, setSearch] = useState("");
    useEffect(() => {
        axios.get('https://jsonplaceholder.typicode.com/users').then(res => setUsers(res.data));
    }, []);
    return <div><input placeholder="Filter by name" value={search} onChange={e => setSearch(e.target.value)} /><ul>{users.filter(u => u.name.toLowerCase().includes(search.toLowerCase())).map(u => <li key={u.id}>{u.name}</li>)}</ul></div>;
}
export default App;
```

### 60. React form sends user data to backend
Run the Express backend from Q.2 Practical 14 first.
```jsx
import { useState } from 'react';
import axios from 'axios';
function App() {
    const [name, setName] = useState("");
    const [message, setMessage] = useState("");
    async function submit(e) {
        e.preventDefault();
        const res = await axios.post('http://localhost:3000/students', { name });
        setMessage(res.data.message);
    }
    return <form onSubmit={submit}><input value={name} onChange={e => setName(e.target.value)} placeholder="Student name" /><button>Submit</button><p>{message}</p></form>;
}
export default App;
```

---

# Q.2 — Node.js, Express and MongoDB

## A. Node.js and Express

Create a folder, open it in VS Code, then run:
```bash
npm init -y
npm install express
```
Create `server.js` for each practical and run it with `node server.js`. Open `http://localhost:3000` in a browser.

### 1. Display a message in browser using server response
```javascript
const express = require('express');
const app = express();
app.get('/', (req, res) => res.send('Hello from Express'));
app.listen(3000);
```

### 2. Create different routes in Express
```javascript
const express = require('express');
const app = express();
app.get('/', (req, res) => res.send('Home'));
app.get('/about', (req, res) => res.send('About'));
app.listen(3000);
```

### 3. Send JSON response
```javascript
const express = require('express');
const app = express();
app.get('/user', (req, res) => res.json({ name: 'Ankit', course: 'BSc IT' }));
app.listen(3000);
```

### 4. Simple REST API
```javascript
const express = require('express');
const app = express();
app.use(express.json());
let items = [{ id: 1, name: 'Book' }];
app.get('/items', (req, res) => res.json(items));
app.post('/items', (req, res) => {
    items.push(req.body);
    res.json({ message: 'Item added', items });
});
app.listen(3000);
```

### 5. GET API to retrieve data
```javascript
const express = require('express');
const app = express();
app.get('/students', (req, res) => res.json([{ id: 1, name: 'Ankit' }, { id: 2, name: 'Ravi' }]));
app.listen(3000);
```

### 6. Welcome to Node.js and Express
```javascript
const express = require('express');
const app = express();
app.get('/', (req, res) => res.send('Welcome to Node.js and Express'));
app.listen(3000);
```

### 7. Home, About, Services and Contact routes
```javascript
const express = require('express');
const app = express();
app.get('/', (req, res) => res.send('Home'));
app.get('/about', (req, res) => res.send('About'));
app.get('/services', (req, res) => res.send('Services'));
app.get('/contact', (req, res) => res.send('Contact'));
app.listen(3000);
```

### 8. Middleware logs method and URL
```javascript
const express = require('express');
const app = express();
app.use((req, res, next) => {
    console.log(req.method, req.url);
    next();
});
app.get('/', (req, res) => res.send('Home'));
app.listen(3000);
```

### 9. Library routes: books and members
```javascript
const express = require('express');
const app = express();
app.get('/books', (req, res) => res.json(['Book A', 'Book B']));
app.get('/members', (req, res) => res.json(['Ankit', 'Ravi']));
app.listen(3000);
```

### 10. List of products in JSON
```javascript
const express = require('express');
const app = express();
app.get('/products', (req, res) => res.json([{ id: 1, name: 'Pen', price: 10 }, { id: 2, name: 'Book', price: 50 }]));
app.listen(3000);
```

### 11. GET /api/books and test in browser
```javascript
const express = require('express');
const app = express();
app.get('/api/books', (req, res) => res.json([{ id: 1, title: 'Wings of Fire' }, { id: 2, title: 'The Alchemist' }]));
app.listen(3000, () => console.log('http://localhost:3000/api/books'));
```

### 12. REST API welcome message
```javascript
const express = require('express');
const app = express();
app.get('/api', (req, res) => res.json({ message: 'Welcome to Node.js and Express' }));
app.listen(3000);
```

### 13. GET all students and student by ID
```javascript
const express = require('express');
const app = express();
const students = [{ id: 1, name: 'Ankit' }, { id: 2, name: 'Ravi' }];
app.get('/students', (req, res) => res.json(students));
app.get('/students/:id', (req, res) => {
    const student = students.find(s => s.id === Number(req.params.id));
    student ? res.json(student) : res.status(404).json({ message: 'Student not found' });
});
app.listen(3000);
```

### 14. POST API to accept student details
```javascript
const express = require('express');
const app = express();
app.use(express.json());
let students = [];
app.post('/students', (req, res) => {
    students.push({ id: students.length + 1, ...req.body });
    res.json({ message: 'Student added' });
});
app.get('/students', (req, res) => res.json(students));
app.listen(3000);
```

### 15. Frontend form validation using Node.js and Express
```javascript
const express = require('express');
const app = express();
app.use(express.json());
app.post('/register', (req, res) => {
    const { name, email } = req.body;
    if (!name || !email || !email.includes('@')) return res.status(400).json({ message: 'Invalid details' });
    res.json({ message: 'Registration successful' });
});
app.listen(3000);
```

### 16. Integrate React frontend with Express backend
Backend `server.js`:
```javascript
const express = require('express');
const cors = require('cors');
const app = express();
app.use(cors());
app.get('/api/message', (req, res) => res.json({ message: 'Hello from Express' }));
app.listen(3000);
```
Install backend packages with `npm install express cors`. In React `App.jsx`:
```jsx
import { useEffect, useState } from 'react';
import axios from 'axios';
function App() {
    const [message, setMessage] = useState('');
    useEffect(() => {
        axios.get('http://localhost:3000/api/message').then(res => setMessage(res.data.message));
    }, []);
    return <h2>{message}</h2>;
}
export default App;
```
Install Axios in the React project with `npm install axios`. Start backend and frontend in separate terminals.

---

## B. MongoDB database operations

### MongoDB setup
1. Install MongoDB Community Server and MongoDB Shell (`mongosh`) using their official Windows installers if not already installed.
2. In VS Code Terminal, start the service if installed as a Windows service:
```bash
net start MongoDB
```
3. Open the shell:
```bash
mongosh
```
4. Type MongoDB commands in the `mongosh` prompt, not at the regular PowerShell/CMD prompt.

### 17. Create database and collection; insert records
```javascript
use CollegeDB
db.createCollection("Students")
db.Students.insertOne({ rollNo: 1, name: "Ankit", marks: 85 })
db.Students.find()
```

### 18. Connect MongoDB with Node.js
In a new folder, run:
```bash
npm init -y
npm install mongodb
```
Create `app.js`:
```javascript
const { MongoClient } = require('mongodb');
const client = new MongoClient('mongodb://127.0.0.1:27017');
async function main() {
    await client.connect();
    console.log('MongoDB connected');
    await client.close();
}
main().catch(console.error);
```
Run `node app.js`.

### 19. Store data in MongoDB using Node.js
Install `mongodb` as in Practical 18. Create `app.js`:
```javascript
const { MongoClient } = require('mongodb');
const client = new MongoClient('mongodb://127.0.0.1:27017');
async function main() {
    await client.connect();
    const db = client.db('CollegeDB');
    await db.collection('Students').insertOne({ rollNo: 2, name: 'Ravi', marks: 78 });
    console.log('Data inserted');
    await client.close();
}
main().catch(console.error);
```

### 20. Insert and update records in MongoDB shell
```javascript
use CollegeDB
db.Students.insertOne({ rollNo: 3, name: "Priya", marks: 70 })
db.Students.updateOne({ rollNo: 3 }, { $set: { marks: 88 } })
db.Students.find({ rollNo: 3 })
```

### 21. Insert and delete records in MongoDB shell
```javascript
use CollegeDB
db.Students.insertOne({ rollNo: 4, name: "Aman", marks: 65 })
db.Students.deleteOne({ rollNo: 4 })
db.Students.find()
```

### 22. Retrieve and display user data from MongoDB using Express
Install `express mongodb` in a Node project. Ensure MongoDB is running.
```javascript
const express = require('express');
const { MongoClient } = require('mongodb');
const app = express();
const client = new MongoClient('mongodb://127.0.0.1:27017');
app.get('/users', async (req, res) => {
    try {
        await client.connect();
        const users = await client.db('CollegeDB').collection('Students').find().toArray();
        res.json(users);
    } catch (e) {
        res.status(500).json({ message: 'Database error' });
    }
});
app.listen(3000);
```

### 23. API to add user details using Express and MongoDB
Install `express mongodb`; ensure MongoDB is running.
```javascript
const express = require('express');
const { MongoClient } = require('mongodb');
const app = express();
app.use(express.json());
const client = new MongoClient('mongodb://127.0.0.1:27017');
app.post('/users', async (req, res) => {
    try {
        await client.connect();
        const result = await client.db('CollegeDB').collection('Users').insertOne(req.body);
        res.json({ message: 'User added', id: result.insertedId });
    } catch (e) {
        res.status(500).json({ message: 'Database error' });
    }
});
app.listen(3000);
```

### 24. CollegeDB tasks: insert, find by roll number, marks > 75, delete
```javascript
use CollegeDB
db.Students.insertMany([{ rollNo: 11, name: "Ravi", marks: 80 }, { rollNo: 12, name: "Priya", marks: 72 }, { rollNo: 13, name: "Aman", marks: 91 }])
db.Students.findOne({ rollNo: 11 })
db.Students.find({ marks: { $gt: 75 } })
db.Students.deleteOne({ rollNo: 12 })
```

### 25. Insert multiple student documents and display all
```javascript
use CollegeDB
db.Students.insertMany([{ rollNo: 21, name: "Asha", marks: 80 }, { rollNo: 22, name: "Raj", marks: 76 }, { rollNo: 23, name: "Neha", marks: 90 }])
db.Students.find()
```

### 26. Connect using Mongoose, insert and display a student
Install:
```bash
npm init -y
npm install mongoose
```
Create `app.js`:
```javascript
const mongoose = require('mongoose');
mongoose.connect('mongodb://127.0.0.1:27017/CollegeDB');
const Student = mongoose.model('Student', new mongoose.Schema({ name: String, rollNo: Number, marks: Number }));
async function main() {
    const student = await Student.create({ name: 'Ankit', rollNo: 30, marks: 86 });
    console.log(student);
    await mongoose.disconnect();
}
main().catch(console.error);
```
Run `node app.js`.

### 27. GET API to retrieve books from MongoDB
Install `express mongodb`. Ensure MongoDB is running and create `Library` database with a `Books` collection.
```javascript
const express = require('express');
const { MongoClient } = require('mongodb');
const app = express();
const client = new MongoClient('mongodb://127.0.0.1:27017');
app.get('/books', async (req, res) => {
    try {
        await client.connect();
        res.json(await client.db('Library').collection('Books').find().toArray());
    } catch (e) {
        res.status(500).json({ message: 'Database error' });
    }
});
app.listen(3000);
```
Open `http://localhost:3000/books` in a browser.

### 28. MongoDB comparison operators and count
```javascript
use CollegeDB
db.Students.find({ marks: { $gt: 75 } })
db.Students.find({ marks: { $lt: 80 } })
db.Students.find({ marks: { $eq: 85 } })
db.Students.countDocuments({ marks: { $gt: 75 } })
```

---

## Quick run-command summary

| Practical type | Command |
|---|---|
| JavaScript file | `node filename.js` |
| React development server | `npm run dev` |
| Express server | `node server.js` |
| MongoDB service (Windows service install) | `net start MongoDB` |
| MongoDB Shell | `mongosh` |
| Install Express | `npm install express` |
| Install Axios in React project | `npm install axios` |
| Install React Router | `npm install react-router-dom` |
| Install MongoDB Node driver | `npm install mongodb` |
| Install Mongoose | `npm install mongoose` |

## Important notes

- The React examples are separate practicals. Use one `App.jsx` practical at a time.
- For public API examples, internet access is required.
- For MongoDB practicals, MongoDB Server must be installed and running locally.
- For React + Express examples, run backend and frontend in separate VS Code terminals.
- No code comments are included in the practical code blocks.
