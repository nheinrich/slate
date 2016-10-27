# Errors

<aside class="notice">
  Errors returned by the API at any endpoint.
</aside>

Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is unrecognized or malformed
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- The data requested is hidden for administrators only
404 | Not Found -- The specified sensor could not be found
405 | Method Not Allowed -- You tried to access a sensor with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.
