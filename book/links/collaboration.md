# Collaboration

### Semantic commit messages

Meaningful commit messages can be achieved in a number of way. This is just an example of what we found to be very useful.

* The message must say what the commit does, like "fixes bug where x happens" or "adds new icon to header".
* Every message must contain the corresponding issue id to make it simple to retrieve all commits for a ticket.
* It must use [semantic commit messages](http://seesparkbox.com/foundry/semantic_commit_messages)

> Why?
>
> * Consistency across all commit messages makes it easy to understand code evolution
> * Issue ids in all messages enforce working with issues and link commits to more comprehensive documentation in the issue tracker
> * Using present-tense is short, expressive and simple
> * Semantic commit messages allow automatic generation of changelogs

```
// bad
"fixed bug where product augmenter would crash on invalid product id"

// good
"fix: SERVER-123 fixes bug where an invalid product ids crashes augmenter"
```



