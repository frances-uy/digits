<img src="doc/Screenshot 2023-11-06 at 8.34.02 PM.png" style="box-shadow: 10px 10px 10px gray; width:700px;">

Digits is an application that allows users to: 

  * Register an account
  * Create and manage a set of contacts
  * Add a set of timestamped notes regarding their interactions with each contact.



## Installation

First, [install Meteor](https://www.meteor.com/install).

Second, download a copy of [Digits](https://github.com/frances-uy/digits). Note that Digits is a private repo and so you will need to request permission from the author to gain access to the repo.

Third, cd into the app directory install the required libraries with:

```
$ meteor npm install
```
Once the libraries are installed, you can run the application by invoking:

```
$ meteor npm run start
```
The first time you run the app, it will create some default users and data. Here is the output:

```
meteor npm run start

> meteor-application-template-react@ start /Users/michelleuy/Desktop/github/digits/app
> meteor --no-release-check --exclude-archs web.browser.legacy,web.cordova --settings ../config/settings.development.json

[[[[[ ~/Desktop/github/digits/app ]]]]]       

=> Started proxy.                             
=> Started HMR server.                        
=> Started MongoDB.                           
W20231106-20:57:09.211(-10)? (STDERR) Unsupported "tracker" option passed to SimpleSchema constructor
W20231106-20:57:09.217(-10)? (STDERR) Unsupported "tracker" option passed to SimpleSchema constructor
I20231106-20:57:09.217(-10)? Ignoring duplicate publish named 'ContactsCollection.publication.user'
I20231106-20:57:09.217(-10)? Ignoring duplicate publish named 'ContactsCollection.publication.admin'
=> Started your app.

=> App running at: http://localhost:3000/

```
__Note regarding bcrypt warning__. You will also get the following message when you run this application:

```
Note: you are using a pure-JavaScript implementation of bcrypt.
While this implementation will work correctly, it is known to be
approximately three times slower than the native implementation.
In order to use the native implementation instead, run

  meteor npm install --save bcrypt

in the root directory of your application
```

On some operating systems (particularly Windows), installing bcrypt is much more difficult than implied by the above message. Bcrypt is only used in Meteor for password checking, so the performance implications are negligible until your site has very high traffic. You can safely ignore this warning without any problems during initial stages of development.

If all goes well, the template application will appear at [http://localhost:3000](http://localhost:3000). You can login using the credentials in [settings.development.json](https://github.com/ics-software-engineering/meteor-application-template-react/blob/master/config/settings.development.json), or else register a new account.

Lastly, you can run ESLint over the code in the imports/ directory with:

```
meteor npm run lint
```

## User Interface Walkthrough

### Landing Page
When you first bring up the application, you will see the landing page that provides a brief introduction to the capabilities of Digits:

<img src="doc/Screenshot 2023-11-06 at 8.34.02 PM.png" style="box-shadow: 10px 10px 10px gray; width:700px;">

### Register
If you do not yet have an account on the system, you can register by clicking on “Login”, then “Sign Up”:

<img src="doc/Screenshot 2023-11-06 at 8.34.48 PM.png" style="box-shadow: 10px 10px 10px gray; width:700px;">

### Sign in
Click on the Login link, then click on the Signin link to bring up the Sign In page which allows you to login:

<img src="doc/Screenshot 2023-11-06 at 8.34.34 PM.png" style="box-shadow: 10px 10px 10px gray; width:700px;">

### User home page
After successfully logging in, the system takes you to your home page. It is just like the landing page, but the NavBar contains links to list contact and add new contacts:

<img src="doc/Screenshot 2023-11-06 at 8.35.20 PM.png" style="box-shadow: 10px 10px 10px gray; width:700px;">

### List Contacts
Clicking on the List Contacts link brings up a page that lists all of the contacts associated with the logged in user:

<img src="doc/Screenshot 2023-11-06 at 8.36.28 PM.png" style="box-shadow: 10px 10px 10px gray; width:700px;">

This page also allows the user to add timestamped “notes” detailing interactions they’ve had with the Contact. _For example:_

<img src="doc/Screenshot 2023-11-06 at 8.36.53 PM.png" style="box-shadow: 10px 10px 10px gray; width:700px;">

### Edit Contacts
From the List Contacts page, the user can click the “Edit” link associated with any Contact to bring up a page that allows that Contact information to be edited:

<img src="doc/Screenshot 2023-11-06 at 8.37.09 PM.png" style="box-shadow: 10px 10px 10px gray; width:700px;">

### Admin mode
It is possible to designate one or more users as “Admins” through the settings file. When a user has the Admin role, they get access to a special NavBar link that retrieves a page listing all Contacts associated with all users:

<img src="doc/Screenshot 2023-11-06 at 8.37.51 PM.png" style="box-shadow: 10px 10px 10px gray; width:700px;">
