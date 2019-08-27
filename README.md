# 🍿 IMDB Movie Search 🍿


## *Getting Started*

Start off by forking this repository into your own github profile. What you will specifically build out is detailed below. Please commit often as you complete tasks.


## *Brief*

1) Load the IMDB dataset into a PostgreSQL database.
2) Create an `express` api with 2 primary routes:
   * `/search`
     * Search route which returns an array of titles
     * In the returned array, each element should contain a subset of the complete data for that title (`title.basics`)
   * `/title/<titleId>`
     * Title details route which returns _all_ data around a given title in an organized manner
3) Optimize for scale! 🚀🚀🚀


## *Resources*

* IMDB Dataset: https://www.imdb.com/interfaces/
* PostgreSQL Connection String: `< given by interviewer - replace here >`


## *Walkthrough*

Take some time to explore the IMDB Dataset page and understand how the data is structured. The `PostgreSQL` connection string provided points to an empty database. Your first task is to populate this database with the IMDB dataset while ensuring any foreign key relationships are properly created / maintained.

You will then create an `express` api in this repository which, using your new loaded `PostgreSQL` database, will expose 2 routes:

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


## *Guidance (what we’d like to see)*

* Spend time at the start of the project to plan things out
* At the conclusion of this project, you should have a locally-runnable and production-ready application
* Please be ready to explain _anything_ and _everything_ - your decision-making process should make sense to us
* _Every_ line of code should have a purpose
* Don't forget to give consideration to things like:
  * environment / configuration variables
  * request validation
  * error handling
  *
  * testing


## *Bonus points*

Can you optimize this project for even more scale by using `Redis`, an simple in-memory caching solution? Show us how you would incorporate such a system and where such logic would go (and don't forget to consider any corner cases).

While we can't provide you with a live `Redis` database, feel free to use [this](https://www.npmjs.com/package/redis-mock) mocking library instead. We'll pretend it's the real thing :)