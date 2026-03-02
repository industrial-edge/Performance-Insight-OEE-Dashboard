# Simulate OEE data

- [Simulate OEE data](#simulate-oee-data)
  - [Setup Flow Creator](#setup-flow-creator)
  - [Configure IIH Essentials](#configure-iih-essentials)

With this instruction you can easily simulate some OEE values for using them within an OEE dashboard.

## Setup Flow Creator

Within the app Flow Creator you are able to simulate those OEE parameters:

- Machine status
- Error status
- Total count
- Good count

The following steps needs to be done:

- Open the app Flow Creator
- Click on the menu > Import
- Select [this](../src/FlowCreatorOEESim.json) .json file and import it

After importing the file, the databus credentials must be adapted for the MQTT nodes:

- Double click on each MQTT node to open the settings
- Click on the edit symbol for the *Server*
- Select tab *Security*
- Enter the correct databus credentials
- Click *Update* to save your changes
- Deploy the flow

![FlowCreatorMQTT](/docs/graphics/FlowCreator_MQTT_nodes.png)

To start the data simulation, you need to click one time on the *timestamp* node. Thereby the MQTT metadata for the four parameter is generated and the simulated data records are published to the Databus each 500 ms.

![FlowCreatorStartSimulation](/docs/graphics/FlowCreator_StartSimulation.png)

## Configure IIH Essentials

First, you need to configure the Databus credentials:

- Open the app IIH Essentials
- In the menu, go to *Settings* > *Databus settings*
- Enter the correct broker URL as well as the dedicated credentials
- Click *Update* to save your settings

Next, you need to create a new connector for receiving the simulated data from Flow Creator:

- In the menu, go to *Get data*
- Click the plus symbol to add a new connector
- Name = any userdefined name
- Activate option *Use Databus settings*
- Metadata topic = *ie/m/j/simatic/v1/sim/dp*
- Click on *Add*

![IIHEssentialsConnector](/docs/graphics/IIH_Essentials_Connector.png)

Finally, the four simulated parameters must be added to an asset:

- In the menu, go to *Manage data*
- Select the dedicated asset where the OEE dashboard will be created
- On the right side > *Connections* > select the newly created connector
- Select all four parameters and drag them into the main area to add them to the asset

![IIHEssentialsAttributes](/docs/graphics/IIH_Essentials_Attributes.png)

Now the following parameters were added to the asset:
  - *ErrorCode*
  - *MachineStateOEE*
  - *NumberGood*
  - *NumberProduced*

See chapter [Configure Performance Insight](/docs/Installation.md#configure-performance-insight) to proceed with the configuration of the OEE dashboard within Performance Insight.
