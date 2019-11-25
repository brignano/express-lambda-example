# Express Lambda Example

Simple Express API with AWS Lambda deploy setup as proof of concept for students.

# Reproduce this Setup
https://www.freecodecamp.org/news/express-js-and-aws-lambda-a-serverless-love-story-7c77ba0eaa35/

*Reference: [Claudia JS](https://claudiajs.com/tutorials/serverless-express.html)*

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

### Step 3
```
$ claudia generate-serverless-express-proxy --express-module app
```

### Step 4
**(4.1)** [Install AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html)

**(4.2)** [Configure AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html)

### Step 5
```
$ claudia create --handler lambda.handler --deploy-proxy-api --region us-east-1
```

# Local Setup
**note:** *this will install all the dependencies as per the **package.json***
'''
$ npm install
'''

# Local Development
**note:** *this will run the command* `node app.local.js` *as per **start** script definition in **package.json***
```
$ npm start

    > express-lambda-example@1.0.0 start /home/anthony/projects/express-lambda-example
    > node app.local.js

    Example app listening on port 3000!
```

# Re-deploy (Update) Application
**note:** *this will run the command* `claudia update` *as per **deploy** script definition in **package.json***
```
$ npm run deploy
```
