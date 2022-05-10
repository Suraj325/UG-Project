# MERNSHOP

## Server:

Directory: [server/](/server/)

## Client

Directory: [client/](/client/)

## Preparing For Deployment

Environment configurations:

```env
JWT_SECRET = 'secret'
MONGO_URI = 'mongodb_uri'
NODE_ENV = 'development'
PAYPAL_CLIENT_ID = 'paypal_id'
PORT = 5000
```

Change the NODE_ENV = 'development' to NODE_ENV = 'production' to run in production mode.

Create a build directory in the client directory,

    $ npm run build

Esure you have the code, in your `app.js` in the server directory:

```js
if (process.env.NODE_ENV === "production") {
  app.use(express.static(path.join(__dirname, "/client/build")));

  app.get("*", (req, res) =>
    res.sendFile(path.resolve(__dirname, "client", "build", "index.html"))
  );
} else {
  app.get("/", (req, res) => {
    res.send("API is running....");
  });
}
```

Run the server in production mode(simulator):

    $ npm start

## Bugs

1. File Uploads

## Working Updates

1. Re-write on Typescript
