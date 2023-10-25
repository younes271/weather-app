# weather-app
A new repository created via Python script


---

Here's a simple Python code using the OpenWeatherMap API to create a basic weather app:

```python
import requests
import json

def weather_data(query):
    res=requests.get('http://api.openweathermap.org/data/2.5/weather?'+query+'&APPID=b35975e18dc93725acb092f7272cc6b8&units=metric');
    return res.json();

def print_weather(result,city):
    print("{}'s temperature: {}°C ".format(city,result['main']['temp']))
    print("Wind speed: {} m/s".format(result['wind']['speed']))
    print("Description: {}".format(result['weather'][0]['description']))
    print("Weather: {}".format(result['weather'][0]['main']))

def main():
    city=input('Enter the city:')
    print()
    try:
        query='q='+city;
        w_data=weather_data(query);
        print_weather(w_data, city)
        print()
    except:
        print('City name not found...')
        
if __name__=='__main__':
    main()
```

Please replace 'b35975e18dc93725acb092f7272cc6b8' with your actual API key. You can get your free API key by signing up on the OpenWeatherMap website.
