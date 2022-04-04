# Spring Boot & OAuth

# What I understanding from this resource read

this process is how we build a sample app donig various things. "The services that we allow the specific user to user it " 

* ##  Types for this Samples  

1. simple : visit home page.  
2. click  : add link on the page to allow the user click on it to go to the login page .
3. logout : add logout to the user 
4. tow-providers : tow login provider when the user want to login such as (Teacher, Student)
5. custom-error : add error message for authenticated users.4

## Add Login  

1. in the home page we have link to go to the login page  
2. the user move to the secure content and fill all information 
3. the endpoint after this will be connect with the server side to save all information.

## make the home page public

 redirect before showing the page. To make the link visible, we also need to switch off the security on the home page by extending WebSecurityConfigurerAdapter  

* / since that’s the page you just made dynamic, with some of its content visible to unauthenticated users  

## Logout Boutton
    
we built by adding a button that allows the user to log out of the app 

* ### Client Side Changes

* we just need to provide a logout button and some JavaScript to call back to the server to ask for the authentication to be cancelled.

* we add /logout endpoint  requires us to POST to it and protect the user from Cross Ste Request Forgery (CSRG).

## Adding the CSRF Token in the Client 

* first we want to add js-cookie dependancy

* then you can reference it in your HTML

