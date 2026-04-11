
# Profile

> Authors: @y9san9, discusssed with @demndevel

This decision describes MVP profile feature and what we want to see there.

## Signup

Signup process is designed to be as little as possible. Usually you need to provide your email/phone number to make it easier to limit potential spam activity.

We don't ask user to provide email/phone number. To sign up, you only need to provide a set of fields that are going to be used to later show you to other users.

This decision is a deliberate choice that was made because we don't have anything public, so spam makes little sense. People can easily ban spammers without our help.

You can link email later when you edit profile, that is going to be described in the later FEDs.

## Fields

User Profile consists of these fields:

- **Nickname**
    - **Not unique.** Whatever user wants other users to see. We don't have any public unique identifiers
    - **Length:** 1...256
    - **Required.** Clients don't need to check and should always allocate some space for nickname
- **Description**
    - **Length:** 1...2024
- **Social Link**
    - Should be rendered as a 'Message' icon which is opened when you click on it
    - Link should be validated with the following Regex: `((http|https):\/\/)?\w+\.\w+.*`
      <sub>You may need double escapes: `((http|https):\\/\\/)?\\w+\\.\\w+.*`</sub>
    - **Length:** 1...2048
    - **Optional.** Clients should have dynamic layout for absent social link
- **Interests**
    - Arbitrary strings representing interests of the user. Can be in any language. May be used to find better matches between users
    - **Max Amount**: 100
    - **Length of each**: 1..64
    - **Optional**
- **Avatar**
    - Clients better send square images, but not required for simplicity
    - Clients **must** crop images to be square even if they received a rectangle one
    - Clients should compress images, since in MVP users will have 20mb of file space for everything

## Not Public

In Friendly we are trying to reduce show off and popularity in order to achieve more honest communication. Therefore, not in MVP, nor in the future versions (as we currently see the project).

Profile does not include information about how much friends they have, who are they. Common friends are only shown in the Feed, not in any other place.
