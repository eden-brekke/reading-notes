# Reading

-   [Web Scrape with Python in 4 minutes](https://towardsdatascience.com/how-to-web-scrape-with-python-in-4-minutes-bc49186a8460)

Web Scraping: A technique to automatically access and extract large amounts of info from a site. 

Important notes about web scraping
1. read through the websites terms and conditions to understand how you can legally use the data. Most sites will prohibit you from using the data for commercial purposes. 
2. Make sure you are not downloading data at too rapid of a rate because that can break the website and cause you to be blocked from the site. 

Python Libraries to use for this:  
```python
import requests  
import urllib.request  
import time  
from bs4 import BeautifulSoup
```

set the URl and response/reuqest
```python
url = "path"
response = request.get(url)
```

Parse the info with beautiful soup and use a method to find all hyperlinks
```python
soup = BeautifulSoup(response.text, “html.parser”)
soup.findAll('a')
```


Entire example code: 
```python
# Import libraries

import requests

import urllib.request

import time

from bs4 import BeautifulSoup

# Set the URL you want to webscrape from

url = 'http://web.mta.info/developers/turnstile.html'

# Connect to the URL

response = requests.get(url)

# Parse HTML and save to BeautifulSoup object¶

soup = BeautifulSoup(response.text, "html.parser")

# To download the whole data set, let's do a for loop through all a tags

line_count = 1 #variable to track what line you are on

for one_a_tag in soup.findAll('a'): #'a' tags are for links

if line_count >= 36: #code for text files starts at line 36

link = one_a_tag['href']

download_url = 'http://web.mta.info/developers/'+ link

urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:])

time.sleep(1) #pause the code for a sec

#add 1 for next line

line_count +=1
```

-   [What is Web Scraping?](https://en.wikipedia.org/wiki/Web_scraping)
Used for extracting data from websites. 
Can be done manually or by bot(web crawler)
Data is then stored into a local database for analysis 

Techniques: 
*  Human copy and paste : manually copy and pasting data from the webpage into text file or spreadsheet
* Text pattern matching: extract info from site based on UNIX grep command or regex matching. 
* HTTP programming: posting HTTP requests to the remote web server using socket programming
* HTML parsing: parse the HTML pages to retreive and transform page contents
* DOM parsing: browser controls parse pages into DOM trees. 
* Vertical aggregation: platforms create and monitory a multitude of bots to grab data
* Semantic annotation recognizing: can be used to locate specific data snippets 
* Computer vision web page analysis: using machine learning and computer vision to identify and extract info from web pages by interpretting pages visually as a human might

-   [How to scrape websites without getting blocked](https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/)
First. Perform it responsibly so the site doesn't have any detrimental occurences happening to it. 
1. respect robots
	1. if it has user-agent: * and Disallow: / it usually means the site doesn't want to be scraped
2. make the crawl slower
3. don't follow repetitive crawling patterns
4. make requests through proxies and rotate as needed
5. rotate user agents and HTTP request headers
6. use headless brower (puppeteer, selenium, playwright)
7. beware of honey  pot traps
	1. these are links that are invisible to normal user but can be seen by web scrapers
8. check if website is changing layouts
9. avoid scraping behind a login
10. use captcha solving services

Few easy giveaways that you are a bot/scraper/crawler:
* scraping too fast on too many pages, faster than a human ever could
* following the same pattern while crawling 
	* going through all pages of search results and to each result only after grabbing links to them 
* too many requests from the same IP address in a short time
* not identifying as a popular browser 
* using a user agent string of a very old browser
* 

## Videos

[Track Amazon Prices](https://www.youtube.com/watch?v=Bg9r_yLk7VY)

```python
# scraper.py
# install two things
# pip install requests bs4
import requests
from bs4 import BeautifulSoup
import smtplib # enables you to send emails
import time

url = "https://www.amazon.com/Sony-Full-frame-Mirrorless-Interchangeable-Camera/dp/B09JZT6YK5/ref=sr_1_1?keywords=sony+e7+camera&qid=1652149071&sprefix=sony+e7%2Caps%2C397&sr=8-1"

headers = {"User-Agent": 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36'}

def check_price():
	page = requests.get(url, headers=headers)

	soup = BeautifulSoup(page.content, 'html.parser')

	print(soup.prettify) # it never stops, I'm in

	title = soup.find(id='productTitle').get_text()
	price = soup.find(id='priceblock_ourprice').get_text()
	converted_price = float(price[0:5])
	
	if(converted_prince < 1.700):
		send_mail()

	print(converted_price)
	print(title.strip())


def send_mail():
	# google less secure apps 
	# or google two step verification and enable it
	# google app password
	# select mail and windows computer and generate new password to use 
	server = smtplib.SMTP('smtp.gmail.com', 587) # gmails stuffs
	server.ehlo() # establish connection
	server.startls() # encrypts server
	server.ehlo()

	server.log('ed.magician@gmail.com', "your generated password")

	subject = "Price fell down!"
	body = "Check the amazon link: https://www.amazon.com/Sony-Full-frame-Mirrorless-Interchangeable-Camera/dp/B09JZT6YK5/ref=sr_1_1?keywords=sony+e7+camera&qid=1652149071&sprefix=sony+e7%2Caps%2C397&sr=8-1"
	msg = f"Subject: {subject}\n\n{body}"

	server.sendmail(
		'ed.magician@gmail.com'
		'simo.edwin@yahoo.com',
		msg
		)
	print("HEY EMAIL HAs BEEN SENT!")
	
	server.quit()


while True: 
	check_price()
	time.sleep(60 * 60 * 24) # seconds, checks every minute, maybe instead change it to once a day :P else you will cause them to block you
``` 

## Bookmark and Review

[Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/)