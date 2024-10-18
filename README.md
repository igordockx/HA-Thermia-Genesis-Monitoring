# HA-Thermia-Genesis-Monitoring
Home Assistant dashboard for monitoring Thermia Genesis heatpumps

I created a 'Picture Elements' card on a separate dashboard to be able to monitor the parameters of my heatpump.
Most of the sensor data is provided through the following integration: https://github.com/CJNE/thermiagenesis

The https://github.com/CJNE/thermiagenesis integration supports Thermia Mega and Thermia Diplomat Inverter heatpumps, and is written based on Thermia Genesis platform version 10.

I have a Calibra heatpump, which is running Genesis platform 13.
The sensor data which is not available from the https://github.com/CJNE/thermiagenesis integration is pulled locally from the heatpump using Modbus TCP.


Steps to get started:

1) Download 'HA_HEATPUMP.png' and upload it to a local folder on your Home Assistant instance (eg /config/www/community/);
  
2) Download the file 'thermiacalibradiy.yaml' and upload it to your Config folder.
3) Open the file and add your heatpump's IP address to the line 'host: 192.168.x.x'
4) Link to the file by adding the following code to your configuration.yaml and reboot:

```
homeassistant:
  packages:
    thermiacalibra: !include thermiacalibradiy.yaml
```

5) Create a new dashboard;
6) Edit the dashboard and edit the view: Select 'Panel (1 card)';
7) Add a Picture elements card to the dashboard;
8) Edit the Picture elements card and paste the code found in 'PictureElementsCardCode';
9) To enable the text descriptions on the Picture elements card, and to calculate the temperature difference deltaT of the heatpump's brine and condenser heat exchangers, add the following code (copy/paste!) to your configuration.yaml template section and reload template entities:

```
###########################################
###Text element on picture elements card###
###########################################
template:
  - sensor:
    - name: Brine delta T
      unit_of_measurement: "°C"
      state: "{{ (( states('sensor.brine_in_temperature') | float ) - ( states('sensor.brine_out_temperature') | float )) | round(2) }}"
    - name: Condenser delta T
      unit_of_measurement: "°C"
      state: "{{ (( states('sensor.condenser_out_temperature') | float ) - ( states('sensor.condenser_in_temperature') | float )) | round(2) }}"
    - name: blank_blank
      state: " "
```
   
10) Enjoy!

Note: By hovering over the Picture elements card you will see which sensor entities are being used. Those entities will need to be enabled in the thermiagenesis integration.

As standard, the heatpump will only take the outdoor temp into account.
If you also monitor the actual room temperature, it's nice to display this on the card as well.
