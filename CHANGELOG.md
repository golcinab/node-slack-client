### v2.0.6 (2016-03-01)

  * Fixes a crash introduce in `2.0.5` if you try and instantiate a `WebClient` without passing in any options

### v2.0.5 (2016-03-01)

  * Updates the way that API requests are throttled to:
    * avoid a condition where the request queue callback could be called multiple times, causing a crash
    * refactor the logic in `_callTransport` into multiple functions to make it easier to follow
  * Updates dev dependencies:
    * eslint
    * nock
    * eslint-config-airbnb

### v2.0.4 (2016-02-28)

  * Passes through the logLevel param to the getLogger function

### v2.0.3 (2016-02-28)

  * The RTM `AUTHENTICATED` event now also emits the `rtm.start` payload
  * Fixes the way that loggers are instantiated and used, so that the JSDoc for `opts.logger` is correct

### v2.0.2 (2016-02-15)

  * Adds coveralls to the repo, to track code coverage and display a badge in the README
  * Updates the disconnect function on the RTM client to support both an error message and a code or reason for the disconnect, e.g. `account_inactive`
  * Updates the message-handlers for `team_xxx` events to set the team back to the data-store once changes are made

### v2.0.1 (2016-02-13)

  * Updates to `ws@1.0.1`
  * Fixes a bad variable name in [`example-web-client`](/examples/example-web-client.js)

### v2.0.0 (2016-02-13)

  Refactors the library to javascript, adds a lot of tests and restructures it to improve maintainability and extend functionality.
  * Creates two separate clients:
    - RTM; manages connection to Slack's RTM API, including reconnects
    - Web; provideas a callback interface to all of Slack's Web API endpoints
  * Moves the memory data store implementation off the clients and into its own class
  * Uncouples the model objects from the clients; model functions to send messages to channels etc are now accessed via the web and RTM client
  * Moves the transport layer (websockets and HTTP) to a pluggable model, so that complex transports (through request proxies etc) can be handled
  * Adds test coverage on most core functionality in the library

### v1.5.1 (2015-12-15)

  * Adds support for a request-proxy URL to use the client from behind a proxy

### v1.5.0 (2015-12-01):

  * Updates the ws library from 0.4.3 to 0.8.1
  * Reconnects when a `team_migration_started` event is received
  * Supports finding users by email from the memory data store
  * Fixes the getUnreadCount and getChannelsWithUnreads functions
  * Emits error code and message when the ws closes
  * Removes no-op call when a `ping` is received on the websocket

### v1.4.0 (2015-02-25):

  * Added callbacks to all API calls ([#20](https://github.com/slackhq/node-slack-client/pull/20))
  * Added support for star added/delete events ([#27](https://github.com/slackhq/node-slack-client/pull/27)
  * Fixed sample code ([#18](https://github.com/slackhq/node-slack-client/issues/18))
  * `getChannelByName` now strips leading hash marks ([#9](https://github.com/slackhq/node-slack-client/pull/9))
  * Dropped support for Node 0.8 ([#25](https://github.com/slackhq/node-slack-client/pull/25))
  * Fix duplicate scripts entries in package.json ([230c7f74](https://github.com/slackhq/node-slack-client/commit/230c7f743a48f600aff5660367cf1e6816cc67e2))

### v1.3.1 (2015-02-03):

  * Added ability to call chat.postMessage web API method ([#15](https://github.com/slackhq/node-slack-client/pull/15))
  * Added ability to update and delete messages ([#14](https://github.com/slackhq/node-slack-client/pull/14) and [#17](https://github.com/slackhq/node-slack-client/pull/17))
  * Added sample code ([7ee93a7b](https://github.com/slackhq/node-slack-client/commit/7ee93a7bd51c97519d6d5deb54bd8058612a9b19))
  * Fixed `getChannelsWithUnreads` ([#8](https://github.com/slackhq/node-slack-client/pull/8))
  * Fixed race condition when emitting `open` event ([#19](https://github.com/slackhq/node-slack-client/pull/19))

### v1.2.2 (2014-12-16):

  * Compile coffeescript to JS before publishing to NPM ([#6](https://github.com/slackhq/node-slack-client/pull/6))
  * Fixed typo in docs ([#2](https://github.com/slackhq/node-slack-client/pull/2/files))

### v1.2.0 (2014-12-08)

  * First public release
