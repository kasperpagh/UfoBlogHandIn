# The Road to Rapid Mongo Queries

In a recent project we used MongoDB to store a very large dataset (millions of entries). But as the number of saved documents increased, we saw a steep decline in the performance of our queries to the database.

This lackluster performance meant that our server often had very slow response time for http requests, and that our frontend often took upwards of 15 seconds just to populate the frontpage.

Through the use of indices in our database we managed to decrease the average response time for the server from 15358 ms to 48 ms - that’s more than 300 times faster!!

Everyone who handles large numbers of documents in MongoDB and isn't already using indices will benefit by introducing them in their collections.

## Description of the Database

In the recent school project, we have set up a simple REST API to handle a HackerNews clone site. For this basic site our teacher would automatically post posts to our API over the projects time period. This ended up with us having millions on posts stored in our database, since we were getting new posts all the time over several weeks. As of right now we have over 5 million posts:

The backend for our web application is a Node.js instance running an Express server with mongoose to model our data to a Mongo database. Each post has several fields most related to the post itself, but some also relating the post to users and other posts.

Our web application is hosted on digitalocean on a very limited server. The server has 1GB of RAM, and 30GB of disk space, and 1 CPU core.
