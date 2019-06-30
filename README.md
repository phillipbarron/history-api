# Proposal for History API

These can form the mockm responses for dev testing - we would expect some variation however this is likely to be modest. 

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

GET:`/events/{assetId}`
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

## State

GET: `/state/{assetId}/{eventId}`
[mock](https://github.com/phillipbarron/history-api/blob/master/mocks/state.json)
