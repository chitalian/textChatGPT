# Text bot that helps you with HVAC (Can be configured for anything!)

<img src="https://pbs.twimg.com/media/Fjpv8lIWIAE8VJw?format=jpg&name=large">

# Setup

You need to setup a [twilio account](twilio.com).

If you don't have a server with https to run this on, I recommend using ngrok.
[install ngrok](https://ngrok.com/download)
Setup your ngrok account, i think you need a paid version.

You will also need an openai account that does not use google auth and just uses email and password.
You can get this by creating an account here: https://openai.com/join/

copy the config.json to your project directory and fill in your openai account info

```bash
cp config_example.json config.json
```

# How to run (using ngrok)

```bash
# in one terminal
export TWILIO_ACCOUNT_SID = <Your Twilio info>
export TWILIO_AUTH_TOKEN = <Your Twilio info>
export TWILIO_NUMBER = <Your Twilio info>
python3 -m venv env
source env/bin/activate
python3 -m pip install -r requirements.txt

python3 main.py

# in another terminal
ngrok http 5005
```

inside the your [console](https://console.twilio.com/us1/develop/phone-numbers/manage/incoming) add the ngrok url for the receiving webhook.
<img src="twilio.png">

Now you can text your number
