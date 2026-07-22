# JavaScript → TypeScript → React Dashboard Development Roadmap
## 3-Month Learning Journey (4 hours/day)

**Goal**: Master JavaScript, TypeScript, and React to build production-level data visualization dashboards integrated with FastAPI backends.

**Target Outcome**: A fully functional dashboard application that displays real-time data with charts, state management, and API integration.

---

## 📋 Table of Contents
1. [Month 1: JavaScript Fundamentals](#month-1-javascript-fundamentals)
2. [Month 2: TypeScript & React Basics](#month-2-typescript--react-basics)
3. [Month 3: Advanced React, State Management & Dashboard Projects](#month-3-advanced-react-state-management--dashboard-projects)
4. [Mini Projects](#mini-projects)
5. [Resources](#resources)

---

## MONTH 1: JavaScript Fundamentals
**Duration**: 4 weeks (20 days of learning)  
**Daily Time**: 4 hours  
**Total Hours**: ~80 hours

### Week 1: JavaScript Basics & DOM Manipulation

#### Day 1-2: JavaScript Fundamentals Review
- **Topics to Cover**:
  - Variables (let, const, var) - differences and best practices
  - Data types (primitives vs objects)
  - Operators (arithmetic, logical, comparison, ternary)
  - Control flow (if/else, switch, loops)
  - Functions (function declaration, expression, arrow functions)
  - Scope and closures
  - Hoisting

- **Tasks**:
  - Write 10 programs covering all operators and control flow
  - Create 5 functions demonstrating scope and closures
  - Practice arrow functions vs regular functions (10 examples)

**Resources**:
- MDN Web Docs: JavaScript Basics
- JavaScript.info - JavaScript Fundamentals

---

#### Day 3-4: Objects & Arrays Deep Dive
- **Topics to Cover**:
  - Object literals and object creation
  - Array methods (map, filter, reduce, forEach, find, some, every)
  - Destructuring (objects and arrays)
  - Spread operator (...)
  - Object methods (Object.keys, Object.values, Object.entries, Object.assign)
  - Array iteration patterns

- **Tasks**:
  - Create objects representing different entities (user, product, etc.)
  - Practice all array methods with real-world data
  - Write 5 destructuring examples
  - Create a function that uses reduce to calculate statistics

**Code Example Structure**:
```javascript
// Array methods practice
const students = [
  { name: 'Alice', score: 85 },
  { name: 'Bob', score: 92 },
  { name: 'Charlie', score: 78 }
];

// Practice: map, filter, reduce
const highScorers = students.filter(s => s.score > 80);
const avgScore = students.reduce((sum, s) => sum + s.score, 0) / students.length;
```

---

#### Day 5: DOM Manipulation & Events
- **Topics to Cover**:
  - Selecting elements (querySelector, getElementById, etc.)
  - Manipulating DOM (innerHTML, textContent, classList, style)
  - Event handling (addEventListener, event object)
  - Event delegation
  - Common events (click, change, input, submit)
  - Event propagation (bubbling, capturing, preventDefault)

- **Tasks**:
  - Build a simple to-do list with add/delete functionality
  - Create a form with validation and dynamic error messages
  - Implement a counter with increment/decrement buttons
  - Practice event delegation with dynamic elements

---

### Week 2: Advanced Functions & Asynchronous JavaScript

#### Day 6-7: Advanced Function Concepts
- **Topics to Cover**:
  - Function constructors
  - `this` keyword and context binding
  - call(), apply(), bind() methods
  - Higher-order functions
  - Function composition
  - Currying
  - Memoization

- **Tasks**:
  - Create a function calculator using bind()
  - Write higher-order functions that return other functions
  - Implement a simple debounce and throttle function
  - Practice currying with real-world examples

**Code Example**:
```javascript
// Higher-order function
const multiply = (factor) => {
  return (number) => number * factor;
};

const double = multiply(2);
console.log(double(5)); // 10

// Debounce example for API calls
const debounce = (func, delay) => {
  let timeout;
  return (...args) => {
    clearTimeout(timeout);
    timeout = setTimeout(() => func(...args), delay);
  };
};
```

---

#### Day 8-9: Promises & Async/Await
- **Topics to Cover**:
  - Promise states (pending, fulfilled, rejected)
  - Creating promises
  - Promise chaining (.then(), .catch(), .finally())
  - Promise.all(), Promise.race(), Promise.allSettled()
  - async/await syntax
  - Error handling with try/catch
  - Comparison: promises vs async/await

- **Tasks**:
  - Convert callback functions to promises
  - Write async functions that fetch data
  - Implement error handling with try/catch
  - Use Promise.all() for parallel operations
  - Build a function that retries failed promises

**Code Example**:
```javascript
// Async function with error handling
async function fetchUserData(userId) {
  try {
    const response = await fetch(`/api/users/${userId}`);
    if (!response.ok) throw new Error('User not found');
    const data = await response.json();
    return data;
  } catch (error) {
    console.error('Error fetching user:', error);
    throw error;
  }
}
```

---

#### Day 10: API Calls & Fetch API
- **Topics to Cover**:
  - Fetch API basics
  - HTTP methods (GET, POST, PUT, DELETE)
  - Headers and request configuration
  - Response handling (json(), text(), blob())
  - Error handling in API calls
  - CORS basics
  - Axios library introduction

- **Tasks**:
  - Make GET requests to a public API (JSONPlaceholder)
  - Create POST requests with request body
  - Handle different response statuses
  - Build a simple weather app using free API
  - Compare fetch vs axios

**Code Example**:
```javascript
// Fetch with error handling
async function fetchAndDisplayPosts() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts');
    if (!response.ok) throw new Error(`HTTP error! status: ${response.status}`);
    const posts = await response.json();
    displayPosts(posts);
  } catch (error) {
    console.error('Failed to fetch posts:', error);
  }
}

// POST request
async function createPost(title, body) {
  const response = await fetch('https://jsonplaceholder.typicode.com/posts', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ title, body, userId: 1 })
  });
  return response.json();
}
```

---

### Week 3: ES6+ Features & Module System

#### Day 11-12: ES6+ Features
- **Topics to Cover**:
  - Template literals
  - Default parameters
  - Rest parameters (...args)
  - Spread operator in objects and arrays
  - Destructuring assignment (advanced)
  - for...of vs for...in loops
  - Symbol and iterators
  - Generators (basic understanding)

- **Tasks**:
  - Refactor old code using modern JavaScript features
  - Create flexible functions with rest/spread operators
  - Write template literal examples with expressions
  - Practice advanced destructuring patterns

**Code Example**:
```javascript
// Modern JavaScript features
const config = {
  host: 'localhost',
  port: 3000,
  timeout: 5000
};

// Spread operator
const newConfig = { ...config, port: 8080 };

// Destructuring with defaults
const { host, port = 3000, ssl = false } = config;

// Template literals with expressions
const message = `Server running on ${host}:${port}`;

// Rest parameters
const sum = (...numbers) => numbers.reduce((a, b) => a + b, 0);
```

---

#### Day 13-14: Modules & Code Organization
- **Topics to Cover**:
  - CommonJS (require/module.exports)
  - ES6 modules (import/export)
  - Default exports vs named exports
  - Importing specific functions/objects
  - Module patterns
  - File organization best practices
  - Introduction to bundlers (webpack, vite concepts)

- **Tasks**:
  - Create multiple JavaScript files with exports/imports
  - Practice default and named exports
  - Organize utility functions in separate modules
  - Create a small project with proper module structure

**Code Example**:
```javascript
// math.js - module with exports
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
export default { add, subtract };

// main.js - importing modules
import math, { add, subtract } from './math.js';
console.log(add(5, 3)); // 8
```

---

#### Day 15: Mini Project - Interactive Dashboard Mockup (HTML/CSS/JS)
- **Create**: A static HTML page with interactive features
- **Features**:
  - Fetch data from JSONPlaceholder API
  - Display data in table format
  - Filter and sort functionality
  - Search functionality using event listeners
  - Display loading state during API calls
  - Error handling with user-friendly messages

- **Deliverables**:
  - HTML file with semantic structure
  - CSS for styling (grid/flexbox layouts)
  - Organized JavaScript with multiple modules
  - Functional buttons and interactions

---

### Week 4: Advanced JavaScript & Preparation for TypeScript

#### Day 16-17: Classes & Prototypes
- **Topics to Cover**:
  - Constructor functions
  - Prototypes and prototype chain
  - ES6 classes
  - Inheritance (extends, super)
  - Static methods and properties
  - Getters and setters
  - Private fields (#)
  - instanceof operator

- **Tasks**:
  - Create class hierarchies (e.g., Animal → Dog, Cat)
  - Practice inheritance with super()
  - Implement private fields and methods
  - Convert prototype-based code to class syntax

**Code Example**:
```javascript
// ES6 Class with inheritance
class DataFetcher {
  #apiKey; // private field
  
  constructor(apiKey) {
    this.#apiKey = apiKey;
  }
  
  async fetch(endpoint) {
    const response = await fetch(endpoint, {
      headers: { 'Authorization': `Bearer ${this.#apiKey}` }
    });
    return response.json();
  }
}

class WeatherFetcher extends DataFetcher {
  async getWeather(city) {
    return this.fetch(`/api/weather/${city}`);
  }
}
```

---

#### Day 18-19: Error Handling & Debugging
- **Topics to Cover**:
  - Error types (Error, TypeError, ReferenceError, etc.)
  - try/catch/finally blocks
  - Custom error classes
  - Stack traces and debugging
  - Console methods (log, warn, error, assert, table)
  - Browser DevTools (breakpoints, stepping, watch)
  - Common pitfalls and how to avoid them

- **Tasks**:
  - Create custom error classes
  - Implement comprehensive error handling
  - Practice debugging with DevTools
  - Write defensive code with validation

**Code Example**:
```javascript
// Custom error class
class APIError extends Error {
  constructor(message, status, response) {
    super(message);
    this.name = 'APIError';
    this.status = status;
    this.response = response;
  }
}

// Usage with proper error handling
async function safeAPICall(url) {
  try {
    const response = await fetch(url);
    if (!response.ok) {
      throw new APIError('API request failed', response.status, response);
    }
    return await response.json();
  } catch (error) {
    if (error instanceof APIError) {
      console.error(`API Error [${error.status}]: ${error.message}`);
    } else {
      console.error('Unexpected error:', error);
    }
  }
}
```

---

#### Day 20: Week 4 Project - Weather Dashboard (Vanilla JS)
- **Create**: Functional weather dashboard
- **Features**:
  - Fetch weather data from Open-Meteo API (free, no key required)
  - Search for cities and display weather
  - Show current weather and forecast
  - Store user preferences in localStorage
  - Responsive design with CSS Grid
  - Error handling and loading states
  - Well-organized modules

- **Deliverables**:
  - index.html with semantic HTML
  - styles.css with responsive design
  - Multiple JS modules (api.js, ui.js, storage.js, main.js)
  - Git repository with commits at milestones

---

### Month 1 Summary
- ✅ Solid understanding of JavaScript fundamentals
- ✅ Comfortable with async operations and API calls
- ✅ Familiar with modern JavaScript (ES6+)
- ✅ Ability to build interactive web applications with vanilla JS
- ✅ Understanding of code organization and modules

---

## MONTH 2: TypeScript & React Basics
**Duration**: 4 weeks (20 days of learning)  
**Daily Time**: 4 hours  
**Total Hours**: ~80 hours

### Week 1: TypeScript Fundamentals

#### Day 1-2: TypeScript Basics & Setup
- **Topics to Cover**:
  - Why TypeScript (type safety, developer experience)
  - TypeScript compilation and configuration (tsconfig.json)
  - Setting up development environment (Node, npm, TypeScript)
  - Basic types: string, number, boolean, null, undefined
  - Type annotations for variables and functions
  - Inference vs explicit typing
  - Running TypeScript code (ts-node, compilation)

- **Setup Instructions**:
  ```bash
  npm init -y
  npm install -D typescript ts-node @types/node
  npx tsc --init
  ```

- **Tasks**:
  - Set up a TypeScript project
  - Write TypeScript files with type annotations
  - Understand compiler errors and fix them
  - Convert JavaScript code to TypeScript

**Code Example**:
```typescript
// Basic TypeScript example
let name: string = "Alice";
let age: number = 25;
let isStudent: boolean = true;

// Function with type annotations
function greet(name: string, age: number): string {
  return `Hello ${name}, you are ${age} years old`;
}

// Type inference
let score = 95; // TypeScript infers number type
```

---

#### Day 3-4: Interfaces & Types
- **Topics to Cover**:
  - Interfaces for objects
  - Type aliases vs interfaces
  - Optional properties (?)
  - Readonly properties
  - Function types
  - Union types (|)
  - Intersection types (&)
  - Type guards and type assertions

- **Tasks**:
  - Define interfaces for User, Product, Order
  - Practice optional and readonly properties
  - Write function type definitions
  - Use union types for flexible APIs
  - Implement type guards

**Code Example**:
```typescript
// Interfaces
interface User {
  id: number;
  name: string;
  email: string;
  age?: number; // optional
  readonly createdAt: Date;
}

// Type alias
type Status = 'active' | 'inactive' | 'pending';

// Function type
interface ApiResponse {
  data: User[];
  status: Status;
  message: string;
}

// Type guard
function isUser(obj: any): obj is User {
  return obj && obj.id && obj.name && obj.email;
}

// Usage
const user: User = {
  id: 1,
  name: "John",
  email: "john@example.com",
  createdAt: new Date()
};
```

---

#### Day 5-6: Generics & Advanced Types
- **Topics to Cover**:
  - Generic functions
  - Generic interfaces and classes
  - Type constraints
  - Keyof operator
  - Conditional types (basic)
  - Mapped types (basic)
  - Utility types (Partial, Required, Record, Pick, Omit)
  - Enum types

- **Tasks**:
  - Create generic functions for different data types
  - Write a generic API response wrapper
  - Use utility types to create new types
  - Practice constraints with generics
  - Define enums for status codes

**Code Example**:
```typescript
// Generic function
function createArray<T>(element: T, length: number): T[] {
  return Array(length).fill(element);
}

// Generic interface
interface ApiResponse<T> {
  data: T;
  status: number;
  message: string;
}

// Generic class
class Repository<T> {
  private items: T[] = [];
  
  add(item: T): void {
    this.items.push(item);
  }
  
  getAll(): T[] {
    return this.items;
  }
}

// Utility types
type UserPreview = Pick<User, 'name' | 'email'>;
type PartialUser = Partial<User>;
type UserReadonly = Readonly<User>;

// Enum
enum Status {
  Active = 'ACTIVE',
  Inactive = 'INACTIVE',
  Pending = 'PENDING'
}
```

---

#### Day 7: Decorators & Advanced Features
- **Topics to Cover**:
  - Decorators (class, method, property, parameter)
  - Enabling decorators in tsconfig.json
  - Practical decorator patterns
  - Abstract classes
  - Access modifiers (public, private, protected)
  - Module declaration (d.ts files)

- **Tasks**:
  - Create a simple logging decorator
  - Use access modifiers in classes
  - Understand abstract classes
  - Practice with readonly and private fields

**Code Example**:
```typescript
// Decorator example
function log(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
  const originalMethod = descriptor.value;
  
  descriptor.value = function(...args: any[]) {
    console.log(`Calling ${propertyKey} with args:`, args);
    return originalMethod.apply(this, args);
  };
  
  return descriptor;
}

// Abstract class
abstract class Shape {
  abstract area(): number;
  
  describe(): string {
    return `Area: ${this.area()}`;
  }
}

class Circle extends Shape {
  constructor(private radius: number) {
    super();
  }
  
  area(): number {
    return Math.PI * this.radius ** 2;
  }
}
```

---

### Week 2: React Fundamentals

#### Day 8-9: React Setup & JSX
- **Topics to Cover**:
  - React fundamentals and virtual DOM
  - Setting up React with Create React App or Vite
  - JSX syntax and compilation
  - Functional components vs class components
  - JSX rules and best practices
  - Rendering elements
  - Component structure

- **Setup**:
  ```bash
  npm create vite@latest my-react-app -- --template react-ts
  cd my-react-app
  npm install
  npm run dev
  ```

- **Topics to Cover**:
  - JSX syntax and how it compiles to JavaScript
  - HTML-like syntax in JavaScript
  - Embedding expressions in JSX
  - JSX children and fragments
  - className vs class
  - Event handlers in JSX

- **Tasks**:
  - Create multiple functional components
  - Practice JSX syntax and expressions
  - Understand component composition
  - Convert HTML pages to React components

**Code Example**:
```typescript
// Functional component with TypeScript
interface GreetingProps {
  name: string;
  age: number;
}

const Greeting: React.FC<GreetingProps> = ({ name, age }) => {
  return (
    <div>
      <h1>Hello, {name}!</h1>
      <p>You are {age} years old</p>
    </div>
  );
};

export default Greeting;
```

---

#### Day 10-11: Props & State
- **Topics to Cover**:
  - Props and prop drilling
  - Default props
  - Children prop (children as JSX.Element)
  - useState hook
  - State updates and re-renders
  - State immutability
  - Handling form inputs with state

- **Tasks**:
  - Create components with multiple props
  - Build a counter component with useState
  - Create form components with controlled inputs
  - Practice parent-child data flow
  - Build a simple note-taking app

**Code Example**:
```typescript
// Counter component with state
interface CounterProps {
  initialValue?: number;
}

const Counter: React.FC<CounterProps> = ({ initialValue = 0 }) => {
  const [count, setCount] = useState(initialValue);
  
  const increment = () => setCount(count + 1);
  const decrement = () => setCount(count - 1);
  
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>+</button>
      <button onClick={decrement}>-</button>
    </div>
  );
};

// Form component with controlled inputs
const UserForm: React.FC = () => {
  const [name, setName] = useState('');
  const [email, setEmail] = useState('');
  
  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault();
    console.log({ name, email });
  };
  
  return (
    <form onSubmit={handleSubmit}>
      <input 
        value={name} 
        onChange={(e) => setName(e.target.value)}
        placeholder="Name"
      />
      <input 
        value={email} 
        onChange={(e) => setEmail(e.target.value)}
        placeholder="Email"
      />
      <button type="submit">Submit</button>
    </form>
  );
};
```

---

#### Day 12-13: Hooks - useEffect & useReducer
- **Topics to Cover**:
  - useEffect hook and lifecycle
  - Dependency array and timing
  - Cleanup functions
  - useReducer hook
  - Custom hooks basics
  - Rules of hooks

- **Tasks**:
  - Fetch data from API using useEffect
  - Create components with side effects
  - Implement useReducer for complex state
  - Write a custom hook (useLocalStorage, useFetch)
  - Handle loading and error states

**Code Example**:
```typescript
// useEffect for data fetching
interface Post {
  id: number;
  title: string;
  body: string;
}

const PostList: React.FC = () => {
  const [posts, setPosts] = useState<Post[]>([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState<string | null>(null);
  
  useEffect(() => {
    const fetchPosts = async () => {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/posts');
        const data = await response.json();
        setPosts(data.slice(0, 10));
      } catch (err) {
        setError('Failed to fetch posts');
      } finally {
        setLoading(false);
      }
    };
    
    fetchPosts();
  }, []);
  
  if (loading) return <p>Loading...</p>;
  if (error) return <p>{error}</p>;
  
  return (
    <div>
      {posts.map(post => (
        <div key={post.id}>
          <h2>{post.title}</h2>
          <p>{post.body}</p>
        </div>
      ))}
    </div>
  );
};

// useReducer for complex state
interface State {
  count: number;
  error: string | null;
}

type Action = 
  | { type: 'INCREMENT' }
  | { type: 'DECREMENT' }
  | { type: 'RESET' }
  | { type: 'SET_ERROR'; payload: string };

const reducer = (state: State, action: Action): State => {
  switch (action.type) {
    case 'INCREMENT':
      return { ...state, count: state.count + 1, error: null };
    case 'DECREMENT':
      return { ...state, count: state.count - 1, error: null };
    case 'RESET':
      return { count: 0, error: null };
    case 'SET_ERROR':
      return { ...state, error: action.payload };
    default:
      return state;
  }
};

const Counter: React.FC = () => {
  const [state, dispatch] = useReducer(reducer, { count: 0, error: null });
  
  return (
    <div>
      <p>Count: {state.count}</p>
      {state.error && <p style={{ color: 'red' }}>{state.error}</p>}
      <button onClick={() => dispatch({ type: 'INCREMENT' })}>+</button>
      <button onClick={() => dispatch({ type: 'DECREMENT' })}>-</button>
      <button onClick={() => dispatch({ type: 'RESET' })}>Reset</button>
    </div>
  );
};
```

---

#### Day 14: Week 2 Project - Todo App with React
- **Create**: A fully functional todo application
- **Features**:
  - Add, delete, and mark todos as complete
  - Persist todos to localStorage
  - Filter todos (all, completed, pending)
  - Edit todo text
  - Clear all completed todos
  - Display todo count

- **Deliverables**:
  - Functional React components
  - TypeScript interfaces for todos
  - useEffect for localStorage sync
  - useState for state management
  - Styled with CSS (flexbox/grid)

---

### Week 3: React Patterns & State Management Introduction

#### Day 15-16: Context API & Prop Drilling Solutions
- **Topics to Cover**:
  - React Context API
  - createContext and useContext
  - Provider components
  - Avoiding prop drilling
  - Context patterns (theme, auth, notifications)
  - Combining multiple contexts

- **Tasks**:
  - Create a theme context (light/dark mode)
  - Implement user authentication context
  - Create a notifications context
  - Practice useContext hook

**Code Example**:
```typescript
// Theme context
interface ThemeContextType {
  theme: 'light' | 'dark';
  toggleTheme: () => void;
}

const ThemeContext = createContext<ThemeContextType | undefined>(undefined);

export const ThemeProvider: React.FC<{ children: React.ReactNode }> = ({ children }) => {
  const [theme, setTheme] = useState<'light' | 'dark'>('light');
  
  const toggleTheme = () => {
    setTheme(prev => prev === 'light' ? 'dark' : 'light');
  };
  
  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
};

export const useTheme = () => {
  const context = useContext(ThemeContext);
  if (!context) {
    throw new Error('useTheme must be used within ThemeProvider');
  }
  return context;
};

// Usage in component
const ThemeSwitcher: React.FC = () => {
  const { theme, toggleTheme } = useTheme();
  
  return (
    <button onClick={toggleTheme}>
      Switch to {theme === 'light' ? 'dark' : 'light'} mode
    </button>
  );
};
```

---

#### Day 17-18: Introduction to State Management (Redux/Zustand basics)
- **Topics to Cover**:
  - Redux fundamentals (actions, reducers, store)
  - Redux Toolkit (simpler Redux setup)
  - Alternative: Zustand (simpler state management)
  - Redux DevTools for debugging
  - Connecting Redux to React components (useSelector, useDispatch)

- **Setup (Redux Toolkit)**:
  ```bash
  npm install @reduxjs/toolkit react-redux
  ```

- **Tasks**:
  - Set up a simple Redux store
  - Create actions and reducers
  - Connect components to Redux
  - Practice dispatching actions
  - Implement a shopping cart with Redux

**Code Example (Redux Toolkit)**:
```typescript
// store/counterSlice.ts
import { createSlice, PayloadAction } from '@reduxjs/toolkit';

interface CounterState {
  value: number;
}

const initialState: CounterState = {
  value: 0,
};

const counterSlice = createSlice({
  name: 'counter',
  initialState,
  reducers: {
    increment: (state) => {
      state.value += 1;
    },
    decrement: (state) => {
      state.value -= 1;
    },
    incrementByAmount: (state, action: PayloadAction<number>) => {
      state.value += action.payload;
    },
  },
});

export const { increment, decrement, incrementByAmount } = counterSlice.actions;
export default counterSlice.reducer;

// store/index.ts
import { configureStore } from '@reduxjs/toolkit';
import counterReducer from './counterSlice';

export const store = configureStore({
  reducer: {
    counter: counterReducer,
  },
});

export type RootState = ReturnType<typeof store.getState>;
export type AppDispatch = typeof store.dispatch;

// Component
import { useAppDispatch, useAppSelector } from '../hooks';
import { increment, decrement, incrementByAmount } from '../store/counterSlice';

const Counter: React.FC = () => {
  const dispatch = useAppDispatch();
  const count = useAppSelector(state => state.counter.value);
  
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => dispatch(increment())}>+</button>
      <button onClick={() => dispatch(decrement())}>-</button>
      <button onClick={() => dispatch(incrementByAmount(5))}>Add 5</button>
    </div>
  );
};
```

---

#### Day 19: UI Components & Styling (Tailwind CSS + UI Library)
- **Topics to Cover**:
  - Tailwind CSS setup and utility classes
  - Responsive design with Tailwind
  - Component libraries (Material-UI or Chakra UI)
  - Installing and using UI components
  - Theming and customization
  - Combining Tailwind with UI libraries

- **Setup**:
  ```bash
  npm install -D tailwindcss postcss autoprefixer
  npx tailwindcss init -p
  
  # Or with component library
  npm install @chakra-ui/react @emotion/react @emotion/styled framer-motion
  ```

- **Tasks**:
  - Style components with Tailwind CSS
  - Use pre-built UI components (buttons, cards, modals)
  - Create responsive layouts
  - Implement a component library in project

**Code Example (Chakra UI)**:
```typescript
import { Box, Button, Input, FormControl, FormLabel } from '@chakra-ui/react';

