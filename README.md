# README #

Hello!

Welcome to the coding homework for Arizona Facility Services.

### What is this repository for? ###

The intention of this is to simulate items similar to the work we do here, in lieu of a technical interview or usage of leetcode.

The code comes from here: https://store.vuetifyjs.com/products/vuetify-material-dashboard-free

It utilizes Vue.js and Vuetify, two of the major frameworks used here to build our product. Everything else is vanilla JS, CSS, and the like.

### How do I get set up? ###

- Pull the repo
- Install [Nodejs](https://nodejs.org/en/)
- Install [Yarn](https://classic.yarnpkg.com/en/docs/install/). Yarn classic is fine for this project!
- Open your terminal
- Navigate to the project
- Run `yarn install`
- Run `yarn serve` to start a local development server
- You will now be able to see the site in your browser on the port the terminal output specifies

### What do I need to do? ###

#### Clone this repo and push it to your own, private repo ####

You will not be pushing code to this Bitbucket repository. 

Create your own repo, push all your commits there, and add dgruici@afs-controls.com to it when you are finished.

#### Complete these tasks ####
All of the below tasks are written in the style of user stories. This is typically how you will see what needs to be done.

##### ESLint is unhappy... #####
As a developer, having a reliable linter helps maintain code style and discover possible errors when compiling.

Running this project cold in VSCode gives an instant error after invoking `yarn serve` stating No ESlint configuration found. This is an unfortunate bug in the template.

Fix the linter so you can run the site!

If you do not encounter an issue with ESLint, let us know what environment you are developing the homework in when you submit the homework, so it will not impact review.

##### There is way too much stuff in the Hamburger Menu #####
As a user, if I am not directed toward the most important items in the site right away, I am liable to go searching around on my own, click on things without intention, and hate the product for no reason because I don't know what to do.

At this moment, the only "feature" is the Dashboard.

Because this is the only feature we have, I do not want to give the user the ability to know, or access any of the other pages or buttons listed in the hamburger menu.  
Please remove any item that is not Dashboard from the menu's list and make sure I am unable to access those sites, even if I know the Url for them. 

The exception for this of course being the Documentation link and the Upgrade to Pro button as we have no control over Vuetifyjs.com. It is sufficient to remove them from the menu.

##### Remove the Settings gear that shows up on all the pages #####
As a product owner, I don't want users to have the ability to change the theme or content of my carefully crafted experience.

Remove the settings gear from the site. A regular user does not need the ability to make site wide changes at this time.

##### The graphs on the Dashboard are super important #####
As a user, the more prominent the presentation of an item on the screen is, the more likely I am to look at it.

We now believe that the graphs are the most important part of the Dashboard.

Get rid of everything but the three graphs for Website Views, Daily Sales, and Completed Tasks on the Dashboard page. 

And since they are now SO IMPORTANT, we also need each one to be on a line by themselves. Currently all three can fit in a row if the screen is wide enough, but now we need it so each appears to be on its own row, regardless of screen size.

##### I cannot stress the importance of these graphs enough #####
As a user, innundating me with information can really drive home the importance of the item at hand.

Now that each of the graphs are on their own, important rows, I want to tell the user how important they are.

In the components section of the codebase is a MaterialCard.vue file. Use this component to add a MaterialCard to the right side of each graph.  
The Title of this component should read: *Extremely important graph*  
The Body of the component should read: *Look at how important this graph is*  

Each graph gets this MaterialCard to the right of it.

If the window is large enough, the Material Card will sit to the right of the graph.  
The Dashboard would show:  
Graph Card  
Graph Card  
Graph Card  

If the window becomes too small, the MaterialCard should shift underneath the graph it is next to.  
The Dashboard would show:  
Graph  
Card  
Graph  
Card  
Graph  
Card

**EXCITING REQUIREMENT ON THIS ONE**

An Exciting Requirement is defined as: Requirements reflecting features that go beyond the customer's expectations and prove to be very satisfying when present

You do not need to complete this task, but if you are feeling showy, give this a try!

As a user, when something gives me feedback after clicking on it, I am better able to understand the item's possible importance.

Instead of having the Cards show all the time, lets have the Cards only show up if a user tries to interact with the graph.

If a user clicks on one of the graphs, have the message card mentioned above show up for only that graph.  
For example, say I click on the second row graph, this should now show on the window:
Graph  
Graph Card  
Graph  

And if I were to make the window smaller, only the second card would interlace.  
For example:  
Graph  
Graph  
Card  
Graph  

#### High fives all around! ####

You have completed all the tasks!

### Who do I talk to? ###

If you run into issues pulling code from here, or have questions, reach out to dgruici@afs-controls.com