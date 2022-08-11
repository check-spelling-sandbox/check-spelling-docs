# Behavior change: case changes in expect

Right now if a user has an item `FILETYPE` in `expect.txt` and adds `filetype` into the corpus, then check spelling will generate:

## Current output
Unrecognized words (1)
filetype


<details><summary>Previously acknowledged words that are now absent</summary>

FILETYPE
</details>

## Proposed change

The UI should at least clearly draw attention to this change, because it's confusing.
