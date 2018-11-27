The QuestionDB API
====================

The API is pretty straightforward to use, and lets you fetch search results for a keyword. 

From there, integrate the results with your internal process or tool however you'd like.

Note: In order to use the API, you will need a paid QuestionDB account.

Making a request
----------------
There's a single endpoint to query for now: `https://questiondb.io/api/questions/(your keyword string)` that supports GET requests.

To make a request, you'll need to pass your username:password with each request.

For example, here's a request to get questions that are related to "protein powder":

```shell
curl -u username:password -i https://questiondb.io/api/questions/protein%20powder
```

A successful response will look something like:

```
HTTP/1.0 200 OK
Content-Type: application/json
Content-Length: 102639
Server: Werkzeug/0.14.1 Python/3.5.5
Date: Mon, 26 Nov 2018 23:53:16 GMT

{
  "data":[
  ["healthy protein shake without expensive protein powder","https://www.reddit.com/r/EatCheapAndHealthy/comments/6tm3wt/healthy_protein_shake_without_expensive_protein/","158"],
  ["good protein powder besides isopure","https://www.reddit.com/r/ketogains/comments/9ap1r3/good_protein_powder_besides_isopure_difficulty/","116"],
  ["mixing black coffee and protein powder","https://www.reddit.com/r/Fitness/comments/4fna8d/mixing_black_coffee_and_protein_powder/","110"],
  ...]
}
```

Questions are sorted in order of popularity in the "data" array.

Each question is its own array consisting of `[question, source_url, number_of_comments_in_source]`.

Feature Requests and Feedback
-----------------------------
If you have any requests for the API, please get in touch using the information on [our contact page](https://questiondb.io/contact).

If you run into any bugs, or need help, get in touch and provide as much detail as possible, or open an issue here on Github.
