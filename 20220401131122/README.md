# architecture of the route that will retrieve questions from
dispositions @lami

We'll create a route that accept an `algorithm` id, an array of which
question was accepted and the last disposition that was retrieved.

With this info, our aim is to be totally stateless

So if the user provide an `null` last disposition and an empty array of
accepted questions, we'll get the available dispositions(ordered ASC)
and return the first one(100 for example)

If the user provide some last disposition and an array with some accepted
questions, we'll get the result message from that disposition and return
(100 will be "Call 911 Now")

If the user provide the last disposition as `99` and an array with some accepted questions, we'll handle it differently because we need to change the algorithm at this point, so we'll return the last algorithm given by user and the new one(as `currentAlgorithm`) that it should be used

Our response will be always this:

```json
{
  "lastAlgorithm": "<number>",
  "currentAlgorithm": "<number>",
  "questions": [
    {
      "dispositionNumber": "<number>",
      "question": "<string>"
    }
  ]
}
```
