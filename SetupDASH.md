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

Setup virutal environment 
'''
>> python -m venv virtenv 
>> source virtenv/bin/activate ## Linux 
>> virtenv\Scripts\activate ## Windows 
'''

Install the following packages: 
'''
>> pip install dash 
>> pip install pandas ## incase you plan to use a local CSV/ Excel/ SQLite file
'''

Create 

