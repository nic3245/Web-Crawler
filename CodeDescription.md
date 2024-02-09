High-level approach: 

After setting up the command-line arguments, our program runs our Crawler. The Crawler will visit fakebook's homepage, making sure to retrieve any necessary cookies as it does so and as it gets redirected to the login. The Crawler needs to extract the extra middleware token, then submits a login POST to the website. After logging in, our Crawler begins to crawl.

This crawl is characterized by first adding any links on the randomized landing page to our list of links to visit. It then starts five threads, each of which will pull a person from the queue of people to visit, mark it as visited, and crawl that person specifically. Crawling the person specifically means visiting the home page for a person, scanning it for flags, and scanning their friends lists for flags, adding any of their friends to the queue while doing so. After visiting all the friends' pages, the task (person) is marked as complete and removed from the queue.

Once all five flags are found, the program will break out of the crawl. The flags are then printed.

Challenges we faced:
A large part of the challenge in this assignment was simply figuring out how HTTP worked. The required headers and way to format took some time to understand, and the cookies also threw us off for a bit. Logging in was the same way, as there is not much feedback other than "you did it wrong".
Another challenge was the crawler taking far to long to find the flags. However, this was not too bad to fix, as simple multithreading improved the performance drastically.


Testing Overview:

Python scratch files with examples were used to independently test aspects of the code, such as scanning an html response for flags, correctly parsing chunked data, retrieving cookies correctly, getting the redirect location correctly, and similar ones.

The crawling itself was tested on the server using various messages to std-out printing the request sent among other information. These requests were then scanned alongside firefox to ensure no loops were occurring, and that all of the friend pages were visited correctly.

The threading was tested again on the server, first with two threads. Print statements were used to make sure they were doing separate tasks and not repeating anything. The program was run to completion to ensure that ending the threads was not an issue.