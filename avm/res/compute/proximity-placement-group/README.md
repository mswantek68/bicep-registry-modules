# Proximity Placement Groups `[Microsoft.Compute/proximityPlacementGroups]`

This module deploys a Proximity Placement Group.

## Navigation

- [Resource Types](#Resource-Types)
- [Usage examples](#Usage-examples)
- [Parameters](#Parameters)
- [Outputs](#Outputs)
- [Cross-referenced modules](#Cross-referenced-modules)
- [Data Collection](#Data-Collection)

## Resource Types

| Resource Type | API Version |
| :-- | :-- |
| `Microsoft.Authorization/locks` | [2020-05-01](https://learn.microsoft.com/en-us/azure/templates/Microsoft.Authorization/2020-05-01/locks) |
| `Microsoft.Authorization/roleAssignments` | [2022-04-01](https://learn.microsoft.com/en-us/azure/templates/Microsoft.Authorization/2022-04-01/roleAssignments) |
| `Microsoft.Compute/proximityPlacementGroups` | [2022-08-01](https://learn.microsoft.com/en-us/azure/templates/Microsoft.Compute/2022-08-01/proximityPlacementGroups) |

## Usage examples

The following section provides usage examples for the module, which were used to validate and deploy the module successfully. For a full reference, please review the module's test folder in its repository.

>**Note**: Each example lists all the required parameters first, followed by the rest - each in alphabetical order.

>**Note**: To reference the module, please use the following syntax `br/public:avm/res/compute/proximity-placement-group:<version>`.

- [Using only defaults](#example-1-using-only-defaults)
- [Using large parameter set](#example-2-using-large-parameter-set)
- [WAF-aligned](#example-3-waf-aligned)

### Example 1: _Using only defaults_

This instance deploys the module with the minimum set of required parameters.


<details>

<summary>via Bicep module</summary>

```bicep
module proximityPlacementGroup 'br/public:avm/res/compute/proximity-placement-group:<version>' = {
  name: 'proximityPlacementGroupDeployment'
  params: {
    // Required parameters
    availabilityZone: -1
    name: 'cppgmin001'
    // Non-required parameters
    location: '<location>'
  }
}
```

</details>
<p>

<details>

<summary>via JSON parameters file</summary>

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentParameters.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {
    // Required parameters
    "availabilityZone": {
      "value": -1
    },
    "name": {
      "value": "cppgmin001"
    },
    // Non-required parameters
    "location": {
      "value": "<location>"
    }
  }
}
```

</details>
<p>

<details>

<summary>via Bicep parameters file</summary>

```bicep-params
using 'br/public:avm/res/compute/proximity-placement-group:<version>'

// Required parameters
param availabilityZone = -1
param name = 'cppgmin001'
// Non-required parameters
param location = '<location>'
```

</details>
<p>

### Example 2: _Using large parameter set_

This instance deploys the module with most of its features enabled.


<details>

<summary>via Bicep module</summary>

```bicep
module proximityPlacementGroup 'br/public:avm/res/compute/proximity-placement-group:<version>' = {
  name: 'proximityPlacementGroupDeployment'
  params: {
    // Required parameters
    availabilityZone: 1
    name: 'cppgmax001'
    // Non-required parameters
    colocationStatus: {
      code: 'ColocationStatus/Aligned'
      displayStatus: 'Aligned'
      level: 'Info'
      message: 'I\'m a default error message'
    }
    intent: {
      vmSizes: [
        'Standard_B1ms'
        'Standard_B4ms'
      ]
    }
    location: '<location>'
    lock: {
      kind: 'CanNotDelete'
      name: 'myCustomLockName'
    }
    roleAssignments: [
      {
        name: '9e0b6b99-ff4b-4c99-a2ce-3a2a1a880874'
        principalId: '<principalId>'
        principalType: 'ServicePrincipal'
        roleDefinitionIdOrName: 'Owner'
      }
      {
        name: '<name>'
        principalId: '<principalId>'
        principalType: 'ServicePrincipal'
        roleDefinitionIdOrName: 'b24988ac-6180-42a0-ab88-20f7382dd24c'
      }
      {
        principalId: '<principalId>'
        principalType: 'ServicePrincipal'
        roleDefinitionIdOrName: '<roleDefinitionIdOrName>'
      }
    ]
    tags: {
      'hidden-title': 'This is visible in the resource name'
      TagA: 'Would you kindly...'
      TagB: 'Tags for sale'
    }
    type: 'Standard'
  }
}
```

</details>
<p>

<details>

<summary>via JSON parameters file</summary>

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentParameters.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {
    // Required parameters
    "availabilityZone": {
      "value": 1
    },
    "name": {
      "value": "cppgmax001"
    },
    // Non-required parameters
    "colocationStatus": {
      "value": {
        "code": "ColocationStatus/Aligned",
        "displayStatus": "Aligned",
        "level": "Info",
        "message": "I\"m a default error message"
      }
    },
    "intent": {
      "value": {
        "vmSizes": [
          "Standard_B1ms",
          "Standard_B4ms"
        ]
      }
    },
    "location": {
      "value": "<location>"
    },
    "lock": {
      "value": {
        "kind": "CanNotDelete",
        "name": "myCustomLockName"
      }
    },
    "roleAssignments": {
      "value": [
        {
          "name": "9e0b6b99-ff4b-4c99-a2ce-3a2a1a880874",
          "principalId": "<principalId>",
          "principalType": "ServicePrincipal",
          "roleDefinitionIdOrName": "Owner"
        },
        {
          "name": "<name>",
          "principalId": "<principalId>",
          "principalType": "ServicePrincipal",
          "roleDefinitionIdOrName": "b24988ac-6180-42a0-ab88-20f7382dd24c"
        },
        {
          "principalId": "<principalId>",
          "principalType": "ServicePrincipal",
          "roleDefinitionIdOrName": "<roleDefinitionIdOrName>"
        }
      ]
    },
    "tags": {
      "value": {
        "hidden-title": "This is visible in the resource name",
        "TagA": "Would you kindly...",
        "TagB": "Tags for sale"
      }
    },
    "type": {
      "value": "Standard"
    }
  }
}
```

</details>
<p>

<details>

<summary>via Bicep parameters file</summary>

```bicep-params
using 'br/public:avm/res/compute/proximity-placement-group:<version>'

// Required parameters
param availabilityZone = 1
param name = 'cppgmax001'
// Non-required parameters
param colocationStatus = {
  code: 'ColocationStatus/Aligned'
  displayStatus: 'Aligned'
  level: 'Info'
  message: 'I\'m a default error message'
}
param intent = {
  vmSizes: [
    'Standard_B1ms'
    'Standard_B4ms'
  ]
}
param location = '<location>'
param lock = {
  kind: 'CanNotDelete'
  name: 'myCustomLockName'
}
param roleAssignments = [
  {
    name: '9e0b6b99-ff4b-4c99-a2ce-3a2a1a880874'
    principalId: '<principalId>'
    principalType: 'ServicePrincipal'
    roleDefinitionIdOrName: 'Owner'
  }
  {
    name: '<name>'
    principalId: '<principalId>'
    principalType: 'ServicePrincipal'
    roleDefinitionIdOrName: 'b24988ac-6180-42a0-ab88-20f7382dd24c'
  }
  {
    principalId: '<principalId>'
    principalType: 'ServicePrincipal'
    roleDefinitionIdOrName: '<roleDefinitionIdOrName>'
  }
]
param tags = {
  'hidden-title': 'This is visible in the resource name'
  TagA: 'Would you kindly...'
  TagB: 'Tags for sale'
}
param type = 'Standard'
```

</details>
<p>

### Example 3: _WAF-aligned_

This instance deploys the module in alignment with the best-practices of the Azure Well-Architected Framework.


<details>

<summary>via Bicep module</summary>

```bicep
module proximityPlacementGroup 'br/public:avm/res/compute/proximity-placement-group:<version>' = {
  name: 'proximityPlacementGroupDeployment'
  params: {
    // Required parameters
    availabilityZone: 1
    name: 'cppgwaf001'
    // Non-required parameters
    colocationStatus: {
      code: 'ColocationStatus/Aligned'
      displayStatus: 'Aligned'
      level: 'Info'
      message: 'I\'m a default error message'
    }
    intent: {
      vmSizes: [
        'Standard_B1ms'
        'Standard_B4ms'
      ]
    }
    location: '<location>'
    tags: {
      'hidden-title': 'This is visible in the resource name'
      TagA: 'Would you kindly...'
      TagB: 'Tags for sale'
    }
    type: 'Standard'
  }
}
```

</details>
<p>

<details>

<summary>via JSON parameters file</summary>

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentParameters.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {
    // Required parameters
    "availabilityZone": {
      "value": 1
    },
    "name": {
      "value": "cppgwaf001"
    },
    // Non-required parameters
    "colocationStatus": {
      "value": {
        "code": "ColocationStatus/Aligned",
        "displayStatus": "Aligned",
        "level": "Info",
        "message": "I\"m a default error message"
      }
    },
    "intent": {
      "value": {
        "vmSizes": [
          "Standard_B1ms",
          "Standard_B4ms"
        ]
      }
    },
    "location": {
      "value": "<location>"
    },
    "tags": {
      "value": {
        "hidden-title": "This is visible in the resource name",
        "TagA": "Would you kindly...",
        "TagB": "Tags for sale"
      }
    },
    "type": {
      "value": "Standard"
    }
  }
}
```

</details>
<p>

<details>

<summary>via Bicep parameters file</summary>

```bicep-params
using 'br/public:avm/res/compute/proximity-placement-group:<version>'

// Required parameters
param availabilityZone = 1
param name = 'cppgwaf001'
// Non-required parameters
param colocationStatus = {
  code: 'ColocationStatus/Aligned'
  displayStatus: 'Aligned'
  level: 'Info'
  message: 'I\'m a default error message'
}
param intent = {
  vmSizes: [
    'Standard_B1ms'
    'Standard_B4ms'
  ]
}
param location = '<location>'
param tags = {
  'hidden-title': 'This is visible in the resource name'
  TagA: 'Would you kindly...'
  TagB: 'Tags for sale'
}
param type = 'Standard'
```

</details>
<p>

## Parameters

**Required parameters**

| Parameter | Type | Description |
| :-- | :-- | :-- |
| [`availabilityZone`](#parameter-availabilityzone) | int | Specifies the Availability Zone where virtual machine, virtual machine scale set or availability set associated with the proximity placement group can be created. If set to 1, 2 or 3, the availability zone is hardcoded to that value. If set to -1, no zone is defined. Note that the availability zone numbers here are the logical availability zone in your Azure subscription. Different subscriptions might have a different mapping of the physical zone and logical zone. To understand more, please refer to [Physical and logical availability zones](https://learn.microsoft.com/en-us/azure/reliability/availability-zones-overview?tabs=azure-cli#physical-and-logical-availability-zones). |
| [`name`](#parameter-name) | string | The name of the proximity placement group that is being created. |

**Optional parameters**

| Parameter | Type | Description |
| :-- | :-- | :-- |
| [`colocationStatus`](#parameter-colocationstatus) | object | Describes colocation status of the Proximity Placement Group. |
| [`enableTelemetry`](#parameter-enabletelemetry) | bool | Enable/Disable usage telemetry for module. |
| [`intent`](#parameter-intent) | object | Specifies the user intent of the proximity placement group. |
| [`location`](#parameter-location) | string | Resource location. |
| [`lock`](#parameter-lock) | object | The lock settings of the service. |
| [`roleAssignments`](#parameter-roleassignments) | array | Array of role assignments to create. |
| [`tags`](#parameter-tags) | object | Tags of the proximity placement group resource. |
| [`type`](#parameter-type) | string | Specifies the type of the proximity placement group. |

### Parameter: `availabilityZone`

Specifies the Availability Zone where virtual machine, virtual machine scale set or availability set associated with the proximity placement group can be created. If set to 1, 2 or 3, the availability zone is hardcoded to that value. If set to -1, no zone is defined. Note that the availability zone numbers here are the logical availability zone in your Azure subscription. Different subscriptions might have a different mapping of the physical zone and logical zone. To understand more, please refer to [Physical and logical availability zones](https://learn.microsoft.com/en-us/azure/reliability/availability-zones-overview?tabs=azure-cli#physical-and-logical-availability-zones).

- Required: Yes
- Type: int
- Allowed:
  ```Bicep
  [
    -1
    1
    2
    3
  ]
  ```

### Parameter: `name`

The name of the proximity placement group that is being created.

- Required: Yes
- Type: string

### Parameter: `colocationStatus`

Describes colocation status of the Proximity Placement Group.

- Required: No
- Type: object

### Parameter: `enableTelemetry`

Enable/Disable usage telemetry for module.

- Required: No
- Type: bool
- Default: `True`

### Parameter: `intent`

Specifies the user intent of the proximity placement group.

- Required: No
- Type: object

### Parameter: `location`

Resource location.

- Required: No
- Type: string
- Default: `[resourceGroup().location]`

### Parameter: `lock`

The lock settings of the service.

- Required: No
- Type: object

**Optional parameters**

| Parameter | Type | Description |
| :-- | :-- | :-- |
| [`kind`](#parameter-lockkind) | string | Specify the type of lock. |
| [`name`](#parameter-lockname) | string | Specify the name of lock. |

### Parameter: `lock.kind`

Specify the type of lock.

- Required: No
- Type: string
- Allowed:
  ```Bicep
  [
    'CanNotDelete'
    'None'
    'ReadOnly'
  ]
  ```

### Parameter: `lock.name`

Specify the name of lock.

- Required: No
- Type: string

### Parameter: `roleAssignments`

Array of role assignments to create.

- Required: No
- Type: array
- Roles configurable by name:
  - `'Contributor'`
  - `'Owner'`
  - `'Reader'`
  - `'Role Based Access Control Administrator'`
  - `'User Access Administrator'`

**Required parameters**

| Parameter | Type | Description |
| :-- | :-- | :-- |
| [`principalId`](#parameter-roleassignmentsprincipalid) | string | The principal ID of the principal (user/group/identity) to assign the role to. |
| [`roleDefinitionIdOrName`](#parameter-roleassignmentsroledefinitionidorname) | string | The role to assign. You can provide either the display name of the role definition, the role definition GUID, or its fully qualified ID in the following format: '/providers/Microsoft.Authorization/roleDefinitions/c2f4ef07-c644-48eb-af81-4b1b4947fb11'. |

**Optional parameters**

| Parameter | Type | Description |
| :-- | :-- | :-- |
| [`condition`](#parameter-roleassignmentscondition) | string | The conditions on the role assignment. This limits the resources it can be assigned to. e.g.: @Resource[Microsoft.Storage/storageAccounts/blobServices/containers:ContainerName] StringEqualsIgnoreCase "foo_storage_container". |
| [`conditionVersion`](#parameter-roleassignmentsconditionversion) | string | Version of the condition. |
| [`delegatedManagedIdentityResourceId`](#parameter-roleassignmentsdelegatedmanagedidentityresourceid) | string | The Resource Id of the delegated managed identity resource. |
| [`description`](#parameter-roleassignmentsdescription) | string | The description of the role assignment. |
| [`name`](#parameter-roleassignmentsname) | string | The name (as GUID) of the role assignment. If not provided, a GUID will be generated. |
| [`principalType`](#parameter-roleassignmentsprincipaltype) | string | The principal type of the assigned principal ID. |

### Parameter: `roleAssignments.principalId`

The principal ID of the principal (user/group/identity) to assign the role to.

- Required: Yes
- Type: string

### Parameter: `roleAssignments.roleDefinitionIdOrName`

The role to assign. You can provide either the display name of the role definition, the role definition GUID, or its fully qualified ID in the following format: '/providers/Microsoft.Authorization/roleDefinitions/c2f4ef07-c644-48eb-af81-4b1b4947fb11'.

- Required: Yes
- Type: string

### Parameter: `roleAssignments.condition`

The conditions on the role assignment. This limits the resources it can be assigned to. e.g.: @Resource[Microsoft.Storage/storageAccounts/blobServices/containers:ContainerName] StringEqualsIgnoreCase "foo_storage_container".

- Required: No
- Type: string

### Parameter: `roleAssignments.conditionVersion`

Version of the condition.

- Required: No
- Type: string
- Allowed:
  ```Bicep
  [
    '2.0'
  ]
  ```

### Parameter: `roleAssignments.delegatedManagedIdentityResourceId`

The Resource Id of the delegated managed identity resource.

- Required: No
- Type: string

### Parameter: `roleAssignments.description`

The description of the role assignment.

- Required: No
- Type: string

### Parameter: `roleAssignments.name`

The name (as GUID) of the role assignment. If not provided, a GUID will be generated.

- Required: No
- Type: string

### Parameter: `roleAssignments.principalType`

The principal type of the assigned principal ID.

- Required: No
- Type: string
- Allowed:
  ```Bicep
  [
    'Device'
    'ForeignGroup'
    'Group'
    'ServicePrincipal'
    'User'
  ]
  ```

### Parameter: `tags`

Tags of the proximity placement group resource.

- Required: No
- Type: object

### Parameter: `type`

Specifies the type of the proximity placement group.

- Required: No
- Type: string
- Default: `'Standard'`
- Allowed:
  ```Bicep
  [
    'Standard'
    'Ultra'
  ]
  ```

## Outputs

| Output | Type | Description |
| :-- | :-- | :-- |
| `location` | string | The location the resource was deployed into. |
| `name` | string | The name of the proximity placement group. |
| `resourceGroupName` | string | The resource group the proximity placement group was deployed into. |
| `resourceId` | string | The resourceId the proximity placement group. |

## Cross-referenced modules

This section gives you an overview of all local-referenced module files (i.e., other modules that are referenced in this module) and all remote-referenced files (i.e., Bicep modules that are referenced from a Bicep Registry or Template Specs).

| Reference | Type |
| :-- | :-- |
| `br/public:avm/utl/types/avm-common-types:0.5.1` | Remote reference |

## Data Collection

The software may collect information about you and your use of the software and send it to Microsoft. Microsoft may use this information to provide services and improve our products and services. You may turn off the telemetry as described in the [repository](https://aka.ms/avm/telemetry). There are also some features in the software that may enable you and Microsoft to collect data from users of your applications. If you use these features, you must comply with applicable law, including providing appropriate notices to users of your applications together with a copy of Microsoft’s privacy statement. Our privacy statement is located at <https://go.microsoft.com/fwlink/?LinkID=824704>. You can learn more about data collection and use in the help documentation and our privacy statement. Your use of the software operates as your consent to these practices.
