Market Price App is a Django Application which integrates MarketStack API to fetch the End of the Day stock price data of 6 companies and store in Database.
It runs a cronjob which runs a task from Tuesday to Saturday at 4:30am HKT to fetch the stock price data and store it in DB.

It also creates a visualisation using line chart to plot the closing price of 6 companies closing stockprice.

Steps (For local):
1. Execute: python manage.py runserver
2. Open the link in browser: http://127.0.0.1:8000/chart


![Screenshot from 2021-04-13 02-37-38](https://user-images.githubusercontent.com/25360174/114444397-69de2a80-9c01-11eb-9080-d34cf186d035.png)

A model manager method highest_increment is implement which returns the symbol (ticker) of the company which has the highest increment in the closing price in last 5 working days.

Steps:
1. Execute: python manage.py shell
2. Inside shell excute the below lines one after another: 

from MarketPrice.models import StockPrice

StockPrice.objects.highest_increment()

The test cases of the model manager method can be excuted using:

Execute: python manage.py test


 
