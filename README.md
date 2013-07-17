GithubBashScripts
=================

Bash scripts to simplify and wrap up a bunch of commands at once to quickly create, update, push, and finish/delete branches. Keywords: git, github, pivotal tracker, productivity, bash, unix, shell

Check them out, they're not totally idiot-proof, but I put in some comments in there, as well as a few aliases to make things easy to use. 

When you unzip it, it's a folder with a period at the beginning to make it a hidden folder on unix systems. Inside is an aliases.sh which is basically the README as well. Some examples of usages:

####Create Branch
    cb 5129384 menuAnimations
* Creates a branch named "menuAnimations/5129384" where the number is a pivotaltracker id number, then pushes it to github and sets upstream tracking

####Update Branch
    ub menuAnimations/5129384 [otherbranchname]
* Second param is optional, will default to development branch
* Checks out the other branch, updates it by doing a pull, then does a rebase on your story branch so your branch has the latest updates from the other branch if any

####Reset Branch
    rb
* If you royally eff up your local repo and need to reset it

####Push Branch
    pb "some sort of commit message"
* Adds all changes in your directory and subdirectories, commits them with the message, and pushes the changes to the remote repo

####Finish Branch
    fb [-d] menuAnimations/5129384 [otherbranchname]
* Optional flag to delete the branch after merging, second param is optional and will default to development
* This updates the other branch, then merges your story branch with the other branch, posts a commit message that parses out the pivotal number and formats it so the jenkins hook will fire and pivotal will update the story automatically, and finally pushes the changes and initiates deletion of branches if set.
