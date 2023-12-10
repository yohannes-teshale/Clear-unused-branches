# Clear-unused-branches

This scripts clears branches that havent been pushed into for two weeks.

at the time being it only deletes branches from local, but thats only for testing purposes and will once stable enough it will be able to delete branches in remote repos too. 
removed branches names are stored in a file alongside thier last commit hashes so if just incase you remove an imoprtant branch you can recover it by using the `--show-history` command option.
The history uses fzf to add some interactivityy so you can select the branch you want and you'll be automatically checkedout there.
I actually planned to use sqlite to store the history (still might in the future) but it got overly complicated.

options:
  - --show-history: shows interactive history
  - --cear-history: clears history (not interactive)
  - -m : main branch
  - -r : remote repository

for yessi:

if you're interested in helping here are things you can do:
  - <del>fzf should be closed once user hits enter</del>
  - even though the program is configure to not delete main when fetching there an error that dispalys the following message: "main already exists" i dont like it.
  - <del>when retrieving deleted branch the program is supposed to checkout to a detached Head by checking out to the last commit of the deleted branch then create a   new branch with the same name as before. but the later is not working. </del>
  - add cron scheduling (never done one of these.)
  - getting rid of git logs (after it's done).
  - resolving naming clashes when recovering branches.
  - prompt before clearing history.
  - switch over to sqlite.
  - So I was thinking today that a dev is most likely to work on multiple repositories at a time. so switching over to each repo and trying to set this up would       behectic. solution? maybe user can provide a dir of thier workspace and the script would go through each dir and find all the .gitconfig files. from there the     script would be able to obtain informations such as name of the remote repo and main branch. But this would create another challenge, as of now delted     
    branches are stored in a single file. if multiple repos have the same branch name it would be confusing, Soln? create a sepatate flie for each repo or switch 
    to sqlite. What do you think yessi?
    


