# Comparing Blaze with React

Comparing Blaze and React using the default functionality of a Meteor app. (This is a sidebar to [Intro to Meteor and React](https://github.com/CodeChron/intro-to-meteor-react))

When installing a Meteor app, by default it uses [Blaze](https://github.com/meteor/blaze) handling the view layer. 

If you're interested in understanding how Blaze and React differ, one great way to do that is to build the same feature using both technologies, so let’s recreate the default functionality of the Meteor app using React and then see how they compare.

## Re-creating the default Meteor app functionality using React
1. Install React using Meteor’s built-in package manager. In your app directory, type: meteor add react

Re-organize our app files a bit so we can keep track of what belongs to Blaze and what belongs to React.
Create a ‘client’ directory.  Anything inside this directory will only be run on the client.  More about special Meteor directories.
Inside the client directory, create a ‘templates’ directory and move the app.js file to client/templates and rename it to “hello.js” (The naming of the file is not important, but just for clarity.)
Create the file “hello.html” in the same directory and add the following to that file:

```
<template name="hello">
  <h1>Blaze: Welcome to Meteor!</h1>
  <button>Click Me</button>
  <p>You've pressed the button {{counter}} times.</p>
</template>
```
(Since this is not an intro to Blaze, I’m not going to spend any time explaining how Blaze templates work.) Then, update the file app/app.html as follows:

```
<head>
  <title>app</title>
</head>
```
```
<body>
  {{> hello}}
  <hr>
  <div id="app-container"></div>
</body>
```

Here, we’ve added a placeholder for our Blaze template ({{> hello}} and for our React components (#app-container)

Add React components:


Similar to Angular, we need to tell React where to render React components.

Note also, that we can render both Blaze and React in the same app. 

## Some differences between Blaze and React

Very quick intro to React: A View layer only (sort of), One-way data flow (virtual DOM -> rendered DOM) 
Bottom line: React is a complete paradigm shift compared to Blaze. Imo, React, and the thinking behind it, is the way forward.

Let’s first create basic Meteor app, which, as we’ll see, is probably the best way to understand how these two technologies differ




## Blaze
Blaze is template-based and has a more traditional division between HTML and JS, with separate HTML and JS files.  We use handlebars syntax (known as “spacebars” in the Meteor world) to define dynamic and/or logic-based elements in our HTML markup.  Then, based on the template name, we associate JS with the file, where we handle events, as well as the template lifecycle.
Discuss Blaze: html templates with handlebars dynamic content and logic, with associated event handlers.  Revolves more about making specific content dynamic.
Imo, more difficult to work with because html and js is separate, a lot of toggling back and forth.


## React
In React, we merge our HTML and JS into a single JS file.  As Pete Hunt, one of the creators of React, has said “template separate technologies, not concerns.”  In other words, even though having JS and HTML in separate files has been considered good practice, they are saying it in fact is wrong, since “display logic and markup are inevitably tightly coupled.” (View Pete Hunt’s seminal intro to React to learn more.)

React, in this way and others, represents a fundamental shift in how one approaches implementing the view layer. Instead of using templates, we use components, where we defined everything about a component in a single file.  This is a very big deal if you think about all the time you spend toggling back and forth between your JS and HTML files.  As a convenience, we can use JSX syntax, which allows us to include instructions for rendering HTML markup in our JS in a way that feels as if we are actually writing HTML. 

React revolves more around abstract UI components ,ie you create a dropdown component and then re-use that wherever you use dropdowns.  Hard to wrap your hand around because it is a paradigm shift in that HTML is mixed in with JS, in the form of JSX.  

The bottom line: React is likely to have a somewhat steeper learning curve, since it is more of a paradigm shift.  However, once you do, I find it far superior to Blaze.
