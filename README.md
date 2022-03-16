# 🤖 Rewrite Bot

Pre-alpha, doesn't do anything, might crash your car.

For now this is just a project stub to try out [Probot](https://probot.github.io) with the
idea being that a bot picks up PR and issue Markdown editing events and rewrites short codes
into something else to save valuable key strokes.

For example, editing a PR description as

```markdown
### Test Plan

[do-the-repetetive-setup-thing]
* do another thing
```

would be transformed into

```markdown
### Test Plan

* run the app with this branch
* open http://localhost:1234
* go to http://localhost:1234/dashboard
* click on the thing
```

after the bot receives the event and rewrites the content.

## Local setup

Install dependencies

```
npm install
```

Start the server

```
npm start
```

Follow the instructions to register a new GitHub app.

## Deployment

The app is continuously deployed using [Vercel's GitHub app](https://github.com/apps/vercel).

## How it works

The [api/github/webhooks/index.js](api/github/webhooks/index.js) file is handling requests to
`POST /api/github/webhooks`, make sure to configure your GitHub App registration's webhook URL
accordingly.

## License

[ISC](LICENSE)
