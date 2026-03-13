# Day 05 — Navigation Between Screens

## Overview

Most mobile applications contain multiple screens. For example, an app might have a home screen, profile screen, settings screen, or details screen.

To move between screens, React Native apps use a navigation system. In this challenge you will learn how to add navigation and move between different screens in your application.

By the end of this challenge, you will be able to create multiple screens and navigate between them.

---

## Learn

### What is Navigation?

Navigation allows users to move between different parts of an application. Instead of placing everything on a single screen, developers organize apps into multiple screens that users can switch between.

Examples of screens in a mobile app:

* Home screen
* Profile screen
* Contacts screen
* Settings screen

---

### Navigation Libraries

To manage navigation in React Native, we commonly use **React Navigation**.

React Navigation provides tools for different types of navigation patterns such as:

* Stack navigation
* Tab navigation
* Drawer navigation

In this challenge we will focus on **Stack Navigation**, which behaves like a stack of screens where new screens appear on top of previous ones.

---

### Installing Navigation

Inside your project install the required packages:

```id="day5install"
npm install @react-navigation/native
npm install @react-navigation/native-stack
```

Then install required dependencies for Expo:

```id="day5expo"
npx expo install react-native-screens react-native-safe-area-context
```

---

### Basic Navigation Setup

First create a stack navigator.

Example structure:

```id="day5structure"
screens/
  HomeScreen.js
  ProfileScreen.js
  ContactsScreen.js
```

Example setup:

```javascript id="day5navsetup"
import { NavigationContainer } from "@react-navigation/native";
import { createNativeStackNavigator } from "@react-navigation/native-stack";

import HomeScreen from "./screens/HomeScreen";
import ProfileScreen from "./screens/ProfileScreen";

const Stack = createNativeStackNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Profile" component={ProfileScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```

---

## Build

Create an application with **three screens**:

* Home Screen
* Profile Screen
* Contacts Screen

Each screen should display a simple title and a button that allows navigation to another screen.

Example flow:

```id="day5flow"
Home Screen → Profile Screen
Home Screen → Contacts Screen
```

Example layout idea:

Home Screen

```
Home Screen

[ Go to Profile ]
[ Go to Contacts ]
```

Profile Screen

```
Profile Screen

[ Back to Home ]
```

Contacts Screen

```
Contacts Screen

[ Back to Home ]
```

Use the navigation prop to move between screens.

Example:

```javascript id="day5navigate"
navigation.navigate("Profile");
```

---

## Suggested Project Structure

Your project might look like this:

```id="day5project"
App.js

screens/
  HomeScreen.js
  ProfileScreen.js
  ContactsScreen.js

components/
```

Each screen should be placed inside the **screens** folder.

---

## Submit

When you complete the challenge:

1. Add your solution to the submissions folder.

Example:

```id="day5submit"
submissions/day-05/your-name-navigation/
```

1. Commit and push your changes.
2. Open a Pull Request.

Example Pull Request title:

```id="day5pr"
Day 05 Challenge — Navigation Between Screens
```

---

## Bonus (Optional)

If you finish early, try the following improvements:

* Pass data between screens using navigation parameters
* Add icons to navigation buttons
* Customize the header title
* Style the screens with better spacing and layout

---

## Goal of Day 05

By completing this challenge you should understand:

* Why navigation is important in mobile apps
* How to create multiple screens
* How to navigate between screens
* How to structure screens in a React Native project
