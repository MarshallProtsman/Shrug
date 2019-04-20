# Group-5_Project-1

# Project Title: 
Shrug (date night planning app)

# Team Members: 
Chaney Durham, Marshall Prostman, John Robertson

# Project Description: 
Web Application designed to facilitate the planning of dates.
Users will be guided through a date planner sequentially.
The initial user location is 

# APIs:
ipdata.io - used to obtain the users initial location (city)
ticketmaster - used to search for events based on the location (city) provided by ipdata.io 
yelp - used to populate a list of restaurants near the users event selection (latitude and longitude coordinates)

# Libraries
materialize.css - basic responsive layout and some transition effects
hover.css - dedicated css library for hover effects
jquery - dom manipulation and view management 
fontawesome - icon library
googlefonts - font library

# Future Versioning - Enhancements and Features
- User account and login validation via firebase (to store history, favorite restaurants, leave reviews, etc.)
- Multiple search keywords for events (most of this is coded already and commented out)
- Expand city via another API and use autocomplete for the field input
- Advanced event and dining serach filtering
- Categories for dining options and the ability to search
- Date Picker and date-based functionality 
- In-app purchase of event tickets (or a more integrated functionaliy eliminating the need to leave the app/site)
- Google Maps integration (distance from event to restaurant is already here - we want advanced functionality like showing the map and directions)
- Advanced animations/transitions and a smoother UI (android-like) - css keyframes and/or anime.js
- Rotating background imgs (close but couldn't quite get it working)    
- Social component > can users have a swiping/dating app and then plan dates using our app as the next step?  Props to Sam for that idea

github link: https://github.com/jrobs87/group_5_project_1 
github pages link:  https://jrobs87.github.io/group_5_project_1/

====================================================================================

# Application Flow and Features
- App is a psuedo SPA, with views managed via jquery dom manipulation.
- Event listeners hide and reveal content to guide the user thru the app while updating common variables and making API calls in the background
- The App functions as follows:
    a. Ping users ip address and bounce it off of ipdata.io to get the city location
        i. user can change the city - validation is done by bouncing the input off of an array of major US cities
    b. Feed the city to the ticketmaster API and use search params to filter events in the users city
        i. Each category button refreshes the keyword 
        ii. Each category button calls the ticketmaster API with the new keyword and re-renders the event cards
        iii. Event array response from ticketmaster is stored in a global variable for access on the summary page
    c. Once the user selects an event, the location of the event (lat and long coordinates) are fed to the Yelp API
        i. This narrows down the search to super local (radius around the event)
        ii. Results are populated automatically on the view change.
        iii. Restaurant API response is stored for later use along with user selection
        iv. Restaurant selection is pushed to Firebase to use later in a favorites/popular list
    d. Summary page displays both user selections (event and restaurant)