const LoginForm: React.FC = () => {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  
  return (
    <Box maxW="md" mx="auto" mt={8}>
      <FormControl mb={4}>
        <FormLabel>Email</FormLabel>
        <Input
          type="email"
          value={email}
          onChange={(e) => setEmail(e.target.value)}
        />
      </FormControl>
      
      <FormControl mb={4}>
        <FormLabel>Password</FormLabel>
        <Input
          type="password"
          value={password}
          onChange={(e) => setPassword(e.target.value)}
        />
      </FormControl>
      
      <Button colorScheme="blue" width="full">
        Login
      </Button>
    </Box>
  );
};
```

---

#### Day 20: Week 3 Project - Dashboard Layout with Data
- **Create**: Multi-section dashboard with mock data
- **Features**:
  - Navigation/sidebar with routing basics
  - Multiple dashboard cards showing different data
  - Theme switcher (light/dark mode with Context)
  - Data visualization placeholder (charts will come next month)
  - Responsive layout with Tailwind/Chakra
  - Redux state for theme and sidebar state
  - Fetch sample data from API and display

- **Deliverables**:
  - Dashboard with 4-5 different sections
  - TypeScript interfaces for data structures
  - Context API for theme management
  - Redux for UI state
  - Chakra UI components with Tailwind styling
  - Responsive design

---

### Month 2 Summary
- ✅ Solid TypeScript fundamentals and patterns
- ✅ React hooks (useState, useEffect, useReducer, useContext)
- ✅ State management with Redux Toolkit
- ✅ Component composition and reusability
- ✅ UI styling with Tailwind and component libraries
- ✅ Building interactive React applications

---

## MONTH 3: Advanced React, State Management & Dashboard Projects
**Duration**: 4 weeks (20 days of learning)  
**Daily Time**: 4 hours  
**Total Hours**: ~80 hours

### Week 1: Advanced Hooks & Custom Hooks

#### Day 1-2: Custom Hooks & Hook Patterns
- **Topics to Cover**:
  - Creating custom hooks
  - useCallback and useMemo for performance
  - useRef hook for DOM access and mutable values
  - useLayoutEffect vs useEffect
  - Custom hook best practices
  - Sharing stateful logic between components

- **Tasks**:
  - Create useFetch custom hook
  - Create useLocalStorage custom hook
  - Create useForm custom hook
  - Implement useDebounce for search
  - Practice useCallback for event handlers

**Code Example**:
```typescript
// Custom hooks
const useFetch = <T>(url: string) => {
  const [data, setData] = useState<T | null>(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState<string | null>(null);
  
  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await fetch(url);
        if (!response.ok) throw new Error('Failed to fetch');
        const result = await response.json();
        setData(result);
      } catch (err) {
        setError(err instanceof Error ? err.message : 'Unknown error');
      } finally {
        setLoading(false);
      }
    };
    
    fetchData();
  }, [url]);
  
  return { data, loading, error };
};

