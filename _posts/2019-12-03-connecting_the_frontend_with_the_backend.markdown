---
layout: post
title:      " Connecting frontend to backend "
date:       2019-12-03 12:20:24 -0500
permalink:  connecting_the_frontend_with_the_backend
---




Attempting to build my React Redux application, using Ruby on Rails for backend started like this:

```
<app-backEnd-name>/config/ initializers/cors.rb

 
Rails.application.config.middleware.insert_before 0, Rack::Cors do
  allow do
    origins '*'
  

    resource '*',
      headers: :any,
      methods: [:get, :post, :put, :patch, :delete, :options, :head],
      credentials: true
  end
end


```


For extra protection, I wanted my backend to accept API calls only from my own frontend, therefore I replaced `origins '*'` with `origins 'localhost:3001'`

```
<app-backEnd-name>/config/ initializers/cors.rb


Rails.application.config.middleware.insert_before 0, Rack::Cors do
  allow do
    origins 'localhost:3001'
  

    resource '*',
      headers: :any,
      methods: [:get, :post, :put, :patch, :delete, :options, :head],
      credentials: true
  end
end
```

Since Rails was already using "localhost:3000", when running “npm start” the React frontend would use a different port at every attempt (and not `'localhost:3001'`), which prevented my frontend to access the backend API. 
> That is when I discovered that in the 'package.json' file there is a block with a key of “scripts”, where I can write a key "start" with a value of “PORT=3001 react-scripts start“ to keep the React server always at 'localhost:3001'


```
<app-frontEnd-name>/package.json



 "scripts": {
    "start": "PORT=3001 react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom",
    "eject": "react-scripts eject"
  }
```



Once all that is in place, the app should be up and running.






