# searching unordered words on a phrase with amazon open search

I'm having a lot of problems to achieve this goal, I basically ran into a
"stable" release for the phrase searches with unordered words. But the results
tend to be a lot specially with Italian articles like `nel`

For example If I input `vomito nel sangue` the results will be:

- `Sangue nel vomito` 
- `Chetoni nel sangue` 
- `Vomito` 
- `Sangue` 
- `Massa nel seno` 
- `Perdite nel periodo intermestruale` 
- `Bruciore nel fare pipi` 
- `Sangue dalla vagina` 
- `Urine color sangue` 
- `Contatto con sangue`

Because of the `nel` article, this search becomes so huge and this is pissing
me off

One idea I could not test it already is this:

[](https://stackoverflow.com/questions/47399956/how-to-handle-unordered-multi-word-query-in-elasticsearch)

This edge ngram apparently serve well our use case because it can match
unordered words pretty well, the syntax to declare it on open search is

> Disclaimer: This completion don't accept grammatical errors like the fuzzy
one does

1. To declare the analyzer under a particular index

```
PUT testando
{
  "mappings": {
    "properties": {
      "text_entry": {
        "type": "text",
        "analyzer": "autocomplete",
        "search_analyzer": "autocomplete_search"
      }
    }
  },
  "settings": {
    "analysis": {
      "analyzer": {
        "autocomplete": {
          "tokenizer": "autocomplete",
          "filter": [
            "lowercase"
          ]
        },
        "autocomplete_search": {
          "tokenizer": "lowercase"
        }
      },
      "tokenizer": {
        "autocomplete": {
          "type": "edge_ngram",
          "min_gram": 1,
          "max_gram": 10,
          "token_chars": [
            "letter"
            ]
        }
      }
    }
  }
}
```

2. To register a new entry under this index

```
POST testando/_bulk
{ "create": { "_index": "testando", "_type": "_doc" } }
{ "text_entry": "Primo grado" }
```

3. Perform search

```
GET testando/_search
{
  "query": {
    "match": {
      "text_entry": {
        "query": "vomi san nel",
        "operator": "and"
      }
    }
  }
}
```
