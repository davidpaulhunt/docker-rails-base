1. Clone repo
2. Start docker
3. Run rails new command: `docker-compose run web rails new . --api --force --no-ri --no-rdoc -T --database=postgresql`
4. Run `docker-compose build`
5. Update database.yml:
  ```
  default: &default
    adapter: postgresql
    encoding: unicode
    host: db
    username: postgres
    password:
    pool: 5

  development:
    <<: *default
    database: myapp_development


  test:
    <<: *default
    database: myapp_test
  ```
6. Run `docker-compose up`
