# how-to-loopback-with-mongodb

## 1. Install LoopBack CLI via NPM
<pre>
<code>
$ npm install -g loopback-cli
</code>
</pre>

## 2.Creating Application
<pre>
<code>
$ lb
? What's the name of your application? loopback-books
? Enter name of the directory to contain the project: loopback-books
   create loopback-books/
     info change the working directory to loopback-books

? Which version of LoopBack would you like to use? 3.x (Active Long Term Support)
? What kind of application do you have in mind? api-server (A LoopBack API server with local User auth)
Generating .yo-rc.json

I'm all done. Running npm install for you to install the required dependencies. If this fails, try running the command yourself.

Next steps:

  Change directory to your app
    $ cd loopback-books

  Create a model in your app
    $ lb model

  Run the app
    $ node .

The API Connect team at IBM happily continues to develop,
support and maintain LoopBack, which is at the core of
API Connect. When your APIs need robust management and
security options, please check out http://ibm.biz/tryAPIC

npm WARN deprecated swagger-ui@2.2.10: No longer maintained, please upgrade to swagger-ui@3.
npm WARN deprecated circular-json@0.3.3: CircularJSON is in maintenance only, flatted is its successor.
npm notice created a lockfile as package-lock.json. You should commit this file.
added 434 packages from 460 contributors and audited 2367 packages in 30.397s
found 0 vulnerabilities
</code>
</pre>

Run the application using the following command:
<pre>
<code>
$ node .
(node:519) DeprecationWarning: current URL string parser is deprecated, and will be removed in a future version. To use the new parser, pass option { useNewUrlParser: true } to MongoClient.connect.
Web server listening at: http://localhost:3000
Browse your REST API at http://localhost:3000/explorer
</code>
</pre>

## 3.Connecting MongoDB
<pre>
<code>
$ npm install --save loopback-connector-mongodb
? Enter the datasource name: mongoDS
? Select the connector for mongoDS: MongoDB (supported by StrongLoop)
? Connection String url to override other settings (eg: mongodb://username:password@hostname:port/database): 
? host: localhost
? port: 27017
? user: root
? password: [hidden]
? database: project-books
</code>
</pre>

Modify datasources.json
<pre>
<code>
{
  "db": {
    "host": "localhost",
    "port": 27017,
    "url": "", 
    "database": "project-books",
    "password": "*****",
    "name": "db",
    "user": "root",
    "connector": "mongodb"
  }
}
</code>
</pre>

## 4. Create Data Models
<pre>
<code>
$ lb model
? Enter the model name: Book
? Select the datasource to attach Book to: db (mongodb)
? Select model's base class PersistedModel
? Expose Book via the REST API? Yes
? Custom plural form (used to build REST URL): 
? Common model or server only? common
Let's add some Book properties now.

Enter an empty property name when done.
? Property name: isbn
? Property type: number
? Required? No
? Default value[leave blank for none]: 

Let's add another Book property.
Enter an empty property name when done.
? Property name: title
? Property type: string
? Required? Yes
? Default value[leave blank for none]: 

Let's add another Book property.
Enter an empty property name when done.
? Property name: author
? Property type: string
? Required? No
? Default value[leave blank for none]: 

Let's add another Book property.
Enter an empty property name when done.
? Property name: userid
? Property type: number
? Required? Yes
? Default value[leave blank for none]: 

Let's add another Book property.
Enter an empty property name when done.
? Property name: genre
? Property type: string
? Required? No
? Default value[leave blank for none]: 

Let's add another Book property.
Enter an empty property name when done.
? Property name: 
</code>
</pre>
