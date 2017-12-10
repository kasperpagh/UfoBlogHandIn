# The Road to Rapid Mongo Queries

In a recent project we used MongoDB to store a very large dataset (millions of entries). But as the number of saved documents increased, we saw a steep decline in the performance of our queries to the database.

This lackluster performance meant that our server often had very slow response time for http requests, and that our frontend often took upwards of 15 seconds just to populate the frontpage.

Through the use of indices in our database we managed to decrease the average response time for the server from 15358 ms to 48 ms - that’s more than 300 times faster!!

Everyone who handles large numbers of documents in MongoDB and isn't already using indices will benefit by introducing them in their collections.

