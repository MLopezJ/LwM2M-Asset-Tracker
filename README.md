# LwM2M Asset Tracker

**Goal**: implement [LwM2M](https://www.openmobilealliance.org/release/LightweightM2M/V1_2-20201110-A/OMA-TS-LightweightM2M_Core-V1_2-20201110-A.pdf) protocol in [Asset Tracker](https://developer.nordicsemi.com/nRF_Connect_SDK/doc/latest/nrf/applications/asset_tracker_v2/README.html) and show how to do it.

**Why**: To make implementation of LwM2M easier for costumers

**How**: Using [Coiote](https://www.avsystem.com/products/iot-application-enablement/) from [AV System](https://www.avsystem.com/), which is a LwM2M server, to send data from a device to a cloud provided already used by Asset Tracker.

## Steps

| Name | -- | -- | -- | -- |
| -- | -- | -- | -- | -- |
| Device Connection | ---> |  |  |  |
| Device Simulator |  | ---> |  |  |
| Coiote Result Transformation |  |  | ---> |  |
| Asset Tracker Connection |  |  |  | ---> |

## Device Connection
* **Goal**: send data from Thingy:91 to a cloud provider through an integration with Coiote
* **How**: Connect the Thingy:91 with nRF Asset Tracker firmware to Coiote and then, implement integration between Coiote and available cloud providers. 
* **Link**: [Connection: Thingy:91 -> Coiote -> Cloud provider](https://github.com/MLopezJ/thingy91-coiote-cloud-connection)

## Device Simulator
* **Goal**: Send and upate data from a simulate device to Coiote
* **How**: Uses LwM2M protocol to connect to Coiote
* **Link**: [LwM2M Device Simulator](https://github.com/MLopezJ/LwM2M-device-simulator)

## Coiote Result Transformation
* **Goal**: Take the result from the cloud integration and transform it from Coiote format to Asset Tracker format
* **How**: Check types and build Asset Tracker expected input object

## Asset Tracker Connection
* **Goal**: Connect the cloud instance with Asset Tracker web application 
* **How**: Implement the transformation process of last step in the cloud provider, this way the data is already transformed before send it to Asset Tracker
