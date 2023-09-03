# DVC

### Steps to follow:
  1. Create a folder mlops/DVCDemo
     ```
     mkdir mlops/DVCDemo
     ```
  2. Create a new environment
     ```
     conda create -p mlops python==3.9 -y
     ```
  3. Create a file .gitignore
  4. Install DVC into the environment 'mlops'
     ```
     pip3 install dvc
     ```
  5. Initialize the dvc
     ```
     dvc init
     ```
  6. Commit the changes to git
     ```
     git status
     ```
     ```
     git commit -m "DVC init"
     ```
  7. create a data folder and keep data file 'data.txt' inside
     ```
     mkdir data && cd data
     ```
     ```
     nano data.txt
     ```
     Put contests
     ```
     First version of Data.
     ```
  8. DVC to track the data file data.txt
     ```
     dvc add data/data.txt
     ```
  9. The two files created by dvc to be tracked by git
     ```
     git add data/.gitignore
     ```
     ```
     git add data/data.txt.dvc
     ```
  10. Now, Edit the contents of data.txt
     ```
     First version of Data.
     Second version of Data.
     ```
  11. commit file data.txt to dvc for tracking again.
     ```
     dvc add data/data.txt
     ```
  12. The file modified by dvc to be tracked by git
     ```
     git add data/data.txt.dvc
     ```
  13. commit the changes to git
     ```
     git commit -m "DVC"
     ```
  14. Now, again Edit the contents of data.txt
     ```
     First version of Data.
     Second version of Data.
     Third version
     ```
  15. commit file data.txt to dvc for tracking again.
      ```
      dvc add data/data.txt
      ```
  16. The file modified by dvc to be tracked by git
      ```
      git add data/data.txt.dvc
      ```
  17. commit the changes to git
      ```
      git commit -m "DVC_2"
      ```
  18. check the git log
      ```
      git log
      ```
      Copy the commit-id of 'DVC'
  19. Now, switch git branch to 'DVC'
      ```
      git checkout {commit-id}
      ```
  20. update the contents of data.txt as with 'DVC' commit
      ```
      dvc checkout
      ``` 
  21. 


### Using Google Storage as remote repo to store data

  1. Create a folder mlops/DVCDemo
     ```
     mkdir mlops/dvcDemo && cd dvcDemo
     ```
  2. Create a new environment
     ```
     conda create -p mlops python==3.9 -y
     conda activate mlops
     ```
  3. Install dvc into the environment 'mlops'
     ```
     pip3 install dvc
     ```
  4. Initialize git
     ```
     git init
     ```
  5. Initialize the dvc
     ```
     dvc init
     ```
     Now, check newly created files
     ```
     git status
     ```
  6. Add these files to staging area and commit the changes
     ```
     git add --all
     ```
     ```
     git commit -m 'Initial Commit'
     ```
  7. Change the default branch to master branch
     ```
     git branch -M main
     ```
  8. Add remote repo
     ```
     git remote add origin https://github.com/amishah137/dvcDemo.git
     ```
     Check the remote repo
     ```
     git remote -v
     ```
  9. Now push contents
     ```
     git push -u origin main
     ```
  10. Add remote GS bucket
     ```
     dvc remote add -d gs_remote gs://dvc_project 
     ```
     Note: Use command to autheticate
     ```
     gcloud auth login
     ```
     Check contents of the bucket
     ```
     gsutils ls gs://dvc_project
     ```
  11. Put the data file 'data.csv' in the folder.
  12. Git contents are not changed
     ```
     git status
     ```
     dvc contents are changed
     ```
     dvc status
     ```
  13. Add data file to dvc to track
     ```
     dvc add data.csv
     ```
  14. Push data to remote repo
      ```
      dvc push
      ```
  15. Add the changes to staging area for git
      ```
      git add --all
      ```
  16. Commit the changes
      ```
      git commit -m "first_ver"
      ```
  17. Add tag to the commit
      ```
      git tag v1.0
      ```
  18.Push the changes to remote repo for Git
      ```
      git push -u origin main
      ```
  19. push the tag
      ```
      git push --tag
      ```
  20. Modify the data.csv
  21. Repeat steps 12 - 19.
  22. Switch to v1.0
      ```
      git checkout v1.0
      ```
  23. pull the data with v1.0
      ```
      dvc pull
      ```
      you can see old data in the data.csv file




