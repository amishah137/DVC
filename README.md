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
  9. DVC to track the data file data.txt
     ```
     dvc add data/data.txt
     ```
  11. The two files created by dvc to be tracked by git
      ```
      git add data/.gitignore
      ```
      ```
      git add data/data.txt.dvc
      ```
  12. Now, Edit the contents of data.txt
      ```
      First version of Data.
      Second version of Data.
      ```
  14. commit file data.txt to dvc for tracking again.
      ```
      dvc add data/data.txt
      ```
  15. The file modified by dvc to be tracked by git
      ```
      git add data/data.txt.dvc
      ```
  16. commit the changes to git
      ```
      git commit -m "DVC"
      ```
  18. Now, again Edit the contents of data.txt
      ```
      First version of Data.
      Second version of Data.
      Third version
      ```
  14. commit file data.txt to dvc for tracking again.
      ```
      dvc add data/data.txt
      ```
  15. The file modified by dvc to be tracked by git
      ```
      git add data/data.txt.dvc
      ```
  16. commit the changes to git
      ```
      git commit -m "DVC_2"
      ```
  17. check the git log
      ```
      git log
      ```
      Copy the commit-id of 'DVC'
  18. Now, switch git branch to 'DVC'
      ```
      git checkout {commit-id}
      ```
  19. update the contents of data.txt as with 'DVC' commit
      ```
      dvc checkout
      ```
  20. 
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
  7. Add these files to staging area and commit the changes
     ```
     git add --all
     ```
     ```
     git commit -m 'Initial Commit'
     ```
  8. Change the default branch to master branch
     ```
     git branch -M main
     ```
  9. Add remote repo
    ```
    git remote add origin https://github.com/amishah137/dvcDemo.git
    ```
    ```
    Check the remote repo
    ```
    ```
    git remote -v
    ```
  11. Now push contents
     ```
     git push -u origin main
     ```
  12. Add remote GS bucket
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
  13. Put the data file 'data.csv' in the folder.
  14. Git contents are not changed
     ```
     git status
     ```
     dvc contents are changed
     ```
     dvc status
     ```
  15. Add data file to dvc to track
     ```
     dvc add data.csv
     ```
  16. Push data to remote repo
      ```
      dvc push
      ```
  17. Add the changes to staging area for git
      ```
      git add --all
      ```
  18. Commit the changes
      ```
      git commit -m "first_ver"
      ```
  19. Add tag to the commit
      ```
      git tag v1.0
      ```
  19.Push the changes to remote repo for Git
      ```
      git push -u origin main
      ```
  20. push the tag
      ```
      git push --tag
      ```
  21. Modify the data.csv
  22. Repeat steps 13 - 20.
  23. Switch to v1.0
      ```
      git checkout v1.0
      ```
  24. pull the data with v1.0
      ```
      dvc pull
      ```
      you can see old data in the data.csv file




