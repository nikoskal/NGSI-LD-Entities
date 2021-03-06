# Machine Model
This entity contains a harmonised description of a generic machine model. This entity is primarily associated with the industry segment and related IoT applications. The machineModel includes a hierarchical structure that allows machine models to be grouped in a flexible way.

| Attribute Name | Attribute Type | Description | Constraint |
|:--- |:--- |:--- |:---:|
| id | @id | Provides a unique identifier for an instance of the entity either in the form of a URI (i.e. either a publicly accessible URL or a URN). | Mandatory |
| type | @type | Defines the type of the entity. | Mandatory |
| createdAt | TemporalProperty | Indicates the date/ time that the instance of the entity was created in ISO 8601 format. The value of this will be set by the server when the entity was created. | Mandatory |
| modifiedAt | TemporalProperty | Indicates the date/ time when the entity was last modified in ISO 8601 format. The value of this will be set by the server when the entity was modified, if the entity has not been modified it may have a null value. | Optional |
| source | Property | Specifies the URL to the source of this data (either organisation or where relevant more specific source) | Recommended |
| dataProvider | Property | Specifies the URL to information about the provider of this information | Recommended |
| entityVersion | Property | The entity specification version as a number. A version number of 2.0 or later denotes the entity is represented using NGSI-LD | Recommended |
| name | Property | The name given to this MachineModel. | Mandatory |
| doc | Property | Reference to data sheet or other manufacturer’s documentation about this MachineModel. | Recommended |
| description | Property | A description of this MachineModel. | Recommended |
| manufacturerName | Property | The name of manufacturer of this MachineModel. | Recommended |
| brandName | Property | The brand name of this MachineModel. | Recommended |
| version | Property | The manufacturer defined version number for the machine model. | Recommended |
| category | Property | A List of functional categories which this machineModel supports. Examples include: **robot, cnc, 2dPrinter, 3dPrinter, 3dScanner, lathe, injectionMolding, laserCutter, millingMachine, grindingMachine, stampingMachine, oven, kiln, packaging, mixer, dryer, fan, saw.** | Optional |
| root | Property | A logical indicator that this MachineModel is the root of a MachineModel hierarchy. True indicates it is the root, false indicates that it is not the root. | Mandatory |
| machineModelParent | Relationship | References any higher level MachineModel that this machine model is based on. | Optional |
| machineModelChildren | Relationship | References any lower level MachineModel entities that are based on this machine model. | Optional |
| processDescription | Property | A description of the industrial process carried out by this machine. | Optional |
| standardOperations | Property | Lists the standard set of operations supported by this machineModel. | Optional |

## NGSI-LD Context Definition
The following NGSI-LD context definition applies to the **Machine Model** entity

[Download context definition.](../examples/Machine-Model-context.jsonld)

```JavaScript
{
    "@context": {
        "source": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/source",
        "dataProvider": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/dataprovider",
        "entityVersion": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/entityversion",
        "name": "https://schema.org/name",
        "doc": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/doc",
        "description": "https://schema.org/description",
        "manufacturerName": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/manufacturername",
        "brandName": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/brandname",
        "version": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/version",
        "category": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/category",
        "root": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/root",
        "machineModelParent": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/machinemodelparent",
        "machineModelChildren": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/machinemodelchildren",
        "processDescription": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/processdescription",
        "standardOperations": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/standardoperations"
    }
}
```
## Example of Machine Model Entity
The following is an example instance of the **Machine Model** entity

[Download example entity definition.](../examples/Machine-Model.jsonld)

```JavaScript
{
    "@context": [
        "https://forge.etsi.org/gitlab/NGSI-LD/NGSI-LD/raw/master/coreContext/ngsi-ld-core-context.json",
        "https://raw.githubusercontent.com/GSMADeveloper/NGSI-LD-Entities/master/examples/Machine-Model-context.jsonld"
    ],
    "id": "urn:ngsi-ld:MachineModel:e01f13d1-fea4-4cc4-92c9-0d9fadb2c509",
    "type": "MachineModel",
    "createdAt": "2017-01-01T01:20:00Z",
    "modifiedAt": "2017-05-04T12:30:00Z",
    "source": "https://source.example.com",
    "dataProvider": "https://provider.example.com",
    "entityVersion": 2.0,
    "name": {
        "type": "Property",
        "value": "CA1256b"
    },
    "doc": {
        "type": "Property",
        "value": {
            "@value": "https://example.com",
            "@type": "https://schema.org/url"
        }
    },
    "description": {
        "type": "Property",
        "value": "Machine to screen print t-shirts"
    },
    "manufacturerName": {
        "type": "Property",
        "value": "ScreenOPrint, Inc."
    },
    "brandName": {
        "type": "Property",
        "value": "QuickT"
    },
    "version": {
        "type": "Property",
        "value": "v1"
    },
    "category": {
        "type": "Property",
        "value": [
            "2dPrinter"
        ]
    },
    "root": {
        "type": "Property",
        "value": false
    },
    "machineModelParent": {
        "type": "Relationship",
        "object": "urn:ngsi-ld:MachineModel:4146335f-839f-4ff9-a575-6b4e6232b734"
    },
    "machineModelChildren": {
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:MachineModel:a74fcf24-58fa-11e8-ae3e-df1abd78f83f",
            "urn:ngsi-ld:MachineModel:b29330f6-58fa-11e8-93b5-1379ded6eef6"
        ]
    },
    "processDescription": {
        "type": "Property",
        "value": "Industrial printer used to mass print t-shirts"
    },
    "standardOperations": {
        "type": "Property",
        "value": [
            "print"
        ]
    }
}
```
