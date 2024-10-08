# HA-Thermia-Genesis-Monitoring
Home Assistant dashboard for monitoring Thermia Genesis heatpumps

I created a 'Picture Elements' dashboard to be able to monitor the parameters of my heatpump.
Most of the sensor data is provided through the following integration: https://github.com/CJNE/thermiagenesis

The https://github.com/CJNE/thermiagenesis integration seems to support either Thermia Mega or Thermia Diplomat inverters, and is written based on Thermia Genesis platform version 10.

I have a Calibra heatpump, which is running Genesis platform 13.
The sensor data which is not available from the https://github.com/CJNE/thermiagenesis integration is pulled locally from the heatpump using Modbus TCP.


Steps to get started:
1) Download the GIF and upload it to a local folder on your Home Assistant instance (eg /config/www/community/);
2) Create a new dashboard;
3) Edit the dashboard and edit the view => Select Panel (1 card);
4) Add a Picture elements card;
5) Edit the Picture elements card and paste the code;
6) Enjoy!
