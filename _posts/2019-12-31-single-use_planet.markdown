---
layout: post
title:      "Single-use Planet"
date:       2019-12-31 01:39:24 -0500
permalink:  single-use_planet
---


Single-use Planet is a React Redux app that helps people figure out what to do with the things that no longer serve them by offering alternatives to sending things to landfills because let's face it - when we throw things 'away' there is no 'away.'

For this project I created a Rails API for the backend. The API holds the data for all of the items that can potentially be repurposed or recycled. Each item has a name, material, alternative to recycling, how to recycle it, and a related image. 

I used the ```create-react-app``` generator to kick start the project. The client side of the app fetches the API with this async action, aided by the Redux Thunk middleware. Thunk is used to make some actions asynchronous so if an action has to wait for a fetch, thunk can help that process rather than having everything load simultaneously.

```
export const getItems = () => {
	return dispatch => {
		return fetch(`${API_URL}`)
		.then(response => response.json())
		.then(items => dispatch(setItems(items)))
		.catch(error => console.log(error));
	}
}
```

If the response is successful, it returns the data in JSON, and dispatches the items to the ```setItems``` action creator which gets sent to the reducer. Here is our action creator:

```
const setItems = items => {
	return {
		type: 'GET_ITEMS_SUCCESS',
		items
	}
}
```

And our reducer:
``` 
const itemsReducer = (state = { items: []}, action) => {
	switch(action.type) {
		case 'GET_ITEMS_SUCCESS':
			return {items: action.items};
		default:
			return state;
	}
}
```

I'm using Redux so that each component can access the stored state without having to send down props from one component to another. I have multiple presentational, stateless components, including ItemName, ItemCard, NavBar, Resources, and About. 

The Items component uses state to pull in the items from the Redux store. The state in this component also keeps track of clicking on the item names and searching for items.  I made the Feedback Form component as an experiment so that I could try out React Hooks with  ```{ useState }```. 

I implemented Bootstrap for some easy styling, though I would love to revisit the appearance to give it an updated look. I would also like to add local zero-waste events and workshops. I like the idea of having a beta version of a project, so you can reflect on it and figure out the best improvements to work on next.

It took me a total of 6 months to do this project, with long stretches of not being able to work on it because paid projects took priority. I've worked on a handful of other sites in the meantime. I kept coming back to this one because I was **determined** to see it through and I'm **passionate** about waste diversion.

This is the culmination of the skills I learned through Flatiron School, and I'm beyond excited! 

[Link to the Github Repo](https://github.com/aellonk/single-use-planet)


