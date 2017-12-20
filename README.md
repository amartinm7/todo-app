# todo-app

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).


git repository init
create a new repository on the command line

``` bash
echo "# todo-app" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/amartinm7/todo-app.git
git push -u origin master
```
heroku pipeline


set the scripts

  "scripts": {
    "dev": "webpack-dev-server --inline --progress --config build/webpack.dev.conf.js",
    "build": "node build/build.js",
    "start-dev": "npm run dev",
    "postinstall": "npm run build",
    "start": "node server.js"
    

install express server
npm install --save express

create server.js file as it is

heroku login
enter email and pass

heroku create <YOUR-PROJECT-NAME-HERE>
in this case amm-todo-app2

heroku config:set NODE_ENV=production --app <YOUR-PROJECT-NAME-HERE>
in this case amm-todo-app2

git init
heroku git:remote --app <YOUR-PROJECT-NAME-HERE>
in this case amm-todo-app2

git add . && git commit -a -m "Adding files."

git push heroku master

If deployment is successful, test out your project’s URL https://<YOUR-PROJECT-NAME-HERE>.herokuapp.com and you’re done!


    