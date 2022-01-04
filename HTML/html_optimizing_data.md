# Building on HTML5: optimizing for data, communicatino and offline apps.

## Tips and learnings

***Saving data in the browswer***
- Web/DOM storage -> client only key/value pair for storing small amounts of data in the browser.
    - Local storage -> is available even when you turn of your pc.
    - Session storage -> is gone when the tab closes
    - Security -> per domain and per session
    - Capacity -> Client controlled thus it can be different per browser and per user. Max 5mb. 
- Web storage vs Cookies 
    - Moderate capacity vs small capacity
    - Data stays on client side vs sent to server with each request
    - Server cannot write to storage vs Server can write to cookies
- IndexDB
    - document database (objects)
    - transactional
    - Same origin policy
    - Query against known keys
    - up to 50% of available disk space, no more than 20% of allowed space for a single origin, Least recently used (LRU) or a user may delete it.
- Web storage vs IndexDB
    - moderate capacity vs high capacity
    - no query language vs key based queries
    - simple api vs comple api

- When and why:
    - Cookies: unique data identifier or small amounts of profile data
    - web storage: simple data storage
    - IndexedDB: support of database (this could be any other db)

- Saving data in the browser options: Localstorage, sessionstorage, storageevents, objects in web storage, objects in web storage, indexeddb

***Creating multithreaded web applications***
- Web workers - browser based background threads
    - Dedicated worker: only accessible throught the script that spawns the worker.
    - Shared worker: available to any page in the domain, handles exclusively with dedicated workers.
- Communication between the page and worker: Navigator, platform, timers, XMlHTTPrequest(ajax), import scripts
- Restriction in the worker script NO ACCES TO THE DOM, UI related members of window, host page.

- When and why 
    - Isolation 
    - Long running and computationally intensive tasks
    - For more information: https://blog.sessionstack.com/how-javascript-works-the-building-blocks-of-web-workers-5-cases-when-you-should-use-them-a547c0757f6a_)


***Taking your application offline***
- Service worker: Proxy server thata sists bewtween web applications, the browser and the network.
    - service worker cookbook: https://css-tricks.com/serviceworker-for-offline/ 
- Lifecycle https://web.dev/offline-cookbook/
- Api's Fetch, cache, service worker.
- Implementation pattern example: pull from cach, if not in cache, make network call and cache the result



***Communication in real time***
- Web sockets: two way client server communication
- Http headers vs web sockets
    - Http polling continuously request - response 100s of bytes
    -  socket header is 2 bytes.
    - Web sockets have a two way continues connection.
- Web sockets are way better for scale. 
- There is no need for a request it can push communication back and forward


***Making your application geographically aware***
- Request patterns for geolocation
    - One time
    - Continual
- Possible ways of getting your location: Ip, GPS, Wifi, cell phone, user defined
- Location options: Accuracy, timeout, maximum age


### Own opinion
I love the different storage options. It is interesting how all the requests are being handeled. I should dive deeper into this subject. In general I think this is a good overview of what is possible. 