# TrueViewer
 A React/Node web app system, with browser plugins and other forms of (user-informed) data generation designed to automate the tracking of film and television viewing for analytic and recommendation purposes.
 
 **Very much in early development status, *do not attempt to use in production!***
 
 ## Project Goals & Scope
 The collection of data about user activity online is frequently scapegoated or viewed as a user-hostile or ethically questionable endeavour. Yet many users praise the outcome of at least one such data gathering enterprise: Netflix's recommendations engine, which has produced many a happy evening (or full day!) of "binging" by suggesting entertainment content a user may enjoy based on their past activity. Unfortunately, this is not a very helpful feature for users when they run out of content on Netflix or want to know if something is likely to be "up their alley" and they have discovered it elsewhere.
 
 It is the belief of this developer that the tight holding of data as a corporate secret, practiced by companies with deep predictive algorithms, is understandable and commercially justifiable, but ultimately unhelpful to end users. It may also help generate public sentiment against data collection, even against data such as film viewing which is generally "safe" to collect. The goal of TrueViewer is to create an open-source framework as a basis for a deployable web app (which could be free software or commercial) offering accurate recommendations for films (and possibily television) for users based on their past activity, shared with their knowledge and understanding; and to create a (again, with user consent) robust framework for research based on this data which will allow, for instance, quantitative comparison between user reactions to Netflix original content and Hulu original content.
 
 The project's **ethical philosophy** is key, and should be summed up as:
 > Users should be fully aware that developers/operators of the application benefit from gathering information for research, whether for curiosity, academic goals, entertainment industry analysis, or some combination of these, and should receive the "reward" of accurate recommendations.
 
 This project is ambitious and requires several components to functions; there are additional challenges that will prevent it from fully replicating even the base information available to a company like Netflix, although with collaboration, I believe that this is a solvable problem. For basic functionality the project will require:
 
 ### Basic infrastructure
- [ ] user authentication and sign-in, creating accounts (preferably with support for including sign in with services that provide authentication APIs and may be connected with the entertainment industry) *currently experimenting with an Okta-based authentication solution*
- [ ] a database that can be run locally, or virtualized in the cloud; a low-cost AWS hosted solution with near-compatibility with Postgres seems advisable in this case. I do not believe that a NoSQL solution such as MongoDB is appropriate - rather, a full relational database will be necessary. I am conducting basic testing using a local Postgres database, but a more complex cloud-based solution will quickly be required. Microsoft SQL Server might be a compromise solution as well, as it can be hosted in Azure but also run locally at limited cost.
- [ ] a domain with an SSH certificate will be required for any significant level of real user participation once the app is functioning
- [ ] ideally, a database of existing media content should be constructed; however, this is not absolutely essential, as it could be autopopulated from user viewing habits
### Security
- [ ] User consent buy-in needs to be clear - users must understand what information will be collectted about them, and consent to it
- [ ] User data and the app in general should be hosted on secure servers, probably AWS or Azure
### Data Collection Components
Several data collection components will be essential to the project's functioning:
- [ ] A basic web interface which allows the user to log in, customize their profile, add other users as "friends," etc. Eventually should include the opportunity to rate and review film and/or television viewed; however, as this does not seem to be a necessity for proprietary algorithms, it is not a priority in this case. *Will be implemented with React.js and Node backend, possibly with some Python code*
- [ ] Browser plugins for at least Chrome and Safari, and for Firefox and Edge if possible, which replicate the concept of the [Last.fm scrobbler](https://en.wikipedia.org/wiki/Last.fm) from before the Spotify acquisition of that site. Functionality will be to (with user consent, while they are logged in to the site *via* the plugin) record viewing of feature films and television on as many specific websites as possible (Netflix, Hulu, Amazon Instant Video, HBO Max, etc.) without violating those site's legal or practical restrictions on automated data collection. This will be possible in many/most cases to a limited scope of accuracy simply from extracting the titles and URL of pages to match viewing time and activity with the names of content, and then uploading this to the site's database. *Implemented in the requisite scripting languages for the browsers - JavaScript for Chrome, Swift/AppleScript for Safari*
- [ ] Possible email and/or pop-up surveys (see [Limitations](#limitations) section)
- [ ] Possible React Native desktop application later in the development cycle, for active users
- [ ] Mobile apps to help with the limits of data collection ([discussed subsequently](#limitations))
### Data Science/Analytics
It will not be possible to immediately or likely ever fully recreate the sophistications of an algorithm like Netflix's; however, I believe that automated recording of viewing activity will be more likely to accurately incorporate, among other things, factors like audience loss of interest in content and forgettable content that was, nonetheless, viewed, than existing "media recommendation engines" which are fully reliant upon user recommendations. 
- [ ] Data should be collated in such a way as to detect user viewing patterns based on more than simply what was watched - viewing time must be factored in, and following Netflix, what was viewed before or after should be considered. Binge sessions should be detected
- [ ] User and [developer manual intervention](https://uxplanet.org/netflix-binging-on-the-algorithm-a3a74a6c1f59) was necessary in establishing Netflix's database to begin with, and should be expected for this project as well
### Limitations
The largest limitation to overcome is that a browser plugin cannot monitor user viewing on mobile devices, IoT devices, game consoles, etc. 
- [ ] To overcome this, with user opt-in (labeled as "Contact Me to Improve Understanding of Viewing Preferences") users should be contacted by either a direct mail daemon or pop-ups from the native application and/or browser plugin, asking users if they have watched anything else and to share information about this viewing
    - [ ] Consistent with project principles about being up-front about what data is collected, these pop-ups should clearly indicate that they want to know if the viewing was abortive or if the content was uninteresting
    - [ ] Mobile apps may be able to detect the opening of streaming services and - with user consent to monitoring this activity - send push notifications requesting the user share their viewing experience later
 -[ ] User buy-in may also be challenging - but given the popularity of film recommendation engines, this should not be insurmountable, and a number of steps can be taken to improve user retentions, including:
     - [ ] Explain the purpose of the app clearly
     - [ ] Include robust social features, including integrations with Twitter and Facebook allowing users, if they so choose, to share their viewing activity
     - [ ] Research surveys to make users feel valued
     
  ## Ultimate Project Goals
  Ultimately my goal is to transform this framework into a software-as-a-service, benevolent commercial research application. The goal would be able to conduct surveys by email, app, and website, as well as passive observation of user behavior, and to collate this with existing entertainment industry data to make actionable predictions about what users engage with what and what content is successful.
 
## Seeking Collaborators
Although I have the technical expertise to build this application, there are likely competitors on the market already, and there are a number of tasks (such as building a database of existing movies) that would benefit from collaboration - as would the coding itself. I'm always available for contact at ellie dot lockhart at aol dot com (my email is retro, sad face!)