# HA-Thermia-Genesis-Monitoring
Home Assistant dashboard for monitoring Thermia Genesis heatpumps

I created a 'Picture Elements' dashboard to be able to monitor the parameters of my heatpump.
Most of the sensor data is provided through the following integration: https://github.com/CJNE/thermiagenesis

The https://github.com/CJNE/thermiagenesis integration supports either Thermia Mega or Thermia Diplomat inverters, and is written based on Thermia Genesis platform version 10.

I have a Calibra heatpump, which is running Genesis platform 13.
The sensor data which is not available from the https://github.com/CJNE/thermiagenesis integration is pulled locally from the heatpump using Modbus TCP.


Steps to get started:

1) Download the 'HA_HEATPUMP' GIF and upload it to a local folder on your Home Assistant instance (eg /config/www/community/);
  
2) Create a file called thermiacalibradiy.yaml in your Config folder and copy/paste the code from 'thermiacalibradiy' into it. Link to this file in your configuration.yaml by adding:

```
homeassistant:
  packages:
    thermiacalibra: !include thermiacalibradiy.yaml
```

4) Create a new dashboard;
5) Edit the dashboard and edit the view => Select Panel (1 card);
6) Add a Picture elements card;
7) Edit the Picture elements card and paste the code 'PictureElementsCardCode';
8) To enable the text descriptions on the Picture elements card, add the 'blank_blank' code (copy/paste!) to your configuration.yaml template section and reload template entities:
9) Enjoy!
