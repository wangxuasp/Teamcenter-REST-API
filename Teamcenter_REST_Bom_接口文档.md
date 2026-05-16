# Teamcenter SOA API — Bom 接口文档（TC 2512）

> 本文档汇总 **Bom** Library 下**全部 API 版本（年-月）**的 SOA 操作，已按版本与 Service 双向合并整理。
> 数据来源：TC 2512 SOA Api Browser（`structure.js`）。
>
> - **API 版本数：** 4 个（`2008-06` ～ `2025-06`）
> - **操作总数：** 8 个（含 1 组同名跨版本操作）
> - **Url 格式：** `Bom-{Year}-{Service}/{operation}`

---

## 目录

1. [API 版本总览](#1-api-版本总览)
2. [按 Service 合并（跨版本）](#2-按-service-合并跨版本)
3. [按 API 版本（年-月）归档](#3-按-api-版本年-月归档)
4. [附录](#4-附录)

---

## 1. API 版本总览

Bom 库在 TC 2512 中通过 **4 个**年-月版本契约发布接口，涵盖结构编辑、基线、规则遍历与配置基线关闭等能力。

### 同名多版本操作

- `addOrUpdateChildrenToParentLine`（StructureManagement）：`2008-06`、`2025-06`

| API 版本 | Service | 操作 | Url |
|----------|---------|------|-----|
| **2008-06** | StructureManagement | `addOrUpdateChildrenToParentLine` | `Bom-2008-06-StructureManagement/addOrUpdateChildrenToParentLine` |
| **2008-06** | StructureManagement | `createBaseline` | `Bom-2008-06-StructureManagement/createBaseline` |
| **2008-06** | StructureManagement | `removeChildrenFromParentLine` | `Bom-2008-06-StructureManagement/removeChildrenFromParentLine` |
| **2010-09** | StructureManagement | `getTraversedObjectsByRule` | `Bom-2010-09-StructureManagement/getTraversedObjectsByRule` |
| **2010-09** | StructureManagement | `verifyObjectCoverageByRule` | `Bom-2010-09-StructureManagement/verifyObjectCoverageByRule` |
| **2024-06** | ConfigBaselineManagement | `closeConfigurationBaselines` | `Bom-2024-06-ConfigBaselineManagement/closeConfigurationBaselines` |
| **2024-06** | ConfigBaselineManagement | `closeConfigurationBaselines2` | `Bom-2024-06-ConfigBaselineManagement/closeConfigurationBaselines2` |
| **2025-06** | StructureManagement | `addOrUpdateChildrenToParentLine` | `Bom-2025-06-StructureManagement/addOrUpdateChildrenToParentLine` |

### 版本—Service 对照

| API 版本 | 包含的 Service | 操作数 |
|----------|----------------|--------|
| 2008-06 | StructureManagement | 3 |
| 2010-09 | StructureManagement | 2 |
| 2024-06 | ConfigBaselineManagement | 2 |
| 2025-06 | StructureManagement | 1 |

---

## 2. 按 Service 合并（跨版本）

同一 Service 下按 **API 版本（年-月）** 分组；同名操作若存在多个版本，分别列出各自契约的 input/output。

### 2.1 配置基线管理（ConfigBaselineManagement）

**涵盖 API 版本：** `2024-06`  
**操作数：** 2

#### 版本 2024-06

##### 2.1.1.1 closeConfigurationBaselines

**接口路径：** `Bom-2024-06-ConfigBaselineManagement/closeConfigurationBaselines`

**API 版本：** `2024-06`  
**Service：** `ConfigBaselineManagement`  
**Library：** `Bom`

**说明：** 将 Fnd0ConfigurationBaseline（配置基线）对象状态变更为 Closed。关闭前可选择为基线内的工作版本创建新版本；支持前台或后台模式执行。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2024_06.ConfigBaselineManagement.closeConfigurationBaselines`

**请求（input）：**

```json
{
  "closeConfigBaselineInput": [
    {
      "clientId": "",
      "configBaseline": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "reviseWorkingContent": "",
      "releaseProcessName": ""
    }
  ],
  "runInBackground": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `closeConfigBaselineInput` | Teamcenter::Soa::Bom::_2024_06::ConfigBaselineManagement::CloseConfigurationBaselineInput[] | A list of CloseConfigurationBaselineInput objects, each object represents one <b>Fnd0ConfigurationBaseline</b> object with additional inputs to revise and release the baseline cont |
| `runInBackground` | bool | If true, the operation is performed in background mode in a separate asynchronous server session; otherwise, the operation is performed synchronously. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.1.2 closeConfigurationBaselines2

**接口路径：** `Bom-2024-06-ConfigBaselineManagement/closeConfigurationBaselines2`

**API 版本：** `2024-06`  
**Service：** `ConfigBaselineManagement`  
**Library：** `Bom`

**说明：** 将 Fnd0ConfigurationBaseline 对象关闭（增强版）。关闭前可对工作版本执行：创建基线修订、发布、保持原状或在存在工作版本时报错等策略；支持前台/后台模式。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2024_06.ConfigBaselineManagement.closeConfigurationBaselines2`

**请求（input）：**

```json
{
  "closeConfigBaselineInput": [
    {
      "clientId": "",
      "configBaseline": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "actionOnWorkingContent": "",
      "releaseProcessName": ""
    }
  ],
  "runInBackground": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `closeConfigBaselineInput` | Teamcenter::Soa::Bom::_2024_06::ConfigBaselineManagement::CloseConfigurationBaselineInput2[] | A list of CloseConfigurationBaselineInput2 objects, each object represents one <b>Fnd0ConfigurationBaseline</b> object with additional inputs to do different actions on the working |
| `runInBackground` | bool | If true, the operation is performed in background mode in a separate asynchronous server session; otherwise, the operation is performed synchronously. |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.2 结构管理（StructureManagement）

**涵盖 API 版本：** `2008-06`、`2010-09`、`2025-06`  
**操作数：** 6

#### 版本 2008-06

##### 2.2.1.1 addOrUpdateChildrenToParentLine

**接口路径：** `Bom-2008-06-StructureManagement/addOrUpdateChildrenToParentLine`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 向产品结构中的父 BOM 行添加或更新子件（Item / ItemRevision / 通用设计元素 GDE）。可指定视图类型创建 BOMView；若传入已有 BOMLine 且 clientId 为空则执行属性更新。返回新建的 BOMLine、Item Element Line 及 ServiceData。

> 本操作另有其他 API 版本，见同 Service 下其他「版本」小节。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2008_06.StructureManagement.addOrUpdateChildrenToParentLine`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentLine": "{{ROOT_BOM_ITEM_BOMLine_UID_out}}",
      "viewType": "",
      "items": [
        {
          "clientId": "",
          "item": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRev": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occType": "",
          "bomline": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemLineProperties": {}
        }
      ],
      "itemElements": [
        {
          "clientId": "",
          "itemElement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occType": "",
          "itemElementline": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemElementLineProperties": {}
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::AddOrUpdateChildrenToParentLineInfo[] | This is a vector of AddOrUpdateChildrenToParentLineInfo. Each element of this vector contains an input <b>BOMLine</b> which is going to get updated, view type e.g. CAEAnalysis, MEP |

**响应（output）：**

```json
{
  "itemLines": [
    {
      "clientId": "",
      "bomline": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "itemelementLines": [
    {
      "clientId": "",
      "bomline": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `itemLines` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BOMLinesOutput[] | Array of Output itemLines |
| `itemelementLines` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BOMLinesOutput[] | Array of Output itemElementLines |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture used to return sets of Teamcenter Data Model object from a service request. This also holds services exceptions. |

---

##### 2.2.1.2 createBaseline

**接口路径：** `Bom-2008-06-StructureManagement/createBaseline`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 基于进行中的 ItemRevision 创建新的基线 ItemRevision。若输入为多级 PSBOMViewRevision 结构，则递归基线化全部组件；支持站点级“智能基线”选项及已发布版本的排除规则。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2008_06.StructureManagement.createBaseline`

**请求（input）：**

```json
{
  "inputs": [
    {
      "dryrun": "",
      "clientID": "",
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "viewType": "",
      "revRule": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "precise": "",
      "releaseProcess": "",
      "description": "",
      "baselineJobName": "",
      "baselineJobDescription": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BaselineInput[] | List of <font face="courier" height="10">BaselineInput</font> structures.<br />Each of the structures , holds the <b>ItemRevision</b> to be baselined, <b>RevisionRule</b> and valid |

**响应（output）：**

```json
{
  "output": [
    {
      "dryrun": "",
      "clientID": "",
      "baselineItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "dryrunLogTicket": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BaselineOutput[] | List of <font face="courier" height="10">BaselineOutput</font> structures |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | structure containing error codes and messages |

---

##### 2.2.1.3 removeChildrenFromParentLine

**接口路径：** `Bom-2008-06-StructureManagement/removeChildrenFromParentLine`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 从装配体/产品结构中移除一条或多条 BOMLine。支持批量传入 BOMLine 向量，一次调用删除多行。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2008_06.StructureManagement.removeChildrenFromParentLine`

**请求（input）：**

```json
{
  "bomlines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `bomlines` | Teamcenter::BOMLine[] | This is a vector of <i>Teamcenter::BOMLine</i> and contains all the <i>BOMLines</i> that need to be deleted from an assembly/product structure |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <i>ServiceData</i> structure is used to return the updated parent <i>BOMLine</i> business objects whose children have been removed and can contain partial errors if the operati |

---

#### 版本 2010-09

##### 2.2.2.1 getTraversedObjectsByRule

**接口路径：** `Bom-2010-09-StructureManagement/getTraversedObjectsByRule`

**API 版本：** `2010-09`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 按给定过滤/遍历规则遍历产品结构，返回满足规则的全部 BOM 行（展开后的完整行列表）。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2010_09.StructureManagement.getTraversedObjectsByRule`

**请求（input）：**

```json
{
  "input": {
    "scopeObjects": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "closureRule": "",
    "depth": "",
    "otherStructure": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Bom::_2010_09::StructureManagement::TraversedObjectsInput | TraversedObjectsInput structure |

**响应（output）：**

```json
{
  "resultObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `resultObjects` | Teamcenter::BusinessObject[] | return vector of the the auto-expanded/filtered lines |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | return errors if verifacation was failed or illegal |

---

##### 2.2.2.2 verifyObjectCoverageByRule

**接口路径：** `Bom-2010-09-StructureManagement/verifyObjectCoverageByRule`

**API 版本：** `2010-09`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 校验传入的 BOM 行是否满足指定的闭合/过滤规则，对每一行返回是否符合规则的结果。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2010_09.StructureManagement.verifyObjectCoverageByRule`

**请求（input）：**

```json
{
  "input": {
    "contexts": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "objectsToCheck": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "closureRule": "",
    "depth": "",
    "otherStructure": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Bom::_2010_09::StructureManagement::ObjectCoverageInput | ObjectCoverageInput structure |

**响应（output）：**

```json
{
  "covered": [],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `covered` | bool[] | return vector (corresponds to the input objects vector) - with true or false |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | contains any errors received during the execution |

---

#### 版本 2025-06

##### 2.2.3.1 addOrUpdateChildrenToParentLine

**接口路径：** `Bom-2025-06-StructureManagement/addOrUpdateChildrenToParentLine`

**API 版本：** `2025-06`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 向产品结构中的父 BOM 行添加或更新子件（Item / ItemRevision / 通用设计元素 GDE）。可指定视图类型创建 BOMView；若传入已有 BOMLine 且 clientId 为空则执行属性更新。返回新建的 BOMLine、Item Element Line 及 ServiceData。

> 本操作另有其他 API 版本，见同 Service 下其他「版本」小节。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2025_06.StructureManagement.addOrUpdateChildrenToParentLine`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentLine": "{{ROOT_BOM_ITEM_BOMLine_UID_out}}",
      "viewType": "",
      "items": [
        {
          "clientId": "",
          "item": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRev": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occType": "",
          "bomline": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemLineProperties": {},
          "usageRevisionType": "",
          "preAllocatedPsOccThreadUid": ""
        }
      ],
      "itemElements": [
        {
          "clientId": "",
          "itemElement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occType": "",
          "itemElementline": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemElementLineProperties": {}
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Bom::_2025_06::StructureManagement::AddOrUpdateChildrenToParentLineInfo2[] | A list of AddUpdateChildrenToParentLineInfo2. Each element of this list contains an input <b>BOMLine</b> which is going to get updated, view type e.g. <b>CAEAnalysis</b> , <b>MEPro |

**响应（output）：**

```json
{
  "itemLines": [
    {
      "clientId": "",
      "bomline": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "itemelementLines": [
    {
      "clientId": "",
      "bomline": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `itemLines` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BOMLinesOutput[] | Array of Output itemLines |
| `itemelementLines` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BOMLinesOutput[] | Array of Output itemElementLines |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture used to return sets of Teamcenter Data Model object from a service request. This also holds services exceptions. |

---

---

## 3. 按 API 版本（年-月）归档

按时间线列出各版本契约下的全部接口定义（与第 2 节内容一致，便于按版本检索）。

### 3.1 API 版本 2008-06

**Service：** StructureManagement  **操作数：** 3

#### 3.1.1 addOrUpdateChildrenToParentLine（2008-06）

**接口路径：** `Bom-2008-06-StructureManagement/addOrUpdateChildrenToParentLine`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 向产品结构中的父 BOM 行添加或更新子件（Item / ItemRevision / 通用设计元素 GDE）。可指定视图类型创建 BOMView；若传入已有 BOMLine 且 clientId 为空则执行属性更新。返回新建的 BOMLine、Item Element Line 及 ServiceData。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2008_06.StructureManagement.addOrUpdateChildrenToParentLine`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentLine": "{{ROOT_BOM_ITEM_BOMLine_UID_out}}",
      "viewType": "",
      "items": [
        {
          "clientId": "",
          "item": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRev": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occType": "",
          "bomline": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemLineProperties": {}
        }
      ],
      "itemElements": [
        {
          "clientId": "",
          "itemElement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occType": "",
          "itemElementline": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemElementLineProperties": {}
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::AddOrUpdateChildrenToParentLineInfo[] | This is a vector of AddOrUpdateChildrenToParentLineInfo. Each element of this vector contains an input <b>BOMLine</b> which is going to get updated, view type e.g. CAEAnalysis, MEP |

**响应（output）：**

```json
{
  "itemLines": [
    {
      "clientId": "",
      "bomline": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "itemelementLines": [
    {
      "clientId": "",
      "bomline": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `itemLines` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BOMLinesOutput[] | Array of Output itemLines |
| `itemelementLines` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BOMLinesOutput[] | Array of Output itemElementLines |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture used to return sets of Teamcenter Data Model object from a service request. This also holds services exceptions. |

---

#### 3.1.2 createBaseline（2008-06）

**接口路径：** `Bom-2008-06-StructureManagement/createBaseline`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 基于进行中的 ItemRevision 创建新的基线 ItemRevision。若输入为多级 PSBOMViewRevision 结构，则递归基线化全部组件；支持站点级“智能基线”选项及已发布版本的排除规则。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2008_06.StructureManagement.createBaseline`

**请求（input）：**

```json
{
  "inputs": [
    {
      "dryrun": "",
      "clientID": "",
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "viewType": "",
      "revRule": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "precise": "",
      "releaseProcess": "",
      "description": "",
      "baselineJobName": "",
      "baselineJobDescription": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BaselineInput[] | List of <font face="courier" height="10">BaselineInput</font> structures.<br />Each of the structures , holds the <b>ItemRevision</b> to be baselined, <b>RevisionRule</b> and valid |

**响应（output）：**

```json
{
  "output": [
    {
      "dryrun": "",
      "clientID": "",
      "baselineItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "dryrunLogTicket": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BaselineOutput[] | List of <font face="courier" height="10">BaselineOutput</font> structures |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | structure containing error codes and messages |

---

#### 3.1.3 removeChildrenFromParentLine（2008-06）

**接口路径：** `Bom-2008-06-StructureManagement/removeChildrenFromParentLine`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 从装配体/产品结构中移除一条或多条 BOMLine。支持批量传入 BOMLine 向量，一次调用删除多行。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2008_06.StructureManagement.removeChildrenFromParentLine`

**请求（input）：**

```json
{
  "bomlines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `bomlines` | Teamcenter::BOMLine[] | This is a vector of <i>Teamcenter::BOMLine</i> and contains all the <i>BOMLines</i> that need to be deleted from an assembly/product structure |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <i>ServiceData</i> structure is used to return the updated parent <i>BOMLine</i> business objects whose children have been removed and can contain partial errors if the operati |

---

### 3.2 API 版本 2010-09

**Service：** StructureManagement  **操作数：** 2

#### 3.2.1 getTraversedObjectsByRule（2010-09）

**接口路径：** `Bom-2010-09-StructureManagement/getTraversedObjectsByRule`

**API 版本：** `2010-09`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 按给定过滤/遍历规则遍历产品结构，返回满足规则的全部 BOM 行（展开后的完整行列表）。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2010_09.StructureManagement.getTraversedObjectsByRule`

**请求（input）：**

```json
{
  "input": {
    "scopeObjects": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "closureRule": "",
    "depth": "",
    "otherStructure": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Bom::_2010_09::StructureManagement::TraversedObjectsInput | TraversedObjectsInput structure |

**响应（output）：**

```json
{
  "resultObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `resultObjects` | Teamcenter::BusinessObject[] | return vector of the the auto-expanded/filtered lines |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | return errors if verifacation was failed or illegal |

---

#### 3.2.2 verifyObjectCoverageByRule（2010-09）

**接口路径：** `Bom-2010-09-StructureManagement/verifyObjectCoverageByRule`

**API 版本：** `2010-09`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 校验传入的 BOM 行是否满足指定的闭合/过滤规则，对每一行返回是否符合规则的结果。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2010_09.StructureManagement.verifyObjectCoverageByRule`

**请求（input）：**

```json
{
  "input": {
    "contexts": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "objectsToCheck": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "closureRule": "",
    "depth": "",
    "otherStructure": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Bom::_2010_09::StructureManagement::ObjectCoverageInput | ObjectCoverageInput structure |

**响应（output）：**

```json
{
  "covered": [],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `covered` | bool[] | return vector (corresponds to the input objects vector) - with true or false |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | contains any errors received during the execution |

---

### 3.3 API 版本 2024-06

**Service：** ConfigBaselineManagement  **操作数：** 2

#### 3.3.1 closeConfigurationBaselines（2024-06）

**接口路径：** `Bom-2024-06-ConfigBaselineManagement/closeConfigurationBaselines`

**API 版本：** `2024-06`  
**Service：** `ConfigBaselineManagement`  
**Library：** `Bom`

**说明：** 将 Fnd0ConfigurationBaseline（配置基线）对象状态变更为 Closed。关闭前可选择为基线内的工作版本创建新版本；支持前台或后台模式执行。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2024_06.ConfigBaselineManagement.closeConfigurationBaselines`

**请求（input）：**

```json
{
  "closeConfigBaselineInput": [
    {
      "clientId": "",
      "configBaseline": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "reviseWorkingContent": "",
      "releaseProcessName": ""
    }
  ],
  "runInBackground": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `closeConfigBaselineInput` | Teamcenter::Soa::Bom::_2024_06::ConfigBaselineManagement::CloseConfigurationBaselineInput[] | A list of CloseConfigurationBaselineInput objects, each object represents one <b>Fnd0ConfigurationBaseline</b> object with additional inputs to revise and release the baseline cont |
| `runInBackground` | bool | If true, the operation is performed in background mode in a separate asynchronous server session; otherwise, the operation is performed synchronously. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.3.2 closeConfigurationBaselines2（2024-06）

**接口路径：** `Bom-2024-06-ConfigBaselineManagement/closeConfigurationBaselines2`

**API 版本：** `2024-06`  
**Service：** `ConfigBaselineManagement`  
**Library：** `Bom`

**说明：** 将 Fnd0ConfigurationBaseline 对象关闭（增强版）。关闭前可对工作版本执行：创建基线修订、发布、保持原状或在存在工作版本时报错等策略；支持前台/后台模式。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2024_06.ConfigBaselineManagement.closeConfigurationBaselines2`

**请求（input）：**

```json
{
  "closeConfigBaselineInput": [
    {
      "clientId": "",
      "configBaseline": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "actionOnWorkingContent": "",
      "releaseProcessName": ""
    }
  ],
  "runInBackground": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `closeConfigBaselineInput` | Teamcenter::Soa::Bom::_2024_06::ConfigBaselineManagement::CloseConfigurationBaselineInput2[] | A list of CloseConfigurationBaselineInput2 objects, each object represents one <b>Fnd0ConfigurationBaseline</b> object with additional inputs to do different actions on the working |
| `runInBackground` | bool | If true, the operation is performed in background mode in a separate asynchronous server session; otherwise, the operation is performed synchronously. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.4 API 版本 2025-06

**Service：** StructureManagement  **操作数：** 1

#### 3.4.1 addOrUpdateChildrenToParentLine（2025-06）

**接口路径：** `Bom-2025-06-StructureManagement/addOrUpdateChildrenToParentLine`

**API 版本：** `2025-06`  
**Service：** `StructureManagement`  
**Library：** `Bom`

**说明：** 向产品结构中的父 BOM 行添加或更新子件（Item / ItemRevision / 通用设计元素 GDE）。可指定视图类型创建 BOMView；若传入已有 BOMLine 且 clientId 为空则执行属性更新。返回新建的 BOMLine、Item Element Line 及 ServiceData。

**Soa Inclusion：** `Teamcenter.Soa.Bom._2025_06.StructureManagement.addOrUpdateChildrenToParentLine`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentLine": "{{ROOT_BOM_ITEM_BOMLine_UID_out}}",
      "viewType": "",
      "items": [
        {
          "clientId": "",
          "item": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRev": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occType": "",
          "bomline": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemLineProperties": {},
          "usageRevisionType": "",
          "preAllocatedPsOccThreadUid": ""
        }
      ],
      "itemElements": [
        {
          "clientId": "",
          "itemElement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occType": "",
          "itemElementline": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemElementLineProperties": {}
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Bom::_2025_06::StructureManagement::AddOrUpdateChildrenToParentLineInfo2[] | A list of AddUpdateChildrenToParentLineInfo2. Each element of this list contains an input <b>BOMLine</b> which is going to get updated, view type e.g. <b>CAEAnalysis</b> , <b>MEPro |

**响应（output）：**

```json
{
  "itemLines": [
    {
      "clientId": "",
      "bomline": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "itemelementLines": [
    {
      "clientId": "",
      "bomline": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `itemLines` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BOMLinesOutput[] | Array of Output itemLines |
| `itemelementLines` | Teamcenter::Soa::Bom::_2008_06::StructureManagement::BOMLinesOutput[] | Array of Output itemElementLines |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture used to return sets of Teamcenter Data Model object from a service request. This also holds services exceptions. |

---

---

## 4. 附录

### 操作一览（合并索引）

| API 版本 | Service | 操作 | Url | Soa Inclusion |
|----------|---------|------|-----|---------------|
| 2008-06 | StructureManagement | `addOrUpdateChildrenToParentLine` | `Bom-2008-06-StructureManagement/addOrUpdateChildrenToParentLine` | `Teamcenter.Soa.Bom._2008_06.StructureManagement.addOrUpdateChildrenToParentLine` |
| 2008-06 | StructureManagement | `createBaseline` | `Bom-2008-06-StructureManagement/createBaseline` | `Teamcenter.Soa.Bom._2008_06.StructureManagement.createBaseline` |
| 2008-06 | StructureManagement | `removeChildrenFromParentLine` | `Bom-2008-06-StructureManagement/removeChildrenFromParentLine` | `Teamcenter.Soa.Bom._2008_06.StructureManagement.removeChildrenFromParentLine` |
| 2010-09 | StructureManagement | `getTraversedObjectsByRule` | `Bom-2010-09-StructureManagement/getTraversedObjectsByRule` | `Teamcenter.Soa.Bom._2010_09.StructureManagement.getTraversedObjectsByRule` |
| 2010-09 | StructureManagement | `verifyObjectCoverageByRule` | `Bom-2010-09-StructureManagement/verifyObjectCoverageByRule` | `Teamcenter.Soa.Bom._2010_09.StructureManagement.verifyObjectCoverageByRule` |
| 2024-06 | ConfigBaselineManagement | `closeConfigurationBaselines` | `Bom-2024-06-ConfigBaselineManagement/closeConfigurationBaselines` | `Teamcenter.Soa.Bom._2024_06.ConfigBaselineManagement.closeConfigurationBaselines` |
| 2024-06 | ConfigBaselineManagement | `closeConfigurationBaselines2` | `Bom-2024-06-ConfigBaselineManagement/closeConfigurationBaselines2` | `Teamcenter.Soa.Bom._2024_06.ConfigBaselineManagement.closeConfigurationBaselines2` |
| 2025-06 | StructureManagement | `addOrUpdateChildrenToParentLine` | `Bom-2025-06-StructureManagement/addOrUpdateChildrenToParentLine` | `Teamcenter.Soa.Bom._2025_06.StructureManagement.addOrUpdateChildrenToParentLine` |

### 与 Cad 库的关系

| 能力 | Bom 库 | Cad 库（常见配套） |
|------|--------|-------------------|
| 创建/展开/保存 BOM 窗口 | — | `createBOMWindows`、`expandPSAllLevels`、`saveBOMWindows` |
| 编辑 BOM 行（增删子件） | `addOrUpdateChildrenToParentLine`、`removeChildrenFromParentLine` | — |
| 条目基线 | `createBaseline` | — |
| 配置基线关闭 | `closeConfigurationBaselines` / `closeConfigurationBaselines2` | — |

### 典型流程

**BOM 行编辑（常与 Cad 库配合）：**
1. `login`（Core Session）
2. `createBOMWindows` / `expandPSAllLevels`（Cad）
3. `addOrUpdateChildrenToParentLine`（Bom，选用 `2008-06` 或 `2025-06` 契约）
4. `saveBOMWindows`（Cad）

**移除子件：**
1. `removeChildrenFromParentLine`（2008-06）

**配置基线关闭：**
1. `closeConfigurationBaselines` 或 `closeConfigurationBaselines2`（2024-06）

### 重新生成

```bash
node generate-bom-doc.js
```
