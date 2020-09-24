# TrueViewer
 A React/Node web app system, with browser plugins and other forms of (user-informed) data generation designed to automate the tracking of film and television viewing for analytic and recommendation purposes.
 
 **Very much in early development status, *do not attempt to use in production!***
 
 ## Project Goals & Scope
 The collection of data about user activity online is frequently scapegoated or viewed as a user-hostile or ethically questionable endeavour. Yet many users praise the outcome of at least one such data gathering enterprise: Netflix's recommendations engine, which has produced many a happy evening (or full day!) of "binging" by suggesting entertainment content a user may enjoy based on their past activity. Unfortunately, this is not a very helpful feature for users when they run out of content on Netflix or want to know if something is likely to be "up their alley" and they have discovered it elsewhere.
 
 It is the belief of this developer that the tight holding of data as a corporate secret, practiced by companies with deep predictive algorithms, is understandable and commercially justifiable, but ultimately unhelpful to end users. It may also help generate public sentiment against data collection, even against data such as film viewing which is generally "safe" to collect. The goal of TrueViewer is to create an open-source framework as a basis for a deployable web app (which could be free software or commercial) offering accurate recommendations for films (and possibily television) for users based on their past activity, shared with their knowledge and understanding; and to create a (again, with user consent) robust framework for research based on this data which will allow, for instance, quantitative comparison between user reactions to Netflix original content and Hulu original content.
 
 This project is ambitious and requires several components to functions; there are additional challenges that will prevent it from fully replicating even the base information available to a company like Netflix, although with collaboration, I believe that this is a solvable problem. For basic functionality the project will require:
 
 ### Basic infrastructure
- [ ] user authentication and sign-in, creating accounts (preferably with support for including sign in with services that provide authentication APIs and may be connected with the entertainment industry) *currently experimenting with an Okta-based authentication solution*
- [ ] a database that can be run locally, or virtualized in the cloud; a low-cost AWS hosted solution with near-compatibility with Postgres seems advisable in this case. I do not believe that a NoSQL solution such as MongoDB is appropriate - rather, a full relational database will be necessary. I am conducting basic testing using a local Postgres database, but a more complex cloud-based solution will quickly be required. Microsoft SQL Server might be a compromise solution as well, as it can be hosted in Azure but also run locally at limited cost.
- [ ] a domain with an SSH certificate will be required for any significant level of real user participation once the app is functioning
### Security
- [ ] User consent buy-in needs to be clear - users must understand what information will be collectted about them, and consent to it
- [ ] User data and the app in general should be hosted on secure servers, probably AWS or Azure
### Data Collection Components
Several data collection components will be essential to the project's functioning:
- [ ] A basic web interface which allows the user to log in, customize their profile, add other users as "friends," etc. Eventually should include the opportunity to rate and review film and/or television viewed; however, as this does not seem to be a necessity for proprietary algorithms, it is not a priority in this case. *Will be implemented with React.js and Node backend, possibly with some Python code*
- [ ] Browser plugins for at least Chrome and Safari, and for Firefox and Edge if possible, which replicate the concept of the [Last.fm scrobbler](https://en.wikipedia.org/wiki/Last.fm) from before the Spotify acquisition of that site
 
