git init
git branch -M main
git remote add origin https://github.com/25101997/library-system.git
git add .
git commit -m "first commit"
git push -u origin main

git branch

git checkout -b dev
git push -u origin dev

git checkout dev
git pull origin dev
git add .
git commit -m "Added new edits"
git push origin dev


git checkout main
git pull origin main
git merge dev
git push origin main