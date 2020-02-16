## Scraping

### Today I Learn

<pre><code>

html = urlopen("//") #obtain html contents
soup = BeautifulSoup(html, "html.parser") # object of beautifulsoup
nameList = soup.find_all("table", {"class":"table_3"}) # table tag, attributes

for name in nameList:
    print (name.get_text())

