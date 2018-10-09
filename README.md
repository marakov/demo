Как развернуть приложение:
1. Привязать Heroku аккаунт к GitHub и указать репозиторий (например: https://github.com/marakov/demo)
2. После локальных изменений, запустить:
2.1. bundle
2.2. rake assets:precompile
2.3. git add .
2.4. git commit -m "message"
2.5. git push
2.6. ввести данные для логина на git hub
3. https://dashboard.heroku.com/apps/grma0716-demo/deploy/github выбрать deploy branch
4. Запустить heroku run rake db:migrate RAILS_ENV=production для миграции базы данных

Обязательное условие:
Gemfile должен содержать две группы:
1. group :development do
  gem 'web-console', '>= 3.3.0'
  gem 'sqlite3'
end
2. group :production do
  gem 'pg'
  gem 'rails_12factor'
end
