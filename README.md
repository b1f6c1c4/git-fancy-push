# `git-fancy-push`: "shallow update not allowed" _killer_

> The ULTIMATE solution towards "shallow update not allowed" during a git push

:worried: :frowning: :anguished:
Ever seen this is your life? Got annoyed?
:anguished: :frowning: :worried:

```bash
git push origin master
## To github.com:...
##  ! [remote rejected] master -> master (shallow update not allowed)
## error: failed to push some refs to 'git@github.com:...
```

:wink: :kissing_smiling_eyes: :stuck_out_tongue:
Here is your solution!
:stuck_out_tongue: :kissing_smiling_eyes: :wink:

(**Guranteed no hidden `--unshallow`. Instant upload to GitHub.**)

```bash
# Get jq
(which pacman  && sudo pacman  -S      jq) ||
(which apt-get && sudo apt-get install jq) ||
(which brew    &&      brew    install jq)
which jq
# Get git-fancy-push
mkdir -p ~/.local/bin/ && curl -o ~/.local/bin/git-fancy-push https://raw.githubusercontent.com/b1f6c1c4/git-fancy-push/master/git-fancy-push
which git-fancy-push || export PATH="$HOME/.local/bin:$PATH"
# Do the push
git fancy-push origin master
## ...
## Notice: Push successful! (to ...)
## ...
```

## Usage

The CLI is 100% compatible with that of `git push`. You just replace `git push` with `git fancy-push`.
Of course, you need to put the `git-fancy-push` script in your `PATH` some where.
It will start fixing the problem once you encounter a "shallow update not allowed" problem.

If you enounter problem, you can add `--verbose` as the _first_ argument for `git-fancy-push`, like this:
`git fancy-push --verbose origin master`

## Dependency

- `jq` - [here](https://stedolan.github.io/jq/)
- `bash`
- `git`
- `curl`
- `awk`

## Internals

`git-fancy-push` is based on GitHub v3 API.
It recursively reads the commits that are not yet on GitHub and upload it using GitHub API.

## Limitation

- It will only work for GitHub.
    Both `git@github.com:` or `https://github.com/` will work.
    It won't work for `file://`, GitLab, BitBucket, etc.
    If you want support for other platforms, create an issue or pull request.
- It will fail on commits with a `mergetag` header, which will be added by newer versions of Git
    during merging a signed annotated tag.

## License

MIT
