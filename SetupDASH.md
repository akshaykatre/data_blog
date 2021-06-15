# Building a web-based application in 15 minutes 

Recently I came across a situation where I wanted to share a dashboard with 
someone but they did not have the same setup/ knowledge of setting up the
dashbaord. 

I wanted to let the user have access to the dashboard at any point in time. 
This way, if they wanted to cross-verify some details, they could do this 
instantly. 

In this document, I will mention how to build a simple web application
using DASH:   
1. Locally on your own machine 
2. Hosted on Heroku

## Enter DASH

DASH is a platform for setting up low-code ML & data science applications 
on your web browser. For more details you can visit: [dash's main pages](https://dash.plotly.com/introduction)



### Building a local instance 

For building the local instance, you need to do as follows:   

In a folder that you want to work in, setup virutal environment 
```(console)
$ python -m venv virtenv  
$ source virtenv/bin/activate ## Linux   
$ virtenv\Scripts\activate ## Windows   
```

Install the following packages: 
```(console)
$ pip install dash 
$ pip install pandas ## incase you plan to use a local CSV/ Excel/ SQLite file
``` 

Follow the instructions as mentioned on the [dash webpage](https://dash.plotly.com/datatable)
<details> 
  <summary> The same code is available here as well </summary>   
  
  
Create a python file (eg. dashboard.py) 
```(python) 
## Import the libraries, i.e. dash and pandas
import pandas
import dash 
import dash_table 

## Load your dataset into a dataframe
df = pandas.read_csv("test_data.csv")

app = dash.Dash("Test") 

## The following describes the layout of the app/ webpage. At this point
## the only layout is a simple table on the webpage i.e. the data table
app.layout = dash_table.DataTable(id='table', 
                                    data=df.to_dict('records'),
                                    columns=[{"name": i, "id": i} for i in df.columns])

## Run the app and to view your results, go to http:/127.0.0.1:8050
app.run_server(debug=True)
```
</details> 

The dashboard is now available to you locally at http:/127.0.0.1:8050

### Hosting on the web with Heroku 

If you'd like to publish this on a browser, and don't want to worry about the hosting, 
and the infrastructure, you can use Heroku.

To the local code above, you need to make a few small changes, again they are all described 
on the [deployment page]()  

<details> 
  <summary> You can find the same descriptions here </summary>   
  You will need a Heroku account: [Heroku getting started with python]()  
  
  Once you are setup with an account with Heroku, startup in a new folder. 
  
  ```(console)
  $ mkdir dash_app_example
  $ cd dash_app_example
  ```
  
  Initialise the folder with git and create a virtual environment 
  ```(console)
  $ git init
  $ python -m venv virtenv  
  $ source virtenv/bin/activate ## Linux   
  $ virtenv\Scripts\activate ## Windows   
  ```


  Install the following packages 
  ```(console)
  $ pip install dash 
  $ pip install pandas ## incase you plan to use a local CSV/ Excel/ SQLite file
  $ pip install plotly
  $ pip install gunicorn 
  ```   
  
  Make changes to your dashboard.py file: 
  


