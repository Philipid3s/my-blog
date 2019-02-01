---
layout: post
title:  "ETL Wikipedia data"
date:   2019-02-01 17:00:00 +0800
categories: javascript web-scraping etl mongodb
---
After having extracted the raw data from wikipedia in a Json file, I need now to clean up the data before a final loading in MongoDB ([mLab](https://mlab.com/)).

The raw data loaded in the JSON file have this format:

```javascript
{
    "title":"1940 Deutsche Lufthansa Ju 90 crash",     
    "gps":"51.2810°N 14.0400°E",
    "url":"https://en.wikipedia.org/wiki/1940_Deutsche_Lufthansa_Ju_90_crash"
}
```

**gps** needs to be transformed in order to extract the location (longitude and latitude) in a usefull format.
After transformation, the format of each record will be this one:

```javascript
{
    "title":"1940 Deutsche Lufthansa Ju 90 crash",
    "latitude":"51.2810",
    "longitude":"14.0400","url":"https://en.wikipedia.org/wiki/1940_Deutsche_Lufthansa_Ju_90_crash"
}
```

This JSON file is then loaded in a MongoDB database using the library [mangoose](https://mongoosejs.com/).

The longitude and latitude are loaded in a **Point-type structure**:

```javascript
const mongoose = require('mongoose');

// ... connect to db ...

// Bring in Model (crash site)
let crash = require('./models/crash');

sites.forEach(element => {
    let site = new crash();

    site.title = element.title;
    site.url = element.url;
    site.location = { type: "Point", coordinates: [element.longitude, element.latitude]};
});
```

Next step, the creation a **REST API**.