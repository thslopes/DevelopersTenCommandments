# Ten Commandments for Software Developers, or What AI won't do for you. (WIP)

### Guide from an elderly developer for a good life.

Pretend that there's a very beautiful introduction that made you think over your entire carrer as a software developer and the problems you've faced(believe, not AI generated).

## I. Thou shalt log wisely. 

It's one of the most important things in a developer's life and, even so, people don't pay the necessary atention.

It's not just "log it", although it's better than no log at all(or maybe not), it's about having meaningfull logs. It's essential to add context to your logs, when possible, enough context data to simulate in debug envoronment the situation. 

It's also very importanto to have a log mature system, where you can query the log data to extract information. If you have to acces log files and search for an specific event manually you have a big problem. Also, you need to have alarms automation like error rate increased, new error, compromised deploy, etc. So, you definitely need a mature log system.

About the previous "maybe not" it's very important to say that log without information can be useless. You don't need a log that say "there was an error" and don't say what error, what the context and don't give you a clue about what happened.

It's also very importanto to have a pattern in your logs. If somewhere you log "productId=1", in another place you log "product=1" and somewhere else "id=1", you'll lost one of the great benefits of a mature log system where you can filter "productId=1" and see everything that happened to that product.

An important part of the log system is the log lib, and I'm talking about an internal lib. It's important that you don't need to code, in every handler, to add default information to the log context, like a handler indentifier, a transaction id, etc.

Always try to have a transaction id. If you found an error and can track the what happened or if you want to inspect a behavior it'll be very usefull.

## II. Thou shalt keep tracking the app metrics. 

If you don't know the performance metrics of your app it's very difficult to find critical behavioring changes that point to bugs or any kind of problem.

There're some specific systems for that but I already had to use custom logs to build my app metrics like request time, request count, error percent, etc. 

When you publish a new version of your app, it's critical to have a way to compare the performance and error rate. Different from a metric of error increasing, a metric of erros per request says much more. You can have a request count decreasing and the error count not going up, but you can still have a problem because the error rate is going up.

I hope you noticed that you need a way to compare app versions metric's. You can keep look to the dashboard after a publication (and you should) but you need some automatizations that alarms for compromized versions.

The request time and resource usage are key metrics in this context. Identifying memory leaks or other performance issues this way is much easier and important. If you suddenly realize your app is restarting, a request is taking too long or your app is taking too much resources and you can't track the when it happened you have big throuble.

Not only for new versions, if you have a metric system that blame resources it'll help you to indentify ongoing problems much easier. "My app error increased because of this resource", "the database time increase", etc.

### III. Thou shalt make unit tests, or even better, TDD. 
### IV. Thou shalt not do coupled deployment. 
### V. Thou shalt keep thy stack updated. 
### VI. Thou shalt do code reviews. 
### VII. Thou shalt not deploy on fridays. 
### VIII. Thou shalt understand what AI coded or thou shalt not use it. 
IX. Thou shalt learn something new. 
X. Thou shalt not believe in commentaries, for they do not compile. 
XI. Thou shalt do refacs.
