# React Bootcamp
**by Tyler McGinnis**

## Day Three Notes 

**Main Life cycle hooks** 

* constructor = what you use to stablish the inital state of your component.
* render = Render into the DOM
* componentDidMount = whenever the component is mounted into the DOM and bring info from outside (databases, apis, etc.)
* componentDidUpdate = change of state or data inside component
* componentWillUnmount = remove eveything created 

**AXAJ Requests**

We started having all our info inside our app but what if we want to get info from outside. 


```
window.API = {
    fetchFriends() {
       return new Promise((res, rej) => {
         const friends = [
           {
             name: 'Jordyn',
             active: true,
           },
           {
             name: 'Mikenzi',
             active: true,
           },
           {
             name: 'Jake',
             active: false
           }
         ]
         setTimeout(() => res(friends), 2000)
       })
     }
   }
</script>

componentDidMount() {
   console.log('--componentDidMount--')
   API.fetchFriends()
     .then((friends) => {
       this.setState({
         friends,
         loading: false,
       })
   })
}

```


