# SAP UI5 Demo Aggregation Binding Using List

In SAPUI5, aggregation binding is a key concept used to bind and display data within UI controls that have aggregations. Aggregations are collections of elements or controls within a UI control, and aggregation binding allows you to dynamically populate and update these collections based on data from a model.

### Code Explaination

Refer to [/webapp/Invoices.json](https://github.com/VaibhavMojidra/SAP-UI5---Demo-Aggregation-Binding-Using-List/blob/master/webapp/Invoices.json "Invoices.json")

A list of invoices for different products. Each invoice is represented as a JSON object with the following properties:

- `"ProductName"`: The name of the product.
- `"Quantity"`: The quantity of the product.
- `"ExtendedPrice"`: The total price for the quantity of the product.
- `"ShipperName"`: The name of the shipper.
- `"ShippedDate"`: The date when the product was shipped.
- `"Status"`: The status of the shipment.
- `"UnitPrice"`: The price per unit of the product.
- `"Discount"`: The discount applied to the product.


Refer to [/webapp/manifest.json](https://github.com/VaibhavMojidra/SAP-UI5---Demo-Aggregation-Binding-Using-List/blob/master/webapp/manifest.json "manifest.json")

- `"sap.ui5"`: This is the namespace for SAP UI5 configuration.
- `"models"`: This is where you define the models for your application. Models in SAP UI5 are used to bind data to your views.
- `"invoice"`: This is the name of the model. You can use this name to refer to this model in your views.
- `"type"`: This defines the type of the model. In this case, it's a JSON model (`"sap.ui.model.json.JSONModel"`), which means the data will be in JSON format.
- `"uri"`: This is the path to the data for your model. In this case, it's `Invoices.json`, which means the data for this model will be loaded from this file.

This code is defining a JSON model named `invoice` that will load its data from a file named `Invoices.json`. You can then bind this data to your views using the model name `invoice`.

Refer to [/webapp/view/InvoiceList.view.xml](https://github.com/VaibhavMojidra/SAP-UI5---Demo-Aggregation-Binding-Using-List/blob/master/webapp/view/InvoiceList.view.xml "InvoiceList.view.xml")

- `<mvc:View xmlns="sap.m" xmlns:mvc="sap.ui.core.mvc">`: This is the root element of the view. It declares the XML namespaces for the core and mobile libraries of SAPUI5.

- `<List headerText="Invoices" class="sapUiResponsiveMargin" width="auto" items="{invoice>/Invoices}">`: This creates a List control with the header text "Invoices". The list items are bound to the "/Invoices" path of the "invoice" model. The class "sapUiResponsiveMargin" is added for responsive margining, and the width is set to "auto".

- `<items>`: This is where you define what each item in the list will look like.

- `<ObjectListItem title="{invoice>Quantity} x {invoice>ProductName}"/>`: For each item in the list, an ObjectListItem is created. The title of each item is set to be a string that includes the Quantity and ProductName properties from the "invoice" model, separated by an 'x'. For example, if Quantity is 5 and ProductName is "Apples", the title will be "5 x Apples".

- `</items>` and `</List>`: These close the items and List elements.

- `</mvc:View>`: This closes the View element.

So, this code will display a list of invoices, where each invoice shows a quantity and product name. The data for these invoices comes from the "invoice" model.


---

[![Vaibhav Mojidra - 1.jpeg](https://raw.githubusercontent.com/VaibhavMojidra/SAP-UI5---Demo-Aggregation-Binding-Using-List/master/screenshot/1.jpeg "Vaibhav Mojidra")](https://vaibhavmojidra.github.io/site/)