---
title: HeySummit API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://heysummit.com'>&copy; HeySummit.com</a>

includes:
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

# Events

## Get All Events

```shell
curl "https://api.heysummit.com/api/events/"
  -X GET
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "count": 17,
    "next": "https://api.heysummit.com/api/events/?page=2",
    "previous": null,
    "results":[{
        "id":"1234",
        "url":"https://api.heysummit.com/api/events/1234/",
        "title":"Demo Event ABC",
        "event_url":"https://event.example.com",
        "first_talk_at":"2019-05-19T11:53:52",
        "last_talk_at":"2019-05-31T12:44:00",
        "is_live": true,
        "is_archived": false,
        "is_evergreen": false,
        "is_open_for_registrations": true
    },{
        "id":"1234",
        "url":"https://api.heysummit.com:8000/api/events/1234/",
        "title":"Demo Event ABC",
        "event_url":"https://event.example.com",
        "first_talk_at":"2019-05-19T11:53:52",
        "last_talk_at":"2019-05-31T12:44:00"
        ...
    }]
}
```

This endpoint retrieves all Events linked to your account.

### HTTP Request

`GET https://api.heysummit.com/api/events/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
is_live | [No Default] | Set this to True to filter Events that are currently marked as Live
is_archived | [No Default] | Set this to True to filter Events that are currently marked as Archived
is_evergreen | [No Default] | Set this to True to filter Events that are setup as Evergreen events
is_open_for_registrations | [No Default] | Set this to True to filter Events that are open for registrations

## Get an Event

```shell
curl "https://api.heysummit.com/api/events/1234/"
  -X GET
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "id":"1234",
    "url":"https://api.heysummit.com/api/events/1234/",
    "title":"Demo Event ABC",
    "event_url":"https://event.example.com",
    "first_talk_at":"2019-05-19T11:53:52",
    "last_talk_at":"2019-05-31T12:44:00",
    ...
}
```

This endpoint retrieves an event.

### HTTP Request

`GET https://api.heysummit.com/api/events/<ID>/`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Event to retrieve

## Archive an Event


```shell
curl "https://api.heysummit.com/api/events/1234/archive/"
  -X POST
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "id":"1234",
    "url":"https://api.heysummit.com/api/events/1234/",
    "title":"Demo Event ABC",
    "event_url":"https://event.example.com",
    "first_talk_at":"2019-05-19T11:53:52",
    "last_talk_at":"2019-05-31T12:44:00",
    ...
}
```

This endpoint archives an Event.

<aside class="warning">Please note that archiving an Event will make it invisible to the public.</aside>


### HTTP Request

`POST https://api.heysummit.com/api/events/<ID>/archive/`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Event to archive
