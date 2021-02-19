# connect-vuejs-with-nodejs

##Installation
```
npm install pg
npm install custom-env
```
##Create database.js
```
require("custom-env").env(true);
const { Pool } = require("pg");
const pool = new Pool({
user: process.env.DB_USER,
host: process.env.DB_HOST,
database: process.env.DB_NAME,
password: process.env.DB_PASSWORD,
port: process.env.DB_PORT,
});
pool.query("SELECT NOW()", (err, res) => {
console.log(err, res);
pool.end();
});
```

##Create a .env file in the root and define your variables
```
DB_USER=maha
DB_HOST=localhost
DB_NAME=maha
DB_PASSWORD=*******
DB_PORT=5432

```
