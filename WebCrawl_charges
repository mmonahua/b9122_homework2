from bs4 import BeautifulSoup
import urllib.request
from urllib.request import Request

seed_url = "https://www.sec.gov/news/pressreleases"
url = 'https://www.sec.gov/news/press-release/'

urls = [seed_url]
seen = [seed_url]
opened = []
charges = []

minNumUrl = 20
#print("Starting with url="+str(urls))

while len(urls) > 0 and len(charges) < minNumUrl:
    try:
        curr_url=urls.pop(0)
        req = urllib.request.Request(curr_url,headers={'User-Agent': 'Mozilla/5.0'})
        webpage = urllib.request.urlopen(req).read()
        opened.append(curr_url)

    except Exception as ex:
        print("Unable to access= "+ curr_url)
        print(ex)
        continue

    soup = BeautifulSoup(webpage)

    text = soup.get_text().lower()
    if 'charges' in text:
        charges.append(curr_url)
        print("-------------------")
        print(curr_url)

        for div in soup.findAll('h1', {'class': "article-title"}  ):
            print(div.text.strip())
            print()
        for div in soup.findAll('div', {'class': "article-body"}  ):
            print(div.text.strip())
            print("\n")
            
    for tag in soup.find_all('a', href = True):
        childUrl = tag['href']
        o_childurl = childUrl
        childUrl = urllib.parse.urljoin(seed_url, childUrl)
        if url in childUrl and childUrl not in seen:
            urls.append(childUrl)
            seen.append(childUrl)

print("num. of URLs contain charges = %d" % len(charges))
print("List of charges URLs:")
for charges_url in charges:
    print(charges_url)
