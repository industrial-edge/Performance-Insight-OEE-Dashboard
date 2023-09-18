# Performance Insight OEE analysis

This example shows how to use the Industrial Edge App "Performance Insight" with it´s embedded OEE dashboard to present the productivity of a plant transparently.

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

With the key figure of Overall Equipment Effectiveness (OEE), you can calculate the productivity of a plant or its losses and display them transparently using the Gantt widget. The OEE widgets are predefined, only a few parameters have to be defined in the OEE settings.

The OEE of a plant is defined as the product of the following three factors:
- Availability factor (e.g. whether there are fault times)
- Performance factor (e.g. whether the system is running at full load or reduced load)
- Quality factor (e.g. how much scrap is produced)

![Overview](/docs/graphics/Overview.png)

You can create an OEE dashboard for each asset. The dashboard is created automatically on the basis of the settings made by you. With the configuration, several OEE-KPIs are generated and displayed in the OEE dashboard.

### General task

This document describes how to create an OEE analysis dashboard within Performance Insight. The OEE settings are configured based on [this](#tia-project) TIA project and then displayed as a dashboard.

This HowTo is a supplement to [Performance Insight getting started](https://github.com/industrial-edge/performance-insight-getting-started).

![OEEDashboard](/docs/graphics/OEEDashboard.png)

## Requirements

### Prerequisites

- Access to an Industrial Edge Management System (IEM)
- Onboarded Industial Edge Device on IEM
- Google Chrome (Version ≥ 72)

### Used components

- Industrial Edge Management (IEM) V1.5.2-4 / V1.10.3
  - IE Databus V 1.8.2-2
  - IE Databus Configurator V 1.8.2-2
  - OPC UA Connector V 1.8.1-6
  - Common Connector Configurator V 1.8.1-4
  - Data Service V 1.5.0
  - Performance Insight V 1.6.2
- Industrial Edge Device V 1.9.0-27
- TIA Portal V16
- CPU 1511-1 PN

### TIA Project

The used TIA Portal project can be found in the [miscellaneous repository](https://github.com/industrial-edge/miscellaneous/tree/main/tank%20application) and is also used for several further application examples.

## Configuration

You can find further information about the following steps in the [Configuration](/docs/Installation.md) documentation:

- [Configure Data Service](/docs/Installation.md#configure-data-service)
- [Configure Performance Insight](/docs/Installation.md#configure-performance-insight)

## Usage

Once the OEE configuration is done, the dashboard is automatically created underneath the dedicated asset. Go to 'My Plant' and select the asset 'OEE Data'. Click on the 'OEE' dashboard to open the view. Please be aware to select a proper time period for displaying the dashboard, that contains useful process data.

The OEE dashboard offers the following possibilities:
- Quick overview of KPIs and machine status
- Detail view for KPIs and machine status
- Adjustable displayed period
- Exporting data
- Access to the OEE settings
- Display of errors that occurred during the analysis

The dashboard shows the OEE-KPIs as pie charts. The limits are pre-defined but can be adjusted for each KPI. To visualize the interaction of the KPIs in a diagram, click 'Details'.

![OEE_KPIs](/docs/graphics/OEE_KPIs.png)

In the 'Machine State' view, the Gantt widget shows an overview of the individual machine statuses and a summary. Only the variables that have a value are displayed. Click 'Details' to also see the machine state as time model or table view.

![OEE_MachineState](/docs/graphics/OEE_MachineState.png)

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
