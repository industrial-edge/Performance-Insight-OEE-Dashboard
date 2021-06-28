# Configuration

- [Configuration](#configuration)
  - [Configure Databus](#configure-databus)
  - [Configure Performance Insight](#configure-performance-insight)
    - [Configure status mapping](#configure-status-mapping)
    - [Configure KPI types](#configure-kpi-types)
    - [Configure Parameter](#configure-parameter)
    - [Configure OEE settings](#configure-oee-settings)
    - [Display OEE dashboard](#display-oee-dashboard)

## Configure Databus

Create a new Add Child with the following variables in the Data Service:

<p align="center"><kbd><img src="graphics/Data_Service_Variables.PNG" /></kbd></p>

## Configure Performance Insight

### Configure status mapping

Open the Performance Insight status mapping and create new status mapping:

<p align="center"><kbd><img src="graphics/Performance_Insight_machine_status.PNG" /></kbd></p>

### Configure KPI types

Create two new KPI types:

<p align="center"><kbd><img src="graphics/Performance_Insight_KPI_theoretical_speed.PNG" /></kbd></p>

<p align="center"><kbd><img src="graphics/Performance_Insight_KPI_good_count.PNG" /></kbd></p>

### Configure Parameter

Open the parameters in the respective asset and create two new KPI instances:

<p align="center"><kbd><img src="graphics/Performance_Insight_parameter_good_count.PNG" /></kbd></p>

<p align="center"><kbd><img src="graphics/Performance_Insight_parameter_theoretical_speed.PNG" /></kbd></p>

### Configure OEE settings

Open Asset Configuration in the respective asset and define OEE settings:

<p align="center"><kbd><img src="graphics/Performance_Insight_define_OEE_settings.PNG" /></kbd></p>

1. select the created machine status under "status mapping

2. Select the machine status variable "GDB_operate_machineState"

2. select the respective variables and created KPI types

<p align="center"><kbd><img src="graphics/Performance_Insight_OEE_settings.PNG" /></kbd></p>

click on save.

### Display OEE dashboard

Open your asset in which the OEE settings have been made.

<p align="center"><kbd><img src="graphics/Performance_Insight_OEE_Dashboard.PNG" /></kbd></p>