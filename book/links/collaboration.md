# Collaboration

### Meaningful commit messages

This is a combination of

* Present-Tense Commit Messages
> Why?
> * Abundant letter prevention and
> * Prevention of grammar rules causing meaning obscurification.
```
// bad (are you done or not?)
git commit -m "had been fixing a bug causing product augmenter failure"
// better (if done)
git commit -m "fixes a bug causing product augmenter failure"
// better (if continuing)
git commit -m "fixes a bug causing product augmenter failure wip"
```
* Ticket IDs in branches and commit messages
> Why?
> * Easy to track updates and discussions over issues for all (non-technical) people
> * Better documentation showing procedures, requirements etc exists on issue tracker
```
// bad
git commit -m "fixes a bug causing product augmenter failure"
// better
git commit -m "SERVER-123 fixes a bug causing product augmenter failure"
```

* Semantic Commit Messages
> Why?
> easy to lookup and filter in (change\|git )log

```
// bad
git commit -m"fixed bug where product augmenter would crash on invalid product id"

// good
git commit -m"fix: SERVER-123 fixes bug where product augmenter would crash on invalid product id"
```

* [seesparkbox.com/foundry/semantic\_commit\_messages](https://seesparkbox.com/foundry/semantic_commit_messages)

###
