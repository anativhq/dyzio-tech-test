# Dyzio Developer Recruitment Test



Thank you for taking the time to do our technical test.

* [A coding test](#coding-test)

Please submit your test as a zip file with any installation instructions in the body of your email.


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

Also build an influencer page that is loaded when the user clicks on an influencer in the table like the wireframe below.
The page must have a back to list button that returns them to the list page. We will expect the list to stay loaded in the browser.

![influencer-screen](images/influencer-screen.png?raw=true)


### Framework Choice

Please build the app in React, Next.js or Angular (in that order of preference).
We expect the developer to use some kind of boilerplate to produce the app bundle (i.e. create-react-app)

Please make the app look as good as possible (without getting involved in design). We expect the developer to use something like material-ui, semantic-ui or bootstrap to make the app look professional and presentable.

Any unit testing will be very good - even if it is only testing shallow renders.


### Task requirements

Feel free to spend as much or as little time on the exercise as you like as long as the following requirements have been met.

- Please complete the user stories below.
- Your code should compile and run in one step.
- Feel free to use whatever frameworks / libraries / packages you like.

### User Story 1


> As a **User running the application**
> 
> I can **Submit an advanced Influencer Query**
> 
> So that **I can view a list of influencers match that query**


### User Story 2

```
As a **User viewing the list of influencer**

I can **Click on an influencer to view their page**

So that **I can view more info about that influencer**
```

### User Story 3

```
As a **User viewing the influencer page (i.e. /influencers/QpbE5rw4hw6gDzoNQ) **

I can **Refresh the page using the browser**

So that **I can see the same data and share it via the URL**
```


### User Story 4

```
As a **User viewing the influencer page**

I can **Click on the back link**

So that **I can view the results table again**
```
#### Acceptance criteria

- For the known query (above), the correct results are returned
- The required attributes of the influencer are displayed
- The influencer screen runs on the correct URL i.e. `influencers/${influencerId]`
- the back link works and another influencer can be selected



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
