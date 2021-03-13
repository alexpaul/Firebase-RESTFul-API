# Firebase-RESTFul-API

## Objective 

* Create a RESTFul API via Firebase. 
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

## There are two ways to add authentication to a RESTFul API

[Authenticate REST Requests](https://firebase.google.com/docs/database/rest/auth#google_oauth2_access_tokens)

1. Google OAuth2 access tokens. 
2. Firebase ID Tokens - similar to those client apps use once the user has successfully logged in using their email and password. This can also be done using the following REST email/password endpoint.   
   POST `https://identitytoolkit.googleapis.com/v1/accounts:signInWithPassword?key=AIzaSyDVkcyUVSZmPDcXR_fC3UYZJRdn7xY6TTs`   
   
   Body payload to POST in exchange for `idToken` response 
  ```json 
  {
      "email": "", 
      "password": "",
      "returnSecureToken": true
  }
  ```

  Response 

  You will get back the `idToken` etc....


## Resources 

1. [Firebase Auth REST API](https://firebase.google.com/docs/reference/rest/auth)
2. [StackOverflow - Create Auth Token](https://stackoverflow.com/questions/38661839/using-postman-to-access-firebase-rest-api)
3. [Video - Creating routes in Firebase Realtime Database](https://www.youtube.com/watch?v=rB1qGYYaoPc)
4. [Vidoe - Creating Service Account Auth Token](https://www.youtube.com/watch?v=ScsID2yPB8k)
5. [Video - Rules](https://www.youtube.com/watch?v=dx_gkSb-Ch0)
6. [Video - Creating custom tokesn - python](https://www.youtube.com/watch?v=FPIJwrr5x4g)
