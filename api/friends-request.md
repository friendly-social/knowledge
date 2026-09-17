# /friends/request

Send a friend request to someone in your [Feed](feed-queue.md).

- URL: `https://api.getfriend.ly/friends/request`
- Method: `POST`
- Headers:
    - `Content-Type: application/json`
    - `X-User-Id: $userId`
    - `X-Token: $token`

## Request Body

```typescript
{
    "userId": number,
    "userAccessHash": string
}
```

- `userId` / `userAccessHash`
    - Identify the person you want to friend.

## 401 Not Authorized

If provided authorization is invalid.

## 200 Success

If the request was sent successfully.

## Example

```bash
curl https://api.getfriend.ly/friends/request \
    --request POST \
    --header "Content-Type: application/json" \
    --header "X-User-Id: $userId" \
    --header "X-Token: $token" \
    --data '{
        "userId": 123,
        "userAccessHash": "..."
    }'
```
