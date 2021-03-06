# smart-vaccine-reminder [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

This project is a Facebook Messenger Bot which can be used by hospitals to remind parents about when their kid(s) should get vaccinated through Facebook Messenger.

## Overview
This bot has the following features, 
- Sends reminders to parents about when the next vaccine is due for their kid(s)
- Check the vaccines that have been already taken.
- Provide information about the vaccines that should be taken in the future.
- Details about each vaccine.
- Managing subscription for vaccine reminders.
- Using Natural language processing(NLP), it answers questions about vaccines.
- Based on user consent, provide the data to hospitals using Google Sheets.
- Hospitals can also edit the due date for vaccines through Google sheets

Check this link to know what is facebook messenger bot and how to use it : [Click Here](https://developers.facebook.com/docs/messenger-platform/getting-started/app-setup)

## Requirements
- Ruby
- MySQL Database
- Online hosting server (AWS, Heroku, Google Cloud or any other hosting server)
- Wit Project (For Natural Language Processing)

## Getting Started
First, you'll need to fork and clone this repo

Open Terminal. Change the current working directory to the location where you want the cloned directory to be created.

```
git clone https://github.com/Balaji-Ramasubramanian/smart-vaccine-reminder.git
```
Let's get all our dependencies setup:
```
 bundle install 
```

## Configuration
You need to change the **.env** file with your appropriate access tokens, usernames, and passwords. You need to add the following details,
- Facebook page access token
- Verify token for your Facebook app
- App secret token
- Wit access token
- Database Host
- Database Name
- Database Username
- Database Password

## Migrate Database
First, you'll need to migrate the database tables
```
rake db:migrate
```

It consists of 2 tables,
- default_vaccine_schedule
- vaccination_schedule

#### default_vaccine_schedule:
The schema of the table is as follows,
- Vaccine name.
- The next due date for the vaccine.
- URL that has more details about that vaccine.

#### vaccination_schedule
This table contains the parents and their kid's details, vaccination days.

## Initializing default_vaccine_schedule table:
After the migration of the database tables, you need to fill up the default_vaccine_schedule table.

To do that, run the following command from your root of the project file
```
 ruby database_editors/default_vaccine_schedule_filler.rb 
 ```
 This will automatically fill the default values in the table.

## Deploying your app:
#### Deploying with Heroku:
You need to have Heroku CLI installed to deploy the bot in Heroku. To find more details about Heroku CLI, [click here](https://devcenter.heroku.com/articles/heroku-cli).

You can follow [this link](https://devcenter.heroku.com/articles/git) to setup the Heroku environment for the project.

For this project, you need the following resources in your Heroku project,
- ClearDB MySQL :: Database
- Heroku Scheduler


I will update the instructions for deploying the app in AWS, Google Cloud and Microsoft Azure shortly.

## Contribute
#### Simple 3 step to contribute to this repo:
1. Fork the project.
2. Make required changes and commit.
3. Generate a pull request. Mention all the required description regarding the changes you have made.

## Author 
#### Balaji Ramasubramanian

If you need any help in customizing and deploying this project, email me @ balaji030698@gmail.com

## License
Copyright 2018 Balaji Ramasubramanian

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.


