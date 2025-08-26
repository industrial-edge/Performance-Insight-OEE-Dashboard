# Performance Insight OEE analysis

This example shows how to use the Industrial Edge App "Performance Insight" with it´s embedded OEE dashboard to present the productivity of a plant transparently (including error analysis and reason tree).

- [Performance Insight OEE analysis](#performance-insight-oee-analysis)
  - [Description](#description)
    - [Overview](#overview)
    - [General task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisites](#prerequisites)
    - [Used components](#used-components)
    - [TIA Project](#tia-project)
  - [Configuration](#configuration)
  - [Usage](#usage)
  - [Documentation](#documentation)
  - [Contribution](#contribution)
  - [Licence and Legal Information](#licence-and-legal-information)

## Description

### Overview

OEE (Overall Equipment Effectiveness) is the key production metric for measuring overall equipment effectiveness of a production.   

It combines these three factors into a percentage value:   
- Availability (equipment uptime, e.g. whether there are fault times)
- Performance (production speed, e.g. whether the system is running at full load or reduced load)
- Quality (good parts, e.g. how much scrap is produced) 

The OEE value and it's dedicated KPIs represents the productivity of a plant.  
Using the OEE dashboard within Performance Insight, these values are displayed transparently using the Gantt widget. This out-of-the-box dashboard can easily be configured with only a view parameter settings. You can create one OEE dashboard per asset.  

![Overview](/docs/graphics/Overview.png)

### General task

This repository describes how to create an OEE analysis dashboard within Performance Insight. It also gives insights into the embedded error analysis and the reason tree functionality.  

![OEEDashboard](/docs/graphics/OEEDashboard.png)

Please visit [Performance Insight getting started](https://github.com/industrial-edge/performance-insight-getting-started) to discover the basics of the app.

## Requirements

### Prerequisites

- Access to an Industrial Edge Management System (IEM)
- Onboarded Industial Edge Device (IED) on IEM
- IED connected to PLC
- TIA Portal project loaded on PLC
- HTML5-capable Internet browser (e.g. Google Chrome)

### Used components

- Industrial Edge Management (IEM) V1.11.7
- Industrial Edge Device V3.0.0
- Management applications:
  - Databus Configurator V3.2.0
  - Common Connector Configurator V2.0.0
- Device applications:
  - Databus V3.1.0
  - OPC UA Connector V2.4.0
  - Common Configurator V2.2.0
  - IIH Essentials V2.2.0
  - Performance Insight V1.21.1
- TIA Portal V19

### TIA Project

This application example is based on the [tank application](https://github.com/industrial-edge/miscellaneous/tree/main/tank%20application) TIA Portal project, which is also used for several further examples.

## Configuration

You can find further information about the following steps in the [Configuration](/docs/Installation.md) documentation:

- [Configure Data Service](/docs/Installation.md#configure-data-service)
- [Configure Performance Insight](/docs/Installation.md#configure-performance-insight)

## Usage

Once the OEE configuration is done, the dashboard is automatically created underneath the dedicated asset. Go to 'My Plant' and select the asset. Click on the 'OEE' dashboard to open the view. Please be aware to select a proper time period for displaying the dashboard, that contains useful process data.

The OEE dashboard offers the following possibilities:
- OEE overview:
  - Quick overview of KPIs and machine status
  - Detail view for KPIs and machine status
- Error analysis (optional):
  - Overview of the most common errors
- Analysis of sub assets (optional):
  - Overview of machine states and OEE KPIs of all configured sub assets 

### OEE overview

The OEE overview shows the current OEE KPI values according to the selected dashboard time range. The KPI formulas as well as the limits are pre-defined but can be adjusted for each KPI. To visualize the interaction of the KPIs in a diagram, click 'Details'.

![OEE_overview](/docs/graphics/OEE_overview.png)

Furthermore, the machine status is displayed as Gantt widget including all the occured states. The Distribution area shows the overall duration of each state for the selected time period. 

Click 'Details' to also see the machine state as time model or table view.

![OEE_MachineState](/docs/graphics/OEE_MachineState.png)

**Reason tree**  

Within the time model view, you can use the reason tree functionality.

The reason tree is a detailed representation of the different error states in which a machine or plant can be. Within the OEE dashboard, this configuration can be used to analyse the reason of downtimes in a more fine granular way. 

The reason tree is based on the specified time categories:
- Production time (Net production time)
- Planned downtime (Planned downtime, e.g. maintenance)
- Unplanned downtime (Unplanned downtime, e.g. machine fault, material shortage)

Each reason belongs to one of these time categories.

-----> HIER WEITER
-----> Screenshot 'Time model' einfügen

### Error analysis

xxx

### Analysis of sub assets

xxx

## Documentation

You can find further documentation and help in the following links:

* [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
* [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
* [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
* [Industrial Edge GitHub page](https://github.com/industrial-edge)

## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you haven't previously signed the [Siemens Contributor License Agreement](https://cla-assistant.io/industrial-edge/) (CLA), the system will automatically prompt you to do so when you submit your Pull Request. This can be conveniently done through the CLA Assistant's online platform. Once the CLA is signed, your Pull Request will automatically be cleared and made ready for merging if all other test stages succeed.

## Licence and Legal Information

Please read the [Legal information](LICENSE.md).
