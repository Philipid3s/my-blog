---
layout: post
title:  "Web scraping: data extraction from Wikipedia"
date:   2019-01-31 10:00:00 +0800
categories: javascript web-scraping
---
I'm currently working on a data extraction from a Wikipedia page. 
My project is to export aircraft crash site locations in order to display them on a map ([leaflet api](https://leafletjs.com/)).

To perform this task, I will use a great javascript web scraping library: [Cheerio](https://github.com/cheeriojs/cheerio). This component will be implemented in a Node.js application.

The Wikipedia page is this one: [list of accidents involving commercial aircrafts](https://en.wikipedia.org/wiki/List_of_accidents_and_incidents_involving_commercial_aircraft).

The HTTP calls will be managed by [Request](https://github.com/request/request):

```js
const request = require('request');
const cheerio = require('cheerio');
request('https://en.wikipedia.org/wiki/List_of_accidents_and_incidents_involving_commercial_aircraft', (error, response, body) => {
    if (!error && response.statusCode == 200) {
                const $ = cheerio.load(body); // the body is loaded in Cheerio
    // ...
    }
});
```
As a first step, I will load the extracted data (title, url and location) in a JSON file. The data are still in a raw format.  
The ETL process will come later...