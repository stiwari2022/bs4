import bs4
import requests
from bs4 import BeautifulSoup
from urllib.request import urlopen
url = 'https://finance.yahoo.com/quote/AAPL?p=AAPL&.tsrc=fin-srch'
try:
  page=requests.get(url)
except:
  print("Error opening the URL")
src=page.text
soup = bs4.BeautifulSoup(src,"html.parser")
m =soup.find_all('div',{'class': 'My(6px) Pos(r) smartphone_Mt(6px)'})[0]
m1=m.find('span')
price=m1.text
print(price)
