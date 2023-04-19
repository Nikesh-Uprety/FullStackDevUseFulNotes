# useEffect hook and javascript fetch method
```javascript
const niku =[];
let [niku, useniku]=useState([]);

useEffect(()=>{
  fetch('https://api.github.com/users/Nikesh-Uprety')
  .then(response => response.json())
  .then(data => niku.push(data)) &&
  .then(data => useniku(data)) // This worke if useState react hook is used

},[])

console.log(niku);
```

# Using axios javascript library
```javascript
fetchData() {
    // Simple GET request using axios
    axios.get('https://api.github.com/users/Nikesh-Uprety')
        .then(response => useState(response.data ));
}
```
## And with the useEffect react hook
```javascript
useEffect(() => {
    // GET request using axios inside useEffect React hook
    axios.get('https://api.github.com/users/Nikesh-Uprety')
        .then(response => useState(response.data));

// empty dependency array means this effect will only run once (like componentDidMount in classes)
}, []);
```
