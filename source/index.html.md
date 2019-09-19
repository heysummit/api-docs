---
title: HeySummit API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://heysummit.com'>&copy; HeySummit.com</a>

includes:
  - events
  - talks
  - attendees
  - errors

search: true
---

# Introduction

Welcome to the HeySummit API. If you're on our [Business plan](https://heysummit.com) then you're able to take advantage of our powerful API to pull data out (such as events, attendees, speakers) and also push data into your HeySummit event (such as registering attendees, importing external ticket sales and much more).

We have language examples in Shell (with other platform examples coming soon)! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

HeySummit uses API Keys to allow access to the API. You can find your API Key on the [API Settings](https://heysummit.com/quick-launch/?path=/manage/event/api-settings/) page, when logged into your HeySummit account..

The API Key needs to be included in ALL API requests to the server in a header that looks like the following:

`Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e`

<aside class="notice">
Please make sure you replace <code>e3c0c748fe9b55386eecc07c339ec4099a8b9b0e</code> with your own API Key!
</aside>
