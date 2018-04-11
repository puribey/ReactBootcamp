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

