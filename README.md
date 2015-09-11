# extra-life-api
A simple API based on Express and Cheerio for showing donations, goals, and team from Extra-Life.org
Now up on NPM : https://www.npmjs.com/package/extra-life-api

Why?
------
I've ran a custom website for our Extra Life team last year, and we had a ton of success with it (we raised over $1700 dollars)!  However, one of the most difficult things was constantly updating donations and other info while we were doing it (which started to fall apart once we hit th 20 hour mark or so).  As a result, I decided to make a web scraper that does the job for you!!

Installation
------
Either locally or on a web-sever, either clone this package, or install from npm with:
```javascript
npm install extra-life-api
```

Once downloaded, move to the base module folder and simply run:

```javascript
node server
```
And you're good to go!  The app should default to port 8081.


API
------
There are 3 endpoints which can be accessed once the express server is up and running.  Each endpoint must be passed the individual's 'Participant ID'.  This can be found by going to your public page, and checking the end of the URL:


http://www.extra-life.org/index.cfm?fuseaction=donordrive.participant&participantID= **ID HERE**


* **/usergoals/[userid]**
  * Provides a json object with the current donation amoutn and donation goal
  * Returns the response:
  
    ```javascript
    {
      "goal":0,
      "raised":0
    }
    ```
    
* **/userinfo/[userid]**
  * Provides a json object with current user name, picture URL, donate URL, team name, and team URL
  * Returns the response:
  
    ```javascript
    {
      "name":"",
      "image":"",
      "donateURL":"",
      "team":"",
      "teamURL":""
    }
    ```
    
* **/recentDonations/[userid]**
  * Provides a json object with an array of your most recent donations (includes name, date, and message from donor)
  * Returns the response:
  
    ```javascript
    {
      "recentDonations":[
        {
          "name":"",
          "date":"",
          "message":""
        },{
          "name":"",
          "date":"",
          "message":""
        },{
          "name":"",
          "date":"",
          "message":""
        }
      ]
    }
    ```
    
License
------
This content is released under the [MIT License](https://opensource.org/licenses/MIT)
