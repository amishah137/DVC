# DVC
### Let's start dvc with local repository.
#### Steps to follow:
  1. Create a folder dvcdemo
     ```
     mkdir dvcdemo && cd dvcdemo
     ```
  2. Create a new environment
     ```
     conda create -p mlops python==3.9 -y
     ```
     ```
     conda activate mlops
     ```
  3. Install dvc into the environment 'mlops'
     ```
     pip3 install dvc
     ```
  4. Create a folder dvc inside dvcdemo.
     ```
     mkdir dvc && cd dvc
     ```
  5. Initialize git
     ```
     git init
     ```
  6. Initialize dvc
     ```
     dvc init
     ```
     This command creates three files.
  7. Commit the changes to git
     ```
     git status
     ```
     ```
     git commit -m "dvc_init"
     ```
  8. Create a file 'data.csv' and put contents inside and save it.
     ```
     nano data.csv
     ```
     ```
     1,Ami,MLE
     2,Shubham,DS
     3,Purav,MLE
     ```
  9. DVC to track the data file data.txt
     ```
     dvc add data.csv
     ```
  10. The two files created by dvc to be tracked by git
      ```
      git add .gitignore
      ```
      ```
      git add data.csv.dvc
      ```
  12. Commit the changes to git
      ```
      git commit -m "dvc_first_ver_db"
      ```
  13. Now, Edit the contents of data.csv
      ```
      1,Ami,MLE
      2,Shubham,DS
      3,Purav,MLE
      4,Pramod,DevOps
      5,Nukul,LLM
      ```
  14. Again, DVC to track the data file data.csv
      ```
      dvc add data.csv
      ```
  15. Again, The one file modified by dvc to be tracked by git
      ```
      git add data.csv.dvc
      ```
  16. Again, commit the changes to git
      ```
      git commit -m "dvc_second_ver_db"
      ```
  17. Check the git log
      ```
      git log
      ```
      Copy the SHA-id of 'DVC' and press ':q' to exit 'git log'
  18. Now, switch to git branch 'DVC'
      ```
      git checkout {SHA-id}
      ```
  19. Update the contents of data.csv as with 'DVC' commit
      ```
      dvc checkout
      ```
      You can see old data in file data.csv
  20. Now, checkout to last branch
      ```
      git checkout master
      ```
  21. Now, pull last updated data.
      ```
      dvc checkout
      ```
  22. Now, you can go back forth between data versions.

#### After steps
1. deactivate conda environment
   ```
   conda deactivate
   ```
2. Remove the environment
   ```
   conda remove --name mlops --all
   ```
3. Remove dvcdemo folder

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
  18. Push the changes to remote repo for Git
      ```
      git push -u origin main
      ```
  19. push the tag
      ```
      git push --tag
      ```
  20. Modify the data.csv
  21. Repeat steps 12 - 19
  22. Switch to v1.0
      ```
      git checkout v1.0
      ```
  23.  pull the data with v1.0
      ```
      dvc pull
      ```
      you can see old data in the data.csv file 
  24. 





