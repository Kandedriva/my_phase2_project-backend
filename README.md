# JSON Server Template

## Setup

Fork and clone this repo. Then install the dependencies by running:

```sh
npm install
```

## Seeding Data

To set up your database, update the `db/seeds.json` file to contain an object
with a key pointing to an array of data, like this:

```json
{
  { "availableJobs" : [
  {
    "id": 0,
    "company": "Amazon",
    "jobTitle": "Amazon Shopper",
    "salary": "$19/hour",
    "website" : "www.amazon.force.com",
    "experience": "No experience Require",
    "location": "Brooklyn New York",
    "description": "work in the warehouse: Work hard, have fun, make history."

  },
  {
    "id": 1,
    "company": "Google",
    "jobTitle": "React developer",
    "salary": "$50/hour",
    "website": "www.google.com",
    "experience": "No experience Require",
    "location": "Online",
    "description": "Apply what you learn at Flatiron School"
  },
  {
    "id": 2,
    "company": "Microsoft",
    "jobTitle": "FrontEnd web developer",
    "salary": "$55/hour",
    "website": "www.microsoft.com",
    "experience": "No experience Require",
    "location": "Online and personal",
    "description": "Apply what you learn at Flatiron School"
  }
],
"users":[
  {
      "id": 0,
      "fName": "Drissa",
      "lName": "Kande",
      "email": "123web@gmail.com",
      "password": "Goodluck"
  },
  {
      "id": 1,
      "fName": "Issa",
      "lName": "Nacanabo",
      "email": "nacson@gmail.com",
      "password": "Youtube"
  },
  {
      "id":2,
      "fName": "Oumar",
      "lName": "Soumahoro",
      "email": "OleO@gmail.com",
      "password": "Filsd'Imam"
  }
],
"waitingList":[
  {
      "id":0,
      "applicationName": "Drissa",
      "lastName": "Kande",
      "email": "123web@gmail.com",
      "history": "I used to work in a Restaurant at Whole Food Market, and I'm currently working at Amazon",
      "education": "Student at Flatiron School",
      "availability": "Every Day, any time"
  }
]
}
  ]
}
```

Then, run `npm run seed` to copy data from the `db/seeds.json` file to the
`db/db.json` file. `json-server` uses the `db.json` file to create your RESTful
API, so make sure your `db.json` file is always up to date!

Any time you want to reset your database back to your original data, run
`npm run seed` again. Doing this will overwrite all the data in your `db.json`
file, so make sure you don't have any data in that file that you don't mind
losing!

## Running the Server Locally

To run your server in development mode, run:

```sh
npm run dev
```

While running in development mode, the server will re-load any time you make
changes to the `db.json` file, so you can test our your seed data.

While your server is running, you can make requests to
[http://localhost:3000](http://localhost:3000). Check it out in the browser to
make sure your server works!

## Deploying

Free services like Render make it simple to deploy your Node server. Render also
works nicely with Rails, which you'll learn later in the program.

### Sign Up for a Render Account

You can sign up for a free account at
[https://dashboard.render.com/register][Render signup]. We recommend that you
sign up using GitHub as that will make it a little easier for you to connect
Render to your GitHub account. The instructions below assume you've done that.

[Render signup]: https://dashboard.render.com/register

Once you've completed the signup process, you will be taken to the Render
dashboard.

In order to connect Render to your GitHub account, you'll need to click the "New
Web Service" button in the "Web Services" box. On the next page, you will see a
GitHub heading on the right side and below that a link labeled "Configure
account". (If you didn't sign up using GitHub, it will say "Connect account"
instead.) Click that link; a modal will appear asking you for permission to
install Render on your GitHub account. Click "Install." You should then be taken
back to the "Create a New Web Service" page, which should now show a list of
your GitHub repos.

### Deploy the Server

Find the GitHub repo for your json server in the list and click Connect. Give
the web service a name and make sure the Environment is set to Node. Everything
else can be left as is. Scroll down to the bottom of the page and click "Create
Web Service." The build process will begin automatically.

The URL for your deployed server is shown in the upper left corner of the page,
e.g., `https://my-server.onrender.com`. Once the build is complete, you will be able to
make fetch requests to that URL.

### Making Updates

Since Render deployment integrates with your GitHub repo, you can easily deploy
changes to your database. First, commit and push your code up to GitHub:

```sh
git add .
git commit -m "Updated database"
git push
```

Then launch the build process by going to the page for your server on the
Render dashboard, clicking the "Manual Deploy" button in the upper right corner
of the page, and selecting "Deploy latest commit."
