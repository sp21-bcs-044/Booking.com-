 
# Introduction: 

We have developed a user-friendly app called Booking.com that simplifies the process of making hotel room reservations. In traditional methods, such as making phone calls, it's challenging to gather comprehensive information about hotels, including reviews, pictures, and detailed facilities. Our app provides a seamless experience where users can check room availability in popular hotels, access detailed information, and make reservations effectively. Additionally, the app offers reservation management and a secure payment gateway for users' convenience. 


# App Title: Booking.com 

  
# Description: 

Booking.com offers an intuitive way to reserve hotel rooms in advance. Users can simply enter their desired destination, dates, room preferences, and the number of adults and children on the home screen to explore available hotels. They can view essential details such as pricing, pictures, reviews, payment methods, addresses, and compare different options. Reservations can be easily made by selecting a hotel and providing necessary personal information. Users can access their bookings through the booking screen. 

  
# Installation: 

To set up the project, install Yarn by typing "yarn" in the terminal, which will automatically add the required node modules. Additionally, the following dependencies need to be added: 

  
"@react-native-async-storage/async-storage": "1.17.11" 
"@react-navigation/bottom-tabs": "^6.5.7" 
"@react-navigation/native": "^6.1.6" 
"@react-navigation/native-stack": "^6.9.12" 
"@reduxjs/toolkit": "^1.9.3" 
"expo": "~48.0.6" 
"expo-status-bar": "~1.4.4" 
"firebase": "^9.17.2" 
"react": "18.2.0" 
"react-native": "0.71.3" 
"react-native-date-ranges": "^2.5.0" 
"react-native-maps": "^1.4.0" 
"react-native-modals": "^0.22.3" 
"react-native-safe-area-context": "4.5.0" 
"react-native-screens": "~3.20.0" 
"react-redux": "^8.0.5" 

If any of these dependencies are missing, they can be added by running "yarn add (dependency)" in the terminal. 
 
 
# Screens: 

The app consists of following screens: 

Login Screen 
Sign Up Screen 
Rooms Screen 
Confirmation Screen
User Screen 
Map Screen 
Search Screen 
Places Screen 
Property Info Screen 
Home Screen 
Profile Screen 
Booking Screen 
Saved Screen  

 
Navigation between the last four screens is facilitated by the bottom tab navigator.  

  

## Login Screen: 

This is the initial screen that appears upon launching the app. Registered users can log in using their email and password, which they provided during registration. Firebase authentication is implemented, allowing only registered users with matching credentials from the Firebase database to log in. Users can switch to the signup screen if they are not registered. 

 

## Sign Up Screen: 

Users can register by providing their email, password, and phone number. Upon clicking the register button, the entered data is stored in the Firebase database, enabling only registered users to sign in. 

 
## Home Screen: 

The Home Screen serves as the main interface upon successful login. It comprises three main parts: 

  

#### Search Your Destination: 
Users can input the desired city where they want to make a reservation. Upon pressing the search icon, the Search Screen appears, allowing users to enter the city name. 

#### Dates: 
Users can select the booking duration using a date picker that provides an interactive interface. They can choose the start and end dates and submit their selection. 

#### Room * Adults * Children: 
This section utilizes a React Native modal view, which slides up from the bottom, allowing users to select the number of rooms, adults, and children for their reservation. 


## Search Screen: 
The search screen is used to search for the desired city the user wants to choose. It appears when the user clicks on the "Select your destination" text input on the home screen. The user inputs the city name and can select from the drop-down options before returning to the home screen. 



## Places Screen: 

This screen displays details of popular hotels in the selected city. It includes information such as price, address, room availability, reviews, payment processes, and capacity. The screen features a top bar navigator with options for sorting (by cost, low to high or vice versa), filtering the search, and viewing the hotel's location on a map. The hotel details are installed in the PropertyCard.js file and imported into this screen. 

## Property Info Screen: 

This screen provides comprehensive information about a specific property. It includes customizable headers, image displays, price details, check-in/out dates, room and guest information, amenities, and a button to check availability. The screen utilizes navigation hooks and styling properties for layout and design. Users can access this screen by selecting a hotel on the Places Screen. 


## Rooms Screen: 

The Room Screen displays available rooms for booking. Users can select rooms, view their details, and make reservations. Selected rooms are highlighted, and a confirmation button appears to proceed with the reservation. 
  

## UserScreen: 

This screen collects user information, including first name, last name, phone number, and email. Users are prompted to provide this information when selecting a room for reservation on the Room Screen. 

## Confirmation Screen: 

The Confirmation Screen is the final step in the reservation process. It displays a confirmation of the reservation, showing the room number, total cost, reviews, and check-in/check-out dates. 

## Map Screen: 
 This file, MapScreen.js, is a React Native component that displays a map using the react-native-maps library. It retrieves the coordinates from the search results and renders markers on the map for each property. The map is initialized with a reference and fitted to display all the markers. 

## Booking Screen:  
This screen displays the details of a booking made by a user. It serves as a summary or confirmation page where users can review the information related to their booking. 
 

## Saved Screen: 

The Saved screen displays details of properties that users have saved for future use. Please note that this screen is still a work in progress and may not be fully completed at this time. 

 
## Profile Screen: 
 
The Profile screen showcases the user's profile information. Kindly be aware that this screen is also under development and may not be fully finished yet. 


# Components: 

Five components have been created and used in different screens: 

## Header: 
The header contains the Booking.com logo and four options for making bookings: Stays (hotel reservations), Flight (flight bookings), Car (car rentals), and Taxi (taxi bookings). This header is utilized in the Home Screen at the topmost view area. 

## Search Result: 
This component displays dropdown options when users enter the starting letters of a city in the search screen. It receives an array declared in the search screen and utilizes a flat list to display three items from the array: Name, Property, and a short description. 

## Property Card: 
This component presents details of popular hotels in the desired city. It is imported into the Places Screen and used to display information about each hotel. 

## Amenities: 
This component showcases the facilities provided by a hotel. The facilities are stored in an array containing IDs and facility names. The Amenities component is imported into the Property Info Screen and Room Screen. 

## Normalization: 
This component is used to normalize pixel sizes based on the screen width of the device. It ensures consistent visual proportions across different devices with varying screen sizes and pixel densities. The Normalization component is imported into the PropertyInfo Screen to maintain a visually harmonious design. 

  
# Firebase.js File: 

FirebaseConfig.js initializes the Firebase SDK and sets up the configuration for the Firebase project. It imports the necessary functions from the Firebase libraries for authentication and Firestore database. The firebase Config object contains the project's specific configuration settings, such as API key, authentication domain, project ID, and more. It initializes the Firebase app using the configuration. The auth variable provides access to the Firebase authentication functionality, while the db variable gives access to the Firestore database. Finally, it exports the auth and db variables to be used in other parts of the application for authentication and database operations, respectively. 

# Stack Navigator File: 
This file, StackNavigator.js, is responsible for defining the navigation structure and screens of the application using the React Navigation library. It creates a bottom tab navigator and a native stack navigator to manage the different screens. It also imports and assigns the appropriate icons for each tab. The file organizes the screens into a navigation container, and each screen is associated with a specific route name. Finally, it exports the Stack Navigator component to be used in the main application file. 


# Reference websites: 

Creating the project: https://reactnative.dev/ 
 
Navigation - https://reactnavigation.org/ 

Icons: https://icons.expo.fyi/ 

React Native modals https://www.npmjs.com/package/react-native-modal 

React Native Maps: https://www.npmjs.com/package/react-native-maps 

