# /users/details/{id?}/{accessHash?}

- URL: `https://api.getfriend.ly/users/details`
- Method: `PATCH`
- Headers:
    - `Content-Type: application/json`
    - `X-User-Id: $userId`
    - `X-Token: $token`

## Parameters

- `id`
    - Long
    - id of the user you want to get
- `accessHash`
    - String
    - accessHash of the user you want to get

You can omit both parameters to get your own profile, or specify both to get
someone else's profile.

## 400 Bad Request

If there is a validation error. This code usually means a logical error in the
implementation of SDK you are using.

## 401 Not Authorized

If provided authorization is invalid.

## 404 Not Found

If user with `id` and `accessHash` was not found.

## 200 Success

If user was found.

### Response Body

```typescript
{
    "id": Long,
    "accessHash": String,
    "nickname": String,
    "email": String?,
    "description": String,
    "interests": String[],
    "avatar": FileDescriptor?,
    "socialLink": String?,
}
```

- `nickname`
    - Length: `1...256`
- `email`
   - Nullable
   - Set via `/email/link`
   - Unset via `/email/unlink`
   - **Only returned for your own profile**
- `description`
    - Length: `1...1024`
- `socialLink`
    - Length: `1...2048`
    - Nullable
    - There is no server validation whether this is a valid link
- `interests`
    - Max Amount: `100`
    - Length of each: `1..64`
- `avatar`
    - Obtained via `/files/upload`

## Example

```bash
curl https://api.getfriend.ly/users/details
    --request PATCH \
    --header "Content-Type: application/json" \
    --header "X-User-Id: $userId" \
    --header "X-Token: $token" \
```

This curl request works for a user with $userId and $token.
