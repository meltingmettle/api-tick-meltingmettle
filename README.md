# ZD Ticket Application

Ticket REST API tool for a Zendesk ticket application. Supports ticket creation, ticket listing/viewing, and ticket updates.  

Application supports additional update capability.

Live version here:
https://zendesk-api-meltingmettle.herokuapp.com/

Software </br>
Python 3.7.1 </br>
Django 2.1  </br>
DataTables </br>
HTML5/CSS3/JS </br>

Dependencies </br>
requests </br>
datetime (This is automatically done by Zendesk's API, but I calculated an independent created_at stamp) </br>
DataTables </br>

As of now, the actual code is in a private repo, so I created this repo to store the public README until I'm cleared to release the source code publicly.  


# Design challenges and time-constraint decisions:
Most notably, I opted to use Python on a Django framework over Ruby on Rails.
Although I was more familiar with the Rails framework, I chose to use Python and learn Django, due to the time constraints and solo nature of this project.  Much of my Rails experience was on a development team where I could get help with debugging or unfamiliar concepts, whereas working in Python granted the assurance that I would be able to finish well within the due date. (This ended up costing time later, but I also got to learn some new things)  
(Also a convinient excuse to learn Django)

I removed a handful of ticket functionalities such as Requester, Assignee, Shared Ticket and a couple others as they wouldn't make sense within a single-user app and it would be difficult to do correctly without auto-complete or referencing a list of fellow agents, which was also difficult to test given the time limitations.

I used a single login session to declare global variables to track the OAuth2 token and the user's company.  Although global variables are heavily frowned upon in general, this solution was the most secure and modular approach that was available at the time.  Passing the token between url requests could allow unauthorized access via url, and using cookies or the local storage would be spotty and unreliable, depending on the users' browser caching settings.  

Using the "Log Out" button will clear the session, but not the browser cache, so it is possible to view a logged out users' information via the browser's "back" button.  Patching this is slightly more complex than the scope of this project would entail.  

