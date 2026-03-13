# Day 04 — Rendering Lists with FlatList

## Overview

Most mobile applications display lists of data such as contacts, messages, posts, or products. Instead of manually rendering each item, React Native provides tools to efficiently display large collections of data.

In this challenge you will learn how to render lists using **FlatList** and display multiple items from an array of data.

By the end of this challenge, you will build a simple **contacts list screen** using a reusable list item component.

---

## Learn

### What is FlatList?

`FlatList` is a component in React Native designed for rendering scrollable lists of data efficiently.

Instead of writing multiple repeated components manually, you provide a **data array** and tell FlatList how to render each item.

Example:

```id="g6axmy"
<FlatList
  data={data}
  renderItem={({ item }) => <Text>{item.name}</Text>}
/>
```

FlatList automatically renders the list and allows the user to scroll through the items.

---

### Key Props

Important properties used with FlatList:

**data**

The array of items you want to display.

```id="r0p1m3"
data={[{ id: 1, name: "John" }]}
```

**renderItem**

A function that tells FlatList how to display each item.

```id="9y2z4h"
renderItem={({ item }) => <Text>{item.name}</Text>}
```

**keyExtractor**

Used to give each item a unique key.

```id="py3n8t"
keyExtractor={(item) => item.id.toString()}
```

---

## Build

Create a **Contacts List Screen**.

Your screen should display a scrollable list of contacts using FlatList.

Each contact item should include:

* Profile image
* Contact name
* Short subtitle (for example: role or occupation)

Example layout idea:

```id="n3t7h8"
[ Avatar ]  John Doe
            Mobile Developer

[ Avatar ]  Mary Smith
            Designer

[ Avatar ]  Alex Johnson
            Student
```

Requirements:

* Use `FlatList` to render the contacts
* Each item should be styled as a row
* Add spacing between items
* Use a reusable component for each contact item

---

## Example Data

You can start with a simple array of contacts.

```javascript id="k4z7da"
const contacts = [
  {
    id: "1",
    name: "John Doe",
    role: "Mobile Developer",
    avatar: "https://i.pravatar.cc/150?img=1",
  },
  {
    id: "2",
    name: "Mary Smith",
    role: "UI Designer",
    avatar: "https://i.pravatar.cc/150?img=2",
  },
  {
    id: "3",
    name: "Alex Johnson",
    role: "Student",
    avatar: "https://i.pravatar.cc/150?img=3",
  },
];
```

---

## Example FlatList Structure

```javascript id="w6k1u9"
import { FlatList, View } from "react-native";
import ContactItem from "./components/ContactItem";

export default function App() {
  return (
    <View>
      <FlatList
        data={contacts}
        renderItem={({ item }) => <ContactItem contact={item} />}
        keyExtractor={(item) => item.id}
      />
    </View>
  );
}
```

---

## Suggested Project Structure

```id="l1v9qf"
App.js

components/
  ContactItem.js
```

The `ContactItem` component should display the avatar, name, and role for each contact.

---

## Submit

When you complete the challenge:

1. Add your solution inside the submissions folder.

Example:

```id="d4q1o2"
submissions/day-04/your-name-flatlist/
```

1. Commit and push your changes.
2. Open a Pull Request.

Example Pull Request title:

```id="s5k3nt"
Day 04 Challenge — FlatList Contacts List
```

---

## Bonus (Optional)

If you finish early, try improving your list:

* Add separators between list items
* Add more contacts
* Add icons or status indicators
* Improve spacing and layout
* Add a header at the top of the list

---

## Goal of Day 04

By completing this challenge you should understand:

* How to render lists using FlatList
* How to display data from arrays
* How to structure list item components
* How to build scrollable list interfaces commonly used in mobile apps
