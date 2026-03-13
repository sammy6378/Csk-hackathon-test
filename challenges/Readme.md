# Daily Challenge Template

Each challenge in the hackathon follows the same structure to make it easy for participants to understand what to learn, what to build, and how to submit their work.

This template should be used inside each challenge folder:

```
challenges/day-xx-topic/README.md
```

---

# Day X — Challenge Title

## Overview

A short description of the concept being introduced and why it matters in mobile development.

Example:

This challenge introduces how to render lists in a React Native application. Lists are commonly used for displaying contacts, messages, posts, or any repeating data.

---

## Learn

Before starting the build, participants should understand the core concepts.

Topics for this section may include:

* What the concept is
* Why it is useful
* Key React Native components or APIs involved

Example learning points:

* Understanding `FlatList`
* Rendering data from arrays
* Using `renderItem` to display each list item

Optional resources:

* Official documentation
* Short reference guides
* Code snippets

---

## Build

Participants now apply the concept by building a small feature.

Clearly describe the task.

Example:

Create a screen that displays a list of contacts using `FlatList`.

Each contact item should contain:

* A profile image
* The contact name
* A short subtitle or role

Sample data:

```
[
  { id: 1, name: "John Doe" },
  { id: 2, name: "Mary Smith" },
  { id: 3, name: "Alex Johnson" }
]
```

Expected result:

* A scrollable list
* Each item styled as a small card or row
* Clean and readable layout

Participants may start from the provided **starter code** if available.

---

## Submit

Once the challenge is complete, submit your work by creating a Pull Request.

Steps:

1. Fork this repository
2. Complete the challenge
3. Add your solution inside the correct submission folder

Example:

```
submissions/day-04/your-name-flatlist/
```

1. Commit your changes
2. Open a Pull Request

Example pull request title:

```
Day 04 Challenge — FlatList Implementation
```

In the Pull Request description include:

* What you built
* Any extra features you added
* (Optional) Screenshot of your app

---

## Bonus Challenge (Optional)

Participants who finish early can try additional improvements.

Examples:

* Add icons or avatars to each item
* Improve the styling
* Add navigation to a detail screen
* Add animations when items appear

Bonus challenges are optional but encouraged.

---

## Tips

* Keep components small and reusable
* Use meaningful variable names
* Focus on readability rather than complexity
* Ask mentors or other participants if you get stuck

---

## Folder Structure Example

Your solution might look like this:

```
App.js
components/
  ContactCard.js
screens/
  ContactsScreen.js
assets/
```

Keep your code organized and easy to understand.
