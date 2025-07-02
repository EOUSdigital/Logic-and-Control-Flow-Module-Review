# 📗 Module 5: Logic and Control Flow – Lesson 11. Module Review

## 🧠 Step 1: Explore the Topic

```javascript
🎯 What Is Logic and Control Flow in JavaScript?
Logic and control flow govern how code **decides**, **branches**, and **repeats** actions in response to inputs or conditions.
```

### 🔑 Core Concepts Reviewed

1. **Conditional Statements**: `if`, `else if`, `else`

```javascript
• Direct the program to execute certain blocks of code only if specific conditions are met.
• Used for decision-making:

if (score > 90) {
    console.log("Excellent");
} else if (score > 70) {
    console.log("Good");
} else {
    console.log("Needs improvement");
}
```

2. **Nesting**: Control structures inside other structures

```javascript
• Placing control structures inside one another.
• Be careful: too much nesting can reduce readability.
```

3. **Comparison & Logical Operators**: `==`, `===`, `&&`, `||`, `!`

```javascript
• Comparison: ==, ===, !=, !==, <, >, <=, >=
• Logical: &&, ||, ! — combine or negate boolean expressions.
```

4. **Switch Statements**: Cleaner than many `if-else` conditions

```javascript
• A clean alternative to many if-else if chains.

switch (role) {
    case 'admin': console.log("Admin panel");   break;
    case 'user': console.log("User Dashboard"); break;
    default: console.log("Guest");
}
```

5. **Ternary Operator**: `condition ? trueValue : falseValue`

```javascript
• A concise way to write simple conditional logic.

let access = isLoggedIn ? "Welcome" : "Please log in";

1. The conditional (ternary) operator is the only JavaScript operator that takes three operands: a condition followed by a question mark (?), then an expression to execute if the condition is truthy followed by a colon (:), and finally the expression to execute if the condition is falsy. This operator is frequently used as an alternative to an if...else statement.

• Syntax: 

condition ? exprIfTrue : exprIfFalse

• Parameters

condition: An expression whose value is used as a condition.

• exprIfTrue: An expression which is executed if the condition evaluates to a truthy value (one which equals or can be converted to true).

• exprIfFalse: An expression which is executed if the condition is falsy (that is, has a value which can be converted to false).

2. In the ternary operator syntax condition ? expressionIfTrue : expressionIfFalse, the "?" acts like an IF — it checks the condition and, if true, executes the first expression. The ":" acts like an ELSE — if the condition is false, it executes the second expression.

We can interpret the ternary operator as a compact form of:
•   ? → IF
•   : → ELSE

let result = score >= 50 ? "Pass" : "Fail";

• Description

Besides false, possible falsy expressions are: null, NaN, 0, the empty string (""), and undefined. If condition is any of these, the result of the conditional expression will be the result of executing the expression exprIfFalse.

• Examples:

• A. basic example

const age = 26;
const beverage = age >= 21 ? "Beer" : "Justice";
console.log(beverage);                              "Beer"

• B. Handling null values

One common usage is to handle a value that may be null:

const greeting = (person) => {
    const name = person ? person.name : "stranger";
    return `Howdy, ${name}`;
};

console.log(greeting({ name: "Alice" }));
console.log(greeting(null));

• C. Conditional chains

The ternary operator is right-associative, which means it can be "chained" in the following way, similar to an if … else if … else if … else chain:

function example() {
    return condition1 ? value1
        : condition2 ? value2
        : condition3 ? value3
        : value4;
}

• This is equivalent to the following if...else chain.

function examples() {
    if (condition1) {
        return value1;
    } else if (condition2) {
        return value2;
    } else if (condition3) {
        return value3;
    } else {
        return value4;
    }
}
```

6. **Loops and Iteration**: `for`, `while`, `do...while`, `for...of`

```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

7. **Logical Assignment Operators**: `||=`, `&&=`, `??=`

```javascript
user.name ||= "Guest";
config.debug &&= false;
settings.theme ??= "light";


A. Logical OR assignment (||=)

The logical OR assignment (||=) operator only evaluates the right operand and assigns to the left if the left operand is falsy.

Example:

const a = { duration: 50, title: "" };

a.duration ||= 10;
console.log(a.duration);
// Expected output: 50

