# Day 03 — Reusable Components

## Overview

As applications grow, repeating the same UI code in multiple places becomes difficult to manage. To keep code clean and maintainable, developers create **reusable components**.

A reusable component is a small piece of UI that can be used in different parts of the application.

In this challenge, you will refactor the UI from the previous day and start organizing your project by creating reusable components.

By the end of this challenge, you should understand how to break a screen into smaller pieces that can be reused.

---

## Learn

### What is a Component?

In React Native, a component is a function that returns UI.

Example:

```id="c5pkfi"
function Greeting() {
  return <Text>Hello</Text>;
}
```

You can use it like this:

```id="9fowql"
<Greeting />
```

Components help you:

* Reduce repeated code
* Keep files organized
* Make apps easier to maintain

---

### Passing Props

Components can receive data using **props**.

Example:

```id="5myy3a"
function Greeting({ name }) {
  return <Text>Hello {name}</Text>;
}
```

Usage:

```id="srfhso"
<Greeting name="Reuben" />
```

Props allow components to be flexible and reusable.

---

### Organizing Components

In real projects, reusable components are usually stored in a **components folder**.

Example project structure:

```id="w3j1s1"
components/
  ProfileCard.js
  Button.js
  Avatar.js
```

This helps keep the main screen files clean.

---

## Build

Today you will convert your **Profile Card UI** from Day 02 into reusable components.

Create a `components` folder and add the following components:

* `Avatar`
* `ProfileCard`
* `PrimaryButton`

Your screen should display **two profile cards** using the same component.

Example layout idea:

```id="yg3o33"
[ Profile Card ]
  Avatar
  Name
  Bio
  Follow Button

[ Profile Card ]
  Avatar
  Name
  Bio
  Follow Button
```

Both cards should use the same reusable component.

---

## Example Component Structure

Your project might look like this:

```id="h2qvtt"
App.js

components/
  Avatar.js
  ProfileCard.js
  PrimaryButton.js
```

---

### Example Avatar Component

```javascript id="07o2w0"
import { Image, StyleSheet } from "react-native";

export default function Avatar({ url }) {
  return <Image source={{ uri: url }} style={styles.avatar} />;
}

const styles = StyleSheet.create({
  avatar: {
    width: 80,
    height: 80,
    borderRadius: 40,
    marginBottom: 10,
  },
});
```

---

### Example Usage

Inside `App.js`:

```javascript id="4wrp3r"
<ProfileCard
  name="John Doe"
  bio="Mobile Developer"
  avatar="https://i.pravatar.cc/150"
/>

<ProfileCard
  name="Mary Smith"
  bio="UI Designer"
  avatar="https://i.pravatar.cc/150?img=5"
/>
```

Your goal is to organize the UI into reusable components.

---

## Submit

When you complete the challenge:

1. Place your solution in the correct submissions folder.

Example:

```id="zw9bnl"
submissions/day-03/your-name-components/
```

1. Commit and push your changes.
2. Open a Pull Request.

Example Pull Request title:

```id="cty7bh"
Day 03 Challenge — Reusable Components
```

---

## Bonus (Optional)

If you finish early, try these improvements:

* Add props for button text
* Add multiple profile cards using different data
* Improve styling of the components
* Create a `Card` component wrapper

---

## Goal of Day 03

By completing this challenge you should understand:

* What reusable components are
* How to break a UI into smaller parts
* How to pass data using props
* How to organize components in a React Native project
