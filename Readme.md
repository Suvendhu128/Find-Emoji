![image](https://github.com/Suvendhu128/Find-Emoji/assets/111605645/cec698ae-4d3a-48c9-bce0-bc72ac5bf8aa)
# Find Emoji

A simple web application to find emojis based on aliases and tags. This project allows users to search for emojis by typing in search terms. The application filters through a list of emojis and displays matching results along with their descriptions and categories.

## Features

- Search for emojis using aliases and tags.
- Display emoji descriptions and categories for matching results.

## Technologies Used
HTML
CSS
JavaScript

## Screenshots
![image](https://github.com/Suvendhu128/Find-Emoji/assets/111605645/67a299c3-e434-41cf-bf42-63472c6c47a8)

## CODE EXPLANATION
The HTML code creates a simple web page with a search bar, a submit button, and a footer. The footer contains a copyright notice for the author of the page.

The JavaScript code defines two variables:

searchField: A reference to the DOM element with the id searchBar. This element is the search bar.
SubmitButton: A reference to the DOM element with the id SubmitButton. This element is the submit button.
The code also defines a function called searchEmoji():

const searchEmoji = () => {
    console.log("function called");
    const  searchFieldValue = searchField.value;
    console.log(emojilist);
    const filteredList = emojilist.filter((e)=>{
        if(e.aliases.some(ele=>ele.startsWith(searchFieldValue ))){
            return true;
        }
        if(e.tags.some(ele=>ele.startsWith(searchFieldValue)))
        return true;
        // if(e.category.some(ele=>ele.startsWith(searchFieldValue ))){
        //     return true;
        // }
        // if(e.description.some(ele=>ele.startsWith(searchFieldValue)))
        // return true;
    });
    const searchResultContainer = document.getElementById("searchResultContainer");
    searchResultContainer.innerText ="";
    filteredList.map((ele)=>{
        console.log(ele);
        const emoji = document.createElement("h1")
        const description = document.createElement("h3")
        const category = document.createElement("p")
        emoji.innerText = ele.emoji;
        description.innerText = ele.description;
        category.innerText = ele.category;
        searchResultContainer.appendChild(emoji);
        searchResultContainer.appendChild(description);
        searchResultContainer.appendChild(category);
    });
};
The searchEmoji() function is called when the user clicks the submit button. It gets the value of the search bar and stores it in the searchFieldValue variable. It then uses the emojilist variable to filter the list of emojis. The emojilist variable is an array of objects, each of which represents an emoji. The filter() method of the array is used to filter the list of emojis based on the value of the searchFieldValue variable. The filter() method takes a callback function as an argument. The callback function is called for each element in the array. The callback function returns true if the element should be included in the filtered list, and false otherwise.

In this case, the callback function checks if the aliases or tags property of the emoji object starts with the value of the searchFieldValue variable. If it does, the element is included in the filtered list.

The filtered list is then used to create a new HTML structure that contains the emojis that match the search criteria. This HTML structure is then appended to the searchResultContainer element.

The SubmitButton element is assigned an event listener for the click event. This event listener calls the searchEmoji() function when the button is clicked.




