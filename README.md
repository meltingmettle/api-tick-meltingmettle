# ZD Ticket Application

Basic customer support ticket management tool. Supports ticket creation, ticket listing/viewing, and ticket updates. 

Live version here: </br>
https://emmettling.me/zd_api_meltingmettle.html</br>
Please note that Heroku dynos take ~30 seconds to start up if a site has not been accessed recently, so your first load may take up to a minute.  


Software </br>
Python 3.7.1 </br>
Django 2.1  </br>
DataTables </br>
HTML5/CSS3/JS </br>

Dependencies </br>
requests </br>
datetime (This is automatically done by the ZD API, but I calculated an independent created_at stamp) </br>
DataTables </br>

As of now, the actual code is in a private repo, so I created this repo to store the public README until I'm cleared to release the source code publicly.  


# Design challenges and time-constraint decisions:
Most notably, I opted to use Python on a Django framework over Ruby on Rails.
Although I was more familiar with the Rails framework, I chose to use Python and learn Django, largely due to the solo nature of this project.  Much of my Rails experience was on a development team where I could get help with debugging or unfamiliar concepts, whereas working in Python granted the assurance that I would be able to finish well within the due date. (This ended up costing time later, but I also got to learn some new things)  
(Also a convinient excuse to learn Django)
</br>
</br>
I removed a handful of ticket functionalities such as Requester, Assignee, Shared Ticket and a couple others as they wouldn't make sense within a single-user app and it would be difficult to implement and test in the given time frame without auto-complete or referencing a list of fellow agents.
</br>
</br>
I used a single login session to declare global variables to track the OAuth2 token and the user's company.  Although global variables are heavily frowned upon in general, this solution was the most secure and modular approach that was available at the time.  Passing the token between url requests could allow unauthorized access via url, and using cookies or the local storage would be spotty and unreliable, depending on the users' browser caching settings.  
</br>
</br>
Using the "Log Out" button will clear the session, but not the browser cache, so it is possible to view a logged out users' information via the browser's "back" button.  Patching this is slightly more complex than the scope of this project would entail.  Furthermore, the global attributes used to authenticate sessions expire in a somewhat unpredictable manner.
</br>
</br>
# Minor front end pet peeves
I hard-coded the toolbars for now, as JQuery is not supported on local servers.  Heroku provides 1000 hours of free server hosting per month, so I limited live-testing strictly to functionality to avoid the possibility of accidentally running out of free hosting.  
</br>
</br>

In addition, I didn't have the chance to reformat the JSONs returned from the API, most notably the lower-case object attributes and the compact-but-difficult-to-read API-generated timestamps. 

</br>
</br>


# Lifesaver DJango Tutorials which are still up to date (Django 2.0 or greater), if you're interested in learning! 
(In addition to the official Django docs and tutorials)
https://medium.com/agatha-codes/9-straightforward-steps-for-deploying-your-django-app-with-heroku-82b952652fb4 </br>
https://www.youtube.com/watch?v=QVX-etwgvJ8 </br>
http://www.learningaboutelectronics.com/Articles/How-to-create-a-drop-down-list-in-a-Django-form.php </br>


--Emmett Ling
