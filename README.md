
User Management
===============

Client
======


### Constructor

```
var ConcordaClient = require('concorda').Client
var client = new ConcordaClient({
  host: '', // optional for browser
  endpoint: '/auth',
  port: 80, // optional for browser
})
```





Authentication
--------------

### client.login()

```
client.login(username, password)
{
  email: 'john.doe@example.com',
  metadata: {
    ...
  },
  sessionToken: '',
  sessionExpiry: ''
}
```

### client.getCurrentUser()

```
client.getCurrentUser()
{
  email: 'john.doe@example.com',
  roles: [],
  metadata: {
    ...
  }
}
```

### client.renewSession()

```
client.renewSession()
{
  sessionToken: ''
  sessionExpiry: ''
}
```

### client.logout()

```
client.logout()
{}
```

### client.resetPassword()

```
client.resetPassword()
{
  resetTokenExpiry: ''
}
```





for node-app use
----------------

### client.verifySessionToken(email, sessionToken)

```
client.verifySessionToken(email, sessionToken)
{
  email: 'john.doe@example.com',
  roles: [],
  metadata: {
    ...
  }
}
```





Administration API
------------------


### client.createUser()

```
client.createUser(email, roles, metadata)
{
}
```

### client.updateUser()

```
client.updateUser(email, roles, metadata)
{
}
```


### client.disableUser(email) // cannot login/reset password

### client.deleteUser(email)

### client.updateUser(email, [roles], [metadata])





Server
======


```

git clone concorda
cd concorda

export DB_PG_HOST=...
export DB_PG_PORT=...
export DB_PG_NAME=...
export DB_PG_USERNAME=...
export DB_PG_PASSWORD=...

export AUTH_COOKIE_SECRET=abcd123
export ADMIN_ROLE=admin

./scripts/createUser.sh admin@example.com admin

npm start
```