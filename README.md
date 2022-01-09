The QuestionDB API
====================

The [QuestionDB](https://questiondb.io/) API is pretty straightforward to use, and lets you fetch search results for a keyword. 

From there, integrate the results with your internal process or tool however you'd like.

Making a request
----------------
There's a single endpoint to query: `https://questiondb.io/api/questions/<your keyword string>` that supports GET requests.

For example, here's a request to get questions that are related to "protein powder", just replace {yourApiKeyHere} with your actual API key (without the brackets):

```shell
curl -i https://questiondb.io/api/questions/protein%20powder
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
  {"question":"thoughts on collagen protein powder"},{"question":"protein powder that doesn't taste like protein powder"},{"question":"protein powder without the protein"},{"question":"favourite protein powder protein bars"},{"question":"extra protein via protein powder"},{"question":"protein shake w o protein powder"},{"question":"what protein powder for added protein"},{"question":"protein powder with highest protein concentration"},{"question":"whey protein powder instead of milk powder"},{"question":"is pumpkin protein powder a complete protein"},{"question":"hydrolised wheat protein protein powder in hair"},{"question":"best protein shakes smoothies without protein powder"}
  ]
}
```

Feature Requests and Feedback
-----------------------------
If you have any requests for the API, please get in touch using the information on [our contact page](https://questiondb.io/contact).

If you run into any bugs, or need help, get in touch and provide as much detail as possible, or open an issue here on Github.