a.title ||= "title is empty.";
console.log(a.title);
// Expected output: "title is empty."

Syntax:

x ||= y;

• Description:

1. Logical OR assignment short-circuits, meaning that x ||= y is equivalent to x || (x = y), except that the expression x is only evaluated once.
2. No assignment is performed if the left-hand side is not falsy, due to short-circuiting of the logical OR operator. For example, the following does not throw an error, despite x being const:

const z = 1;
z ||= 2;


B. Logical AND assignment (&&=)

The logical AND assignment (&&=) operator only evaluates the right operand and assigns to the left if the left operand is truthy.

• Example:

let c = 1;
let b = 0;

c &&= 2;
console.log(c);
// Expected output: 2

b &&= 2;
console.log(b);
// Expected output: 0

• Syntax

x &&= y;

• Description:

1. Logical AND assignment short-circuits, meaning that x &&= y is equivalent to x && (x = y), except that the expression x is only evaluated once.
2. No assignment is performed if the left-hand side is not truthy, due to short-circuiting of the logical AND operator. For example, the following does not throw an error, despite x being const:

const x = 0;
x &&= 2;


C. Nullish coalescing assignment (??=)

The nullish coalescing assignment (??=) operator, also known as the logical nullish assignment operator, only evaluates the right operand and assigns to the left if the left operand is nullish (null or undefined).

• Example:

const d = { duration: 50 };

d.speed ??= 25;
console.log(d.speed);
// Expected output: 25

d.duration ??= 10;
console.log(d.duration);
// Expected output: 50

• Syntax:

x ??= y;

• Description:

1. Nullish coalescing assignment short-circuits, meaning that x ??= y is equivalent to x ?? (x = y), except that the expression x is only evaluated once.
2. No assignment is performed if the left-hand side is not nullish, due to short-circuiting of the nullish coalescing operator. For example, the following does not throw an error, despite x being const:

const y = 1;
y ??= 2;
```

8. **Practical Logic Patterns**: guard clauses, defaults, short-circuiting

```javascript
• Common reusable logic structures:
    → Guard clauses
    → Short-circuiting
    → Default parameters
    → Ternary in assignments
    → Switch for clean flow
```

9.  **Truthy and Falsy**: values that implicitly behave like `true` or `false`

```javascript
• Every value is either "truthy" or "falsy" in conditionals.
    → Falsy: false, 0, "", null, undefined, NaN
    → Truthy: everything else (including [], {}, "0")

if (!email) console.log("Email is required");

🧠 Why This Matters
Understanding control flow is foundational to all programming:
  • It determines what code runs when
  • It's essential for debugging
  • It prepares you for real-world decision logic, forms, APIs, dynamic content, etc.

```

---

## 🧩 Step 2: Real-World Example

### Scenario: Login & Access Control System

```javascript
🌐 Scenario: Login & Dashboard Access Control System
  • Imagine we are building the access system for a website. We need to:
  • Validate login credentials
  • Assign access based on user role
  • Display messages based on subscription and status
  • Handle missing inputs gracefully
  • Track login attempts with a loop

* 🧠 Concepts in Action

function login(user) {
    // Guard clause (Practical Logic Pattern)
    if (!user.username || !user.password) {
        console.log("Missing credentials");
        return;
    }

    // Logical assignment – default fallback
    user.role ||= "guest";
    user.subscribed ??= false;

    // Comparison and Logical operators
    if (user.isBanned || user.failedAttempts > 3) {
        console.log("Access denied");
        return;
    }

    // Switch statement for role-based access
    switch (user.role) {
        case "admin":
        console.log("Redirect to Admin Dashboard");
        break;
        case "editor":
        console.log("Open Content Manager");
        break;
        case "subscriber":
        console.log("Welcome to Premium Content");
        break;
        default:
        console.log("Limited access: Guest");
    }

    // Truthy check
    if (user.subscribed) {
        console.log("Thank you for subscribing!");
    }

    // Ternary for quick decision
    let greeting = user.username ? `Welcome, ${user.username}` : "Welcome, Guest";
    console.log(greeting);

    // Loop for login attempts log
    for (let i = 0; i < user.failedAttempts; i++) {
        console.log(`⚠️ Failed login attempt #${i + 1}`);
    }
}

