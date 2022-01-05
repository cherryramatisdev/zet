# solution purpose to return professional data on availability route @work

## The problem
1. The problem we have today is that we can't show activity price and activity name data on professional card component
2. Another problem we have is to show professional description from tuotempo api

## The solution
1. Here we'll return a top level object with professional data and an array for availabilities, this was the first design but we tried to be simpler and don't work, this solution will solve on our current frontend architecture

```json
{
  "searchid": "{\"tt_dbmed_test\":\"61d57efd7372a|d7f345b773b769a6f8b17a3ba12e6f0d|0\"}",
  "professionalId": "sc16152e732d6194",
  "name": "Fisioterapista Lami Bergamo",
  "activityTitle": "",
  "activityPrice": 0,
  "availabilities": [
    {
      "searchid": "{\"tt_dbmed_test\":\"61d57efd7372a|d7f345b773b769a6f8b17a3ba12e6f0d|0\"}",
      "id": "sc16078566a6a6f0",
      "professionalId": "sc16152e732d6194",
      "name": "Fisioterapista Lami Bergamo",
      "description": null,
      "startDate": "2022-01-05T15:30:00.000Z",
      "formattedStartDate": "05/01/2022",
      "endDate": "2022-01-05T15:30:00.000Z",
      "formattedEndDate": "05/01/2022",
      "startTime": "2022-01-05T15:30:00.000Z",
      "formattedStartTime": "12:30",
      "endTime": "2022-01-05T15:30:00.000Z",
      "formattedEndTime": "12:30",
      "activityTitle": "",
      "activityPrice": 0
    },
    {
      "searchid": "{\"tt_dbmed_test\":\"61d57efd7372a|d7f345b773b769a6f8b17a3ba12e6f0d|0\"}",
      "id": "sc1607856f7928da",
      "professionalId": "sc16152e732d6194",
      "name": "Fisioterapista Lami Brescia",
      "description": null,
      "startDate": "2022-01-05T15:30:00.000Z",
      "formattedStartDate": "05/01/2022",
      "endDate": "2022-01-05T15:30:00.000Z",
      "formattedEndDate": "05/01/2022",
      "startTime": "2022-01-05T15:30:00.000Z",
      "formattedStartTime": "12:30",
      "endTime": "2022-01-05T15:30:00.000Z",
      "formattedEndTime": "12:30",
      "activityTitle": "",
      "activityPrice": 0
    }
  ]
}
```

2. This is mostly a try and nor a finish solution because the database is mostly empty on this aspect, but the idea is to use `cv_text` field as professional description
