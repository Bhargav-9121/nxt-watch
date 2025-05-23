Live Link: <a>https://nxtwatchdh5.ccbp.tech/</a>

### Completion Instructions

<details>
<summary>Functionality added</summary>
<br/>

The app must have the following functionalities

- Initially, the app should be in **light** theme

- **Login Route**

  - When a invalid username and password are provided and the Login button is clicked, then the respective error message received from the response should be displayed
  - When a valid username and password are provided and the Login button is clicked, then the page should be navigated to the **Home** route
  - When an _unauthenticated_ user, tries to access the `HomeRoute`, `TrendingRoute`, `GamingRoute`, `SavedVideosRoute`, `VideoDetailsRoute`, then the page should be navigated to **Login** route
  - When an _authenticated_ user, tries to access the `HomeRoute`, `TrendingRoute`, `GamingRoute`, `SavedVideosRoute`, `VideoDetailsRoute`, then the page should be navigated to the respective route
  - When an authenticated user tries to access the `LoginRoute`, then the page should be navigated to the **Home** route
  - When show password checkbox is checked, then the password should be shown
  - When show password checkbox is unchecked, then the password should be masked

- **Home Route**

  - When an authenticated user opens the **Home** Route,
    - An HTTP GET request should be made to **homeVideosApiUrl** with query parameter as `search` and its initial value as empty string
      - **_Loader_** should be displayed while the HTTP request is fetching the data
      - After the data is fetched successfully, display the list of videos received in the response
      - If the HTTP GET request made is unsuccessful, then the [Failure view](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-home-failure-light-theme-lg-output.png) should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to **homeVideosApiUrl**
    - When a non-empty value is provided in the Search Input and button with search icon is clicked
      - Make an HTTP GET request to the **homeVideosApiUrl** with `jwt_token` in the Cookies and query parameter `search` with value as the text provided in the Search Input
      - **_Loader_** should be displayed while the HTTP request is fetching the data
      - After the data is fetched successfully, display the list of videos received in the response
    - When the HTTP GET request made to the **homeVideosApiUrl** returns an empty list for videos then [No Videos View](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-home-no-videos-light-theme-lg-output.png) should be displayed
  - When the **website logo** image is clicked, the page should be navigated to the **Home** route
  - When a **Video** is clicked, the page should be navigated to the **Video Item Details** route
  - Clicks on the **Trending** link in the Sidebar is clicked, then the page should be navigated to the **Trending** route
  - Clicks on the **Gaming** link in the Sidebar is clicked, then the page should be navigated to the **Gaming** route
  - Clicks on the **Saved Videos** link in the Sidebar is clicked, then the page should be navigated to the **SavedVideos** route

- **Trending Route**

  - When an authenticated user opens the **Trending** Route,
    - An HTTP GET request should be made to **trendingVideosApiUrl**
      - **_Loader_** should be displayed while the HTTP request is fetching the data
      - After the data is fetched successfully, display the list of videos received in the response
      - If the HTTP GET request made is unsuccessful, then the [Failure view](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-trending-failure-light-theme-lg-output.png) should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to **trendingVideosApiUrl**
  - When the **website logo** image is clicked, the page should be navigated to the **Home** route
  - When a **Video** is clicked, the page should be navigated to the **Video Item Details** route
  - Clicks on the **Home** link in the Sidebar is clicked, then the page should be navigated to the **Home** route
  - Clicks on the **Gaming** link in the Sidebar is clicked, then the page should be navigated to the **Gaming** route
  - Clicks on the **Saved Videos** link in the Sidebar is clicked, then the page should be navigated to the **SavedVideos** route

