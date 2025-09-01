---
description: >-
  This is a fictional case-study that illustrates some of the challenges of data
  science
---

# Case Study: Sanchez Pulse

Let’s imagine you are a data scientist and you have been asked to help a politician, Celia Sanchez, understand how popular she is before an election. You don’t have the details of what her team wants, but you are told that they want to know about how much people are talking about her online.

This seems to you as something very simple; counting the number of times that the name of something is mentioned each day on a web forum. In fact you already implemented something similar and you can just re-use that. In a 50 line code script you can scan the latest posts one by one searching for the appearance of a given word. This means you have to figure out how new posts are assigned a new URL of the form forum.com/posts\&postid=1234. Your script runs every day at midnight and counts the number of appearances. A web developer then reads that number and displays it on a simple dashboard for the team to check. Your job is done.

A few days later you get a message from the web developer. He was working on the dashboard and noticed that there has been a massive spike in mentions and wondered what was going on. You run the code manually to check the output. It turns out that a musician also called Celia Sanchez is in town and everyone is talking about her and not the politician! Luckily there is a category tag to the posts so you can filter out those tagged with ‘Music’ and the numbers go back to normal.\


<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfUOpFoanaPftbgHRAUx79Up54uQOMoPOhsq8Z4-dxDj8r6KAYyOYRehOJx0LxXPab4s_h8lXVVJ2VjLmrPZ9b1bq9sFyLO89l183qqhuEaDe6-3YYlmqVXb43hESdsSCnTAJcE6v3M9XWKYGZLAxjj-HE?key=AzFKC2-hTxgjaEOVRGVcHQ" alt=""><figcaption></figcaption></figure>

_Produced by DALLE, prompted with  A disorganized scene showing a Latin American tech startup managing remote tech workers. Politicians in an office eagerly watch a large screen display_

A few weeks later you get another message. The team using the dashboard are not finding it useful. They don’t know how to interpret the number they get each day. Your colleague has a few chats with them and eventually understands that what would be more useful is to know the change in the number of mentions from day to day. Again, that is a simple enough change. You change the final number that you output not to be number of posts that day `n_today`, but instead a percentage change relative to yesterday `(n_today - n_yesterday)/n_yesterday * 100`.\


In the meantime, you had a message from your CTO who tells you that he was about to show the dashboard to a new client but instead of showing a percentage increase it was showing ‘NaN %’! What does NaN mean? Once again you go into your code and run it through step by step. It turns out that the way the posts get assigned a URL has changed from [forum.com/posts\&postid=1234](http://forum.com/posts\&postid=1234) to forum.com/posts\&date =2024-07-21\&postid=1. As a result your program didn’t find any mentions at all from one day to the next. Then when you tried to get the percentage change you had to divide zero by zero giving you NaN - Not a Number. You update the code to read the new URL format.&#x20;

Finally things seem to be working out. The dashboard is no longer confused by unrelated mentions and the URL formats are not changing. Casually you hear some feedback from the team who maintain the relationship, they asked why there might be a delay between events and a spike in mentions online? Clearly it’s just some misunderstanding, so you don’t think anything of it. Then out of the blue you heard that Celia Sanchez, the politician, and her team have ended the contract. In a post-mortem you learned that they were seeing spikes in mentions the day after relevant events had caused more mentions. This meant that they were constantly behind the curve and were not able to get in front of events. In order to understand what was going on, you go back and dive into the data. Looking at the hour at which posts were made, there is always two periods of activity; in the early evening and again in the early hours after midnight just before everyone signs off and goes to sleep. As a result, your program is missing a lot of mentions in the daily count by running at midnight. Simply by running from 3AM - 3AM instead of 12 - 12 you could have caught these. Worse than that, by exploring the data more, you see that there is a weekly pattern; no-one posts on the weekend and the activity in the week is focused on the beginning and end with very little on Wednesdays. As a result all of the percentage changes were misleading.
