# Day 02 — Layout and Styling

## Overview

In mobile development, layout and styling determine how your application looks and feels. A well-structured interface makes an application easier to use and understand.

Today’s challenge introduces **basic layout and styling in React Native**. You will learn how to organize elements on the screen and apply styles using the built-in styling system.

By the end of this challenge, you will build a simple **profile card UI** using layout and styling principles.

---

## Learn

### Flexbox Layout

React Native uses **Flexbox** for layout. Flexbox helps you control how components are positioned and aligned on the screen.

Common properties include:

* `flex`
* `flexDirection`
* `justifyContent`
* `alignItems`

Example:

```id="exf1lu"
<View style={{ flex: 1, justifyContent: "center", alignItems: "center" }}>
  <Text>Hello</Text>
</View>
```

This centers the content both vertically and horizontally.

---

### Styling with StyleSheet

Styles in React Native are typically defined using `StyleSheet`.

Example:

```id="2pxkpr"
const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: "#ffffff",
  },
});
```

Using `StyleSheet` helps organize styles and improves performance.

---

### Core Styling Concepts

During this challenge you will practice:

* Spacing (`margin`, `padding`)
* Alignment
* Background colors
* Border radius
* Font styling

These are essential skills for building user interfaces.

---

## Build

Create a **Profile Card UI**.

Your screen should include:

* Profile image
* Name
* Short bio
* Follow button

Example layout idea:

```id="7vcsd3"
[ Profile Image ]

John Doe
Mobile Developer

[ Follow Button ]
```

Requirements:

* The card should be centered on the screen
* Add spacing between elements
* Style the card with padding and rounded corners
* Add a background color for the card

You may place everything in `App.js` for now.

---

## Starter Code

You can begin with a basic layout and extend it.

Example starting structure:

```javascript id="qj8sn9"
import { View, Text, StyleSheet, Image, Pressable } from "react-native";

export default function App() {
  return (
    <View style={styles.container}>
      <View style={styles.card}>
        <Image
          source={{ uri: "https://i.pravatar.cc/150" }}
          style={styles.avatar}
        />

        <Text style={styles.name}>Your Name</Text>
        <Text style={styles.bio}>Mobile Developer</Text>

        <Pressable style={styles.button}>
          <Text style={styles.buttonText}>Follow</Text>
        </Pressable>
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: "center",
    justifyContent: "center",
    backgroundColor: "#f2f2f2",
  },

  card: {
    width: 250,
    padding: 20,
    borderRadius: 12,
    backgroundColor: "white",
    alignItems: "center",
  },

  avatar: {
    width: 80,
    height: 80,
    borderRadius: 40,
    marginBottom: 12,
  },

  name: {
    fontSize: 18,
    fontWeight: "bold",
  },

  bio: {
    marginTop: 4,
    marginBottom: 12,
    color: "#666",
  },

  button: {
    backgroundColor: "#2563eb",
    paddingVertical: 8,
    paddingHorizontal: 16,
    borderRadius: 8,
  },

  buttonText: {
    color: "white",
  },
});
```

You can modify and improve this UI.

---

## Submit

Once you finish the challenge:

1. Add your solution inside the submissions folder.

Example:

```id="e9y0s4"
submissions/day-02/your-name-styling/
```

1. Commit and push your changes.
2. Open a Pull Request.

Example Pull Request title:

```id="cyfa3a"
Day 02 Challenge — Layout and Styling
```

---

## Bonus (Optional)

If you complete the challenge early, try one or more of the following improvements:

* Add shadows to the card
* Add a second profile card
* Improve typography and spacing
* Change the background color of the screen
* Add an icon inside the button
* Configure Tailwind CSS for React Native and use it for styling

---

## Goal of Day 02

By completing this challenge you should understand:

* How layout works in React Native
* How to style components using StyleSheet
* How to organize UI elements using Flexbox
* How to build a simple, styled mobile interface
