import requests

email=input('Enter email : ')

headers = {
    'authority': 'www.instagram.com',
    'accept': '*/*',
    'accept-language': 'en-US,en;q=0.9,ar-EG;q=0.8,ar;q=0.7',
    'content-type': 'application/x-www-form-urlencoded',
    'origin': 'https://www.instagram.com',
    'referer': 'https://www.instagram.com/accounts/password/reset/',
    'sec-ch-prefers-color-scheme': 'dark',
    'sec-ch-ua': '"Not-A.Brand";v="99", "Chromium";v="124"',
    'sec-ch-ua-full-version-list': '"Not-A.Brand";v="99.0.0.0", "Chromium";v="124.0.6327.1"',
    'sec-ch-ua-mobile': '?0',
    'sec-ch-ua-model': '""',
    'sec-ch-ua-platform': '"Linux"',
    'sec-ch-ua-platform-version': '""',
    'sec-fetch-dest': 'empty',
    'sec-fetch-mode': 'cors',
    'sec-fetch-site': 'same-origin',
    'user-agent': 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/124.0.0.0 Safari/537.36',
    'x-asbd-id': '359341',
    'x-csrftoken': '1TmqF2aHNqS3Vm5XeesLcVgcXKDbxwq7',
    'x-ig-app-id': '936619743392459',
    'x-ig-www-claim': '0',
    'x-instagram-ajax': '1025986038',
    'x-requested-with': 'XMLHttpRequest',
    'x-web-session-id': 'yj18qp:my2pct:sr5snx',
}

data = {
    'email_or_username': email,
    'jazoest': '22821',
}

response = requests.post(
    'https://www.instagram.com/api/v1/web/accounts/account_recovery_send_ajax/',
    headers=headers,
    data=data,
).text
if 'send_email' in response:
 print('تم الارسال اذهب الى الجميل')
else:
 print('فشل الارسال حاول مجددا ')