# UaExpert Usage

## Connect to OPC UA Server

1. Go to `https://www.unified-automation.com/downloads.html` to register and download UaExpert and install it.

2. Open UaExpert software, click the toolbar `+` button, double click **Custom Discovery** -> **< Double click to Add Server... >**, in the pop-up dialog box, fill in the access address of OPC UA Server, click `OK` and the address will be added to the end of the list.
  ![uaexpert1](./assets/uaexpert1.jpg)

3. Fully expand the child nodes under Access Addresses, double click on the appropriate connection policy and the connection will be added to UaExpert's **Project** view.
  ![uaexpert2](./assets/uaexpert2.jpg)

4. Right-click on the target OPC UA Server (SIMATIC.S7-1200... in the example) under **Servers** in the **Project** view on the left. and select the `Connect` interface in the pop-up menu to connect to the target server.
  ![uaexpert3](./assets/uaexpert3.jpg)

5. Expand the child nodes in the **Address Space** view on the left to see the address information of the corresponding node in **Attributes** on the right, where `NamespaceIndex` is the **Namespace Index** and `Identifier` is the **Node ID**.
  ![uaexpert4](./assets/uaexpert4.jpg)

6. Drag the child node in the **Address Space** view to the **Data Access View** view to see the data type of the node.
  ![uaexpert5](./assets/uaexpert5.jpg)

7. Set the type of measurement point for the Neuron OPC UA plug-in according to the type information in the **Data Access View** view.
