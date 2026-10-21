# Git Workflow

_Notice: migration is ongoing. We currently host some repos on GitHub, others
are self-hosted. This document describes our goal with git workflow, while the
actual migration is going to happen for the next couple of years._

## Why not GitHub, Codeberg, etc.?

Code itself is not a contribution. Code is a liability. GitHub is filled with
AI-slop that we don't really need in our projects. But we do need long-term
contributors, people who will drive vision of this project, etc.

Codeberg, Tangled and others are a better place to be for sure. But what all
these git hostings provide is a _social network_ in the first place. Pull
Requests, Issues, Discussions, Wikis, etc. It is a place for human interactions
about software.

## Domains

What any git hosting needs is:

* Git itself, ability to invoke `git clone`, `git pull`, `git push`, etc.
* Code browsing capabilities for people to check sources without downloading
* Code submitting capabilities to send patches
* A bunch of social features to talk about project itself

But Friendly itself is a place to talk about Friendly! So here is the matrix of
technologies we use to develop Friendly:

| Domain          | Solution                                               |
| --------------- | ------------------------------------------------------ |
| Git             | Plain SSH via git user                                 |
| Code Browsing   | CGit at [git.getfriend.ly](https://git.getfriend.ly)   |
| Code Submitting | Patchbin at [pr.getfriend.ly](https://pr.getfriend.ly) |
| Social          | A circle within Friendly itself!                       |

## Cloning

You can clone any repo under [git.getfriend.ly](https://git.getfriend.ly) using
this command:

```sh
git clone https://git.getfriend.ly/{repo}
```

## Sending patches

If you are an outside collaborator, we have a patchbin instance hosted at
[pr.getfriend.ly](https://pr.getfriend.ly). To create a patch link, use:

```sh
git format-patch main --stdout | ssh pr.getfriend.ly {repo}
```

You need to have SSH key set up to do that. It will be used to check permissions
to update/delete patchset.

## Pushing

To push, your ssh key must be added to git user with the respective permissions
set up. Then, you can do:

```sh
git remote add origin git@ssh.getfriend.ly
```

After that, push works as usual:

```sh
git push
```

---

Internal development communication happens within Friendly itself, and you can
get there either via social graph and builtin Friendly features, or via invite
after contacting @y9san9 via [friendly@y9san9.me](mailto:friendly@y9san9.me)