const useLocalStorage = <T>(key: string, initialValue: T) => {
  const [storedValue, setStoredValue] = useState<T>(() => {
    try {
      const item = window.localStorage.getItem(key);
      return item ? JSON.parse(item) : initialValue;
    } catch (error) {
      console.error(error);
      return initialValue;
    }
  });
  
  const setValue = (value: T | ((val: T) => T)) => {
    try {
      const valueToStore = value instanceof Function ? value(storedValue) : value;
      setStoredValue(valueToStore);
      window.localStorage.setItem(key, JSON.stringify(valueToStore));
    } catch (error) {
      console.error(error);
    }
  };
  
  return [storedValue, setValue] as const;
};

const useForm = <T extends Record<string, any>>(initialValues: T) => {
  const [values, setValues] = useState(initialValues);
  const [errors, setErrors] = useState<Partial<T>>({});
  
  const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    const { name, value } = e.target;
    setValues(prev => ({ ...prev, [name]: value }));
  };
  
  const reset = () => setValues(initialValues);
  
  return { values, errors, handleChange, reset, setValues };
};

// Usage
const SearchUsers: React.FC = () => {
  const [searchTerm, setSearchTerm] = useState('');
  const debouncedSearchTerm = useDebounce(searchTerm, 500);
  const { data: results } = useFetch<User[]>(
    `/api/users?q=${debouncedSearchTerm}`
  );
  
  return (
    <div>
      <input
        value={searchTerm}
        onChange={(e) => setSearchTerm(e.target.value)}
        placeholder="Search users..."
      />
      {results && results.map(user => <div key={user.id}>{user.name}</div>)}
    </div>
  );
};
```

---

#### Day 3-4: Advanced React Patterns
- **Topics to Cover**:
  - Render props pattern
  - Higher-order components (HOCs)
  - Compound components pattern
  - Hooks composition
  - Error boundaries
  - Lazy loading and code splitting
  - Suspense (basic understanding)

- **Tasks**:
  - Create an error boundary component
  - Implement lazy loading for routes
  - Use code splitting with React.lazy
  - Understand HOC pattern with examples
  - Create compound components

**Code Example**:
```typescript
// Error Boundary
class ErrorBoundary extends React.Component<
  { children: React.ReactNode },
  { hasError: boolean; error: Error | null }
