---
layout: post
title:      "React Card Flip"
date:       2021-02-05 20:12:56 +0000
permalink:  react_card_flip
---


The package react-card-flipper is a fantastic package that gives you the ability to flip cards that you have created. The problem though is there are not many helper blogs to explain the package. The docs are not very clear and they only show you how to create one card and have it flip, but what if you have a lot of cards and you only want to flip one out of the many you have? That's where I step in, to help YOU. First you want to install the package using your respective package manager --- yarn or npm.

`npm install --save react-card-flip` 

The top container component will map through your data that you are using throughout your application. You then want to render the child component inside of your map function to create all of the cards needed.

            <div className="flex-container">
				{this.props.map((item) => <Child item={item} />)}
            </div>

Create your child component that has local state in that card component so that every card has their own state. The package gives you the prop isFlipped, false to show the front of the card, true to show the back of the card. That prop helps you out tremendously, you want to use this.state to set the isFlipped state in your child component. 

```
    constructor(props) {
		super(props);
		this.state = {
			isFlipped: false
		}
		this.handleClick = this.handleClick.bind(this);
	}
```

Your handle click function will want to use the previous state of isFlipped and just return the opposite of what the previous state was set at, sort of like a "toggle" function.

```
	handleClick = (e) => {
		e.preventDefault();
		this.setState(prevState => ({ isFlipped: !prevState.isFlipped }));
	}
```

The child component is using the Card Flipper package. So this is where you want to import the package with the line `import ReactCardFlip from 'react-card-flip'` and call it with 

```
					<ReactCardFlip isFlipped={this.state.isFlipped} flipDirection="horizontal">
                        <ChildComponent1 />
                        <ChildComponent2 />
					</ReactCardFlip>
```

You should now have a fully functioning single card flipping application.





