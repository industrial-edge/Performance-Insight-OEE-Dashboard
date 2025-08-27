# Configuration

- [Configuration](#configuration)
  - [Configure IIH Essentials](#configure-iih-essentials)
  - [Configure Performance Insight](#configure-performance-insight)
    - [Configure Reason Tree](#configure-reason-tree)
    - [Create status mappings](#create-status-mappings)
    - [Create OEE dashboard](#create-oee-dashboard)
  
## Configure IIH Essentials

The PLC with the running TIA project is connected via the OPC UA connector to the Industrial Edge Device (IED). Within the connector, all necessary tags are configured and deployed.

Now the app IIH Essentials needs to collect and store this data, to further use it within Performance Insight. Make sure the OPC UA Connector is activated within IIH Essentials.

![Connector](/docs/graphics/Connector.png)

Add the following PLC attributes to a new or existing asset:

![Variables](/docs/graphics/Variables.png)

## Configure Performance Insight

## Configure Reason Tree

The reason tree defines single error states that are mapped to one of these time categories:

- Production time
- Planned downtime
- Unplanned downtime

Go to *Configuration* > *Reason Tree* and configure it according to this example:

![ReasonTreeConfig](/docs/graphics/ReasonTreeConfig.png)

The export of this reason tree can be downloaded [here](/src/ReasonTree.zip) for using the function *Data export and import*.

As soon as the reason tree was configured, the single reasons with it's dedicated time category can be further used within the status mapping.

### Create status mappings

Status mappings can be used in a Gantt widget to visualize different values by colors and labels. Within Performance Insight we can create several status mappings for different use cases.

You can create simple mappings (value and label) or you can additionally use the time categories, if you need the status mapping for an OEE dashboard, to calculate the productivity of the plant.

**Status mapping for machine state**

The machine state of the plant is madatory for calculating the OEE values. You need to map the dedicated PLC parameter and also assign a time category for each status. All time categories (Net Production Time, Planned Downtime, Unplanned Downtime) must be covered by the mapping.

![OEE_Times](/docs/graphics/OEE_Times.png)

Go to *Configuration* > *Status mappings* and create a new status mapping according to this example:

![StatusMappingMachineState](/docs/graphics/StatusMapping_MachineState.png)

The export of this status mapping can be downloaded [here](/src/StatusMapping_MachineState.json) for using the function *Import status mapping*.

**Status mapping for error state**

For using the embedded OEE function *error analysis* you need an additional status mapping for the error codes.

Go to *Configuration* > *Status mappings* and create a new status mapping according to this example:

![StatusMappingErrorCode](/docs/graphics/StatusMapping_ErrorCode.png)

The export of this status mapping can be downloaded [here](/src/StatusMapping_ErrorCode.json) for using the function *Import status mapping*.


-----> HIER WEITER


### Create OEE dashboard

After we have prepared all necessary input data, we can create the OEE dashboard.

Therefore go to 'My Plant' and select the Asset 'OEE Data'. Click 'Add dashboard' and then 'OEE dashboard'. Within the OEE configuration window, proceed as following:

- select the previously created status mapping
- select a parameter that represents the machine status
- link the operand 'TotalCount' to the dedicated parameter and set the aggregation to 'Counter'
- link the operand 'TheroreticalSpeed' to a fixed number that represents the speed of your production in pcs/s (here the value 0,18 roughly reflects the speed of the simulated tank application)
- link the operand 'GoodCount' to the previously created KPI instance
- save the configuration

![OEEConfig](/docs/graphics/OEEConfig.png)

Now the dashboard is automatically created and can be used. Please find more information in the [Usage](/README.md#usage) chapter.
