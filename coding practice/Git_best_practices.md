
Demonstration of git ##branching and git ##pull best practices (to avoid merge conflicts)
A new blank repo was already created on github website


cd Documets
mkdir pathnex #created a new folder on PC
cd pathnex
ls -la

git status
git init
git status
git add .
git status check
git commit -m "first commit" #commited the new created folder to the repo
git status
git log
git branch -M main
git remote add origin https://github.com/VasuGargDev/MCB_FullStack.git #HTTPS link from repo’s quick setup page
git push -u origin main #pushed the changes



#for new branch
git checkout -b <new branch name> #make a new branch and jump to it 

git push -u origin <branch name>  #(origin) uploads your new branch to GitHub remote repo, now others can see it as well
                                                               #(-u) sets upstream tracking, in other words links your local branch to the remote branch


#(made changes to the new test branch — Eg:created a readme.md file manually)

git status  #(red)
git add  .      #(staged changes for commit)
git status  #(green)
git commit -m "added readme"
git status   
git push

(Now we will create a PR using GitHub desktop app or website, and wait for it to be merged by the reviewers/collaborators) 

git checkout main #jump back to our main branch 

#once our PR (changes) are merged into the main branch, we will be able to get the changes in our code using git pull
git pull 







TRIVIA:
{{
After:
git checkout -b <branch name> 

Can I just use: 
git push 
git pull 

 instead of: 
git push -u origin <branch-name>

Answer: No, not the first time. Because your branch exists only locally and has no upstream (tracking) branch set.

But afterwards we can simply use
git push
git pull
}}








#Best practice (how and when) to use "git pull" to make sure I have updated codebase before I start making any changes

Always sync before you start working
Pull from the correct branch (usually main)
Avoid blind git pull ❌ (blindly on feature branch)
git checkout main
git pull origin main
git checkout <new branch name>
git merge main

OR using rebase instead of merge:
git checkout feature/my-task
git fetch origin
git rebase origin/main
What this does:
Replays your changes on top of latest main
Keeps history clean and linear

Summary:-
pull = fetch + merge (automatic, sometimes messy)
fetch = safe preview
rebase = clean history
merge = safe but adds commits





MISC:


Create a new repo on the command line…code from Quick Setup page (adding readme and first commit from cmd)

echo "# JS-101" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/VasuGargDev/JS-101.git
git push -u origin main

(to pull changes from main branch to develop branch)
git pull origin main



Also learn to git clone any existing repository to local #git clone 
Create and merge PR from command line?

