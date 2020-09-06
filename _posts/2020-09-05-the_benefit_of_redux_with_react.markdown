---
layout: post
title:      "The Benefit of Redux (with React)"
date:       2020-09-06 03:33:25 +0000
permalink:  the_benefit_of_redux_with_react
---


Redux is a JavaScript library used for managing state in applications. Now what exactly does this mean? Well, if Redux is paired with React it means that you can store data in state and as long as the component is connected to Redux that means you can access anything from state.

Alright cool, we can access state in different components which means that if we have a child component a few layers down from a base component; the child component can update the data in state and the base component can easily access it. An example of this would be if we have a base component named Display, and in that component we render 2 children components called Button and Clicks. In this example if Display is connected to the Redux store we can pass Button a prop called updateClicks that will be called when the button is pressed in order to update the clicks in our state. At the same time we also want to pass the number of clicks from our state to props in the Clicks component. When we do these things, we no longer have to worry about state changes in the Clicks or Button components as now the base component, Display, is using Redux to handle state changes and simply passing down the data.

In reality it is possible to work out a way of doing the previous example just using React without Redux. The real benefit is  the ease of access to state and having cleaner and simpler code to work with. While being introduced to Redux in the Flatiron School curriculum, it was very hard to understand why one would truly need to use Redux and it wasn't until I started working on a React-Redux project of my own that I saw how it can be used.

The project is a simple interactive volleyball game. The objective is to click on the volleyballs coming towards the net to spike them back and then after the game ends submit a name that will be used to save the score. While animating these volleyballs does require a change in state, none of the other components besides that specific ball needs to know the state of that ball and thus Redux state would be excessive. On the other hand though, saving the score into Redux state is really useful because the score needs to be accessed from the component asking the user to submit a name for the Hiscores.

While being able to access the Redux state throughout any component can be a benefit, if used carelessly can cause issues in the application. Being able to access that state in any component means that you can also change the state in any component if you choose to. What this means is that all components relying on that data in state to render will now render improperly or potentially not render at all. Being aware of this potential downside, you might not want to include data in the Redux state if only a single component needs to know that specific data.

Redux is a great way to help manage data throughout many components but it is not always needed. To truly understand all the benefits of Redux, or any library for the most part, you should try to incorporate it into a project or ask other developers how they use the library. The more ways of using Redux you are exposed to, the better you will understand it.

