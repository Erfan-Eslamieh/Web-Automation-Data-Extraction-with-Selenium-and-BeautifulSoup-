from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.chrome.options import Options
from selenium.webdriver.common.keys import Keys
from bs4 import BeautifulSoup

options = Options()
options.add_experimental_option("detach", True)   # مرورگر را مستقل می‌کند

service = Service('chromedriver.exe')
driver = webdriver.Chrome(service=service, options=options)

driver.get("https://google.com")

search_bar = driver.find_element("name", "q")
search_bar.send_keys("scholarship db")
search_bar.send_keys(Keys.ENTER)

input("کپچا را بزن و بعد Enter فشار بده...")

soup = BeautifulSoup(driver.page_source, 'html.parser')
name_list = soup.find_all('h3')

with open('names.txt', 'a', encoding='utf-8') as f:
    for name in name_list:
        f.write(name.text + "\n")


