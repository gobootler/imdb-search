# 🍿 IMDB Movie Search 🍿


## *Getting Started*

Start off by forking this repository into your own github profile. What you will specifically build out is detailed below. Please commit often as you complete tasks.


## *Brief*

1) Create an Entity-Relationship (ER) diagram of the IMDB dataset.
2) Load the IMDB dataset into provided PostgreSQL database.
3) Create an `express` api with 2 primary routes:
   * `/search`
     * Search route which returns an array of titles
     * In the returned array, each element should contain a subset of the complete data for that title (see `title.basics`)
   * `/title/<titleId>`
     * Title details route which returns _all_ related data for a given title in an organized manner
4) Optimize for scale! 🚀🚀🚀


## *Resources*

* IMDB Dataset: https://www.imdb.com/interfaces/
* PostgreSQL Connection String: `< given by interviewer - replace here >`


## *Walkthrough*

Take some time to explore the IMDB dataset page and understand how the data is structured. Create an Entity-Relationship (ER) diagram, and include a `.jpg` of it in this repository.

The provided `PostgreSQL` connection string points to an empty database. Populate this database with the IMDB dataset while ensuring any foreign key relationships are properly created / maintained.

Then create an `express` api in this repository which will expose 2 routes using your newly populated `PostgreSQL` database:
* `[BASE_URL]/search`
  * Search route which returns an array of titles
  * Must handle following optional search parameters:
    * `keyword`: to fuzzy search for specific title names
    * `titleType`
    * `isAdult`
    * `allowedGenres`
    * `withPerson`
    * `minYear`
    * `maxYear`
    * `minDuration`
    * `maxDuration`
    * `minRating`
    * `maxRating`
  * Response: an array of titles, where for each title return data from `title.basics`
* `[BASE_URL]/title/<titleId>`
  * Title details route which returns *__all__* data around a given title in an organized manner

Your first goal should be to put together a simple working implementation of these 2 routes. Then we would like for you to optimize the setup for production. Don't forget to consider scale related issues; for example: should certain filtering logic reside in the api or in the database query itself?

Use the `.eslint` file included in this project to ensure that your code formatting is consistent with our practices. Look for linting plugins that support ESLint for whatever your text editior of choice is.


## *Measurables (what we’d like to see)*

* Please be ready to explain _anything_ and _everything_ - your decision-making process should make sense to us
* _Every_ line of code should have a purpose
* Abstract logic into seperate files wherever it makes sense
* Organize files - repository structure should be easy to follow
* Don't forget to consider things like:
  * environment / configuration variables
  * request validation
  * error handling
  * api spec
  * testing
* We like seeing you use effecient utility methods such as `map`, `filter`, and `reduce`
* We like seeing you use modern ES6 syntax
* At the conclusion of this project, you should have a locally-runnable and production-ready application


## *Bonus points*

Can you optimize this project for even more scale by using `Redis`, a simple in-memory caching solution? Show us how you would incorporate such a system and where such logic would go (and don't forget to consider any corner cases).

While we can't provide you with a live `Redis` database, feel free to use [this](https://www.npmjs.com/package/redis-mock) mocking library instead. We'll pretend it's the real thing :)