---
layout: post
title: How to purge the content of the Heroku db
---

WARNING! Never execute these commands if you don't want to nuke all the data in the database being served by Heroku!

To purge the content of a Postgresql database in Heroku

```bash
heroku pg:reset DATABASE_URL --confirm vs-acme-app
heroku run rake db:migrate 
heroku run rake db:seed
```





