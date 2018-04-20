# Agri Pest
This entity contains a harmonised description of an agricultural pest. This entity is primarily associated with the agricultural vertical and related IoT applications.

| Attribute Name | Attribute Type | Description | Constraint |
|:--- |:--- |:--- |:---:|
| id | @id | Provides a unique identifier for an instance of the entity either in the form of a URI (i.e. either a publicly accessible URL or a URN). | Mandatory |
| type | @type | Defines the type of the entity. | Mandatory |
| createdAt | DateTime | Indicates the date/ time that the instance of the entity was created in ISO 8601 format. The value of this will be set by the server when the entity was created. | Mandatory |
| modifiedAt | DateTime | Indicates the date/ time when the entity was last modified in ISO 8601 format. The value of this will be set by the server when the entity was modified, if the entity has not been modified it may have a null value. | Optional |
| source | Property | Specifies the URL to the source of this data (either organisation or where relevant more specific source) | Recommended |
| dataProvider | Property | Specifies the URL to information about the provider of this information | Recommended |
| entityVersion | Property | The entity specification version as a number. A version number of 2.0 or later denotes the entity is represented using NGSI-LD | Recommended |
| name | Property | The name of this agricultural pest. | Mandatory |
| alternateName | Property | Alternative name of this agricultural pest. | Optional |
| description | Property | A description of this agricultural pest. | Recommended |
| agriProduct | Relationship | Reference to the recommended types of product that can be used to treat this pest. | Optional |

## NGSI-LD Context Definition
The following NGSI-LD context definition applies to the **Agri Pest** entity

[Download context definition.](../examples/Agri-Pest-context.jsonld)

```JavaScript
{
    "id": "@id",
    "type": "@type",
    "DateTime": "http://uri.etsi.org/ngsi-ld/DateTime",
    "createdAt": {
        "@id": "http://uri.etsi.org/ngsi-ld/createdAt",
        "@type": "DateTime"
    },
    "modifiedAt": {
        "@id": "http://uri.etsi.org/ngsi-ld/modifiedAt",
        "@type": "DateTime"
    },
    "Property": "http://etsi.org/nsgi-ld/Property",
    "Relationship": "http://uri.etsi.org/ngsi-ld/Relationship"
}
```
## Example of Agri Pest Entity
The following is an example instance of the **Agri Pest** entity

[Download example entity definition.](../examples/Agri-Pest.jsonld)

```JavaScript
{
    "@context": [
        "https://example.com/contexts/coreContext.jsonld",
        "https://example.com/contexts/agri-pest.jsonld"
    ],
    "id": "urn:ngsi-ld:AgriPest:fb3f1295-500c-4aa3-b995-c909097d5c01",
    "type": "AgriPest",
    "createdAt": "2017-01-01T01:20:00Z",
    "modifiedAt": "2017-05-04T12:30:00Z",
    "source": "https://source.example.com",
    "dataProvider": "https://provider.example.com",
    "entityVersion": 2.0,
    "name": {
        "type": "Property",
        "value": "Grasshopper"
    },
    "alternateName": {
        "type": "Property",
        "value": "Chorthippus parallelus"
    },
    "description": {
        "type": "Property",
        "value": "Common European grasshopper"
    },
    "agriProduct": {
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:AgriProduct:06afffde-4488-11e8-861a-cfcf50aaa9cc",
            "urn:ngsi-ld:AgriProduct:0c094486-4488-11e8-a15f-afa816790c64",
            "urn:ngsi-ld:AgriProduct:14bf9f26-4488-11e8-9e3d-bfb78de66dd3"
        ]
    }
}
```