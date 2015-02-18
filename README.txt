This is a simple example of getting docker and fig up and running with Rails 4.2.

1. Clone the repository

2. fig run web rails new . --force --database=postgresql --skip-bundle
3. Uncommment ruby racer from Gemfile
4. fig build
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

6. fig up
7. fig run web rake db:create
8. `boot2docker ip` to get the ip of the server.
9. Open browser to http://<ip>:3000
