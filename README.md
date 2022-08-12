# heroku-sample

### Install and run Postgres
```buildoutcfg
# Mac/Linux
# Install Postgres using Brew. Reference: https://wiki.postgresql.org/wiki/Homebrew 
brew install postgresql
# Verify the installation
postgres --version
pg_ctl -D /usr/local/var/postgres start
pg_ctl -D /usr/local/var/postgres stop
```

- Verify the database
```buildoutcfg
# Open psql prompt
ex. psql postgres
# View the available roles
\du
# View databases
\list
```
### Setup environment
```buildoutcfg
# You should have setup.sh and requirements.txt available
chmod +x setup.sh
source setup.sh
# The setup.sh will run the following:
# export DATABASE_URL="postgresql://postgres@localhost:5432/postgres"
# export EXCITED="true"
# Change the DATABASE_URL, as applicable to you.
echo $DATABASE_URL
# postgresql://postgres@localhost:5432/postgres
echo $EXCITED
# true
```

### Migrate database
```buildoutcfg
python manage.py db init
python manage.py db migrate
python manage.py db upgrade
```

## Create an App in Heroku Cloud
```buildoutcfg
heroku create [my-app-name] --buildpack heroku/python
# For example, 
# heroku create myapp-663697908 --buildpack heroku/python
# https://myapp-663697908.herokuapp.com/ | https://git.heroku.com/myapp-663697908.git
```
