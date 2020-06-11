# Twitter Clone

This Twttier Clone is built using Ruby on Rails

- Ruby version:

```
ruby v2.6.3
```
Here are some steps to intall Ruby for Linux:

Configure ```.gemrc``` file to skip installation of Ruby documentation
```
$ echo "gem: --no-document" >> ~/.gemrc
```

Next, install Rails with a sepcific version number
```
$ gem install rails -v 6.0.2.2
```
Check your Rails version:
```
$ rails  -v
```

Install Yarn with this command which downloads and executes the necessary command:
```
$ source <(curl -sL https://cdn.learnenough.com/yarn_install)
```
You could meet a warning message like this:
```
========================================
Your Yarn packages are out of date!
Please run `yarn install --check-files` to update.
========================================
```
All you need to do is to execute the ```yarn``` command
```
$ yarn install --check-files
```
And that will be all!


- System dependencies

Due to the unfortunate case of my laptop being a Windows laptop, I am using <a href='https://aws.amazon.com/cloud9/'>Amazon EC2 Cloud9</a>'s Ubuntu Server environment.


- Database 

I used PostgreSQL for this application which can be installed quite easily.

Just add the Postgres ```pg gem``` into the production environment - ```Gemfile```:
```
group :production do
  gem 'pg', '1.1.4'
end
```
Next, run ```bundle install``` to install the Postgres gem
```
$ bundle install --without production
```

Don't forget to commit the changes!
YOU ARE DONE!


- Deployment instructions

I used Heroku to deploy this application, riding on the Postgres and SendGrid add ons. Here is a short guide to install Heroku:

Create an account for Heroku and check if your system has it
```
$ heroku --version
```

Install the necessary files!
```
$ source <(curl -sL https://cdn.learnenough.com/heroku_install)
```
This only works for cloud IDE. For other systems, do install <a href='https://devcenter.heroku.com/articles/heroku-cli'>Heroku CLI</a> by hand!

Next, login to your Heroku account. A new browser will pop up to prompt you to sign in.
```
$ heroku login --interactive
```

Finally, create a place on Heroku servers for the application to live.
```
$ heroku create
```

To deploy your commits, use Git to push the master branch to Heroku. ```master``` is included for the first time you push to Heroku, subsequent attempts can exclude ```master```
```
$ git push heroku master
```

Demo link: https://radiant-sierra-39624.herokuapp.com/