- **Gaming Route**

  - When an authenticated user opens the **Gaming** Route,
    - An HTTP GET request should be made to **gamingVideosApiUrl**
      - **_Loader_** should be displayed while the HTTP request is fetching the data
      - After the data is fetched successfully, display the list of videos received in the response
      - If the HTTP GET request made is unsuccessful, then the [Failure view](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-gaming-failure-light-theme-lg-output.png) should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to **gamingVideosApiUrl**
  - When the **website logo** image is clicked, the page should be navigated to the **Home** route
  - When a **Video** is clicked, the page should be navigated to the **Video Item Details** route
  - Clicks on the **Home** link in the Sidebar is clicked, then the page should be navigated to the **Home** route
  - Clicks on the **Trending** link in the Sidebar is clicked, then the page should be navigated to the **Trending** route
  - Clicks on the **Saved Videos** link in the Sidebar is clicked, then the page should be navigated to the **SavedVideos** route

- **Video Item Details Route**

  - When an authenticated user opens the **Video Item Details** route
    - An HTTP GET request should be made to **videoItemDetailsApiUrl** with `jwt_token` in the Cookies and `video_id` as path parameter
      - **_loader_** should be displayed while the HTTP request is fetching the data
      - After the HTTP request is successful, the response received should be displayed
      - If the HTTP GET request made is unsuccessful, then the [Failure view](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-video-item-details-failure-light-theme-lg-output.png) should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to **videoItemDetailsApiUrl**
  - Corresponding video should be displayed using `react-player` package
  - Initially, all the three buttons (Like, Dislike, Save) will be inactive
  - When the **Like** button is clicked,
    - It will change to an active state
    - If the **Dislike** button is already in the active state, then the **Dislike** button needs to be changed to the inactive state
  - When the **Dislike** button is clicked,

    - It will change to an active state
    - If the **Like** button is already in the active state, then the **Like** button needs to be changed to the inactive state

  - When the **Save** button is clicked
    - The button will change to an active state and the respective video details should be added to the list of saved videos
    - **Save** button text will be changed to **Saved**
  - When the **Saved** button is clicked
    - The button will change to an inactive state and the respective video details will be removed from the list of saved videos
    - **Saved** button text will be changed to **Save**

- **SavedVideos Route**

  - When an authenticated user opens the **SavedVideos** Route,
    - If the list of saved videos is empty, then [No Saved Videos Found View](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-no-saved-videos-light-theme-lg-output.png) should be displayed
    - The **Videos** in the list of saved videos should be displayed as a list of videos
  - When the **website logo** image is clicked, the page should be navigated to the **Home** route
  - When a **Video** is clicked, the page should be navigated to the **Video Item Details** route
  - Clicks on the **Home** link in the Sidebar is clicked, then the page should be navigated to the **Home** route
  - Clicks on the **Trending** link in the Sidebar is clicked, then the page should be navigated to the **Trending** route
  - Clicks on the **Gaming** link in the Sidebar is clicked, then the page should be navigated to the **Gaming** route

- **Not Found Route**

  - When a random path is provided in the URL then the page should navigate to the **Not Found** route

- When the **theme** button in the header is clicked, then the theme should be changed accordingly

- **Logout**
  - When the **Logout** button in the header is clicked, then the [Logout Popup](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-logout-popup-light-theme-lg-output.png) should be displayed
    - When **Cancel** button is clicked, then the popup should be closed and the page should not be navigated
    - When **Confirm** button is clicked, then the page should be navigated to the **Login** route

</details>

<details>

<summary>API Requests & Responses</summary>
<br/>

**loginApiUrl**

#### API: `https://apis.ccbp.in/login`

#### Method: `POST`

#### Description:

Returns a response containing the jwt_token

#### Success Response

```json
{
  "jwt_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InJhaHVsIiwicm9sZSI6IlBSSU1FX1VTRVIiLCJpYXQiOjE2MTk2Mjg2MTN9. nZDlFsnSWArLKKeF0QbmdVfLgzUbx1BGJsqa2kc_21Y"
}
```

#### Failure Response

```json
{
  "status_code": 404,
  "error_msg": "Username is not found"
}
```

**homeVideosApiUrl**

#### API: `https://apis.ccbp.in/videos/all?search=`

#### Method: `GET`

#### Description:

Returns a response containing the list of all videos

#### Response

