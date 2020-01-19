# Heroku Cheat Sheet

## Heroku CLI (heroku)

### Authenticating
    heroku login
    
### Creating an Application
    heroku create <app-name>

### Provisioning a Database
    heroku addons:create heroku-postgresql:hobby-dev
    
### Setting Environment Variables
    heroku config:set <key>=<value>

### Testing with Heroku Local
    heroku local
Environment variables defined by `heroku config:set` are not available when running the application
locally. The `heroku local` command looks for environment variables in the top-level `.env` file.

### Deploying an Application
    git push heroku master
    
### Deploying an Upgrade
    heroku maintenance:on
    git push heroku master
    heroku restart
    heroku maintenance:off
    
### Reviewing Logs
    heroku logs -t
* The `-t` argument indicates to only show the "tail" of the log file.

### One-Off Dyno
    heroku run <command>
One-off dynos run attached to your terminal, with a character-by-character TCP connection for `STDIN` and `STDOUT`. 

## Procfile
    web: gunicorn run:app
In each line a task name is given, followed by a colon and then the command that runs the task.
The task name `web` is special; it is recognized by Heroku as the task that starts the web server.
