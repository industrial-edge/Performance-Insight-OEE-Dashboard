# Configuration

- [Configuration](#configuration)
  - [Configure Data Service](#configure-data-service)
  - [Configure Performance Insight](#configure-performance-insight)
    - [Configure status mapping](#configure-status-mapping)
    - [Configure KPI types](#configure-kpi-types)
    - [Configure Parameter](#configure-parameter)
    - [Configure OEE settings](#configure-oee-settings)
  - [Display OEE dashboard](#display-oee-dashboard)

## Configure Data Service

Create a new asset with the following variables in the Data Service to collect all needed data.

<p align="center"><kbd><img src="graphics/Data_Service_Variables.PNG" /></kbd></p>

## Configure Performance Insight

### Configure status mapping

Open the Performance Insight status mapping and create a new status mapping which is needed later for the OEE settings.

<p align="center"><kbd><img src="graphics/Performance_Insight_machine_status.PNG" /></kbd></p>

### Configure KPI types

Create two new KPI types to calculate the "theoretical speed" and the "good count", which are later needed to define parameters in the OEE settings.

<p align="center"><kbd><img src="graphics/Performance_Insight_KPI_theoretical_speed.PNG" /></kbd></p>

<p align="center"><kbd><img src="graphics/Performance_Insight_KPI_good_count.PNG" /></kbd></p>

### Configure Parameter

Open the parameters in the respective asset and create two new KPI instances for "theoretical speed" and "good count".

<p align="center"><kbd><img src="graphics/Performance_Insight_parameter_good_count.PNG" /></kbd></p>

<p align="center"><kbd><img src="graphics/Performance_Insight_parameter_theoretical_speed.PNG" /></kbd></p>

### Configure OEE settings

Open Asset Configuration in the respective asset and define OEE settings.

<p align="center"><kbd><img src="graphics/Performance_Insight_Asset_Configuration.PNG" /></kbd></p>

<p align="center"><kbd><img src="graphics/Performance_Insight_define_OEE_settings.PNG" /></kbd></p>

- Select the created machine status under "status mapping

- Select the machine status variable "GDB_operate_machineState"

- Select the respective variables and created KPI types

- Click on save
 
<p align="center"><kbd><img src="graphics/Performance_Insight_OEE_settings.PNG" /></kbd></p>

## Display OEE dashboard

Open your asset in which the OEE settings have been made and select the tab "OEE". Choose a proper time range within the dashboard for which data is definitely available.

<p align="center"><kbd><img src="graphics/Performance_Insight_OEE_Dashboard.PNG" /></kbd></p>
