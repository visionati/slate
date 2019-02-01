# Errors

> Below is a sample error message.

```json
{"error":"Invalid URLs detected."}
```

The Visionati API uses the error codes below. Many errors can be returned during
normal API usage. Developers should always look at the `error` key on any returned
JSON response!

Error Code | Meaning
---------- | -------
500 | Internal Server Error -- We had a problem with our server. Try again later.