> {
  constructor(props: { children: React.ReactNode }) {
    super(props);
    this.state = { hasError: false, error: null };
  }
  
  static getDerivedStateFromError(error: Error) {
    return { hasError: true, error };
  }
  
  render() {
    if (this.state.hasError) {
      return <h1>Something went wrong: {this.state.error?.message}</h1>;
    }
    return this.props.children;
  }
}

// Code splitting with lazy
const Dashboard = React.lazy(() => import('./Dashboard'));
const Settings = React.lazy(() => import('./Settings'));

const App: React.FC = () => {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <ErrorBoundary>
        <Dashboard />
      </ErrorBoundary>
    </Suspense>
  );
};

// Compound Components
const Dropdown: React.FC<{ children: React.ReactNode }> = ({ children }) => {
  const [isOpen, setIsOpen] = useState(false);
  
  return (
    <div>
      {React.Children.map(children, child =>
        React.cloneElement(child as React.ReactElement, { isOpen, setIsOpen })
      )}
    </div>
  );
};

const DropdownTrigger: React.FC<{ isOpen: boolean; setIsOpen: any }> = ({
  isOpen,
  setIsOpen,
}) => (
  <button onClick={() => setIsOpen(!isOpen)}>Toggle</button>
);

const DropdownContent: React.FC<{ isOpen: boolean; children: React.ReactNode }> = ({
  isOpen,
  children,
}) => isOpen ? <div>{children}</div> : null;

