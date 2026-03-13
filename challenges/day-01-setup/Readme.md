# Day 01 — Setup and First React Native App

## Overview

Today’s goal is to set up a working mobile development environment and run your first **React Native** application using **Expo**. By the end of this challenge, you should be able to start a project, run it on your device or emulator, and modify the UI.

This step is important because every mobile app starts with a working development environment.

---

## Learn

Before building, understand the basic tools we will use.

### React Native

React Native allows developers to build mobile applications using JavaScript and React. Instead of building separate apps for Android and iOS, React Native lets you write most of your code once.

### Expo

Expo is a toolchain that simplifies React Native development. It removes the need for complex setup and allows you to run your mobile app quickly.

With Expo you can:

* Start a mobile project quickly
* Run your app on a phone or emulator
* See live updates while developing

---

## Setup

Make sure you have the following installed:

* **Node.js** (LTS version recommended)
* **npm** or **yarn**
* **Git**

Check installation:

```id="9g0uzg"
node -v
npm -v
git --version
```

---

## Create Your First App

Create a new Expo project:

```id="1iz1qu"
npx create-expo-app csk-mobile-day1
```

Move into the project folder:

```id="jrn0os"
cd csk-mobile-day1
```

Start the development server:

```id="yma3g6"
npx expo start
```

This will open the Expo development server where you can run the app on:

* A physical device
* An Android emulator
* A web preview

---

## Project Structure

After creating the project you will see a structure similar to this:

```id="9os2u6"
csk-mobile-day1/
  App.js
  assets/
  node_modules/
  package.json
```

Important file:

* **App.js** — the main entry point of the application.

---

## Build

Your task is to modify the `App.js` file to display a simple welcome screen.

Create a screen that displays:

* Hackathon title
* Your name
* Your university

Example layout idea:

```id="0hz0rb"
CSK Mobile Hackathon

Your Name
Your University
```

You may also add:

* A logo or image
* Basic styling
* Centered layout

The goal is simply to confirm that your development environment works.

---

## Starter Code

You may start from the default Expo template and modify `App.js`.

Example minimal structure:

```id="6ub5q4"
import { Text, View } from "react-native";

export default function App() {
  return (
    <View>
      <Text>CSK Mobile Hackathon</Text>
      <Text>Your Name</Text>
      <Text>Your University</Text>
    </View>
  );
}
```

## Running the App

Install dependencies:

```npm install```

Start the project:

```npx expo start```

Then open the app on your phone using Expo Go or an emulator.

`` Install Expo Go from playstore or app store to run the app on your phone. ``

Feel free to improve the layout and styling.

---

## Submit

When you finish the challenge:

1. Fork the hackathon repository.
2. Create a folder for your submission.

Example:

```id="9sqql0"
submissions/day-01/your-name-setup/
```

1. Add your project files.
2. Commit and push your changes.
3. Open a Pull Request.

Example Pull Request title:

```id="5jzwzw"
Day 01 Challenge — Setup and First App
```

---

## Bonus (Optional)

If you finish early, try the following improvements:

* Center the content using Flexbox
* Add a background color
* Add an image or logo
* Improve spacing and typography

---

## Goal of Day 01

By completing this challenge you should:

* Have a working React Native environment
* Understand the basic project structure
* Be able to modify and run your first mobile UI

This foundation will be used throughout the rest of the hackathon.
