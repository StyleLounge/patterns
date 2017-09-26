# Collaboration

### Meaningful commit messages

This is a combination of

* Present-Tense Commit Messages, the sentence should sound like the whole sentence started with "This commit will "
* Ticket IDs in branches and commit messages
* Semantic Commit Messages

> * Why?
> * Present-Tense Commit Messages makes the message easier to read and understand for team mates
> * Having ticket numbers in commit message and branch name will make it easier to find the relevant ticket for more information
> * Following the same logical structure enables the reader to find relevant parts faster and easier

```
// bad
git commit -m "fixed bug where product augmenter would crash on invalid product id"

// good
git commit -m "fix: SERVER-123 fix bug where product augmenter would crash on invalid product id"
```

* [seesparkbox.com/foundry/semantic\_commit\_messages](https://seesparkbox.com/foundry/semantic_commit_messages)

###
