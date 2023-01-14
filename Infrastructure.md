# Backend
The backend will consist of a webserver built in Rust with Rocket.rs. API requests will be POSTS and everything will be in json format.

## Storage
User data will be stored in an sqlite database and accessed through the Rocket db pool functionality. While this is not the most robust database for lots of transactions, it is sufficient for our current purposes and the abstraction of rocket db pools should make it easy to switch over to a more robust db in future releases. 

### Information to be stored
* Name
* Email Address
* age
* Gender Identity (optional)
* Emergency Contact(s) (default to campo)
* ratings
* preferences for age, gender identity, and ratings of partner

## Emergency Notification (Post-hackathon)
* VoIP?	
	* TTS information
* Email

## Route Deviation Detection (Post-hackathon)
* apple or google maps routing API to determine possible routes to destination
* if user deviates significantly from excpected pahts, send a time-sensitive push notification, If they do not respond, generate an emergency notification

## Mail
To verify that users have valid WPI email addresses, we need to store the user's email, send custom links to WPI accounts, and respond correctly to verification links in the webserver. 

# Frontend
## Pretty
A UI mockup for an iOS applicaiton will be created in uizard to demonstrate the proposed functionality and interface of the application.

## Ugly
Due to time limitations, implimenting an actual mobile app or pretty frontend with JavaScript and CSS is not feasible. Therefore, we will add a barebones html interface to the Rocket server. 

The ugly interfacde will still need some javascript to grab location data
