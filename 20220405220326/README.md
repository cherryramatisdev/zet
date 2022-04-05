# searching unordered words on a phrase with amazon open search

I'm having a lot of problems to achieve this goal, I basically ran into
a "stable" release for the phrase searches with unordered words But the results
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

I could not finish this because open search syntax is a little different on
this particular aspect(a piece of shit right)

So right now I'm discovering what to do with this edge n-gram tokeniser that
elastic search provides and *apparently* open search too, but the syntax
appears to be different on the studio.