Dropdown.Trigger = DropdownTrigger;
Dropdown.Content = DropdownContent;

// Usage
<Dropdown>
  <Dropdown.Trigger />
  <Dropdown.Content>
    <a href="#">Option 1</a>
  </Dropdown.Content>
</Dropdown>
```

---

### Week 2: Data Visualization & Chart Libraries

#### Day 5-6: Chart Libraries & Data Visualization
- **Topics to Cover**:
  - Recharts library for React
  - Chart.js for React
  - D3.js basics (optional advanced)
  - Common chart types (line, bar, pie, scatter)
  - Real-time data updates
  - Responsive charts
  - Custom tooltips and legends

- **Setup**:
  ```bash
  npm install recharts
  # or
  npm install react-chartjs-2 chart.js
  ```

- **Tasks**:
  - Create line charts for time series data
  - Build bar charts for category comparisons
  - Create pie charts for distributions
  - Implement responsive charts
  - Add interactive features (click, hover)
  - Combine multiple chart types

**Code Example (Recharts)**:
```typescript
import {
  LineChart,
  Line,
  BarChart,
  Bar,
  PieChart,
  Pie,
  XAxis,
  YAxis,
  CartesianGrid,
  Tooltip,
  Legend,
  ResponsiveContainer,
} from 'recharts';

