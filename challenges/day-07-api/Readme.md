# Day 07 — Fetching Data from an API

## Overview

Many mobile applications display data that comes from external services. Examples include news apps, social media feeds, weather applications, and product listings.

Instead of hardcoding data inside the app, developers often retrieve it from an **API (Application Programming Interface)**.

In this challenge, you will learn how to fetch data from a public API and display it inside your mobile application.

By the end of this challenge, you will build a screen that retrieves and displays a list of posts from an API.

---

## Learn

### What is an API?

An API allows applications to communicate with external services and retrieve data.

Examples of data that may come from APIs:

* Posts
* Users
* Products
* Weather information

For this challenge, we will use a public testing API.

Example endpoint:

```
https://jsonplaceholder.typicode.com/posts
```

This API returns a list of posts in JSON format.

---

### Fetching Data

In React Native, you can retrieve data using the `fetch()` function.

Example:

```javascript id="day7fetch"
fetch("https://jsonplaceholder.typicode.com/posts")
  .then((response) => response.json())
  .then((data) => {
    console.log(data);
  });
```

This retrieves the data and converts it into a JavaScript object.

---

### useEffect and useState

When fetching data in React, we typically use two hooks:

* `useState` to store the data
* `useEffect` to run the fetch when the screen loads

Example:

```javascript id="day7hooks"
const [posts, setPosts] = useState([]);

useEffect(() => {
  fetch("https://jsonplaceholder.typicode.com/posts")
    .then((res) => res.json())
    .then((data) => setPosts(data));
}, []);
```

This loads the posts when the component appears.

---

## Build

Create a **Posts Screen** that retrieves and displays posts from the API.

Requirements:

* Fetch posts from the API
* Store them in state
* Display them using **FlatList**
* Each item should show the post title

Example layout idea:

```
Posts

Post Title 1
Post Title 2
Post Title 3
Post Title 4
```

Each item should appear as a simple list entry.

---

## Example Implementation

```javascript id="day7example"
import { useState, useEffect } from "react";
import { View, Text, FlatList } from "react-native";

export default function PostsScreen() {
  const [posts, setPosts] = useState([]);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/posts")
      .then((res) => res.json())
      .then((data) => setPosts(data));
  }, []);

  return (
    <View>
      <FlatList
        data={posts}
        keyExtractor={(item) => item.id.toString()}
        renderItem={({ item }) => <Text>{item.title}</Text>}
      />
    </View>
  );
}
```

Participants can style the list or improve the layout.

---

## Suggested Project Structure

```id="day7structure"
App.js

screens/
  HomeScreen.js
  PostsScreen.js

components/
  PostItem.js
```

You may create a reusable `PostItem` component for rendering each post.

---

## Submit

When you complete the challenge:

1. Place your solution inside the submissions folder.

Example:

```id="day7submit"
submissions/day-07/your-name-api/
```

1. Commit and push your changes.
2. Open a Pull Request.

Example Pull Request title:

```id="day7pr"
Day 07 Challenge — Fetch Data from API
```

---

## Bonus (Optional)

If you finish early, try one or more of the following improvements:

* Show a loading message while the data is being fetched
* Limit the number of posts displayed
* Style each post item as a card
* Add navigation to view a post's details

---

## Goal of Day 07

By completing this challenge you should understand:

* What an API is
* How to fetch data in a React Native application
* How to store fetched data using useState
* How to render API data using FlatList
