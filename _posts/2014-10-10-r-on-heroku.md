---
layout: post
title: "R on Heroku"
description: ""
category: heroku 
tags: [heroku,r]
---
{% include JB/setup %}

Except for the officially supported buildpacks, Heroku also has many third-party buildpacks available, R is one of them.

#Run the R console on Heroku

Here is a test from [github.com/virtualstaticvoid/heroku-buildpack-r](https://github.com/virtualstaticvoid/heroku-buildpack-r).

```
#!/bin/bash
rm -rf .git
git init
git add --all
git commit -m "initial"

heroku apps:create -s cedar -b https://github.com/virtualstaticvoid/heroku-buildpack-r.git your-app-name

app=$(heroku apps:info -s | grep ^name=)
app=${app:5}

git push heroku master

#run R console
heroku run "R --no-save" --app $app
```

Under the fold with file `init.r` which auto-run when `git push`, run all the commands above, then you can have an app named `your-app-name` on Heroku, and run R console on Heroku.

First `app` get the value `name=your-app-name`, then `${app:5}` take from the sixth character and we get `your-app-name` for `app`.

When pushed up on Heroku, the whole app takes nearly 100MB, that is the drawback part compared to the official supported language like nodejs.

You can also run `heroku run bash`, which will open the shell under the app space. When you push a nodejs app to Heroku, you can run `heroku run "node"` to open the node command line.

When you run `heroku run "R --no-save" --app $app` under the program folder, `--app $app` is not necessary.

#Another way to push app on Heroku

First directly build a new app named your-app-name on Heroku website, then we can run the follow commands locally:

```
#!/bin/bash
rm -rf .git
git init
git add --all
git commit -m "initial"

git remote add heroku git@heroku.com:your-app-name.git

heroku config:set BUILDPACK_URL: https://github.com/virtualstaticvoid/heroku-buildpack-r.git

git push heroku master
```

Then we can use `heroku run "R --no-save"` to start R console.
