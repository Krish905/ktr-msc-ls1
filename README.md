# Test KTR Epitech

## Intro 

This project is a business card manager. It is aimed at young entrepreneurs who are looking for a digital
solution to store the information from their multiple business cards acquired during their various networking
evenings.

## Step 1 

1. Create your github account if you don’t have one yet
2. Create a private repository named ktr-msc-ls1
3. Give the rights to this deposit to the login you were given when you made contact

## Step 2 Account creation

1.To create an user, from the front-end I created a component "Register.js" that can take the informations of the user (name, company, mail,...) with inputs calling the method "setcred".
2.Then, we click on the button "create account" to call the POST request that will send the informations taken to the back-end.
3.Finally, in the back-end, we verify if the username sent is already in the database. If not, it will create a new user and add this username to the database. The data will be persistent.

To access this database, I created a file env where the url of the database is located.

## Step 3 Log in

1. Thanks to the component "Login.js", the username and password of the user are taken and sent to the back-end with the POST request.
2. Then, in the back-end, the password will be hashed and it will be compared to the hashed password of the user located in the database

+ BONUS 2 - MULTI-USERS 
Create one profile per user.
We can create many users that will be saved in the database and the username must be only one.

+ BONUS 3 - USER SWITCH 
This one allow the users to log out.

**Implementation:**
-> We can create as multiple profile as we want and we use the 'name' field as unique field to 
identify a user: the users are stored into a 'users' collection in mongodb (database).

-We can login / logout via an authentication process which encrypt our password into the database (with bcrypt and salt is used to prevent attacks) from where the back-end send back to the client a JWT (JSON Web Token).

-The JWT allows the user to maintain session, which can be destroyed by logout in the header top corner right.

To go further :
Implement some protected endpoint in the back-end which authenticate the access_token, which i didn't implemented yet.


## Step 4

Create a “library” interface that allows your user to add new business cards to your application with the
following fields:
• Name (optional short text field)
• Company name (optional short text field)
• Email address (mandatory email field)
• Telephone number (optional phone field)

Allow two users of your application on two different devices to automatically exchange their profile infor-
mation and add it to their business card “library”.

**Implementation:**
-> We can add a business card in the '/add' endpoint with the same fields as a profile, 
but we are adding our username into that card to recognize that this card belong to us (logged user).
I didn't implement the allowance of users to share their business cards because of a lack of time.
In order to do this, i would implement some "joints" while retrieving data from 'cards' collection.

