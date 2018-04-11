# React Bootcamp
**by Tyler McGinnis**

## Day Two Notes 

State within components 

Whenever you use .map (loop over any array in js) react need the elements to have its own key. Keys need to be unique. 

```
function FriendsList(props) {
	return (
		<ul>
			{props.list.map((name) =>(
				<li key={name}>
					{name}
				</li>
			))}
		</ul>
	)
}

function App () {
	const friends = ['Agus','Gina','Camila']
	return(
		<div>
			<FriendsList list={friends}/>
		</div>
	)
}

ReactDOM.render(
	<App/>,
	document.getElementById('app')
)

```


If you want react to manage your state we need to use a **class component** instead of a **function component**.
In order to do that we need to make the imput part of a state inside of the component. For this we need to create a constructor (always include super(props) inside of it) that takes props and adding the state with the info there.

Here we made the component App from the gist above from function component to class component: 

```
class App extends React.Component {
	constructor(props) {
		super(props)
		this.state = {
			friends: ['Agus','Gina','Camila']
		}
	}
	render() {
		return(
			<div>
				<FriendsList list={this.state.friends}/>
			</div>
		)
	}
}	
```

Updating state: 

In order to do this we need to evoque a function within the component and using **.setState** funtion so whenever there is a change of that info it will merge with the state. 


```
handleRemoveFriends(name){
	this.setState((currentState) => {
		friends: currentState.friends.filter((friend) => friend !== name)
	})
}

```

*Extra note: .filter removes an element from an array following a condition*

In order to use this brand new function we need to make the component to have this function as a prop and then when rendering make an element call that function through props.

```
<FriendsList 
	list={this.state.friends}
	onRemoveFriend={this.handleRemoveFriends}
/>

<li key={name}>
	<span>{name}</span>
	<button onClick={() => props.onRemoveFriend(name)}> Remove </button>
</li>

```


This will not work as the **this.** key word is not referencing App. Actually in order to know what it is referencing we need to see where it is invoqued and then look to its left. 

In order to make all this work we need to make this a reference that will be referencing App inside of constructor fase and we do this by using bind:

```
this.handleRemoveFriends = this.handleRemoveFriends.bind(this)

```

We have, for now, to use bind every time we use a new function.

*Extra note: we use concat because we should never modify the state directly, with concat we create a new array*