```json
{
  "total": 60,
  "videos": [
    {
      "id": "30b642bd-7591-49f4-ac30-5c538f975b15",
      "title": "Sehwag shares his batting experience in iB Cricket | iB Cricket Super Over League",
      "thumbnail_url": "https://assets.ccbp.in/frontend/react-js/nxt-watch/ibc-sol-1-img.png",
      "channel": {
        "name": "iB Cricket",
        "profile_image_url": "https://assets.ccbp.in/frontend/react-js/nxt-watch/ib-cricket-img.png"
      },
      "view_count": "1.4K",
      "published_at": "Apr 19, 2019"
    },
    ...
  ],
}
```

**trendingVideosApiUrl**

#### API: `https://apis.ccbp.in/videos/trending`

#### Method: `GET`

#### Description:

Returns a response containing the list of trending videos

#### Response

```json
{
  "total": 30,
  "videos": [
    {
      "id": "ad9822d2-5763-41d9-adaf-baf9da3fd490",
      "title": "iB Hubs Announcement Event",
      "thumbnail_url": "https://assets.ccbp.in/frontend/react-js/nxt-watch/ibhubs-img.png",
      "channel": {
        "name": "iB Hubs",
        "profile_image_url": "https://assets.ccbp.in/frontend/react-js/nxt-watch/ib-hubs-img.png"
      },
      "view_count": "26K",
      "published_at": "Nov 29, 2016"
    },
    ...
  ]
}
```

**gamingVideosApiUrl**

#### API: `https://apis.ccbp.in/videos/gaming`

#### Method: `GET`

#### Description:

Returns a response containing the list of gaming videos

#### Response

```json
{
  "total": 30,
  "videos": [
    {
      "id": "b214dc8a-b126-4d15-8523-d37404318347",
      "title": "Drop Stack Ball",
      "thumbnail_url": "https://assets.ccbp.in/frontend/react-js/nxt-watch/drop-stack-ball-img.png",
      "view_count": "44K"
    },
    ...
  ]
}
```

**videoItemDetailsApiUrl**

#### API: `https://apis.ccbp.in/videos/:id`

#### Example: `https://apis.ccbp.in/videos/802fcd20-1490-43c5-9e66-ce6dfefb40d1`

#### Method: `GET`

#### Description:

Returns a response containing the list of gaming videos

#### Response

```json
{
  "video_details": {
    "id": "ad9822d2-5763-41d9-adaf-baf9da3fd490",
    "title": "iB Hubs Announcement Event",
    "video_url": "https://www.youtube.com/watch?v=pT2ojWWjum8",
    "thumbnail_url": "https://assets.ccbp.in/frontend/react-js/nxt-watch/ibhubs-img.png",
    "channel": {
      "name": "iB Hubs",
      "profile_image_url": "https://assets.ccbp.in/frontend/react-js/nxt-watch/ib-hubs-img.png",
      "subscriber_count": "1M"
    },
    "view_count": "26K",
    "published_at": "Nov 29, 2016",
    "description": "iB Hubs grandly celebrated its Announcement Event in November 13, 2016, in the presence of many eminent personalities from the Government, Industry, and Academia with Shri Amitabh Kant, CEO, NITI Aayog as the Chief Guest."
  }
}
```

</details>

### Resources

<details>
<summary>Image URLs</summary>

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-logo-light-theme-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-logo-light-theme-img.png)

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-logo-dark-theme-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-logo-dark-theme-img.png)

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-profile-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-profile-img.png) alt should be **profile**

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-failure-view-light-theme-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-failure-view-light-theme-img.png)

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-failure-view-dark-theme-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-failure-view-dark-theme-img.png)

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-no-search-results-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-no-search-results-img.png) alt should be **no videos**

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-no-saved-videos-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-no-saved-videos-img.png) alt should be **no saved videos**

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-not-found-light-theme-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-not-found-light-theme-img.png)

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-not-found-dark-theme-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-not-found-dark-theme-img.png)

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-banner-bg.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-banner-bg.png) **Banner Background image**

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-facebook-logo-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-facebook-logo-img.png) alt should be **facebook logo**

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-twitter-logo-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-twitter-logo-img.png) alt should be **twitter logo**

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-linked-in-logo-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-linked-in-logo-img.png) alt should be **linked in logo**

