import requests
import smtplib

OWM_Endpoint = "https://api.openweathermap.org/data/2.5/weather"
api_key = “enter_api_key_here”


weather_params = {
    "lat": enter_latitude_here,
    "lon": enter_longitude_here,
    "APPID": api_key,
}

data_response = requests.get(OWM_Endpoint, params=weather_params)
data = data_response.json()

main = data["weather"][0]["main"]
description = data["weather"][0]["description"]

message = f”Enjoy your morning walk.\n” \
          f"Main weather description for today: {main}\n" \
          f"More specific weather description: {description}"

my_email = “enter_sender_email_here”
sister_email = “enter_receipient_email_here”
password = “enter_gmail_third_party_password_here”

with smtplib.SMTP("smtp.gmail.com") as connection:
    connection.starttls()
    connection.login(user=my_email, password=password)
    connection.sendmail(from_addr=my_email,
                        to_addrs=sister_email,
                        msg=f"Subject:Weather Update\n\n{message}")

