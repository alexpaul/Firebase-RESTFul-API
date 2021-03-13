# Firebase-RESTFul-API

## 1, Objective 

* Create a RESTFul API using Firebase. 
* Implement security rules to allow access only with a valid token.  
  ```json
  {
    "rules": {
      ".read": "auth.token != null",
      ".write": "auth.token != null" 
    }
  }
  ```
* Be able to access endpoint(s) from e.g Postman. 

## 2. There are two ways to add authentication to a RESTFul API

[Authenticate REST Requests](https://firebase.google.com/docs/database/rest/auth#google_oauth2_access_tokens)

1. Google OAuth2 access tokens. 
2. Firebase ID Tokens - similar to those client apps use once the user has successfully logged in using their email and password. This can also be done using the following REST email/password endpoint.   

   #### Using Firebase ID Tokens
   
   POST `https://identitytoolkit.googleapis.com/v1/accounts:signInWithPassword?key={API key goes here}`   
   
   The API key is located in your Firebase console under settings. 
   
   **Body** payload to POST to Firebase in exchange for `idToken` response 
  ```json 
  {
      "email": "", 
      "password": "",
      "returnSecureToken": true
  }
  ```

  **Response** back from request

  You will get back the `idToken` etc....
  ```json 
  {
    "kind": "",
    "localId": "",
    "email": "",
    "displayName": "",
    "idToken": "",
    "registered": true,
    "refreshToken": "",
    "expiresIn": ""
  }
  ```
  
## 3. Using the `idToken` to make a CRUD request to Firebase 

> When the `idToken` expires, redo step 2 above to generate an new `idToken`. 

Making a POST request to `/books` `https://{Project name Firebase URL}/books.json?auth={idToken}`

#### Body 

```json 
{
  "title": "The Pragmatic Programmer"
}
```

Making a GET request to `/books` `https://{Project name Firebase URL}/books.json?auth={idToken}`

#### JSON Payload Response 

```json 
{
    "-MVfMNQvfOAkIvZJmjji": {
        "title": "The Pragmatic Programmer"
    },
    "-MVfMUGmx3P4ngTxaaet": {
        "title": "Unbroken"
    }
}
```


## Resources 

1. [Firebase Auth REST API](https://firebase.google.com/docs/reference/rest/auth)
2. [StackOverflow - Create Auth Token](https://stackoverflow.com/questions/38661839/using-postman-to-access-firebase-rest-api)
3. [Video - Creating routes in Firebase Realtime Database](https://www.youtube.com/watch?v=rB1qGYYaoPc)
5. [Video - Rules](https://www.youtube.com/watch?v=dx_gkSb-Ch0)
6. [Video - Creating custom tokesn - python](https://www.youtube.com/watch?v=FPIJwrr5x4g)
