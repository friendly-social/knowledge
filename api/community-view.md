# /community/view

- URL: `https://api.getfriend.ly/{id}/{accessHash}/view`
- Method: `POST`
- Headers:
    - `Content-Type: application/json`
    - `X-User-Id: $userId`
    - `X-Token: $token`

Invoke that when post is opened with focus on it. This resets `newReply` property for `CommunityPostDetails`.

If `newReply.transitive` is true, this method does nothing.

Transitive means that new reply was posted not as a direct reply to this post (deeper in threads).

## Parameters

- `id`
    - Long
    - id of the post you want to view
- `accessHash`
    - String
    - accessHash of the post you want to view

## 400 Bad Request

If there is a validation error. This code usually means a logical error in the
implementation of SDK you are using.

## 401 Not Authorized

If provided authorization is invalid.

## 404 Not Found

If user with `id` and `accessHash` was not found.

## 200 Success

If user was found.

## Example

```bash
curl https://api.getfriend.ly/auth/login
    --request POST \
    --header "Content-Type: application/json" \
    --data '{
        "email": "mail@example.com",
        "code": 11111111,
    }'
```
