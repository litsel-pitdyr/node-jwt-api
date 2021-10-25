# Node simple API with Mongodb

## Description
API made with node and mongodb, using jwt authentication.
First of all, you need to have node, npm and mondodb installed on your local machine to continue.

## Configuring project
Let's go ;-)

### Downloading and install node and npm
To download and install go to [nodejs docs](https://nodejs.org/en/download/`) and follow the stepps.
This project was made using node 14.17.0, please check the node version in case of incompatibility.
### Downloading and install mondogb
To download and install mongodb go to [MongoDB Download](https://www.mongodb.com/try/download/community`) docs and follow the stepps.

### Downloading the project
Open your terminal in the some folder for project and type:
~~~bash
git clone https://github.com/jimmyginga/node-jwt-api.git .
~~~

### Installing dependences
To install the dependencies execute in the project folder terminal the following command:
~~~bash
npm install
~~~

if its done, you can run the server using:
~~~bash
npm start
~~~
the server will run on 3003 port.

## Routes test 
The API base URL for locall machine is http://localhost:3003/api

#### User endpoints

*  List user [/user] - GET
``http://localhost:3003/api/user``

return a array with users registed
___

* Create user [/user/register] - POST
``http://localhost:3003/api/user``
The resquest data required are email and password.
eg.: 
~~~js
{
	"name":"Jimi Nginga",
	"mail": "jimi@gmail.com",
	"password":"123456"
}
~~~
return a user created
___
* List a single user by ID [/user/:id] - GET
    * The resquest data required are email and password.
id is the user id inside database
``http://localhost:3003/api/user/:id``
e.g: ``http://localhost:3003/api/user/617434caac776ee3921ef701``

return the user which the id belongs to
___
* Update user by ID [/user/:id] - PUT
id is the user id inside database
``http://localhost:3003/api/user/:id``
e.g: ``http://localhost:3003/api/user/617434caac776ee3921ef701``

return the user updated
___
* Delete user by ID [/user/:id] - DELETE
id is the user id inside database
``http://localhost:3003/api/user/:id``
e.g: ``http://localhost:3003/api/user/617434caac776ee3921ef701``

return a success mesage
___
* User **Login** [user/login] - POST
The resquest data required are mail and password.
eg.: 
~~~js
{
	"mail":"jimi@gmail.com",
	"password":"123456"
}
~~~
return a user data like name, email and session token


#### Posts endpoints

*  List post [/posts] - GET
``http://localhost:3003/api/posts``

return a array with posts registed
___

**Note: the routes belows needs a user token to works**
* Create post [/posts/] - POST
``http://localhost:3003/api/posts``
The resquest data required are email and password.
**Require a valid user token, meke user login get it**
eg.: 
~~~js
{
    "title":"Post title",
    "text": "Post content comes here!"
}
~~~
return a created post
___
*  List a single post by ID [/post/:postID] - GET
    * The resquest data required are email and password.
id is the posts id inside database
``http://localhost:3003/api/posts/:postid``
e.g: ``http://localhost:3003/api/posts/617434caac776ee3921ef701``
**Require a valid user token, meke user login get it**
return the post which the id belongs to
___
* Update posts by ID [/posts/:id] - PUT
id is the post id inside database
``http://localhost:3003/api/posts/:id``
e.g: ``http://localhost:3003/api/posts/617434caac776ee3921ef701``
**Require a valid user token, meke user login get it**
 
 return the post updated
___
* Delete post by ID [/posts/:id] - DELETE
id is the post id inside database
``http://localhost:3003/api/posts/:id``
e.g: ``http://localhost:3003/api/posts/617434caac776ee3921ef701``
**Require a valid user token, meke user login get it**

return a ssuccess mesage

