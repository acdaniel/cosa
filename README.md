# Cosa

Simplified object modeling for MongoDB

## Installation

Use your favorite package manager to add cosa to your project.

    $ yarn add cosa

## Usage

First define a model:

``` javascript
const { Model } = require('cosa');

const UserModel = Model.define({
  name: 'UserModel',
  collection: 'users',
  properties: {
    name: { type: 'string', required: true },
    email: { type: 'string', required: true, email: true }
  }
})
```

Use the model to add users to the database:

```javascript
const newUser = UserModel.create({ 
  name: 'John Smith', 
  email: 'jsmith@example.com' 
})
newUser.save()
```

Fetch all the users in the database:

```javascript
UserModel
  .find({}, { array: true })
  .then((users) => {
    // loop over the array of users and do something
  })
```

## Reference

- [Cosa API Documentation](API.md)
- [MongoDB API Documentation](http://mongodb.github.io/node-mongodb-native/3.0/api/)