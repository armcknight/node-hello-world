# node-hello-world

A simple Hello, World! server app using Node deployable locally and on Heroku.

## Requirements

- [git](https://git-scm.com)
- [homebrew](https://brew.sh)
- [node](https://nodejs.org)
- [heroku-cli]()

> Assuming you already have git and Homebrew, `brew install node heroku-cli`

## Create from scratch

```sh
# write the server code to file
echo "const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});" > app.js

# make a Profile and package.json for Heroku
echo "web: node app.js" > Procfile
npm init --yes
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
git push heroku master
heroku open
```

## References

- [How do I start with Node.js after I installed it?](https://nodejs.org/en/docs/guides/getting-started-guide/)
- [Getting Started on Heroku with Node.js](https://devcenter.heroku.com/articles/getting-started-with-nodejs)

> References are archived as PDFs in `docs/`.
