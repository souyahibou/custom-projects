# custom-projects
App of apps using ruby hanami framework



# Custom Projects

Welcome to your new Hanami project!

## Setup

How to run tests:

```
% bundle exec rake
```

How to run the development console:

```
% bundle exec hanami console
```

How to run the development server:

```
% bundle exec hanami server
```

How to prepare (create and migrate) DB for `development` and `test` environments:

```
% bundle exec hanami db prepare

% HANAMI_ENV=test bundle exec hanami db prepare
```

## Steps

 ```
% gem install hanami
```

```
% hanami new bookshelf --database=postgresql
```

###change inner .env.development
Pattern: DATABASE_URL="postgresql://username:password@host/dbname"
Origin: DATABASE_URL="postgresql://localhost/custom_projects_development" =>
Final: DATABASE_URL="postgresql://syb8@/custom_projects_development"

_username: syb8_
_password: #no password setted for this app_
_host: #no host setted for this app_
_dbname: custom_projects_development_

## Procédure to set postgresql

###Edit .development and .test environment config files
* #.env_development Pattern
DATABASE_URL="postgresql://username:password@localhost/project_name_hanami_development"

* .env_test Pattern
DATABASE_URL="postgresql://username:password@localhost/project_name_hanami_test"

###Create a database for development and test environment.

sudo su - postgres
createuser --pwprompt username
createdb -O username project_name_hanami_development
createdb -O username project_name_hanami_test

###Prepare database.
hanami db prepare

### Run Server

```
% bundle exec hanami server
```

```
% bundle exec hanami generate action cv crtl1#show --skip-view
```












##How to Manage PostgreSQL data form CLI

###run the server's root user:
    su - postgres

###Creating PostgreSQL users
    createuser --pwprompt
      At the Enter name of role to add: prompt, type the user's name.
      At the Enter password for new role: prompt, type a password for the user.
      At the Enter it again: prompt, retype the password.
      At the Shall the new role be a superuser? prompt, type y if you want to grant superuser access. Otherwise, type n.
      At the Shall the new role be allowed to create databases? prompt, type y if you want to allow the user to create new databases. Otherwise, type n.
      At the Shall the new role be allowed to create more new roles? prompt, type y if you want to allow the user to create new users. Otherwise, type n.
      PostgreSQL creates the user with the settings you specified.

###Creating PostgreSQL databases
  createdb -O user dbname (createdb dbname)

###GRANT permissions ON DATABASE dbname TO username;
  permissions(ALL PERMISSIONS)

###Deleting PostgreSQL databases
  dropdb dbname

###Deleting PostgreSQL users
  dropuser username


##latexpdf
Latexpdf::Configuration.new
a=Latexpdf::PdfGenerator.new("/home/syb8/Documents/Projet/1.Ruby/Rails/custom_projects/apps/cv/templates/ctrl1/show.pdf.erb")

```
% hanami console
```

```
% bundle exec hanami generate action web projects#home --skip-view
```

```
% hanami routes
```
