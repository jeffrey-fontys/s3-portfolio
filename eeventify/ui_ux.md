# UI/UX Design Eeventify

For the final part of our group assignment, we had to build a front end for Eeventify that would be able to connect with the back end that we had developed earlier. In order to make sure that it is user-friendly, we have put some effort into making good UI and UX designs for our front end.

## UI design

Below you can see some sketches for the front end of the application. They show the basic structure of the four pages that are going to incorporate all the functionality that we have agreed upon with the product owner. Functionality such as: log in, event overview with filtering, event details, event creation, and an overview map. We tried to make these designs as intuitive and logically structured as possible, with emphasis on a good overview and complete information. 

![Photo of UI sketches for Eeventify front end.](/images/eeventify_ui_sketch.jpeg)  
*UI sketches for Eeventify front end.*

![Screenshot of final design for event feed page of Eeventify.](/images/eeventify_overview.png)  
*Final design for event feed page of Eeventify.*

## UX design

User experience is determined by many factors, such as: the presence of useful features, the customer attention span, aesthetics, accessibility, and value for the user. We feel that our application definitely provides useful features and therefore also value for the user, and aesthetically it is also not too bad to look at.

### Delete confirmation

An example of making sure the user has a good experience can be found in the process of deleting an event. If the logged in user is the owner of an event, a button will appear on the event detail page which allows the user to delete the event. Initially, the event would immediately be deleted when the user pressed this button, but we felt that an action with destructive consequences like these should require extra confirmation. This because a user could accidentally press the button, and then their entire event would be deleted while this wasn't their intent. So we implemented a confirmation modal, to verify if deleting the event is really the user's intent.

![Screenshot of delete confirmation modal for Eeventify.](/images/eeventify_delete_modal.png)  
*Delete confirmation modal for Eeventify.*

### Response times

Response times are also a very important part of the user experience. In [this article from the Nielsen Norman Group](https://www.nngroup.com/articles/website-response-times/) about website response times, it is said that users will wait no longer than 10 seconds for a website to load before they give up and leave. Response times of 1 second or less are preferred, because it keeps the user's flow of thought seamless. We measured the main page and found a response time of about 0.9 seconds. Most of the other pages loaded in a similar amount of time, with the pages containing a map taking the longest, between 1 and 2 seconds. These times seem very reasonable and as such we are pretty satisfied with our website's response times.

![Screenshot of response time Eeventify main page.](/images/eeventify_response1.png)  
*Response time Eeventify main page.*

### Map overview

The map view is also a very important part of the user experience for us, because the application is all about finding events that match your interests and that are close to you. On the map overview page, it is very easy to find events that are close to you, as they are indicated by markers on the map. These markers contain the title of the event, a short description, and a button taking you to the event's detail page. We believe this is a very useful feature which adds a lot to a good user experience.

![Screenshot of map overview page.](/images/eeventify_map.png)  
*Map overview page.*

## Sources

- [IT Business Mind: 9 User Experience Factors You Need to Consider](https://itbusinessmind.com/9-user-experience-factors-you-need-to-consider/)
- [Nielsen Norman Group: Website Response Times](https://www.nngroup.com/articles/website-response-times/)
