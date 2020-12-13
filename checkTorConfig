import requests
from bs4 import BeautifulSoup

def checkTorConfig():
    url = "https://check.torproject.org/"
    proxies = globals()['proxies'] if 'proxies' in globals() else {} 
    headers = globals()['headers'] if 'headers' in globals() else {"User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.83 Safari/537.36"}
    response = requests.get(url, headers = headers, proxies = proxies)
    soup = BeautifulSoup(response.text, "html.parser")
    return {'ip': soup.find('strong').text, 'withTor': 'Congratulations' in soup.find('h1').text}

headers = {"User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.83 Safari/537.36"}

proxies = {
    'http': 'socks5://127.0.0.1:9050',
    'https': 'socks5://127.0.0.1:9050'
}

print(checkTorConfig())
