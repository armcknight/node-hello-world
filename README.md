# node-hello-world

A simple Hello, World! server app using Node.js and Express.js deployable locally and on Heroku.

## Requirements

- [git](https://git-scm.com)
- [homebrew](https://brew.sh)
- [node](https://nodejs.org)
- [heroku cli](https://devcenter.heroku.com/articles/heroku-cli)

> Assuming you already have git and Homebrew, `brew install node heroku-cli`

## Create from scratch

```sh
# start new app
npm init --yes

# add express module
npm install express

# gitignore node modules
echo "node_modules/" > .gitignore

# write the server code
echo "const express = require('express')
const app = express()
const port = process.env.PORT || 3000

app.get('/', (req, res) => res.send('Hello World!'))

app.listen(port, () => console.log(`Example app listening on port ${port}!`))" > app.js

# make a Profile and package.json for Heroku
echo "web: node app.js" > Procfile
npm init --yes

# add the command to start node in package.json
sed -i '' 's/   \"scripts\": \{/  \"scripts\": \{\
    \"start\": \"node index.js\",/g' package.json
```

## Deployment

### Local

```sh
node app.js &
open http://localhost:3000
```

### Locally via Heroku

```sh
heroku local &
open http://localhost:3000
```

### Remote

```sh
heroku create # make sure your ‘heroku’ git remote points to the correct app's git url, like if there was a previous one
heroku config:set HOST=
git push heroku master
heroku open
```

## References

- [How do I start with Node.js after I installed it?](https://nodejs.org/en/docs/guides/getting-started-guide/)
- [Getting Started on Heroku with Node.js](https://devcenter.heroku.com/articles/getting-started-with-nodejs)

> References are archived as PDFs in `docs/`.
