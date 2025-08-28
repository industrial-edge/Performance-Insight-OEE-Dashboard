# Configuration

- [Configuration](#configuration)
  - [Configure IIH Essentials](#configure-iih-essentials)
  - [Configure Performance Insight](#configure-performance-insight)
    - [Configure Reason Tree](#configure-reason-tree)
    - [Create status mappings](#create-status-mappings)
    - [Create OEE dashboard](#create-oee-dashboard)
  
## Configure IIH Essentials

The PLC with the running TIA project is connected via the OPC UA connector to the Industrial Edge Device (IED). Within the connector, all necessary tags are configured and deployed.

Now the app IIH Essentials needs to collect and store this data, to further use it within Performance Insight.

- Make sure the OPC UA Connector is activated within IIH Essentials

![Connector](/docs/graphics/Connector.png)

- Add the following PLC attributes to a new or existing asset:
  - *GDB.operate.machineStateOEE*
  - *GDB.process.numberGood*
  - *GDB.process.numberProduced*
  - *GDB.signals.errorCode*

![Variables](/docs/graphics/Variables.png)

## Configure Performance Insight

## Configure Reason Tree

The reason tree defines single error states that are mapped to one of the three main time categories (Production time / Planned downtime / Unplanned downtime).

- Go to *Configuration* > *Reason Tree*
- Configure it according to this example:

![ReasonTreeConfig](/docs/graphics/ReasonTreeConfig.png)

The export of this reason tree can be downloaded [here](/src/ReasonTree.zip) for using the function *Data export and import*.

As soon as the reason tree was configured, the single reasons with it's dedicated time category can be further used within the status mapping.

### Create status mappings

Status mappings can be used in a Gantt widget to visualize different values by colors and labels. Within Performance Insight we can create several status mappings for different use cases.

You can create simple mappings (value and label) or you can additionally use the time categories, if you need the status mapping for an OEE dashboard, to calculate the productivity of the plant.

**Status mapping for machine state**

The machine state of the plant is madatory for calculating the OEE values. You need to map the dedicated PLC parameter and also assign a time category for each status. All time categories (Net Production Time, Planned Downtime, Unplanned Downtime) must be covered by the mapping.

![OEE_Times](/docs/graphics/OEE_Times.png)

- Go to *Configuration* > *Status mappings*
- Create a new status mapping according to this example:

![StatusMappingMachineState](/docs/graphics/StatusMapping_MachineState.png)

The export of this status mapping can be downloaded [here](/src/MachineState.json) for using the function *Import status mapping*.

**Status mapping for error state**

For using the embedded OEE function *error analysis* you need an additional status mapping for the error codes.

- Go to *Configuration* > *Status mappings*
- Create a new status mapping according to this example:

![StatusMappingErrorCode](/docs/graphics/StatusMapping_ErrorCode.png)

The export of this status mapping can be downloaded [here](/src/ErrorCode.json) for using the function *Import status mapping*.

### Create OEE dashboard

After preparing all necessary input data, you can configure the OEE dashboard.

- Go to *My Plant* and select the dedicated asset
- Click *Add dashboard* > *OEE dashboard*

The OEE configuration opens. Set the configuration as following:

Section 1:
- *Machine status variable* = parameter *GDB.operate.machineStateOEE* (representing the machine state)
- *Status assignment* = status mapping *MachineState*

Section 2:
- *Error status variable* = *GDB.signals.errorCode* (representing the error status)
- *Status assignment* = status mapping *ErrorCode*

Section 4:
- *TotalCount* = parameter *GDB.process.numberProduced*; set the aggregation to *Counter*
- *TheoreticalSpeed* = 2500 pcs/h (representing the speed of production)
- *GoodCount* = parameter *GDB.process.numberGood*; set the aggregation to *Counter*

All other fields are prefilled an must not be adapted.

- Save the configuration

![OEEConfig](/docs/graphics/OEEConfig.png)

Now the dashboard is automatically created and can be used.

See the chapter [Usage](/README.md#usage) to discover further information.
