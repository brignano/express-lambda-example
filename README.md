# Express Lambda Example

Simple Express API with AWS Lambda deploy setup as proof of concept for students.

# Tutorial
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
```
(set AWS environment variables)

Mac/Linux:
export AWS_ACCESS_KEY_ID=AKIAIOSFODNN7EXAMPLE
export AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
setx AWS_DEFAULT_REGION us-east-1

Windows:
setx AWS_ACCESS_KEY_ID AKIAIOSFODNN7EXAMPLE
setx AWS_SECRET_ACCESS_KEY wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
setx AWS_DEFAULT_REGION us-east-1
```

### Step 5
```
$ claudia create --handler lambda.handler --deploy-proxy-api --region us-east-1
```
