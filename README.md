# Express Lambda Example

Simple Express API with AWS Lambda deploy setup as proof of concept for students.

# Tutorial
https://www.freecodecamp.org/news/express-js-and-aws-lambda-a-serverless-love-story-7c77ba0eaa35/

### Step 1
```
$ cp app.js app.local.js
```

### Step 2
```
(app.js)

Replace:    app.listen(...)
With:       module.exports = app
```

*Reference: [Claudia JS](https://claudiajs.com/tutorials/serverless-express.html)*

### Step 3
```
$ claudia generate-serverless-express-proxy --express-module app
```

### Step 4
```
$ claudia create --handler lambda.handler --deploy-proxy-api --region us-east-1
```