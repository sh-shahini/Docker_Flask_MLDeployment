# Docker_Flask_MLDeployment

## Containerize ML-Model-Flask-app using Docker
The ML model was depolyed using flask api and then containerized with Docker.

### Prerequisites
You must have Scikit Learn, Pandas (for Machine Leraning Model) ,Flask (for API), virtual environment and docker installed.

### Project Structure
This project has four major parts :
1. model.py - This contains code for our Machine Learning model to predict employee salaries absed on trainign data in 'hiring.csv' file.
2. app.py - This contains Flask APIs that receives employee details through GUI or API calls, computes the precited value based on our model and returns it.
3. templates - This folder contains the HTML template to allow user to enter employee detail and displays the predicted employee salary.
4. This step contains building an image and containerizing the flask api. 


### Running the project
1. Ensure that you are in the project home directory. Create the machine learning model by running below command -
```
python model.py
```
This would create a serialized version of our model into a file model.pkl

2. Run app.py using below command to start Flask API
```
python app.py
```
By default, flask will run on port 5000.

3. Navigate to URL http://localhost:5000

You should be able to view the homepage as below :
![alt text](http://www.thepythonblog.com/wp-content/uploads/2019/02/Homepage.png)

Enter valid numerical values in all 3 input boxes and hit Predict.

If everything goes well, you should  be able to see the predcited salary vaule on the HTML page!
![alt text](http://www.thepythonblog.com/wp-content/uploads/2019/02/Result.png)

4. Create a Dockerfile and package dependancies file (requirements.txt)

5. Build the image using this command:  
```
docker build -t <nameofImage:Tag> . 
```
6. Confirm the successful creation of image by running $docker images.

7. Now, run the image to create a container by this command: ~$ 
 ```
docker run -it -d p5000:5000 <nameofImage> 
``` 