interface SalesData {
  date: string;
  sales: number;
  profit: number;
}

const SalesChart: React.FC<{ data: SalesData[] }> = ({ data }) => {
  return (
    <ResponsiveContainer width="100%" height={300}>
      <LineChart data={data}>
        <CartesianGrid strokeDasharray="3 3" />
        <XAxis dataKey="date" />
        <YAxis />
        <Tooltip />
        <Legend />
        <Line type="monotone" dataKey="sales" stroke="#8884d8" />
        <Line type="monotone" dataKey="profit" stroke="#82ca9d" />
      </LineChart>
    </ResponsiveContainer>
  );
};

// Pie chart example
interface Distribution {
  name: string;
  value: number;
}

const DistributionChart: React.FC<{ data: Distribution[] }> = ({ data }) => {
  return (
    <ResponsiveContainer width="100%" height={300}>
      <PieChart>
        <Pie
          data={data}
          cx="50%"
          cy="50%"
          labelLine={false}
          label={({ name, value }) => `${name}: ${value}`}
          outerRadius={80}
          fill="#8884d8"
          dataKey="value"
        />
        <Tooltip />
      </PieChart>
    </ResponsiveContainer>
  );
};
```

---

#### Day 7-8: Advanced Data Visualization & Real-time Updates
- **Topics to Cover**:
  - Updating charts with new data
  - WebSocket integration for real-time data
  - Animation and transitions
  - Custom chart components
  - Handling large datasets
  - Performance optimization for charts

- **Tasks**:
  - Create a live updating chart
  - Implement chart filtering and time range selection
  - Build a dashboard with multiple chart types
  - Practice responsive chart layouts
  - Handle streaming data

**Code Example**:
```typescript
interface ChartDataPoint {
  timestamp: number;
  value: number;
}

const LiveChart: React.FC = () => {
  const [data, setData] = useState<ChartDataPoint[]>([]);
  
  useEffect(() => {
    const interval = setInterval(() => {
      setData(prev => [
        ...prev.slice(-19), // Keep last 20 points
        {
          timestamp: Date.now(),
          value: Math.random() * 100,
        },
      ]);
    }, 1000);
    
    return () => clearInterval(interval);
  }, []);
  
  return (
    <ResponsiveContainer width="100%" height={300}>
      <LineChart data={data}>
        <CartesianGrid />
        <XAxis 
          dataKey="timestamp" 
          tickFormatter={(time) => new Date(time).toLocaleTimeString()}
        />
        <YAxis />
        <Tooltip />
        <Line
          type="monotone"
          dataKey="value"
          stroke="#8884d8"
          isAnimationActive={false}
        />
      </LineChart>
    </ResponsiveContainer>
  );
};
```

---

### Week 3: Advanced State Management & API Integration

#### Day 9-10: Redux Advanced Patterns
- **Topics to Cover**:
  - Redux middleware (Redux Thunk, Redux Saga basics)
  - Async thunks (createAsyncThunk)
  - Normalized state structure
  - Selectors and reselect library
  - Redux DevTools advanced features
  - Performance optimization with Redux

- **Tasks**:
  - Implement async API calls with Redux Thunk
  - Create normalized state structures
  - Use selectors for derived data
  - Practice middleware patterns
  - Debug with Redux DevTools

**Code Example**:
```typescript
// Async thunk for API calls
import { createAsyncThunk, createSlice } from '@reduxjs/toolkit';

interface User {
  id: number;
  name: string;
  email: string;
}

interface UsersState {
  items: User[];
  status: 'idle' | 'loading' | 'succeeded' | 'failed';
  error: string | null;
}

export const fetchUsers = createAsyncThunk(
  'users/fetchUsers',
  async (_, { rejectWithValue }) => {
    try {
      const response = await fetch('/api/users');
      if (!response.ok) throw new Error('Failed to fetch users');
      return await response.json();
    } catch (error) {
      return rejectWithValue(
        error instanceof Error ? error.message : 'Unknown error'
      );
    }
  }
);

const usersSlice = createSlice({
  name: 'users',
  initialState: {
    items: [],
    status: 'idle',
    error: null,
  } as UsersState,
  reducers: {},
  extraReducers: (builder) => {
    builder
      .addCase(fetchUsers.pending, (state) => {
        state.status = 'loading';
      })
      .addCase(fetchUsers.fulfilled, (state, action) => {
        state.status = 'succeeded';
        state.items = action.payload;
      })
      .addCase(fetchUsers.rejected, (state, action) => {
        state.status = 'failed';
        state.error = action.payload as string;
      });
  },
});

export default usersSlice.reducer;

// Selectors
export const selectUsers = (state: RootState) => state.users.items;
export const selectUsersStatus = (state: RootState) => state.users.status;
export const selectUsersError = (state: RootState) => state.users.error;

// Memoized selector with reselect
import { createSelector } from '@reduxjs/toolkit';

export const selectUsersByName = createSelector(
  [selectUsers, (_, name: string) => name],
  (users, name) => users.filter(u => u.name.includes(name))
);
```

---

#### Day 11-12: API Integration & Error Handling
- **Topics to Cover**:
  - Axios vs Fetch API
  - Request/response interceptors
  - Error handling strategies
  - Retry logic
  - Request cancellation
  - Rate limiting
  - API authentication (tokens, headers)

- **Setup**:
  ```bash
  npm install axios
  ```

- **Tasks**:
  - Create an axios instance with interceptors
  - Implement token-based authentication
  - Add global error handling
  - Create a request retry mechanism
  - Handle API errors gracefully

**Code Example**:
```typescript
// API service with axios
import axios, { AxiosInstance, AxiosError } from 'axios';

interface ApiConfig {
  baseURL: string;
  timeout: number;
  token?: string;
}

class ApiService {
  private client: AxiosInstance;
  
