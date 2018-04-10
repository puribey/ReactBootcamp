# React Bootcamp
**by Tyler McGinnis**

---

> React is a library for building user interfaces

## Intro notes

### Pros: 
* Composition 
* Unidirection Dataflow
* Explicit Mutations 
* Just JS


_Compositon:_ 

Components: slider, navbar, date, router, map, datepicker, header, calendar, avatar, carousel, chart, icon

Made out of components. 

2 things to consider:
- what state is it going to get from it parents 
- how the ui is going to look like 

_Unidirectional Data Flow:_
In react you hace event handlers like with Jquery but the state (data in your app) of the react application doesn't live in the DOM it lives within the components. React is responsable for rendering. 


_Explicit Mutations:_

```
this.setState({
	handle:'saraza',
	authed: true 
})
```

This sets the new state of the application. 

_Just JS:_
Nothing else needed. 

Go to branch **dayOne** to see the rest of my notes...


