
<a name="readme-top"></a>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/tonitoar/event.io-GENERAL-">
    <img src="./public/images/readme-logo2.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">README</h3>

  <p align="center">
    An awesome README for Eventio, our Final Project at Ironhack!
    <br />
    <a href="https://github.com/tonitoar/event.io-GENERAL-"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/tonitoar/event.io-GENERAL-">View Demo</a>
    ·
    <a href="https://github.com/tonitoar/event.io-GENERAL/issues">Report Bug</a>
    ·
    <a href="https://github.com/tonitoar/event.io-GENERAL/issues">Request Feature</a>
  </p>
</div>


<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With MERN and much love from our team</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



## About The Project

[![Product Name Screen Shot][product-screenshot]](https://example.com)

"eventio" is an event booking app that allows users to discover and book various events in the city they live and love, filtering per several criterias like proximity, type of event, number of attendees, etc. The app aims to provide a seamless user experience and facilitate event management for both organizers and attendees.

Its the final project (Project3) from Web Development-Full Time 2023. As you already can imagine, we have spent so many hours trying to create this amazing final project, which includes all technical requirements requested by the Student Portal.
* Develop a Full-stack application using the MERN stack (MongoDB, Express, React and Node.JS). 
* Using MERN stack.
* To have a fully functional full-stack application.
* Using Agile methodologies and participating in Agile rituals, such as daily stand-ups.

So, in conclusion:

* Have a SPA frontend, built with React, consisting of multiple views and implementing all CRUD actions.
* Have a REST API backend built with ExpressJS, MongoDB and Mongoose, that our React app will communicate with.
Have a REST API backend with routes that perform all CRUD actions for at least one model (excluding the user model).
* Have 3 database models or more. Having one model for users is the first step. The other two (or more) models should represent the main functionality of our app.
* Include sign-up, log-in and log-out functionality with encrypted passwords (or social login) and authorization (logged-in users can do additional things).
* Have two separate repos on GitHub. One repo is for frontend React application and the other is for our backend REST API.
* Have at least 2 commits per day that we worked on.
* Have a backend validation and centralized error handling in our REST API.
* Be deployed online, allowing anyone to access and use our app.


<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Built With

This section should list any major frameworks/libraries used to bootstrap your project. Leave any add-ons/plugins for the acknowledgements section. Here are a few examples.

* [![React][React.js]][React-url]
* [![Express][Express.js]][Express-url]
* [![Node.js][Node.js]][Node-url]
* [![Tailwind-css][Tailwind-css]][Tailwind-url]
* [![Yarn][Yarn]][Yarn-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.

### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
* npm
  ```sh
  npm install npm@latest -g
  ```

### Installation

_Below is an example of how you can instruct your audience on installing and setting up your app. This template doesn't rely on any external dependencies or services._

1. Get a free API Key at [https://example.com](https://example.com)
2. Clone the repo
   ```sh
   git clone https://github.com/your_username_/Project-Name.git
   ```
3. Install NPM packages
   ```sh
   npm install
   ```
4. Enter your API in `config.js`
   ```js
   const API_KEY = 'ENTER YOUR API';
   ```

### Setting up Models

**Model #01: Event**
- [ ] Title
- [ ] Date
- [ ] Location
- [ ] Event Description
- [ ] Max Capacity # of Attendees
- [ ] Total # of Attendees
- [ ] Image "URL"
- [ ] Buyers {type: Schema.Types.ObjectId...ref:"User"}
- [ ] is cancelled

**Model #02: User**
- [ ] (_id)
- [ ] Created Events {type: Schema.Types.ObjectId...ref:"Events"}
- [ ] Username
- [ ] Email
- [ ] Password
- [ ] isAdmin


**Model #03: Event_User_Quant**
- [ ] idUser
- [ ] idEvent
- [ ] Quantity


### Setting up Routes

### Front - End

- /signup  (publicview)
- /login (publicview)
- (/logout) (privateview)
- /  --->mainpage (publicview)
- event/:eventId (publicview)
- /user/:userId (privateview) This page will be only available to current userId
- /admin
- /admin/event/create
- /admin/:eventId/edit

### Back - End

| Method | Endpoint                    | Require                                             | Response (200)                                                        | Action                                                                    |
| :----: | --------------------------- | --------------------------------------------------- |---------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| POST   | auth/signup                     | const { username, email, password } = req.body      | json({user: user})                                                    | Registers the user in the database and returns the logged in user.        |
| POST   | auth/login                      | const { email, password } = req.body                | json({authToken: authToken})                                          | Logs in a user already registered.                                        |
| POST   | verify                      | |  | Logs in a user already registered.                                        |
| POST   | user/:eventId/unnatend                      | const { email, password } = req.body                | json({authToken: authToken})                                          | Logs in a user already registered.                                        |
| POST   | user/:eventId/cancel                      | const { email, password } = req.body                | json({authToken: authToken})                                          | Logs in a user already registered.                                        |
| POST   | user/events/create                      | const { email, password } = req.body                | json({authToken: authToken})                                          | Logs in a user already registered.                                        |
| POST   | /admin/events/:eventsId/edit                      | const { email, password } = req.body                | json({authToken: authToken})                                          | Logs in a user already registered.                                        |
| POST   | user/events/:eventId/confirm                      | const { email, password } = req.body                | json({authToken: authToken})                                          | Logs in a user already registered.                                        |
| POST   | events/:eventId/confirm                      | const { email, password } = req.body                | json({authToken: authToken})                                          | Logs in a user already registered.                                        |



**GET ROUTES**

- GET/events ---> res.json ({{events}})
  - [ ] Returns last 10 events 
  if request.query is empty, it will return the last 10. If there's a filter, it will return filter applied coincidences
- GET/events? ---> filter = =(req.query)
  - [ ] Returns coincidences with filter applied
- GET/events/:eventId ---> 
  - [ ] Returns an event with populated buyers
- GET/user/:userId --->
  - [ ] Returns all the user events
  Model 3 Event_User_Quant
- GET/admin/events --->
  - [ ] Returns all admin events
  Model 2 created events

**POST ROUTES**

- POST/auth/signup
- POST/auth/login
- POST/auth/verify
- POST/user/:eventId/unnatend
eliminate from model 3 and update model 1 (buyeer,invitados, update buyer array)
- POST/admin/events/create
creates model 1 event
- POST/admin/events/:eventId/cancel
model 3
update model 1 is cancelled, seleccionate buyers and send email to each one. cancelled true
- POST/admin/events/:eventId/edit
if admin updates event, nodemailer 
- POST/events/:eventId/confirm
  - [ ] Check that there's availability
  - [ ] Update event with number of invited people and userid buyer array to let them know.
  - [ ] Create an "event_user_quant"

if aforo - invitats >= ticket que demanes


<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Roadmap

- [x] Create Readme.md 
- [x] Create [Project Repo](https://github.com/tonitoar/event.io-GENERAL-)
- [x] Create MongoDB Database
- [x] Create both Front and Back Routes
- [x] Create and setup Models
    - [ ] Event
    - [ ] User
- [ ] Add design

See the full [Height Control](https://height.app/HZgn9mMHKU/eventio---wd-ft-bcn-2023-pedro-toni-xavi) we used for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**, but please bear in mind that this Project is the result of 2 intensive full time months and there's plenty of margin to improve. **So we would appreciate constructive feedback only**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>




## License & Copyright.

Distributed under the Ironhack License. All copyrights and intelectual property belong to the owners of the present Project. The owners may user their legal rights to defend the project at any time.

<p align="right">(<a href="#readme-top">back to top</a>)</p>




## Contact

Pedro Torres - [@kitschest_](https://twitter.com/kitschest_) - kitschestt@gmail.com 

Toni Torredemer  - toni.torredemer.argiles@gmail.com

Xavier Trallero [@XTG1724](https://twitter.com/XTG1724) - xaviertralleroguillot@gmail.com

Project Link: [https://github.com/tonitoar/event.io-GENERAL-](https://github.com/tonitoar/event.io-GENERAL-)

<p align="right">(<a href="#readme-top">back to top</a>)</p>




## Acknowledgments & Recognition

We could have not succeeded without the help of our teacher Mariona Roca and our Teacher Asssistant Yabel Rodriguez. Thank you for all your work!

* [Mariona Roca](https://www.linkedin.com/in/marionaroca/)
* [Yabel Rodriguez](https://www.linkedin.com/in/yabel-rodriguez/)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]:https://github.com/trallas;https://github.com/Kitchest;https://github.com/tonitoar

[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/xaviertrallero
[product-screenshot]: ./public/images/eventio-demo.png
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Express.js]: https://img.shields.io/badge/-Express-yellow
[Express-url]: https://expressjs.com/
[Node.js]: https://img.shields.io/badge/-Node.js-brightgreen
[Node-url]: https://nodejs.org/es
[Tailwind-css]: https://img.shields.io/badge/-Tailwind-blue
[Tailwind-url]: https://tailwindcss.com/
[Yarn]: https://img.shields.io/badge/-Yarn-red
[Yarn-url]: https://yarnpkg.com/
