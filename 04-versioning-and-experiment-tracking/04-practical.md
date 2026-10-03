# Data Version Control

Project link: [Wind-Prediction-Model](https://github.com/Adarsh097/Wine-Prediction-Model.git)

```
1. data is there in data/wine-sample.csv

2. git init -> Initialise the git repository

3. dvc init -> install it
    - python -m venv .venv -> create a virtual environment
    - source .venv/bin/activate
    - python -m pip install dvc
    - dvc init
4. dvc add data/wine_sample.csv
--
(.venv) (base) adarsh@adarsh:~/Wine-Prediction-Model$ ls data/
wine_sample.csv(S3-bucket) wine_sample.csv.dvc (file created)
--


5. (.venv) (base) adarsh@adarsh:~/Wine-Prediction-Model$ cat data/wine_sample.csv.dvc 

outs:
- md5: e7e9047980458dadce38426c09c9a5cf (unique checksum, stored on github)
  size: 323
  hash: md5
  path: wine_sample.csv

6. make some data change
7. dvc add data/wine_sample.csv


8. (.venv) (base) adarsh@adarsh:~/Wine-Prediction-Model$ cat data/wine_sample.csv.dvc 
outs:
- md5: ea689f221435d6f318d7944650dd718e (check will change)
  size: 353
  hash: md5
  path: wine_sample.csv

9. Pushing data files to AWS S3-bucket
    - create s3-bucket: adarsh-mlops-demo-dev-5559
    
10. (base) adarsh@adarsh:~/mlops-zero-to-hero$ aws configure
AWS Access Key ID [****************KM54]: 
AWS Secret Access Key [****************pcEZ]: 
Default region name [ap-south-1]: 
Default output format [json]: 

11. dvc remote add -d wineremote s3://adarsh-mlops-demo-dev-5559

12. dvc push
    - python -m pip install dvc_s3
    - dvc push

13. make small change in the data
    - dvc add data/wine_sample.csv
    - commit the change to github also
    - dvc push

14. Now, s3-bucket has new data file and github as new .dvc file.

15 cat .dvc/config -> contains the remote s3-bucket configurations


```