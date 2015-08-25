This is a simple example of getting docker-compose up and running with Rails 4.2.

1. Clone the repository

2. docker-compose run web rails new . --force --database=postgresql --skip-bundle
3. Uncommment ruby racer from Gemfile
4. docker-compose build
5. Update database.yml

development: &default
  adapter: postgresql
  encoding: unicode
  database: postgres
  pool: 5
  username: postgres
  password:
  host: db

test:
  <<: *default
  database: myapp_test

6. docker-compose up
7. docker-compose run web rake db:create
8. `docker-machine default ip` to get the ip of the server.
9. Open browser to http://<ip>:3000
