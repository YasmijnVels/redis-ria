# redis-ria


Integrates Discord.js caching with Redis.  Stores users, guilds, channels, messages, and emojis in a hash set of IDs (keys are the plural of the type: e.g. `users`, `messages`, etc.).  You can subscribe to channels named `[type]Set` and `[type]Delete` which will contain a payload of the resource ID.

changed in this version? 
support discord.js **v12.5.1**

## Example
```js
const discord = require('discord.js');
const { RedisClient } = require('redis-ria');

const client = new discord.Client();
const redis = new RedisClient(client, {});

redis.on('ready', () => console.log('Redis ready!'));
client.login('token');
```
