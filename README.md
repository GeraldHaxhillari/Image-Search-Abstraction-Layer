mage Search Abstraction Layer
==============================

An API which allows to get a list of links to images related to a specific term, and the latest searches.

Notes
------

I am using Google's Custom Search API, which allows only 100 free requests per day.

This project will not work out of the box, you should set some values in the `.env` file.
- `MONGO_URL` = a string used to connect to MongoDB, I used something like `mongodb://localhost:27017/fcc-projects`. Note: "fcc-projects" is the name of the database.
- `API_KEY` = key to use the Search Engine JSON API. [More info here](https://developers.google.com/custom-search/json-api/v1/overview#prerequisites)
- `CX` = another key, [more info here](https://developers.google.com/custom-search/docs/tutorial/creatingcse)

User stories
------------

- [x] I can get the image URLs, alt text and page urls for a set of images relating to a given search string.
  - [x] What if there's no results? // An empty array will be returned.
  - [ ] What if the server does not answer or is down?
- [x] I can paginate through the responses by adding a `?offset=2` parameter to the URL.
- [x] I can get a list of the most recently submitted search strings.
  - [x] Is it really necessary to use MongoDB? // No, but hey it is still practice, don't get lazy!
  - [x] If there's no recent searches, return an empty array.
  - [x] Show only the 10 latest searches (or less if there's less searches)

Questions
-----------
- What happens if I reach the API's 100 requests daily limit?