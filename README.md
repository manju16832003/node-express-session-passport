### Node+Express+Passport: Session, Authentication, Authorization with passport

Illustration of Node app session management with passport

# How to run

`> npm install`

`> node index.js`

Run with nodemon?  do install nodemon globally `npm install nodemon -g`

`nodemon index.js`

Without JWT encoding

<img src="https://github.com/manju16832003/node-express-session-passport/blob/master/images/postman.png?raw=true"/>

With JWT encoding
<img src="https://github.com/manju16832003/node-express-session-passport/blob/master/images/postman-jwt.png?raw=true"/>

### Session

*Browsers will automatically save/send the session id and send it in each request to the server; however, cURL doesn’t automatically save our session ID*

```
    app.use(session({
        name: 'manju.cookie', // optional; if not provided, cookie name would be connect.sid
        genid: (req) => {
            console.log('Session middleware', req.sessionID)
            return uuid() // use UUID's for session id
        },
        secret: 'nomnomnom',
        resave: false,
        saveUninitialized: true
    }))
```

<img src="https://github.com/manju16832003/node-express-session-passport/blob/master/images/session.png?raw=true"/>

## Further improvements

- Use Session to authenticate and persist the session in either Cookie or Session storage
- Use redis as a session storage

https://scotch.io/tutorials/easy-node-authentication-setup-and-local

https://codeburst.io/node-js-by-example-part-3-31a29f5d7e9c
