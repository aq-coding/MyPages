---
layout: post
title: "My Jekyll notes"
date: 18.11.2022
categories: jekyll
---
`Ctrl+Shift+P`, `Open folder in container`
---
`bundle exec jekyll serve --livereload` Запустить сервер jekyll на localhost:4000

dockerfile для jekyll
```
FROM ruby:3.1-alpine
RUN apk update
RUN apk add --no-cache build-base gcc cmake git
RUN gem update bundler && gem install bundler jekyll
```

`docker build -t 'github-pages-jekyll:1.0.0' .` Создать image

`docker images` Посмотреть доступные имиджи

`docker image history 83b` Посмотреть историю имиджа с id начинающимся на 83b

`docker run -d` запустить из имиджа контейнер, не отключать при закрытии терминала.
`docker run --name mycontainer -p 8080:80 github-pages-jekyll:1.0.0` 
Запустить из имиджа контейнер mycontainer, по адресу localhost:8080 (внутри контейнера порт 80)

`jekyll -v` Узнать версию. Github Pages поддерживает не последнюю.

`bundle remove jekyll`

`bundle add jekyll --version "~>3.9.2"`

`jekyll new MyPages --force --skip-bundle .` Создать проект jekyll в папке MyPages если она уже существует

`bundle exec jekyll serve --livereload` Запустить сервер jekyll на localhost:4000

`bundle add webrick`

`bundle add kramdown-parser-gfm`

`bundle install`

`bundle update`
