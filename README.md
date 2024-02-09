# Web-Crawler
A from scratch, no (crawler) package web crawler to college secret flags on a fake website
# Description
The fake website can be found here: <br>
[Fakebook](https://www.3700.network/) <br>
3700crawler is run with optional server and port, and with the username and password to log into fakebook with. <br>
Usage: <br>
$ ./3700crawler <-s server> <-p port> <username> <password> <br>
The crawler uses HTML 1.1 and multi-threading to scrape the website efficiently and safely, then scans the contents for secret flags and prints them out when found.
Once it has found all five, it saves them to a file called "secret-flags.txt" and exits.
