# Authentication

* The Amplify Auth category provides an interface for authenticating a user It comes with default, built-in support for Amazon Cognito .

## Configure Auth Category (Setup AWS Congito Auth Plugin)

1. go to the project directory then execute the command (amplify add auth).
2. Enter the use default authentication and how do you want users to be able to sign in? and do you want to configure advanced settings?
3. push your change to the cloud (amplify push)
4. add this dependencies (implementation 'com.amplifyframework:aws-auth-cognito:1.35.4').
5. Add the Auth plugin before calling Amplify.configure (Amplify.addPlugin(new AWSCognitoAuthPlugin());).
6. Check the current auth session : 
    - We can now check the current auth session.
        * Amplify.Auth.fetchAuthSession();



# Sign in 

* The Auth category can be used to register a user, confirm attributes like email/phone, and sign in with optional multi-factor authentication. It is set up to use Amazon Cognito User Pools which manages the users and their properties.

## Steps to do this process 

1. Regester a user : 
    * AuthSignUpOptions options = AuthSignUpOptions.builder()
    .userAttribute(AuthUserAttributeKey.email(), "my@email.com")
    .build();
Amplify.Auth.signUp("username", "Password123", options,
    result -> Log.i("AuthQuickStart", "Result: " + result.toString()),
    error -> Log.e("AuthQuickStart", "Sign up failed", error)
);
2. Confirm the user : 
    * Amplify.Auth.confirmSignUp(  
    "username",  
    "the code you received via email",  
    result -> Log.i("AuthQuickstart", result.isSignUpComplete() ? "Confirm signUp succeeded" : "Confirm sign up not complete"),
    error -> Log.e("AuthQuickstart", error.toString())  
    );
    *   You will know the sign up flow is complete if you see the following in your console window (Confirm signUp succeeded)
3. Sign in a User : 
    * Implement a UI to get the username and password from the user
        - Amplify.Auth.signIn();
        
4. push your code on cloud.

___


