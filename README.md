## workonflow-bot-client ##

#### Установка

```js
$ npm install workonflow-bot-client

const botConnect = require('workonflow-bot-client').connect

const creds = {
  email: "you email",
  password: "you password"
}

const botClient = await botConnect(creds)
```

### Как использовать ###

```js
const botClient = await botConnect(creds)

const { comment } = botClient

comment.onDirect(async message => {
  console.log('ON_DIRECT', message)
  const { teamId } = message
  const to = message.data.content.from

  const att = [{ type: 'text', data: { text: "text for response" } }]
  const resp = await comment.create(teamId, { to, att })
  console.log('resp', resp)
})
```

##[Документация](https://github.com/workonflow/bot-client-docs)##
