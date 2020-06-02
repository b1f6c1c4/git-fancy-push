# `git-fancy-push`: "shallow update not allowed" _killer_

> The ULTIMATE solution towards "shallow update not allowed"
> when you are trying to do a git push

## TL;DR

:worried: :frowning: :anguished:
Ever seen this is your life? Got annoyed?
:anguished: :frowning: :worried:

And you don't want to download the 100GiB commit history for doing a simple push?
```bash
git push origin master
## To github.com:...
##  ! [remote rejected] master -> master (shallow update not allowed)
## error: failed to push some refs to 'git@github.com:...
```

:wink: :kissing_smiling_eyes: :stuck_out_tongue:
Here is your solution!
:stuck_out_tongue: :kissing_smiling_eyes: :wink:
```bash
# Get jq!
(which pacman  && sudo pacman  -S      jq) ||
(which apt-get && sudo apt-get install jq) ||
(which brew    &&      brew    install jq)
which jq
# Get git-fancy-push!
mkdir -p ~/.local/bin/ && curl -o ~/.local/bin/git-fancy-push https://raw.githubusercontent.com/b1f6c1c4/git-fancy-push/master/git-fancy-push
which git-fancy-push || export PATH="$HOME/.local/bin:$PATH"
# Do the push!
git fancy-push origin master
## ...
## Notice: Push successful! (to ...)
## ...
```

## Usage

The CLI is 100% compatible with that of `git push`.
You just replace `git push` with `git fancy-push`.
It will start running automatically once you encounter
a "shallow update not allowed" problem.

## Dependency

- `jq` - [here](https://stedolan.github.io/jq/)
- `bash`
- `git`
- `curl`
- `awk`

## Limitation

It will only work for GitHub.
If you want support for other platforms, create an issue or pull request.

## License

MIT
