# tech-challenge

This was one of the hardest challenges I've done. It was a full Crud with several tasks, but, we're here for the challenge.

### DEPLOY

This project was deployed in [Heroku](https://id.heroku.com/login).

It has 2 applications, one for the [front-end](https://tech-challenge-frontend.herokuapp.com/) in React and also one for the [back-end](https://tech-challenge-backend.herokuapp.com/) in NodeJs.

The current github repositories are:
https://github.com/julioclopes32/tech-challenge-frontend

https://github.com/julioclopes32/tech-challenge-backend

### Database

For this project, I choose to use the Firebase Database, it's a nice solution, easy to use, with several tools and also, it's a noSQL JSON formatted database, and that the my main concern, with firebase it's really easy to store and retrieve JSON data because we don't have to treat the data, we can just store as it's as the same as recover the data.

### Concept-map

The bigger the problem, the harder it's to join all the ideas and not get lost during the development. To help with the process I made a concept map, on it, we can discuss about my ideas and how I faced the solution.
<br/>
<img src="./mapa Conceitual.png">
<br/>
Looking at the concept map we can see that the application has a Front-end and a Back-end.
I kind of lost a lot of time in the Front-End because I wanted to get the best result and also learn with this challenge.
Basically, There are 5 pages in the front end, the login and register, which are managed by the firebase database.
The Favorite movie page, the research and result pages.

Each one of them is integrated to the back-end with APIs in a NodeJS application.

### Time Issues
Unfortunately trying to impress, I kind of lost a lot of time in the Front-End, at least the result was a nice web layout,
but, because of that, I couldn't finish the cache memory allocation and database keyword savings, so the app returns the list always straight from the omdbapi. Heroku comports cache memory, but the time wasn't enought to finish, so I tried to make the application as functional as possible. About the database keyword savigs, I believe that with the Favorite movie list, it was enought to show my database skills.

### Integration
Now I'll be more technical about the project. Basically, the Front-End starts in the login page. It uses routes to move between pages and the firebase authenticator to manage the login and password storage as well as the verification, I only do the input treatment and send a request directly to firebase.

Once logged in, the Front-End itself manages the session, with session persistence in all pages. Unfortunately when refreshing the pages, the Front-End might crash, this happens, because during the development, I pass the keyword values of research from the research page to the result page, and these values go to null when refreshing the page. Access null values may crash the application, after I  finished this part, I realized It would've been much better to pass the research attributes to the result page as link parameters.

When logged, the home page is the search page, with a nice input to look for movies, if the value is too short, the application won't research because the own API doesn't send results that exceed a big number of movies.

So, as said, the Front-End receives from the movieAPI the data, and show as a list. Once decided which are the favorites, on click, the Front-End sends a POST method ```/favorite``` to store the data in the firebase database. 

In the Favorite List, the Front-End sends a GET method ```/getfavorite``` to receive the data in the firebase database, and it waits to display on the page. In this part, It was necessary to async render, because, the page can only render after the GET method return the favorite list.

### How It Works?
Well, it's really simple to use this app, first access the [front-end Website](https://github.com/julioclopes32/tech-challenge-frontend) in heroku.

go in register, go back to the login screen, authenticate, search for a movie and add to the favorite list.

the application is functional, even though it is not completed.

### Improvements

Well, If there were more time, I'd be happy to finish my CRUD app, but, even though I'm going to finish this project later.

- At the research page, the log-out+favorite box doesn't go away.
- on Refreshing the pages may crash.
- Implement the cache memory and database research memory.
- some nodeJS methods return a generic {foo:var} Json, because the catch error and onSuccess callbacks must be implemented.

### Conclusion

Well, It was hard, but, I did my best ! I focused in having a good looking and functional application, with login and logout system as well as a nice Front-End.
