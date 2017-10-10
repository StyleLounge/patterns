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

### Don't get stuck refactoring the codebase while updating it

> * Why?
> * Refactoring takes time, usually more than estimated. While developing an update to the codebase, huge amount of refactoring will prevent you from (creating | publishing | deploying | saving the day).

###### IMPORTANT: This does not mean you should never refactor!
* You should be wary of your software engineer responsibilities and do it after what needs to be done is done.
* So make a memo, create a ticket or do whatever you can to remember to refactor the code.
* Perhaps code that needs to be refactored at first will then give birth to a brand new microservice :)