🧪 Sample Input

login({
    username: "Jasmine",
    password: "secure123",
    role: "subscriber",
    subscribed: true,
    failedAttempts: 2,
});

✅ Output

  • Welcome to Premium Content
  • Thank you for subscribing!
  • Welcome, Jasmine
  • ⚠️ Failed login attempt #1
  • ⚠️ Failed login attempt #2

🧠 Recap of Concepts Used:

  ☑️Concept                            ✅ How It is Used
  • Guard Clause                        Early return for missing credentials
  • Logical Assignment (``)
  • Nullish Coalescing (??=)            Only set subscribed if null or undefined
  • if / else                           Check for bans or failed attempts
  • switch                              Determine what to show based on role
  • Ternary                             Inline greeting based on username
  • Loop (for)                          Repeat log for failed login attempts
  • Truthy/Falsy                        Checks	Confirm subscribed or missing fields
```

---

## 📝 Step 3: Quiz Evaluation

### ✅ Your Answers and Results

⚙️ Instructions: Select the best answer for each question. 

```javascript
1. What does this code log?

let role2 = "";
let access2 = role2 || "guest";
console.log(access2);

A. ""
B. undefined
C. null
D. "guest"

Answer: D

2. Which keyword is used to exit a function early?
A. end
B. break
C. return
D. stop

Answer: C

3. What is the result of this comparison?

5 == "5"

A. true
B. false
C. undefined
D. error

Answer: A

4. Which of these values is truthy?
A. ""
B. 0
C. []
D. null

Answer: C

5. What does the following ternary expression evaluate to?

let isAdmin = false;
let message = isAdmin ? "Access granted" : "Access denied";

A. "Access granted"
B. "Access denied"
C. undefined
D. false

Answer: B

6. What will this code output?

let value;
value ??= "default";
console.log(value);

A. undefined
B. "default"
C. false
D. null

Answer: B

7. Which structure is best for handling multiple possible values of a single variable?
A. if-else
B. switch
C. loop
D. try-catch

Answer: B

8. How many times does this loop run?

for (let i = 0; i < 3; i++) {
    console.log(i);
}

A. 2
B. 3
C. 4
D. Infinite

Answer: B

9. What does this logical assignment do?

settings.theme ||= "light";

A. Always sets theme to "light"
B. Sets theme only if it's falsy
C. Sets theme only if it's truthy
D. Throws an error if theme is undefined

Answer: B

10. What does this guard clause do?

function process(user) {
    if (!user) return;
    console.log("Processing user");
}

A. Prevents code from running if user is missing
B. Always runs console.log
C. Throws an error if user is undefined
D. Declares a function without parameters

Answer: A
```
---

### ☑️ Quiz Evaluation

```javascript
1. D – "guest" ✅
✔️ "" is falsy, so || falls back to "guest".

2. C – return ✅
✔️ return exits the function immediately.

3. A – true ✅
✔️ == allows type coercion: "5" becomes 5.

4. C – [] ✅
✔️ An empty array is a truthy value in JavaScript.

5. B – "Access denied" ✅
✔️ false ? A : B → picks the second option.

6. B – "default" ✅
✔️ value is undefined, so ??= assigns "default".

7. B – switch ✅
✔️ switch is best for checking one variable against many known values.

8. B – 3 ✅
✔️ Runs for i = 0, 1, 2.

9. B – Sets theme only if it’s falsy ✅
✔️ ||= assigns only when the left-hand side is falsy.

10. A – Prevents code from running if user is missing ✅
✔️ Classic guard clause behavior.

🏆 Score: 10 / 10 – Perfect!
```
---

## 🔍 Why This Matters

Control flow allows you to:
- Handle user input conditionally
- Structure logic clearly
- Prevent bugs with default values and early exits
- Loop through collections and respond dynamically
- Write concise code with modern patterns like logical assignment and ternary operators

---

## 🛠 Tips Moving Forward

- Use `switch` to keep logic clean
- Use ternary and guard clauses to reduce nesting
- Remember the power of `||=`, `&&=`, and `??=` to simplify fallbacks
- Know your **falsy values**: `false`, `0`, `""`, `null`, `undefined`, `NaN`
