# Phases

Friendly is going to be rolled out in multiple phases. Each phase is planned to be implemented in a quarter of the year, so this document is expected to be deprecated in 2027. Only labs from [Tier I](DEVELOPERS.md#tiers) are expected to implement this in time.

## Phase I. Match-making

> Delivery date: 2026.2

This is what most dating apps do. We are not such app (tho dating is arguably done better in Friendly than in the actual dating apps), but we need to start somewhere. During this phase we create an app to find people in the friends-of-friends circle.

It is expected to have little to no engagement as besides just finding people you don't have a way to interact with them in the app. Social link provides offloads all communication to other apps like Discord, Telegram, plain old email or whatever user decided to set as their social link.

In this phase people start to pour in the app and build their **Network**. We expect a big collaboration with [Sylvan Franklin](https://www.youtube.com/@sylvanfranklin) right after Phase I. Expected amount of users is at least one hundred.

## Phase II. Community

> Delivery date: 2026.3

After people from the first phase have built their network, they need to have a way of engaging with this network. During Phase II we are going to implement a **Community** feature. In **Community** you can talk to people from your **Network** by creating posts that are visible to people who added each-other.

Community targets for mutual communication. There's no way you can "subscribe" to someone. Only if they subscribe back to you. That is the whole idea of the app we build that should help with building local intranet communities whilst all the world tries to be global.

At that phase the amount of users doesn't matter. As users will increase people will not get better/worse UX from the app. It will stay fairly the same because people usually have just about a few undreds of people they can keep contact with.

## Phase III. Messenger

After public posts are refined, we finally can start to implement features that will allow to keep Friendly the only app people need for communication. That includes messenger with 1-to-1 chats, groups, everything you need from messenger.

Some development chats are going to migrate from Discord to Friendly during this phase. We will look for a new contributors during this phase and listen to other ideas people have in mind.

We will also help our catching-up laboratories to catch with the phases they didn't catch.

## Looking Forward

Something we are going to implement in a few years, but we don't have time and resources to do it right now.

### Transport 2.0

Migrate to a more efficient protocol from HTTP, presumably grpc, bson, cbor, etc. This will affect user experience A LOT. Considering that we will have instant messaging we can't operate on HTTP. We can implement some hacky solution over websockets + jsonrpc in the Phase III first, but it will all be unified in a single RPC endpoint for everything.

### Multi-accounts

We want to embrace multiple accounts usage since you might have different circles in your network that you don't want to interact with each-other. For example a family circle, english-speaking friends, your-native-language-speaking friends and others.

### Federations

As a free and open source piece of software, we embrace every bit of flexibility and freedom. Support for federations is going to be a major step in that direction. It is very hard to implement with limited resources we have currently, so that's why we defer implementation of it for better times. However, all the features are implemented having that in mind.
