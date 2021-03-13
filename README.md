# Firebase-RESTFul-API


```javascript
{
  "rules": {
    ".read": "auth.uid.matches(/^MRBWgooKJUYE2HS2JeX3VlY99us2/)",
    ".write": false  // 2021-4-11
  }
}
```

```javascript 
{
  "rules": {
    ".read": "auth.token.endsWith('MRBWgooKJUYE2HS2JeX3VlY99us2')",
    ".write":false 
  }
}
```

```javascript 
{
  "rules": {
    ".read": "auth.token.email.endsWith('@gmail.com')",
    ".write":false 
  }
}
```


## Resources 

1. [Create Auth Token](https://stackoverflow.com/questions/38661839/using-postman-to-access-firebase-rest-api)
2. [Creating routes in Firebase Realtime Database](https://www.youtube.com/watch?v=rB1qGYYaoPc)
