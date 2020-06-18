# This project is of type script. Explain about logging in typescript
    * This project explain about the logging feature in typescript
    * You can see the configuration in folder config/logging 
    * There are various config properties and level and appender,
    * Focus on index.js which include logging usage. 
    * This project also explain about the json mapping with object in type script.
        * Using the class-transformer
    * nodemon is node application runtime. the difference between node and nodeman is
        * Nodeman takes the runtime changes and execute at the same time without re-starting the application
    * Execute below command in project directory where package.json file is present
       ``` npm install
       ```
    * For access logging in type script : Follow : https://github.com/log4js-node/log4js-node/blob/master/docs/connect-logger.md
        ```
        var log4js = require('log4js');
        var express = require('express');
        
        log4js.configure({
         appenders: {
           console: { type: 'console' },
           file: { type: 'file', filename: 'cheese.log' }
         },
         categories: {
           cheese: { appenders: ['file'], level: 'info' },
           default: { appenders: ['console'], level: 'info' }
         }
        });
        
        var logger = log4js.getLogger('cheese');
        var app = express();
        app.use(log4js.connectLogger(logger, { level: 'info' }));
        app.get('/', function(req,res) {
          res.send('hello world');
        });
        app.listen(5000);
        ```
