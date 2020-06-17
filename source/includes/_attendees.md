# Attendees

## Get All Attendees

```shell
curl "https://api.heysummit.com/api/attendees/" \
  -X GET \
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "count": 294,
    "next": "https://api.heysummit.com/api/attendees/?page=2",
    "previous": null,
    "results":[{
        "id": 245,
        "url": "https://api.heysummit.com/api/attendees/246/",
        "email": "joe@bloggs.com",
        "name": "Joe Bloggs",
        "registration_status": "Completed Order",
        "event_id": 24,
        "event_name": "Demo Summit ABC",
        "created_at": "2019-04-18T19:51:24.073422"
        "agreed_terms": "2020-06-15T23:14:52.970120",
        "affiliate_email": "affilaite1@testdomain.com",
        "speaker_referrer_email": null,
        "utm_source": "News Weekly",
        "utm_medium": "Article",
        "utm_campaign": "EMAIL-CHAIN-29561",
        "referer_ref": null,
        "http_referer": "https://subd.myreferralsite.com/",
        "http_referer_domain": "mydomain.com",
        "ip_address": "8.8.8.8",
        "categories": [
            {
                "id": 241,
                "event": 6,
                "title": "Motivation",
                "description": null
            }
        ],
        "talks": [
            "https://api.heysummit.com/api/talks/155/",
            "https://api.heysummit.com/api/talks/156/"
        ],
        "questions": [],
        "tickets": [
            {
                "ticket_id": 10,
                "ticket_name": "Free Access",
                "amount_gross": null,
                "amount_net": null,
                "created_at": "2020-06-15T23:14:56.309526"
            }
        ]
    },{
        "id": 246,
        "url": "https://api.heysummit.com/api/attendees/246/",
        "email": "joe@bloggs.com",
        "name": "Joe Bloggs",
        "registration_status": "Completed Order",
        "event_id": 24,
        "event_name": "Demo Summit ABC",
        "created_at": "2019-04-18T19:51:24.073422",
        "agreed_terms": "2020-06-15T23:14:52.970120",
        "affiliate_email": "affilaite1@testdomain.com",
        "speaker_referrer_email": null,
        "utm_source": "News Weekly",
        "utm_medium": "Article",
        "utm_campaign": "EMAIL-CHAIN-29561",
        "referer_ref": null,
        "http_referer": "https://subd.myreferralsite.com/",
        "http_referer_domain": "mydomain.com",
        "ip_address": "8.8.4.4",
        "categories": [
            {
                "id": 240,
                "event": 6,
                "title": "Empowerment",
                "description": null
            },
            {
                "id": 241,
                "event": 6,
                "title": "Motivation",
                "description": null
            }
        ],
        "talks": [
            "https://api.heysummit.com/api/talks/155/",
            "https://api.heysummit.com/api/talks/156/"
        ],
        "questions": [],
        "tickets": [
            {
                "ticket_id": 10,
                "ticket_name": "Free Access",
                "amount_gross": null,
                "amount_net": null,
                "created_at": "2020-06-15T23:14:56.309526"
            }
        ]
        ...
    }]
}
```

This endpoint retrieves all Attendees linked to your account.

### HTTP Request

`GET https://api.heysummit.com/api/attendees/`

### Query Parameters

Parameter | Description
--------- | ------- | -----------
event | The ID of the event you want to filter the list of Attendees by

## Get an Attendee

```shell
curl "https://api.heysummit.com/api/attendees/1234/" \
  -X GET \
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "id": 246,
    "url": "https://api.heysummit.com/api/attendees/246/",
    "email": "joe@bloggs.com",
    "name": "Joe Bloggs",
    "registration_status": "Completed Order",
    "event_id": 24,
    "event_name": "Demo Summit ABC",
    "created_at": "2019-04-18T19:51:24.073422",
    "agreed_terms": "2020-06-15T23:14:52.970120",
    "affiliate_email": "affilaite1@testdomain.com",
    "speaker_referrer_email": null,
    "utm_source": "News Weekly",
    "utm_medium": "Article",
    "utm_campaign": "EMAIL-CHAIN-29561",
    "referer_ref": null,
    "http_referer": "https://subd.myreferralsite.com/",
    "http_referer_domain": "mydomain.com",
    "ip_address": "8.8.8.8",
    "categories": [
        {
            "id": 241,
            "event": 6,
            "title": "Motivation",
            "description": null
        }
    ],
    "talks": [
        "https://api.heysummit.com/api/talks/155/",
        "https://api.heysummit.com/api/talks/156/"
    ],
    "questions": [],
    "tickets": [
        {
            "ticket_id": 10,
            "ticket_name": "Free Access",
            "amount_gross": null,
            "amount_net": null,
            "created_at": "2020-06-15T23:14:56.309526"
        }
    ],
}
```

This endpoint retrieves an Attendee.

### HTTP Request

`GET https://api.heysummit.com/api/attendees/<ID>/`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Attendee to retrieve

## Add an Attendee


```shell
curl "https://api.heysummit.com/api/attendees/" \
  -X POST \
  -d '{"event":1234, "email":"joe@bloggs.com", "name":"Joe Bloggs"}' \
  -H "Content-Type: application/json" \
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "id": 246,
    "url": "https://api.heysummit.com/api/attendees/246/",
    "email": "joe@bloggs.com",
    "name": "Joe Bloggs",
    "event_id": 24,
    "event_name": "Demo Summit ABC",
    "created_at": "2019-04-18T19:51:24.073422",
    "agreed_terms": "2020-06-15T23:14:52.970120",
    "affiliate_email": null,
    "speaker_referrer_email": null,
    "utm_source": null,
    "utm_medium": null,
    "utm_campaign": null,
    "referer_ref": null,
    "http_referer": null,
    "http_referer_domain": null,
    "ip_address": null,
    "categories": [],
    "talks": [],
    "questions": [],
    "tickets": []
}
```

This endpoint creates a new Attendee for the Event passed.

<aside class="warning">Please note that once the Attendee has been added, you may still need to add them to Talks. It is also assumed that any Attendee added, has accepted your terms and conditions and has agreed to be added to this Event and emailed regarding the event (with reminders and notifications relating to the talks they are booked into).</aside>


### HTTP Request

`POST https://api.heysummit.com/api/attendees/`

### URL Parameters

Parameter | Required | Description
--------- | ----------- | -----------
event | Yes | The ID of the Event you want to add this attendee to
email | Yes | The email address of the Attendee you're adding
name | Yes | The name of the Attendee you're adding
ticket_id | No | The ID of the Ticket you want to add for this attendee
