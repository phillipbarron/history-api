# History API response mocks

These are propsed History API response mocks

### Event Structure

```javascript
{
  "eventId": "GUID",
  "assetId": "String",
  "type": [
    "Created",
    "Saved",
    "Withdrawn",
    "Deleted",
    "Restored",
    "MinorUpdatePublished",
    "Published"
  ],
  "timestamp": "Date",
  "userId": "some.one@bbc.co.uk",
  "assertVersion": "SemVer"
},
```

## Events

initial proposal does not leave space for headline & version would be inferred

GET:`/events/{assetId}?page=n`
[mock](https://github.com/phillipbarron/history-api/blob/master/mocks/events.json)

## History

added in headline and events and renamed results to events

GET:`/history/{assetId}?page=n`
[mock](https://github.com/phillipbarron/history-api/blob/master/mocks/history.json)

## History with full range of events

GET:`/history/{assetId}?page=n`
[mock](https://github.com/phillipbarron/history-api/blob/master/mocks/history-with-all-events.json)

## History with pagination

GET:`/history/{assetId}?page=n`
[mock](https://github.com/phillipbarron/history-api/blob/master/mocks/history-with-pagination.json)

## Questions

* should we move the assetId out of the `Event` item and include it only at the route?

  ```javascript
  {
    "version": "0.0",
    "assetId": "cq915kk4wy5o",
    "headline": "Man bites dog",
    "totalCount": 37,
    "hasNextPage": false,
    "history": [
      {
        "version": 0,
        "events": [
          {
            "eventId": "2a925310-e7f9-4a5b-9fd0-25e368ec5b40",
            "type": "Published",
            "timestamp": "Mon, 24 Jun 2019 21:09:04 GMT",
            "userId": "some.one@bbc.co.uk",
            "assertVersion": 0.0
          }
        ]
      },
      {
        ...
      }
    ]
  }
  ```
