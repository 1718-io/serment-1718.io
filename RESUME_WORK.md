# The 1718 French Oath

This markdown file is a utility I use to quickly resume work on my last task, on this repo.

Change this for your own needs when you fork this repo.

# To (re-init) work

* create an empty github.com/gitlab.com repo,
* git clone it into local `~/gravitee-circleci-orbinoid` folder (change that folder path to wherever you want on your machine), and launch atom in this folder `atom ~/gravitee-circleci-orbinoid`
* Add this `README.md`
* then run copy/paster :

```bash

git config --global commit.gpgsign true
git config --global user.name "Jean-Baptiste-Lasselle"
git config --global user.email jean.baptiste.lasselle.pegasus@gmail.com
git config --global user.signingkey 7B19A8E1574C2883

git config --global --list

# will re-define the default identity in use
# https://docstore.mik.ua/orelly/networking_2ndEd/ssh/ch06_04.htm
ssh-add ~/.ssh.perso.backed/id_rsa

export GIT_SSH_COMMAND='ssh -i ~/.ssh.perso.backed/id_rsa'
ssh -Ti ~/.ssh.perso.backed/id_rsa git@github.com


export LOCAL_WORKSPACE=~/serment1718
# git clone git@github.com:1718-io/serment-1718.io.git ${LOCAL_WORKSPACE}
cd ${LOCAL_WORKSPACE}
git remote add origin git@github.com:1718-io/serment-1718.io.git ${LOCAL_WORKSPACE}
atom .
export FEATURE_ALIAS="premiere_redaction"
export COMMIT_MESSAGE="feat.(${FEATURE_ALIAS}): j'ajoute la rédaction de la génèse de l'idée dans [README.md]"
# Fuuuck, they at microsoft modified default branch name from 'master' to 'main', those f***cking morons
git add --all && git commit -m "${COMMIT_MESSAGE}" && git push -u origin master
# git add --all && git commit --amend -m "${COMMIT_MESSAGE}" && git push -ff -u origin HEAD
git flow init --defaults
git push -u origin --all

```

# To resume work

* copy/paster :

```bash

git config --global commit.gpgsign true
git config --global user.name "Jean-Baptiste-Lasselle"
git config --global user.email jean.baptiste.lasselle.pegasus@gmail.com
git config --global user.signingkey 7B19A8E1574C2883

git config --global --list

# will re-define the default identity in use
# https://docstore.mik.ua/orelly/networking_2ndEd/ssh/ch06_04.htm
ssh-add ~/.ssh.perso.backed/id_rsa

export GIT_SSH_COMMAND='ssh -i ~/.ssh.perso.backed/id_rsa'
ssh -Ti ~/.ssh.perso.backed/id_rsa git@github.com


export LOCAL_WORKSPACE=~/gravitee-circleci-orbinoid
cd ${LOCAL_WORKSPACE}
atom .
export FEATURE_ALIAS="orbinoid_init"
export FEATURE_ALIAS="premiere_redaction"
export COMMIT_MESSAGE="feat.(${FEATURE_ALIAS}): j'ajoute la rédaction de l'idée dans [README.md]"
export COMMIT_MESSAGE="feat.(${FEATURE_ALIAS}): j'ajoute un montage docker-compose hugo avec Hugo / RevealJS pour faire un powerpoint [docs]"
export COMMIT_MESSAGE="feat.(${FEATURE_ALIAS}): je transfère la rédaction de la génèse de l'idée et de l'idée elle-même du [README.md] vers le power-point  HUGO/RevealJS"

# git flow init --defaults
# git flow feature start "${FEATURE_ALIAS}"
# git add --all && git commit -m "${COMMIT_MESSAGE}" && git push -u origin HEAD
# git add --all && git commit --amend -m "${COMMIT_MESSAGE}" && git push -ff -u origin HEAD

```