  constructor(config: ApiConfig) {
    this.client = axios.create({
      baseURL: config.baseURL,
      timeout: config.timeout,
    });
    
    // Request interceptor
    this.client.interceptors.request.use((config) => {
      if (config.token) {
        config.headers.Authorization = `Bearer ${config.token}`;
      }
      return config;
    });
    
    // Response interceptor
    this.client.interceptors.response.use(
      (response) => response.data,
      (error: AxiosError) => {
        console.error('API Error:', error);
        throw error;
      }
    );
  }
  
  async get<T>(url: string): Promise<T> {
    return this.client.get<T>(url);
  }
  
  async post<T>(url: string, data: any): Promise<T> {
    return this.client.post<T>(url, data);
  }
}

// Usage
const apiService = new ApiService({
  baseURL: 'http://localhost:8000/api',
  timeout: 10000,
  token: localStorage.getItem('token') || undefined,
});

interface UserResponse {
  id: number;
  name: string;
  email: string;
}

const getUser = async (id: number) => {
  try {
    const user = await apiService.get<UserResponse>(`/users/${id}`);
    return user;
  } catch (error) {
    console.error('Failed to fetch user:', error);
    throw error;
  }
};
```

---

### Week 4: Complete Dashboard Project

#### Day 13-20: Full Dashboard Application Project

**Project Overview**: Build a complete, production-level data dashboard that integrates with a FastAPI backend.

**Project Structure**:
```
dashboard-app/
├── src/
│   ├── components/
│   │   ├── Layout/
│   │   │   ├── Sidebar.tsx
│   │   │   ├── Header.tsx
│   │   │   └── Layout.tsx
│   │   ├── Dashboard/
│   │   │   ├── OverviewCards.tsx
│   │   │   ├── SalesChart.tsx
│   │   │   ├── UserAnalytics.tsx
│   │   │   └── DataTable.tsx
│   │   ├── Common/
│   │   │   ├── Button.tsx
│   │   │   ├── Card.tsx
│   │   │   ├── Modal.tsx
│   │   │   └── Loading.tsx
│   │   └── Charts/
│   │       ├── LineChart.tsx
│   │       ├── BarChart.tsx
│   │       └── PieChart.tsx
│   ├── hooks/
│   │   ├── useFetch.ts
│   │   ├── useLocalStorage.ts
│   │   └── useAsync.ts
│   ├── store/
│   │   ├── slices/
│   │   │   ├── dashboardSlice.ts
│   │   │   ├── themeSlice.ts
│   │   │   └── userSlice.ts
│   │   └── index.ts
│   ├── services/
│   │   ├── api.ts
│   │   └── dashboard.ts
│   ├── types/
│   │   ├── dashboard.ts
│   │   ├── user.ts
│   │   └── api.ts
│   ├── pages/
│   │   ├── DashboardPage.tsx
│   │   ├── AnalyticsPage.tsx
│   │   ├── SettingsPage.tsx
│   │   └── NotFoundPage.tsx
│   ├── App.tsx
│   └── main.tsx
├── public/
├── package.json
├── tsconfig.json
├── vite.config.ts
└── README.md
```

**Features to Implement**:

1. **Authentication** (Day 13-14)
   - Login form with validation
   - Token storage and management
   - Protected routes
   - Logout functionality

2. **Dashboard Overview** (Day 14-15)
   - Key metrics cards (total users, revenue, etc.)
   - Summary statistics
   - Quick actions
   - Recent activity feed

3. **Data Visualization** (Day 15-16)
   - Sales/revenue trends (line chart)
   - Product/category distribution (pie chart)
   - User growth analytics (bar chart)
   - Custom time range selector

4. **Data Table** (Day 16-17)
   - Sortable columns
   - Pagination
   - Search/filter functionality
   - Edit/delete actions
   - Bulk actions

5. **Theme & Settings** (Day 17-18)
   - Dark/light mode toggle (Context API)
   - User preferences saved to localStorage
   - Settings page
   - Responsive layout

6. **State Management** (Day 18-19)
   - Redux for global state
   - Async data fetching with createAsyncThunk
   - Selectors for derived data
   - Proper error handling

7. **Testing & Polish** (Day 19-20)
   - Error boundaries
   - Loading states
   - Empty states
   - Error messages
   - Final refinement and deployment preparation

**FastAPI Backend Integration**:

**Expected API Endpoints**:
```
GET  /api/auth/login
POST /api/auth/login
POST /api/auth/logout
GET  /api/dashboard/overview
GET  /api/dashboard/sales
GET  /api/dashboard/users
GET  /api/users
POST /api/users
PUT  /api/users/{id}
DELETE /api/users/{id}
GET  /api/analytics/trends
GET  /api/analytics/distribution
```

**Code Examples for Dashboard Components**:

```typescript
// services/api.ts
import axios from 'axios';

const API_BASE_URL = 'http://localhost:8000/api';

const apiClient = axios.create({
  baseURL: API_BASE_URL,
  timeout: 10000,
});

// Add token to requests
apiClient.interceptors.request.use((config) => {
  const token = localStorage.getItem('token');
  if (token) {
    config.headers.Authorization = `Bearer ${token}`;
  }
  return config;
});

export const dashboardApi = {
  getOverview: () => apiClient.get('/dashboard/overview'),
  getSalesData: (period: string) => apiClient.get(`/dashboard/sales?period=${period}`),
  getUserAnalytics: () => apiClient.get('/dashboard/users'),
  getUsers: (page: number, limit: number) =>
    apiClient.get(`/users?page=${page}&limit=${limit}`),
};

// store/slices/dashboardSlice.ts
import { createSlice, createAsyncThunk } from '@reduxjs/toolkit';
import { dashboardApi } from '../../services/api';

interface DashboardState {
  overview: any;
  salesData: any[];
  status: 'idle' | 'loading' | 'succeeded' | 'failed';
  error: string | null;
}

export const fetchDashboardData = createAsyncThunk(
  'dashboard/fetchData',
  async (_, { rejectWithValue }) => {
    try {
      const [overview, sales, users] = await Promise.all([
        dashboardApi.getOverview(),
        dashboardApi.getSalesData('month'),
        dashboardApi.getUserAnalytics(),
      ]);
      return { overview, sales, users };
    } catch (error) {
      return rejectWithValue('Failed to fetch dashboard data');
    }
  }
);

const dashboardSlice = createSlice({
  name: 'dashboard',
  initialState: {
    overview: null,
    salesData: [],
    status: 'idle',
    error: null,
  } as DashboardState,
  extraReducers: (builder) => {
    builder
      .addCase(fetchDashboardData.pending, (state) => {
        state.status = 'loading';
      })
      .addCase(fetchDashboardData.fulfilled, (state, action) => {
        state.status = 'succeeded';
        state.overview = action.payload.overview;
        state.salesData = action.payload.sales;
      })
      .addCase(fetchDashboardData.rejected, (state, action) => {
        state.status = 'failed';
        state.error = action.payload as string;
      });
  },
});

