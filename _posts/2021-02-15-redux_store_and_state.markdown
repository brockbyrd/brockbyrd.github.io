---
layout: post
title:      "Redux Store and State"
date:       2021-02-15 20:57:34 +0000
permalink:  redux_store_and_state
---


Redux is to React like Mjollnir to Thor. They should go hand in hand in every application or situation. Redux's management of state staves React from the "prop drilling" problem that comes with React. The importance of Redux can not be overstated. Connect gives you the ability to pass props from the global "store" to anywhere in the application, but you still have the ability to create local state for containers and components throughout the application. The createStore function given to you from Redux has three functions inside of it. Dispatch, which takes in an action as an argument, sets the state from a given reducer and then runs render. GetState, which just returns state. Then createStore runs return which returns dispatch and getState. MapStateToProps and mapDispatchToProps is where everything becomes availible to the components that are wrapped inside of a connect function. MapStateToProps makes the global store available to the component through props. Any prop can be made visible or "invisible" to any component, the developer chooses what they want the component to "see" from the store. MapDispatch to props does basically the same thing that mapStateToProps does but with dispatch actions that are created by the user and then passed into the createStore function.

The simplisticity of Redux makes React desirable to code with. Being able to connect to the global store by simply writing two functions and passing them into connect takes a lot of stress off of a React developer.

Redux also provides a Provider, funny enough, to React developers. Provider is what makes the Redux store available to any nested component inside of the application that have been wrapped inside of the connect function.

While using Redux in a React application is not necessary, if your application is "complex" and you have more than two levels of the "family tree", I HIGHLY recommend implementing Redux into your application to help you manage state.
