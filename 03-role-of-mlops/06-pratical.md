# Using the IRIS Dataset

- Project Github Repo: [hello-world-mlops](https://github.com/Adarsh097/hello-world-mlops)

```
1. python -> start python terminal

2. from sklearn.datasets import load_iris -> load the iris dataset

3. import pandas as pd

4. iris = load_iris()

5. df = pd.DataFrame(iris.data,columns=iris.feature_names)

6. print("\nTarget names: ",iris.target_names)

7. unsertand train.py -> to see how the model is built.

8. python -m venv .venv -> creat a virtual environment
9. source .venv/bin/activate
10. which python -> to verify the virtual environment

11. python -m pip install -r requirements.txt -> install the project dependencies

12. python train.py -> trian the model and see the efficiency

13. ls artifacts -> to see the model.pkl and metrics.json

14. vim run_model.py -> to run/evaluate the model

15. python run_model.py --input "[10,1,5,10]" -> to test the prediction


17. Understand the github-action CI-workflow -> push the changes to start the workflow and run the pipeline


18. Understand the API developement for the model

19. curl -X POST "http://127.0.0.1:5001/predict" -H "Content-Type: application/json" -d '{"features":[5.1,3.5,1.4,0.2]}' -> Test the application


20. Create Dockerfile -> containerize the app
21. docker build -t mlops-model:latest .
22. docker images
23. docker run -d -p 5001:5001 mlops-model:latest
24. docker ps -> container will start running
25. curl -X POST "http://127.0.0.1:5001/predict" -H "Content-Type: application/json" -d '{"features":[5.1,3.5,1.4,0.2]}' 




```