# Configuration

- [Configuration](#configuration)
  - [Configure Data Service](#configure-data-service)
  - [Configure Performance Insight](#configure-performance-insight)
    - [Create status mapping](#create-status-mapping)
    - [Create KPI goodCount](#create-kpi-goodcount)
    - [Create OEE dashboard](#create-oee-dashboard)

## Configure Data Service

The PLC with the running TIA project is connected via the OPC UA connector to the Industrial Edge Device (IED). Within the connector, all necessary tags are configured and deployed.

Now the app Data Service needs to collect and store this data, to further use it within Performance Insight. Make sure the OPC UA connector is activated within the Data Service.

![Connector](/docs/graphics/Connector.png)

Then create a new asset with the following variables:

![Variables](/docs/graphics/Variables.png)

## Configure Performance Insight

### Create status mapping

The machine state of a PLC is one of the main parts of the OEE calculation. To correctly map this data, you need to create a status mapping within Performance Insight. All time categories (Net Production Time, Planned Downtime, Unplanned Downtime) must be covered my the mapping. Go to 'Configuration' > 'Status mappings' and create a new status mapping according to this example:

![StatusMapping](/docs/graphics/StatusMapping.png)

### Create KPI goodCount

For the OEE configuration, we need a parameter that represents the 'goodCounts'. Since the PLC is not offering this parameter, we need to calculate it and save it as KPI instance.

Go to 'My Plant' and select the Asset 'OEE Data'. Go to the 'parameter' view and click 'Create new KPI instance'. Create a KPI instance according to this example, assign the operands to the dedicated parameter and set the aggregation to 'Counter'. Save the KPI instance. 

![KPI](/docs/graphics/KPI.png)

### Create OEE dashboard

After we have prepared all necessary input data, we can create the OEE dashboard.

Therefore go to 'My Plant' and select the Asset 'OEE Data'. Click 'Add dashboard' and then 'OEE dashboard'. Within the OEE configuration window, proceed as following:

- select the previously created status mapping
- select a parameter that represents the machine status
- link the operand 'TotalCount' to the dedicated parameter and set the aggregation to 'Counter'
- link the operand 'TheroreticalSpeed' to a fixed number that represents the speed of your production in pcs/s
- link the operand 'GoodCount' to the previously created KPI instance
- save the configuration

![OEEConfig](/docs/graphics/OEEConfig.png)