</details>

<details>
<summary>Colors</summary>

<br/>

<div style="background-color: #0f0f0f; width: 150px; padding: 10px; color: white">Hex: #0f0f0f</div>
<div style="background-color: #f9f9f9; width: 150px; padding: 10px; color: black">Hex: #f9f9f9</div>
<div style="background-color: #f8fafc; width: 150px; padding: 10px; color: black">Hex: #f8fafc</div>
<div style="background-color: #1e293b; width: 150px; padding: 10px; color: white">Hex: #1e293b</div>
<div style="background-color: #f1f5f9; width: 150px; padding: 10px; color: black">Hex: #f1f5f9</div>
<div style="background-color: #475569; width: 150px; padding: 10px; color: white">Hex: #475569</div>
<div style="background-color: #f1f1f1; width: 150px; padding: 10px; color: black">Hex: #f1f1f1</div>
<div style="background-color: #181818; width: 150px; padding: 10px; color: white">Hex: #181818</div>
<div style="background-color: #e2e8f0; width: 150px; padding: 10px; color: black">Hex: #e2e8f0</div>
<div style="background-color: #94a3b8; width: 150px; padding: 10px; color: black">Hex: #94a3b8</div>
<div style="background-color: #4f46e5; width: 150px; padding: 10px; color: white">Hex: #4f46e5</div>
<div style="background-color: #64748b; width: 150px; padding: 10px; color: white">Hex: #64748b</div>
<div style="background-color: #231f20; width: 150px; padding: 10px; color: white">Hex: #231f20</div>
<div style="background-color: #ffffff; width: 150px; padding: 10px; color: black">Hex: #ffffff</div>
<div style="background-color: #212121; width: 150px; padding: 10px; color: white">Hex: #212121</div>
<div style="background-color: #616e7c; width: 150px; padding: 10px; color: white">Hex: #616e7c</div>
<div style="background-color: #3b82f6; width: 150px; padding: 10px; color: white">Hex: #3b82f6</div>
<div style="background-color: #00306e; width: 150px; padding: 10px; color: white">Hex: #00306e</div>
<div style="background-color: #ebebeb; width: 150px; padding: 10px; color: black">Hex: #ebebeb</div>
<div style="background-color: #7e858e; width: 150px; padding: 10px; color: black">Hex: #7e858e</div>
<div style="background-color: #d7dfe9; width: 150px; padding: 10px; color: black">Hex: #d7dfe9</div>
<div style="background-color: #cbd5e1; width: 150px; padding: 10px; color: black">Hex: #cbd5e1</div>
<div style="background-color: #000000; width: 150px; padding: 10px; color: white">Hex: #000000</div>
<div style="background-color: #ff0b37; width: 150px; padding: 10px; color: white">Hex: #ff0b37</div>
<div style="background-color: #ff0000; width: 150px; padding: 10px; color: white">Hex: #ff0000</div>
<div style="background-color: #383838; width: 150px; padding: 10px; color: white">Hex: #383838</div>
<div style="background-color: #606060; width: 150px; padding: 10px; color: white">Hex: #606060</div>
<div style="background-color: #909090; width: 150px; padding: 10px; color: black">Hex: #909090</div>
<div style="background-color: #cccccc; width: 150px; padding: 10px; color: black">Hex: #cccccc</div>
<div style="background-color: #424242; width: 150px; padding: 10px; color: black">Hex: #424242</div>
<div style="background-color: #313131; width: 150px; padding: 10px; color: black">Hex: #313131</div>
<div style="background-color: #f4f4f4; width: 150px; padding: 10px; color: black">Hex: #f4f4f4</div>
<div style="background-color: #424242; width: 150px; padding: 10px; color: black">Hex: #424242</div>

</details>

<details>
<summary>Font-families</summary>

- Roboto

</details>
