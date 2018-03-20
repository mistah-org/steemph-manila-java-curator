### Local Deployment

```
$ mvn clean install
$ mvn spring-boot:run
```

Navigate to [http://localhost:8080](http://localhost:8080).

The application can also be deployed by running the `Application.java` class.

### Deploying to Heroku

<i>The following steps require that the [Heroku Toolbelt](https://toolbelt.heroku.com/) has been installed locally and that a Heroku account has been created.</i>

Navigate to the project directory on the command line.

Before creating your Heroku application, make sure that there is a Git repository associated with the project.
```
$ git status
```

If a Git repository is not associated with the project, then create one before continuing.

Create a new application on Heroku
```
$ heroku create
```

Rename your Heroku application if interested
```
$ heroku apps:rename new-name
```

Add a MongoDB database to your Heroku application with MongoLab.
Note that your Heroku account must have a credit card attached in order to use free add-ons other than the PostgreSQL and MySQL add-ons.
```
$ heroku addons:create mongolab:sandbox
```

Retrieve your MongoDB database name by clicking on the MongoLab addon.  Place the database name into the `src/main/resources/config/application-prod.yml` configuration file in the database field.

Create a new collection by clicking on the MongoLab addon.
Click on the `Add collection` button.
Create an arbitrary collection (e.g., `POST`).

Deploy project to Heroku.
```
$ git push heroku master
```

Look at your application logs to see what is happening behind the scenes.
```
$ heroku logs
```

If your application deploys without timing out then open it as follows.
```
$ heroku open
```

### Bugs and Feedback
For bugs or feature requests please create a [GitHub Issue](https://github.com/mistah-org/steemph-manila-java-curator/issues).

For general discussions or questions you can also:

* Contact me on steemit.chat