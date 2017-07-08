# Express Server

Node codealong with [Wes Bos](https://learnnode.com/)

## Notes

`app.js`
```js
const routes = require('./routes/index');

const app = express();
app.use('/', routes);

// done! we export it so we can start the site in start.js
module.exports = app;
```

`start.js`
```js

const app = require('./app');
app.set('port', process.env.PORT || 3000);
const server = app.listen(app.get('port'), () => {
  console.log(`Express running → PORT ${server.address().port}`);
});
```

`routes.js`
```js
const express = require('express');
const router = express.Router();

router.get('/', (req, res) => {
  res.send('Hey! It works!');
});

module.exports = router;
```

```js
res.json()
// Sends a JSON response. This method sends a response (with the correct content-type) that is the parameter converted to a JSON string using JSON.stringify().

// The parameter can be any JSON type, including object, array, string, Boolean, or number, and you can also use it to convert other values to JSON, such as null, and undefined (although these are technically not valid JSON).
```

```js
// access query from the url
// myapi.com/?name=cool
req.query.name // cool
```
