# E-Commerce-Mobile-App
The sample project provides a shopping demo app built for android phones with Android and SQL Lite Database
## Features
### The App screens are as follows:
* Register Screen 
* Login Screen
* Product list screen
* Product details screen
* Product search Screen
* One-tap sign-in and sign-out
## App Generation
* download the .rar file and Extract it and then open it in android Studio
### Compilation environment
* Android Studio: 4.1
* Android SDK: 19
* Gradle: 6.3
## App Screens 
### Register Sceen
![Alt Text](https://media.giphy.com/media/SHEN9wj3Rnmri8mNB4/giphy.gif)
#### where in this Screen the App is validating the user's inputs through checking in the database for several things :- 
* checking if the user is already registered 
```java
public boolean checkUsernameAvailability(String username) {
            ecommerceDatabase = getReadableDatabase();
            String Query = "Select * From Customer Where Username = ?";
            Cursor cursor = ecommerceDatabase.rawQuery(Query, new String[] {username});
            if(cursor.getCount() <= 0){
                cursor.close();
                return false;
            }
            cursor.close();
            return true;
    }
    
    public boolean checkEmailAvailability(String email) {
        ecommerceDatabase = getReadableDatabase();
        String Query = "Select * from Customer where Email = ?";
        Cursor cursor = ecommerceDatabase.rawQuery(Query, new String[] {email});
        if(cursor.getCount() <= 0){
            cursor.close();
            return false;
        }
        cursor.close();
        return true;
    }
```
* email is in correct format using this Regex String 
```java
private static final String regex = "^[\\w-_\\.+]*[\\w-_\\.]\\@([\\w]+\\.)+[\\w]+[\\w]$";

    private boolean validateEmail(String email) {
        return email.matches(regex);
    }

    public void parseString(String email) throws InvalidEmailException {
        if (!validateEmail(email))
            throw new InvalidEmailException();

        address = email;
    }
 ```
## if all the fields are correct then the user will be added succesfully  
## Login Screen
#### where in this Screen the App is validating the user's inputs through checking in the database if the username already exists or not 
![Alt Text](https://media.giphy.com/media/q8Lj6jc2QFc9eirurp/giphy.gif)
## Main Screen 
#### where in this Screen contains all the Games with the available quantities , and when the user press on it , if the it has quantities it is successfuly added to the user's cart  
![Alt Text](https://media.giphy.com/media/xDuoxX5FN4pU116AlA/giphy.gif)
## Shopping Cart Screen
#### where in this Screen it contains all the Games the user has added to his/her cart with the number of quantities and he can increase or decrease the quantities 
![Alt Text](https://media.giphy.com/media/0Ncoo6Ghec8782Ma9Q/giphy.gif)
## Main Screen after pressing Purchase 
### the quantities of the items the user purchased is being decreased here 
![Alt Text](https://media.giphy.com/media/0Ncoo6Ghec8782Ma9Q/giphy.gif)



