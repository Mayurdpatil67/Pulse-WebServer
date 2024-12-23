<h1>Multi Threaded Proxy Server with Cache</h1>

This project is implemented using `C` and Parsing of HTTP referred from <a href = "https://github.com/vaibhavnaagar/proxy-server"> Proxy Server </a>

## Index
- [Project Theory](#project-theory)
- [How to Run](#How-to-Run)
- [Contributing](#contributing)

## Project Theory

##### Introduction

##### Basic Working Flow of the Proxy Server:
![](https://github.com/Mayurdpatil67/Pulse-WebServer/blob/master/Images/webs.jpg)

##### How did we implement Multi-threading?
- Used Semaphore instead of Condition Variables and pthread_join() and pthread_exit() function. 
- pthread_join() requires us to pass the thread id of the the thread to wait for. 
- Semaphore’s sem_wait() and sem_post() doesn’t need any parameter. So it is a better option. 

##### Motivation/Need of Project
- To Understand → 
  - The working of requests from our local computer to the server.
  - The handling of multiple client requests from various clients.
  - Locking procedure for concurrency.
  - The concept of cache and its different functions that might be used by browsers.
- Proxy Server do → 
  - It speeds up the process and reduces the traffic on the server side.
  - It can be used to restrict user from accessing specific websites.
  - A good proxy will change the IP such that the server wouldn’t know about the client who sent the request.
  - Changes can be made in Proxy to encrypt the requests, to stop anyone accessing the request illegally from your client.
 
##### OS Component Used ​
- Threading
- Locks 
- Semaphore
- Cache (LRU algorithm is used in it)

##### Limitations ​
- If a URL opens multiple clients itself, then our cache will store each client’s response as a separate element in the linked list. So, during retrieval from the cache, only a chunk of response will be send and the website will not open
- Fixed size of cache element, so big websites may not be stored in cache. 

#### Note :-
- Code is well commented. For any doubt you can refer to the comments.

## How to Run

```bash
$ git clone https://github.com/Mayurdpatil67/Pulse-WebServer.git
$ cd Pulse-WebServer
$ make all
$ ./proxy <port no.>
```
`Open http://localhost:port/https://www.cs.princeton.edu/`

# Note:
- This code can only be run in Linux Machine. Please disable your browser cache.

## Contributing
Feel free to fork and CHANGE. 
1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/AmazingFeature`).
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Open a pull request.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

I would like to express my gratitude to Lovepreet Singh for their excellent tutorial, which was instrumental in the development of this project.
You can find the tutorial here: Build Your Own WebServer : https://www.youtube.com/watch?v=eTvSgOoc_BE&list=PL7CBVLpg0zqdefaZ8SSZp-QgqsSimPQaA.


[[Back to top]](#index)
