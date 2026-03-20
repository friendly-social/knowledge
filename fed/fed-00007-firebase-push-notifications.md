# Firebase Push Notifications

There are many ways to set up push notifications, but the easiest crossplatform solution is to use Firebase Services. They are built-in for Android Devices and also have interoperability with [iOS APNs](https://firebase.google.com/docs/ios/setup) and [Web Pushes](https://firebase.google.com/docs/cloud-messaging/web/get-started).

For that reason, server supports attaching a firebase token to an existing user token. Note that firebase tokens may be updated/revoked and app logic should be able to handle these cases. If a delivery fails, client should retry infinitely with some delay to avoid DDoS-attacks. Even if application restarts, it should check on startup whether it sent token to server and retry if not.

Multiple user tokens can be generated (for example if user uses Friendly on multiple devices), a unique firebase token can be attached to each of the user tokens, so user will receive notifications on both devices.

## Sign out

Push notifications is the reason why you should call sign out method on the server. Otherwise the app will continue receive notifications when a user signed-out. That is also going to reduce server load when sending a notification. But server should obviously handle the case when client didn't call sign out method and token expired, because app might be deleted and no callbacks are reveived in that case.
