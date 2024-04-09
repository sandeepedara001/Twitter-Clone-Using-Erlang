# Twitter Clone System Using Erlang

## Overview

This project extends our initial Twitter Clone System from Part 1 by adding a client tester/simulator with a web interface, developed using the WebSharper framework. It implements the basic functionalities of Twitter, allowing users to tweet, retweet, subscribe, and query tweets through a JSON-based API.

## Team Members

- **Sai Sandeep Edara**
  - UFID: 78776619
  - Email: saisandeep.edara@ufl.edu
- **Nandani Yadav**
  - UFID: 18186343
  - Email: nandaniyadav@ufl.edu

## Video Demonstration

A demonstration of our project can be viewed [here](https://drive.google.com/file/d/1sNMa0ZHFn4yDz8mOAwCzfX49lX1D9Uy4/view?usp=sharing).

## Architecture Model

The system architecture consists of a server responsible for persisting user data and tweets, and multiple clients representing users. These clients enable users to engage in typical Twitter activities such as tweeting, retweeting, mentioning others, querying for hashtags, and subscribing to other users.

## Implementation

The project is structured into three main Erlang files:

### `mainFunctions.erl`

This file acts as the server, implementing core Twitter functionalities including user registration, tweeting, retweeting, and user subscriptions.

### `functionsForTweets.erl`

Contains helper functions that perform the underlying operations for tweet-related activities detailed in `mainFunctions.erl`.

### `userFunctions.erl`

Includes helper functions for user management tasks such as user sign-in/out, registration, and managing data storage.

## Running the Project

### Setup for Two Users

**First User:**

1. Open Erlang terminal: `erl -sname twitterServer`
2. Compile the files:
   ```erlang
   c(mainFunctions).
   c(userFunctions).
   c(functionsForTweets).
Start the server: mainFunctions:startServer().
Register and sign in the first user:
erlang
Copy code
userFunctions:userRegistration().
userFunctions:userSignIn().
Second User:

Open another Erlang terminal: erl -sname user1
Register and sign in the second user:
erlang
Copy code
userFunctions:userRegistration().
userFunctions:userSignIn().
Subscribe to the first user: mainFunctions:subscribeToAUser().
Posting and Viewing Tweets:

From the first user's terminal, send a tweet: mainFunctions:sendTweetToServer("My first tweet").
The second user, being subscribed to the first, will see the tweet appear on their homepage.
