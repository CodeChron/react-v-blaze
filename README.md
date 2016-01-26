# Comparing Blaze with React

<img width="952" alt="screen shot 2016-01-26 at 9 32 29 am" src="https://cloud.githubusercontent.com/assets/819213/12583296/ffb11d94-c40f-11e5-9366-8fecb176cf21.png">

_This is a sidebar to [Intro to Meteor and React](https://github.com/CodeChron/intro-to-meteor-react)._

- Start by cloning this repo and reviewing the code in your editor: ```git clone https://github.com/CodeChron/intro-to-meteor-react.git```
- If you run the app locally, you'll see two instances of the identical functionality.

When installing a Meteor app, by default it uses [Blaze](https://github.com/meteor/blaze) for handling the view layer.  If you're interested in understanding how Blaze and React differ, one great way to do that is to build the same feature using both technologies, wnich is what we've done here.
, so let’s recreate the default functionality of the Meteor app using React and then see how they compare.

## Blaze
Blaze is template-based and has a more traditional division between HTML and JS, with separate HTML and JS files.  We use handlebars syntax (known as “spacebars” in the Meteor world) to define dynamic and/or logic-based elements in our HTML markup.  Then, based on the template name, we associate JS with the file, where we handle events, as well as the template lifecycle.

## React
In React, we merge our HTML and JS into a single JS file.  As Pete Hunt, one of the creators of React, has [said](https://www.youtube.com/watch?v=x7cQ3mrcKaY) “templates separate technologies, not concerns.”  In other words, even though having JS and HTML in separate files has been considered good practice, the thinking behind React says this in fact is wrong, since “display logic and markup are inevitably tightly coupled.” ([View Pete Hunt’s seminal intro to React](https://www.youtube.com/watch?v=x7cQ3mrcKaY) to learn more.)

React, in this way and others, represents a fundamental shift in how one approaches implementing the view layer. Instead of using templates, we use components, where we define everything about a component in a single file.  This is a very big deal, if nothing else on a purely practical level, if you think about all the time you spend toggling back and forth between your JS and HTML files.  As a convenience, we can use JSX syntax, which allows us to include instructions for rendering HTML markup in our JS in a way that feels as if we are actually writing HTML. 

The bottom line in my opinion: React is likely to have a somewhat steeper learning curve, since it is more of a paradigm shift.  However, once you do, I find it far superior to Blaze.
