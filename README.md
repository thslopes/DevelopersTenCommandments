# Ten Commandments for Software Developers, or What AI won't do for you. (WIP)
A guide from an elderly developer for a good life.

Picture a very beautiful introduction that made you think over your entire career as a software developer and the problems you've faced.

### I. Thou shalt log wisely.

It's one of the most important things in a developer's life and, yet, people don't pay the necessary attention.

It's not just "log it", although it's better than no log at all (or maybe not), it's about having meaningful logs. It's essential to add context to your logs, when possible, enough context data to simulate the situation in debug environment.

It's also very important to have a mature logging system, where you can query the log data to extract information. If you have to access log files and search for a specific event manually, you have a big problem. Also, you need to have alarm automation like error rate increased, new error, compromised deploy, etc. So, you definitely need a mature logging system.

About the previous "maybe not", it's very important to say that a log without information can be useless. You don't need a log that says "there was an error" and doesn't say what error, what the context is, and doesn't give you a clue about what happened.

It's also very important to have a pattern in your logs. If somewhere you log "productId=1", in another place you log "product=1" and somewhere else "id=1", you'll lose one of the great benefits of a mature logging system where you can filter "productId=1" and see everything that happened to that product.

An important part of the logging system is the log lib, and I'm talking about an internal lib. It's important that you don't need to code, in every handler, to add default information to the log context, like a handler identifier, a transaction id, etc.

Always try to have a transaction id. If you found an error and can track what happened or if you want to inspect a behavior, it'll be very useful.

### II. Thou shalt keep tracking the app metrics.

If you don't know the performance metrics of your app, it's very difficult to find critical behavioral changes that point to bugs or any kind of problem.

There are some specific systems for that but I already had to use custom logs to build my app metrics like request time, request count, error rate, etc.

When you publish a new version of your app, it's critical to have a way to compare the performance and error rate. Unlike a simple error count metric, an errors-per-request metric says much more. You can have a request count decreasing and the error count not going up, but you can still have a problem because the error rate is going up.

I hope you noticed that you need a way to compare app version metrics. You can keep looking at the dashboard after a publication (and you should), but you need some automation that alerts you to compromised versions.

The request time and resource usage are key metrics in this context. Identifying memory leaks or other performance issues this way is much easier and more important. If you suddenly realize your app is restarting, a request is taking too long, or your app's resource usage increases drastically and you can't track when it happened you have big trouble.

Not only for new versions, if you have a metric system that blames resources, it'll help you to identify ongoing problems much more easily. "My app error increased because of this resource", "the database time increased", etc.

### III. Thou shalt make unit tests, or even better, TDD. 
### IV. Thou shalt not do coupled deployment. 
### V. Thou shalt keep thy stack updated. 
### VI. Thou shalt do code reviews. 
### VII. Thou shalt not deploy on fridays. 
### VIII. Thou shalt understand what AI coded or thou shalt not use it. 
### IX. Thou shalt learn something new. 
### X. Thou shalt not believe in commentaries, for they do not compile. 
### XI. Thou shalt do refacs.
