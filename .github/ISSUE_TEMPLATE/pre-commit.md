---
name: pre-commit
about: donot commit direct to master

---

#!usr/bin/bash

BRANCH=`git rev-parse --abbrev-ref HEAD`

if [[ "$BRANCH" == "master"  ]]; then
  echo "You are on branch $BRANCH. Are you sure you want to commit to this branch?"
  echo "If so, commit with -n to bypass this pre-commit hook."
  exit 1
fi
