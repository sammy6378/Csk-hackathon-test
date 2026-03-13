# Day 08 — Authentication with Supabase

## Overview

Most mobile applications require users to create accounts and log in before accessing certain features. Authentication helps protect user data and allows apps to provide personalized experiences.

In this challenge, you will implement **user authentication** using Supabase. You will create screens that allow users to **register** and **log in** using their email and password.

By the end of this challenge, you will understand how to connect a React Native application to a backend authentication service.

---

## Learn

### What is Authentication?

Authentication verifies the identity of a user before allowing access to an application.

Common authentication features include:

* User registration
* Login
* Logout
* Session management

In this challenge we will focus on **registering new users and logging in existing users**.

---

### What is Supabase?

Supabase is a backend platform that provides services such as:

* Authentication
* Databases
* Storage
* APIs

It allows developers to quickly add backend features to their applications without building everything from scratch.

---

### Creating a Supabase Project

1. Create an account at the Supabase website.
2. Create a new project.
3. Locate your project credentials:

* Project URL
* Public Anon Key

You will use these to connect your React Native app to Supabase.

---

### Installing Supabase Client

Install the Supabase JavaScript client inside your project.

```id="day8install"
npm install @supabase/supabase-js
```

---

### Create a Supabase Client

Create a file to configure the Supabase connection.

Example:

```javascript id="day8client"
import { createClient } from "@supabase/supabase-js";

const supabaseUrl = "YOUR_PROJECT_URL";
const supabaseAnonKey = "YOUR_PUBLIC_ANON_KEY";

export const supabase = createClient(supabaseUrl, supabaseAnonKey);
```

---

### Registering a User

Supabase allows users to sign up using email and password.

Example:

```javascript id="day8signup"
const { data, error } = await supabase.auth.signUp({
  email: email,
  password: password,
});
```

---

### Logging In

To log in an existing user:

```javascript id="day8login"
const { data, error } = await supabase.auth.signInWithPassword({
  email: email,
  password: password,
});
```

---

## Build

Create two authentication screens:

* Register Screen
* Login Screen

Each screen should include:

Register Screen

```
Register

Email:    [___________]
Password: [___________]

[ Register Button ]
```

Login Screen

```
Login

Email:    [___________]
Password: [___________]

[ Login Button ]
```

Requirements:

* Use `TextInput` for email and password
* Connect the form to Supabase authentication
* Display a success or error message after login or registration

Optional navigation flow:

```
Login Screen → Home Screen
```

---

## Suggested Project Structure

```id="day8structure"
App.js

screens/
  LoginScreen.js
  RegisterScreen.js
  HomeScreen.js

lib/
  supabase.js
```

The `supabase.js` file should contain the Supabase client configuration.

---

## Submit

When you complete the challenge:

1. Add your solution inside the submissions folder.

Example:

```id="day8submit"
submissions/day-08/your-name-auth/
```

1. Commit and push your changes.
2. Open a Pull Request.

Example Pull Request title:

```id="day8pr"
Day 08 Challenge — Supabase Authentication
```

---

## Bonus (Optional)

If you finish early, try improving the authentication flow:

* Add a logout button
* Redirect to a Home Screen after login
* Show validation messages if fields are empty
* Store the logged-in user session

---

## Goal of Day 08

By completing this challenge you should understand:

* How authentication works in modern applications
* How to connect a mobile app to Supabase
* How to register and log in users
* How to integrate backend services into a React Native app
