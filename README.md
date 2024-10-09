# HA-Thermia-Genesis-Monitoring
Home Assistant dashboard for monitoring Thermia Genesis heatpumps

I created a 'Picture Elements' dashboard to be able to monitor the parameters of my heatpump.
Most of the sensor data is provided through the following integration: https://github.com/CJNE/thermiagenesis

The https://github.com/CJNE/thermiagenesis integration supports either Thermia Mega or Thermia Diplomat inverters, and is written based on Thermia Genesis platform version 10.

I have a Calibra heatpump, which is running Genesis platform 13.
The sensor data which is not available from the https://github.com/CJNE/thermiagenesis integration is pulled locally from the heatpump using Modbus TCP.


Steps to get started:

1) Download the 'HA_HEATPUMP' GIF and upload it to a local folder on your Home Assistant instance (eg /config/www/community/);
  
2) Download the file 'thermiacalibradiy.yaml' and upload it to your Config folder. Link to this file by adding code below to your configuration.yaml and reboot:

```
homeassistant:
  packages:
    thermiacalibra: !include thermiacalibradiy.yaml
```

3) Create a new dashboard;
4) Edit the dashboard and edit the view => Select 'Panel (1 card)';
5) Add a Picture elements card;
6) Edit the Picture elements card and paste the code 'PictureElementsCardCode';
7) To enable the text descriptions on the Picture elements card, add the following code (copy/paste!) to your configuration.yaml template section and reload template entities:

```

```
   
8) Enjoy!
