[https://apify.com/epctex/google-news-scraper](https://apify.com/epctex/google-news-scraper?fpr=yhdrb)

# Actor - Google News Scraper

## Google News scraper

Since Google News doesn't provide a good and free API, this actor should help you to retrieve data from it.

The Google News data scraper supports the following features:

-   Keyword Customization - Tailor your news searches with Google News, enabling precise retrieval of articles on topics of interest.

-   Multilingual Support - Google News offers language options, ensuring global news coverage for diverse audiences.

-   Date Filtering - Stay up-to-date with Google News by narrowing results to specific timeframes, from hours to years.

-   Comprehensive Sources - Google News aggregates data from a wide range of Google News categories and topics.

-   Effortless Access - With Google News, accessing news data is hassle-free and authentication-free.

-   Multi-URL Integration - Combine multiple start URLs for a holistic news retrieval experience.

-   No Usage Restrictions - Enjoy unlimited access and retrieval with Google News—no restrictions apply.

-   Customizable Language & Region - Adjust language settings to match your preferences and target regions with Google News.

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/google-news-scraper/issues).


## Input Parameters

The input of this scraper should be JSON containing the list of pages on Google News that should be visited. Required fields are:

- `startUrls`: (Optional) (Array) URLs to start with. It should be search, topic, category, or list URL.

- `search`: (Optional) (String) Keyword that you want to search on Google News.

- `language`: (Optional) (String) This value determines language and region for the news. This setting only applies to Search queries, not the start URLs.

- `date`: (Optional) (String) Date of the news. This setting only applies to Search queries, not the start URLs.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

- `extendOutputFunction`: (Optional) (String) Function that takes a JQuery handle ($) as an argument and returns an object with data.

- `customMapFunction`: (Optional) (String) Function that takes each object's handle as an argument and returns the object with executing the function.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Compute Unit Consumption

The actor is optimized to run blazing fast and scrape as many items as possible. Therefore, it forefronts all the detailed requests. If the actor doesn't block very often it'll scrape 100 listings in less than a minute with ~0.01-0.03 compute units.

### Google News Scraper Input example

```json
{
  "proxy":{
    "useApifyProxy":true
  },
  "startUrls":[
    "https://news.google.com/topics/CAAqIggKIhxDQkFTRHdvSkwyMHZNR054ZERrd0VnSmxiaWdBUAE?hl=en-US&gl=US&ceid=US%3Aen",
    "https://news.google.com/topics/CAAqJggKIiBDQkFTRWdvSUwyMHZNRGx6TVdZU0FtVnVHZ0pWVXlnQVAB?hl=en-US&gl=US&ceid=US%3Aen",
    "https://news.google.com/search?q=banana&hl=en-US&gl=US&ceid=US%3Aen"
  ],
  "maxItems":10
}

```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.

## Google News Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any language (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this Google News actor.

## Scraped Google News Properties

The structure of each item in Google News looks like this:

### Item Detail

