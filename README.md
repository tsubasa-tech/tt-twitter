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
  
  NOTE:  
  In order to use twitter API, you need to get twitter API consumer key.  
  https://developer.twitter.com/en.html
  
  After getting the consumer key:
  ```
  $ rm config/credentials.yml.enc
  $ docker-compose run -e EDITOR=vi web rails credentials:edit
  ```
  edit credentials as below:
  ```
  # twitter:
   twitter_consumer_key: XXXXXXXXXXXXXXXXXXXX
   twitter_consumer_secret: XXXXXXXXXXXXXXXXXXXX
  ```
  then twitter API is ready to use!

* Rails command
  ```
  docker-compose run web rails xxxx
  ```

* Reflect your change
  ```
  $ docker-compose restart
  ```

* Deployment instructions
  ```
  $ heroku login
  $ heroku container:login
  $ heroku container:push web -a tt-twitter
  $ heroku container:release web -a tt-twitter
  ```

* Reference  
『DockerComposeでコンテナベースのRailsアプリを作成してそのままHerokuにデプロイする』  
https://qiita.com/akirakudo/items/16a01271b0a39316e439  
『Railsでツイッターのツイート検索アプリを作成する』  
https://qiita.com/nishina555/items/1cebe7c953c5821158ad  
『Rails5.2から追加された credentials.yml.enc のキホン』  
https://qiita.com/NaokiIshimura/items/2a179f2ab910992c4d39
