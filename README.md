# stiebel-eltron-isg-dashboard
This is an example dashboard for the [Custom Integration for Stiebel Eltron Heatpumps](https://github.com/pail23/stiebel_eltron_isg_component/discussions) for Home Assistant.
After activate the integration via HACS or similar you can paste the yaml-code in the Code Editor of a dashboard.

The following templates are needed:
```
- sensor:
  - name: "Heatpump COP Today"
    unique_id: heatpump_cop_today
    unit_of_measurement: "COP"
    state: >
      {{ (states('sensor.stiebel_eltron_isg_produced_heating_today')|float / 
        states('sensor.stiebel_eltron_isg_consumed_heating_today')|float) | round(1) }}

  - name: "Heatpump COP Total"
    unique_id: heatpump_cop_total
    unit_of_measurement: "COP"
    state: >
      {{ (states('sensor.stiebel_eltron_isg_produced_heating_total')|float / 
        states('sensor.stiebel_eltron_isg_consumed_heating_total')|float) | round(1) }}
```

![Overview](https://github.com/mrebbert/stiebel-eltron-isg-dashboard/blob/main/overview.jpeg)
![Preferences](https://github.com/mrebbert/stiebel-eltron-isg-dashboard/blob/main/preferences.png)
