# Final Project — Campus Hub App

## Overview

For your final project, you will build a **Campus Hub App**, a mobile application for students to register, view campus posts/events, and manage their profile.

This project integrates all the skills you have learned during the hackathon:

* React Native components and styling
* Navigation between screens
* Reusable components
* FlatList for lists
* API fetching
* Supabase authentication
* AsyncStorage for local data

The goal is to create a **working, polished app** while leaving room for optional enhancements.

---

## Project Requirements

### 1. Authentication

* Users must be able to **register** and **login** using Supabase.
* Login should redirect to the Home screen.
* Optional: implement logout functionality.

### 2. Home Screen

* Display a welcome message with the user’s name.
* Include navigation to other sections (e.g., posts, profile).

### 3. Posts / Events Screen

* Fetch posts or events from a public API (or mock data).
* Display them using **FlatList**.
* Each post should show a title and a short description.
* Optional: add search or filtering.

### 4. Profile Screen

* Show user information (name, email).
* Allow the user to **save preferences locally** using AsyncStorage (e.g., favorite posts, theme).
* Optional: allow editing of profile info.

### 5. Navigation

* Use **React Navigation** to move between screens.
* Recommended flow:

```
Login / Register → Home → Posts / Events → Profile
```

### 6. Components & Styling

* Use **reusable components** for repeated UI elements (buttons, cards, avatars).
* Apply consistent styling throughout the app.

---

## Suggested Project Structure

```id="finalstructure"
App.js

screens/
  LoginScreen.js
  RegisterScreen.js
  HomeScreen.js
  PostsScreen.js
  ProfileScreen.js

components/
  Button.js
  PostCard.js
  Avatar.js

lib/
  supabase.js
```

---

## Submission

1. Place your final project in the submissions folder:

```
submissions/final-project/your-name/
```

2. Commit and push your changes.
3. Open a Pull Request with the title:

```
Final Project — Campus Hub App
```

---

## Bonus / Optional Features

These features are **not required**, but will make your project stand out:

* Dark mode or theme switching
* Save favorite posts locally
* Pagination or infinite scrolling in FlatList
* Custom animations
* Advanced reusable components
* Offline caching

---

## Assessment Criteria

| Criteria                     | Weight |
| ---------------------------- | ------ |
| Functionality                | 40%    |
| Code Structure & Reusability | 20%    |
| UI / Styling                 | 20%    |
| Creativity / Bonus Features  | 20%    |

---

## Tips

* Focus on **completing the required features first**.
* Use **clear, consistent component structure**.
* Test your app thoroughly on a device or emulator.
* Optional features are for those who finish early.

---

By completing this final project, you will demonstrate the **full spectrum of skills** learned in the hackathon and deliver a working, polished mobile application.
