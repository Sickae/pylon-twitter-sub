# Twitter Sub

Twitter Sub is a [Pylon](https://pylon.bot) app for Discord, allowing dynamic subscriptions to Twitter feeds. With simple commands you, can follow any user you want and have their tweets posted to the channel you select on your server.

# Commands

*  `!twitter sub <username: string> (channel: string)`
    > Subscribes to a Twitter feed in the channel you select.
    ---
    - **username**: Username of the twitter user (eg: IGN)
    - **channel**: The discord channel mentioned you want the tweets to be posted in. Leaving this parameter will default to the channel you send your message in.
    > **Example:** `!twitter sub ign #ign-tweets`

* `!twitter unsub <username: string>`
    > Unsubscribes from a Twitter feed.
    - **username**: Username of the twitter user (eg: IGN)
    > **Example:** `!twitter unsub ign`

* `!twitter list`
    > Lists all the active Twitter feed subscriptions and the channels they're assigned to.

* `!twitter poll`
    > Manually polls all the subscribed Twitter feeds once.

# Basic Info

The app automatically polls all the subscribed Twitter feeds every 5 minutes and posts only the tweets that haven't been posted yet to their assigned channel. Upon a new subscription via `!twitter sub`, the latest tweet from the given Twitter feed will be posted.

# Setting It Up

You will need to have access to the Twitter API, meaning you need to have a Twitter Developer account. You can apply for one freely [here](https://developer.twitter.com/en/apply-for-access).

1. Setup your initial configuration inside the `twitter-sub.ts` file. You need to change the property values of `TwitterSubCfg`.
    * `TWITTER_API_KEY`: Required to communicate with the Twitter API. You will find it in your Twitter Developer Portal.
    * `TWITTER_BEARER_TOKEN`: Required to authenticate yourself while sending requests to the Twitter API. You will find it in your Twitter Developer Portal.
    * `ICON_URL`: An image link that the app will use as its icon. By default it is a Twitter icon.
    * `REQUIRED_ROLE_ID`: Only users that have this role will be able to use the Twitter Sub commands. Optionally you can leave it empty to enable it for everyone.

2. Import the `twitter-sub.ts` file inside your `main.ts` file.
    > `import 'twitter-sub';`

