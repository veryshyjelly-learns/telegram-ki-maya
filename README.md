> [!NOTE]
> Archived component of the Setu group-bridging experiment.
> Setu used a shared bot to bridge groups through modular platform adapters.
> It explores a different architecture from [Bifrost](https://github.com/veryshyjelly/bifrost), my current messaging project.

# Setu Telegram adapter

The Telegram adapter for [Setu Engine](https://github.com/veryshyjelly-learns/setu-engine). It exposes chat events and messaging through a WebSocket interface for the group bridge.

Related component: [whatsapp-ki-maya](https://github.com/veryshyjelly-learns/whatsapp-ki-maya).

## Historical setup

## Usage
### Get Bot Token From BotFather
- Create a new bot from [BotFather](https://t.me/BotFather)
- Get the bot token from BotFather
- Set the bot token as environment variable
```bash
TOKEN=<bot_token>
```

### Using Docker
- Build the docker image
```bash
docker build -t telegram-ki-maya .
```
- Run the docker container
```bash
docker run -d -p 8060:8060 --name telegram-ki-maya telegram-ki-maya
```

### Using Golang
- Install Golang
- Run the application
```bash
go run main.go
```

### Connecting to Websocket
- Get the chat id from the bot
  - Add the bot to a group
  - Use the command `/chat_id` in the group
  - Save the chat id for later use
- Using Postman
  - Create a new request
  - Set the request type to `WebSocket`
  - Set the request URL to `ws://localhost:8060/ws?sub=$chat_id`
  - Click on `Connect` button
  - Send the first message as API token
  - You are now connected to the bot