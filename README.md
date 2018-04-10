React is a library for building user interfaces

Pros: 
Composition 
Unidirection Dataflow
Explicit Mutations 
Just JS


Compositon: 

Components: slider, navbar, date, router, map, datepicker, header, calendar, avatar, carousel, chart, icon

A react made app is made out of components. 
2 things to consider:
- what state is it going to get from it parents 
- how the ui is going to look like 

Unidirectional Data Flow:
In react you hace event handlers like with Jquery but the state (data in your app) of the react application doesn't live in the DOM it lives within the components. React is responsable for rendering. 

this.setState({
	handle:'saraza',
	authed: true 
})

This sets the new state of the application. 

Just JS:
Nothing else needed. 

Go to branch One To see my notes on day one 

createElement =  actual representation of a DOM node
