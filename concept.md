So, here's the concept for how I'm planning on porting over LMD to JS:

## Basic Idea
1. I'm going to leverage [mustache](http://mustache.github.io) to handle:
  a. mixins
  b. partials
1. To handle structured levels, I'm going to leverage the concept of the [dc-code-prototype model](https://github.com/joshdata/dc-code-prototype) and do the following:
  a. Go through each line of text.
  b. Assign the line to a JSON object, where sub-levels are nested arrays of objects.
  c. At the same level, you iterate.
  c. This will make for powerful cross-reference and structure.

## How it might work

> {"document":[{"id":"1","level":"0","num":"","heading":"","text":"Lorem ipsum","children":null},{"id":"2", "level":"1","num":"I","heading":"Level Heading 1", "text":"Testing of the level heading 1","children":[{"id":"3", "level":"2","num":A","heading":"Level Heading 2","text":"This would be a sub-level of level I","children":null},{"id":"3", "level":"2","num":B","heading":"Second Sublevel Heading","text":"This would also be a sub-level of level I","children":null}]}
