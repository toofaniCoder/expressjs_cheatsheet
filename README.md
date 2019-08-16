## ExpressJS CheatSheet

### Basic
```javascript
const express = require("express");
const app = express();
const port = 3000;

app.get("/", (req, res) => {
    res.send("hello world!");
});

app.listen(port, () => console.log(`Server app listening on port ${port}!`));
```

### Basic Routes
```javascript
app.get('/', function (req, res) {
  // your code goes here
})
```

```javascript
app.post('/', function (req, res) {
  // your code goes here
})
```

```javascript
app.put('/', function (req, res) {
  // your code goes here
})
```

```javascript
app.delete('/', function (req, res) {
  // your code goes here
})
```


### Router Routes
```javascript
router.get('/', function (req, res) {
  // your code goes here
})
```

```javascript
router.post('/', function (req, res) {
  // your code goes here
})
```

```javascript
router.put('/', function (req, res) {
  // your code goes here
})
```

```javascript
router.delete('/', function (req, res) {
  // your code goes here
})
```

### Setting Static Files

```javascript
// basic syntax
app.use(express.static('public'))

// use multilpe dir for assets
app.use(express.static('public'))
app.use(express.static('files'))

// use virtual prefix path
app.use('/static', express.static('public'))

app.use(express.static(path.join(__dirname, 'public')))

app.use('/static', express.static(path.join(__dirname, 'public')))
```


### Body Parser Middleware

```javascript
var bodyParser = require('body-parser')

// parse application/x-www-form-urlencoded
app.use(bodyParser.urlencoded({ extended: false }))

// parse application/json
app.use(bodyParser.json())
```

### Mongoose Middleware

```javascript
// Using Node.js `require()`
const mongoose = require('mongoose');

// Using ES6 imports
import mongoose from 'mongoose';
```

```javascript
const mongoose = require('mongoose');

mongoose.connect('mongodb://localhost/my_database', {useNewUrlParser: true});
```

```javascript
const Schema = mongoose.Schema;
const ObjectId = Schema.ObjectId;

const BlogPost = new Schema({
  author: ObjectId,
  title: String,
  body: String,
  date: Date
});
```


```javascript
const MyModel = mongoose.model('ModelName');
// or
const MyModel = mongoose.model('ModelName', mySchema);

```

### Express Handlebars

```javascript
// import
const exphbs  = require('express-handlebars');

// set view engine
app.engine('handlebars', exphbs());
app.set('view engine', 'handlebars');

// render
app.get('/', function (req, res) {
    res.render('home');
});
```