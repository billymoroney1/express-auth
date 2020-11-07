1. initialize npm, git
2. make gitignore with node_modules
3. make entry point file

4. set up express and home route to test

const express = require('express')
const app = express()

app.get('/', (req, res) =>{
    res.send('express auth home route')
})

app.listen(8000, ()=>{
    console.log('you\'re listening to the sweet sounds of port 8000')
})

5. create controllers and include this code in entry point:

app.use('/auth', require('./controllers/auth.js'))

6. in controller, require express, create a router

const router = express.Router()

and export that router

module.exports = router

7. make routes in controller

router.get('/login', (req, res) => {
    res.send('GET /login successfully hit')
})

8. Set up views

npm i ejs express-ejs-layouts

const ejsLayouts = require('express-ejs-layouts')
app.set('view engine', 'ejs')
app.use(ejsLayouts)

9. Make layout.ejs, boilerplate, <%- body %>, etc

10. change any 'res.send' to res.render('with a file path here')

11. When making a form:

12. when retreiving post info, set up middleware

app.use(express.urlencoded({extended: false}))

13. Time for database:

install sequelize "npm i sequelize pg"

set up config file

sequelize db:create <name of database>
sequelzie model:create --name <> --attributes <>
sequelize db:migrate

check psql

14. require models wherever making routes and using sequelize functions
const db = require('../models')


-------------------

# To use this boilerplate
1. fork and clone
2. install dependencies
```
    npm i
```

3. Create a config.json with the following code:
```

3. create database

```
sequelize db:create 





