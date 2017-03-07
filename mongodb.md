## Install Mongodb from Mac

* `brew install mongodb --with-openssl`

* To restart mongodb after an upgrade:

  `brew services restart mongodb`
  
* Or, if you don't want/need a background service you can just run:

  `mongod --config /usr/local/etc/mongod.conf`
