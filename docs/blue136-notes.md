# Releasing Software

## What?

* Snapshot of the software

  - Software release is a process which produces a snapshot.
  - Known good state.
  - Should be done every Sprint in which the software was modified.
  - Includes changes to documentation.
  - Update CHANGELOG, README, LICENSE.

* Tested

  - Unit tests.
  - Automated tests.
  - Manually if necessary.

* Tagged

  - Easy reference.
  - Semantic versioning (Major.Minor.Patch) all about backwards-compatibility.
      - Was an existing feature buggy and fixed? +Patch
      - Unless a new feature added? +Minor
      - Modify the existing API? +Major
  - Major bumps are more frequent than developers will admit, but it could also
    be a sign of sloppy/cowboy programming.


## Who?

Every developer should understand the process.


## Why?

It helps the rest of the software development process, especially deployment.

- Also, bug reporting and debugging.

Release != Deployment

- Really emphasize the distinction between release and deployment.
- Deployment my involve upgrading to a new release, or a new setup entirely.
- Configuration may vary for same release.


## Where?

Right from your command line.


## How?

    $ git flow release start 2.0.0

* After adding a feature:
    git checkout develop
    git pull
    git checkout -b release/2.0.0
    edit CHANGELOG.md
    git commit CHANGELOG.md
    git push
    git checkout master
    git merge --no-ff release/2.0.0
    git tag -a 2.0.0
    git checkout develop
    git merege --no-ff release/2.0.0
    git branch -d release/2.0.0
    git push
    git push --tags

## Credits


