# This Is My Fifth Day Of Mastering JavaScript In 20 Days

## Lessons Summary:

- I learned how to get information from an API using fetch function
- I see promises and how to use it in my programs
- The use of await in asynchronous programs and the JSON method
- Destructuring data and how to get values from an object based on the property name in one line and the differnce between the use of {}
- The array destructuring [] and how to skip values and ... to get all remaining values
- The poing of using asynch programming is that there is some methods take a long time to be done and we don't need to keep waiting for them
- Modules let us split large code across multiple files and it create it's new scope
- How to use import and export
- 
## Coding Examples
```
fetch("https://dog.ceo/api/breed/hound/list") //i will be able to git information from this url
```
```
//we use await to force JavaScript to synchronize asynchronous cose
let response = await fetch("https://dog.ceo/api/breed/hound/list");
let body = await response.json(); 
```
```
let {nickname} = people[2];
```
```
const [babySpice, ...adultSpices] = spices;
```
```
// myModule.js
const veryUsefulFunction = () => "I came from a module";
export { veryUsefulFunction };
// otherModule.js
import { veryUsefulFunction } from './myModule.js'
veryUsefulFunction();
```
## Coding Exercises
**Web page that fetches data from the Rick and Morty API**
- HTML code
```
<!DOCTYPE html>
<html>
<head>
  <title>Alive Character List</title>
  <link rel="stylesheet" href="./styles.css">
</head>
<body>
  <h1>Alive Character List</h1>
  <ul id="characterList"></ul>

  <script src="./script.js"></script>
</body>
</html>
```
- JavaScript code
```
// Function to fetch character data from the API
async function fetchCharacters() {
    try {
      const response = await fetch('https://rickandmortyapi.com/api/character?status=alive');
      if (!response.ok) {
        throw new Error('Unable to fetch character data.');
      }
      const data = await response.json();
      return data.results.slice(0, 50);
    } catch (error) {
      throw new Error('An error occurred while fetching character data.');
    }
  }
  
  // Function to display character data on the webpage
  function displayCharacters(characters) {
    const characterList = document.getElementById('characterList');
    characters.forEach(character => {
      const listItem = document.createElement('li');
      listItem.innerHTML = `
        <img src="${character.image}" alt="${character.name}" />
        <h2>${character.name}</h2>
        <p>Location: ${character.location.name}</p>
        <p>Species: ${character.species}</p>
        <p>Gender: ${character.gender}</p>
      `;
      characterList.appendChild(listItem);
    });
  }
  
  // Fetch character data and display it on the webpage
  fetchCharacters()
    .then(characters => displayCharacters(characters))
    .catch(error => {
      const characterList = document.getElementById('characterList');
      characterList.innerHTML = `<li>Error: ${error.message}</li>`;
    });
  
```
- CSS code
```
h1 {
    text-align: center;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
  }
  
  li {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
  }
  
  img {
    width: 100px;
    height: 100px;
    margin-right: 10px;
  }
  
  h2, p {
    margin: 0;
  }
  
```
