# /friends/generate

Generate a one-time invitation token so someone can add you as a friend, either
by scanning a QR code or opening a link.

- URL: `https://api.getfriend.ly/friends/generate`
- Method: `POST`
- Headers:
    - `Content-Type: application/json`
    - `X-User-Id: $userId`
    - `X-Token: $token`

Calling this again before the previous token is used returns that same token
instead of generating a new one. `/friends/generate/force` forces a new one.

## 401 Not Authorized

If provided authorization is invalid.

## 200 Success

```typescript
{
    "token": string
}
```

Combine this with your `id` to build a shareable link or QR code payload:

```
https://getfriend.ly/#?reference=add%2F{your id}%2F{token}
```

Whoever opens that link (or scans a QR code with it) calls
[/friends/add](friends-add.md) with your `id` and this `token`.

## /friends/generate/force

Always issues a new token and invalidates the previous.

- URL: `https://api.getfriend.ly/friends/generate/force`
- Method: `POST`
- Headers:
    - `Content-Type: application/json`
    - `X-User-Id: $userId`
    - `X-Token: $token`

## Example

```bash
curl https://api.getfriend.ly/friends/generate \
    --request POST \
    --header "Content-Type: application/json" \
    --header "X-User-Id: $userId" \
    --header "X-Token: $token"
```
