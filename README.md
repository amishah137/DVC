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
