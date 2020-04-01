## View logs
Heroku treats logs as streams of time-ordered events aggregated from the output streams of all your app and Heroku components, providing a single channel for all of the events.

## Define a Procfile
Use a Procfile, a text file in the root directory of your application, to explicitly declare what command should be executed to start your app.

## Scale the app
Right now, your app is running on a single web dyno. Think of a dyno as a lightweight container that runs the command specified in the Procfile.

## Declare app dependencies
Heroku recognizes an app as Node.js by the existence of a package.json file in the root directory. For your own apps, you can create one by running npm init --yes.

## Run the app locally
Now start your application locally using the heroku local command, which was installed as part of the Heroku CLI:

heroku local web
[OKAY] Loaded ENV .env File as KEY=VALUE Format
1:23:15 PM web.1 |  Node app is running on port 5000
Just like Heroku, heroku local examines the Procfile to determine what to run.

Open http://localhost:5000 with your web browser. You should see your app running locally.

To stop the app from running locally, in the CLI, press Ctrl+C to exit.

## Push local changes
In this step you’ll learn how to propagate a local change to the application through to Heroku. As an example, you’ll modify the application to add an additional dependency and the code to use it.

Begin by adding a dependency for cool-ascii-faces in package.json. Run the following command to do this:

npm install cool-ascii-faces
+ cool-ascii-faces@1.3.4
added 9 packages in 2.027s
Modify index.js so that it requires this module at the start. Also add a new route (/cool) that uses it. Your final code should look like this:

const cool = require('cool-ascii-faces')
const express = require('express')
const path = require('path')
const PORT = process.env.PORT || 5000

express()
  .use(express.static(path.join(__dirname, 'public')))
  .set('views', path.join(__dirname, 'views'))
  .set('view engine', 'ejs')
  .get('/', (req, res) => res.render('pages/index'))
  .get('/cool', (req, res) => res.send(cool()))
  .listen(PORT, () => console.log(`Listening on ${ PORT }`))
Now test locally:

npm install
heroku local
Visiting your application at http://localhost:5000/cool, you should see cute faces displayed on each refresh: ( ⚆ _ ⚆ ).

Now deploy. Almost every deploy to Heroku follows this same pattern. First, add the modified files to the local git repository:

git add .
Now commit the changes to the repository:

git commit -m "Add cool face API"
Now deploy, just as you did previously:

git push heroku master
Finally, check that everything is working:

heroku open cool

## Provision add-ons
Add-ons are third-party cloud services that provide out-of-the-box additional services for your application, from persistence through logging to monitoring and more.

By default, Heroku stores 1500 lines of logs from your application. However, it makes the full log stream available as a service - and several add-on providers have written logging services that provide things such as log persistence, search, and email and SMS alerts.

In this step you will provision one of these logging add-ons, Papertrail.

## Start a console
To get a real feel for how dynos work, you can create another one-off dyno and run the bash command, which opens up a shell on that dyno. You can then execute commands there. Each dyno has its own ephemeral filespace, populated with your app and its dependencies - once the command completes (in this case, bash), the dyno is removed.

## Define config vars
Heroku lets you externalize configuration - storing data such as encryption keys or external resource addresses in config vars.

At runtime, config vars are exposed as environment variables to the application. For example, modify index.js so that it introduces a new route, /times, that repeats an action depending on the value of the TIMES environment variable. Under the existing get() call, add another:

.get('/times', (req, res) => res.send(showTimes()))
At the end of the file, add the following definition for the new function, showTimes():

showTimes = () => {
  let result = ''
  const times = process.env.TIMES || 5
  for (i = 0; i < times; i++) {
    result += i + ' '
  }
  return result;
}
heroku local will automatically set up the environment based on the contents of the .env file in your local directory. In the top-level directory of your project, there is already a .env file that has the following contents:

TIMES=2
If you run the app with heroku local, you’ll see two numbers will be generated every time.

## Provision a database
The add-on marketplace has a large number of data stores, from Redis and MongoDB providers, to Postgres and MySQL. In this step, you will add a free Heroku Postgres Starter Tier dev database to your app.

Add the database:

heroku addons:create heroku-postgresql:hobby-dev
Adding heroku-postgresql:hobby-dev... done, v3 (free)
This creates a database, and sets a DATABASE_URL environment variable (you can check by running heroku config).

Use npm to install the pg module to your dependencies:

npm install pg@7
+ pg@7.18.2
added 14 packages in 2.108s
  "dependencies": {
    "cool-ascii-faces": "^1.3.4",
    "ejs": "^2.5.6",
    "express": "^4.15.2",
    "pg": "^7.18.2"
  },

  ## Next steps
You now know how to deploy an app, change its configuration, view logs, scale, and attach add-ons.

Here’s some recommended reading. The first, an article, will give you a firmer understanding of the basics. 