---
layout: post
title: Using Rancher to deploy Feel Good News app backend on Kubernets
excerpt: "Take my horse to the old town road!"
categories: [Kubernets, Rancher]
comment: true
share: true
---

> TL;DR: this deployment was overkill but I learned a lot. Hats off to all the DevOps out there.

Some days ago I launched an app on both iOS and Andriod with help from a friend (frontend is not my cup of tea). The backend, however, I wrote in python. The app is based on a very simple concept, use a sentiment analysis algorithm to filter out sad, negative, and gloomy news from the news feed. The app is very rudimentary; it will show you different categories of news to select from and then you can scroll the feed to read the gist of news, if you like what you see from the gist, just click on the news item and it will redirect you to the original article.

The architecture of the app is very simple. It collects the news from some predefined news sources and runs sentiment analysis on them using out of the box sentiment analysis algorithm from flair's NLP library. If the sentiment is positive we push it to the app. Currently, the app is restricted to show news from Indian news media outlets, but plans are in place to give the user the choice to select the country that they want to get the news from, and then they can select news media outlets of their liking. You can check out the apps here: Android, iOS.

![clustersetup](https://raw.githubusercontent.com/jdvala/website/master/img/cluster_setup.png?token=AFYSSSZI4MJPG3QLF7FSRHS7L2BNG)

