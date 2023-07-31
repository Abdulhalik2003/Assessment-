import requests

def get_weather(date):
    response = requests.get(f'https://api.example.com/weather?date={date}')
    data = response.json()
    return data['temp']

def get_wind_speed(date):
    response = requests.get(f'https://api.example.com/wind_speed?date={date}')
    data = response.json()
    return data['wind_speed']

def get_pressure(date):
    response = requests.get(f'https://api.example.com/pressure?date={date}')
    data = response.json()
    return data['pressure']

while True:
    print("1. Get weather")
    print("2. Get Wind Speed")
    print("3. Get Pressure")
    print("0. Exit")

    choice = int(input("Enter your choice: "))

    if choice == 1:
        date = input("Enter the date (YYYY-MM-DD): ")
        temp = get_weather(date)
        print(f"The temperature on {date} is {temp} degrees Celsius.")

    elif choice == 2:
        date = input("Enter the date (YYYY-MM-DD): ")
        wind_speed = get_wind_speed(date)
        print(f"The wind speed on {date} is {wind_speed} m/s.")

    elif choice == 3:
        date = input("Enter the date (YYYY-MM-DD): ")
        pressure = get_pressure(date)
        print(f"The pressure on {date} is {pressure} hPa.")

    elif choice == 0:
        print("Exiting the program.")
        break

    else:
        print("Invalid choice. Please try again.")
