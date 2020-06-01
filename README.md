# `git-fancy-push`: "shallow update not allowed" _killer_

> The ULTIMATE solution towards "shallow update not allowed"
> when you are trying to do a git push

## TL;DR

```bash
# Get the code!
git get -o ~/.local/bin/ b1f6c1c4/git-fancy-push -- git-fancy-push
# Go push!
git fancy-push [<options>] [<remote>] [<refspec>...]
# Optionally, use fancy-push by default!
git config --global alias.push fancy-push
```

## Usage

The CLI is 100% compatible with that of `git push`.

## Dependency

- `bash`
- `git`
- `curl`

## Limitation

It will only work for GitHub.
If you want support for other platforms, create issues or pull requests.

## License

MIT
