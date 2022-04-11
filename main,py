import requests

api_url_cw = 'https://api.openweathermap.org/data/2.5/weather'
api_url_geocord = 'http://api.openweathermap.org/geo/1.0/direct'

city = input("City:")

params_geocord = {
    'q': city,
    'appid': 'aa2e2c84ed4a53a0941701439de11f0b'
}

data_geocord = (requests.get(api_url_geocord, params=params_geocord)).json()
print(data_geocord)
lat = data_geocord[0]['lat']
lon = data_geocord[0]['lon']

params_cw = {
    'lat': lat,
    'lon': lon,
    'appid': 'aa2e2c84ed4a53a0941701439de11f0b',
    'units': 'metric'
}

res = requests.get(api_url_cw, params=params_cw)
print(res.status_code)
print(res.json())
data = res.json()
template = "Current temperature in {} is {}"
print(template.format(city, data['main']['temp']))
