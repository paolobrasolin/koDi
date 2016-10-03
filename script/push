#!/usr/bin/env bash

SOURCE_BRANCH="nanoc"
TARGET_BRANCH="gh-pages"

# Save some useful information
REPO=`git config remote.origin.url`
SSH_REPO=${REPO/https:\/\/github.com\//git@github.com:}
SHA=`git rev-parse --verify HEAD`

# Now let's go have some fun with the cloned repo
cd output
git config user.name "Travis CI"
# git config user.email "$COMMIT_AUTHOR_EMAIL"
git config user.email "paolo.brasolin@gmail.com"
# git config user.name "Paolo Brasolin"

# If there are no changes to the compiled out (e.g. this is a README update) then just bail.
# if [ -z `git diff --exit-code` ]; then
    # echo "No changes to the output on this push; exiting."
    # exit 0
# fi

# Commit the "changes", i.e. the new version.
# The delta will show diffs between new and old versions.
git add -A
git commit -m "Deploy to GitHub Pages: ${SHA}"
# git commit -a -m "Travis #$TRAVIS_BUILD_NUMBER"

# Now that we're all set up, we can push.
git push $SSH_REPO $TARGET_BRANCH
