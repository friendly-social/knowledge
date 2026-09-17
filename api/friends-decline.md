# /friends/decline

Decline someone in your [Feed](feed-queue.md).

- URL: `https://api.getfriend.ly/friends/decline`
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
    - Identify the person you want to decline

## 401 Not Authorized

If provided authorization is invalid.

## 200 Success

If the person was declined.

## Example

```bash
curl https://api.getfriend.ly/friends/decline \
    --request POST \
    --header "Content-Type: application/json" \
    --header "X-User-Id: $userId" \
    --header "X-Token: $token" \
    --data '{
        "userId": 123,
        "userAccessHash": "..."
    }'
```
