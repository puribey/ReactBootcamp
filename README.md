# React Bootcamp
**by Tyler McGinnis**

## Day one notes 

We use createElement to create new elements and ReactDOM.render to render those inside the DOM.

React creates and object representation of the DOM (known as virtual DOM) in order to make it easier to compare and rerender. 

Whats the difference between the react element and the react component?

Component = is a fuction or class that optionally accepts imput (props) and returns a react element. We create components that return elements. 

```

		function NameComponent (props) {
			return React.createElement(
				'h1',
				null,
				props.name
			)
		}

		function HandleComponent (props) {
			return React.createElement(
				'h3',
				null,
				props.handle
			)
		} 

		const wrapperElement = React.createElement(
			'div',
			{id:'container'},
			React.createElement(NameComponent, {name: 'Puri'}),
			React.createElement(HandleComponent, {handle: '@puribey'})
		)

		ReactDOM.render(
			wrapperElement, 
			document.getElementById('app')
		)

```

Working with JSX 
To be able to use JSX we need babel.

Here we see the difference: 
```

		const name = 'Puri'
		const handle = '@puribey'

		function NameComponent (props) {
			return <h1>{props.name}</h1>
		}

		function HandleComponent (props) {
			return <h3>{props.handle}</h3>
		}

		function App () {
			return (
				<div id='container'>
					<NameComponent name={name}/>
					<HandleComponent handle={handle}/>
				</div>
			)
		}

		ReactDOM.render(
			<App/>, 
			document.getElementById('app')
		)

```
