# Day 06 — Forms and User Input

## Overview

Most mobile applications collect information from users. This may include login forms, search fields, profile information, or feedback forms.

In this challenge, you will learn how to handle **user input** in a React Native application. You will create a simple form using input fields and manage the entered data using state.

By the end of this challenge, you will understand how to capture user input and display or use that data inside your app.

---

## Learn

### TextInput

React Native provides a component called `TextInput` that allows users to type text into the application.

Example:

```id="day6textinput"
<TextInput placeholder="Enter your name" />
```

You can customize input fields with placeholders, styles, and keyboard types.

---

### Managing Input with State

To capture what the user types, we store the value using **state**.

Example:

```javascript id="day6state"
const [name, setName] = useState("");
```

Then connect it to the input:

```javascript id="day6inputbind"
<TextInput
  placeholder="Enter your name"
  value={name}
  onChangeText={setName}
/>
```

Now every time the user types, the state updates automatically.

---

### Handling Form Submission

When the user presses a button, we can use the entered data.

Example:

```javascript id="day6submit"
<Button
  title="Submit"
  onPress={() => {
    console.log(name);
  }}
/>
```

This allows the application to process the form data.

---

## Build

Create a **Simple Login Form Screen**.

Your screen should include:

* Email input field
* Password input field
* Login button

Example layout idea:

```
Login

Email:    [___________]
Password: [___________]

[ Login Button ]
```

Requirements:

* Use `TextInput` for the fields
* Store input values using `useState`
* When the user presses the login button, display a welcome message

Example result after submission:

```
Welcome, user@example.com
```

You can display the message on the same screen or navigate to another screen.

---

## Example Starter Structure

```javascript id="day6example"
import { useState } from "react";
import { View, Text, TextInput, Button, StyleSheet } from "react-native";

export default function App() {
  const [email, setEmail] = useState("");
  const [password, setPassword] = useState("");

  return (
    <View style={styles.container}>
      <Text style={styles.title}>Login</Text>

      <TextInput
        placeholder="Email"
        style={styles.input}
        value={email}
        onChangeText={setEmail}
      />

      <TextInput
        placeholder="Password"
        style={styles.input}
        secureTextEntry
        value={password}
        onChangeText={setPassword}
      />

      <Button title="Login" onPress={() => alert(`Welcome ${email}`)} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    padding: 20,
  },

  title: {
    fontSize: 20,
    marginBottom: 20,
    textAlign: "center",
  },

  input: {
    borderWidth: 1,
    borderColor: "#ccc",
    padding: 10,
    marginBottom: 12,
    borderRadius: 6,
  },
});
```

You can improve the layout and styling.

---

## Submit

When you complete the challenge:

1. Place your solution in the correct submissions folder.

Example:

```id="day6submit"
submissions/day-06/your-name-forms/
```

1. Commit and push your changes.
2. Open a Pull Request.

Example Pull Request title:

```id="day6pr"
Day 06 Challenge — Forms and User Input
```

---

## Bonus (Optional)

If you complete the challenge early, try these improvements:

* Add input validation (check if email is empty)
* Show an error message if fields are missing
* Navigate to another screen after login
* Improve the styling of the form

---

## Goal of Day 06

By completing this challenge you should understand:

* How to capture user input using TextInput
* How to manage form state with useState
* How to handle simple form submissions
* How user input flows through a React Native application
