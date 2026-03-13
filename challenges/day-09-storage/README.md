# Day 09 — Local Storage in React Native

## Overview

Many mobile applications need to store small amounts of data locally on the user's device. This allows the app to remember information even after the app is closed.

Examples include:

* Saving user preferences
* Storing login tokens
* Remembering form inputs
* Saving small pieces of offline data

In this challenge, you will learn how to store and retrieve data using **AsyncStorage**, a simple local storage solution for React Native applications.

By the end of this challenge, you will be able to persist data locally in your mobile app.

---

## Learn

### What is Local Storage?

Local storage allows an application to save data directly on the device.

Unlike APIs or databases that store data remotely, local storage keeps data **inside the user's phone**.

This is useful for:

* App settings
* User preferences
* Cached information
* Temporary offline data

---

### What is AsyncStorage?

AsyncStorage is a simple key-value storage system commonly used in React Native applications.

It works similarly to how browsers store data using local storage.

Data is saved using a **key** and retrieved later using that same key.

---

### Installing AsyncStorage

Install the package inside your project:

```id="day9install"
npx expo install @react-native-async-storage/async-storage
```

---

### Saving Data

To store data locally, use `setItem`.

Example:

```javascript id="day9save"
import AsyncStorage from "@react-native-async-storage/async-storage";

await AsyncStorage.setItem("username", "John");
```

This saves the value `"John"` using the key `"username"`.

---

### Retrieving Data

To read stored data, use `getItem`.

Example:

```javascript id="day9get"
const username = await AsyncStorage.getItem("username");
console.log(username);
```

---

### Removing Data

To delete stored data:

```javascript id="day9remove"
await AsyncStorage.removeItem("username");
```

---

## Build

Create a simple **Profile Preferences Screen** that allows the user to save and retrieve their name.

Example layout:

```id="day9layout"
Profile Preferences

Name: [__________]

[ Save Name ]
[ Load Name ]
[ Clear Name ]
```

Requirements:

* Use `TextInput` to enter the name
* Save the name using AsyncStorage
* Load the saved name when requested
* Allow clearing the saved data

---

## Example Implementation

```javascript id="day9example"
import { useState } from "react";
import { View, Text, TextInput, Button } from "react-native";
import AsyncStorage from "@react-native-async-storage/async-storage";

export default function StorageScreen() {
  const [name, setName] = useState("");

  const saveName = async () => {
    await AsyncStorage.setItem("name", name);
  };

  const loadName = async () => {
    const savedName = await AsyncStorage.getItem("name");
    if (savedName) setName(savedName);
  };

  const clearName = async () => {
    await AsyncStorage.removeItem("name");
    setName("");
  };

  return (
    <View>
      <Text>Profile Preferences</Text>

      <TextInput
        placeholder="Enter your name"
        value={name}
        onChangeText={setName}
      />

      <Button title="Save Name" onPress={saveName} />
      <Button title="Load Name" onPress={loadName} />
      <Button title="Clear Name" onPress={clearName} />
    </View>
  );
}
```

---

## Suggested Project Structure

```id="day9structure"
App.js

screens/
  LoginScreen.js
  RegisterScreen.js
  StorageScreen.js

lib/
  supabase.js
```

The storage screen can be accessed after login or as a separate feature screen.

---

## Submit

When you complete the challenge:

1. Place your solution inside the submissions folder.

Example:

```id="day9submit"
submissions/day-09/your-name-storage/
```

1. Commit and push your changes.
2. Open a Pull Request.

Example Pull Request title:

```id="day9pr"
Day 09 Challenge — Local Storage
```

---

## Bonus (Optional)

If you finish early, try these improvements:

* Automatically load the saved name when the screen opens
* Save additional preferences such as theme or favorite color
* Store the logged-in user's session
* Display a confirmation message when data is saved

---

## Goal of Day 09

By completing this challenge you should understand:

* What local storage is
* How to store data using AsyncStorage
* How to retrieve and remove stored data
* How mobile apps persist small pieces of information locally
