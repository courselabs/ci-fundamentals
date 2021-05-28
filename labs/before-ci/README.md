#

## References

> prep

- add ps1
- commit 
- tag `git tag release/25.06`
- `git checkout -b rishi-bugfix`
- fix case & commit
- `git checkout main`; `git checkout -b katherine-feature`
- add variable & commit


## 1 - Run the demo app

This app couldn't be simpler - it's a script which prints _Hello world_. 

Thanks to some careful coding, it works with PowerShell on Windows and on a Linux shell. 

First you need to make the script runnable:

_On Windows:_

```
TODO
```
_On Linux/Mac (may ask for your password):_

```
chmod +x ./app/*.ps1
```

_Now run the app:_

```
./app/hello-world.ps1
```

There are two other branches with changes to the app. Rishi has been working on a bugfix, and Katherine has added a new feature.

📋 List the branches to see what we're working with.

<details>
  <summary>Not sure how?</summary>

git branch

> We have `rishi-bugfix` and `katherine-feature` which look good.

</details><br/>

## Merge in both sets of changes

You're the release manager and you need to build a new version of the app with both changes.

There's no CI so this is a manual process, you need to:

- add Rishi's bug fix to the `main` branch
- add Katherine's new feature to the `main` branch

It's been months since the last release, so the merge might not go well.

📋 Try to merge both sets of changes.

<details>
  <summary>Not sure how?</summary>

You can do the merging in any order - it will fail both ways :)

```
# make sure you're on main
git checkout main 

# merge in the bugfix
git merge rishi-bugfix

# and the new feature
git merge katherine-feature
```

</details><br/>

> You'll get an error when you try the second merge:

```
Auto-merging app/hello-world.ps1
CONFLICT (content): Merge conflict in app/hello-world.ps1
Automatic merge failed; fix conflicts and then commit the result.
```

Both developers have changed the same file and their changes are in conflict.

## We can't release this

We'll need to get the devs to sort this out. Right now `main` is broken on the release machine, so we'd better revert the changes.

A Git reset should do it:

```
git reset --hard
```

> Ah. That only takes us so far.

Luckily we've tagged the last release, so we can revert back to a good version. 

📋 Find the release tag and reset.

<details>
  <summary>Not sure how?</summary>

You can do the merging in any order - it will fail both ways :)

```
# list the tags
git tag

# reset to the latest release tag:
git reset --hard release/25.06
```

</details><br/>

## Lab

How did we get into this state? How can we prevent it happening again?

This lab is a thinking exercise

- timing
- feedback
- enforcement



> Stuck? Try [hints](hints.md) or check the [solution](solution.md).

___

## Cleanup