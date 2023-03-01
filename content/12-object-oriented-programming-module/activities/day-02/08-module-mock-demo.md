+++
title = "08.  Module Mock Demo 👩‍🏫🧑‍🏫"
weight = 8
tags = ["oop"] 
+++

### movieSearch.test.js
```js
const axios = require("axios");
const MovieSearch = require("../movieSearch");

jest.mock("axios");

describe("MovieSearch", () => {
  describe("buildUrl", () => {
    it("should return an OMDB movie search URL using a movie name", () => {
      const movie = new MovieSearch();
      const name = "Rocky";

      const url = movie.buildUrl(name);

      expect(url).toEqual(`https://www.omdbapi.com/?t=${name}&apikey=trilogy`);
    });
  });

  describe("search", () => {
    it("should search the OMDB API for a given movie", () => {
      const movie = new MovieSearch();
      const name = "Rocky";

      axios.get.mockReturnValue(
        new Promise(function(resolve) {
          resolve({ data: {} });
        })
      );

      expect(movie.search(name)).resolves.toEqual({ data: {} });
      expect(axios.get).lastCalledWith(movie.buildUrl(name));
    });
  });
});
```

### movieSearch.js
```js
const axios = require("axios");

function MovieSearch() {}

MovieSearch.prototype.buildUrl = function(movie) {
  return `https://www.omdbapi.com/?t=${movie}&apikey=trilogy`;
};

MovieSearch.prototype.search = function(movie) {
  return axios.get(this.buildUrl(movie));
};

module.exports = MovieSearch;
```