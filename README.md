# tt-twitter
twitter search app on Rails+Docker-compose+Heroku Container Registry

* Ruby version
  - 2.5.1

* System dependencies
  - Docker  
  - Heroku

* Configuration
  ```
  $ git clone https://github.com/tsubasa-tech/tt-twitter.git
  $ docker-compose run web rails db:create
  $ docker-compose up
  ```
  - just follow three commands above, and then check http://localhost:3000/
  - from the second time, you just need start-command.
  ```
  $ docker-compose start
  ```
  - further information about docker-compose  
  https://docs.docker.com/compose/reference/overview/

* Rails command
  ```
  docker-compose run web rails xxxx
  ```

* Reflect your change
  ```
  $ docker-compose restart
  ```

* Deployment instructions
  - TBD

* Reference  
『DockerComposeでコンテナベースのRailsアプリを作成してそのままHerokuにデプロイする』  
https://qiita.com/akirakudo/items/16a01271b0a39316e439
