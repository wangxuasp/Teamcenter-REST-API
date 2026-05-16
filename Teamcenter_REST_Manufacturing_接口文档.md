# Teamcenter SOA API — Manufacturing 接口文档（TC 2512）

> 本文档汇总 **Manufacturing** Library 下**全部 API 版本（年-月）**的 SOA 操作，已按版本与 Service 双向合并整理。
> 功能说明与参数说明均已中文化（基于官方英文描述翻译）。
>
> - **API 版本数：** 21 个（`2008-06` ～ `2020-04`）
> - **Service 数：** 14 个
> - **操作总数：** 123 个
> - **同名多版本操作：** 3 个（须按版本选择 Url）
> - **Url 格式：** `Manufacturing-{Year}-{Service}/{operation}`

---

## 目录

1. [API 版本总览](#1-api-版本总览)
2. [按 Service 合并（跨版本）](#2-按-service-合并跨版本)
3. [按 API 版本（年-月）归档](#3-按-api-版本年-月归档)
4. [附录](#4-附录)

---

## 1. API 版本总览

Manufacturing 在 TC 2512 中通过 **21 个**年-月版本契约发布接口，覆盖工艺结构、BOP、IPA、时间管理、导入导出等能力。

### 同名多版本操作

| 操作 | 可用 API 版本 |
|------|---------------|
| `StructureManagement/pasteDuplicateStructure` | `2009-10`、`2018-11` |
| `Core/findNodeInContext` | `2010-09`、`2013-05` |
| `ImportExport/importManufacturingFeatures` | `2013-05`、`2015-10`、`2016-03` |

### 全量索引（按版本排序）

| API 版本 | Service | 操作 | Url |
|----------|---------|------|-----|
| **2008-06** | Core | `findCheckedOutsInStructure` | `Manufacturing-2008-06-Core/findCheckedOutsInStructure` |
| **2008-06** | DataManagement | `createOrUpdateMEActivityFolders` | `Manufacturing-2008-06-DataManagement/createOrUpdateMEActivityFolders` |
| **2008-06** | DataManagement | `createOrUpdateMENXObjects` | `Manufacturing-2008-06-DataManagement/createOrUpdateMENXObjects` |
| **2008-06** | TimeManagement | `allocatedTimeRollUp` | `Manufacturing-2008-06-TimeManagement/allocatedTimeRollUp` |
| **2008-06** | TimeManagement | `timeAnalysisRollup` | `Manufacturing-2008-06-TimeManagement/timeAnalysisRollup` |
| **2008-12** | IPAManagement | `deletefilteredIPA` | `Manufacturing-2008-12-IPAManagement/deletefilteredIPA` |
| **2008-12** | IPAManagement | `generateSearchScope` | `Manufacturing-2008-12-IPAManagement/generateSearchScope` |
| **2008-12** | IPAManagement | `getFilteredIPA` | `Manufacturing-2008-12-IPAManagement/getFilteredIPA` |
| **2008-12** | IPAManagement | `saveSearchResult` | `Manufacturing-2008-12-IPAManagement/saveSearchResult` |
| **2009-06** | StructureManagement | `closeAttachmentWindow` | `Manufacturing-2009-06-StructureManagement/closeAttachmentWindow` |
| **2009-06** | StructureManagement | `createOrUpdateAttachments` | `Manufacturing-2009-06-StructureManagement/createOrUpdateAttachments` |
| **2009-06** | StructureManagement | `deleteAttachments` | `Manufacturing-2009-06-StructureManagement/deleteAttachments` |
| **2009-06** | StructureManagement | `getAttachmentLineChildren` | `Manufacturing-2009-06-StructureManagement/getAttachmentLineChildren` |
| **2009-06** | StructureManagement | `getBOMLineActivities` | `Manufacturing-2009-06-StructureManagement/getBOMLineActivities` |
| **2009-06** | StructureManagement | `getBOMLineAttachments` | `Manufacturing-2009-06-StructureManagement/getBOMLineAttachments` |
| **2009-06** | StructureManagement | `getStructureContextActivityLines` | `Manufacturing-2009-06-StructureManagement/getStructureContextActivityLines` |
| **2009-06** | StructureManagement | `getStructureContextTopLines` | `Manufacturing-2009-06-StructureManagement/getStructureContextTopLines` |
| **2009-10** | DataManagement | `createObjects` | `Manufacturing-2009-10-DataManagement/createObjects` |
| **2009-10** | DataManagement | `disconnectObjects` | `Manufacturing-2009-10-DataManagement/disconnectObjects` |
| **2009-10** | MFGPropertyCollector | `collectProperties` | `Manufacturing-2009-10-MFGPropertyCollector/collectProperties` |
| **2009-10** | Model | `calculateCriticalPath` | `Manufacturing-2009-10-Model/calculateCriticalPath` |
| **2009-10** | Model | `createFlow` | `Manufacturing-2009-10-Model/createFlow` |
| **2009-10** | Model | `editLogicalAssignments` | `Manufacturing-2009-10-Model/editLogicalAssignments` |
| **2009-10** | Model | `getResolvedNodesFromLA` | `Manufacturing-2009-10-Model/getResolvedNodesFromLA` |
| **2009-10** | Model | `removeFlow` | `Manufacturing-2009-10-Model/removeFlow` |
| **2009-10** | Model | `resolveLogicalAssignments` | `Manufacturing-2009-10-Model/resolveLogicalAssignments` |
| **2009-10** | ModelDefinitions | `getManufacturingPropretyDescs` | `Manufacturing-2009-10-ModelDefinitions/getManufacturingPropretyDescs` |
| **2009-10** | ModelDefinitions | `getValidRelationTypes` | `Manufacturing-2009-10-ModelDefinitions/getValidRelationTypes` |
| **2009-10** | StructureManagement | `copyEBOPStructure` | `Manufacturing-2009-10-StructureManagement/copyEBOPStructure` |
| **2009-10** | StructureManagement | `getStructureContextLines` | `Manufacturing-2009-10-StructureManagement/getStructureContextLines` |
| **2009-10** | StructureManagement | `pasteDuplicateStructure` | `Manufacturing-2009-10-StructureManagement/pasteDuplicateStructure` |
| **2009-10** | StructureSearch | `nextSearch` | `Manufacturing-2009-10-StructureSearch/nextSearch` |
| **2009-10** | StructureSearch | `startSearch` | `Manufacturing-2009-10-StructureSearch/startSearch` |
| **2009-10** | StructureSearch | `stopSearch` | `Manufacturing-2009-10-StructureSearch/stopSearch` |
| **2010-09** | Core | `findNodeInContext` | `Manufacturing-2010-09-Core/findNodeInContext` |
| **2010-09** | Core | `getAffectedProperties` | `Manufacturing-2010-09-Core/getAffectedProperties` |
| **2010-09** | ImportExport | `importManufaturingFeatures` | `Manufacturing-2010-09-ImportExport/importManufaturingFeatures` |
| **2010-09** | TimeManagement | `calculateCriticalPathEx` | `Manufacturing-2010-09-TimeManagement/calculateCriticalPathEx` |
| **2010-09** | TimeManagement | `getActivityTimes` | `Manufacturing-2010-09-TimeManagement/getActivityTimes` |
| **2010-09** | TimeManagement | `populateAllocatedTimeProperties` | `Manufacturing-2010-09-TimeManagement/populateAllocatedTimeProperties` |
| **2010-09** | TimeManagement | `updateTimeManagementProperties` | `Manufacturing-2010-09-TimeManagement/updateTimeManagementProperties` |
| **2011-06** | DataManagement | `closeContexts` | `Manufacturing-2011-06-DataManagement/closeContexts` |
| **2011-06** | DataManagement | `closeViews` | `Manufacturing-2011-06-DataManagement/closeViews` |
| **2011-06** | DataManagement | `openContexts` | `Manufacturing-2011-06-DataManagement/openContexts` |
| **2011-06** | DataManagement | `openViews` | `Manufacturing-2011-06-DataManagement/openViews` |
| **2011-06** | StructureManagement | `getReferenceContexts` | `Manufacturing-2011-06-StructureManagement/getReferenceContexts` |
| **2011-06** | StructureManagement | `setReferenceContexts` | `Manufacturing-2011-06-StructureManagement/setReferenceContexts` |
| **2012-02** | Constraints | `getPrecedenceConstraintPaths` | `Manufacturing-2012-02-Constraints/getPrecedenceConstraintPaths` |
| **2012-02** | Constraints | `getPrecedenceConstraints` | `Manufacturing-2012-02-Constraints/getPrecedenceConstraints` |
| **2012-02** | Constraints | `validateConstraintConsistency` | `Manufacturing-2012-02-Constraints/validateConstraintConsistency` |
| **2012-02** | Constraints | `validateProcessAreaAssignments` | `Manufacturing-2012-02-Constraints/validateProcessAreaAssignments` |
| **2012-02** | DataManagement | `addAssociatedContexts` | `Manufacturing-2012-02-DataManagement/addAssociatedContexts` |
| **2012-02** | DataManagement | `associateAndAllocateByPreview` | `Manufacturing-2012-02-DataManagement/associateAndAllocateByPreview` |
| **2012-02** | DataManagement | `automaticAllocatePreview` | `Manufacturing-2012-02-DataManagement/automaticAllocatePreview` |
| **2012-02** | DataManagement | `automaticAssociateAndAllocate` | `Manufacturing-2012-02-DataManagement/automaticAssociateAndAllocate` |
| **2012-02** | DataManagement | `connectObjects` | `Manufacturing-2012-02-DataManagement/connectObjects` |
| **2012-02** | DataManagement | `disconnectFromOrigin` | `Manufacturing-2012-02-DataManagement/disconnectFromOrigin` |
| **2012-02** | DataManagement | `getAssociatedContexts` | `Manufacturing-2012-02-DataManagement/getAssociatedContexts` |
| **2012-02** | IPAManagement | `deleteFilteredIPA` | `Manufacturing-2012-02-IPAManagement/deleteFilteredIPA` |
| **2012-02** | IPAManagement | `getFilteredIPAType` | `Manufacturing-2012-02-IPAManagement/getFilteredIPAType` |
| **2012-02** | Model | `getCandidateToolsForToolRequirement` | `Manufacturing-2012-02-Model/getCandidateToolsForToolRequirement` |
| **2012-02** | Model | `getToolRequirements` | `Manufacturing-2012-02-Model/getToolRequirements` |
| **2012-02** | Model | `resolveToolRequirement` | `Manufacturing-2012-02-Model/resolveToolRequirement` |
| **2012-02** | Model | `updateFlows` | `Manufacturing-2012-02-Model/updateFlows` |
| **2012-09** | DataManagement | `applyConfigObjects` | `Manufacturing-2012-09-DataManagement/applyConfigObjects` |
| **2012-09** | DataManagement | `createOrUpdateConfigObjects` | `Manufacturing-2012-09-DataManagement/createOrUpdateConfigObjects` |
| **2012-09** | Validation | `executeValidations` | `Manufacturing-2012-09-Validation/executeValidations` |
| **2012-09** | Validation | `getAllValidations` | `Manufacturing-2012-09-Validation/getAllValidations` |
| **2013-05** | Core | `findNodeInContext` | `Manufacturing-2013-05-Core/findNodeInContext` |
| **2013-05** | Core | `matchObjectsAgainstVariantRules` | `Manufacturing-2013-05-Core/matchObjectsAgainstVariantRules` |
| **2013-05** | DataManagement | `createAttachments` | `Manufacturing-2013-05-DataManagement/createAttachments` |
| **2013-05** | DataManagement | `setAttributes` | `Manufacturing-2013-05-DataManagement/setAttributes` |
| **2013-05** | DataManagement | `syncStudyAndSource` | `Manufacturing-2013-05-DataManagement/syncStudyAndSource` |
| **2013-05** | ImportExport | `importManufacturingFeatures` | `Manufacturing-2013-05-ImportExport/importManufacturingFeatures` |
| **2013-05** | IPAManagement | `cleanIPATree` | `Manufacturing-2013-05-IPAManagement/cleanIPATree` |
| **2013-05** | IPAManagement | `doesIPAExist` | `Manufacturing-2013-05-IPAManagement/doesIPAExist` |
| **2013-05** | IPAManagement | `generateIPATree` | `Manufacturing-2013-05-IPAManagement/generateIPATree` |
| **2013-05** | IPAManagement | `localUpdateIPATree` | `Manufacturing-2013-05-IPAManagement/localUpdateIPATree` |
| **2013-05** | IPAManagement | `updateIPATree` | `Manufacturing-2013-05-IPAManagement/updateIPATree` |
| **2013-05** | StructureManagement | `findAffectedCCs` | `Manufacturing-2013-05-StructureManagement/findAffectedCCs` |
| **2013-05** | StructureSearch | `findStudies` | `Manufacturing-2013-05-StructureSearch/findStudies` |
| **2013-05** | TimeWayPlan | `getTWPInformation` | `Manufacturing-2013-05-TimeWayPlan/getTWPInformation` |
| **2013-05** | TimeWayPlan | `setProductImage` | `Manufacturing-2013-05-TimeWayPlan/setProductImage` |
| **2013-12** | Model | `computeAppearancePath` | `Manufacturing-2013-12-Model/computeAppearancePath` |
| **2013-12** | ResourceManagement | `getStepP21FileCounts` | `Manufacturing-2013-12-ResourceManagement/getStepP21FileCounts` |
| **2013-12** | ResourceManagement | `getVendorCatalogInfo` | `Manufacturing-2013-12-ResourceManagement/getVendorCatalogInfo` |
| **2013-12** | ResourceManagement | `importStep3DModels` | `Manufacturing-2013-12-ResourceManagement/importStep3DModels` |
| **2013-12** | ResourceManagement | `importStepP21Files` | `Manufacturing-2013-12-ResourceManagement/importStepP21Files` |
| **2013-12** | ResourceManagement | `importVendorCatalogHierarchy` | `Manufacturing-2013-12-ResourceManagement/importVendorCatalogHierarchy` |
| **2013-12** | ResourceManagement | `updateNXToolAssemblies` | `Manufacturing-2013-12-ResourceManagement/updateNXToolAssemblies` |
| **2014-06** | DataManagement | `addOrRemoveAssociatedContexts` | `Manufacturing-2014-06-DataManagement/addOrRemoveAssociatedContexts` |
| **2014-06** | DataManagement | `cloneAssemblyAndProcessObjects` | `Manufacturing-2014-06-DataManagement/cloneAssemblyAndProcessObjects` |
| **2014-06** | DataManagement | `establishOriginLink` | `Manufacturing-2014-06-DataManagement/establishOriginLink` |
| **2014-06** | DataManagement | `getProcessResourceRelatedInfo` | `Manufacturing-2014-06-DataManagement/getProcessResourceRelatedInfo` |
| **2014-06** | ResourceManagement | `checkToolParameters` | `Manufacturing-2014-06-ResourceManagement/checkToolParameters` |
| **2014-06** | StructureSearch | `searchConnectedLines` | `Manufacturing-2014-06-StructureSearch/searchConnectedLines` |
| **2014-12** | IPAManagement | `findAndRepopulateDynamicIPAs` | `Manufacturing-2014-12-IPAManagement/findAndRepopulateDynamicIPAs` |
| **2014-12** | IPAManagement | `repopulateDynamicIPAs` | `Manufacturing-2014-12-IPAManagement/repopulateDynamicIPAs` |
| **2014-12** | Model | `validateScopeFlowsConsistency` | `Manufacturing-2014-12-Model/validateScopeFlowsConsistency` |
| **2014-12** | StructureSearch | `createOrUpdateAssignmentRecipe` | `Manufacturing-2014-12-StructureSearch/createOrUpdateAssignmentRecipe` |
| **2014-12** | StructureSearch | `deleteAssignmentRecipes` | `Manufacturing-2014-12-StructureSearch/deleteAssignmentRecipes` |
| **2014-12** | StructureSearch | `getAssignmentRecipes` | `Manufacturing-2014-12-StructureSearch/getAssignmentRecipes` |
| **2014-12** | StructureSearch | `resolveAssignmentRecipe` | `Manufacturing-2014-12-StructureSearch/resolveAssignmentRecipe` |
| **2014-12** | Validation | `getMaturityReport` | `Manufacturing-2014-12-Validation/getMaturityReport` |
| **2015-03** | StructureManagement | `moveAndResequenceNodes` | `Manufacturing-2015-03-StructureManagement/moveAndResequenceNodes` |
| **2015-10** | ImportExport | `importManufacturingFeatures` | `Manufacturing-2015-10-ImportExport/importManufacturingFeatures` |
| **2015-10** | StructureManagement | `createCollabPlanningContext` | `Manufacturing-2015-10-StructureManagement/createCollabPlanningContext` |
| **2016-03** | ImportExport | `exportToBriefcase` | `Manufacturing-2016-03-ImportExport/exportToBriefcase` |
| **2016-03** | ImportExport | `importManufacturingFeatures` | `Manufacturing-2016-03-ImportExport/importManufacturingFeatures` |
| **2017-05** | ImportExport | `importFromBriefcase` | `Manufacturing-2017-05-ImportExport/importFromBriefcase` |
| **2017-05** | Validation | `getAllRegisteredCallbacks` | `Manufacturing-2017-05-Validation/getAllRegisteredCallbacks` |
| **2017-11** | DataManagement | `getConnectorInfo` | `Manufacturing-2017-11-DataManagement/getConnectorInfo` |
| **2017-11** | DataManagement | `getPhysicalAttachmentsInScope` | `Manufacturing-2017-11-DataManagement/getPhysicalAttachmentsInScope` |
| **2017-11** | DataManagement | `removePhysicalAttachementRelation` | `Manufacturing-2017-11-DataManagement/removePhysicalAttachementRelation` |
| **2017-11** | DataManagement | `setConnectorInfo` | `Manufacturing-2017-11-DataManagement/setConnectorInfo` |
| **2017-11** | DataManagement | `setPhysicalAttachementsInScope` | `Manufacturing-2017-11-DataManagement/setPhysicalAttachementsInScope` |
| **2018-06** | DataManagement | `getOccurrenceKinematicsInformation` | `Manufacturing-2018-06-DataManagement/getOccurrenceKinematicsInformation` |
| **2018-06** | DataManagement | `setOccurrenceKinematicsInformation` | `Manufacturing-2018-06-DataManagement/setOccurrenceKinematicsInformation` |
| **2018-11** | StructureManagement | `copyRecursively` | `Manufacturing-2018-11-StructureManagement/copyRecursively` |
| **2018-11** | StructureManagement | `pasteDuplicateStructure` | `Manufacturing-2018-11-StructureManagement/pasteDuplicateStructure` |
| **2019-06** | DataManagement | `publishSelectionFromStudyToSource` | `Manufacturing-2019-06-DataManagement/publishSelectionFromStudyToSource` |
| **2019-06** | DataManagement | `syncSelectionInStudyWithSource` | `Manufacturing-2019-06-DataManagement/syncSelectionInStudyWithSource` |
| **2020-04** | Core | `cancelManufacturingCheckout` | `Manufacturing-2020-04-Core/cancelManufacturingCheckout` |

### 版本—Service 对照

| API 版本 | 包含的 Service | 操作数 |
|----------|----------------|--------|
| 2008-06 | Core、DataManagement、TimeManagement | 5 |
| 2008-12 | IPAManagement | 4 |
| 2009-06 | StructureManagement | 8 |
| 2009-10 | DataManagement、MFGPropertyCollector、Model、ModelDefinitions、StructureManagement、StructureSearch | 17 |
| 2010-09 | Core、ImportExport、TimeManagement | 7 |
| 2011-06 | DataManagement、StructureManagement | 6 |
| 2012-02 | Constraints、DataManagement、IPAManagement、Model | 17 |
| 2012-09 | DataManagement、Validation | 4 |
| 2013-05 | Core、DataManagement、ImportExport、IPAManagement、StructureManagement、StructureSearch、TimeWayPlan | 15 |
| 2013-12 | Model、ResourceManagement | 7 |
| 2014-06 | DataManagement、ResourceManagement、StructureSearch | 6 |
| 2014-12 | IPAManagement、Model、StructureSearch、Validation | 8 |
| 2015-03 | StructureManagement | 1 |
| 2015-10 | ImportExport、StructureManagement | 2 |
| 2016-03 | ImportExport | 2 |
| 2017-05 | ImportExport、Validation | 2 |
| 2017-11 | DataManagement | 5 |
| 2018-06 | DataManagement | 2 |
| 2018-11 | StructureManagement | 2 |
| 2019-06 | DataManagement | 2 |
| 2020-04 | Core | 1 |

---

## 2. 按 Service 合并（跨版本）

同一 Service 下按 **API 版本（年-月）** 分组；调用时必须使用对应版本的 Url。

### 2.1 约束（Constraints）

**涵盖 API 版本：** `2012-02`  
**操作数：** 4

#### 版本 2012-02

##### 2.1.1.1 getPrecedenceConstraintPaths

**接口路径：** `Manufacturing-2012-02-Constraints/getPrecedenceConstraintPaths`

**API 版本：** `2012-02`  
**Service：** `Constraints`  
**Library：** `Manufacturing`

**说明：** 获取给定起止操作/工艺之间的优先顺序约束路径。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Constraints.getPrecedenceConstraintPaths`

**请求（input）：**

```json
{
  "inputData": [
    {
      "startNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "endNode": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputData` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::GetPrecedenceConstraintPathsInputs[] | 输入 data 包含 列表，元素为 start and 终止操作 or 工艺行s. |

**响应（output）：**

```json
{
  "results": [
    {
      "paths": [
        {
          "components": [
            {
              "predecessor": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "constraint": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "constraintIsInherited": ""
            }
          ],
          "endNode": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::GetPrecedenceConstraintPathsResult[] | A 列表，元素为 result structures that conta在 paths 对于每个 起点与终点 node pair specfied 在 输入 structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 对象 对于 matching GetPrecedenceConstraintPathsInputs 结构. |

---

##### 2.1.1.2 getPrecedenceConstraints

**接口路径：** `Manufacturing-2012-02-Constraints/getPrecedenceConstraints`

**API 版本：** `2012-02`  
**Service：** `Constraints`  
**Library：** `Manufacturing`

**说明：** 获取指定对象的前驱与后继优先顺序约束（可配置遍历层级）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Constraints.getPrecedenceConstraints`

**请求（input）：**

```json
{
  "inputData": [
    {
      "predecessorLevel": "",
      "successorLevel": "",
      "inputObject": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputData` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::GetPrecedenceConstraintsIn[] | The 列表，元素为 输入 对象 (Mfg0BvrProcess / Mfg0BvrOperation) whose precedence constraints are to be fetched along 与 数量为 levels to be traversed 在 predecessor and successor chains. |

**响应（output）：**

```json
{
  "predecessorMap": {},
  "successorMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `predecessorMap` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::AdjacentObjectsMap | The 映射，键值对为 对象 到ir predecessors |
| `successorMap` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::AdjacentObjectsMap | The 映射，键值对为 对象 到ir successors |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 结构 |

---

##### 2.1.1.3 validateConstraintConsistency

**接口路径：** `Manufacturing-2012-02-Constraints/validateConstraintConsistency`

**API 版本：** `2012-02`  
**Service：** `Constraints`  
**Library：** `Manufacturing`

**说明：** 校验产品 BOP 或其子结构中的优先顺序约束是否一致。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Constraints.validateConstraintConsistency`

**请求（input）：**

```json
{
  "inputData": [
    {
      "constraintTypes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "rootNodes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputData` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::ValidateConstraintConsistencyInputs[] | A 向量，元素为 ValidateConstraintConsistencyInputs structures that 定义 one or multiple substructures to check. |

**响应（output）：**

```json
{
  "results": [
    {
      "errors": [
        {
          "constraintType": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "message": "",
          "objects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "constraints": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::ValidateConstraintConsistencyResult[] | The 列表，元素为 result structures that holds one entry 对于每个 输入 结构. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 对象 for this request. |

---

##### 2.1.1.4 validateProcessAreaAssignments

**接口路径：** `Manufacturing-2012-02-Constraints/validateProcessAreaAssignments`

**API 版本：** `2012-02`  
**Service：** `Constraints`  
**Library：** `Manufacturing`

**说明：** 校验产品 BOP 操作/工艺与工厂 BOP 工艺区域分配是否符合约束定义。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Constraints.validateProcessAreaAssignments`

**请求（input）：**

```json
{
  "inputData": [
    {
      "constraintTypes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "contextToValidate": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "contextOfConstraints": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "rootProcessAreas": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "maxErrors": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputData` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::ValidateProcessAreaAssignmentsInputs[] | A 向量，元素为 ValidateProcessAreaAssignmentsInputs structures that define the the Plant and 产品 BOPs and the 集合，元素为 nodes to validate 在 工厂 BOP. |

**响应（output）：**

```json
{
  "results": [
    {
      "errors": [
        {
          "constraintType": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "message": "",
          "objectsOfContextOfConstraint": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "objectsOfContextToValidate": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "processAreas": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "constraints": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::ValidateProcessAreaAssignmentsResult[] | The 列表，元素为 result structures that holds one entry 对于每个 输入 结构. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 对象 for this request. |

---

### 2.2 核心（Core）

**涵盖 API 版本：** `2008-06`、`2010-09`、`2013-05`、`2020-04`  
**操作数：** 6

#### 版本 2008-06

##### 2.2.1.1 findCheckedOutsInStructure

**接口路径：** `Manufacturing-2008-06-Core/findCheckedOutsInStructure`

**API 版本：** `2008-06`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 在指定结构范围内查找所有已检出对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_06.Core.findCheckedOutsInStructure`

**请求（input）：**

```json
{
  "searchScope": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchScope` | Teamcenter::BusinessObject[] | 向量，元素为 l即 that we would like to get all the 已检出 对象 from. |

**响应（output）：**

```json
{
  "checkedOutList": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `checkedOutList` | Teamcenter::BusinessObject[] | This is the 结构 包含 Tags of all the 已检出s 对象. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

#### 版本 2010-09

##### 2.2.2.1 findNodeInContext

**接口路径：** `Manufacturing-2010-09-Core/findNodeInContext`

**API 版本：** `2010-09`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 在目标上下文中根据输入条件查找与选定节点相关的对象。（存在 2010-09、2013-05 两个 API 版本，接口定义可能不同）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.Core.findNodeInContext`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "nodes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "byIdOnly": "",
      "allContexts": "",
      "inContextLine": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2010_09::Core::FindNodeInContextInputInfo[] | 输入 struct. |

**响应（output）：**

```json
{
  "resultInfo": [
    {
      "clientID": "",
      "resultNodes": [
        {
          "foundNodes": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "originalNode": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `resultInfo` | Teamcenter::Soa::Manufacturing::_2010_09::Core::FoundNodesInfo[] | Infornation retrieves 对于每个 输入 struct that we looked for. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据. |

---

##### 2.2.2.2 getAffectedProperties

**接口路径：** `Manufacturing-2010-09-Core/getAffectedProperties`

**API 版本：** `2010-09`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 当工艺/操作中节点工期变更时，返回受影响依赖节点的运行时属性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.Core.getAffectedProperties`

**请求（input）：**

```json
{
  "arguments": [
    {
      "rootNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "changedNodes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "changedProperties": [
        ""
      ]
    }
  ],
  "requestedProperties": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arguments` | Teamcenter::Soa::Manufacturing::_2010_09::Core::GetAffectedPropertiesArg[] | A 列表，元素为 GetAffectedPropertiesChanges structures that describe the changes that have been made to a process or 操作 结构. |
| `requestedProperties` | std::string[] | The names 的 属性 that are to be retrieved. 在 first version only the 属性 that are processed by the Gantt application are accepted (Mfg0calc_duration, Mfg0calc_start_time, Mfg0calc_dur_start_time). |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2013-05

##### 2.2.3.1 findNodeInContext

**接口路径：** `Manufacturing-2013-05-Core/findNodeInContext`

**API 版本：** `2013-05`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 在目标上下文中根据输入条件查找与选定节点相关的对象。（存在 2010-09、2013-05 两个 API 版本，接口定义可能不同）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.Core.findNodeInContext`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "nodes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "byIdOnly": "",
      "allContexts": "",
      "inContextLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationTypes": [
        ""
      ],
      "relationDirection": "",
      "relationDepth": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::Core::FindNodeInContextInputInfo[] | 输入 struct |

**响应（output）：**

```json
{
  "resultInfo": [
    {
      "clientID": "",
      "resultNodes": [
        {
          "foundNodes": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "originalNode": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `resultInfo` | Teamcenter::Soa::Manufacturing::_2010_09::Core::FoundNodesInfo[] | Infornation retrieves 对于每个 输入 struct that we looked for. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据. |

---

##### 2.2.3.2 matchObjectsAgainstVariantRules

**接口路径：** `Manufacturing-2013-05-Core/matchObjectsAgainstVariantRules`

**API 版本：** `2013-05`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 将运行时对象与变型规则列表匹配，判断对象在各变型规则下是否配置可见。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.Core.matchObjectsAgainstVariantRules`

**请求（input）：**

```json
{
  "args": [
    {
      "objects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "variantRules": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `args` | Teamcenter::Soa::Manufacturing::_2013_05::Core::MatchObjectsAgainstVariantRulesArg[] | A 列表，元素为 structures, 其中 each entry describes a 列表，元素为 runtime 对象 and a 列表，元素为 变型规则 or product variants that are matched against each other. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "results": [
    {
      "matrix": {},
      "warnings": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 对象 for this request. |
| `results` | Teamcenter::Soa::Manufacturing::_2013_05::Core::MatchObjectsAgainstVariantRulesResult[] | A 列表，元素为 result structures; each entry corresponds to an entry 在 MatchObjectsAgainstVariantRulesArg 向量 passed 到 matchObjectsAgainstVariantRules 操作. |

---

#### 版本 2020-04

##### 2.2.4.1 cancelManufacturingCheckout

**接口路径：** `Manufacturing-2020-04-Core/cancelManufacturingCheckout`

**API 版本：** `2020-04`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 取消用户对制造 BOP/工艺/操作/研究等工作对象的检出状态。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2020_04.Core.cancelManufacturingCheckout`

**请求（input）：**

```json
{
  "rootObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "additionalInfo": {
    "strToBooleanVectorMap": {},
    "strToDateVectorMap": {},
    "strToDoubleVectorMap": {},
    "strToIntegerVectorMap": {},
    "strToObjVectorMap": {},
    "strToStringVectorMap": {}
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `rootObjects` | Teamcenter::BusinessObject[] | A 列表，元素为 对象 to cancel checkout. Valid types are: Mfg0BvrProcess, Mfg0BvrProcessArea, Mfg0MESimStudy, Mfg0MEShdStudy, Mfg0BvrOperation and Mfg0BvrWorkarea. |
| `additionalInfo` | Teamcenter::Soa::Manufacturing::_2020_04::Core::AdditionalInfo | Additional information in form of generic 映射 (string, 列表，元素为 boolean) . Valid keys: "isConsiderSubHierarchy". If true, sub hierarchy is traversed and all checkouts 在 hierarchy are canceled. If false, the 操作 取消 checkout 对… |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.3 数据管理（DataManagement）

**涵盖 API 版本：** `2008-06`、`2009-10`、`2011-06`、`2012-02`、`2012-09`、`2013-05`、`2014-06`、`2017-11`、`2018-06`、`2019-06`  
**操作数：** 33

#### 版本 2008-06

##### 2.3.1.1 createOrUpdateMEActivityFolders

**接口路径：** `Manufacturing-2008-06-DataManagement/createOrUpdateMEActivityFolders`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 创建或更新 ME 活动文件夹；支持多级子活动。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_06.DataManagement.createOrUpdateMEActivityFolders`

**请求（input）：**

```json
{
  "activityInfos": [
    {
      "activity": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "name": "",
      "description": "",
      "type": "",
      "toolInfo": {
        "processBV": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "toolOccThreadChains": {}
      },
      "contents": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "parentActivities": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "predecessors": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "attributes": [
        {
          "name": "",
          "values": [
            ""
          ]
        }
      ],
      "complete": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `activityInfos` | Teamcenter::Soa::Manufacturing::_2008_06::DataManagement::MEActivityFolderInfo[] | 输入 is a 向量，元素为 ME 活动文件夹Info structs. A Boolean 值 part 的 结构 signifying if 输入 data 表示 the complete representation 的 folder tools, predecessors, and contents or if it 表示 对象 to be appended 到 existing folder tools, predecesso… |

**响应（output）：**

```json
{
  "successfullyProcessedMEAct": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `successfullyProcessedMEAct` | Teamcenter::Soa::Manufacturing::_2008_06::DataManagement::SuccessFullyProcessedMapMEAct | successfullyProcessedMEAct |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

##### 2.3.1.2 createOrUpdateMENXObjects

**接口路径：** `Manufacturing-2008-06-DataManagement/createOrUpdateMENXObjects`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 创建或更新 MENX 对象及其属性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_06.DataManagement.createOrUpdateMENXObjects`

**请求（input）：**

```json
{
  "meObjectInfos": [
    {
      "menxObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "name": "",
      "description": "",
      "type": "",
      "subType": "",
      "attributes": [
        {
          "name": "",
          "values": [
            ""
          ]
        }
      ]
    }
  ],
  "container": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `meObjectInfos` | Teamcenter::Soa::Manufacturing::_2008_06::DataManagement::MENXObjectInfo[] | 输入 is a 向量，元素为 MENX 对象Info structs. |
| `container` | Teamcenter::Folder | The folder into 其 the created 对象 are to be placed. This can be a NULLTAG in 其 case the created 对象 will not be inserted 到ny folder. |

**响应（output）：**

```json
{
  "successfullyProcessedMENXObj": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `successfullyProcessedMENXObj` | Teamcenter::Soa::Manufacturing::_2008_06::DataManagement::SuccessFullyProcessedMapMENXObj | successfullyProcessedMENXObj |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

#### 版本 2009-10

##### 2.3.2.1 createObjects

**接口路径：** `Manufacturing-2009-10-DataManagement/createObjects`

**API 版本：** `2009-10`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 通用制造对象创建，支持递归创建附属对象（如 Item、版本、表单等）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.DataManagement.createObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": "",
      "data": {
        "type": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "compoundCreateInput": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2009_10::DataManagement::CreateIn[] | a 列表，元素为 CreateIn 对象 representing the Create 输入 for 业务对象 to be created |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "objects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2009_10::DataManagement::CreateOut[] | 向量，元素为 输出 对象 representing 对象 that were created |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 包括 部分错误 that are mapped 到 客户端 ID |

---

##### 2.3.2.2 disconnectObjects

**接口路径：** `Manufacturing-2009-10-DataManagement/disconnectObjects`

**API 版本：** `2009-10`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 断开制造节点之间的连接关系。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.DataManagement.disconnectObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "disconnectFrom": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2009_10::DataManagement::DisconnectInput[] | A 列表，元素为 disconnectInput 对象 对于 对象 to disconnect |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2011-06

##### 2.3.3.1 closeContexts

**接口路径：** `Manufacturing-2011-06-DataManagement/closeContexts`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 关闭基础视图窗口（Context）及其关联的 OG 视图。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.DataManagement.closeContexts`

**请求（input）：**

```json
{
  "contexts": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `contexts` | Teamcenter::BusinessObject[] | A 向量 与 contexts (top lines 的 windows) to close |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.3.2 closeViews

**接口路径：** `Manufacturing-2011-06-DataManagement/closeViews`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 关闭已打开的 OG 视图窗口。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.DataManagement.closeViews`

**请求（input）：**

```json
{
  "structureContext": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "views": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `structureContext` | Teamcenter::BusinessObject | The 结构 context 包含 views. Can be NULL if not 使用 structire context. |
| `views` | Teamcenter::BusinessObject[] | A 向量 与 open views (top lines 的 OG windows) to close |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.3.3 openContexts

**接口路径：** `Manufacturing-2011-06-DataManagement/openContexts`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 在新建基础视图窗口中打开现有对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.DataManagement.openContexts`

**请求（input）：**

```json
{
  "input": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "openViews": "",
      "openAssociatedContexts": "",
      "contextSettings": {
        "type": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "compoundCreateInput": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2011_06::DataManagement::OpenContextInput[] | A 列表，元素为 OpenContextInput representing the 对象 to open |

**响应（output）：**

```json
{
  "output": [
    {
      "contexts": [
        {
          "context": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "views": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "structureContext": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "collaborationContext": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2011_06::DataManagement::ContextGroup[] | A 向量 with information 的 method 输出 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 操作 ServiceData（服务数据） |

---

##### 2.3.3.4 openViews

**接口路径：** `Manufacturing-2011-06-DataManagement/openViews`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 打开 OG 视图窗口。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.DataManagement.openViews`

**请求（input）：**

```json
{
  "context": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "structureContext": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "views": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `context` | Teamcenter::BusinessObject | The context (top line 的 base view window) for 其 the views 将 opened |
| `structureContext` | Teamcenter::BusinessObject | The 结构 context 包含 context. This can be null |
| `views` | Teamcenter::BusinessObject[] | A 向量 与 views to open |

**响应（output）：**

```json
{
  "views": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `views` | Teamcenter::BusinessObject[] | A 向量 与 opened views (the top lines 的 created OG windows) |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 操作 ServiceData（服务数据） |

---

#### 版本 2012-02

##### 2.3.4.1 addAssociatedContexts

**接口路径：** `Manufacturing-2012-02-DataManagement/addAssociatedContexts`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 建立工厂 BOP 与产品 BOP 等对象之间的关联上下文。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.addAssociatedContexts`

**请求（input）：**

```json
{
  "input": [
    {
      "associateToContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "addedContexts": [
        {
          "context": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationName": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AddAssociationInput[] | 列表，元素为 AddAssociationInput BOM 行s 对于 contexts to be 关联. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.4.2 associateAndAllocateByPreview

**接口路径：** `Manufacturing-2012-02-DataManagement/associateAndAllocateByPreview`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 按预览结果执行关联与分配操作。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.associateAndAllocateByPreview`

**请求（input）：**

```json
{
  "input": {
    "sourceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "targetPlantBOPLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "referenceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    }
  },
  "allocationMap": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AssociateAndAllocateInput | 输入，用于指定 source, target and reference 对象. |
| `allocationMap` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AllocationMap | 映射，键值对为 allocations 从 source 结构 到 target 结构. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": {
    "ticket": "",
    "fileName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 将包含 部分错误, warnings and 错误, 若有. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::FileTicket | 文件票据 包含 UID and 文件 名称 对于 日志文件 为本命令生成. |

---

##### 2.3.4.3 automaticAllocatePreview

**接口路径：** `Manufacturing-2012-02-DataManagement/automaticAllocatePreview`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 自动分配预览，返回拟分配结果供确认。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.automaticAllocatePreview`

**请求（input）：**

```json
{
  "input": {
    "sourceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "targetPlantBOPLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "referenceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AssociateAndAllocateInput | 输入，用于指定 source, target and reference 对象. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "previewFileTicket": {
    "ticket": "",
    "fileName": ""
  },
  "allocationMap": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 将包含 部分错误, warnings and 错误, 若有. |
| `previewFileTicket` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::FileTicket | 文件票据 包含 UID and 文件 名称 对于 CSV 文件 generated for preview during this command. |
| `allocationMap` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AllocationMap | 映射，键值对为 allocations 从 source 结构 到 target 结构. |

---

##### 2.3.4.4 automaticAssociateAndAllocate

**接口路径：** `Manufacturing-2012-02-DataManagement/automaticAssociateAndAllocate`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 自动完成关联与分配。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.automaticAssociateAndAllocate`

**请求（input）：**

```json
{
  "input": {
    "sourceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "targetPlantBOPLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "referenceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AssociateAndAllocateInput | 输入，用于指定 source, target and reference 对象. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": {
    "ticket": "",
    "fileName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 将包含 部分错误, warnings and 错误, 若有. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::FileTicket | 文件票据 包含 UID and 文件 名称 对于 日志文件 为本命令生成. |

---

##### 2.3.4.5 connectObjects

**接口路径：** `Manufacturing-2012-02-DataManagement/connectObjects`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 连接制造（MFG）节点，支持粘贴特殊场景下的数量与出现次数参数。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.connectObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "targetObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "sourceInfo": {
        "sourceObjects": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "relationType": "",
        "relationName": "",
        "additionalInfo": {
          "stringProps": {},
          "stringArrayProps": {},
          "dateProps": {},
          "dateArrayProps": {},
          "tagProps": {},
          "tagArrayProps": {},
          "doubleProps": {},
          "doubleArrayProps": {},
          "floatProps": {},
          "floatArrayProps": {},
          "intProps": {},
          "intArrayProps": {},
          "boolProps": {},
          "boolArrayProps": {}
        }
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::ConnectObjectsInputData[] | A 列表，元素为 ConnectInput BOM 行s 对于 nodes to connect |

**响应（output）：**

```json
{
  "newObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `newObjects` | Teamcenter::BusinessObject[] | new BOM 行s, created as a result of connection 操作 under the new target BOM 行s |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

##### 2.3.4.6 disconnectFromOrigin

**接口路径：** `Manufacturing-2012-02-DataManagement/disconnectFromOrigin`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 断开与源对象的链接关系。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.disconnectFromOrigin`

**请求（input）：**

```json
{
  "inputVector": [
    {
      "lineToDisconnect": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isRecursive": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputVector` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::DisconnectFromOriginInputData[] | 向量，元素为 DisconnectFromOriginInputData specifying the lines to be disconnected and 是否 the children are to be recursively disconnected too. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.4.7 getAssociatedContexts

**接口路径：** `Manufacturing-2012-02-DataManagement/getAssociatedContexts`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 获取对象已关联的上下文列表。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.getAssociatedContexts`

**请求（input）：**

```json
{
  "input": [
    {
      "associateToContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::GetAssociatedContextsInputData[] | 输入 |

**响应（output）：**

```json
{
  "output": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "associatedContextsInfo": [
        {
          "context": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationName": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AssociateOutput[] | A 向量，元素为 BOM 行s 关联 到 输入 context |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 部分错误 mapped 到 客户端 ID |

---

#### 版本 2012-09

##### 2.3.5.1 applyConfigObjects

**接口路径：** `Manufacturing-2012-09-DataManagement/applyConfigObjects`

**API 版本：** `2012-09`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 应用配置对象到目标结构。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_09.DataManagement.applyConfigObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "configObj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_09::DataManagement::ApplyConfigInput[] | 输入参数s for applying configuration 对象 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.5.2 createOrUpdateConfigObjects

**接口路径：** `Manufacturing-2012-09-DataManagement/createOrUpdateConfigObjects`

**API 版本：** `2012-09`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 创建或更新制造配置对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_09.DataManagement.createOrUpdateConfigObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "data": {
        "type": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "compoundCreateInput": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      },
      "modifyObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "basedOn": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "internalConfigData": []
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_09::DataManagement::CreateConfigInput[] | 向量，元素为 CreateConfigInput 结构 其 包含 information for creating or updating context 对象. |

**响应（output）：**

```json
{
  "output": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "internalConfigData": []
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2012_09::DataManagement::CreateConfigOutput[] | 对象 of CreateConfigOutput. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 包括 部分错误. |

---

#### 版本 2013-05

##### 2.3.6.1 createAttachments

**接口路径：** `Manufacturing-2013-05-DataManagement/createAttachments`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 为业务对象创建附件对象（支持增量模式）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.DataManagement.createAttachments`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": "",
      "data": {
        "type": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "compoundCreateInput": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2009_10::DataManagement::CreateIn[] | A 列表，元素为 CreateIn 对象 representing the Create 输入 for 业务对象 to be created. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "objects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2009_10::DataManagement::CreateOut[] | 向量，元素为 输出 对象 representing 对象 that were created |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 包括 部分错误 that are mapped 到 客户端 ID |

---

##### 2.3.6.2 setAttributes

**接口路径：** `Manufacturing-2013-05-DataManagement/setAttributes`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 设置业务对象及其附加对象的属性值。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.DataManagement.setAttributes`

**请求（input）：**

```json
{
  "input": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attachedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attributeDetails": [
        {
          "attributeName": "",
          "attributeValueDetails": {
            "dataType": "",
            "boolAttributes": [],
            "charAttributes": "",
            "integerAttributes": [],
            "doubleAttributes": [],
            "stringAttributes": [
              ""
            ],
            "tagAttributes": [
              {
                "uid": "",
                "type": "",
                "className": ""
              }
            ],
            "dateAttributes": [
              "0001-01-01T00:00:00"
            ]
          }
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::DataManagement::ObjectAttributesInput[] | 输入 结构 包含 对象(s) to be edited and the details 的 属性 or relations 其 need to be edited. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.6.3 syncStudyAndSource

**接口路径：** `Manufacturing-2013-05-DataManagement/syncStudyAndSource`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 将仿真研究与源 BOP 结构同步，返回 FMS 文件信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.DataManagement.syncStudyAndSource`

**请求（input）：**

```json
{
  "input": [
    {
      "study": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "direction": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::DataManagement::SyncStudyInput[] | The Mfg0BvrStudy 对象 to synchronize and the direction to synchronize (to/从 study). |

**响应（output）：**

```json
{
  "logFileTicket": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `logFileTicket` | std::string | The fmd 票据 到 日志文件 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard 服务数据 |

---

#### 版本 2014-06

##### 2.3.7.1 addOrRemoveAssociatedContexts

**接口路径：** `Manufacturing-2014-06-DataManagement/addOrRemoveAssociatedContexts`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 添加或移除各类关联上下文（由输入参数控制目标类型）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.DataManagement.addOrRemoveAssociatedContexts`

**请求（input）：**

```json
{
  "input": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "addContext": [
        {
          "context": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationName": ""
        }
      ],
      "removeContext": [
        {
          "context": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationName": ""
        }
      ],
      "actionMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_06::DataManagement::AddOrRemoveContextsInfo[] | A target context , 列表，元素为 contexts to associate, 列表，元素为 contexts to remove and the parameters that governs the functionality. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.7.2 cloneAssemblyAndProcessObjects

**接口路径：** `Manufacturing-2014-06-DataManagement/cloneAssemblyAndProcessObjects`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 响应工程 BOM 变更，在制造 BOM 中克隆装配与工艺对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.DataManagement.cloneAssemblyAndProcessObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "sourceObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scopeSearchObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "sourceOccEff": "",
      "newCloneOccEff": "",
      "additionalInfo": {
        "stringProps": {},
        "stringArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {},
        "boolArrayProps": {}
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_06::DataManagement::CloneAssemblyInputData[] | 包含 source 对象 that should be cloned, target parent 对象 对于 cloned 对象 and additional parameters that govern the functionality. |

**响应（output）：**

```json
{
  "clonedObject": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clonedObject` | Teamcenter::BusinessObject | 业务对象 of new BOM 行 对象, created as a result of clone 操作 under the new target. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard 服务数据 |

---

##### 2.3.7.3 establishOriginLink

**接口路径：** `Manufacturing-2014-06-DataManagement/establishOriginLink`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 在工艺/操作之间建立源（Origin）链接。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.DataManagement.establishOriginLink`

**请求（input）：**

```json
{
  "input": {
    "inputObjects": [
      {
        "sourceObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "targetObjects": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    ],
    "criteria": [
      ""
    ],
    "considerHierarchy": "",
    "action": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_06::DataManagement::EstablishOriginLinkInfo | A 列表，元素为 a source and targets to be linked and the parameters that governs the functionality. |

**响应（output）：**

```json
{
  "candidates": [
    {
      "sourceObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "targetObjects": [
        {
          "targetObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "linkState": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData",
  "logFileTicket": {
    "ticket": "",
    "fileName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `candidates` | Teamcenter::Soa::Manufacturing::_2014_06::DataManagement::EstablishOriginLinkCandidates[] | The source and target 对象 与ir linked state. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 包含 部分错误 若有. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::FileTicket | The 文件票据 包含 UID and 文件 名称 对于 日志文件 为本命令生成. |

---

##### 2.3.7.4 getProcessResourceRelatedInfo

**接口路径：** `Manufacturing-2014-06-DataManagement/getProcessResourceRelatedInfo`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 获取工艺资源相关工作内容信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.DataManagement.getProcessResourceRelatedInfo`

**请求（input）：**

```json
{
  "input": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "objectPreference": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::BusinessObject[] | 输入 包含 对象 for 其 process-resource 相关 information is 必需. The valid 对象 are BOM 行 在 context of 工厂 BOP 结构 as specified below - Mfg0BvrProcessLine - 工艺行 - Mfg0BvrProcessArea - Process area - Mfg0BvrProcessStation - Process stat… |
| `objectPreference` | std::string | 指定 the 对象 that response must return. The valid 值 are Process, 操作 and ProcessAndOperation denoting respectively that process of 类型 Mfg0BvrProcess, 操作 of 类型 Mfg0BvrOperation and both process and 操作 that are allocated to 工艺… |

**响应（output）：**

```json
{
  "infoMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `infoMap` | Teamcenter::Soa::Manufacturing::_2014_06::DataManagement::ProcResourceRelatedInfoMap | 映射，键值对为 BOM 行 对象 (业务对象/列表，元素为 业务对象). If the key is process area of 类型 Mfg0BvrProcessArea then 值 is 列表，元素为 工艺资源s of 类型 Mfg0BvrProcessResource that are defined under the process area and process/操作 of 类型 Mfg0BvrProcess/Mfg… |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误. |

---

#### 版本 2017-11

##### 2.3.8.1 getConnectorInfo

**接口路径：** `Manufacturing-2017-11-DataManagement/getConnectorInfo`

**API 版本：** `2017-11`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 获取连接器（Connector）信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_11.DataManagement.getConnectorInfo`

**请求（input）：**

```json
{
  "itemRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `itemRevs` | Teamcenter::BusinessObject[] | 列表，元素为 ItemRevision（物料版本） for 其 connector information is 必需. |

**响应（output）：**

```json
{
  "connectorInfo": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "connectorProperties": [
        {
          "stringProps": {},
          "stringArrayProps": {},
          "dateProps": {},
          "dateArrayProps": {},
          "tagProps": {},
          "tagArrayProps": {},
          "doubleProps": {},
          "doubleArrayProps": {},
          "floatProps": {},
          "floatArrayProps": {},
          "intProps": {},
          "intArrayProps": {},
          "boolProps": {},
          "boolArrayProps": {}
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `connectorInfo` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::ConnectorTableInfo[] | 列表，元素为 structures containing connector information for given ItemRevision（物料版本） 对象. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 部分错误 as part 的 ServiceData（服务数据）. |

---

##### 2.3.8.2 getPhysicalAttachmentsInScope

**接口路径：** `Manufacturing-2017-11-DataManagement/getPhysicalAttachmentsInScope`

**API 版本：** `2017-11`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 获取作用域内的物理附件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_11.DataManagement.getPhysicalAttachmentsInScope`

**请求（input）：**

```json
{
  "input": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::GetPhysicalAttachmentsInput[] | 输入 包含以下内容的结构体 scope and context information for 其 the attachments need to be retrieved. |

**响应（output）：**

```json
{
  "attachmentsInfo": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "source": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": "",
      "relationInfo": {
        "stringProps": {},
        "stringArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {},
        "boolArrayProps": {}
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `attachmentsInfo` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::PhysicalAttachmentInfo[] | 列表，元素为 structures containing information about the physical attachment relation Mfg0MEPhysicalAttachment or Mfg0MEMountToolToRobot between AbsOccurrence of BOM 行 对象 under the given scope Mfg0BvrWorkarea. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 部分错误 as part 的 ServiceData（服务数据）. |

---

##### 2.3.8.3 removePhysicalAttachementRelation

**接口路径：** `Manufacturing-2017-11-DataManagement/removePhysicalAttachementRelation`

**API 版本：** `2017-11`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 移除物理附件关系。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_11.DataManagement.removePhysicalAttachementRelation`

**请求（input）：**

```json
{
  "input": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "source": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::RemovePhysicalAttachmentRelInput[] | 输入 包含以下内容的结构体 information about the context Mfg0BvrWorkarea, scope Mfg0BvrWorkarea and the source and target BOM 行. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.8.4 setConnectorInfo

**接口路径：** `Manufacturing-2017-11-DataManagement/setConnectorInfo`

**API 版本：** `2017-11`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 设置连接器信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_11.DataManagement.setConnectorInfo`

**请求（input）：**

```json
{
  "input": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "connectorInformation": [
        {
          "stringProps": {},
          "stringArrayProps": {},
          "dateProps": {},
          "dateArrayProps": {},
          "tagProps": {},
          "tagArrayProps": {},
          "doubleProps": {},
          "doubleArrayProps": {},
          "floatProps": {},
          "floatArrayProps": {},
          "intProps": {},
          "intArrayProps": {},
          "boolProps": {},
          "boolArrayProps": {}
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::SetConnectorInput[] | 输入 包含以下内容的结构体 information about the ItemRevision（物料版本） and the connectors information. i.e. connector 类型, connector 名称, connector ID and transformation. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.8.5 setPhysicalAttachementsInScope

**接口路径：** `Manufacturing-2017-11-DataManagement/setPhysicalAttachementsInScope`

**API 版本：** `2017-11`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 设置作用域内的物理附件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_11.DataManagement.setPhysicalAttachementsInScope`

**请求（input）：**

```json
{
  "input": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "source": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": "",
      "relationInfo": {
        "stringProps": {},
        "stringArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {},
        "boolArrayProps": {}
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::SetPhysicalAttachmentsInput[] | 输入 包含以下内容的结构体 information about the scope (Mfg0BvrWorkarea), the source (BOM 行) and target (BOM 行) 对象 and Mfg0MEPhysicalAttachment or Mfg0MEMountToolToRobot relation 属性. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2018-06

##### 2.3.9.1 getOccurrenceKinematicsInformation

**接口路径：** `Manufacturing-2018-06-DataManagement/getOccurrenceKinematicsInformation`

**API 版本：** `2018-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 获取出现实例的运动学信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2018_06.DataManagement.getOccurrenceKinematicsInformation`

**请求（input）：**

```json
{
  "occKinematicsInfoinput": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `occKinematicsInfoinput` | Teamcenter::Soa::Manufacturing::_2018_06::DataManagement::GetOccKinematicsInfoInput[] | 输入 包含以下内容的结构体 context and scope for 其 the occurrence kinematics information of resource occurrence is 必需 |

**响应（output）：**

```json
{
  "occurrenceKinematicInfo": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "resourceLineInformation": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `occurrenceKinematicInfo` | Teamcenter::Soa::Manufacturing::_2018_06::DataManagement::OccurrenceKinematicsInfo[] | A 列表 containing information about BOM 行 representing occurrence of Mfg0MEResourceRevision or ItemRevision（物料版本） and ImanFile having occurrence kinematics information |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Teamcenter Services 结构 用于 return status 的 操作. |

---

##### 2.3.9.2 setOccurrenceKinematicsInformation

**接口路径：** `Manufacturing-2018-06-DataManagement/setOccurrenceKinematicsInformation`

**API 版本：** `2018-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 设置出现实例的运动学信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2018_06.DataManagement.setOccurrenceKinematicsInformation`

**请求（input）：**

```json
{
  "occInfoInputMap": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `occInfoInputMap` | Teamcenter::Soa::Manufacturing::_2018_06::DataManagement::OccKinematicsInfoMap | A 映射 (BOM 行, Dataset) containing BOM 行 representing the occurrence of Mfg0MEResourceRevision or ItemRevision（物料版本） and the dataset Mfg0OccKinematicsInfo having occurrence kinematics information. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2019-06

##### 2.3.10.1 publishSelectionFromStudyToSource

**接口路径：** `Manufacturing-2019-06-DataManagement/publishSelectionFromStudyToSource`

**API 版本：** `2019-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 将研究中的选定内容发布到源结构。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2019_06.DataManagement.publishSelectionFromStudyToSource`

**请求（input）：**

```json
{
  "input": [
    {
      "selectedLines": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "mode": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2019_06::DataManagement::SelectedSyncPublishStudyInput[] | A 列表，元素为 selected 业务对象 from 仿真研究 结构. The valid types are Mfg0BvrSimStudy, Mfg0BvrProcessArea, Mfg0BvrProcessLine, Mfg0BvrProcessStation Mfg0BvrProcess, and Mfg0BvrOperation. It also 包含 synchronization mode (Time based/Ev… |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误 若有. |
| `logFileTicket` | std::string | The FMS 票据 到 日志文件. |

---

##### 2.3.10.2 syncSelectionInStudyWithSource

**接口路径：** `Manufacturing-2019-06-DataManagement/syncSelectionInStudyWithSource`

**API 版本：** `2019-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 将研究选定内容与源结构同步。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2019_06.DataManagement.syncSelectionInStudyWithSource`

**请求（input）：**

```json
{
  "input": [
    {
      "selectedLines": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "mode": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2019_06::DataManagement::SelectedSyncPublishStudyInput[] | A 列表，元素为 selected 业务对象 from 仿真研究. The valid types are Mfg0BvrSimStudy, Mfg0BvrProcessArea, Mfg0BvrProcessLine, Mfg0BvrProcessStation Mfg0BvrProcess, and Mfg0BvrOperation.It also 包含 study root node and the synchronization… |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误 若有. |
| `logFileTicket` | std::string | The FMS 票据 到 日志文件. |

---

### 2.4 在制品装配管理（IPAManagement）

**涵盖 API 版本：** `2008-12`、`2012-02`、`2013-05`、`2014-12`  
**操作数：** 13

#### 版本 2008-12

##### 2.4.1.1 deletefilteredIPA

**接口路径：** `Manufacturing-2008-12-IPAManagement/deletefilteredIPA`

**API 版本：** `2008-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 删除筛选条件下的在制品装配数据（早期版本接口）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_12.IPAManagement.deletefilteredIPA`

**请求（input）：**

```json
{
  "processes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processes` | Teamcenter::BusinessObject[] | 输入 向量，元素为 process l即 from 其 we want to delete the filteredIPA. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.4.1.2 generateSearchScope

**接口路径：** `Manufacturing-2008-12-IPAManagement/generateSearchScope`

**API 版本：** `2008-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 生成在制品装配搜索范围。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_12.IPAManagement.generateSearchScope`

**请求（input）：**

```json
{
  "processes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processes` | Teamcenter::BusinessObject[] | processes 向量，元素为 process l即 that we would like to get all the search scope from. |

**响应（output）：**

```json
{
  "bomlines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `bomlines` | Teamcenter::BusinessObject[] | A vectoer of all the BOM 行s that are the search scope. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

##### 2.4.1.3 getFilteredIPA

**接口路径：** `Manufacturing-2008-12-IPAManagement/getFilteredIPA`

**API 版本：** `2008-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 获取筛选后的在制品装配结果。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_12.IPAManagement.getFilteredIPA`

**请求（input）：**

```json
{
  "processes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processes` | Teamcenter::BusinessObject[] | 输入 向量，元素为 process l即 from 其 we want to find the filteredIPA. |

**响应（output）：**

```json
{
  "filteredIPAs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `filteredIPAs` | Teamcenter::BusinessObject[] | A vectoer of all the filteredIPAs found. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

##### 2.4.1.4 saveSearchResult

**接口路径：** `Manufacturing-2008-12-IPAManagement/saveSearchResult`

**API 版本：** `2008-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 保存在制品装配搜索结果。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_12.IPAManagement.saveSearchResult`

**请求（input）：**

```json
{
  "input": [
    {
      "process": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "searchResultList": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "name": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2008_12::IPAManagement::IPAManagementSaveSearchResultInput[] | 输入 向量，元素为 IPAManagementSaveSearchResultInput Structures see discription in 结构 definition 文件. |

**响应（output）：**

```json
{
  "filteredIPA": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "filteredIPARoot": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "rejectedList": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `filteredIPA` | Teamcenter::BusinessObject | This is the new filteredIPA 结构. |
| `filteredIPARoot` | Teamcenter::BusinessObject | The flat 列表，元素为 all filteredIPA structures. |
| `rejectedList` | Teamcenter::BusinessObject[] | A 列表，元素为 all the BOM 行s that were not found 在 IPA 结构. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

#### 版本 2012-02

##### 2.4.2.1 deleteFilteredIPA

**接口路径：** `Manufacturing-2012-02-IPAManagement/deleteFilteredIPA`

**API 版本：** `2012-02`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 删除筛选条件下的在制品装配数据。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.IPAManagement.deleteFilteredIPA`

**请求（input）：**

```json
{
  "input": [
    {
      "process": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isRecursive": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::IPAManagement::DeleteFilteredIPAInputInfo[] | 包含 information about deleting filtered IPAs. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.4.2.2 getFilteredIPAType

**接口路径：** `Manufacturing-2012-02-IPAManagement/getFilteredIPAType`

**API 版本：** `2012-02`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 获取筛选在制品装配的类型信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.IPAManagement.getFilteredIPAType`

**请求（input）：**

```json
{
  "processes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processes` | Teamcenter::BusinessObject[] | a 向量，元素为 processes. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "flat": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "nested": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "unset": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serive data |
| `flat` | Teamcenter::BusinessObject[] | a 向量，元素为 processes that their 工艺结构 already contain a flat FIPA. |
| `nested` | Teamcenter::BusinessObject[] | a 向量，元素为 processes that their 工艺结构 already 包含 a nested FIPA |
| `unset` | Teamcenter::BusinessObject[] | processes that their 工艺结构 doesn't contain any FIPA yet. |

---

#### 版本 2013-05

##### 2.4.3.1 cleanIPATree

**接口路径：** `Manufacturing-2013-05-IPAManagement/cleanIPATree`

**API 版本：** `2013-05`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 从工艺结构中清理在制品装配（IPA）出现并删除相关对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.IPAManagement.cleanIPATree`

**请求（input）：**

```json
{
  "processWindow": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "forceCleanAll": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processWindow` | Teamcenter::BusinessObject | Window 的 工艺结构 包含 IPA that is to be deleted. |
| `forceCleanAll` | bool | This 标志 is 用于 forcefully delete all IPAs. This functionality is not supported currently. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "appPathRootWindows": [
    {
      "productWindowAppPathRoot": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "appPathRootType": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "logFileTicket": {
    "fileName": "",
    "fileTicket": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |
| `appPathRootWindows` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::AppPathRootWindowDetails[] | 列表，元素为 appearance windows deleted by the 操作. These windows corressponds to 产品结构s consumed 在 process strcuture to be cleaned. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::FileTicketDetails | The details 的 log 文件票据. |

---

##### 2.4.3.2 doesIPAExist

**接口路径：** `Manufacturing-2013-05-IPAManagement/doesIPAExist`

**API 版本：** `2013-05`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 检查指定工艺结构是否已存在在制品装配树。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.IPAManagement.doesIPAExist`

**请求（input）：**

```json
{
  "processWindow": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processWindow` | Teamcenter::BusinessObject | Window 的 工艺结构. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "isIPAExist": "",
  "configFileTicket": {
    "fileName": "",
    "fileTicket": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |
| `isIPAExist` | bool | The 标志，指示 是否 IPA tree exists 对于 工艺结构. |
| `configFileTicket` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::FileTicketDetails | The 票据 of configuration 文件. This 文件 is saved as an attachment 在 top-level process element on 其 the assembly tree was generated/updated. This 文件 包含 information about all the configured 产品结构s consumed 在 工艺结构. |

---

##### 2.4.3.3 generateIPATree

**接口路径：** `Manufacturing-2013-05-IPAManagement/generateIPATree`

**API 版本：** `2013-05`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 基于消耗件与工位信息生成在制品装配（IPA）树。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.IPAManagement.generateIPATree`

**请求（input）：**

```json
{
  "ipaInput": {
    "configDetails": {
      "processWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "ipaName": "",
      "occGrpType": "",
      "processTypes": [
        ""
      ],
      "consumptionOccTypes": [
        ""
      ],
      "effectivityDetails": {
        "effectivityEndItem": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "effectivityEndItemRev": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "effectivityUnitRange": "",
        "effectivityDateRange": ""
      }
    },
    "emailDetails": {
      "logFileName": "",
      "isLogFileNeeded": "",
      "mailToReceivers": [
        ""
      ],
      "mailCcReceivers": [
        ""
      ],
      "mailSubject": "",
      "mailMessage": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `ipaInput` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::IPATreeInput | All the details for IPA generation that includes the 名称 的 IPA, process types, consumption types, occurrence group 类型, effectivity, email notification details etc. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "productWindowAppPathRoot": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "appPathRootType": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "logFileTicket": {
    "fileName": "",
    "fileTicket": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |
| `productWindowAppPathRoot` | Teamcenter::BusinessObject | The appearance window 其 was created. |
| `appPathRootType` | Teamcenter::BusinessObject | The 类型 of appearance window 其 was created. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::FileTicketDetails | The details 的 log 文件票据. |

---

##### 2.4.3.4 localUpdateIPATree

**接口路径：** `Manufacturing-2013-05-IPAManagement/localUpdateIPATree`

**API 版本：** `2013-05`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 对在制品装配树执行本地更新（仅更新工作站相关 IPA）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.IPAManagement.localUpdateIPATree`

**请求（input）：**

```json
{
  "processLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processLines` | Teamcenter::BusinessObject[] | 列表，元素为 processes 在 工艺结构 on 其 local update requested. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileticket": {
    "fileName": "",
    "fileTicket": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |
| `logFileticket` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::FileTicketDetails | The details about the log 文件票据. |

---

##### 2.4.3.5 updateIPATree

**接口路径：** `Manufacturing-2013-05-IPAManagement/updateIPATree`

**API 版本：** `2013-05`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 当工艺结构变更时更新已存在的在制品装配树。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.IPAManagement.updateIPATree`

**请求（input）：**

```json
{
  "ipaInput": {
    "configDetails": {
      "processWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "ipaName": "",
      "occGrpType": "",
      "processTypes": [
        ""
      ],
      "consumptionOccTypes": [
        ""
      ],
      "effectivityDetails": {
        "effectivityEndItem": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "effectivityEndItemRev": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "effectivityUnitRange": "",
        "effectivityDateRange": ""
      }
    },
    "emailDetails": {
      "logFileName": "",
      "isLogFileNeeded": "",
      "mailToReceivers": [
        ""
      ],
      "mailCcReceivers": [
        ""
      ],
      "mailSubject": "",
      "mailMessage": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `ipaInput` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::IPATreeInput | All the details for updating IPA that includes the 名称 的 IPA, process types, consumption types, occurrence group 类型, effectivity, email notification details etc. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "productWindowAppPathRoot": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "appPathRootType": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "logFileTicket": {
    "fileName": "",
    "fileTicket": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |
| `productWindowAppPathRoot` | Teamcenter::BusinessObject | The appearance window 其 was created. |
| `appPathRootType` | Teamcenter::BusinessObject | The 类型 of appearance window 其 was created. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::FileTicketDetails | The details 的 log 文件票据. |

---

#### 版本 2014-12

##### 2.4.4.1 findAndRepopulateDynamicIPAs

**接口路径：** `Manufacturing-2014-12-IPAManagement/findAndRepopulateDynamicIPAs`

**API 版本：** `2014-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 查找并重新填充动态在制品装配。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.IPAManagement.findAndRepopulateDynamicIPAs`

**请求（input）：**

```json
{
  "inputBOPLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputBOPLines` | Teamcenter::BusinessObject[] | 本操作 recieves a 列表，元素为 ImanItemBOPLine as an 输入. (The 类型 of 的 bop line 对象 can be either Mfg0BvrProcess or Mfg0BvrShdStudy). |

**响应（output）：**

```json
{
  "dynamicIPAsData": [
    {
      "bopLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "dynamicIPAsData": [
        {
          "dynamicIPA": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "consumedParts": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `dynamicIPAsData` | Teamcenter::Soa::Manufacturing::_2014_12::IPAManagement::DynamicIPAsOfLine[] | A 列表，元素为 DynamicIPAsOfLine. Each element 在 列表 包含 data about all the dynamic IPAs of a single line. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. The following 部分错误 被返回 in case invalid parameters are passed 到 操作:- 25439 :- The 类型 的 given 对象 is not supported. 25440 :- The given 对象 doesn&apos;t have any dynamic IPA. |

---

##### 2.4.4.2 repopulateDynamicIPAs

**接口路径：** `Manufacturing-2014-12-IPAManagement/repopulateDynamicIPAs`

**API 版本：** `2014-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 重新填充动态在制品装配数据。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.IPAManagement.repopulateDynamicIPAs`

**请求（input）：**

```json
{
  "input": {
    "topLine": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "ids": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_12::IPAManagement::RepopulateDynamicIPAsData | The top BOPLine and a 列表，元素为 absolute occurrence IDs of processes (Mfg0BvrProcess) or shared studies (Mfg0BvrShdStudy). |

**响应（output）：**

```json
{
  "dynamicIPAsData": [
    {
      "bopLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "dynamicIPAsInfo": [
        {
          "dynamicIPA": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "consumedParts": [
            {
              "consumedPart": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "referencedPart": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "occInformation": {}
            }
          ],
          "occInformation": {}
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `dynamicIPAsData` | Teamcenter::Soa::Manufacturing::_2014_12::IPAManagement::DynamicIPAsProcLineInfo[] | 列表，元素为 data containing information about 工艺行s (Mfg0BvrProcess) and their respective Dynamic IPA nodes (Mfg0BvrDynamicIPA). |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard 服务数据. |

---

### 2.5 导入导出（ImportExport）

**涵盖 API 版本：** `2010-09`、`2013-05`、`2015-10`、`2016-03`、`2017-05`  
**操作数：** 6

#### 版本 2010-09

##### 2.5.1.1 importManufaturingFeatures

**接口路径：** `Manufacturing-2010-09-ImportExport/importManufaturingFeatures`

**API 版本：** `2010-09`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 从 PLMXML 导入制造特征（早期版本，注意拼写 Manufaturing）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.ImportExport.importManufaturingFeatures`

**请求（input）：**

```json
{
  "input": {
    "fileName": "",
    "root": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2010_09::ImportExport::ImportInput | 输入 包含 PLMXML 文件 and the root 的 结构 to 其 the data should be imported. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileFullPath": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 |
| `logFileFullPath` | std::string | The full path 的 日志文件 (created by the import). |

---

#### 版本 2013-05

##### 2.5.2.1 importManufacturingFeatures

**接口路径：** `Manufacturing-2013-05-ImportExport/importManufacturingFeatures`

**API 版本：** `2013-05`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 从 PLMXML 文件向目标产品结构导入制造特征（MFG）。（存在 2013-05、2015-10、2016-03 三个 API 版本）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.ImportExport.importManufacturingFeatures`

**请求（input）：**

```json
{
  "input": {
    "context": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "content": [
      {
        "fileName": "",
        "container": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "importMode": ""
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::ImportExport::AdvancedImportInput | 输入 for PLMXML import of 制造特征. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileName": "",
  "logFileTicket": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据.The 错误 conditions and the corresponding 错误 codes are as listed below. 200373 Import is tried to be done from an incomplete PLMXML 文件. 200374 The preference MEImportMFGsManufacturingFeatureIdAttributeName 不 have … |
| `logFileName` | std::string | The 名称 的 generated 日志文件. |
| `logFileTicket` | std::string | The FMS 票据 对于 transient 文件 that captures the log of import. |

---

#### 版本 2015-10

##### 2.5.3.1 importManufacturingFeatures

**接口路径：** `Manufacturing-2015-10-ImportExport/importManufacturingFeatures`

**API 版本：** `2015-10`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 从 PLMXML 文件向目标产品结构导入制造特征（MFG）。（存在 2013-05、2015-10、2016-03 三个 API 版本）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2015_10.ImportExport.importManufacturingFeatures`

**请求（input）：**

```json
{
  "input": {
    "context": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "content": [
      {
        "xmlFileTicket": "",
        "container": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "importMode": "",
        "nameRefFileTickets": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2015_10::ImportExport::ImportManufaturingFeaturesInput | 输入 for import manufaturing features. |

**响应（output）：**

```json
{
  "logFileName": "",
  "logFileTicket": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `logFileName` | std::string | The 名称 的 generated 日志文件. |
| `logFileTicket` | std::string | The FMS 票据 的 日志文件. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |

---

#### 版本 2016-03

##### 2.5.4.1 exportToBriefcase

**接口路径：** `Manufacturing-2016-03-ImportExport/exportToBriefcase`

**API 版本：** `2016-03`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 将制造数据导出到 Briefcase。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2016_03.ImportExport.exportToBriefcase`

**请求（input）：**

```json
{
  "reason": "",
  "sites": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "transferOptionSet": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "optionNameAndValues": {},
  "sessionOptionNamesAndValues": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `reason` | std::string | The reason 对于 export, the size is limited to 240 characters. This can be blank. |
| `sites` | Teamcenter::BusinessObject[] | The destination s即 only one site is supported as of now. The site should be marked as offline 在 Organization application in Teamcenter to perform a briefcase export. |
| `objects` | Teamcenter::BusinessObject[] | 列表，元素为 对象 to be exported 例如 CC, BOM 行. |
| `transferOptionSet` | Teamcenter::BusinessObject | A reference 到 TransferOptionSet 对象, this 对象 holds the 列表，元素为 options and their 默认 值 其 can influence the contents 的 exported briefcase. Please refer the documentation 的 PLM XML Export Import administration tool for more d… |
| `optionNameAndValues` | Teamcenter::Soa::Manufacturing::_2016_03::ImportExport::NamesAndValuesMap | A 映射 (string, string) 的 options names and 值. This 列表 overrides the 值 的 transferOptionSet. 例如， there is an option in TransferOptionSet, 其 is 用于 control 是否 to export configured assembly. The 默认 值 在 TransferOptionSet is fal… |
| `sessionOptionNamesAndValues` | Teamcenter::Soa::Manufacturing::_2016_03::ImportExport::NamesAndValuesMap | A 映射 (string, string) of all the session option names (options 其 are not part 的 transferOptionSet) and 值. Please refer the documentation 的 PLM XML Export Import administration tool for more details. Few 的 options are lis… |

**响应（output）：**

```json
{
  "briefcaseFileFMSTicket": "",
  "fileTickets": [
    ""
  ],
  "messageIds": [
    ""
  ],
  "briefcaseDataSet": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `briefcaseFileFMSTicket` | std::string | FMS 票据 的 briefcase 文件, 其 can be 用于 download the briefcase 文件 from 服务器 to 客户端. |
| `fileTickets` | std::string[] | To represent a 文件票据 and its original 文件 名称. |
| `messageIds` | std::string[] | 列表，元素为 message IDs. |
| `briefcaseDataSet` | Teamcenter::BusinessObject | A 业务对象 of Dataset 其 includes the out briefcase 文件 in its namedReference. After export, a new Dataset 将 created. The exported briefcase 文件 将 added 到 new Dataset. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 包含 列表，元素为 created or modified 对象 and also the 部分错误 in case of failure conditions. |

---

##### 2.5.4.2 importManufacturingFeatures

**接口路径：** `Manufacturing-2016-03-ImportExport/importManufacturingFeatures`

**API 版本：** `2016-03`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 从 PLMXML 文件向目标产品结构导入制造特征（MFG）。（存在 2013-05、2015-10、2016-03 三个 API 版本）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2016_03.ImportExport.importManufacturingFeatures`

**请求（input）：**

```json
{
  "input": {
    "context": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "content": [
      {
        "xmlFileTicket": "",
        "scope": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "container": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "importMode": "",
        "nameRefFileTickets": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2016_03::ImportExport::ImportManufaturingFeaturesInput | 输入 for import manufaturing features. |

**响应（output）：**

```json
{
  "logFileName": "",
  "logFileTicket": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `logFileName` | std::string | The 名称 的 generated 日志文件. |
| `logFileTicket` | std::string | The FMS 票据 的 日志文件. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |

---

#### 版本 2017-05

##### 2.5.5.1 importFromBriefcase

**接口路径：** `Manufacturing-2017-05-ImportExport/importFromBriefcase`

**API 版本：** `2017-05`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 从 Briefcase 导入制造数据。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_05.ImportExport.importFromBriefcase`

**请求（input）：**

```json
{
  "fmsTicket": "",
  "optionSetTag": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "optionNamesAndValues": {},
  "sessionOptionAndValues": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `fmsTicket` | std::string | The FMS 文件 票据 对于 briefcase 文件, the 文件 should be uploaded 到 服务器 before calling 本操作. |
| `optionSetTag` | Teamcenter::BusinessObject | A reference 到 TransferOptionSet 对象, this 对象 holds the 列表，元素为 options and their 默认 值 其 can influence importing briefcase. |
| `optionNamesAndValues` | Teamcenter::Soa::Manufacturing::_2017_05::ImportExport::NamesAndValues | A 列表，元素为 all the option set containing option names and 值. This 列表 overrides the 值 从 optionSetTag. For example: For option opt_imp_XXX in TransferOptionSet, the 默认值为 false. It can be overridden by adding the option with … |
| `sessionOptionAndValues` | Teamcenter::Soa::Manufacturing::_2017_05::ImportExport::NamesAndValues | A 列表，元素为 all the session option names (options 其 are not part 的 option set) and 值. For example: A session option modified_objects_only 指定 是否 to import modified 对象. |

**响应（output）：**

```json
{
  "logFileFMSTicket": "",
  "errorFileFMSTicket": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `logFileFMSTicket` | std::string | FMS 票据 的 import 日志文件, 其 can be 用于 download the import 日志文件 from 服务器 to 客户端. |
| `errorFileFMSTicket` | std::string | FMS 票据 的 import 错误 文件, 其 can be 用于 download the import 错误 文件 from 服务器 to 客户端. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 包含 列表，元素为 created or modified 对象 and also the 部分错误 in case of failure conditions. |

---

### 2.6 制造属性收集（MFGPropertyCollector）

**涵盖 API 版本：** `2009-10`  
**操作数：** 1

#### 版本 2009-10

##### 2.6.1.1 collectProperties

**接口路径：** `Manufacturing-2009-10-MFGPropertyCollector/collectProperties`

**API 版本：** `2009-10`  
**Service：** `MFGPropertyCollector`  
**Library：** `Manufacturing`

**说明：** 收集制造对象的属性信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.MFGPropertyCollector.collectProperties`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "rootNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "traversalRuleList": [
        {
          "traversalRuleKeys": [
            {
              "types": [
                ""
              ],
              "context": ""
            }
          ],
          "targets": [
            ""
          ]
        }
      ],
      "propVisitorList": [
        {
          "traversalVisitorsKeys": [
            {
              "types": [
                ""
              ],
              "context": ""
            }
          ],
          "propToCollectList": [
            ""
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2009_10::MFGPropertyCollector::CollectPropertiesInputInfo[] | MfgNode, traversal rules and 属性 names to collect |

**响应（output）：**

```json
{
  "outputList": [
    {
      "clientId": "",
      "output": [
        {
          "contextType": "",
          "nodeValueList": [
            {
              "node": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "props": {}
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `outputList` | Teamcenter::Soa::Manufacturing::_2009_10::MFGPropertyCollector::CollectPropertiesOutput[] | The collection of MfgNode, 属性 names and theit 值. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 containing partial 错误 data |

---

### 2.7 模型（Model）

**涵盖 API 版本：** `2009-10`、`2012-02`、`2013-12`、`2014-12`  
**操作数：** 12

#### 版本 2009-10

##### 2.7.1.1 calculateCriticalPath

**接口路径：** `Manufacturing-2009-10-Model/calculateCriticalPath`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 计算模型中的关键路径。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.calculateCriticalPath`

**请求（input）：**

```json
{
  "roots": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `roots` | Teamcenter::BusinessObject[] | The 列表，元素为 MFG BVR or APS root 对象 the critical path is to be calculated for. |

**响应（output）：**

```json
{
  "results": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "components": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "duration": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2009_10::Model::CalculateCriticalPathResult[] | A 列表，元素为 CalculateCriticalPathResult structures 对于每个 path returned. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

##### 2.7.1.2 createFlow

**接口路径：** `Manufacturing-2009-10-Model/createFlow`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 创建工艺流（Flow）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.createFlow`

**请求（input）：**

```json
{
  "input": [
    {
      "successor": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "predecessor": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "delay": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2009_10::Model::FlowInput[] | a 向量，元素为 FlowInput structures. |

**响应（output）：**

```json
{
  "flowsResult": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `flowsResult` | Teamcenter::BusinessObject[] | A 向量，元素为 the new succesfully created flow 对象. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

##### 2.7.1.3 editLogicalAssignments

**接口路径：** `Manufacturing-2009-10-Model/editLogicalAssignments`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 编辑逻辑分配（Logical Assignment）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.editLogicalAssignments`

**请求（input）：**

```json
{
  "laEditVec": [
    {
      "laObj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "laAttributes": [
        {
          "name": "",
          "value": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `laEditVec` | Teamcenter::Soa::Manufacturing::_2009_10::Model::LogicalAssignmentData[] | 向量，元素为 对象 to edit. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.7.1.4 getResolvedNodesFromLA

**接口路径：** `Manufacturing-2009-10-Model/getResolvedNodesFromLA`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 从逻辑分配获取已解析节点。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.getResolvedNodesFromLA`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "laObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputObjects` | Teamcenter::Soa::Manufacturing::_2009_10::Model::ResolvedNodesInput[] | 输入 对象 for 其 to return resolved nodes. |

**响应（output）：**

```json
{
  "outResolvedNodes": [
    {
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "laResolvedNodes": [
        {
          "laObj": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "resolvedNodes": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `outResolvedNodes` | Teamcenter::Soa::Manufacturing::_2009_10::Model::ResolvedNodesOutput[] | All the resolved nodes of all 对象 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 对象 |

---

##### 2.7.1.5 removeFlow

**接口路径：** `Manufacturing-2009-10-Model/removeFlow`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 移除工艺流。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.removeFlow`

**请求（input）：**

```json
{
  "input": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::BusinessObject[] | a 向量，元素为 Flows to remove. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.7.1.6 resolveLogicalAssignments

**接口路径：** `Manufacturing-2009-10-Model/resolveLogicalAssignments`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 解析逻辑分配关系。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.resolveLogicalAssignments`

**请求（input）：**

```json
{
  "laVec": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "resolveObjects": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "laResolveType": "",
      "recursive": ""
    }
  ],
  "externalSources": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `laVec` | Teamcenter::BusinessObject[] | 向量，元素为 Logical Assignment 对象 to resolve |
| `resolveObjects` | Teamcenter::Soa::Manufacturing::_2009_10::Model::ResolveData[] | 向量，元素为 对象 to resolve 对于每个 对象 the 服务 will resolve all its Logical Assignments |
| `externalSources` | Teamcenter::BusinessObject[] | 向量，元素为 loaded 产品结构s on 其 to run the resolve mechanism |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2012-02

##### 2.7.2.1 getCandidateToolsForToolRequirement

**接口路径：** `Manufacturing-2012-02-Model/getCandidateToolsForToolRequirement`

**API 版本：** `2012-02`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 获取满足刀具需求的候选刀具列表。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Model.getCandidateToolsForToolRequirement`

**请求（input）：**

```json
{
  "resolveObjects": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "trObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toolSource": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `resolveObjects` | Teamcenter::Soa::Manufacturing::_2012_02::Model::ToolRequirementInput[] | 输入 结构 specifying 操作. Tool Requirement for 其 candidate tools are to be fetched. And tool source from 其中 tools are to be fetched. |

**响应（output）：**

```json
{
  "candidateTools": [
    {
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tools": [
        {
          "trObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "toolObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `candidateTools` | Teamcenter::Soa::Manufacturing::_2012_02::Model::CandidateTool[] | 结构 with member as 操作 or Process and the candidate tools. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 将包含 warnings and 错误. 若有. |

---

##### 2.7.2.2 getToolRequirements

**接口路径：** `Manufacturing-2012-02-Model/getToolRequirements`

**API 版本：** `2012-02`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 获取刀具需求信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Model.getToolRequirements`

**请求（input）：**

```json
{
  "parentObject": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "toolRequirementStatus": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `parentObject` | Teamcenter::BusinessObject[] | 指定 the 操作 of 类型 Mfg0BvrOperation or Process of 类型 Mfg0BvrProcess. |
| `toolRequirementStatus` | std::string[] | 指定 the status 的 Tool requirement. The possible 值 are ALL & RESOLVED and UNRESOLVED. RESOLVED 指示 that the Tool Requirement is resolved against the Tool. This option is relevant only 对于 工厂 BOP 其中 it is allowed to resolve t… |

**响应（output）：**

```json
{
  "toolRequirements": [
    {
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toolRequirements": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `toolRequirements` | Teamcenter::Soa::Manufacturing::_2012_02::Model::ToolRequirementResult[] | 指定 the Tool Requirements. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 将包含 warnings and 错误. 若有. |

---

##### 2.7.2.3 resolveToolRequirement

**接口路径：** `Manufacturing-2012-02-Model/resolveToolRequirement`

**API 版本：** `2012-02`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 解析并匹配刀具需求。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Model.resolveToolRequirement`

**请求（input）：**

```json
{
  "resolveObjects": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "trObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toolObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toolSource": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `resolveObjects` | Teamcenter::Soa::Manufacturing::_2012_02::Model::ResolveDataInfo[] | 指定 the data 必需 for resolving the Tool requirement. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.7.2.4 updateFlows

**接口路径：** `Manufacturing-2012-02-Model/updateFlows`

**API 版本：** `2012-02`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 更新工艺流定义。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Model.updateFlows`

**请求（input）：**

```json
{
  "input": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "isSubHierarchies": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::BusinessObject[] | Should be a 向量，元素为 BOM 行. This is a scope of update flow command. |
| `isSubHierarchies` | bool | If isSubHierarchies parameter is true, flows are recursively updated 对于所有 children. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2013-12

##### 2.7.3.1 computeAppearancePath

**接口路径：** `Manufacturing-2013-12-Model/computeAppearancePath`

**API 版本：** `2013-12`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 计算外观路径（Appearance Path）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.Model.computeAppearancePath`

**请求（input）：**

```json
{
  "input": {
    "parentObject": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "childPaths": [
      {
        "threadIDs": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_12::Model::AppearancePathInput | A 列表，元素为 AppearancePathInput that holds parent 对象 and a 列表，元素为 paths 对于每个 one. Each path 表示 a node for 其 we would like to get the 值 的 prorperties. |

**响应（output）：**

```json
{
  "results": [
    {
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childResults": [
        {
          "absOccUID": "",
          "apnUID": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2013_12::Model::ComputeAppearancePathResult[] | Data 结构 that holds the results |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 包含ll the modified BO and the 错误 |

---

#### 版本 2014-12

##### 2.7.4.1 validateScopeFlowsConsistency

**接口路径：** `Manufacturing-2014-12-Model/validateScopeFlowsConsistency`

**API 版本：** `2014-12`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 校验作用域内工艺流的一致性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.Model.validateScopeFlowsConsistency`

**请求（input）：**

```json
{
  "rootLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `rootLines` | Teamcenter::BusinessObject[] | 列表，元素为 业务对象 representing BOP line 对象 (the 类型 的 bop line 对象 can be either Mfg0BvrProcess or Mfg0BvrOperation) |

**响应（output）：**

```json
{
  "data": [
    {
      "isConsistent": "",
      "cycles": [
        {
          "objects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "flows": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "fileTicket": {
    "ticket": "",
    "fileName": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `data` | Teamcenter::Soa::Manufacturing::_2014_12::Model::ConsistencyData[] | A 列表，元素为 ConsistencyData. Each element 在 列表 包含 indication 是否 the data is consistent and information about the in-cosistencies (cycles), if found. |
| `fileTicket` | Teamcenter::Soa::Manufacturing::_2014_12::Model::FileTicket | An FMS 文件 票据. The 文件 包含 report about the cycles found by the algorithm. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据. |

---

### 2.8 模型定义（ModelDefinitions）

**涵盖 API 版本：** `2009-10`  
**操作数：** 2

#### 版本 2009-10

##### 2.8.1.1 getManufacturingPropretyDescs

**接口路径：** `Manufacturing-2009-10-ModelDefinitions/getManufacturingPropretyDescs`

**API 版本：** `2009-10`  
**Service：** `ModelDefinitions`  
**Library：** `Manufacturing`

**说明：** 获取制造属性描述定义。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.ModelDefinitions.getManufacturingPropretyDescs`

**请求（input）：**

```json
{
  "inputs": [
    {
      "typeName": "",
      "propNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Manufacturing::_2009_10::ModelDefinitions::PropDescInfo[] | - 向量，元素为 结构 of PropDescInfo with 类型 名称 and 属性 names 向量. |

**响应（output）：**

```json
{
  "inputTypeNameToPropDescOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputTypeNameToPropDescOutput` | Teamcenter::Soa::Manufacturing::_2009_10::ModelDefinitions::InputTypeNameToPropDescOutputMap | 映射，键值对为 输入 类型 名称 to PropertyDescriptor |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） 其 has 输出 tags as plain 对象 and 错误 in partialError |

---

##### 2.8.1.2 getValidRelationTypes

**接口路径：** `Manufacturing-2009-10-ModelDefinitions/getValidRelationTypes`

**API 版本：** `2009-10`  
**Service：** `ModelDefinitions`  
**Library：** `Manufacturing`

**说明：** 获取有效的关系类型列表。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.ModelDefinitions.getValidRelationTypes`

**请求（input）：**

```json
{
  "relationTypesInput": [
    {
      "sourceType": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "targetType": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `relationTypesInput` | Teamcenter::Soa::Manufacturing::_2009_10::ModelDefinitions::RelationTypesInput[] | 向量，元素为 source and target types pairs. |

**响应（output）：**

```json
{
  "relationTypesResults": [
    {
      "sourceType": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "targetType": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "validRelationTypes": [
        {
          "name": "",
          "displayName": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `relationTypesResults` | Teamcenter::Soa::Manufacturing::_2009_10::ModelDefinitions::RelationTypesOutput[] | Array of relation types results |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Exceptions from internal processing returned as PartialErrors |

---

### 2.9 资源管理（ResourceManagement）

**涵盖 API 版本：** `2013-12`、`2014-06`  
**操作数：** 7

#### 版本 2013-12

##### 2.9.1.1 getStepP21FileCounts

**接口路径：** `Manufacturing-2013-12-ResourceManagement/getStepP21FileCounts`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 获取 STEP P21 文件数量统计。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.getStepP21FileCounts`

**请求（input）：**

```json
{
  "classIDs": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classIDs` | std::string[] | The class IDs of specific vendor catalog classes. All products from this class and all child classes of this class 将 counted. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "countMap": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 |
| `countMap` | Teamcenter::Soa::Manufacturing::_2013_12::ResourceManagement::MapStringInt | A 映射，键值对为 class IDs for 其 the counts are requested and its corresponding counts. |

---

##### 2.9.1.2 getVendorCatalogInfo

**接口路径：** `Manufacturing-2013-12-ResourceManagement/getVendorCatalogInfo`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 获取供应商目录信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.getVendorCatalogInfo`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "catalogInfo": [
    {
      "vendorName": "",
      "vendorAcronym": "",
      "vendorCatalogVersion": "",
      "vendorCatalogLanguage": "",
      "vendorCatalogDescription": "",
      "vendorCatalogShortDescription": "",
      "vendorCatalogID": "",
      "vendorCatalogRootClassID": "",
      "vendorCatalogRootDir": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 |
| `catalogInfo` | Teamcenter::Soa::Manufacturing::_2013_12::ResourceManagement::CatalogInfo[] | The vendor catalog information |

---

##### 2.9.1.3 importStep3DModels

**接口路径：** `Manufacturing-2013-12-ResourceManagement/importStep3DModels`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 导入 STEP 三维模型。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.importStep3DModels`

**请求（input）：**

```json
{
  "icoIDs": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icoIDs` | std::string[] | The Classification 对象 (ICO) IDs identifying the tool component under 其 the graphics 将 imported. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.9.1.4 importStepP21Files

**接口路径：** `Manufacturing-2013-12-ResourceManagement/importStepP21Files`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 导入 STEP P21 文件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.importStepP21Files`

**请求（input）：**

```json
{
  "classID": "",
  "importOptions": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classID` | std::string | The class ID of a specific vendor catalog class. All catalog products from this class and all child classes of this class 将 imported. |
| `importOptions` | int | The import options allow to specify if (0) exisitng product data should be ignored and not be touched, (1) existing data should be overwritten (2) existing data should be overwritten only if the import 文件 is newer than t… |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": {
    "ticket": "",
    "fileName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2013_12::ResourceManagement::RMFileTicket | 票据 的 import 日志文件 |

---

##### 2.9.1.5 importVendorCatalogHierarchy

**接口路径：** `Manufacturing-2013-12-ResourceManagement/importVendorCatalogHierarchy`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 导入供应商目录层级结构。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.importVendorCatalogHierarchy`

**请求（input）：**

```json
{
  "vendorCatalogRootDir": "",
  "importOptions": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `vendorCatalogRootDir` | std::string | The root directory that 包含 GTC vendor catalog |
| `importOptions` | int | The import options allow you to control 是否 the catalog hierarchy will overwrite (1) existing classes or ignore (0) those classes and not import them. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": {
    "ticket": "",
    "fileName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 that can contain 错误 codes |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2013_12::ResourceManagement::RMFileTicket | 票据 的 import 日志文件 |

---

##### 2.9.1.6 updateNXToolAssemblies

**接口路径：** `Manufacturing-2013-12-ResourceManagement/updateNXToolAssemblies`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 更新 NX 刀具装配数据。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.updateNXToolAssemblies`

**请求（input）：**

```json
{
  "icoIDs": [
    ""
  ],
  "identifyCutAndNoCut": "",
  "generateSpinning": "",
  "setToolJunctions": "",
  "writePartAttributes": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icoIDs` | std::string[] | The Classification 对象 (ICO) IDs identifying the tool assemblies |
| `identifyCutAndNoCut` | bool | If true, the "Cut" and "NoCut" information 从 different tool components is taken and stored 在 assembly itself. |
| `generateSpinning` | bool | If true, the "Cut" and "NoCut" information 从 tool assembly is taken and the "Cut" and "NoCut" rotation spun. |
| `setToolJunctions` | bool | If true, the poition and orientation 的 tool tip and tool mount junctions are evaluated and set 在 assembly. |
| `writePartAttributes` | bool | If true, the X, Y and Z offset 值 的 tool are evaluated 基于 the tool tip and tool mount junctions. Those 值 are written 到 part 属性 在 part 文件 and can be mapped to Teamcenter. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2014-06

##### 2.9.2.1 checkToolParameters

**接口路径：** `Manufacturing-2014-06-ResourceManagement/checkToolParameters`

**API 版本：** `2014-06`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 检查刀具是否具备生成三维图形或使用所需的属性值。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.ResourceManagement.checkToolParameters`

**请求（input）：**

```json
{
  "icoIds": [
    ""
  ],
  "checkLevel": "",
  "checkTypes": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icoIds` | std::string[] | A 列表，元素为 classification 对象 IDs that identify the 列表，元素为 tools to be checked. |
| `checkLevel` | std::string | The level of checks to be performed: "none", "preferred", "错误", "all". If the provided 值 is "preferred", the 值 的 single-值 preference MRMToolCheckLevel 将 used. |
| `checkTypes` | std::string[] | A 列表，元素为 the types of checks to be performed: "preferred", "NX CAM", "MRL PFT". If the only provided 值 is "preferred", the 值 的 multi-值 preference MRMToolCheckType 将 be used. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "checkResults": [
    {
      "icoId": "",
      "status": "",
      "report": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 that can contain 错误 descriptions. |
| `checkResults` | Teamcenter::Soa::Manufacturing::_2014_06::ResourceManagement::CheckResult[] | A 列表 containing a check result 对于每个 tool. |

---

### 2.10 结构管理（StructureManagement）

**涵盖 API 版本：** `2009-06`、`2009-10`、`2011-06`、`2013-05`、`2015-03`、`2015-10`、`2018-11`  
**操作数：** 18

#### 版本 2009-06

##### 2.10.1.1 closeAttachmentWindow

**接口路径：** `Manufacturing-2009-06-StructureManagement/closeAttachmentWindow`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 关闭附件窗口。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.closeAttachmentWindow`

**请求（input）：**

```json
{
  "lines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::BOMLine[] | 输入 BOM 行s for 其 the attachmentwindow has to be closed. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.10.1.2 createOrUpdateAttachments

**接口路径：** `Manufacturing-2009-06-StructureManagement/createOrUpdateAttachments`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 创建或更新结构附件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.createOrUpdateAttachments`

**请求（input）：**

```json
{
  "attachments": [
    {
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objects": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `attachments` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::CreateOrUpdateAttachmentsData[] | 输入 either BOM 行 or attachmentline (parent) and the relations and 工作区对象 to be processed as attachments. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.10.1.3 deleteAttachments

**接口路径：** `Manufacturing-2009-06-StructureManagement/deleteAttachments`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 删除结构附件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.deleteAttachments`

**请求（input）：**

```json
{
  "lines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::CfgAttachmentLine[] | remove the specified lines 从 parent attachment window. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.10.1.4 getAttachmentLineChildren

**接口路径：** `Manufacturing-2009-06-StructureManagement/getAttachmentLineChildren`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取附件行的子行。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.getAttachmentLineChildren`

**请求（input）：**

```json
{
  "attlines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `attlines` | Teamcenter::CfgAttachmentLine[] | 输入 parent attachment lines |

**响应（output）：**

```json
{
  "lines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::AttachmentLineToChildLinesMap | 映射，键值对为 parent attachmentline to child lines. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | any 部分错误 to be returned. |

---

##### 2.10.1.5 getBOMLineActivities

**接口路径：** `Manufacturing-2009-06-StructureManagement/getBOMLineActivities`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取 BOM 行关联的活动。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.getBOMLineActivities`

**请求（input）：**

```json
{
  "bomLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `bomLines` | Teamcenter::BOMLine[] | 输入 向量，元素为 BOM 行s for 其 activities are needed. |

**响应（output）：**

```json
{
  "lines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::BOMLineToActivitiesMap | 向量，元素为 BOM 行 to activities 映射 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） 对象 to capture 部分错误. |

---

##### 2.10.1.6 getBOMLineAttachments

**接口路径：** `Manufacturing-2009-06-StructureManagement/getBOMLineAttachments`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取 BOM 行附件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.getBOMLineAttachments`

**请求（input）：**

```json
{
  "bomlines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "filter": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `bomlines` | Teamcenter::BOMLine[] | 列表，元素为 输入 BOM 行s |
| `filter` | std::string[] | 可选 relation filter to be used for attachments. The relation names specified here are used as a filter 在 attachmentwindow |

**响应（output）：**

```json
{
  "lines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::BOMLineToAttachmentLinesMap | BOM 行 to attachmentlines 映射 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） to capture 部分错误. |

---

##### 2.10.1.7 getStructureContextActivityLines

**接口路径：** `Manufacturing-2009-06-StructureManagement/getStructureContextActivityLines`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取结构上下文活动行。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.getStructureContextActivityLines`

**请求（input）：**

```json
{
  "scs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `scs` | Teamcenter::StructureContext[] | 列表，元素为 输入 structurecontext 对象 |

**响应（output）：**

```json
{
  "lines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::StructureContextActivityLinesMap | 映射，键值对为 sc to activity lines |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | for reporting 部分错误. |

---

##### 2.10.1.8 getStructureContextTopLines

**接口路径：** `Manufacturing-2009-06-StructureManagement/getStructureContextTopLines`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取结构上下文顶层行。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.getStructureContextTopLines`

**请求（input）：**

```json
{
  "scs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `scs` | Teamcenter::StructureContext[] | 输入 列表，元素为 SC's |

**响应（output）：**

```json
{
  "lines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::StructureContextToLinesMap | 映射，键值对为 SC to it's lines |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） to hold 部分错误 |

---

#### 版本 2009-10

##### 2.10.2.1 copyEBOPStructure

**接口路径：** `Manufacturing-2009-10-StructureManagement/copyEBOPStructure`

**API 版本：** `2009-10`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 复制 EBOP 结构。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureManagement.copyEBOPStructure`

**请求（input）：**

```json
{
  "newRoot": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "configuringEBOPWindow": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "workingWindow": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "copyRulesKey": "",
  "copyFutureEffectivity": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `newRoot` | Teamcenter::WorkspaceObject | The newly created rootobject under 其 the 结构 将 cloned. |
| `configuringEBOPWindow` | Teamcenter::BusinessObject | The window with source BOP(GBOP/PBOP) item as root. |
| `workingWindow` | Teamcenter::BusinessObject | 可选 window (the actual source window), from 其 the IncrementalChange Rev is picked up. In additi在 window settings like show unconfigured etc. are also picked up. |
| `copyRulesKey` | std::string | The 名称 的 preference 其 将 used for cloning rule to be used. |
| `copyFutureEffectivity` | bool | if true, future ICRevs 将 created appropriately, instead of all ICEs being cloned 到 currently active ICRev. Note that if this is true - it is expected that there is an currently selected ICRev 在 working window. |

**响应（output）：**

```json
{
  "createdICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "createdFutureICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData",
  "updatedObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `createdICRevs` | Teamcenter::WorkspaceObject[] | any newly created incremental change revisions |
| `createdFutureICRevs` | Teamcenter::WorkspaceObject[] | any newly created future Incremental Change Revisions. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | the updated item(root) and any 部分错误 returned here. |
| `updatedObject` | Teamcenter::WorkspaceObject | The updatedObject 其 is the ItemRevision（物料版本） 的 passed in item. |

---

##### 2.10.2.2 getStructureContextLines

**接口路径：** `Manufacturing-2009-10-StructureManagement/getStructureContextLines`

**API 版本：** `2009-10`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取结构上下文行数据。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureManagement.getStructureContextLines`

**请求（input）：**

```json
{
  "scList": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `scList` | Teamcenter::StructureContext[] | The 列表，元素为 StructureContexts for 其 toplines and selected lines are needed. |

**响应（output）：**

```json
{
  "topLines": {},
  "selectedLines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `topLines` | Teamcenter::Soa::Manufacturing::_2009_10::StructureManagement::StructureContextToLinesMap2 | 映射，键值对为 StructureContext to its toplines. 例如， 产品结构 and 工艺结构 top lines. |
| `selectedLines` | Teamcenter::Soa::Manufacturing::_2009_10::StructureManagement::StructureContextToLinesMap2 | 映射，键值对为 StructureContext to any selected child lines. Note: If the topline is selected this 映射 将 empty. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 结构 to capture any 部分错误. |

---

##### 2.10.2.3 pasteDuplicateStructure

**接口路径：** `Manufacturing-2009-10-StructureManagement/pasteDuplicateStructure`

**API 版本：** `2009-10`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 粘贴并复制制造结构（重复粘贴）。（存在 2009-10、2018-11 两个 API 版本）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureManagement.pasteDuplicateStructure`

**请求（input）：**

```json
{
  "srcLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "targetLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "copyRulesKey": "",
  "copyFutureEffectivity": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `srcLines` | Teamcenter::BusinessObject[] | 输入 src lines 其 need to be cloned under the targetline(s). All 的m 必须为 从 same 结构. |
| `targetLines` | Teamcenter::BusinessObject[] | the targetline(s) under 其 the clones 的 对象 underlying the srclines 将 created/pasted. These should be 从 same 结构. |
| `copyRulesKey` | std::string | 名称 的 preference that 将 used for cloning. |
| `copyFutureEffectivity` | bool | 标志 to indicate 是否 future effectivities are to be created. |

**响应（output）：**

```json
{
  "createdICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "createdFutureICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData",
  "newChildLines": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `createdICRevs` | Teamcenter::WorkspaceObject[] | any newly created Incremental Change Revisions. |
| `createdFutureICRevs` | Teamcenter::WorkspaceObject[] | any newly created future IC revs |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 returns the populated targetLines along with any 部分错误. |
| `newChildLines` | Teamcenter::Soa::Manufacturing::_2009_10::StructureManagement::LineToLinesMap | the 映射，键值对为 targetline and the newly created lines under it. |

---

#### 版本 2011-06

##### 2.10.3.1 getReferenceContexts

**接口路径：** `Manufacturing-2011-06-StructureManagement/getReferenceContexts`

**API 版本：** `2011-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取引用上下文。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.StructureManagement.getReferenceContexts`

**请求（input）：**

```json
{
  "contexts": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `contexts` | Teamcenter::BusinessObject[] | 向量，元素为 输入 contexts |

**响应（output）：**

```json
{
  "refcontexts": [
    {
      "contextsarray": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `refcontexts` | Teamcenter::Soa::Manufacturing::_2011_06::StructureManagement::ContextsArray[] | 向量，元素为 vectors referenced contexts 根据 the order 从 输入 向量 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 will return 错误 only. No data 将 return via 服务数据. |

---

##### 2.10.3.2 setReferenceContexts

**接口路径：** `Manufacturing-2011-06-StructureManagement/setReferenceContexts`

**API 版本：** `2011-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 设置引用上下文。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.StructureManagement.setReferenceContexts`

**请求（input）：**

```json
{
  "input": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "addRefContexts": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "removeRefContexts": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "removeExistingRef": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2011_06::StructureManagement::ReferencedContexts[] | includes ReferencedContexts 结构 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2013-05

##### 2.10.4.1 findAffectedCCs

**接口路径：** `Manufacturing-2013-05-StructureManagement/findAffectedCCs`

**API 版本：** `2013-05`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 查找包含输入对象工艺路径的所有协同上下文（CC）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.StructureManagement.findAffectedCCs`

**请求（input）：**

```json
{
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `objects` | Teamcenter::WorkspaceObject[] | The items to find their 协同上下文s (as a reference). |

**响应（output）：**

```json
{
  "output": [
    {
      "affectedObjects": [
        {
          "queryObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "affectedCC": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2013_05::StructureManagement::FindAffectedCCsOutput[] | 输出 data includes the affected CCs and the items 其 is 与…相关 each CC. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 输出. |

---

#### 版本 2015-03

##### 2.10.5.1 moveAndResequenceNodes

**接口路径：** `Manufacturing-2015-03-StructureManagement/moveAndResequenceNodes`

**API 版本：** `2015-03`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 移动并重新排序制造结构节点。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2015_03.StructureManagement.moveAndResequenceNodes`

**请求（input）：**

```json
{
  "inputList": [
    {
      "sourceNodes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "targetNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "predecessor": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isDroppedOnTarget": "",
      "findNumberContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isPasteDuplicate": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputList` | Teamcenter::Soa::Manufacturing::_2015_03::StructureManagement::MoveAndResequenceParameter[] | The 列表，元素为 moveAndResequenceParameter 结构. Each 结构 指定 the nodes to be moved, their target, 是否 dropped 在 target, context 基于 其 find 编号 to be decided and 是否 to clone or move the nodes 到 new target. |

**响应（output）：**

```json
{
  "createdICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "createdFutureICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "newChildLines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `createdICRevs` | Teamcenter::WorkspaceObject[] | 列表，元素为 newly created Incremental Change (IC) revisions. |
| `createdFutureICRevs` | Teamcenter::WorkspaceObject[] | 列表，元素为 newly created future IC revisions. |
| `newChildLines` | Teamcenter::Soa::Manufacturing::_2015_03::StructureManagement::TargetToNewChildLinesMap | The 映射 (BOM 行, 列表，元素为 BOM 行) of target BOM 行 and the newly created or moved BOM 行 对象 under it. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误. |

---

#### 版本 2015-10

##### 2.10.6.1 createCollabPlanningContext

**接口路径：** `Manufacturing-2015-10-StructureManagement/createCollabPlanningContext`

**API 版本：** `2015-10`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 创建协同规划上下文（CPC）并封装输入结构。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2015_10.StructureManagement.createCollabPlanningContext`

**请求（input）：**

```json
{
  "cpcInput": {
    "cloningStructsInfo": [
      {
        "newName": "",
        "newDescription": "",
        "newId": "",
        "newRevId": "",
        "scopes": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "cloningRule": "",
        "cloningParams": {}
      }
    ],
    "releaseStatus": "",
    "effectivityInfo": {
      "endItem": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "endItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "unitRangeText": "",
      "dateRange": [
        "0001-01-01T00:00:00"
      ],
      "openEndedStatus": ""
    },
    "originalCCUid": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "cpcName": "",
    "cpcDesc": "",
    "refStructures": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `cpcInput` | Teamcenter::Soa::Manufacturing::_2015_10::StructureManagement::CreateCPCInputInfo | 输入 到 服务 is a 结构 其 包含 a 列表，元素为 BOM 行 对象 that are to be cloned and\or referred, cloning information, 名称 and description of new CPC. |

**响应（output）：**

```json
{
  "cpcObject": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `cpcObject` | Teamcenter::BusinessObject | The created CPC 对象. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 |

---

#### 版本 2018-11

##### 2.10.7.1 copyRecursively

**接口路径：** `Manufacturing-2018-11-StructureManagement/copyRecursively`

**API 版本：** `2018-11`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 递归复制制造结构节点。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2018_11.StructureManagement.copyRecursively`

**请求（input）：**

```json
{
  "copyInput": [
    {
      "templateInfo": {
        "objectToClone": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "cloningRule": "",
        "referenceWindow": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "additionalInfo": {
          "strToDateVectorMap": {},
          "strToDoubleVectorMap": {},
          "strToStrVectorMap": {},
          "strToObjVectorMap": {},
          "strToIntVectorMap": {}
        }
      },
      "configurationInfo": {
        "revisionRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "variantRules": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "copySuppressedLines": "",
        "copyFutureEffectivities": "",
        "additionalInfo": {
          "strToDateVectorMap": {},
          "strToDoubleVectorMap": {},
          "strToStrVectorMap": {},
          "strToObjVectorMap": {},
          "strToIntVectorMap": {}
        }
      },
      "newObjectInfo": {
        "newName": "",
        "newDescription": "",
        "newId": "",
        "newrevId": "",
        "pasteTarget": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "additionalInfo": {
          "strToDateVectorMap": {},
          "strToDoubleVectorMap": {},
          "strToStrVectorMap": {},
          "strToObjVectorMap": {},
          "strToIntVectorMap": {}
        }
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `copyInput` | Teamcenter::Soa::Manufacturing::_2018_11::StructureManagement::CopyRecursivelyInputInfo[] | A 列表，元素为 输入 结构 其 包含 information about the template 结构 to be cloned, configuration information and the information about the cloned 对象. |

**响应（output）：**

```json
{
  "dataMap": {},
  "logFileTicket": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `dataMap` | Teamcenter::Soa::Manufacturing::_2018_11::StructureManagement::OriginalToCloneStructureMap | A 映射 &lt;BusinessObject, BusinessObject&gt; 包含 输入 对象 其 has been cloned as key and the 物料版本 的 cloned 对象 as 值. |
| `logFileTicket` | std::string | The FMS 票据 对于 transient 文件 that captures the log of cloning 操作. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The standard 服务数据. |

---

##### 2.10.7.2 pasteDuplicateStructure

**接口路径：** `Manufacturing-2018-11-StructureManagement/pasteDuplicateStructure`

**API 版本：** `2018-11`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 粘贴并复制制造结构（重复粘贴）。（存在 2009-10、2018-11 两个 API 版本）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2018_11.StructureManagement.pasteDuplicateStructure`

**请求（input）：**

```json
{
  "pasteDuplicateInput": [
    {
      "sourceLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "targetLine": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "copyRulesKey": "",
  "notifyEvents": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `pasteDuplicateInput` | Teamcenter::Soa::Manufacturing::_2018_11::StructureManagement::PasteDuplicateInput[] | The source BOM 行 and target BOM 行. |
| `copyRulesKey` | std::string | 名称 的 preference that 将 used for cloning. The preference 值 should be 列表，元素为 Strings. The format of each entry is as follows, sourceType.targetType.PasteDuplicateTemplate This entry 在 preference 值 means, an 对象 of 类型 source… |
| `notifyEvents` | bool | If true, the 客户端 is notified about BOM 行 events. |

**响应（output）：**

```json
{
  "pasteDuplicateOutput": [
    {
      "srcLineIndex": "",
      "targetLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newChildLine": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `pasteDuplicateOutput` | Teamcenter::Soa::Manufacturing::_2018_11::StructureManagement::PasteDuplicateStructureOutput[] | The target BOM 行, the new child BOM 行 created under this target and the 索引 of corresponding source BOM 行 在 输入. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 部分错误 as part 的 ServiceData（服务数据）. |

---

### 2.11 结构搜索（StructureSearch）

**涵盖 API 版本：** `2009-10`、`2013-05`、`2014-06`、`2014-12`  
**操作数：** 9

#### 版本 2009-10

##### 2.11.1.1 nextSearch

**接口路径：** `Manufacturing-2009-10-StructureSearch/nextSearch`

**API 版本：** `2009-10`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 获取下一批结构搜索结果。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureSearch.nextSearch`

**请求（input）：**

```json
{
  "searchCursor": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchCursor` | Teamcenter::BusinessObject | searchCursor |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "objectDone": "",
  "estimatedObjectsLeft": "",
  "percentComplete": "",
  "searchCursor": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "finished": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |
| `objects` | Teamcenter::BusinessObject[] | A batch of 对象 that satisfy the search criteria for this search |
| `objectDone` | int | The 数量为 对象 在 结构 that have been processed so far |
| `estimatedObjectsLeft` | int | An estimate 的 数量为 lines yet to be processed |
| `percentComplete` | double | percentComplete |
| `searchCursor` | Teamcenter::BusinessObject | Search cursor 对象 that holds the current state 的 search 在 BOM session |
| `finished` | bool | A boolean 值 其 当 'true' 指定 the search is finished |

---

##### 2.11.1.2 startSearch

**接口路径：** `Manufacturing-2009-10-StructureSearch/startSearch`

**API 版本：** `2009-10`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 启动结构搜索。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureSearch.startSearch`

**请求（input）：**

```json
{
  "scope": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "searchExpression": {
    "itemAndRevisionAttributeExpressions": [
      {
        "className": "",
        "attributeName": "",
        "attributeType": "BooleanType",
        "queryOperator": "Equal",
        "values": {
          "boolValues": [],
          "intValues": [],
          "doubleValues": [],
          "stringValues": [
            ""
          ],
          "dateValues": "0001-01-01T00:00:00",
          "tagValues": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      }
    ],
    "occurrenceNoteExpressions": [
      {
        "noteType": "",
        "queryOperator": "Equal",
        "values": [
          ""
        ]
      }
    ],
    "returnScopedSubTreesHit": "",
    "formAttributeExpressions": [
      {
        "isItemForm": "",
        "relationType": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "formType": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "attributeName": "",
        "attributeType": "BooleanType",
        "queryOperator": "Equal",
        "values": {
          "boolValues": [],
          "intValues": [],
          "doubleValues": [],
          "stringValues": [
            ""
          ],
          "dateValues": "0001-01-01T00:00:00",
          "tagValues": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      }
    ],
    "proximitySearchExpressions": [
      {
        "bomLines": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "distance": "",
        "includeChildBomLines": ""
      }
    ],
    "boxZoneExpressions": [
      {
        "searchBoxes": [
          {
            "xmin": "",
            "ymin": "",
            "zmin": "",
            "xmax": "",
            "ymax": "",
            "zmax": "",
            "transform": []
          }
        ],
        "boxOperator": "Inside"
      }
    ],
    "planeZoneExpressions": [
      {
        "planzeZone": {
          "xvalue": "",
          "yvalue": "",
          "zvalue": "",
          "displacement": ""
        },
        "planeZoneOperator": "PlaneAbove"
      }
    ],
    "savedQueryExpressions": [
      {
        "savedQuery": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "entries": [
          ""
        ],
        "values": [
          ""
        ]
      }
    ],
    "inClassQueryExpressions": [
      {
        "inClassClassNames": [
          ""
        ],
        "inClassAttributeIDs": [],
        "inClassAttributeValues": [
          ""
        ]
      }
    ],
    "sizeSearchExpression": {
      "largerThan": "",
      "diagonalLength": ""
    },
    "doTrushapeRefinement": ""
  },
  "mfgSearchCriteria": {
    "objectTypes": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "logicalDesignator": [
      {
        "name": "",
        "value": ""
      }
    ],
    "refinements": [
      {
        "refinements": [
          {
            "relatedScopes": [
              {
                "uid": "",
                "type": "",
                "className": ""
              }
            ],
            "relations": [
              {
                "relationName": "",
                "matchType": "NotApplicableMatch",
                "objectClass": ""
              }
            ]
          }
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `scope` | Teamcenter::BusinessObject[] | scope lines within 其 to search |
| `searchExpression` | Teamcenter::Soa::Manufacturing::_2009_10::StructureSearch::SearchExpressionSet | generic search expression |
| `mfgSearchCriteria` | Teamcenter::Soa::Manufacturing::_2009_10::StructureSearch::MFGSearchCriteria | The MFG addition search criteria |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "objectDone": "",
  "estimatedObjectsLeft": "",
  "percentComplete": "",
  "searchCursor": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "finished": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |
| `objects` | Teamcenter::BusinessObject[] | A batch of 对象 that satisfy the search criteria for this search |
| `objectDone` | int | The 数量为 对象 在 结构 that have been processed so far |
| `estimatedObjectsLeft` | int | An estimate 的 数量为 lines yet to be processed |
| `percentComplete` | double | percentComplete |
| `searchCursor` | Teamcenter::BusinessObject | Search cursor 对象 that holds the current state 的 search 在 BOM session |
| `finished` | bool | A boolean 值 其 当 'true' 指定 the search is finished |

---

##### 2.11.1.3 stopSearch

**接口路径：** `Manufacturing-2009-10-StructureSearch/stopSearch`

**API 版本：** `2009-10`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 停止结构搜索。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureSearch.stopSearch`

**请求（input）：**

```json
{
  "searchCursor": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchCursor` | Teamcenter::BusinessObject | the search identifier |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "objectDone": "",
  "estimatedObjectsLeft": "",
  "percentComplete": "",
  "searchCursor": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "finished": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |
| `objects` | Teamcenter::BusinessObject[] | A batch of 对象 that satisfy the search criteria for this search |
| `objectDone` | int | The 数量为 对象 在 结构 that have been processed so far |
| `estimatedObjectsLeft` | int | An estimate 的 数量为 lines yet to be processed |
| `percentComplete` | double | percentComplete |
| `searchCursor` | Teamcenter::BusinessObject | Search cursor 对象 that holds the current state 的 search 在 BOM session |
| `finished` | bool | A boolean 值 其 当 'true' 指定 the search is finished |

---

#### 版本 2013-05

##### 2.11.2.1 findStudies

**接口路径：** `Manufacturing-2013-05-StructureSearch/findStudies`

**API 版本：** `2013-05`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 查找引用给定工艺/操作对象的所有研究（Study）对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.StructureSearch.findStudies`

**请求（input）：**

```json
{
  "inputNodes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputNodes` | Teamcenter::BusinessObject[] | A 列表，元素为 业务对象 for 其 referencing studies should be searced (对象 of 类型 Mfg0BvrProcess or Mfg0BvrOperation). |

**响应（output）：**

```json
{
  "results": [
    {
      "listOfStudies": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2013_05::StructureSearch::FindStudiesResults[] | The found Mfg0BvrStudy 对象 对于每个 inputNodes Mfg0BvrProcess or Mfg0BvrOperation |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 |

---

#### 版本 2014-06

##### 2.11.3.1 searchConnectedLines

**接口路径：** `Manufacturing-2014-06-StructureSearch/searchConnectedLines`

**API 版本：** `2014-06`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 搜索与输入连接 BOM 行相连的所有 BOM 行。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.StructureSearch.searchConnectedLines`

**请求（input）：**

```json
{
  "inputConnLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputConnLines` | Teamcenter::BusinessObject[] | 输入 BOM 行 对象 whose connected to information needs to be found. |

**响应（output）：**

```json
{
  "output": [
    {
      "connectionLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "connectedLines": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2014_06::StructureSearch::SrchConnectedLinesOutput[] | 列表，元素为 对象 containing 输入 connection and connected BOM 行s. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard 服务数据. |

---

#### 版本 2014-12

##### 2.11.4.1 createOrUpdateAssignmentRecipe

**接口路径：** `Manufacturing-2014-12-StructureSearch/createOrUpdateAssignmentRecipe`

**API 版本：** `2014-12`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 创建或更新分配方案。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.StructureSearch.createOrUpdateAssignmentRecipe`

**请求（input）：**

```json
{
  "input": [
    {
      "name": "",
      "recipeAnchorOrRecipe": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "searchContextSC": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "additionalSearchCriteria": {
        "objectTypes": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "logicalDesignator": {
          "name": "",
          "value": ""
        },
        "refinements": [
          {
            "refinements": [
              {
                "relatedScopes": [
                  {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                ],
                "relations": [
                  {
                    "relationName": "",
                    "matchType": "NotApplicableMatch",
                    "objectClass": ""
                  }
                ]
              }
            ]
          }
        ],
        "absoccAttributes": [
          {
            "name": "",
            "value": ""
          }
        ]
      },
      "appKey": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_12::StructureSearch::CreateOrUpdateAssignmentRecipeInputElem[] | A 列表，元素为 输入 elements specifying the details 的 recipe to be created and 附加到 a given node. |

**响应（output）：**

```json
{
  "info": [
    {
      "intMap": {},
      "dblMap": {},
      "strMap": {},
      "objMap": {},
      "dateMap": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `info` | Teamcenter::Soa::Manufacturing::_2014_12::StructureSearch::AdditionalInfo[] | A 列表，元素为 AdditionalInfo structures. If recipe 被创建, the objMap member will have the key "CreatedObject" 与 值 being the Mfg0MEMBOMRecipe 对象. If recipe 被更新 the objMap member will have the key "UpdatedObject". The strMap memb… |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

##### 2.11.4.2 deleteAssignmentRecipes

**接口路径：** `Manufacturing-2014-12-StructureSearch/deleteAssignmentRecipes`

**API 版本：** `2014-12`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 删除分配方案。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.StructureSearch.deleteAssignmentRecipes`

**请求（input）：**

```json
{
  "recipes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "recipeAnchors": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "contextForRemovingResolvedObjs": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "appKey": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `recipes` | Teamcenter::BusinessObject[] | A 列表，元素为 Mfg0MEMBOMRecipe 对象 to be deleted. |
| `recipeAnchors` | Teamcenter::BusinessObject[] | A 列表，元素为 BOM 行 对象 for 其 recipes are to be deleted. |
| `contextForRemovingResolvedObjs` | Teamcenter::BusinessObject | An 可选 BOMWindow 对象 to indicate resolved lines are to be deleted too. |
| `appKey` | std::string | The 名称 的 Application to identify the resolver 在 服务器. Currently, only allowed 值 is Mfg0AssignmentRecipe. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.11.4.3 getAssignmentRecipes

**接口路径：** `Manufacturing-2014-12-StructureSearch/getAssignmentRecipes`

**API 版本：** `2014-12`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 获取分配方案（Assignment Recipe）列表。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.StructureSearch.getAssignmentRecipes`

**请求（input）：**

```json
{
  "recipeAnchors": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "recipeNames": [
    ""
  ],
  "appKey": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `recipeAnchors` | Teamcenter::BusinessObject[] | A 列表，元素为 BOM 行 对象 for 其 recipes are to be obtained. |
| `recipeNames` | std::string[] | An 可选 列表，元素为 recipeNames to search for recipes under the specified recipeAnchors. |
| `appKey` | std::string | The 名称 的 Application to identify the resolved 在 服务器. Currently, only allowed 值 is Mfg0AssignmentRecipe. |

**响应（output）：**

```json
{
  "info": [
    {
      "intMap": {},
      "dblMap": {},
      "strMap": {},
      "objMap": {},
      "dateMap": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `info` | Teamcenter::Soa::Manufacturing::_2014_12::StructureSearch::AdditionalInfo[] | A 列表，元素为 AdditionInfo structures. If the recipe is found objMap member will have the key "Recipe" and the Mfg0MEMBOMRecipe 对象 as the 值, the strMap will have "名称" for key and the corresponding names 的 rec即 the objMap will… |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 capturing 部分错误 使用 输入 array 索引 as 客户端 ID. |

---

##### 2.11.4.4 resolveAssignmentRecipe

**接口路径：** `Manufacturing-2014-12-StructureSearch/resolveAssignmentRecipe`

**API 版本：** `2014-12`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 解析并应用分配方案。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.StructureSearch.resolveAssignmentRecipe`

**请求（input）：**

```json
{
  "input": [
    {
      "recipeAnchor": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "recipeObjs": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "searchScopes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "reResolve": "",
      "removePreviouslyResolved": "",
      "recursive": "",
      "generateLog": "",
      "appKey": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_12::StructureSearch::ResolveAssignmentRecipeInputElement[] | A 列表，元素为 ResolveAssignmentRecipeInputElement structures each detailing the node on 其 the recipe is to be resolved. |

**响应（output）：**

```json
{
  "info": [
    {
      "intMap": {},
      "dblMap": {},
      "strMap": {},
      "objMap": {},
      "dateMap": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `info` | Teamcenter::Soa::Manufacturing::_2014_12::StructureSearch::AdditionalInfo[] | A 列表，元素为 AdditionInfo structures. The names 的 resolved recipes appear under the "Recipe" key of strMap. Each 值 in this strMap is a further key into objMap and the 值 for those are the resolved BOM 行 对象. Any BOM 行 对象 that … |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） to caputre 部分错误. |

---

### 2.12 时间管理（TimeManagement）

**涵盖 API 版本：** `2008-06`、`2010-09`  
**操作数：** 6

#### 版本 2008-06

##### 2.12.1.1 allocatedTimeRollUp

**接口路径：** `Manufacturing-2008-06-TimeManagement/allocatedTimeRollUp`

**API 版本：** `2008-06`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 计算各工艺行的已分配时间汇总。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_06.TimeManagement.allocatedTimeRollUp`

**请求（input）：**

```json
{
  "object": {
    "roots": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "calculatedBy": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `object` | Teamcenter::Soa::Manufacturing::_2008_06::TimeManagement::AllocatedTime | TODO |

**响应（output）：**

```json
{
  "results": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2008_06::TimeManagement::MapAllocatedTimeResults | 映射，键值对为 each root and its allocated time result. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

##### 2.12.1.2 timeAnalysisRollup

**接口路径：** `Manufacturing-2008-06-TimeManagement/timeAnalysisRollup`

**API 版本：** `2008-06`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 按活动类别汇总工艺行的时间分析结果。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_06.TimeManagement.timeAnalysisRollup`

**请求（input）：**

```json
{
  "inputs": {
    "roots": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "runTimePropertiesToRecalc": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Manufacturing::_2008_06::TimeManagement::TimeAnalysisInputs | a Time Analysis 输入 结构, 必需 |

**响应（output）：**

```json
{
  "results": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "categoryResults": {},
      "mapRunTimeResult": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2008_06::TimeManagement::TimeAnalysisResult[] | 向量，元素为 the TimeAnalysisResult. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

#### 版本 2010-09

##### 2.12.2.1 calculateCriticalPathEx

**接口路径：** `Manufacturing-2010-09-TimeManagement/calculateCriticalPathEx`

**API 版本：** `2010-09`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 扩展计算关键路径（含附加规则）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.TimeManagement.calculateCriticalPathEx`

**请求（input）：**

```json
{
  "roots": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "processLeafNodes": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `roots` | Teamcenter::BusinessObject[] | The 列表，元素为 MFG process or 操作 对象 the critical path is to be calculated for. |
| `processLeafNodes` | bool | A 标志 that determines 是否 to compute the path 从 leave nodes 的 process/操作 结构 or 从 direct children of a root 对象. |

**响应（output）：**

```json
{
  "results": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "components": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "duration": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2010_09::TimeManagement::CalculateCriticalPathResultEx[] | A 列表，元素为 CalculateCriticalPathResultEx structures 对于每个 path returned. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 包含 a 列表，元素为 错误 descriptions if the path computation has failed. |

---

##### 2.12.2.2 getActivityTimes

**接口路径：** `Manufacturing-2010-09-TimeManagement/getActivityTimes`

**API 版本：** `2010-09`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 获取活动的时间属性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.TimeManagement.getActivityTimes`

**请求（input）：**

```json
{
  "rootNodes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `rootNodes` | Teamcenter::BusinessObject[] | The root nodes 的 tree structures for 其 the activity times are to be computed. |

**响应（output）：**

```json
{
  "results": [
    {
      "rootNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "timePerCategoryMap": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2010_09::TimeManagement::GetActivityTimesResult[] | A 向量，元素为 GetActivityTimesResult structures that holds 对于每个 root node the 列表，元素为 activity times indexed by category. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data 结构 that is 用于 return Teamcenter model data from a 服务 request. This member 同时包含 服务 exceptions. |

---

##### 2.12.2.3 populateAllocatedTimeProperties

**接口路径：** `Manufacturing-2010-09-TimeManagement/populateAllocatedTimeProperties`

**API 版本：** `2010-09`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 填充已分配时间相关属性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.TimeManagement.populateAllocatedTimeProperties`

**请求（input）：**

```json
{
  "rootNodes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "propagateZeroValues": "",
  "stopLevel": "",
  "precedence": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `rootNodes` | Teamcenter::BusinessObject[] | 定义 the root nodes 的 trees to be updated. |
| `propagateZeroValues` | bool | If this parameter is false, the allocated time of a specific node is only overwritten if more detailed information is available at a lower level. This means that if a given node is not further detailed by any sub node, o… |
| `stopLevel` | int | If this parameter is greater than 0, the update will stop that 数量为 levels below the root node. This means that the root node itself 将 excluded 从 update if the 值 is 1; if it is 2, all child nodes with exception 的 root's d… |
| `precedence` | std::string[] | The precedence 向量 定义 how the allocated time of a leaf node is to be determined. Each entry must consist of one 的 值 'estimated_t即 'simulated_t即 'allocated_time' or 'analysis'. 在 case of 'estimated_time' or 'simulated_time… |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.12.2.4 updateTimeManagementProperties

**接口路径：** `Manufacturing-2010-09-TimeManagement/updateTimeManagementProperties`

**API 版本：** `2010-09`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 更新时间管理相关属性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.TimeManagement.updateTimeManagementProperties`

**请求（input）：**

```json
{
  "rootNodes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "fieldNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `rootNodes` | Teamcenter::BusinessObject[] | The root nodes 的 tree structures for 其 the runtime 属性 are to be calculated. |
| `fieldNames` | std::string[] | The names 的 calculated fields to recompute. Currently the following fieldnames are accepted: Mfg0calc_duration, Mfg0calc_start_time, Mfg0calc_dur_start_time, bl_me_work_time and bl_me_duration. If the fieldName 向量 is emp… |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.13 时间路径计划（TimeWayPlan）

**涵盖 API 版本：** `2013-05`  
**操作数：** 2

#### 版本 2013-05

##### 2.13.1.1 getTWPInformation

**接口路径：** `Manufacturing-2013-05-TimeWayPlan/getTWPInformation`

**API 版本：** `2013-05`  
**Service：** `TimeWayPlan`  
**Library：** `Manufacturing`

**说明：** 从工厂 BOP 获取时间路径计划（TWP）信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.TimeWayPlan.getTWPInformation`

**请求（input）：**

```json
{
  "input": {
    "requestedObjects": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "contextProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "requiredData": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::TimeWayPlan::TwpInfoInput | 输入 结构 包含 对象(s) for 其 information is requ即 the 列表，元素为 string specifying what information is 必需 and the product 工艺清单（BOP） (BOP) context. The 对象 can be process station(s), 工艺行(s), process area(s), or 工厂 BOP. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "infoMap": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误 若有. |
| `infoMap` | Teamcenter::Soa::Manufacturing::_2013_05::TimeWayPlan::InformationMap | A 映射，键值对为 业务对象 for 其 TWP information is requested and its corresponding TWP information. |

---

##### 2.13.1.2 setProductImage

**接口路径：** `Manufacturing-2013-05-TimeWayPlan/setProductImage`

**API 版本：** `2013-05`  
**Service：** `TimeWayPlan`  
**Library：** `Manufacturing`

**说明：** 为时间路径计划对象设置产品图像。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.TimeWayPlan.setProductImage`

**请求（input）：**

```json
{
  "input": [
    {
      "targetObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "contextProductBOP": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "imageDataset": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::TimeWayPlan::ProductImageInfo[] | 输入 结构 包含 对象(s) for 其 product image is to be set, the 业务对象 的 dataset representing the image and the product 工艺清单（BOP）es (BOP) context. The 对象 can be process station(s), 工艺行(s), process area(s), or 工厂 BOP. |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.14 验证（Validation）

**涵盖 API 版本：** `2012-09`、`2014-12`、`2017-05`  
**操作数：** 4

#### 版本 2012-09

##### 2.14.1.1 executeValidations

**接口路径：** `Manufacturing-2012-09-Validation/executeValidations`

**API 版本：** `2012-09`  
**Service：** `Validation`  
**Library：** `Manufacturing`

**说明：** 对指定对象执行已注册的制造验证规则。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_09.Validation.executeValidations`

**请求（input）：**

```json
{
  "input": [
    {
      "root": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "validationChecks": [
        {
          "type": "",
          "library": "",
          "name": "",
          "func": "",
          "failAllOnError": ""
        }
      ]
    }
  ],
  "failAllOnError": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_09::Validation::ValidationCheckExecutionParam[] | Validation Check Execution Param |
| `failAllOnError` | bool | 是否 or not to fail all tests 当 错误 occurs on a specific validation check for a specific line or to continue. |

**响应（output）：**

```json
{
  "errors": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "validationErrors": [
        {
          "msgId": "",
          "msg": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "validationNoticeType": ""
        }
      ],
      "validationTest": {
        "type": "",
        "library": "",
        "name": "",
        "func": "",
        "failAllOnError": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `errors` | Teamcenter::Soa::Manufacturing::_2012_09::Validation::ValidationCheckExecutionErrors[] | 错误 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData（服务数据） member |

---

##### 2.14.1.2 getAllValidations

**接口路径：** `Manufacturing-2012-09-Validation/getAllValidations`

**API 版本：** `2012-09`  
**Service：** `Validation`  
**Library：** `Manufacturing`

**说明：** 获取所有可用的制造验证定义。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_09.Validation.getAllValidations`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "params": [
    {
      "type": "",
      "library": "",
      "name": "",
      "func": "",
      "failAllOnError": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `params` | Teamcenter::Soa::Manufacturing::_2012_09::Validation::ValidationCheckCallbackParam[] | params |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

#### 版本 2014-12

##### 2.14.2.1 getMaturityReport

**接口路径：** `Manufacturing-2014-12-Validation/getMaturityReport`

**API 版本：** `2014-12`  
**Service：** `Validation`  
**Library：** `Manufacturing`

**说明：** 获取制造成熟度（Maturity）报告。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.Validation.getMaturityReport`

**请求（input）：**

```json
{
  "maturityReportRequest": {
    "inputObjects": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "selectedRules": {},
    "supportingInformation": [
      {
        "propertyName": "",
        "value": [
          ""
        ],
        "dataType": ""
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `maturityReportRequest` | Teamcenter::Soa::Manufacturing::_2014_12::Validation::MaturityReportRequest | 输入 到 getMaturityReport 操作. It has the below parameters - inputObjects - 输入 包含 BOM 行 其 acts as a scope for maturity check. The 对象 在 hierarchy 的 scope are candidates 对于 check. ruleList - The 列表，元素为 rules for 其 maturity is … |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "maturityResult": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误. |
| `maturityResult` | Teamcenter::Soa::Manufacturing::_2014_12::Validation::MaturityResult | The result of getMaturityData 操作, 包含 BusinessObjects and their maturity data. |

---

#### 版本 2017-05

##### 2.14.3.1 getAllRegisteredCallbacks

**接口路径：** `Manufacturing-2017-05-Validation/getAllRegisteredCallbacks`

**API 版本：** `2017-05`  
**Service：** `Validation`  
**Library：** `Manufacturing`

**说明：** 获取所有已注册的验证回调。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_05.Validation.getAllRegisteredCallbacks`

**请求（input）：**

```json
{
  "callbackType": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `callbackType` | std::string | The 类型 of customized registered callback functions to retrieve. |

**响应（output）：**

```json
{
  "parameters": [
    {
      "type": "",
      "library": "",
      "name": "",
      "functionName": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `parameters` | Teamcenter::Soa::Manufacturing::_2017_05::Validation::RegisteredCallbackParam[] | The registered callback functions details for 给定输入 类型. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData（服务数据） member. |

---

---

## 3. 按 API 版本（年-月）归档

按时间线列出各版本契约下的全部接口（与第 2 节内容一致，便于按版本检索）。

### 3.1 API 版本 2008-06

**Service：** Core、DataManagement、TimeManagement  **操作数：** 5

#### 3.1.1 findCheckedOutsInStructure（2008-06）

**接口路径：** `Manufacturing-2008-06-Core/findCheckedOutsInStructure`

**API 版本：** `2008-06`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 在指定结构范围内查找所有已检出对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_06.Core.findCheckedOutsInStructure`

**请求（input）：**

```json
{
  "searchScope": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchScope` | Teamcenter::BusinessObject[] | 向量，元素为 l即 that we would like to get all the 已检出 对象 from. |

**响应（output）：**

```json
{
  "checkedOutList": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `checkedOutList` | Teamcenter::BusinessObject[] | This is the 结构 包含 Tags of all the 已检出s 对象. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

#### 3.1.2 createOrUpdateMEActivityFolders（2008-06）

**接口路径：** `Manufacturing-2008-06-DataManagement/createOrUpdateMEActivityFolders`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 创建或更新 ME 活动文件夹；支持多级子活动。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_06.DataManagement.createOrUpdateMEActivityFolders`

**请求（input）：**

```json
{
  "activityInfos": [
    {
      "activity": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "name": "",
      "description": "",
      "type": "",
      "toolInfo": {
        "processBV": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "toolOccThreadChains": {}
      },
      "contents": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "parentActivities": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "predecessors": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "attributes": [
        {
          "name": "",
          "values": [
            ""
          ]
        }
      ],
      "complete": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `activityInfos` | Teamcenter::Soa::Manufacturing::_2008_06::DataManagement::MEActivityFolderInfo[] | 输入 is a 向量，元素为 ME 活动文件夹Info structs. A Boolean 值 part 的 结构 signifying if 输入 data 表示 the complete representation 的 folder tools, predecessors, and contents or if it 表示 对象 to be appended 到 existing folder tools, predecesso… |

**响应（output）：**

```json
{
  "successfullyProcessedMEAct": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `successfullyProcessedMEAct` | Teamcenter::Soa::Manufacturing::_2008_06::DataManagement::SuccessFullyProcessedMapMEAct | successfullyProcessedMEAct |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

#### 3.1.3 createOrUpdateMENXObjects（2008-06）

**接口路径：** `Manufacturing-2008-06-DataManagement/createOrUpdateMENXObjects`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 创建或更新 MENX 对象及其属性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_06.DataManagement.createOrUpdateMENXObjects`

**请求（input）：**

```json
{
  "meObjectInfos": [
    {
      "menxObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "name": "",
      "description": "",
      "type": "",
      "subType": "",
      "attributes": [
        {
          "name": "",
          "values": [
            ""
          ]
        }
      ]
    }
  ],
  "container": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `meObjectInfos` | Teamcenter::Soa::Manufacturing::_2008_06::DataManagement::MENXObjectInfo[] | 输入 is a 向量，元素为 MENX 对象Info structs. |
| `container` | Teamcenter::Folder | The folder into 其 the created 对象 are to be placed. This can be a NULLTAG in 其 case the created 对象 will not be inserted 到ny folder. |

**响应（output）：**

```json
{
  "successfullyProcessedMENXObj": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `successfullyProcessedMENXObj` | Teamcenter::Soa::Manufacturing::_2008_06::DataManagement::SuccessFullyProcessedMapMENXObj | successfullyProcessedMENXObj |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

#### 3.1.4 allocatedTimeRollUp（2008-06）

**接口路径：** `Manufacturing-2008-06-TimeManagement/allocatedTimeRollUp`

**API 版本：** `2008-06`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 计算各工艺行的已分配时间汇总。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_06.TimeManagement.allocatedTimeRollUp`

**请求（input）：**

```json
{
  "object": {
    "roots": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "calculatedBy": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `object` | Teamcenter::Soa::Manufacturing::_2008_06::TimeManagement::AllocatedTime | TODO |

**响应（output）：**

```json
{
  "results": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2008_06::TimeManagement::MapAllocatedTimeResults | 映射，键值对为 each root and its allocated time result. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

#### 3.1.5 timeAnalysisRollup（2008-06）

**接口路径：** `Manufacturing-2008-06-TimeManagement/timeAnalysisRollup`

**API 版本：** `2008-06`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 按活动类别汇总工艺行的时间分析结果。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_06.TimeManagement.timeAnalysisRollup`

**请求（input）：**

```json
{
  "inputs": {
    "roots": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "runTimePropertiesToRecalc": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Manufacturing::_2008_06::TimeManagement::TimeAnalysisInputs | a Time Analysis 输入 结构, 必需 |

**响应（output）：**

```json
{
  "results": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "categoryResults": {},
      "mapRunTimeResult": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2008_06::TimeManagement::TimeAnalysisResult[] | 向量，元素为 the TimeAnalysisResult. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

### 3.2 API 版本 2008-12

**Service：** IPAManagement  **操作数：** 4

#### 3.2.1 deletefilteredIPA（2008-12）

**接口路径：** `Manufacturing-2008-12-IPAManagement/deletefilteredIPA`

**API 版本：** `2008-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 删除筛选条件下的在制品装配数据（早期版本接口）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_12.IPAManagement.deletefilteredIPA`

**请求（input）：**

```json
{
  "processes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processes` | Teamcenter::BusinessObject[] | 输入 向量，元素为 process l即 from 其 we want to delete the filteredIPA. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.2 generateSearchScope（2008-12）

**接口路径：** `Manufacturing-2008-12-IPAManagement/generateSearchScope`

**API 版本：** `2008-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 生成在制品装配搜索范围。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_12.IPAManagement.generateSearchScope`

**请求（input）：**

```json
{
  "processes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processes` | Teamcenter::BusinessObject[] | processes 向量，元素为 process l即 that we would like to get all the search scope from. |

**响应（output）：**

```json
{
  "bomlines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `bomlines` | Teamcenter::BusinessObject[] | A vectoer of all the BOM 行s that are the search scope. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

#### 3.2.3 getFilteredIPA（2008-12）

**接口路径：** `Manufacturing-2008-12-IPAManagement/getFilteredIPA`

**API 版本：** `2008-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 获取筛选后的在制品装配结果。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_12.IPAManagement.getFilteredIPA`

**请求（input）：**

```json
{
  "processes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processes` | Teamcenter::BusinessObject[] | 输入 向量，元素为 process l即 from 其 we want to find the filteredIPA. |

**响应（output）：**

```json
{
  "filteredIPAs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `filteredIPAs` | Teamcenter::BusinessObject[] | A vectoer of all the filteredIPAs found. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

#### 3.2.4 saveSearchResult（2008-12）

**接口路径：** `Manufacturing-2008-12-IPAManagement/saveSearchResult`

**API 版本：** `2008-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 保存在制品装配搜索结果。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2008_12.IPAManagement.saveSearchResult`

**请求（input）：**

```json
{
  "input": [
    {
      "process": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "searchResultList": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "name": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2008_12::IPAManagement::IPAManagementSaveSearchResultInput[] | 输入 向量，元素为 IPAManagementSaveSearchResultInput Structures see discription in 结构 definition 文件. |

**响应（output）：**

```json
{
  "filteredIPA": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "filteredIPARoot": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "rejectedList": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `filteredIPA` | Teamcenter::BusinessObject | This is the new filteredIPA 结构. |
| `filteredIPARoot` | Teamcenter::BusinessObject | The flat 列表，元素为 all filteredIPA structures. |
| `rejectedList` | Teamcenter::BusinessObject[] | A 列表，元素为 all the BOM 行s that were not found 在 IPA 结构. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

### 3.3 API 版本 2009-06

**Service：** StructureManagement  **操作数：** 8

#### 3.3.1 closeAttachmentWindow（2009-06）

**接口路径：** `Manufacturing-2009-06-StructureManagement/closeAttachmentWindow`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 关闭附件窗口。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.closeAttachmentWindow`

**请求（input）：**

```json
{
  "lines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::BOMLine[] | 输入 BOM 行s for 其 the attachmentwindow has to be closed. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.3.2 createOrUpdateAttachments（2009-06）

**接口路径：** `Manufacturing-2009-06-StructureManagement/createOrUpdateAttachments`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 创建或更新结构附件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.createOrUpdateAttachments`

**请求（input）：**

```json
{
  "attachments": [
    {
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objects": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `attachments` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::CreateOrUpdateAttachmentsData[] | 输入 either BOM 行 or attachmentline (parent) and the relations and 工作区对象 to be processed as attachments. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.3.3 deleteAttachments（2009-06）

**接口路径：** `Manufacturing-2009-06-StructureManagement/deleteAttachments`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 删除结构附件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.deleteAttachments`

**请求（input）：**

```json
{
  "lines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::CfgAttachmentLine[] | remove the specified lines 从 parent attachment window. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.3.4 getAttachmentLineChildren（2009-06）

**接口路径：** `Manufacturing-2009-06-StructureManagement/getAttachmentLineChildren`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取附件行的子行。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.getAttachmentLineChildren`

**请求（input）：**

```json
{
  "attlines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `attlines` | Teamcenter::CfgAttachmentLine[] | 输入 parent attachment lines |

**响应（output）：**

```json
{
  "lines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::AttachmentLineToChildLinesMap | 映射，键值对为 parent attachmentline to child lines. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | any 部分错误 to be returned. |

---

#### 3.3.5 getBOMLineActivities（2009-06）

**接口路径：** `Manufacturing-2009-06-StructureManagement/getBOMLineActivities`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取 BOM 行关联的活动。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.getBOMLineActivities`

**请求（input）：**

```json
{
  "bomLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `bomLines` | Teamcenter::BOMLine[] | 输入 向量，元素为 BOM 行s for 其 activities are needed. |

**响应（output）：**

```json
{
  "lines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::BOMLineToActivitiesMap | 向量，元素为 BOM 行 to activities 映射 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） 对象 to capture 部分错误. |

---

#### 3.3.6 getBOMLineAttachments（2009-06）

**接口路径：** `Manufacturing-2009-06-StructureManagement/getBOMLineAttachments`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取 BOM 行附件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.getBOMLineAttachments`

**请求（input）：**

```json
{
  "bomlines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "filter": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `bomlines` | Teamcenter::BOMLine[] | 列表，元素为 输入 BOM 行s |
| `filter` | std::string[] | 可选 relation filter to be used for attachments. The relation names specified here are used as a filter 在 attachmentwindow |

**响应（output）：**

```json
{
  "lines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::BOMLineToAttachmentLinesMap | BOM 行 to attachmentlines 映射 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） to capture 部分错误. |

---

#### 3.3.7 getStructureContextActivityLines（2009-06）

**接口路径：** `Manufacturing-2009-06-StructureManagement/getStructureContextActivityLines`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取结构上下文活动行。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.getStructureContextActivityLines`

**请求（input）：**

```json
{
  "scs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `scs` | Teamcenter::StructureContext[] | 列表，元素为 输入 structurecontext 对象 |

**响应（output）：**

```json
{
  "lines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::StructureContextActivityLinesMap | 映射，键值对为 sc to activity lines |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | for reporting 部分错误. |

---

#### 3.3.8 getStructureContextTopLines（2009-06）

**接口路径：** `Manufacturing-2009-06-StructureManagement/getStructureContextTopLines`

**API 版本：** `2009-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取结构上下文顶层行。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_06.StructureManagement.getStructureContextTopLines`

**请求（input）：**

```json
{
  "scs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `scs` | Teamcenter::StructureContext[] | 输入 列表，元素为 SC's |

**响应（output）：**

```json
{
  "lines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `lines` | Teamcenter::Soa::Manufacturing::_2009_06::StructureManagement::StructureContextToLinesMap | 映射，键值对为 SC to it's lines |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） to hold 部分错误 |

---

### 3.4 API 版本 2009-10

**Service：** DataManagement、MFGPropertyCollector、Model、ModelDefinitions、StructureManagement、StructureSearch  **操作数：** 17

#### 3.4.1 createObjects（2009-10）

**接口路径：** `Manufacturing-2009-10-DataManagement/createObjects`

**API 版本：** `2009-10`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 通用制造对象创建，支持递归创建附属对象（如 Item、版本、表单等）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.DataManagement.createObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": "",
      "data": {
        "type": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "compoundCreateInput": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2009_10::DataManagement::CreateIn[] | a 列表，元素为 CreateIn 对象 representing the Create 输入 for 业务对象 to be created |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "objects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2009_10::DataManagement::CreateOut[] | 向量，元素为 输出 对象 representing 对象 that were created |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 包括 部分错误 that are mapped 到 客户端 ID |

---

#### 3.4.2 disconnectObjects（2009-10）

**接口路径：** `Manufacturing-2009-10-DataManagement/disconnectObjects`

**API 版本：** `2009-10`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 断开制造节点之间的连接关系。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.DataManagement.disconnectObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "disconnectFrom": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2009_10::DataManagement::DisconnectInput[] | A 列表，元素为 disconnectInput 对象 对于 对象 to disconnect |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.4.3 collectProperties（2009-10）

**接口路径：** `Manufacturing-2009-10-MFGPropertyCollector/collectProperties`

**API 版本：** `2009-10`  
**Service：** `MFGPropertyCollector`  
**Library：** `Manufacturing`

**说明：** 收集制造对象的属性信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.MFGPropertyCollector.collectProperties`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "rootNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "traversalRuleList": [
        {
          "traversalRuleKeys": [
            {
              "types": [
                ""
              ],
              "context": ""
            }
          ],
          "targets": [
            ""
          ]
        }
      ],
      "propVisitorList": [
        {
          "traversalVisitorsKeys": [
            {
              "types": [
                ""
              ],
              "context": ""
            }
          ],
          "propToCollectList": [
            ""
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2009_10::MFGPropertyCollector::CollectPropertiesInputInfo[] | MfgNode, traversal rules and 属性 names to collect |

**响应（output）：**

```json
{
  "outputList": [
    {
      "clientId": "",
      "output": [
        {
          "contextType": "",
          "nodeValueList": [
            {
              "node": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "props": {}
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `outputList` | Teamcenter::Soa::Manufacturing::_2009_10::MFGPropertyCollector::CollectPropertiesOutput[] | The collection of MfgNode, 属性 names and theit 值. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 containing partial 错误 data |

---

#### 3.4.4 calculateCriticalPath（2009-10）

**接口路径：** `Manufacturing-2009-10-Model/calculateCriticalPath`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 计算模型中的关键路径。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.calculateCriticalPath`

**请求（input）：**

```json
{
  "roots": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `roots` | Teamcenter::BusinessObject[] | The 列表，元素为 MFG BVR or APS root 对象 the critical path is to be calculated for. |

**响应（output）：**

```json
{
  "results": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "components": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "duration": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2009_10::Model::CalculateCriticalPathResult[] | A 列表，元素为 CalculateCriticalPathResult structures 对于每个 path returned. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data strucuture 用于 return sets of Teamcenter Data Model 对象 from a 服务 request. This 同时包含 services exceptions. |

---

#### 3.4.5 createFlow（2009-10）

**接口路径：** `Manufacturing-2009-10-Model/createFlow`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 创建工艺流（Flow）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.createFlow`

**请求（input）：**

```json
{
  "input": [
    {
      "successor": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "predecessor": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "delay": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2009_10::Model::FlowInput[] | a 向量，元素为 FlowInput structures. |

**响应（output）：**

```json
{
  "flowsResult": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `flowsResult` | Teamcenter::BusinessObject[] | A 向量，元素为 the new succesfully created flow 对象. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

#### 3.4.6 editLogicalAssignments（2009-10）

**接口路径：** `Manufacturing-2009-10-Model/editLogicalAssignments`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 编辑逻辑分配（Logical Assignment）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.editLogicalAssignments`

**请求（input）：**

```json
{
  "laEditVec": [
    {
      "laObj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "laAttributes": [
        {
          "name": "",
          "value": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `laEditVec` | Teamcenter::Soa::Manufacturing::_2009_10::Model::LogicalAssignmentData[] | 向量，元素为 对象 to edit. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.4.7 getResolvedNodesFromLA（2009-10）

**接口路径：** `Manufacturing-2009-10-Model/getResolvedNodesFromLA`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 从逻辑分配获取已解析节点。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.getResolvedNodesFromLA`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "laObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputObjects` | Teamcenter::Soa::Manufacturing::_2009_10::Model::ResolvedNodesInput[] | 输入 对象 for 其 to return resolved nodes. |

**响应（output）：**

```json
{
  "outResolvedNodes": [
    {
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "laResolvedNodes": [
        {
          "laObj": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "resolvedNodes": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `outResolvedNodes` | Teamcenter::Soa::Manufacturing::_2009_10::Model::ResolvedNodesOutput[] | All the resolved nodes of all 对象 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 对象 |

---

#### 3.4.8 removeFlow（2009-10）

**接口路径：** `Manufacturing-2009-10-Model/removeFlow`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 移除工艺流。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.removeFlow`

**请求（input）：**

```json
{
  "input": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::BusinessObject[] | a 向量，元素为 Flows to remove. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.4.9 resolveLogicalAssignments（2009-10）

**接口路径：** `Manufacturing-2009-10-Model/resolveLogicalAssignments`

**API 版本：** `2009-10`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 解析逻辑分配关系。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.Model.resolveLogicalAssignments`

**请求（input）：**

```json
{
  "laVec": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "resolveObjects": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "laResolveType": "",
      "recursive": ""
    }
  ],
  "externalSources": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `laVec` | Teamcenter::BusinessObject[] | 向量，元素为 Logical Assignment 对象 to resolve |
| `resolveObjects` | Teamcenter::Soa::Manufacturing::_2009_10::Model::ResolveData[] | 向量，元素为 对象 to resolve 对于每个 对象 the 服务 will resolve all its Logical Assignments |
| `externalSources` | Teamcenter::BusinessObject[] | 向量，元素为 loaded 产品结构s on 其 to run the resolve mechanism |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.4.10 getManufacturingPropretyDescs（2009-10）

**接口路径：** `Manufacturing-2009-10-ModelDefinitions/getManufacturingPropretyDescs`

**API 版本：** `2009-10`  
**Service：** `ModelDefinitions`  
**Library：** `Manufacturing`

**说明：** 获取制造属性描述定义。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.ModelDefinitions.getManufacturingPropretyDescs`

**请求（input）：**

```json
{
  "inputs": [
    {
      "typeName": "",
      "propNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Manufacturing::_2009_10::ModelDefinitions::PropDescInfo[] | - 向量，元素为 结构 of PropDescInfo with 类型 名称 and 属性 names 向量. |

**响应（output）：**

```json
{
  "inputTypeNameToPropDescOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputTypeNameToPropDescOutput` | Teamcenter::Soa::Manufacturing::_2009_10::ModelDefinitions::InputTypeNameToPropDescOutputMap | 映射，键值对为 输入 类型 名称 to PropertyDescriptor |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） 其 has 输出 tags as plain 对象 and 错误 in partialError |

---

#### 3.4.11 getValidRelationTypes（2009-10）

**接口路径：** `Manufacturing-2009-10-ModelDefinitions/getValidRelationTypes`

**API 版本：** `2009-10`  
**Service：** `ModelDefinitions`  
**Library：** `Manufacturing`

**说明：** 获取有效的关系类型列表。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.ModelDefinitions.getValidRelationTypes`

**请求（input）：**

```json
{
  "relationTypesInput": [
    {
      "sourceType": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "targetType": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `relationTypesInput` | Teamcenter::Soa::Manufacturing::_2009_10::ModelDefinitions::RelationTypesInput[] | 向量，元素为 source and target types pairs. |

**响应（output）：**

```json
{
  "relationTypesResults": [
    {
      "sourceType": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "targetType": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "validRelationTypes": [
        {
          "name": "",
          "displayName": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `relationTypesResults` | Teamcenter::Soa::Manufacturing::_2009_10::ModelDefinitions::RelationTypesOutput[] | Array of relation types results |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Exceptions from internal processing returned as PartialErrors |

---

#### 3.4.12 copyEBOPStructure（2009-10）

**接口路径：** `Manufacturing-2009-10-StructureManagement/copyEBOPStructure`

**API 版本：** `2009-10`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 复制 EBOP 结构。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureManagement.copyEBOPStructure`

**请求（input）：**

```json
{
  "newRoot": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "configuringEBOPWindow": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "workingWindow": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "copyRulesKey": "",
  "copyFutureEffectivity": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `newRoot` | Teamcenter::WorkspaceObject | The newly created rootobject under 其 the 结构 将 cloned. |
| `configuringEBOPWindow` | Teamcenter::BusinessObject | The window with source BOP(GBOP/PBOP) item as root. |
| `workingWindow` | Teamcenter::BusinessObject | 可选 window (the actual source window), from 其 the IncrementalChange Rev is picked up. In additi在 window settings like show unconfigured etc. are also picked up. |
| `copyRulesKey` | std::string | The 名称 的 preference 其 将 used for cloning rule to be used. |
| `copyFutureEffectivity` | bool | if true, future ICRevs 将 created appropriately, instead of all ICEs being cloned 到 currently active ICRev. Note that if this is true - it is expected that there is an currently selected ICRev 在 working window. |

**响应（output）：**

```json
{
  "createdICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "createdFutureICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData",
  "updatedObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `createdICRevs` | Teamcenter::WorkspaceObject[] | any newly created incremental change revisions |
| `createdFutureICRevs` | Teamcenter::WorkspaceObject[] | any newly created future Incremental Change Revisions. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | the updated item(root) and any 部分错误 returned here. |
| `updatedObject` | Teamcenter::WorkspaceObject | The updatedObject 其 is the ItemRevision（物料版本） 的 passed in item. |

---

#### 3.4.13 getStructureContextLines（2009-10）

**接口路径：** `Manufacturing-2009-10-StructureManagement/getStructureContextLines`

**API 版本：** `2009-10`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取结构上下文行数据。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureManagement.getStructureContextLines`

**请求（input）：**

```json
{
  "scList": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `scList` | Teamcenter::StructureContext[] | The 列表，元素为 StructureContexts for 其 toplines and selected lines are needed. |

**响应（output）：**

```json
{
  "topLines": {},
  "selectedLines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `topLines` | Teamcenter::Soa::Manufacturing::_2009_10::StructureManagement::StructureContextToLinesMap2 | 映射，键值对为 StructureContext to its toplines. 例如， 产品结构 and 工艺结构 top lines. |
| `selectedLines` | Teamcenter::Soa::Manufacturing::_2009_10::StructureManagement::StructureContextToLinesMap2 | 映射，键值对为 StructureContext to any selected child lines. Note: If the topline is selected this 映射 将 empty. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 结构 to capture any 部分错误. |

---

#### 3.4.14 pasteDuplicateStructure（2009-10）

**接口路径：** `Manufacturing-2009-10-StructureManagement/pasteDuplicateStructure`

**API 版本：** `2009-10`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 粘贴并复制制造结构（重复粘贴）。（存在 2009-10、2018-11 两个 API 版本）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureManagement.pasteDuplicateStructure`

**请求（input）：**

```json
{
  "srcLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "targetLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "copyRulesKey": "",
  "copyFutureEffectivity": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `srcLines` | Teamcenter::BusinessObject[] | 输入 src lines 其 need to be cloned under the targetline(s). All 的m 必须为 从 same 结构. |
| `targetLines` | Teamcenter::BusinessObject[] | the targetline(s) under 其 the clones 的 对象 underlying the srclines 将 created/pasted. These should be 从 same 结构. |
| `copyRulesKey` | std::string | 名称 的 preference that 将 used for cloning. |
| `copyFutureEffectivity` | bool | 标志 to indicate 是否 future effectivities are to be created. |

**响应（output）：**

```json
{
  "createdICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "createdFutureICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData",
  "newChildLines": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `createdICRevs` | Teamcenter::WorkspaceObject[] | any newly created Incremental Change Revisions. |
| `createdFutureICRevs` | Teamcenter::WorkspaceObject[] | any newly created future IC revs |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 returns the populated targetLines along with any 部分错误. |
| `newChildLines` | Teamcenter::Soa::Manufacturing::_2009_10::StructureManagement::LineToLinesMap | the 映射，键值对为 targetline and the newly created lines under it. |

---

#### 3.4.15 nextSearch（2009-10）

**接口路径：** `Manufacturing-2009-10-StructureSearch/nextSearch`

**API 版本：** `2009-10`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 获取下一批结构搜索结果。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureSearch.nextSearch`

**请求（input）：**

```json
{
  "searchCursor": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchCursor` | Teamcenter::BusinessObject | searchCursor |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "objectDone": "",
  "estimatedObjectsLeft": "",
  "percentComplete": "",
  "searchCursor": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "finished": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |
| `objects` | Teamcenter::BusinessObject[] | A batch of 对象 that satisfy the search criteria for this search |
| `objectDone` | int | The 数量为 对象 在 结构 that have been processed so far |
| `estimatedObjectsLeft` | int | An estimate 的 数量为 lines yet to be processed |
| `percentComplete` | double | percentComplete |
| `searchCursor` | Teamcenter::BusinessObject | Search cursor 对象 that holds the current state 的 search 在 BOM session |
| `finished` | bool | A boolean 值 其 当 'true' 指定 the search is finished |

---

#### 3.4.16 startSearch（2009-10）

**接口路径：** `Manufacturing-2009-10-StructureSearch/startSearch`

**API 版本：** `2009-10`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 启动结构搜索。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureSearch.startSearch`

**请求（input）：**

```json
{
  "scope": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "searchExpression": {
    "itemAndRevisionAttributeExpressions": [
      {
        "className": "",
        "attributeName": "",
        "attributeType": "BooleanType",
        "queryOperator": "Equal",
        "values": {
          "boolValues": [],
          "intValues": [],
          "doubleValues": [],
          "stringValues": [
            ""
          ],
          "dateValues": "0001-01-01T00:00:00",
          "tagValues": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      }
    ],
    "occurrenceNoteExpressions": [
      {
        "noteType": "",
        "queryOperator": "Equal",
        "values": [
          ""
        ]
      }
    ],
    "returnScopedSubTreesHit": "",
    "formAttributeExpressions": [
      {
        "isItemForm": "",
        "relationType": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "formType": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "attributeName": "",
        "attributeType": "BooleanType",
        "queryOperator": "Equal",
        "values": {
          "boolValues": [],
          "intValues": [],
          "doubleValues": [],
          "stringValues": [
            ""
          ],
          "dateValues": "0001-01-01T00:00:00",
          "tagValues": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      }
    ],
    "proximitySearchExpressions": [
      {
        "bomLines": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "distance": "",
        "includeChildBomLines": ""
      }
    ],
    "boxZoneExpressions": [
      {
        "searchBoxes": [
          {
            "xmin": "",
            "ymin": "",
            "zmin": "",
            "xmax": "",
            "ymax": "",
            "zmax": "",
            "transform": []
          }
        ],
        "boxOperator": "Inside"
      }
    ],
    "planeZoneExpressions": [
      {
        "planzeZone": {
          "xvalue": "",
          "yvalue": "",
          "zvalue": "",
          "displacement": ""
        },
        "planeZoneOperator": "PlaneAbove"
      }
    ],
    "savedQueryExpressions": [
      {
        "savedQuery": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "entries": [
          ""
        ],
        "values": [
          ""
        ]
      }
    ],
    "inClassQueryExpressions": [
      {
        "inClassClassNames": [
          ""
        ],
        "inClassAttributeIDs": [],
        "inClassAttributeValues": [
          ""
        ]
      }
    ],
    "sizeSearchExpression": {
      "largerThan": "",
      "diagonalLength": ""
    },
    "doTrushapeRefinement": ""
  },
  "mfgSearchCriteria": {
    "objectTypes": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "logicalDesignator": [
      {
        "name": "",
        "value": ""
      }
    ],
    "refinements": [
      {
        "refinements": [
          {
            "relatedScopes": [
              {
                "uid": "",
                "type": "",
                "className": ""
              }
            ],
            "relations": [
              {
                "relationName": "",
                "matchType": "NotApplicableMatch",
                "objectClass": ""
              }
            ]
          }
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `scope` | Teamcenter::BusinessObject[] | scope lines within 其 to search |
| `searchExpression` | Teamcenter::Soa::Manufacturing::_2009_10::StructureSearch::SearchExpressionSet | generic search expression |
| `mfgSearchCriteria` | Teamcenter::Soa::Manufacturing::_2009_10::StructureSearch::MFGSearchCriteria | The MFG addition search criteria |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "objectDone": "",
  "estimatedObjectsLeft": "",
  "percentComplete": "",
  "searchCursor": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "finished": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |
| `objects` | Teamcenter::BusinessObject[] | A batch of 对象 that satisfy the search criteria for this search |
| `objectDone` | int | The 数量为 对象 在 结构 that have been processed so far |
| `estimatedObjectsLeft` | int | An estimate 的 数量为 lines yet to be processed |
| `percentComplete` | double | percentComplete |
| `searchCursor` | Teamcenter::BusinessObject | Search cursor 对象 that holds the current state 的 search 在 BOM session |
| `finished` | bool | A boolean 值 其 当 'true' 指定 the search is finished |

---

#### 3.4.17 stopSearch（2009-10）

**接口路径：** `Manufacturing-2009-10-StructureSearch/stopSearch`

**API 版本：** `2009-10`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 停止结构搜索。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2009_10.StructureSearch.stopSearch`

**请求（input）：**

```json
{
  "searchCursor": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchCursor` | Teamcenter::BusinessObject | the search identifier |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "objectDone": "",
  "estimatedObjectsLeft": "",
  "percentComplete": "",
  "searchCursor": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "finished": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |
| `objects` | Teamcenter::BusinessObject[] | A batch of 对象 that satisfy the search criteria for this search |
| `objectDone` | int | The 数量为 对象 在 结构 that have been processed so far |
| `estimatedObjectsLeft` | int | An estimate 的 数量为 lines yet to be processed |
| `percentComplete` | double | percentComplete |
| `searchCursor` | Teamcenter::BusinessObject | Search cursor 对象 that holds the current state 的 search 在 BOM session |
| `finished` | bool | A boolean 值 其 当 'true' 指定 the search is finished |

---

### 3.5 API 版本 2010-09

**Service：** Core、ImportExport、TimeManagement  **操作数：** 7

#### 3.5.1 findNodeInContext（2010-09）

**接口路径：** `Manufacturing-2010-09-Core/findNodeInContext`

**API 版本：** `2010-09`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 在目标上下文中根据输入条件查找与选定节点相关的对象。（存在 2010-09、2013-05 两个 API 版本，接口定义可能不同）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.Core.findNodeInContext`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "nodes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "byIdOnly": "",
      "allContexts": "",
      "inContextLine": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2010_09::Core::FindNodeInContextInputInfo[] | 输入 struct. |

**响应（output）：**

```json
{
  "resultInfo": [
    {
      "clientID": "",
      "resultNodes": [
        {
          "foundNodes": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "originalNode": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `resultInfo` | Teamcenter::Soa::Manufacturing::_2010_09::Core::FoundNodesInfo[] | Infornation retrieves 对于每个 输入 struct that we looked for. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据. |

---

#### 3.5.2 getAffectedProperties（2010-09）

**接口路径：** `Manufacturing-2010-09-Core/getAffectedProperties`

**API 版本：** `2010-09`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 当工艺/操作中节点工期变更时，返回受影响依赖节点的运行时属性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.Core.getAffectedProperties`

**请求（input）：**

```json
{
  "arguments": [
    {
      "rootNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "changedNodes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "changedProperties": [
        ""
      ]
    }
  ],
  "requestedProperties": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arguments` | Teamcenter::Soa::Manufacturing::_2010_09::Core::GetAffectedPropertiesArg[] | A 列表，元素为 GetAffectedPropertiesChanges structures that describe the changes that have been made to a process or 操作 结构. |
| `requestedProperties` | std::string[] | The names 的 属性 that are to be retrieved. 在 first version only the 属性 that are processed by the Gantt application are accepted (Mfg0calc_duration, Mfg0calc_start_time, Mfg0calc_dur_start_time). |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.5.3 importManufaturingFeatures（2010-09）

**接口路径：** `Manufacturing-2010-09-ImportExport/importManufaturingFeatures`

**API 版本：** `2010-09`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 从 PLMXML 导入制造特征（早期版本，注意拼写 Manufaturing）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.ImportExport.importManufaturingFeatures`

**请求（input）：**

```json
{
  "input": {
    "fileName": "",
    "root": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2010_09::ImportExport::ImportInput | 输入 包含 PLMXML 文件 and the root 的 结构 to 其 the data should be imported. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileFullPath": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 |
| `logFileFullPath` | std::string | The full path 的 日志文件 (created by the import). |

---

#### 3.5.4 calculateCriticalPathEx（2010-09）

**接口路径：** `Manufacturing-2010-09-TimeManagement/calculateCriticalPathEx`

**API 版本：** `2010-09`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 扩展计算关键路径（含附加规则）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.TimeManagement.calculateCriticalPathEx`

**请求（input）：**

```json
{
  "roots": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "processLeafNodes": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `roots` | Teamcenter::BusinessObject[] | The 列表，元素为 MFG process or 操作 对象 the critical path is to be calculated for. |
| `processLeafNodes` | bool | A 标志 that determines 是否 to compute the path 从 leave nodes 的 process/操作 结构 or 从 direct children of a root 对象. |

**响应（output）：**

```json
{
  "results": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "components": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "duration": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2010_09::TimeManagement::CalculateCriticalPathResultEx[] | A 列表，元素为 CalculateCriticalPathResultEx structures 对于每个 path returned. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 包含 a 列表，元素为 错误 descriptions if the path computation has failed. |

---

#### 3.5.5 getActivityTimes（2010-09）

**接口路径：** `Manufacturing-2010-09-TimeManagement/getActivityTimes`

**API 版本：** `2010-09`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 获取活动的时间属性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.TimeManagement.getActivityTimes`

**请求（input）：**

```json
{
  "rootNodes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `rootNodes` | Teamcenter::BusinessObject[] | The root nodes 的 tree structures for 其 the activity times are to be computed. |

**响应（output）：**

```json
{
  "results": [
    {
      "rootNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "timePerCategoryMap": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2010_09::TimeManagement::GetActivityTimesResult[] | A 向量，元素为 GetActivityTimesResult structures that holds 对于每个 root node the 列表，元素为 activity times indexed by category. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This is a common data 结构 that is 用于 return Teamcenter model data from a 服务 request. This member 同时包含 服务 exceptions. |

---

#### 3.5.6 populateAllocatedTimeProperties（2010-09）

**接口路径：** `Manufacturing-2010-09-TimeManagement/populateAllocatedTimeProperties`

**API 版本：** `2010-09`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 填充已分配时间相关属性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.TimeManagement.populateAllocatedTimeProperties`

**请求（input）：**

```json
{
  "rootNodes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "propagateZeroValues": "",
  "stopLevel": "",
  "precedence": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `rootNodes` | Teamcenter::BusinessObject[] | 定义 the root nodes 的 trees to be updated. |
| `propagateZeroValues` | bool | If this parameter is false, the allocated time of a specific node is only overwritten if more detailed information is available at a lower level. This means that if a given node is not further detailed by any sub node, o… |
| `stopLevel` | int | If this parameter is greater than 0, the update will stop that 数量为 levels below the root node. This means that the root node itself 将 excluded 从 update if the 值 is 1; if it is 2, all child nodes with exception 的 root's d… |
| `precedence` | std::string[] | The precedence 向量 定义 how the allocated time of a leaf node is to be determined. Each entry must consist of one 的 值 'estimated_t即 'simulated_t即 'allocated_time' or 'analysis'. 在 case of 'estimated_time' or 'simulated_time… |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.5.7 updateTimeManagementProperties（2010-09）

**接口路径：** `Manufacturing-2010-09-TimeManagement/updateTimeManagementProperties`

**API 版本：** `2010-09`  
**Service：** `TimeManagement`  
**Library：** `Manufacturing`

**说明：** 更新时间管理相关属性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2010_09.TimeManagement.updateTimeManagementProperties`

**请求（input）：**

```json
{
  "rootNodes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "fieldNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `rootNodes` | Teamcenter::BusinessObject[] | The root nodes 的 tree structures for 其 the runtime 属性 are to be calculated. |
| `fieldNames` | std::string[] | The names 的 calculated fields to recompute. Currently the following fieldnames are accepted: Mfg0calc_duration, Mfg0calc_start_time, Mfg0calc_dur_start_time, bl_me_work_time and bl_me_duration. If the fieldName 向量 is emp… |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.6 API 版本 2011-06

**Service：** DataManagement、StructureManagement  **操作数：** 6

#### 3.6.1 closeContexts（2011-06）

**接口路径：** `Manufacturing-2011-06-DataManagement/closeContexts`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 关闭基础视图窗口（Context）及其关联的 OG 视图。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.DataManagement.closeContexts`

**请求（input）：**

```json
{
  "contexts": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `contexts` | Teamcenter::BusinessObject[] | A 向量 与 contexts (top lines 的 windows) to close |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.6.2 closeViews（2011-06）

**接口路径：** `Manufacturing-2011-06-DataManagement/closeViews`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 关闭已打开的 OG 视图窗口。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.DataManagement.closeViews`

**请求（input）：**

```json
{
  "structureContext": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "views": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `structureContext` | Teamcenter::BusinessObject | The 结构 context 包含 views. Can be NULL if not 使用 structire context. |
| `views` | Teamcenter::BusinessObject[] | A 向量 与 open views (top lines 的 OG windows) to close |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.6.3 openContexts（2011-06）

**接口路径：** `Manufacturing-2011-06-DataManagement/openContexts`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 在新建基础视图窗口中打开现有对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.DataManagement.openContexts`

**请求（input）：**

```json
{
  "input": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "openViews": "",
      "openAssociatedContexts": "",
      "contextSettings": {
        "type": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "compoundCreateInput": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2011_06::DataManagement::OpenContextInput[] | A 列表，元素为 OpenContextInput representing the 对象 to open |

**响应（output）：**

```json
{
  "output": [
    {
      "contexts": [
        {
          "context": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "views": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "structureContext": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "collaborationContext": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2011_06::DataManagement::ContextGroup[] | A 向量 with information 的 method 输出 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 操作 ServiceData（服务数据） |

---

#### 3.6.4 openViews（2011-06）

**接口路径：** `Manufacturing-2011-06-DataManagement/openViews`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 打开 OG 视图窗口。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.DataManagement.openViews`

**请求（input）：**

```json
{
  "context": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "structureContext": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "views": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `context` | Teamcenter::BusinessObject | The context (top line 的 base view window) for 其 the views 将 opened |
| `structureContext` | Teamcenter::BusinessObject | The 结构 context 包含 context. This can be null |
| `views` | Teamcenter::BusinessObject[] | A 向量 与 views to open |

**响应（output）：**

```json
{
  "views": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `views` | Teamcenter::BusinessObject[] | A 向量 与 opened views (the top lines 的 created OG windows) |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 操作 ServiceData（服务数据） |

---

#### 3.6.5 getReferenceContexts（2011-06）

**接口路径：** `Manufacturing-2011-06-StructureManagement/getReferenceContexts`

**API 版本：** `2011-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 获取引用上下文。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.StructureManagement.getReferenceContexts`

**请求（input）：**

```json
{
  "contexts": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `contexts` | Teamcenter::BusinessObject[] | 向量，元素为 输入 contexts |

**响应（output）：**

```json
{
  "refcontexts": [
    {
      "contextsarray": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `refcontexts` | Teamcenter::Soa::Manufacturing::_2011_06::StructureManagement::ContextsArray[] | 向量，元素为 vectors referenced contexts 根据 the order 从 输入 向量 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 will return 错误 only. No data 将 return via 服务数据. |

---

#### 3.6.6 setReferenceContexts（2011-06）

**接口路径：** `Manufacturing-2011-06-StructureManagement/setReferenceContexts`

**API 版本：** `2011-06`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 设置引用上下文。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2011_06.StructureManagement.setReferenceContexts`

**请求（input）：**

```json
{
  "input": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "addRefContexts": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "removeRefContexts": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "removeExistingRef": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2011_06::StructureManagement::ReferencedContexts[] | includes ReferencedContexts 结构 |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.7 API 版本 2012-02

**Service：** Constraints、DataManagement、IPAManagement、Model  **操作数：** 17

#### 3.7.1 getPrecedenceConstraintPaths（2012-02）

**接口路径：** `Manufacturing-2012-02-Constraints/getPrecedenceConstraintPaths`

**API 版本：** `2012-02`  
**Service：** `Constraints`  
**Library：** `Manufacturing`

**说明：** 获取给定起止操作/工艺之间的优先顺序约束路径。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Constraints.getPrecedenceConstraintPaths`

**请求（input）：**

```json
{
  "inputData": [
    {
      "startNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "endNode": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputData` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::GetPrecedenceConstraintPathsInputs[] | 输入 data 包含 列表，元素为 start and 终止操作 or 工艺行s. |

**响应（output）：**

```json
{
  "results": [
    {
      "paths": [
        {
          "components": [
            {
              "predecessor": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "constraint": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "constraintIsInherited": ""
            }
          ],
          "endNode": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::GetPrecedenceConstraintPathsResult[] | A 列表，元素为 result structures that conta在 paths 对于每个 起点与终点 node pair specfied 在 输入 structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 对象 对于 matching GetPrecedenceConstraintPathsInputs 结构. |

---

#### 3.7.2 getPrecedenceConstraints（2012-02）

**接口路径：** `Manufacturing-2012-02-Constraints/getPrecedenceConstraints`

**API 版本：** `2012-02`  
**Service：** `Constraints`  
**Library：** `Manufacturing`

**说明：** 获取指定对象的前驱与后继优先顺序约束（可配置遍历层级）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Constraints.getPrecedenceConstraints`

**请求（input）：**

```json
{
  "inputData": [
    {
      "predecessorLevel": "",
      "successorLevel": "",
      "inputObject": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputData` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::GetPrecedenceConstraintsIn[] | The 列表，元素为 输入 对象 (Mfg0BvrProcess / Mfg0BvrOperation) whose precedence constraints are to be fetched along 与 数量为 levels to be traversed 在 predecessor and successor chains. |

**响应（output）：**

```json
{
  "predecessorMap": {},
  "successorMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `predecessorMap` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::AdjacentObjectsMap | The 映射，键值对为 对象 到ir predecessors |
| `successorMap` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::AdjacentObjectsMap | The 映射，键值对为 对象 到ir successors |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 结构 |

---

#### 3.7.3 validateConstraintConsistency（2012-02）

**接口路径：** `Manufacturing-2012-02-Constraints/validateConstraintConsistency`

**API 版本：** `2012-02`  
**Service：** `Constraints`  
**Library：** `Manufacturing`

**说明：** 校验产品 BOP 或其子结构中的优先顺序约束是否一致。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Constraints.validateConstraintConsistency`

**请求（input）：**

```json
{
  "inputData": [
    {
      "constraintTypes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "rootNodes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputData` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::ValidateConstraintConsistencyInputs[] | A 向量，元素为 ValidateConstraintConsistencyInputs structures that 定义 one or multiple substructures to check. |

**响应（output）：**

```json
{
  "results": [
    {
      "errors": [
        {
          "constraintType": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "message": "",
          "objects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "constraints": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::ValidateConstraintConsistencyResult[] | The 列表，元素为 result structures that holds one entry 对于每个 输入 结构. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 对象 for this request. |

---

#### 3.7.4 validateProcessAreaAssignments（2012-02）

**接口路径：** `Manufacturing-2012-02-Constraints/validateProcessAreaAssignments`

**API 版本：** `2012-02`  
**Service：** `Constraints`  
**Library：** `Manufacturing`

**说明：** 校验产品 BOP 操作/工艺与工厂 BOP 工艺区域分配是否符合约束定义。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Constraints.validateProcessAreaAssignments`

**请求（input）：**

```json
{
  "inputData": [
    {
      "constraintTypes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "contextToValidate": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "contextOfConstraints": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "rootProcessAreas": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "maxErrors": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputData` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::ValidateProcessAreaAssignmentsInputs[] | A 向量，元素为 ValidateProcessAreaAssignmentsInputs structures that define the the Plant and 产品 BOPs and the 集合，元素为 nodes to validate 在 工厂 BOP. |

**响应（output）：**

```json
{
  "results": [
    {
      "errors": [
        {
          "constraintType": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "message": "",
          "objectsOfContextOfConstraint": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "objectsOfContextToValidate": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "processAreas": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "constraints": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2012_02::Constraints::ValidateProcessAreaAssignmentsResult[] | The 列表，元素为 result structures that holds one entry 对于每个 输入 结构. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 对象 for this request. |

---

#### 3.7.5 addAssociatedContexts（2012-02）

**接口路径：** `Manufacturing-2012-02-DataManagement/addAssociatedContexts`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 建立工厂 BOP 与产品 BOP 等对象之间的关联上下文。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.addAssociatedContexts`

**请求（input）：**

```json
{
  "input": [
    {
      "associateToContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "addedContexts": [
        {
          "context": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationName": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AddAssociationInput[] | 列表，元素为 AddAssociationInput BOM 行s 对于 contexts to be 关联. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.7.6 associateAndAllocateByPreview（2012-02）

**接口路径：** `Manufacturing-2012-02-DataManagement/associateAndAllocateByPreview`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 按预览结果执行关联与分配操作。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.associateAndAllocateByPreview`

**请求（input）：**

```json
{
  "input": {
    "sourceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "targetPlantBOPLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "referenceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    }
  },
  "allocationMap": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AssociateAndAllocateInput | 输入，用于指定 source, target and reference 对象. |
| `allocationMap` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AllocationMap | 映射，键值对为 allocations 从 source 结构 到 target 结构. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": {
    "ticket": "",
    "fileName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 将包含 部分错误, warnings and 错误, 若有. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::FileTicket | 文件票据 包含 UID and 文件 名称 对于 日志文件 为本命令生成. |

---

#### 3.7.7 automaticAllocatePreview（2012-02）

**接口路径：** `Manufacturing-2012-02-DataManagement/automaticAllocatePreview`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 自动分配预览，返回拟分配结果供确认。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.automaticAllocatePreview`

**请求（input）：**

```json
{
  "input": {
    "sourceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "targetPlantBOPLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "referenceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AssociateAndAllocateInput | 输入，用于指定 source, target and reference 对象. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "previewFileTicket": {
    "ticket": "",
    "fileName": ""
  },
  "allocationMap": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 将包含 部分错误, warnings and 错误, 若有. |
| `previewFileTicket` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::FileTicket | 文件票据 包含 UID and 文件 名称 对于 CSV 文件 generated for preview during this command. |
| `allocationMap` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AllocationMap | 映射，键值对为 allocations 从 source 结构 到 target 结构. |

---

#### 3.7.8 automaticAssociateAndAllocate（2012-02）

**接口路径：** `Manufacturing-2012-02-DataManagement/automaticAssociateAndAllocate`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 自动完成关联与分配。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.automaticAssociateAndAllocate`

**请求（input）：**

```json
{
  "input": {
    "sourceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "targetPlantBOPLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "referenceProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AssociateAndAllocateInput | 输入，用于指定 source, target and reference 对象. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": {
    "ticket": "",
    "fileName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 将包含 部分错误, warnings and 错误, 若有. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::FileTicket | 文件票据 包含 UID and 文件 名称 对于 日志文件 为本命令生成. |

---

#### 3.7.9 connectObjects（2012-02）

**接口路径：** `Manufacturing-2012-02-DataManagement/connectObjects`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 连接制造（MFG）节点，支持粘贴特殊场景下的数量与出现次数参数。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.connectObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "targetObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "sourceInfo": {
        "sourceObjects": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "relationType": "",
        "relationName": "",
        "additionalInfo": {
          "stringProps": {},
          "stringArrayProps": {},
          "dateProps": {},
          "dateArrayProps": {},
          "tagProps": {},
          "tagArrayProps": {},
          "doubleProps": {},
          "doubleArrayProps": {},
          "floatProps": {},
          "floatArrayProps": {},
          "intProps": {},
          "intArrayProps": {},
          "boolProps": {},
          "boolArrayProps": {}
        }
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::ConnectObjectsInputData[] | A 列表，元素为 ConnectInput BOM 行s 对于 nodes to connect |

**响应（output）：**

```json
{
  "newObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `newObjects` | Teamcenter::BusinessObject[] | new BOM 行s, created as a result of connection 操作 under the new target BOM 行s |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

#### 3.7.10 disconnectFromOrigin（2012-02）

**接口路径：** `Manufacturing-2012-02-DataManagement/disconnectFromOrigin`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 断开与源对象的链接关系。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.disconnectFromOrigin`

**请求（input）：**

```json
{
  "inputVector": [
    {
      "lineToDisconnect": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isRecursive": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputVector` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::DisconnectFromOriginInputData[] | 向量，元素为 DisconnectFromOriginInputData specifying the lines to be disconnected and 是否 the children are to be recursively disconnected too. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.7.11 getAssociatedContexts（2012-02）

**接口路径：** `Manufacturing-2012-02-DataManagement/getAssociatedContexts`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 获取对象已关联的上下文列表。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.DataManagement.getAssociatedContexts`

**请求（input）：**

```json
{
  "input": [
    {
      "associateToContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::GetAssociatedContextsInputData[] | 输入 |

**响应（output）：**

```json
{
  "output": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "associatedContextsInfo": [
        {
          "context": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationName": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::AssociateOutput[] | A 向量，元素为 BOM 行s 关联 到 输入 context |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 部分错误 mapped 到 客户端 ID |

---

#### 3.7.12 deleteFilteredIPA（2012-02）

**接口路径：** `Manufacturing-2012-02-IPAManagement/deleteFilteredIPA`

**API 版本：** `2012-02`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 删除筛选条件下的在制品装配数据。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.IPAManagement.deleteFilteredIPA`

**请求（input）：**

```json
{
  "input": [
    {
      "process": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isRecursive": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_02::IPAManagement::DeleteFilteredIPAInputInfo[] | 包含 information about deleting filtered IPAs. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.7.13 getFilteredIPAType（2012-02）

**接口路径：** `Manufacturing-2012-02-IPAManagement/getFilteredIPAType`

**API 版本：** `2012-02`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 获取筛选在制品装配的类型信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.IPAManagement.getFilteredIPAType`

**请求（input）：**

```json
{
  "processes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processes` | Teamcenter::BusinessObject[] | a 向量，元素为 processes. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "flat": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "nested": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "unset": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serive data |
| `flat` | Teamcenter::BusinessObject[] | a 向量，元素为 processes that their 工艺结构 already contain a flat FIPA. |
| `nested` | Teamcenter::BusinessObject[] | a 向量，元素为 processes that their 工艺结构 already 包含 a nested FIPA |
| `unset` | Teamcenter::BusinessObject[] | processes that their 工艺结构 doesn't contain any FIPA yet. |

---

#### 3.7.14 getCandidateToolsForToolRequirement（2012-02）

**接口路径：** `Manufacturing-2012-02-Model/getCandidateToolsForToolRequirement`

**API 版本：** `2012-02`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 获取满足刀具需求的候选刀具列表。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Model.getCandidateToolsForToolRequirement`

**请求（input）：**

```json
{
  "resolveObjects": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "trObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toolSource": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `resolveObjects` | Teamcenter::Soa::Manufacturing::_2012_02::Model::ToolRequirementInput[] | 输入 结构 specifying 操作. Tool Requirement for 其 candidate tools are to be fetched. And tool source from 其中 tools are to be fetched. |

**响应（output）：**

```json
{
  "candidateTools": [
    {
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tools": [
        {
          "trObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "toolObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `candidateTools` | Teamcenter::Soa::Manufacturing::_2012_02::Model::CandidateTool[] | 结构 with member as 操作 or Process and the candidate tools. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 将包含 warnings and 错误. 若有. |

---

#### 3.7.15 getToolRequirements（2012-02）

**接口路径：** `Manufacturing-2012-02-Model/getToolRequirements`

**API 版本：** `2012-02`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 获取刀具需求信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Model.getToolRequirements`

**请求（input）：**

```json
{
  "parentObject": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "toolRequirementStatus": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `parentObject` | Teamcenter::BusinessObject[] | 指定 the 操作 of 类型 Mfg0BvrOperation or Process of 类型 Mfg0BvrProcess. |
| `toolRequirementStatus` | std::string[] | 指定 the status 的 Tool requirement. The possible 值 are ALL & RESOLVED and UNRESOLVED. RESOLVED 指示 that the Tool Requirement is resolved against the Tool. This option is relevant only 对于 工厂 BOP 其中 it is allowed to resolve t… |

**响应（output）：**

```json
{
  "toolRequirements": [
    {
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toolRequirements": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `toolRequirements` | Teamcenter::Soa::Manufacturing::_2012_02::Model::ToolRequirementResult[] | 指定 the Tool Requirements. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 将包含 warnings and 错误. 若有. |

---

#### 3.7.16 resolveToolRequirement（2012-02）

**接口路径：** `Manufacturing-2012-02-Model/resolveToolRequirement`

**API 版本：** `2012-02`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 解析并匹配刀具需求。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Model.resolveToolRequirement`

**请求（input）：**

```json
{
  "resolveObjects": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "trObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toolObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toolSource": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `resolveObjects` | Teamcenter::Soa::Manufacturing::_2012_02::Model::ResolveDataInfo[] | 指定 the data 必需 for resolving the Tool requirement. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.7.17 updateFlows（2012-02）

**接口路径：** `Manufacturing-2012-02-Model/updateFlows`

**API 版本：** `2012-02`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 更新工艺流定义。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_02.Model.updateFlows`

**请求（input）：**

```json
{
  "input": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "isSubHierarchies": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::BusinessObject[] | Should be a 向量，元素为 BOM 行. This is a scope of update flow command. |
| `isSubHierarchies` | bool | If isSubHierarchies parameter is true, flows are recursively updated 对于所有 children. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.8 API 版本 2012-09

**Service：** DataManagement、Validation  **操作数：** 4

#### 3.8.1 applyConfigObjects（2012-09）

**接口路径：** `Manufacturing-2012-09-DataManagement/applyConfigObjects`

**API 版本：** `2012-09`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 应用配置对象到目标结构。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_09.DataManagement.applyConfigObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "configObj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_09::DataManagement::ApplyConfigInput[] | 输入参数s for applying configuration 对象 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.8.2 createOrUpdateConfigObjects（2012-09）

**接口路径：** `Manufacturing-2012-09-DataManagement/createOrUpdateConfigObjects`

**API 版本：** `2012-09`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 创建或更新制造配置对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_09.DataManagement.createOrUpdateConfigObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "data": {
        "type": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "compoundCreateInput": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      },
      "modifyObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "basedOn": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "internalConfigData": []
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_09::DataManagement::CreateConfigInput[] | 向量，元素为 CreateConfigInput 结构 其 包含 information for creating or updating context 对象. |

**响应（output）：**

```json
{
  "output": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "internalConfigData": []
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2012_09::DataManagement::CreateConfigOutput[] | 对象 of CreateConfigOutput. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 包括 部分错误. |

---

#### 3.8.3 executeValidations（2012-09）

**接口路径：** `Manufacturing-2012-09-Validation/executeValidations`

**API 版本：** `2012-09`  
**Service：** `Validation`  
**Library：** `Manufacturing`

**说明：** 对指定对象执行已注册的制造验证规则。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_09.Validation.executeValidations`

**请求（input）：**

```json
{
  "input": [
    {
      "root": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "validationChecks": [
        {
          "type": "",
          "library": "",
          "name": "",
          "func": "",
          "failAllOnError": ""
        }
      ]
    }
  ],
  "failAllOnError": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2012_09::Validation::ValidationCheckExecutionParam[] | Validation Check Execution Param |
| `failAllOnError` | bool | 是否 or not to fail all tests 当 错误 occurs on a specific validation check for a specific line or to continue. |

**响应（output）：**

```json
{
  "errors": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "validationErrors": [
        {
          "msgId": "",
          "msg": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "validationNoticeType": ""
        }
      ],
      "validationTest": {
        "type": "",
        "library": "",
        "name": "",
        "func": "",
        "failAllOnError": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `errors` | Teamcenter::Soa::Manufacturing::_2012_09::Validation::ValidationCheckExecutionErrors[] | 错误 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData（服务数据） member |

---

#### 3.8.4 getAllValidations（2012-09）

**接口路径：** `Manufacturing-2012-09-Validation/getAllValidations`

**API 版本：** `2012-09`  
**Service：** `Validation`  
**Library：** `Manufacturing`

**说明：** 获取所有可用的制造验证定义。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2012_09.Validation.getAllValidations`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "params": [
    {
      "type": "",
      "library": "",
      "name": "",
      "func": "",
      "failAllOnError": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `params` | Teamcenter::Soa::Manufacturing::_2012_09::Validation::ValidationCheckCallbackParam[] | params |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

### 3.9 API 版本 2013-05

**Service：** Core、DataManagement、ImportExport、IPAManagement、StructureManagement、StructureSearch、TimeWayPlan  **操作数：** 15

#### 3.9.1 findNodeInContext（2013-05）

**接口路径：** `Manufacturing-2013-05-Core/findNodeInContext`

**API 版本：** `2013-05`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 在目标上下文中根据输入条件查找与选定节点相关的对象。（存在 2010-09、2013-05 两个 API 版本，接口定义可能不同）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.Core.findNodeInContext`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "nodes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "byIdOnly": "",
      "allContexts": "",
      "inContextLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationTypes": [
        ""
      ],
      "relationDirection": "",
      "relationDepth": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::Core::FindNodeInContextInputInfo[] | 输入 struct |

**响应（output）：**

```json
{
  "resultInfo": [
    {
      "clientID": "",
      "resultNodes": [
        {
          "foundNodes": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "originalNode": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `resultInfo` | Teamcenter::Soa::Manufacturing::_2010_09::Core::FoundNodesInfo[] | Infornation retrieves 对于每个 输入 struct that we looked for. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据. |

---

#### 3.9.2 matchObjectsAgainstVariantRules（2013-05）

**接口路径：** `Manufacturing-2013-05-Core/matchObjectsAgainstVariantRules`

**API 版本：** `2013-05`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 将运行时对象与变型规则列表匹配，判断对象在各变型规则下是否配置可见。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.Core.matchObjectsAgainstVariantRules`

**请求（input）：**

```json
{
  "args": [
    {
      "objects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "variantRules": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `args` | Teamcenter::Soa::Manufacturing::_2013_05::Core::MatchObjectsAgainstVariantRulesArg[] | A 列表，元素为 structures, 其中 each entry describes a 列表，元素为 runtime 对象 and a 列表，元素为 变型规则 or product variants that are matched against each other. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "results": [
    {
      "matrix": {},
      "warnings": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 对象 for this request. |
| `results` | Teamcenter::Soa::Manufacturing::_2013_05::Core::MatchObjectsAgainstVariantRulesResult[] | A 列表，元素为 result structures; each entry corresponds to an entry 在 MatchObjectsAgainstVariantRulesArg 向量 passed 到 matchObjectsAgainstVariantRules 操作. |

---

#### 3.9.3 createAttachments（2013-05）

**接口路径：** `Manufacturing-2013-05-DataManagement/createAttachments`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 为业务对象创建附件对象（支持增量模式）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.DataManagement.createAttachments`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": "",
      "data": {
        "type": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "compoundCreateInput": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2009_10::DataManagement::CreateIn[] | A 列表，元素为 CreateIn 对象 representing the Create 输入 for 业务对象 to be created. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "objects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2009_10::DataManagement::CreateOut[] | 向量，元素为 输出 对象 representing 对象 that were created |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 包括 部分错误 that are mapped 到 客户端 ID |

---

#### 3.9.4 setAttributes（2013-05）

**接口路径：** `Manufacturing-2013-05-DataManagement/setAttributes`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 设置业务对象及其附加对象的属性值。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.DataManagement.setAttributes`

**请求（input）：**

```json
{
  "input": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attachedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attributeDetails": [
        {
          "attributeName": "",
          "attributeValueDetails": {
            "dataType": "",
            "boolAttributes": [],
            "charAttributes": "",
            "integerAttributes": [],
            "doubleAttributes": [],
            "stringAttributes": [
              ""
            ],
            "tagAttributes": [
              {
                "uid": "",
                "type": "",
                "className": ""
              }
            ],
            "dateAttributes": [
              "0001-01-01T00:00:00"
            ]
          }
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::DataManagement::ObjectAttributesInput[] | 输入 结构 包含 对象(s) to be edited and the details 的 属性 or relations 其 need to be edited. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.9.5 syncStudyAndSource（2013-05）

**接口路径：** `Manufacturing-2013-05-DataManagement/syncStudyAndSource`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 将仿真研究与源 BOP 结构同步，返回 FMS 文件信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.DataManagement.syncStudyAndSource`

**请求（input）：**

```json
{
  "input": [
    {
      "study": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "direction": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::DataManagement::SyncStudyInput[] | The Mfg0BvrStudy 对象 to synchronize and the direction to synchronize (to/从 study). |

**响应（output）：**

```json
{
  "logFileTicket": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `logFileTicket` | std::string | The fmd 票据 到 日志文件 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard 服务数据 |

---

#### 3.9.6 importManufacturingFeatures（2013-05）

**接口路径：** `Manufacturing-2013-05-ImportExport/importManufacturingFeatures`

**API 版本：** `2013-05`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 从 PLMXML 文件向目标产品结构导入制造特征（MFG）。（存在 2013-05、2015-10、2016-03 三个 API 版本）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.ImportExport.importManufacturingFeatures`

**请求（input）：**

```json
{
  "input": {
    "context": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "content": [
      {
        "fileName": "",
        "container": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "importMode": ""
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::ImportExport::AdvancedImportInput | 输入 for PLMXML import of 制造特征. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileName": "",
  "logFileTicket": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据.The 错误 conditions and the corresponding 错误 codes are as listed below. 200373 Import is tried to be done from an incomplete PLMXML 文件. 200374 The preference MEImportMFGsManufacturingFeatureIdAttributeName 不 have … |
| `logFileName` | std::string | The 名称 的 generated 日志文件. |
| `logFileTicket` | std::string | The FMS 票据 对于 transient 文件 that captures the log of import. |

---

#### 3.9.7 cleanIPATree（2013-05）

**接口路径：** `Manufacturing-2013-05-IPAManagement/cleanIPATree`

**API 版本：** `2013-05`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 从工艺结构中清理在制品装配（IPA）出现并删除相关对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.IPAManagement.cleanIPATree`

**请求（input）：**

```json
{
  "processWindow": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "forceCleanAll": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processWindow` | Teamcenter::BusinessObject | Window 的 工艺结构 包含 IPA that is to be deleted. |
| `forceCleanAll` | bool | This 标志 is 用于 forcefully delete all IPAs. This functionality is not supported currently. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "appPathRootWindows": [
    {
      "productWindowAppPathRoot": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "appPathRootType": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "logFileTicket": {
    "fileName": "",
    "fileTicket": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |
| `appPathRootWindows` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::AppPathRootWindowDetails[] | 列表，元素为 appearance windows deleted by the 操作. These windows corressponds to 产品结构s consumed 在 process strcuture to be cleaned. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::FileTicketDetails | The details 的 log 文件票据. |

---

#### 3.9.8 doesIPAExist（2013-05）

**接口路径：** `Manufacturing-2013-05-IPAManagement/doesIPAExist`

**API 版本：** `2013-05`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 检查指定工艺结构是否已存在在制品装配树。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.IPAManagement.doesIPAExist`

**请求（input）：**

```json
{
  "processWindow": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processWindow` | Teamcenter::BusinessObject | Window 的 工艺结构. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "isIPAExist": "",
  "configFileTicket": {
    "fileName": "",
    "fileTicket": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |
| `isIPAExist` | bool | The 标志，指示 是否 IPA tree exists 对于 工艺结构. |
| `configFileTicket` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::FileTicketDetails | The 票据 of configuration 文件. This 文件 is saved as an attachment 在 top-level process element on 其 the assembly tree was generated/updated. This 文件 包含 information about all the configured 产品结构s consumed 在 工艺结构. |

---

#### 3.9.9 generateIPATree（2013-05）

**接口路径：** `Manufacturing-2013-05-IPAManagement/generateIPATree`

**API 版本：** `2013-05`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 基于消耗件与工位信息生成在制品装配（IPA）树。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.IPAManagement.generateIPATree`

**请求（input）：**

```json
{
  "ipaInput": {
    "configDetails": {
      "processWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "ipaName": "",
      "occGrpType": "",
      "processTypes": [
        ""
      ],
      "consumptionOccTypes": [
        ""
      ],
      "effectivityDetails": {
        "effectivityEndItem": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "effectivityEndItemRev": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "effectivityUnitRange": "",
        "effectivityDateRange": ""
      }
    },
    "emailDetails": {
      "logFileName": "",
      "isLogFileNeeded": "",
      "mailToReceivers": [
        ""
      ],
      "mailCcReceivers": [
        ""
      ],
      "mailSubject": "",
      "mailMessage": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `ipaInput` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::IPATreeInput | All the details for IPA generation that includes the 名称 的 IPA, process types, consumption types, occurrence group 类型, effectivity, email notification details etc. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "productWindowAppPathRoot": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "appPathRootType": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "logFileTicket": {
    "fileName": "",
    "fileTicket": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |
| `productWindowAppPathRoot` | Teamcenter::BusinessObject | The appearance window 其 was created. |
| `appPathRootType` | Teamcenter::BusinessObject | The 类型 of appearance window 其 was created. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::FileTicketDetails | The details 的 log 文件票据. |

---

#### 3.9.10 localUpdateIPATree（2013-05）

**接口路径：** `Manufacturing-2013-05-IPAManagement/localUpdateIPATree`

**API 版本：** `2013-05`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 对在制品装配树执行本地更新（仅更新工作站相关 IPA）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.IPAManagement.localUpdateIPATree`

**请求（input）：**

```json
{
  "processLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `processLines` | Teamcenter::BusinessObject[] | 列表，元素为 processes 在 工艺结构 on 其 local update requested. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileticket": {
    "fileName": "",
    "fileTicket": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |
| `logFileticket` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::FileTicketDetails | The details about the log 文件票据. |

---

#### 3.9.11 updateIPATree（2013-05）

**接口路径：** `Manufacturing-2013-05-IPAManagement/updateIPATree`

**API 版本：** `2013-05`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 当工艺结构变更时更新已存在的在制品装配树。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.IPAManagement.updateIPATree`

**请求（input）：**

```json
{
  "ipaInput": {
    "configDetails": {
      "processWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "ipaName": "",
      "occGrpType": "",
      "processTypes": [
        ""
      ],
      "consumptionOccTypes": [
        ""
      ],
      "effectivityDetails": {
        "effectivityEndItem": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "effectivityEndItemRev": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "effectivityUnitRange": "",
        "effectivityDateRange": ""
      }
    },
    "emailDetails": {
      "logFileName": "",
      "isLogFileNeeded": "",
      "mailToReceivers": [
        ""
      ],
      "mailCcReceivers": [
        ""
      ],
      "mailSubject": "",
      "mailMessage": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `ipaInput` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::IPATreeInput | All the details for updating IPA that includes the 名称 的 IPA, process types, consumption types, occurrence group 类型, effectivity, email notification details etc. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "productWindowAppPathRoot": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "appPathRootType": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "logFileTicket": {
    "fileName": "",
    "fileTicket": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |
| `productWindowAppPathRoot` | Teamcenter::BusinessObject | The appearance window 其 was created. |
| `appPathRootType` | Teamcenter::BusinessObject | The 类型 of appearance window 其 was created. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2013_05::IPAManagement::FileTicketDetails | The details 的 log 文件票据. |

---

#### 3.9.12 findAffectedCCs（2013-05）

**接口路径：** `Manufacturing-2013-05-StructureManagement/findAffectedCCs`

**API 版本：** `2013-05`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 查找包含输入对象工艺路径的所有协同上下文（CC）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.StructureManagement.findAffectedCCs`

**请求（input）：**

```json
{
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `objects` | Teamcenter::WorkspaceObject[] | The items to find their 协同上下文s (as a reference). |

**响应（output）：**

```json
{
  "output": [
    {
      "affectedObjects": [
        {
          "queryObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "affectedCC": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2013_05::StructureManagement::FindAffectedCCsOutput[] | 输出 data includes the affected CCs and the items 其 is 与…相关 each CC. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 输出. |

---

#### 3.9.13 findStudies（2013-05）

**接口路径：** `Manufacturing-2013-05-StructureSearch/findStudies`

**API 版本：** `2013-05`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 查找引用给定工艺/操作对象的所有研究（Study）对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.StructureSearch.findStudies`

**请求（input）：**

```json
{
  "inputNodes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputNodes` | Teamcenter::BusinessObject[] | A 列表，元素为 业务对象 for 其 referencing studies should be searced (对象 of 类型 Mfg0BvrProcess or Mfg0BvrOperation). |

**响应（output）：**

```json
{
  "results": [
    {
      "listOfStudies": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2013_05::StructureSearch::FindStudiesResults[] | The found Mfg0BvrStudy 对象 对于每个 inputNodes Mfg0BvrProcess or Mfg0BvrOperation |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 |

---

#### 3.9.14 getTWPInformation（2013-05）

**接口路径：** `Manufacturing-2013-05-TimeWayPlan/getTWPInformation`

**API 版本：** `2013-05`  
**Service：** `TimeWayPlan`  
**Library：** `Manufacturing`

**说明：** 从工厂 BOP 获取时间路径计划（TWP）信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.TimeWayPlan.getTWPInformation`

**请求（input）：**

```json
{
  "input": {
    "requestedObjects": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "contextProductBOP": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "requiredData": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::TimeWayPlan::TwpInfoInput | 输入 结构 包含 对象(s) for 其 information is requ即 the 列表，元素为 string specifying what information is 必需 and the product 工艺清单（BOP） (BOP) context. The 对象 can be process station(s), 工艺行(s), process area(s), or 工厂 BOP. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "infoMap": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误 若有. |
| `infoMap` | Teamcenter::Soa::Manufacturing::_2013_05::TimeWayPlan::InformationMap | A 映射，键值对为 业务对象 for 其 TWP information is requested and its corresponding TWP information. |

---

#### 3.9.15 setProductImage（2013-05）

**接口路径：** `Manufacturing-2013-05-TimeWayPlan/setProductImage`

**API 版本：** `2013-05`  
**Service：** `TimeWayPlan`  
**Library：** `Manufacturing`

**说明：** 为时间路径计划对象设置产品图像。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_05.TimeWayPlan.setProductImage`

**请求（input）：**

```json
{
  "input": [
    {
      "targetObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "contextProductBOP": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "imageDataset": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_05::TimeWayPlan::ProductImageInfo[] | 输入 结构 包含 对象(s) for 其 product image is to be set, the 业务对象 的 dataset representing the image and the product 工艺清单（BOP）es (BOP) context. The 对象 can be process station(s), 工艺行(s), process area(s), or 工厂 BOP. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.10 API 版本 2013-12

**Service：** Model、ResourceManagement  **操作数：** 7

#### 3.10.1 computeAppearancePath（2013-12）

**接口路径：** `Manufacturing-2013-12-Model/computeAppearancePath`

**API 版本：** `2013-12`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 计算外观路径（Appearance Path）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.Model.computeAppearancePath`

**请求（input）：**

```json
{
  "input": {
    "parentObject": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "childPaths": [
      {
        "threadIDs": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2013_12::Model::AppearancePathInput | A 列表，元素为 AppearancePathInput that holds parent 对象 and a 列表，元素为 paths 对于每个 one. Each path 表示 a node for 其 we would like to get the 值 的 prorperties. |

**响应（output）：**

```json
{
  "results": [
    {
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childResults": [
        {
          "absOccUID": "",
          "apnUID": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `results` | Teamcenter::Soa::Manufacturing::_2013_12::Model::ComputeAppearancePathResult[] | Data 结构 that holds the results |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 包含ll the modified BO and the 错误 |

---

#### 3.10.2 getStepP21FileCounts（2013-12）

**接口路径：** `Manufacturing-2013-12-ResourceManagement/getStepP21FileCounts`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 获取 STEP P21 文件数量统计。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.getStepP21FileCounts`

**请求（input）：**

```json
{
  "classIDs": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classIDs` | std::string[] | The class IDs of specific vendor catalog classes. All products from this class and all child classes of this class 将 counted. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "countMap": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 |
| `countMap` | Teamcenter::Soa::Manufacturing::_2013_12::ResourceManagement::MapStringInt | A 映射，键值对为 class IDs for 其 the counts are requested and its corresponding counts. |

---

#### 3.10.3 getVendorCatalogInfo（2013-12）

**接口路径：** `Manufacturing-2013-12-ResourceManagement/getVendorCatalogInfo`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 获取供应商目录信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.getVendorCatalogInfo`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "catalogInfo": [
    {
      "vendorName": "",
      "vendorAcronym": "",
      "vendorCatalogVersion": "",
      "vendorCatalogLanguage": "",
      "vendorCatalogDescription": "",
      "vendorCatalogShortDescription": "",
      "vendorCatalogID": "",
      "vendorCatalogRootClassID": "",
      "vendorCatalogRootDir": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 |
| `catalogInfo` | Teamcenter::Soa::Manufacturing::_2013_12::ResourceManagement::CatalogInfo[] | The vendor catalog information |

---

#### 3.10.4 importStep3DModels（2013-12）

**接口路径：** `Manufacturing-2013-12-ResourceManagement/importStep3DModels`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 导入 STEP 三维模型。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.importStep3DModels`

**请求（input）：**

```json
{
  "icoIDs": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icoIDs` | std::string[] | The Classification 对象 (ICO) IDs identifying the tool component under 其 the graphics 将 imported. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.10.5 importStepP21Files（2013-12）

**接口路径：** `Manufacturing-2013-12-ResourceManagement/importStepP21Files`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 导入 STEP P21 文件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.importStepP21Files`

**请求（input）：**

```json
{
  "classID": "",
  "importOptions": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classID` | std::string | The class ID of a specific vendor catalog class. All catalog products from this class and all child classes of this class 将 imported. |
| `importOptions` | int | The import options allow to specify if (0) exisitng product data should be ignored and not be touched, (1) existing data should be overwritten (2) existing data should be overwritten only if the import 文件 is newer than t… |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": {
    "ticket": "",
    "fileName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2013_12::ResourceManagement::RMFileTicket | 票据 的 import 日志文件 |

---

#### 3.10.6 importVendorCatalogHierarchy（2013-12）

**接口路径：** `Manufacturing-2013-12-ResourceManagement/importVendorCatalogHierarchy`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 导入供应商目录层级结构。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.importVendorCatalogHierarchy`

**请求（input）：**

```json
{
  "vendorCatalogRootDir": "",
  "importOptions": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `vendorCatalogRootDir` | std::string | The root directory that 包含 GTC vendor catalog |
| `importOptions` | int | The import options allow you to control 是否 the catalog hierarchy will overwrite (1) existing classes or ignore (0) those classes and not import them. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": {
    "ticket": "",
    "fileName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 that can contain 错误 codes |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2013_12::ResourceManagement::RMFileTicket | 票据 的 import 日志文件 |

---

#### 3.10.7 updateNXToolAssemblies（2013-12）

**接口路径：** `Manufacturing-2013-12-ResourceManagement/updateNXToolAssemblies`

**API 版本：** `2013-12`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 更新 NX 刀具装配数据。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2013_12.ResourceManagement.updateNXToolAssemblies`

**请求（input）：**

```json
{
  "icoIDs": [
    ""
  ],
  "identifyCutAndNoCut": "",
  "generateSpinning": "",
  "setToolJunctions": "",
  "writePartAttributes": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icoIDs` | std::string[] | The Classification 对象 (ICO) IDs identifying the tool assemblies |
| `identifyCutAndNoCut` | bool | If true, the "Cut" and "NoCut" information 从 different tool components is taken and stored 在 assembly itself. |
| `generateSpinning` | bool | If true, the "Cut" and "NoCut" information 从 tool assembly is taken and the "Cut" and "NoCut" rotation spun. |
| `setToolJunctions` | bool | If true, the poition and orientation 的 tool tip and tool mount junctions are evaluated and set 在 assembly. |
| `writePartAttributes` | bool | If true, the X, Y and Z offset 值 的 tool are evaluated 基于 the tool tip and tool mount junctions. Those 值 are written 到 part 属性 在 part 文件 and can be mapped to Teamcenter. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.11 API 版本 2014-06

**Service：** DataManagement、ResourceManagement、StructureSearch  **操作数：** 6

#### 3.11.1 addOrRemoveAssociatedContexts（2014-06）

**接口路径：** `Manufacturing-2014-06-DataManagement/addOrRemoveAssociatedContexts`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 添加或移除各类关联上下文（由输入参数控制目标类型）。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.DataManagement.addOrRemoveAssociatedContexts`

**请求（input）：**

```json
{
  "input": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "addContext": [
        {
          "context": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationName": ""
        }
      ],
      "removeContext": [
        {
          "context": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationName": ""
        }
      ],
      "actionMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_06::DataManagement::AddOrRemoveContextsInfo[] | A target context , 列表，元素为 contexts to associate, 列表，元素为 contexts to remove and the parameters that governs the functionality. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.11.2 cloneAssemblyAndProcessObjects（2014-06）

**接口路径：** `Manufacturing-2014-06-DataManagement/cloneAssemblyAndProcessObjects`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 响应工程 BOM 变更，在制造 BOM 中克隆装配与工艺对象。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.DataManagement.cloneAssemblyAndProcessObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "sourceObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scopeSearchObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "sourceOccEff": "",
      "newCloneOccEff": "",
      "additionalInfo": {
        "stringProps": {},
        "stringArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {},
        "boolArrayProps": {}
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_06::DataManagement::CloneAssemblyInputData[] | 包含 source 对象 that should be cloned, target parent 对象 对于 cloned 对象 and additional parameters that govern the functionality. |

**响应（output）：**

```json
{
  "clonedObject": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clonedObject` | Teamcenter::BusinessObject | 业务对象 of new BOM 行 对象, created as a result of clone 操作 under the new target. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard 服务数据 |

---

#### 3.11.3 establishOriginLink（2014-06）

**接口路径：** `Manufacturing-2014-06-DataManagement/establishOriginLink`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 在工艺/操作之间建立源（Origin）链接。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.DataManagement.establishOriginLink`

**请求（input）：**

```json
{
  "input": {
    "inputObjects": [
      {
        "sourceObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "targetObjects": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    ],
    "criteria": [
      ""
    ],
    "considerHierarchy": "",
    "action": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_06::DataManagement::EstablishOriginLinkInfo | A 列表，元素为 a source and targets to be linked and the parameters that governs the functionality. |

**响应（output）：**

```json
{
  "candidates": [
    {
      "sourceObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "targetObjects": [
        {
          "targetObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "linkState": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData",
  "logFileTicket": {
    "ticket": "",
    "fileName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `candidates` | Teamcenter::Soa::Manufacturing::_2014_06::DataManagement::EstablishOriginLinkCandidates[] | The source and target 对象 与ir linked state. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData（服务数据） 包含 部分错误 若有. |
| `logFileTicket` | Teamcenter::Soa::Manufacturing::_2012_02::DataManagement::FileTicket | The 文件票据 包含 UID and 文件 名称 对于 日志文件 为本命令生成. |

---

#### 3.11.4 getProcessResourceRelatedInfo（2014-06）

**接口路径：** `Manufacturing-2014-06-DataManagement/getProcessResourceRelatedInfo`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 获取工艺资源相关工作内容信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.DataManagement.getProcessResourceRelatedInfo`

**请求（input）：**

```json
{
  "input": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "objectPreference": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::BusinessObject[] | 输入 包含 对象 for 其 process-resource 相关 information is 必需. The valid 对象 are BOM 行 在 context of 工厂 BOP 结构 as specified below - Mfg0BvrProcessLine - 工艺行 - Mfg0BvrProcessArea - Process area - Mfg0BvrProcessStation - Process stat… |
| `objectPreference` | std::string | 指定 the 对象 that response must return. The valid 值 are Process, 操作 and ProcessAndOperation denoting respectively that process of 类型 Mfg0BvrProcess, 操作 of 类型 Mfg0BvrOperation and both process and 操作 that are allocated to 工艺… |

**响应（output）：**

```json
{
  "infoMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `infoMap` | Teamcenter::Soa::Manufacturing::_2014_06::DataManagement::ProcResourceRelatedInfoMap | 映射，键值对为 BOM 行 对象 (业务对象/列表，元素为 业务对象). If the key is process area of 类型 Mfg0BvrProcessArea then 值 is 列表，元素为 工艺资源s of 类型 Mfg0BvrProcessResource that are defined under the process area and process/操作 of 类型 Mfg0BvrProcess/Mfg… |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误. |

---

#### 3.11.5 checkToolParameters（2014-06）

**接口路径：** `Manufacturing-2014-06-ResourceManagement/checkToolParameters`

**API 版本：** `2014-06`  
**Service：** `ResourceManagement`  
**Library：** `Manufacturing`

**说明：** 检查刀具是否具备生成三维图形或使用所需的属性值。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.ResourceManagement.checkToolParameters`

**请求（input）：**

```json
{
  "icoIds": [
    ""
  ],
  "checkLevel": "",
  "checkTypes": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icoIds` | std::string[] | A 列表，元素为 classification 对象 IDs that identify the 列表，元素为 tools to be checked. |
| `checkLevel` | std::string | The level of checks to be performed: "none", "preferred", "错误", "all". If the provided 值 is "preferred", the 值 的 single-值 preference MRMToolCheckLevel 将 used. |
| `checkTypes` | std::string[] | A 列表，元素为 the types of checks to be performed: "preferred", "NX CAM", "MRL PFT". If the only provided 值 is "preferred", the 值 的 multi-值 preference MRMToolCheckType 将 be used. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "checkResults": [
    {
      "icoId": "",
      "status": "",
      "report": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 that can contain 错误 descriptions. |
| `checkResults` | Teamcenter::Soa::Manufacturing::_2014_06::ResourceManagement::CheckResult[] | A 列表 containing a check result 对于每个 tool. |

---

#### 3.11.6 searchConnectedLines（2014-06）

**接口路径：** `Manufacturing-2014-06-StructureSearch/searchConnectedLines`

**API 版本：** `2014-06`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 搜索与输入连接 BOM 行相连的所有 BOM 行。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_06.StructureSearch.searchConnectedLines`

**请求（input）：**

```json
{
  "inputConnLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputConnLines` | Teamcenter::BusinessObject[] | 输入 BOM 行 对象 whose connected to information needs to be found. |

**响应（output）：**

```json
{
  "output": [
    {
      "connectionLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "connectedLines": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Manufacturing::_2014_06::StructureSearch::SrchConnectedLinesOutput[] | 列表，元素为 对象 containing 输入 connection and connected BOM 行s. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard 服务数据. |

---

### 3.12 API 版本 2014-12

**Service：** IPAManagement、Model、StructureSearch、Validation  **操作数：** 8

#### 3.12.1 findAndRepopulateDynamicIPAs（2014-12）

**接口路径：** `Manufacturing-2014-12-IPAManagement/findAndRepopulateDynamicIPAs`

**API 版本：** `2014-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 查找并重新填充动态在制品装配。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.IPAManagement.findAndRepopulateDynamicIPAs`

**请求（input）：**

```json
{
  "inputBOPLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputBOPLines` | Teamcenter::BusinessObject[] | 本操作 recieves a 列表，元素为 ImanItemBOPLine as an 输入. (The 类型 of 的 bop line 对象 can be either Mfg0BvrProcess or Mfg0BvrShdStudy). |

**响应（output）：**

```json
{
  "dynamicIPAsData": [
    {
      "bopLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "dynamicIPAsData": [
        {
          "dynamicIPA": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "consumedParts": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `dynamicIPAsData` | Teamcenter::Soa::Manufacturing::_2014_12::IPAManagement::DynamicIPAsOfLine[] | A 列表，元素为 DynamicIPAsOfLine. Each element 在 列表 包含 data about all the dynamic IPAs of a single line. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. The following 部分错误 被返回 in case invalid parameters are passed 到 操作:- 25439 :- The 类型 的 given 对象 is not supported. 25440 :- The given 对象 doesn&apos;t have any dynamic IPA. |

---

#### 3.12.2 repopulateDynamicIPAs（2014-12）

**接口路径：** `Manufacturing-2014-12-IPAManagement/repopulateDynamicIPAs`

**API 版本：** `2014-12`  
**Service：** `IPAManagement`  
**Library：** `Manufacturing`

**说明：** 重新填充动态在制品装配数据。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.IPAManagement.repopulateDynamicIPAs`

**请求（input）：**

```json
{
  "input": {
    "topLine": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "ids": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_12::IPAManagement::RepopulateDynamicIPAsData | The top BOPLine and a 列表，元素为 absolute occurrence IDs of processes (Mfg0BvrProcess) or shared studies (Mfg0BvrShdStudy). |

**响应（output）：**

```json
{
  "dynamicIPAsData": [
    {
      "bopLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "dynamicIPAsInfo": [
        {
          "dynamicIPA": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "consumedParts": [
            {
              "consumedPart": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "referencedPart": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "occInformation": {}
            }
          ],
          "occInformation": {}
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `dynamicIPAsData` | Teamcenter::Soa::Manufacturing::_2014_12::IPAManagement::DynamicIPAsProcLineInfo[] | 列表，元素为 data containing information about 工艺行s (Mfg0BvrProcess) and their respective Dynamic IPA nodes (Mfg0BvrDynamicIPA). |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard 服务数据. |

---

#### 3.12.3 validateScopeFlowsConsistency（2014-12）

**接口路径：** `Manufacturing-2014-12-Model/validateScopeFlowsConsistency`

**API 版本：** `2014-12`  
**Service：** `Model`  
**Library：** `Manufacturing`

**说明：** 校验作用域内工艺流的一致性。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.Model.validateScopeFlowsConsistency`

**请求（input）：**

```json
{
  "rootLines": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `rootLines` | Teamcenter::BusinessObject[] | 列表，元素为 业务对象 representing BOP line 对象 (the 类型 的 bop line 对象 can be either Mfg0BvrProcess or Mfg0BvrOperation) |

**响应（output）：**

```json
{
  "data": [
    {
      "isConsistent": "",
      "cycles": [
        {
          "objects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "flows": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ]
    }
  ],
  "fileTicket": {
    "ticket": "",
    "fileName": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `data` | Teamcenter::Soa::Manufacturing::_2014_12::Model::ConsistencyData[] | A 列表，元素为 ConsistencyData. Each element 在 列表 包含 indication 是否 the data is consistent and information about the in-cosistencies (cycles), if found. |
| `fileTicket` | Teamcenter::Soa::Manufacturing::_2014_12::Model::FileTicket | An FMS 文件 票据. The 文件 包含 report about the cycles found by the algorithm. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据. |

---

#### 3.12.4 createOrUpdateAssignmentRecipe（2014-12）

**接口路径：** `Manufacturing-2014-12-StructureSearch/createOrUpdateAssignmentRecipe`

**API 版本：** `2014-12`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 创建或更新分配方案。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.StructureSearch.createOrUpdateAssignmentRecipe`

**请求（input）：**

```json
{
  "input": [
    {
      "name": "",
      "recipeAnchorOrRecipe": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "searchContextSC": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "additionalSearchCriteria": {
        "objectTypes": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "logicalDesignator": {
          "name": "",
          "value": ""
        },
        "refinements": [
          {
            "refinements": [
              {
                "relatedScopes": [
                  {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                ],
                "relations": [
                  {
                    "relationName": "",
                    "matchType": "NotApplicableMatch",
                    "objectClass": ""
                  }
                ]
              }
            ]
          }
        ],
        "absoccAttributes": [
          {
            "name": "",
            "value": ""
          }
        ]
      },
      "appKey": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_12::StructureSearch::CreateOrUpdateAssignmentRecipeInputElem[] | A 列表，元素为 输入 elements specifying the details 的 recipe to be created and 附加到 a given node. |

**响应（output）：**

```json
{
  "info": [
    {
      "intMap": {},
      "dblMap": {},
      "strMap": {},
      "objMap": {},
      "dateMap": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `info` | Teamcenter::Soa::Manufacturing::_2014_12::StructureSearch::AdditionalInfo[] | A 列表，元素为 AdditionalInfo structures. If recipe 被创建, the objMap member will have the key "CreatedObject" 与 值 being the Mfg0MEMBOMRecipe 对象. If recipe 被更新 the objMap member will have the key "UpdatedObject". The strMap memb… |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） |

---

#### 3.12.5 deleteAssignmentRecipes（2014-12）

**接口路径：** `Manufacturing-2014-12-StructureSearch/deleteAssignmentRecipes`

**API 版本：** `2014-12`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 删除分配方案。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.StructureSearch.deleteAssignmentRecipes`

**请求（input）：**

```json
{
  "recipes": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "recipeAnchors": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "contextForRemovingResolvedObjs": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "appKey": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `recipes` | Teamcenter::BusinessObject[] | A 列表，元素为 Mfg0MEMBOMRecipe 对象 to be deleted. |
| `recipeAnchors` | Teamcenter::BusinessObject[] | A 列表，元素为 BOM 行 对象 for 其 recipes are to be deleted. |
| `contextForRemovingResolvedObjs` | Teamcenter::BusinessObject | An 可选 BOMWindow 对象 to indicate resolved lines are to be deleted too. |
| `appKey` | std::string | The 名称 的 Application to identify the resolver 在 服务器. Currently, only allowed 值 is Mfg0AssignmentRecipe. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.12.6 getAssignmentRecipes（2014-12）

**接口路径：** `Manufacturing-2014-12-StructureSearch/getAssignmentRecipes`

**API 版本：** `2014-12`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 获取分配方案（Assignment Recipe）列表。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.StructureSearch.getAssignmentRecipes`

**请求（input）：**

```json
{
  "recipeAnchors": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "recipeNames": [
    ""
  ],
  "appKey": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `recipeAnchors` | Teamcenter::BusinessObject[] | A 列表，元素为 BOM 行 对象 for 其 recipes are to be obtained. |
| `recipeNames` | std::string[] | An 可选 列表，元素为 recipeNames to search for recipes under the specified recipeAnchors. |
| `appKey` | std::string | The 名称 的 Application to identify the resolved 在 服务器. Currently, only allowed 值 is Mfg0AssignmentRecipe. |

**响应（output）：**

```json
{
  "info": [
    {
      "intMap": {},
      "dblMap": {},
      "strMap": {},
      "objMap": {},
      "dateMap": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `info` | Teamcenter::Soa::Manufacturing::_2014_12::StructureSearch::AdditionalInfo[] | A 列表，元素为 AdditionInfo structures. If the recipe is found objMap member will have the key "Recipe" and the Mfg0MEMBOMRecipe 对象 as the 值, the strMap will have "名称" for key and the corresponding names 的 rec即 the objMap will… |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 capturing 部分错误 使用 输入 array 索引 as 客户端 ID. |

---

#### 3.12.7 resolveAssignmentRecipe（2014-12）

**接口路径：** `Manufacturing-2014-12-StructureSearch/resolveAssignmentRecipe`

**API 版本：** `2014-12`  
**Service：** `StructureSearch`  
**Library：** `Manufacturing`

**说明：** 解析并应用分配方案。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.StructureSearch.resolveAssignmentRecipe`

**请求（input）：**

```json
{
  "input": [
    {
      "recipeAnchor": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "recipeObjs": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "searchScopes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "reResolve": "",
      "removePreviouslyResolved": "",
      "recursive": "",
      "generateLog": "",
      "appKey": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2014_12::StructureSearch::ResolveAssignmentRecipeInputElement[] | A 列表，元素为 ResolveAssignmentRecipeInputElement structures each detailing the node on 其 the recipe is to be resolved. |

**响应（output）：**

```json
{
  "info": [
    {
      "intMap": {},
      "dblMap": {},
      "strMap": {},
      "objMap": {},
      "dateMap": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `info` | Teamcenter::Soa::Manufacturing::_2014_12::StructureSearch::AdditionalInfo[] | A 列表，元素为 AdditionInfo structures. The names 的 resolved recipes appear under the "Recipe" key of strMap. Each 值 in this strMap is a further key into objMap and the 值 for those are the resolved BOM 行 对象. Any BOM 行 对象 that … |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData（服务数据） to caputre 部分错误. |

---

#### 3.12.8 getMaturityReport（2014-12）

**接口路径：** `Manufacturing-2014-12-Validation/getMaturityReport`

**API 版本：** `2014-12`  
**Service：** `Validation`  
**Library：** `Manufacturing`

**说明：** 获取制造成熟度（Maturity）报告。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2014_12.Validation.getMaturityReport`

**请求（input）：**

```json
{
  "maturityReportRequest": {
    "inputObjects": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "selectedRules": {},
    "supportingInformation": [
      {
        "propertyName": "",
        "value": [
          ""
        ],
        "dataType": ""
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `maturityReportRequest` | Teamcenter::Soa::Manufacturing::_2014_12::Validation::MaturityReportRequest | 输入 到 getMaturityReport 操作. It has the below parameters - inputObjects - 输入 包含 BOM 行 其 acts as a scope for maturity check. The 对象 在 hierarchy 的 scope are candidates 对于 check. ruleList - The 列表，元素为 rules for 其 maturity is … |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "maturityResult": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误. |
| `maturityResult` | Teamcenter::Soa::Manufacturing::_2014_12::Validation::MaturityResult | The result of getMaturityData 操作, 包含 BusinessObjects and their maturity data. |

---

### 3.13 API 版本 2015-03

**Service：** StructureManagement  **操作数：** 1

#### 3.13.1 moveAndResequenceNodes（2015-03）

**接口路径：** `Manufacturing-2015-03-StructureManagement/moveAndResequenceNodes`

**API 版本：** `2015-03`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 移动并重新排序制造结构节点。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2015_03.StructureManagement.moveAndResequenceNodes`

**请求（input）：**

```json
{
  "inputList": [
    {
      "sourceNodes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "targetNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "predecessor": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isDroppedOnTarget": "",
      "findNumberContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isPasteDuplicate": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputList` | Teamcenter::Soa::Manufacturing::_2015_03::StructureManagement::MoveAndResequenceParameter[] | The 列表，元素为 moveAndResequenceParameter 结构. Each 结构 指定 the nodes to be moved, their target, 是否 dropped 在 target, context 基于 其 find 编号 to be decided and 是否 to clone or move the nodes 到 new target. |

**响应（output）：**

```json
{
  "createdICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "createdFutureICRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "newChildLines": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `createdICRevs` | Teamcenter::WorkspaceObject[] | 列表，元素为 newly created Incremental Change (IC) revisions. |
| `createdFutureICRevs` | Teamcenter::WorkspaceObject[] | 列表，元素为 newly created future IC revisions. |
| `newChildLines` | Teamcenter::Soa::Manufacturing::_2015_03::StructureManagement::TargetToNewChildLinesMap | The 映射 (BOM 行, 列表，元素为 BOM 行) of target BOM 行 and the newly created or moved BOM 行 对象 under it. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误. |

---

### 3.14 API 版本 2015-10

**Service：** ImportExport、StructureManagement  **操作数：** 2

#### 3.14.1 importManufacturingFeatures（2015-10）

**接口路径：** `Manufacturing-2015-10-ImportExport/importManufacturingFeatures`

**API 版本：** `2015-10`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 从 PLMXML 文件向目标产品结构导入制造特征（MFG）。（存在 2013-05、2015-10、2016-03 三个 API 版本）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2015_10.ImportExport.importManufacturingFeatures`

**请求（input）：**

```json
{
  "input": {
    "context": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "content": [
      {
        "xmlFileTicket": "",
        "container": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "importMode": "",
        "nameRefFileTickets": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2015_10::ImportExport::ImportManufaturingFeaturesInput | 输入 for import manufaturing features. |

**响应（output）：**

```json
{
  "logFileName": "",
  "logFileTicket": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `logFileName` | std::string | The 名称 的 generated 日志文件. |
| `logFileTicket` | std::string | The FMS 票据 的 日志文件. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |

---

#### 3.14.2 createCollabPlanningContext（2015-10）

**接口路径：** `Manufacturing-2015-10-StructureManagement/createCollabPlanningContext`

**API 版本：** `2015-10`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 创建协同规划上下文（CPC）并封装输入结构。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2015_10.StructureManagement.createCollabPlanningContext`

**请求（input）：**

```json
{
  "cpcInput": {
    "cloningStructsInfo": [
      {
        "newName": "",
        "newDescription": "",
        "newId": "",
        "newRevId": "",
        "scopes": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "cloningRule": "",
        "cloningParams": {}
      }
    ],
    "releaseStatus": "",
    "effectivityInfo": {
      "endItem": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "endItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "unitRangeText": "",
      "dateRange": [
        "0001-01-01T00:00:00"
      ],
      "openEndedStatus": ""
    },
    "originalCCUid": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "cpcName": "",
    "cpcDesc": "",
    "refStructures": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `cpcInput` | Teamcenter::Soa::Manufacturing::_2015_10::StructureManagement::CreateCPCInputInfo | 输入 到 服务 is a 结构 其 包含 a 列表，元素为 BOM 行 对象 that are to be cloned and\or referred, cloning information, 名称 and description of new CPC. |

**响应（output）：**

```json
{
  "cpcObject": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `cpcObject` | Teamcenter::BusinessObject | The created CPC 对象. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 |

---

### 3.15 API 版本 2016-03

**Service：** ImportExport  **操作数：** 2

#### 3.15.1 exportToBriefcase（2016-03）

**接口路径：** `Manufacturing-2016-03-ImportExport/exportToBriefcase`

**API 版本：** `2016-03`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 将制造数据导出到 Briefcase。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2016_03.ImportExport.exportToBriefcase`

**请求（input）：**

```json
{
  "reason": "",
  "sites": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "transferOptionSet": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "optionNameAndValues": {},
  "sessionOptionNamesAndValues": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `reason` | std::string | The reason 对于 export, the size is limited to 240 characters. This can be blank. |
| `sites` | Teamcenter::BusinessObject[] | The destination s即 only one site is supported as of now. The site should be marked as offline 在 Organization application in Teamcenter to perform a briefcase export. |
| `objects` | Teamcenter::BusinessObject[] | 列表，元素为 对象 to be exported 例如 CC, BOM 行. |
| `transferOptionSet` | Teamcenter::BusinessObject | A reference 到 TransferOptionSet 对象, this 对象 holds the 列表，元素为 options and their 默认 值 其 can influence the contents 的 exported briefcase. Please refer the documentation 的 PLM XML Export Import administration tool for more d… |
| `optionNameAndValues` | Teamcenter::Soa::Manufacturing::_2016_03::ImportExport::NamesAndValuesMap | A 映射 (string, string) 的 options names and 值. This 列表 overrides the 值 的 transferOptionSet. 例如， there is an option in TransferOptionSet, 其 is 用于 control 是否 to export configured assembly. The 默认 值 在 TransferOptionSet is fal… |
| `sessionOptionNamesAndValues` | Teamcenter::Soa::Manufacturing::_2016_03::ImportExport::NamesAndValuesMap | A 映射 (string, string) of all the session option names (options 其 are not part 的 transferOptionSet) and 值. Please refer the documentation 的 PLM XML Export Import administration tool for more details. Few 的 options are lis… |

**响应（output）：**

```json
{
  "briefcaseFileFMSTicket": "",
  "fileTickets": [
    ""
  ],
  "messageIds": [
    ""
  ],
  "briefcaseDataSet": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `briefcaseFileFMSTicket` | std::string | FMS 票据 的 briefcase 文件, 其 can be 用于 download the briefcase 文件 from 服务器 to 客户端. |
| `fileTickets` | std::string[] | To represent a 文件票据 and its original 文件 名称. |
| `messageIds` | std::string[] | 列表，元素为 message IDs. |
| `briefcaseDataSet` | Teamcenter::BusinessObject | A 业务对象 of Dataset 其 includes the out briefcase 文件 in its namedReference. After export, a new Dataset 将 created. The exported briefcase 文件 将 added 到 new Dataset. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 包含 列表，元素为 created or modified 对象 and also the 部分错误 in case of failure conditions. |

---

#### 3.15.2 importManufacturingFeatures（2016-03）

**接口路径：** `Manufacturing-2016-03-ImportExport/importManufacturingFeatures`

**API 版本：** `2016-03`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 从 PLMXML 文件向目标产品结构导入制造特征（MFG）。（存在 2013-05、2015-10、2016-03 三个 API 版本）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2016_03.ImportExport.importManufacturingFeatures`

**请求（input）：**

```json
{
  "input": {
    "context": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "content": [
      {
        "xmlFileTicket": "",
        "scope": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "container": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "importMode": "",
        "nameRefFileTickets": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2016_03::ImportExport::ImportManufaturingFeaturesInput | 输入 for import manufaturing features. |

**响应（output）：**

```json
{
  "logFileName": "",
  "logFileTicket": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `logFileName` | std::string | The 名称 的 generated 日志文件. |
| `logFileTicket` | std::string | The FMS 票据 的 日志文件. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据. |

---

### 3.16 API 版本 2017-05

**Service：** ImportExport、Validation  **操作数：** 2

#### 3.16.1 importFromBriefcase（2017-05）

**接口路径：** `Manufacturing-2017-05-ImportExport/importFromBriefcase`

**API 版本：** `2017-05`  
**Service：** `ImportExport`  
**Library：** `Manufacturing`

**说明：** 从 Briefcase 导入制造数据。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_05.ImportExport.importFromBriefcase`

**请求（input）：**

```json
{
  "fmsTicket": "",
  "optionSetTag": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "optionNamesAndValues": {},
  "sessionOptionAndValues": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `fmsTicket` | std::string | The FMS 文件 票据 对于 briefcase 文件, the 文件 should be uploaded 到 服务器 before calling 本操作. |
| `optionSetTag` | Teamcenter::BusinessObject | A reference 到 TransferOptionSet 对象, this 对象 holds the 列表，元素为 options and their 默认 值 其 can influence importing briefcase. |
| `optionNamesAndValues` | Teamcenter::Soa::Manufacturing::_2017_05::ImportExport::NamesAndValues | A 列表，元素为 all the option set containing option names and 值. This 列表 overrides the 值 从 optionSetTag. For example: For option opt_imp_XXX in TransferOptionSet, the 默认值为 false. It can be overridden by adding the option with … |
| `sessionOptionAndValues` | Teamcenter::Soa::Manufacturing::_2017_05::ImportExport::NamesAndValues | A 列表，元素为 all the session option names (options 其 are not part 的 option set) and 值. For example: A session option modified_objects_only 指定 是否 to import modified 对象. |

**响应（output）：**

```json
{
  "logFileFMSTicket": "",
  "errorFileFMSTicket": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `logFileFMSTicket` | std::string | FMS 票据 的 import 日志文件, 其 can be 用于 download the import 日志文件 from 服务器 to 客户端. |
| `errorFileFMSTicket` | std::string | FMS 票据 的 import 错误 文件, 其 can be 用于 download the import 错误 文件 from 服务器 to 客户端. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据 包含 列表，元素为 created or modified 对象 and also the 部分错误 in case of failure conditions. |

---

#### 3.16.2 getAllRegisteredCallbacks（2017-05）

**接口路径：** `Manufacturing-2017-05-Validation/getAllRegisteredCallbacks`

**API 版本：** `2017-05`  
**Service：** `Validation`  
**Library：** `Manufacturing`

**说明：** 获取所有已注册的验证回调。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_05.Validation.getAllRegisteredCallbacks`

**请求（input）：**

```json
{
  "callbackType": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `callbackType` | std::string | The 类型 of customized registered callback functions to retrieve. |

**响应（output）：**

```json
{
  "parameters": [
    {
      "type": "",
      "library": "",
      "name": "",
      "functionName": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `parameters` | Teamcenter::Soa::Manufacturing::_2017_05::Validation::RegisteredCallbackParam[] | The registered callback functions details for 给定输入 类型. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData（服务数据） member. |

---

### 3.17 API 版本 2017-11

**Service：** DataManagement  **操作数：** 5

#### 3.17.1 getConnectorInfo（2017-11）

**接口路径：** `Manufacturing-2017-11-DataManagement/getConnectorInfo`

**API 版本：** `2017-11`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 获取连接器（Connector）信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_11.DataManagement.getConnectorInfo`

**请求（input）：**

```json
{
  "itemRevs": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `itemRevs` | Teamcenter::BusinessObject[] | 列表，元素为 ItemRevision（物料版本） for 其 connector information is 必需. |

**响应（output）：**

```json
{
  "connectorInfo": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "connectorProperties": [
        {
          "stringProps": {},
          "stringArrayProps": {},
          "dateProps": {},
          "dateArrayProps": {},
          "tagProps": {},
          "tagArrayProps": {},
          "doubleProps": {},
          "doubleArrayProps": {},
          "floatProps": {},
          "floatArrayProps": {},
          "intProps": {},
          "intArrayProps": {},
          "boolProps": {},
          "boolArrayProps": {}
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `connectorInfo` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::ConnectorTableInfo[] | 列表，元素为 structures containing connector information for given ItemRevision（物料版本） 对象. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 部分错误 as part 的 ServiceData（服务数据）. |

---

#### 3.17.2 getPhysicalAttachmentsInScope（2017-11）

**接口路径：** `Manufacturing-2017-11-DataManagement/getPhysicalAttachmentsInScope`

**API 版本：** `2017-11`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 获取作用域内的物理附件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_11.DataManagement.getPhysicalAttachmentsInScope`

**请求（input）：**

```json
{
  "input": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::GetPhysicalAttachmentsInput[] | 输入 包含以下内容的结构体 scope and context information for 其 the attachments need to be retrieved. |

**响应（output）：**

```json
{
  "attachmentsInfo": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "source": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": "",
      "relationInfo": {
        "stringProps": {},
        "stringArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {},
        "boolArrayProps": {}
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `attachmentsInfo` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::PhysicalAttachmentInfo[] | 列表，元素为 structures containing information about the physical attachment relation Mfg0MEPhysicalAttachment or Mfg0MEMountToolToRobot between AbsOccurrence of BOM 行 对象 under the given scope Mfg0BvrWorkarea. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 部分错误 as part 的 ServiceData（服务数据）. |

---

#### 3.17.3 removePhysicalAttachementRelation（2017-11）

**接口路径：** `Manufacturing-2017-11-DataManagement/removePhysicalAttachementRelation`

**API 版本：** `2017-11`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 移除物理附件关系。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_11.DataManagement.removePhysicalAttachementRelation`

**请求（input）：**

```json
{
  "input": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "source": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::RemovePhysicalAttachmentRelInput[] | 输入 包含以下内容的结构体 information about the context Mfg0BvrWorkarea, scope Mfg0BvrWorkarea and the source and target BOM 行. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.17.4 setConnectorInfo（2017-11）

**接口路径：** `Manufacturing-2017-11-DataManagement/setConnectorInfo`

**API 版本：** `2017-11`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 设置连接器信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_11.DataManagement.setConnectorInfo`

**请求（input）：**

```json
{
  "input": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "connectorInformation": [
        {
          "stringProps": {},
          "stringArrayProps": {},
          "dateProps": {},
          "dateArrayProps": {},
          "tagProps": {},
          "tagArrayProps": {},
          "doubleProps": {},
          "doubleArrayProps": {},
          "floatProps": {},
          "floatArrayProps": {},
          "intProps": {},
          "intArrayProps": {},
          "boolProps": {},
          "boolArrayProps": {}
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::SetConnectorInput[] | 输入 包含以下内容的结构体 information about the ItemRevision（物料版本） and the connectors information. i.e. connector 类型, connector 名称, connector ID and transformation. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.17.5 setPhysicalAttachementsInScope（2017-11）

**接口路径：** `Manufacturing-2017-11-DataManagement/setPhysicalAttachementsInScope`

**API 版本：** `2017-11`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 设置作用域内的物理附件。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2017_11.DataManagement.setPhysicalAttachementsInScope`

**请求（input）：**

```json
{
  "input": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "source": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": "",
      "relationInfo": {
        "stringProps": {},
        "stringArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {},
        "boolArrayProps": {}
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2017_11::DataManagement::SetPhysicalAttachmentsInput[] | 输入 包含以下内容的结构体 information about the scope (Mfg0BvrWorkarea), the source (BOM 行) and target (BOM 行) 对象 and Mfg0MEPhysicalAttachment or Mfg0MEMountToolToRobot relation 属性. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.18 API 版本 2018-06

**Service：** DataManagement  **操作数：** 2

#### 3.18.1 getOccurrenceKinematicsInformation（2018-06）

**接口路径：** `Manufacturing-2018-06-DataManagement/getOccurrenceKinematicsInformation`

**API 版本：** `2018-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 获取出现实例的运动学信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2018_06.DataManagement.getOccurrenceKinematicsInformation`

**请求（input）：**

```json
{
  "occKinematicsInfoinput": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `occKinematicsInfoinput` | Teamcenter::Soa::Manufacturing::_2018_06::DataManagement::GetOccKinematicsInfoInput[] | 输入 包含以下内容的结构体 context and scope for 其 the occurrence kinematics information of resource occurrence is 必需 |

**响应（output）：**

```json
{
  "occurrenceKinematicInfo": [
    {
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "scope": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "resourceLineInformation": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `occurrenceKinematicInfo` | Teamcenter::Soa::Manufacturing::_2018_06::DataManagement::OccurrenceKinematicsInfo[] | A 列表 containing information about BOM 行 representing occurrence of Mfg0MEResourceRevision or ItemRevision（物料版本） and ImanFile having occurrence kinematics information |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Teamcenter Services 结构 用于 return status 的 操作. |

---

#### 3.18.2 setOccurrenceKinematicsInformation（2018-06）

**接口路径：** `Manufacturing-2018-06-DataManagement/setOccurrenceKinematicsInformation`

**API 版本：** `2018-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 设置出现实例的运动学信息。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2018_06.DataManagement.setOccurrenceKinematicsInformation`

**请求（input）：**

```json
{
  "occInfoInputMap": {}
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `occInfoInputMap` | Teamcenter::Soa::Manufacturing::_2018_06::DataManagement::OccKinematicsInfoMap | A 映射 (BOM 行, Dataset) containing BOM 行 representing the occurrence of Mfg0MEResourceRevision or ItemRevision（物料版本） and the dataset Mfg0OccKinematicsInfo having occurrence kinematics information. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.19 API 版本 2018-11

**Service：** StructureManagement  **操作数：** 2

#### 3.19.1 copyRecursively（2018-11）

**接口路径：** `Manufacturing-2018-11-StructureManagement/copyRecursively`

**API 版本：** `2018-11`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 递归复制制造结构节点。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2018_11.StructureManagement.copyRecursively`

**请求（input）：**

```json
{
  "copyInput": [
    {
      "templateInfo": {
        "objectToClone": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "cloningRule": "",
        "referenceWindow": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "additionalInfo": {
          "strToDateVectorMap": {},
          "strToDoubleVectorMap": {},
          "strToStrVectorMap": {},
          "strToObjVectorMap": {},
          "strToIntVectorMap": {}
        }
      },
      "configurationInfo": {
        "revisionRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "variantRules": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "copySuppressedLines": "",
        "copyFutureEffectivities": "",
        "additionalInfo": {
          "strToDateVectorMap": {},
          "strToDoubleVectorMap": {},
          "strToStrVectorMap": {},
          "strToObjVectorMap": {},
          "strToIntVectorMap": {}
        }
      },
      "newObjectInfo": {
        "newName": "",
        "newDescription": "",
        "newId": "",
        "newrevId": "",
        "pasteTarget": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "additionalInfo": {
          "strToDateVectorMap": {},
          "strToDoubleVectorMap": {},
          "strToStrVectorMap": {},
          "strToObjVectorMap": {},
          "strToIntVectorMap": {}
        }
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `copyInput` | Teamcenter::Soa::Manufacturing::_2018_11::StructureManagement::CopyRecursivelyInputInfo[] | A 列表，元素为 输入 结构 其 包含 information about the template 结构 to be cloned, configuration information and the information about the cloned 对象. |

**响应（output）：**

```json
{
  "dataMap": {},
  "logFileTicket": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `dataMap` | Teamcenter::Soa::Manufacturing::_2018_11::StructureManagement::OriginalToCloneStructureMap | A 映射 &lt;BusinessObject, BusinessObject&gt; 包含 输入 对象 其 has been cloned as key and the 物料版本 的 cloned 对象 as 值. |
| `logFileTicket` | std::string | The FMS 票据 对于 transient 文件 that captures the log of cloning 操作. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The standard 服务数据. |

---

#### 3.19.2 pasteDuplicateStructure（2018-11）

**接口路径：** `Manufacturing-2018-11-StructureManagement/pasteDuplicateStructure`

**API 版本：** `2018-11`  
**Service：** `StructureManagement`  
**Library：** `Manufacturing`

**说明：** 粘贴并复制制造结构（重复粘贴）。（存在 2009-10、2018-11 两个 API 版本）

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2018_11.StructureManagement.pasteDuplicateStructure`

**请求（input）：**

```json
{
  "pasteDuplicateInput": [
    {
      "sourceLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "targetLine": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "copyRulesKey": "",
  "notifyEvents": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `pasteDuplicateInput` | Teamcenter::Soa::Manufacturing::_2018_11::StructureManagement::PasteDuplicateInput[] | The source BOM 行 and target BOM 行. |
| `copyRulesKey` | std::string | 名称 的 preference that 将 used for cloning. The preference 值 should be 列表，元素为 Strings. The format of each entry is as follows, sourceType.targetType.PasteDuplicateTemplate This entry 在 preference 值 means, an 对象 of 类型 source… |
| `notifyEvents` | bool | If true, the 客户端 is notified about BOM 行 events. |

**响应（output）：**

```json
{
  "pasteDuplicateOutput": [
    {
      "srcLineIndex": "",
      "targetLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newChildLine": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `pasteDuplicateOutput` | Teamcenter::Soa::Manufacturing::_2018_11::StructureManagement::PasteDuplicateStructureOutput[] | The target BOM 行, the new child BOM 行 created under this target and the 索引 of corresponding source BOM 行 在 输入. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 部分错误 as part 的 ServiceData（服务数据）. |

---

### 3.20 API 版本 2019-06

**Service：** DataManagement  **操作数：** 2

#### 3.20.1 publishSelectionFromStudyToSource（2019-06）

**接口路径：** `Manufacturing-2019-06-DataManagement/publishSelectionFromStudyToSource`

**API 版本：** `2019-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 将研究中的选定内容发布到源结构。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2019_06.DataManagement.publishSelectionFromStudyToSource`

**请求（input）：**

```json
{
  "input": [
    {
      "selectedLines": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "mode": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2019_06::DataManagement::SelectedSyncPublishStudyInput[] | A 列表，元素为 selected 业务对象 from 仿真研究 结构. The valid types are Mfg0BvrSimStudy, Mfg0BvrProcessArea, Mfg0BvrProcessLine, Mfg0BvrProcessStation Mfg0BvrProcess, and Mfg0BvrOperation. It also 包含 synchronization mode (Time based/Ev… |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误 若有. |
| `logFileTicket` | std::string | The FMS 票据 到 日志文件. |

---

#### 3.20.2 syncSelectionInStudyWithSource（2019-06）

**接口路径：** `Manufacturing-2019-06-DataManagement/syncSelectionInStudyWithSource`

**API 版本：** `2019-06`  
**Service：** `DataManagement`  
**Library：** `Manufacturing`

**说明：** 将研究选定内容与源结构同步。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2019_06.DataManagement.syncSelectionInStudyWithSource`

**请求（input）：**

```json
{
  "input": [
    {
      "selectedLines": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "mode": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Manufacturing::_2019_06::DataManagement::SelectedSyncPublishStudyInput[] | A 列表，元素为 selected 业务对象 from 仿真研究. The valid types are Mfg0BvrSimStudy, Mfg0BvrProcessArea, Mfg0BvrProcessLine, Mfg0BvrProcessStation Mfg0BvrProcess, and Mfg0BvrOperation.It also 包含 study root node and the synchronization… |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "logFileTicket": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The 服务数据 containing 部分错误 若有. |
| `logFileTicket` | std::string | The FMS 票据 到 日志文件. |

---

### 3.21 API 版本 2020-04

**Service：** Core  **操作数：** 1

#### 3.21.1 cancelManufacturingCheckout（2020-04）

**接口路径：** `Manufacturing-2020-04-Core/cancelManufacturingCheckout`

**API 版本：** `2020-04`  
**Service：** `Core`  
**Library：** `Manufacturing`

**说明：** 取消用户对制造 BOP/工艺/操作/研究等工作对象的检出状态。

**Soa Inclusion：** `Teamcenter.Soa.Manufacturing._2020_04.Core.cancelManufacturingCheckout`

**请求（input）：**

```json
{
  "rootObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "additionalInfo": {
    "strToBooleanVectorMap": {},
    "strToDateVectorMap": {},
    "strToDoubleVectorMap": {},
    "strToIntegerVectorMap": {},
    "strToObjVectorMap": {},
    "strToStringVectorMap": {}
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `rootObjects` | Teamcenter::BusinessObject[] | A 列表，元素为 对象 to cancel checkout. Valid types are: Mfg0BvrProcess, Mfg0BvrProcessArea, Mfg0MESimStudy, Mfg0MEShdStudy, Mfg0BvrOperation and Mfg0BvrWorkarea. |
| `additionalInfo` | Teamcenter::Soa::Manufacturing::_2020_04::Core::AdditionalInfo | Additional information in form of generic 映射 (string, 列表，元素为 boolean) . Valid keys: "isConsiderSubHierarchy". If true, sub hierarchy is traversed and all checkouts 在 hierarchy are canceled. If false, the 操作 取消 checkout 对… |

**响应（output）：**

```json
"IServiceData"
```

---

---

## 4. 附录

### Service 统计

| Service | 涵盖版本数 | 操作数 |
|---------|------------|--------|
| 约束（Constraints） | 1 | 4 |
| 核心（Core） | 4 | 6 |
| 数据管理（DataManagement） | 10 | 33 |
| 在制品装配管理（IPAManagement） | 4 | 13 |
| 导入导出（ImportExport） | 5 | 6 |
| 制造属性收集（MFGPropertyCollector） | 1 | 1 |
| 模型（Model） | 4 | 12 |
| 模型定义（ModelDefinitions） | 1 | 2 |
| 资源管理（ResourceManagement） | 2 | 7 |
| 结构管理（StructureManagement） | 7 | 18 |
| 结构搜索（StructureSearch） | 4 | 9 |
| 时间管理（TimeManagement） | 2 | 6 |
| 时间路径计划（TimeWayPlan） | 1 | 2 |
| 验证（Validation） | 3 | 4 |

### 典型流程

**PLMXML 制造特征导入：** `ImportExport/importManufacturingFeatures`（注意选择正确 API 版本）

**IPA 在制品装配：** `IPAManagement/generateIPATree` → `updateIPATree` / `localUpdateIPATree`

**工艺结构粘贴复制：** `StructureManagement/pasteDuplicateStructure`（`2009-10` 与 `2018-11` 两版）

### 重新生成

```bash
node generate-manufacturing-doc.js
```