export default dashboardSlice.reducer;

// components/Dashboard/SalesChart.tsx
const SalesChart: React.FC = () => {
  const dispatch = useAppDispatch();
  const { salesData, status } = useAppSelector(state => state.dashboard);
  
  useEffect(() => {
    dispatch(fetchDashboardData());
  }, [dispatch]);
  
  if (status === 'loading') return <Loading />;
  if (status === 'failed') return <ErrorMessage />;
  
  return (
    <Card title="Sales Trends">
      <ResponsiveContainer width="100%" height={300}>
        <LineChart data={salesData}>
          <CartesianGrid />
          <XAxis dataKey="date" />
          <YAxis />
          <Tooltip />
          <Legend />
          <Line type="monotone" dataKey="sales" stroke="#8884d8" />
        </LineChart>
      </ResponsiveContainer>
    </Card>
  );
};
```

**Deployment Checklist**:
- [ ] TypeScript compilation without errors
- [ ] All API endpoints working
- [ ] Error handling for all async operations
- [ ] Loading states displayed
- [ ] Responsive design on all screen sizes
- [ ] Dark mode working correctly
- [ ] Token refresh handling
- [ ] Performance optimized (lazy loading, memoization)
- [ ] Environment variables configured (.env.local)
- [ ] Git repository with clean history

---

### Month 3 Summary
- ✅ Advanced React patterns and performance optimization
- ✅ Professional data visualization with charts
- ✅ Advanced state management with Redux
- ✅ API integration with error handling
- ✅ Complete, production-level dashboard application
- ✅ Ready for portfolio and interviews

---

## Mini Projects

Throughout the 3 months, complete these mini-projects:

### Project 1: Weather App (End of Month 1)
- **Tech Stack**: Vanilla JavaScript, HTML, CSS
- **Features**: Fetch weather data, display forecasts, localStorage
- **APIs**: Open-Meteo (free), or OpenWeatherMap

### Project 2: Todo App (Week 2, Month 2)
- **Tech Stack**: React, TypeScript, localStorage
- **Features**: Add/edit/delete todos, filters, persistence
- **State**: useState, useEffect

### Project 3: Dashboard Layout (Week 3, Month 2)
- **Tech Stack**: React, TypeScript, Chakra UI, Context API
- **Features**: Navigation, theme switcher, responsive layout
- **State**: Redux for UI state, Context for theme

### Project 4: Data Visualization Dashboard (Week 2, Month 3)
- **Tech Stack**: React, TypeScript, Recharts, Redux
- **Features**: Multiple chart types, filtering, real-time updates
- **State**: Redux with async thunks

### Project 5: Full Stack Dashboard (Week 4, Month 3)
- **Tech Stack**: React, TypeScript, Redux, Recharts, FastAPI backend
- **Features**: Authentication, CRUD operations, analytics, charts
- **Backend**: FastAPI with database integration

---

## Resources

### JavaScript Learning
- **MDN Web Docs**: https://developer.mozilla.org/en-US/docs/Web/JavaScript
- **JavaScript.info**: https://javascript.info/
- **You Don't Know JS**: https://github.com/getify/You-Dont-Know-JS

### TypeScript Learning
- **Official TypeScript Handbook**: https://www.typescriptlang.org/docs/
- **TypeScript Deep Dive**: https://basarat.gitbook.io/typescript/
- **Practical TypeScript**: https://www.typescriptlang.org/play/

### React Learning
- **Official React Documentation**: https://react.dev
- **React TypeScript Cheatsheet**: https://react-typescript-cheatsheet.netlify.app/
- **Epic React**: https://epicreact.dev (paid but comprehensive)

### State Management
- **Redux Official**: https://redux.js.org/
- **Redux Toolkit**: https://redux-toolkit.js.org/
- **Zustand**: https://github.com/pmndrs/zustand

### UI Libraries & Styling
- **Chakra UI**: https://chakra-ui.com/
- **Tailwind CSS**: https://tailwindcss.com/
- **Material-UI**: https://mui.com/

### Data Visualization
- **Recharts**: https://recharts.org/
- **Chart.js**: https://www.chartjs.org/
- **D3.js**: https://d3js.org/

### Tools & Setup
- **Node.js & npm**: https://nodejs.org/
- **Vite**: https://vitejs.dev/
- **TypeScript Playground**: https://www.typescriptlang.org/play

### Practice Platforms
- **LeetCode**: https://leetcode.com/ (JavaScript algorithms)
- **HackerRank**: https://www.hackerrank.com/ (React challenges)
- **Frontend Mentor**: https://www.frontendmentor.io/ (UI projects)

---

## Daily Study Tips

1. **First 1-1.5 hours**: Theory and concepts
   - Read documentation
   - Watch tutorial videos
   - Take notes

2. **Next 2-2.5 hours**: Hands-on coding
   - Implement examples
   - Build mini projects
   - Debug issues

3. **Last 30 minutes**: Review and planning
   - Review what you learned
   - Plan next day
   - Commit code to Git

## Git Workflow

```bash
# Initialize repo
git init
git add .
git commit -m "Initial commit"

# Daily commits
git add .
git commit -m "Day X: Topic - Description"

# End of week summary commit
git add .
git commit -m "Week X: Completed [topics]"
```

## Success Metrics

By the end of 3 months, you should be able to:
- ✅ Write production-level TypeScript code
- ✅ Build complex React applications with custom hooks
- ✅ Manage state efficiently with Redux
- ✅ Create data visualizations with Recharts
- ✅ Integrate React frontends with FastAPI backends
- ✅ Deploy dashboard applications
- ✅ Write clean, maintainable, and well-organized code
- ✅ Build a portfolio project for interviews

---

## Notes for Data Science Masters Transition

As you learn web development, keep these connections to data science in mind:

1. **JavaScript/React Skills for DS**:
   - Interactive dashboards for data analysis
   - Real-time data visualization
   - Building data apps for model deployment

2. **Recommended Additions Post-Roadmap**:
   - Learn Python data science stack (NumPy, Pandas, Scikit-learn)
   - Integrate ML models with React dashboards
   - Practice full-stack data applications

3. **Portfolio Projects for DS Masters**:
   - Build dashboards that visualize ML models
   - Create interactive data exploration tools
   - Develop end-to-end data pipeline with visualization

4. **Continue Learning**:
   - Deep dive into Python after Month 3
   - Advanced SQL for data querying
   - Cloud platforms (AWS, GCP) for deployment
   - Docker and containerization

---

**Good luck on your learning journey! Stay consistent, commit daily, and enjoy building! 🚀**
