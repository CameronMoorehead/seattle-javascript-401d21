![cf](http://i.imgur.com/7v5ASc8.png) 19: Continuos Integration and Deployment
===

## Daily Plan
- Notes:
    - Anything top of mind?

- Code Review _How did tests go?_
- Continuous Integration _w/Travis-CI_
- Heroku Deployment _Lets deploy your RESTful APIs_
- Lab Preview

## Learning Objectives
* Students will be able to deploy their application on Heroku with a continuos delivery pipeline
* Students will be able to configure TravisCI to run their tests on all pushes to GitHub
* Students will learn about Continuous Integration
* Students will learn about Continuous Delivery

## Resources
* Read [Deploying NodeJS Apps on Heroku](https://devcenter.heroku.com/articles/deploying-nodejs)
* Read [Getting started with NodeJS on TravisCI](https://docs.travis-ci.com/user/languages/javascript-with-nodejs)

## Continuous Integration
Continuous Integration (CI) is the process of regularly merging individually developed features of code into a shared repository as frequently as they are made. In the most basic setup a team could simply use Git to merge code into a master branch. However more advanced CI patterns can be developed, that automate static analysis (linting), running unit and integration tests, testing platform support, enforcing code reviews, and much more.

## Continuous Delivery
Continuous Delivery (CD) is the process of deploying software in short cycles, by ensuring that software can be deployed at any time. CD pairs very wil with advanced CI setups that help ensure the core product is always a stable code base.

## Heroku Deployment
- enable your repository to work with TravisCI
  - *note: you may have to sync your account for TravisCI to show the repo as an option*
- add your environment variables to TravisCI by clicking on the **Settings** option in the **More options** drop-down
- log into the Heroku dashboard
- create a new app
- create a staging app *(ex: cfgram-staging)*
- click on the **Resources** tab
- in the **Add-ons** section, type *mongo* and choose the mLab option and associated free price plan
  - *note: you will need to provide a credit card with Heroku to do this - even with the free option*
- click on the **Settings** tab
- click on the **Reveal Config Vars** button and add your environment variables
  - *note: you do not need to add the MONGODB_URI variable as this was added by Heroku when you provisioned the DB - there's also no need to add a PORT, Heroku will handle this for you*
- click on the **Deploy** tab
- create a new pipeline called **staging**
- click the button to connect your application to GitHub
- in the **Automatic deploys** field, choose **staging** as your deployment branch *(you'll need to already have a `staging` branch pushed to GitHub)* and click the button to **Enable Automatic Deploys**
- **repeat** the following steps to create a production pipeline
  - *note: be sure to name the application "myapp-production", add it to a production pipeline, and enable automatic deploys to deploy to your `master` branch*