The QuestionDB API
====================

The API is pretty straightforward to use, and lets you fetch search results for a keyword. 

From there, integrate the results with your internal process or tool however you'd like.

Making a request
----------------
There's a single endpoint to query: `https://questiondb.io/api/questions/<your keyword string>` that supports GET requests.

There are 2 arguments you can pass in the request header:

* (Required) API Key - To make a request, you'll need to pass your API key in the header with a key value of `Api-Key`. You can get your API key from your account panel in QuestionDB.
* (Optional) Strict search value - By default, QuestionDB uses fuzzy search based on Levenshtein Distance. Usually it's useful, but sometimes you'll need to get only questions with your keyword in it. In that case, add a header of `strict:true`.

For example, here's a request to get questions that are related to "protein powder", just replace {yourApiKeyHere} with your actual API key (without the brackets):

```shell
curl -i https://questiondb.io/api/questions/protein%20powder -H "Api-Key:<yourApiKeyHere>" -H "strict:true"
```

A successful response will look something like:

```
HTTP/1.0 200 OK
Content-Type: application/json
Content-Length: 102639
Server: Werkzeug/0.14.1 Python/3.5.5
Date: Mon, 24 Feb 2020 23:53:16 GMT

{
 "data":[
  {
  "source":"https://www.reddit.com/r/EatCheapAndHealthy/comments/6tm3wt/healthy_protein_shake_without_expensive_protein/",
  "num_comments":"158",
  "question":"healthy protein shake without expensive protein powder"
  },
  {
  "source":"https://www.reddit.com/r/ketogains/comments/9ap1r3/good_protein_powder_besides_isopure_difficulty/",
  "num_comments":"116",
  "question":"good protein powder besides isopure"
  },
 ...]
}
```

Questions are sorted in order of popularity (number of comments) in the "data" array.

Each question is its own object with the following keys:
* "question" - The question string.
* "source" - The URL where the original question is from.
* "num_comments" - The number of comments in the source.

Feature Requests and Feedback
-----------------------------
If you have any requests for the API, please get in touch using the information on [our contact page](https://questiondb.io/contact).

If you run into any bugs, or need help, get in touch and provide as much detail as possible, or open an issue here on Github.
