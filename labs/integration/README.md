# Your First CI Pipeline

## References

## Run the integration steps manually

git checkout main

cd app

./build.ps1

./run.ps1


## Rishi's bugfix

Create a new branch & make Rishi's change

git checkout -b rishi/bugfix-2

#TODO - UTF issue; mv?
cat hello-world-rishi.ps1 > hello-world.ps1

./build.ps1

./run.ps1

git commit -m "Rishi's bugfix"

git checkout main

git merge rishi/bugfix-2

git push

## Katherine's new feature


git checkout -b katherine/feature-2

#TODO - UTF issue; mv?
cat hello-world-katherine.ps1 > hello-world.ps1

./build.ps1

./run.ps1

git commit -m "Kat's new feature"

git push

> Fails "need to pull first"

git pull

> Now the merge conflict is the developer's problem :)

## Lab

What have we changed?

- dev responsibility to merge
- git enforces conflict mgmt

Have we fixed the problem?

- yes - reduced timeframe to find issue
- dev hits roadblock  encourages merge soon & often
- main branch is always releasable

> Stuck? Try [hints](hints.md) or check the [solution](solution.md).

___

## Cleanup