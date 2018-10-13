---
title: Styling React
---

## Styling in React

Styling is a huge part of user experience for your apps. You've got a new design and you're going to build your new awesome app in React. But how do you go about implementing that design?

Here, you get introduced to styling in React. In React, have four different option to style React Components. All Options on your personal preferences and the complexity of your application.

If you want to add just a few style properties, **Inline Styling** is the best option. When you want to reuse your style properties in the same file then **style-component** is nice. If your application is more complex use **CSS Modules** or regular **CSS Stylesheets** .

#### 1. CSS Stylesheet

```javascript
	import React from 'react';
	import './HelloWorld.css';

	const HelloWorld = () => {
		return(
			<div classname="HelloWorld">
				Hello World i'm React Styling!
			</div>
		)
	}

	export default HelloWorld;

```

Simply Import css file import './HelloWorld.css' so you can have a separate css file for each component.

```css
	.HelloWorld {
		border: 2px solid black;
		text-align: center;
		background: #f5f5f5;
		color: #333;
		margin: 20px;
		padding: 20px;
	}
```

#### 2. Inline Style

```javascript
	import React from 'react';
	
	const divStyle  = {
		border: '2px solid black',
		textAlign: 'center',
		background: '#f5f5f5',
		color: '#333',
		margin: '20px',
		padding: '20px'
	}

	const HelloWorld = () => {
		return(
			<div style={divStyle}>
				Hello World i'm React Styling!
			</div>
		)
	}

	export default HelloWorld;
	
```

In Inline Style are not specified as a string. Instead they are specified with an object whose **Key** is the **camelCased** version of the style name. We can also pass the styling directly style={{color: 'pink'}}.

#### 3. CSS Modules

A CSS Module is a CSS file in which all class names and animation names are scoped locally by default.

```javascript
	import React from 'react';
	import styles from './helloworld.css'

	const HelloWorld = () => {
		return(
			<div classname={styles.helloworld}>
				Hello World i'm React Styling!
			</div>
		)
	}

	export default HelloWorld;
	
```
After that access to classname as we access object

```css
	:local(.helloworld) {
			border: 2px solid black;
			text-align: center;
			background: #f5f5f5;
			color: #333;
			margin: 20px;
			padding: 20px;
	}
```

```:local(.className)```, this when you use create-react-app because of webpack configurations.
To make CSS modules work with Webpack you only have to include the modules mentioned above and add the following loader to your webpack.config.js file:

```
{
  test: /\.css$/,
  loader: 'style!css-loader?modules&importLoaders=1&localIdentName=[name]__[local]___[hash:base64:5]' 
}
```

#### 4. Style-Components
Styled-components is a library for React and React Native that allows you to use component-level styles in your application that are written with a mixture of JavaScript and CSS.


```javascript
	import React from 'react';
	import styled from 'styled-components';
	
	const Div  = styled.div{
		border: '2px solid black',
		textAlign: 'center',
		background: '#f5f5f5',
		color: '#333',
		margin: '20px',
		padding: '20px'
	}

	const HelloWorld = () => {
		return(
			<Div>
				Hello World i'm React Styling!
			</Div>
		)
	}

	export default HelloWorld;
	
```

- First we need to install styled-components library 
- ``` npm install styled-components --save ```

Congrats !! You have created styling in react with all Options.

Happy Coding  !! 
