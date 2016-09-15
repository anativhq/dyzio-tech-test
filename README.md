# Dyzio Developer Recruitment Test



Thank you for taking the time to do our technical test. It consists of two parts:

* [A coding test](#coding-test)
* [A few technical questions](#technical-questions)

Please submit your test as a zip file with any installation instructions in the body of your email.

Please make this a **single** zip file containing:

1. a single markdown file with the answers to the technical questions
2. one folder containing the technical test

## Coding Test

Dyzio has a sandbox public API available at [https://influencers.dyzio.co/](https://influencers.dyzio.co/) that you can use to get influencer data, including YouTube, twitter and Instagram data.

As an example the POST below returns a list of influencers that are in the **gaming** category and have minimum reach of 10,000, maximum reach of 500,000. The API returns JSON data.

The API requires you specify a set of valid request headers.

    Accept-Tenant: uk
    Accept-Language: en-GB
    Authorization: Basic cmVkaG90YmFuYW5hcG9rZXJzbGlwdGVzdA==
    Host: influencers.dyzio.co
    Content-Type: application/json

Example POST for the search

    POST /api/v2/influencers/search HTTP/1.1
    Host: influencers.dyzio.co
    Content-Type: application/json
    Accept-Language: en-GB
    Authorization: Basic cmVkaG90YmFuYW5hcG9rZXJzbGlwdGVzdA==
    Cache-Control: no-cache
    Postman-Token: a06ed921-53e7-2108-83d5-5ed77fdba182

    {
      "category": "Gaming",
        "minimumReach": 10000,
        "maximumReach": 500000
    }

The task is to create an application that accepts the category and min and max reach as a parameter, for a web app this could be achieved using a simple form.

The application should then display the following information about each influencer in a grid (table on a webpage).

- Name
- Category
- YouTube subscriber count (aggregateYoutubeChannelStatistics.subscriberCount)
- totalSocialReach
- twitter followers (twitterStatistics.followersCount)
- instagram followers (instagramStatistics.followersCount)

A list of categories can be found below.

Here is a low fidelity wireframe of the likely screen:

![wireframe](images/wireframe.png?raw=true)

### Stack Choice

I would suggest developing the web app in a popular Node.js stack such as MEAN or MERN.

I would also suggest using popular packages such as [Griddle](http://griddlegriddle.github.io/Griddle/) for the table. You should favour using open source packages where possible, rather than coding from scratch.

### Task requirements

Feel free to spend as much or as little time on the exercise as you like as long as the following requirements have been met.

- Please complete the user story below.
- Your code should compile and run in one step.
- Feel free to use whatever frameworks / libraries / packages you like.

### User Story

As a **user running the application**
I can **view a list of influencers in a user submitted query**
So that **I know which influencers match that query**


#### Acceptance criteria

- For the known query (above), the correct results are returned
- The required attributes of the influencer are displayed

# Technical questions

Please answer the following questions in a markdown file called `Answers to technical questions.md`.

1. How long did you spend on the coding test? What would you add to your solution if you had more time? If you didn't spend much time on the coding test then use this as an opportunity to explain what you would add.
2. What was the most useful feature that was added to the latest version of your chosen language? Please include a snippet of code that shows how you've used it.
3. Why did you select your chosen Node stack?
4. What was the most useful feature of the Node stack you chose?
5. Do you have any observations about the Influencer API? What improvements could/should be made to it?



---
----


## Resources and further info

#### Sample Influencer JSON response

    {
      "results": 1,
      "influencers": [
    {
          "_id": "QpbE5rw4hw6gDzoNQ",
          "name": "Andru Edwards",
          "twitter": "andruedwards",
          "facebookPage": "andru",
          "instagram": "andru",
          "tumblr": null,
          "vine": null,
          "twitch": null,
          "thumbnail": "https://yt3.ggpht.com/-lgLS3_AR248/AAAAAAAAAAI/AAAAAAAAAAA/Ngm72xAAICw/s240-c-k-no-rj-c0xffffff/photo.jpg",
          "description": "I host the Gear Live YouTube channel, bringing you the latest in consumer electronics hotness!\n\nGear Live is a trend-setting web magazine, devoted to the high tech lifestyle. We provide news, reviews, and more on all your favorite gadgets, consumer electronics, games, and tech trends.\n\nI have won awards for my tech coverage--including being named as the best Technology Video Series as voted on by a bunch of big-name Hollywood folks, including Tom Hanks and Zach Braff.\n\nGearLive.com is my main website. Thank you for subscribing!\n\nBusiness ONLY: andru @ gearlive.com. We work with brands: sponsor us!\n\nGear Live\nc/o Review Labs\n17324 14th Dr SE\nBothell, WA 98012",
          "aggregateYoutubeChannelStatistics": {
            "subscriberCount": 69065,
            "viewCount": 36603120,
            "videoCount": 722,
            "commentCount": 568,
            "channelCount": 1,
            "averageDailyViews": 9887,
            "averageMonthlyViews": 296610
          },
          "youtubeChannels": [
            "UC55Jb99LT3IINRY_g5V6rtA"
          ],
          "category": "Gaming",
          "trending": false,
          "isInfluencer": true,
          "isReviewed": false,
          "twitterStatistics": {
            "followersCount": 18984,
            "friendsCount": 1529,
            "updatedDate": "2016-07-07T10:28:03.899Z"
          },
          "instagramStatistics": {
            "followersCount": 4214,
            "updatedDate": "2016-06-23T17:05:06.364Z"
          },
          "createdDate": "2016-06-23T17:05:06.381Z",
          "createdBy": "unknown",
          "totalSocialReach": 92263
        }
        ]
    }

#### cURL Statement

    curl -X POST -H "Content-Type: application/json" -H "Accept-Language: en-GB" -H "Authorization: Basic cmVkaG90YmFuYW5hcG9rZXJzbGlwdGVzdA==" -H "Cache-Control: no-cache" -H "Postman-Token: eaf2c446-7a42-27b2-e19e-25aa8fe1a9be" -d '{
      "category": "Gaming",
        "minimumReach": 10000,
        "maximumReach": 500000
    }' "https://influencers.dyzio.co/api/v2/influencers/search"

#### Category List


          [
            "Film & Animation",
            "Autos & Vehicles",
            "Music",
            "Pets & Animals",
            "Sports",
            "Short Movies",
            "Travel & Events",
            "Gaming",
            "Videoblogging",
            "People & Blogs",
            "Comedy",
            "Entertainment",
            "News & Politics",
            "Howto & Style",
            "Education",
            "Science & Technology",
            "Movies",
            "Anime/Animation",
            "Action/Adventure",
            "Classics",
            "Comedy",
            "Documentary",
            "Drama",
            "Family",
            "Foreign",
            "Horror",
            "Sci-Fi/Fantasy",
            "Thriller",
            "Shorts",
            "Shows",
            "Trailers"
          ]
