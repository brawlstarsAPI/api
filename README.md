# About the API
This is a Brawl Stars (Game by Supercell) API (details below) 
```json
{
    "base_url": "https://brawl-stars.herokuapp.com/api", 
    "endpoints": [
        "players/:tag", 
        "bands/:tag", 
        "events" 
    ], 
    "github":"https://github.com/brawlstarsAPI/api" 
}
``` 
The above JSON object can be retrieved by doing a `GET` Request to either `/` or `/api`

All requests should be `GET` requests 

Every response by the API is a JSON object. In any case we respond with a non-JSON object, please [create an issue](https://github.com/brawlstarsAPI/api/issues) so we can fix the error. 

# Errors
When the API provides an error, it uses the following format:

```json
{
    "error":true,
    "message":"message",
    "code":504,
    "details":"This field might or might not be provided by the API"
}
```

# Error Codes
| Code | Definition | Notes |
| ------------- | ------------- | ------------- | 
| 200 | OK | |
| 400 | Bad Request | You might be missing the `User-Agent` header, refer below |
| 403 | Forbidden | You might be blocked by the API, refer below |
| 404 | Invalid Endpoint | |
| 404 | Invalid Tag | |
| 500 | Unexpected Error | This is an error on our side and we will fix it ASAP. This would have a details field. |
| 504 | API Down | |

# What about Authentication?
We have not started using API Keys on the API but we might if too many people start using the API.

For now, please provide a `User-Agent` header in your request with the name of your application (This will be made necessary in the next API Update)

Users without the `User-Agent` header will be returned with a `400 Bad Request` once this is implemented. 

For example: `User-Agent: https://www.brawlstarsstats.com`

This would allow us to identify, and possibly contact the people using the API before we blacklist the IP Address.

# Blacklisted
**I'm blacklisted! What can I do?**   
To appeal, [create an issue](https://github.com/brawlstarsAPI/api/issues) on this github repository with the following details:   
- Your value in the User-Agent header
- Reason why your application made that many requests to the API
- How you fixed that issue

If, for some reason, you did not set a `User-Agent` header and got blacklisted, there is no way to appeal as of now (unless you would like to let everyone see your IP Address)
