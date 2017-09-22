# My *frecklets*


This repository contains a collections of Ansible roles, freckles adapters as well as frecklecutables (frecklets?) I commonly use, or work on at the moment.

It's organized as a git repository that includes a [git subtree](https://github.com/git/git/blob/master/contrib/subtree/git-subtree.txt) per 'frecklet'.

To add a new (Ansible) role, I choose an appropriate location (need to think of a formal structure for repos like this that makes sense at some point), then I do:

```
git subtree add --prefix <path_to_frecklet> <role_url> master --squash
```

It's best to make the target folder named the same as the (Ansible galaxy) role name, even if the original repository is called differently. This makes it more likely *freckles* will pick it up correctly later on.

So, as an example, for adding the role I wrote for setting up a [grav](https://getgrav.org) environment, I did (in the root of this repo):
```
git subtree add --prefix web/cms/grav/makkus.grav https://github.com/makkus/grav_ansible.git master --squash
```

Now, in this example, if I want to merge changes from the original url, I do:
```
git subtree pull --prefix web/cms/grav/makkus.grav https://github.com/makkus/grav_ansible.git master --squash
```