```json
{
	"url": "https://news.google.com/search?q=banana&hl=en-US&gl=US&ceid=US%3Aen",
	"name": "Google News - Search",
	"newsData": [
		{
			"title": "Climate tech start up aims to reduce banana waste through alternative leather",
			"link": "https://www.nbcnews.com/now/video/climate-tech-start-up-aims-to-reduce-banana-waste-through-alternative-leather-193302085969",
			"time": "2023-09-19T19:14:55Z",
			"image": "https://lh3.googleusercontent.com/proxy/BM70v_z78TJwMI9RbZUHuPD6rqy5rUaLpxG0Xo45SMxHjWXC3QZGq4UMd6zwY35kwaRkYoAnStxCnv7tBZOWcl-FZyBicwZd3FfUwShV0PFixeUcQLa5teVUvXdhmR7mTBxDzKiy_NWjypEv5M5-pWkFqsT5JEl7GbLEuMXryDJ01s9xVt2DVMdnnmwFtboVo5qYAM2Wis-b-k2i-5sIvzuo1Ssc=s0-w100-h100-dchQGEKCHjNdKIosE"
		},
		{
			"title": "Video: Guide to easy no bake banana pudding",
			"link": "https://gulfnews.com/food/guide-cooking/video-guide-to-easy-no-bake-banana-pudding-1.1695221205993",
			"time": "2023-09-21T12:25:56Z",
			"image": "https://lh3.googleusercontent.com/proxy/_t-dtLJk3qdFxWKETdue4c_OOgntA7D2UWvjYWWMsJiKpBfh053VjOQGRjxu6Ls4fO4JFzyE3z_zbZlH17YxwpbgQAysz3fpgFslqqklnZ7S9sC4JLB2SD25bNG05_sACILJeELI5vZ_afkXwI-0Lr-SHk1Ri2Y-ASjYUpUoVB0NDwBKcJFDUaTUeBfsJJTe=s0-w100-h100-dcKSSMjp0G"
		},
		{
			"title": "'That's bananas': Unique 'banana train' holds up traffic in Costa Rica",
			"link": "https://www.independent.co.uk/tv/lifestyle/costa-rica-banana-crossing-tiktok-b2414084.html",
			"time": "2023-09-19T07:30:03Z",
			"image": "https://lh3.googleusercontent.com/proxy/k6BQHG9G86tymdn3DVWjhmcuJrRhOEUXGuLk3cP7yfNhwA7Fuj0_1seeS8RRwZlMRAvTUo_3Ecc0nq-0um38qOFBsn26ex1BCx66pH9RHB9oczV0fGWnpVylAQ=s0-w100-h100-dcAQAG"
		},
		{
			"title": "Savannah Bananas exhibit opens at National Baseball Hall of Fame",
			"link": "https://www.mlb.com/news/savannah-bananas-exhibit-opens-at-national-baseball-hall-of-fame",
			"time": "2023-09-21T23:00:39Z",
			"image": "https://lh3.googleusercontent.com/proxy/JWP3cjH5E2Z13SR9Tj8jRNs1I-oS1rsn_2DRNY9iTmM3v4YI1ckBppkx6og7yU14rs1OKB7bFB1pK4xvTDPiO7XHa3pvdK6vlSGVAYrIIedcQYvpNHyuCrt8wlwWkuFnuuGt1m5kWeUES1fEIxxh_Key3qI=s0-w100-h100-dcATCQGJjpgUsC"
		},
		{
			"title": "Wild monkeys raid Thailand 7-11, make off with banana haul in bizarre theft: video",
			"link": "https://nypost.com/2023/09/20/wild-monkeys-raid-thailand-7-11-make-off-with-banana-haul-in-bizarre-theft-video/",
			"time": "2023-09-20T19:35:00Z",
			"image": "https://lh3.googleusercontent.com/proxy/GXplBMtHdDPkBvxX-wZ5ws5UFeuQQpnnmUQ_DihC4MituXtTiZq_OQrDkAD920GlQEsE4HMCJazdTba6YJqgpTTYkhDfDPcOmD3ZvEdORaEDaTvqRl3TfwXY7c6VixKSr0pmQcSuC7c29jFRF-2X0cHj-wE9ywb1g06xJHTdG-L6KYDJ5S7MpBXKycc0QhKbS-WLcy3aIMwycuDzQqQFPCrgQ1ZoYQ=s0-w100-h100-dcHTCCziQjNecC"
		},
		{
			"title": "Banana On Empty Stomach: What Happens To Your Body When You Eat Banana First Thing In The Morning? | TheHe",
			"link": "https://www.thehealthsite.com/fitness/banana-on-empty-stomach-what-happens-to-your-body-when-you-eat-banana-first-thing-in-the-morning-2-1012171/",
			"time": "2023-09-21T05:23:00Z",
			"image": "https://lh3.googleusercontent.com/proxy/DPT9ua3xVX5lBP5yNl9mYaIsNJ1z2nWxV8eA3Vy3XVEKkiBjAOVSu0H4EK9hwEvAO2o93_YJ2D_mwNOK7HIVR1e73XIHlSpyet4nojt65aR2sdt_XUFlZZ0aUlWL9aUakR0nN6m36r-Y06FzG0YC=s0-w100-h100-dcCWKOZzXmmWsC"
		},
		{
			"title": "‘Irresponsible behaviour’: Zomato’s post on banana chips tagging Gurugram police receives backlash",
			"link": "https://www.tribuneindia.com/news/haryana/irresponsible-behaviour-zomatos-post-on-banana-chips-tagging-gurugram-police-receives-backlash-546511",
			"time": "2023-09-21T14:28:00Z",
			"image": "https://lh3.googleusercontent.com/proxy/AmC93N44-XJ7ed7YM_Oq-fnoL9KnOjnrWo4LjLk0JI4rrt-LWsMLZkqmWg8A7iP6il8K45GTlwifIYnvkw8gZ1aIY72hEAsxZVtuIvZ15PvZBbDKzLCqWYzYnI2IT9yS9z0lLi-X8OKgGiv_LcWkvrIxv7aXQSDlMiamThS3lXf1azk=s0-w100-h100-dcHQOCbYkqc7gA"
		},
		{
			"title": "West Virginia Thread Alert: BANANA SUITS!!!!",
			"link": "https://www.smokingmusket.com/2023/9/21/23884868/west-virginia-thread-alert-banana-suits-wvu-football-uniform-watch",
			"time": "2023-09-21T23:51:07Z",
			"image": "https://lh3.googleusercontent.com/proxy/Z5_-7GF08zyuaGMnmesz34vsr6y4ig6Q2_6kvIf9jfL1YHPGCnNIPDvzKQ-gyljziyi1lEz0f4d2ZUbW54108O9EezsNqtJH6dOLG48ix4eis4wfYZHAN8A0I-CvEMnHYrsf4nsOGNVTk6HLMf4libcs2ZcS6EkZThjEIXmEaEDJpKlL811SJ0fuy_wVxfeng-YGmX7IggeceozB_8pRUg4DuB7Mam4rWhv_P4PTRFi6FEPLwYao9pg=s0-w100-h100-dcHSSMzJkJ"
		}
	]
}
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
