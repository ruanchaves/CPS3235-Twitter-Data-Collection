# CPS3235-Twitter-Data-Collection

This repository contains data collected from Twitter related to Elon Musk. The data is saved in JSONL format, which is a combination of JSON objects separated by newlines.

## How to read the files

Here is an example of how to read and process the data contained in the JSONL files:

```python
import json

# Open the file for reading
with open('following.json', 'r') as f:
    # Read each line of the file
    for line in f:
        # Parse the line as a JSON object
        data = json.loads(line)
        # Do something with the data
        print(f'Name: {data["name"]}, Username: {data["username"]}')
```

## Files

### following.json 

A list of JSON objects, each representing a user that Elon Musk is following on Twitter.

#### Fields

* `id: The unique identifier for the user.
* name: The user's real name.
* username: The user's Twitter handle.

#### Example

```
{
  "id": "1234567890",
  "name": "John Smith",
  "username": "jsmith"
}
```

## followers.json

A list of JSON objects, each representing a user who is following Elon Musk on Twitter.

#### Fields

Same as `following.json`. 

#### Example

Same as `following.json`.

## tweets.json

A list of JSON objects, each representing a tweet made by Elon Musk.

#### Fields

- "entities": information about various entities mentioned in the tweet, such as URLs and hashtags. 
  - "urls":
    - "start": the start position of the URL within the tweet.
    - "end": the end position of the URL within the tweet.
    - "url": the URL as it appears in the tweet text.
    - "expanded_url": the fully expanded version of the URL.
    - "display_url": the shortened version of the URL that is displayed to users.
    - "media_key": a unique identifier for media attached to the tweet.
- "reply_settings": who the tweet is intended to be visible to. Possible values include "everyone" and "followers".
- "author_id": the unique identifier of the user who created the tweet.
- "context_annotations": an array of entities mentioned in the tweet and the domain they belong to.
  - "domain": 
    - "id": a unique identifier for the domain.
    - "name": the name of the domain.
    - "description": a description of the domain.
  - "entity": 
    - "id": a unique identifier for the entity.
    - "name": the name of the entity.
    - "description": a description of the entity.
- "lang": the language of the tweet text.
- "text": the text of the tweet.
- "edit_history_tweet_ids": an array of unique identifiers of tweet versions in the edit history.
- "public_metrics": metrics about the tweet.
  - "retweet_count": number of times the tweet has been retweeted.
  - "reply_count": number of replies to the tweet.
  - "like_count": number of likes the tweet has received.
  - "quote_count": number of times the tweet has been quoted in other tweets.
- "attachments": information about media attached to the tweet.
  - "media_keys": an array of unique identifiers for media attached to the tweet.
- "conversation_id": the unique identifier of the conversation the tweet belongs to.
- "possibly_sensitive": a boolean True or False value indicating whether the tweet may contain sensitive content.
- "id": the unique identifier of the tweet.
- "created_at": the date and time the tweet was created.
- "source": the source from which the tweet was sent.

#### Example

```
{
  "entities": {
    "urls": [
      {
        "start": 29,
        "end": 52,
        "url": "https://t.co/jgGYovK6jL",
        "expanded_url": "https://twitter.com/elonmusk/status/1600439088560996353/video/1",
        "display_url": "pic.twitter.com/jgGYovK6jL",
        "media_key": "7_1600439072404619264"
      }
    ]
  },
  "reply_settings": "everyone",
  "author_id": "44196397",
  "context_annotations": [
    {
      "domain": {
        "id": "46",
        "name": "Business Taxonomy",
        "description": "Categories within Brand Verticals that narrow down the scope of Brands"
      },
      "entity": {
        "id": "1557696848252391426",
        "name": "Financial Services Business",
        "description": "Brands, companies, advertisers and every non-person handle with the profit intent related to Banks, Credit cards, Insurance, Investments, Stocks "
      }
    },
    {
      "domain": {
        "id": "46",
        "name": "Business Taxonomy",
        "description": "Categories within Brand Verticals that narrow down the scope of Brands"
      },
      "entity": {
        "id": "1557697333571112960",
        "name": "Technology Business",
        "description": "Brands, companies, advertisers and every non-person handle with the profit intent related to softwares, apps, communication equipments, hardwares"
      }
    },
    {
      "domain": {
        "id": "10",
        "name": "Person",
        "description": "Named people in the world like Nelson Mandela"
      },
      "entity": {
        "id": "808713037230157824",
        "name": "Elon Musk",
        "description": "Elon Musk"
      }
    },
    {
      "domain": {
        "id": "65",
        "name": "Interests and Hobbies Vertical",
        "description": "Top level interests and hobbies groupings, like Food or Travel"
      },
      "entity": {
        "id": "781974596148793345",
        "name": "Business & finance"
      }
    },
    {
      "domain": {
        "id": "66",
        "name": "Interests and Hobbies Category",
        "description": "A grouping of interests and hobbies entities, like Novelty Food or Destinations"
      },
      "entity": {
        "id": "857878777191211008",
        "name": "Leadership",
        "description": "Leadership"
      }
    },
    {
      "domain": {
        "id": "131",
        "name": "Unified Twitter Taxonomy",
        "description": "A taxonomy of user interests. "
      },
      "entity": {
        "id": "808713037230157824",
        "name": "Elon Musk",
        "description": "Elon Musk"
      }
    },
    {
      "domain": {
        "id": "131",
        "name": "Unified Twitter Taxonomy",
        "description": "A taxonomy of user interests. "
      },
      "entity": {
        "id": "1091420346660470784",
        "name": "Tech personalities",
        "description": "Tech Professionals"
      }
    },
    {
      "domain": {
        "id": "131",
        "name": "Unified Twitter Taxonomy",
        "description": "A taxonomy of user interests. "
      },
      "entity": {
        "id": "1166406108623163392",
        "name": "Business personalities"
      }
    }
  ],
  "lang": "en",
  "text": "Oh, you know, keeping busy … https://t.co/jgGYovK6jL",
  "edit_history_tweet_ids": [
    "1600439088560996353"
  ],
  "public_metrics": {
    "retweet_count": 5958,
    "reply_count": 6127,
    "like_count": 79683,
    "quote_count": 462
  },
  "attachments": {
    "media_keys": [
      "7_1600439072404619264"
    ]
  },
  "conversation_id": "1600439088560996353",
  "possibly_sensitive": false,
  "id": "1600439088560996353",
  "created_at": "2022-12-07T10:36:28.000Z",
  "source": "Twitter for iPhone"
}
```