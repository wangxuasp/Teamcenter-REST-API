# Teamcenter SOA API — Workflow 接口文档（TC 2512）

> 本文档汇总 **Workflow** Library 下**全部 API 版本（年-月）**的 SOA 操作，已合并整理；**功能说明与参数字段说明均为简体中文**。
> 数据来源：TC 2512 SOA Api Browser（`structure.js`）。
>
> - **API 版本数：** 10 个（`2007-06` ～ `2020-01`）
> - **操作总数：** 33 个（含 2 个跨版本同名操作）
> - **Url 格式：** `Workflow-{Year}-Workflow/{operation}`

---

## 目录

1. [API 版本总览](#1-api-版本总览)
2. [按操作合并（含多版本）](#2-按操作合并含多版本)
3. [按 API 版本（年-月）归档](#3-按-api-版本年-月归档)
4. [附录](#4-附录)

---

## 1. API 版本总览

Workflow 库仅包含 **Workflow** 一个 Service，通过 **10 个**年-月版本契约演进；部分操作名在多个版本中重复定义（参数可能不同）。

| API 版本 | 操作 | Url |
|----------|------|-----|
| **2007-06** | `setReleaseStatus` | `Workflow-2007-06-Workflow/setReleaseStatus` |
| **2008-06** | `addAttachments` | `Workflow-2008-06-Workflow/addAttachments` |
| **2008-06** | `addSignoffs` | `Workflow-2008-06-Workflow/addSignoffs` |
| **2008-06** | `assignAllTasks` | `Workflow-2008-06-Workflow/assignAllTasks` |
| **2008-06** | `changeState` | `Workflow-2008-06-Workflow/changeState` |
| **2008-06** | `createInstance` | `Workflow-2008-06-Workflow/createInstance` |
| **2008-06** | `delegateSignoff` | `Workflow-2008-06-Workflow/delegateSignoff` |
| **2008-06** | `getAllTasks` | `Workflow-2008-06-Workflow/getAllTasks` |
| **2008-06** | `getAssignmentLists` | `Workflow-2008-06-Workflow/getAssignmentLists` |
| **2008-06** | `getResourcePool` | `Workflow-2008-06-Workflow/getResourcePool` |
| **2008-06** | `getWorkflowTemplates` | `Workflow-2008-06-Workflow/getWorkflowTemplates` |
| **2008-06** | `listDefinitions` | `Workflow-2008-06-Workflow/listDefinitions` |
| **2008-06** | `performAction` | `Workflow-2008-06-Workflow/performAction` |
| **2008-06** | `removeAttachments` | `Workflow-2008-06-Workflow/removeAttachments` |
| **2008-06** | `removeSignoffs` | `Workflow-2008-06-Workflow/removeSignoffs` |
| **2008-06** | `viewAuditFile` | `Workflow-2008-06-Workflow/viewAuditFile` |
| **2010-09** | `applyTemplateToProcesses` | `Workflow-2010-09-Workflow/applyTemplateToProcesses` |
| **2010-09** | `applyTemplateToProcessesAsync` | `Workflow-2010-09-Workflow/applyTemplateToProcessesAsync` |
| **2012-10** | `performAction2` | `Workflow-2012-10-Workflow/performAction2` |
| **2013-05** | `getWorkflowTemplates` | `Workflow-2013-05-Workflow/getWorkflowTemplates` |
| **2014-06** | `performAction3` | `Workflow-2014-06-Workflow/performAction3` |
| **2014-06** | `performActionWithSignature` | `Workflow-2014-06-Workflow/performActionWithSignature` |
| **2014-06** | `setActiveSurrogate` | `Workflow-2014-06-Workflow/setActiveSurrogate` |
| **2014-06** | `setOutOfOffice` | `Workflow-2014-06-Workflow/setOutOfOffice` |
| **2014-06** | `setSurrogate` | `Workflow-2014-06-Workflow/setSurrogate` |
| **2014-10** | `createRemoteWorkflowAsync` | `Workflow-2014-10-Workflow/createRemoteWorkflowAsync` |
| **2014-10** | `createWorkflow` | `Workflow-2014-10-Workflow/createWorkflow` |
| **2015-07** | `addSignoffs` | `Workflow-2015-07-Workflow/addSignoffs` |
| **2019-06** | `createOrUpdateHandler` | `Workflow-2019-06-Workflow/createOrUpdateHandler` |
| **2019-06** | `createOrUpdatePAL` | `Workflow-2019-06-Workflow/createOrUpdatePAL` |
| **2019-06** | `createOrUpdateTemplate` | `Workflow-2019-06-Workflow/createOrUpdateTemplate` |
| **2019-06** | `getRegisteredHandlers` | `Workflow-2019-06-Workflow/getRegisteredHandlers` |
| **2020-01** | `getSupportedHandlerArguments` | `Workflow-2020-01-Workflow/getSupportedHandlerArguments` |

### 版本统计

| API 版本 | 操作数 |
|----------|--------|
| 2007-06 | 1 |
| 2008-06 | 15 |
| 2010-09 | 2 |
| 2012-10 | 1 |
| 2013-05 | 1 |
| 2014-06 | 5 |
| 2014-10 | 2 |
| 2015-07 | 1 |
| 2019-06 | 4 |
| 2020-01 | 1 |

### 跨版本同名操作

| 操作 | API 版本 |
|------|----------|
| `addSignoffs` | `2008-06`、`2015-07` |
| `getWorkflowTemplates` | `2008-06`、`2013-05` |

---

## 2. 按操作合并（含多版本）

按操作名称归类；若存在多个 API 版本，则在同一节下分别列出各版本接口详情。

### 2.1 addAttachments

**API 版本：** `2008-06`

#### 2.1 addAttachments

**接口路径：** `Workflow-2008-06-Workflow/addAttachments`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 向工作流任务添加附件（目标对象）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.addAttachments`

**请求（input）：**

```json
{
  "task": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "attachments": {
    "attachment": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "attachmentType": []
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `task` | Teamcenter::EPMTask | 工作流任务 |
| `attachments` | Teamcenter::Soa::Workflow::_2008_06::Workflow::AttachmentInfo | 结构体，包含 列表： 附件 及 附件 types. 附件 can be target_objects, reference_objects,release status etc 附件 types can be EPM_target_附件, EPM_reference_附件, EPM_release_status_附件 及 EPM_签审_附件 |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.2 addSignoffs

**API 版本：** `2008-06`、`2015-07`（同名多版本，调用时注意 Url 差异）

#### 版本 2008-06

##### 2.2.1 addSignoffs

**接口路径：** `Workflow-2008-06-Workflow/addSignoffs`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 向工作流任务添加签审人。可添加临时签审、配置 Profile 签审，支持审阅/确认/通知等类型；2015-07 版支持地址列表与必选/可选评审人。注意：2008-06 与 2015-07 为不同 API 版本，参数结构有差异。（当前 API 版本：`2008-06`）

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.addSignoffs`

**请求（input）：**

```json
{
  "signoffs": [
    {
      "task": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "signoffInfo": [
        {
          "signoffMember": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "origin": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "signoffAction": "SOA_EPM_ACTION_UNDEFINED",
          "originType": "SOA_EPM_ORIGIN_UNDEFINED"
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `signoffs` | Teamcenter::Soa::Workflow::_2008_06::Workflow::CreateSignoffs[] | 数组： Create签审s - 结构体，包含 task tag 及 数组： Create签审Info 说明： Create签审Info structure contains information to add adhoc 签审 或 add 签审 based on a profile Case of Adhoc 签审:this is used for case of adhoc 签审 : Provide 签审Member can … |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2015-07

##### 2.2.2 addSignoffs

**接口路径：** `Workflow-2015-07-Workflow/addSignoffs`

**API 版本：** `2015-07`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 向工作流任务添加签审人。可添加临时签审、配置 Profile 签审，支持审阅/确认/通知等类型；2015-07 版支持地址列表与必选/可选评审人。注意：2008-06 与 2015-07 为不同 API 版本，参数结构有差异。（当前 API 版本：`2015-07`）

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2015_07.Workflow.addSignoffs`

**请求（input）：**

```json
{
  "signoffs": [
    {
      "task": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "signoffInfo": [
        {
          "signoffMember": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "origin": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "signoffAction": "",
          "originType": "",
          "signoffRequired": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `signoffs` | Teamcenter::Soa::Workflow::_2015_07::Workflow::CreateSignoffs[] | This is a 列表： Create签审s structures which contain Task for which 签审s need to be added 及 列表： Create签审Info 结构体，包含 requisite information to create 签审 object. |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.3 applyTemplateToProcesses

**API 版本：** `2010-09`

#### 2.3 applyTemplateToProcesses

**接口路径：** `Workflow-2010-09-Workflow/applyTemplateToProcesses`

**API 版本：** `2010-09`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 将指定模板应用到所有基于该模板旧版本的活动工作流进程（同步）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2010_09.Workflow.applyTemplateToProcesses`

**请求（input）：**

```json
{
  "applyTemplateInput": [
    {
      "clientId": "",
      "processTemplate": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "processingMode": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `applyTemplateInput` | Teamcenter::Soa::Workflow::_2010_09::Workflow::ApplyTemplateInput[] | Templates to be applied to active processes |
| `processingMode` | int | Indicates if request needs to be processed asynchronously. 0 - Indicates synchronous processing. 1 - Indicates asynchronous processing. |

**响应（output）：**

```json
{
  "applyTemplateOutput": [
    {
      "clientId": "",
      "updatedProcesses": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "failedProcesses": [
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
| `applyTemplateOutput` | Teamcenter::Soa::Workflow::_2010_09::Workflow::ApplyTemplateOutput[] | 列表： processes that were updated 及 列表： processes that failed. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data |

---

### 2.4 applyTemplateToProcessesAsync

**API 版本：** `2010-09`

#### 2.4 applyTemplateToProcessesAsync

**接口路径：** `Workflow-2010-09-Workflow/applyTemplateToProcessesAsync`

**API 版本：** `2010-09`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 将指定模板应用到活动工作流进程（异步，无返回值）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2010_09.Workflow.applyTemplateToProcessesAsync`

**请求（input）：**

```json
{
  "applyTemplateInput": [
    {
      "clientId": "",
      "processTemplate": {
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
| `applyTemplateInput` | Teamcenter::Soa::Workflow::_2010_09::Workflow::ApplyTemplateInput[] | Templates to be applied to active processes. |

**响应（output）：**

```json
"void"
```

---

### 2.5 assignAllTasks

**API 版本：** `2008-06`

#### 2.5 assignAllTasks

**接口路径：** `Workflow-2008-06-Workflow/assignAllTasks`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 将流程分配列表（PAL）应用到工作流进程，或根据 Resources 结构批量分配任务执行人。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.assignAllTasks`

**请求（input）：**

```json
{
  "process": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "assignmentList": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "resources": [
    {
      "taskTemplate": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "templateResources": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "profiles": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "actions": [],
      "revQuorum": "",
      "ackQuorum": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `process` | Teamcenter::EPMJob |  process to which process assignment list has to be assigned. |
| `assignmentList` | Teamcenter::EPMAssignmentList | assignment list to be applied to process |
| `resources` | Teamcenter::Soa::Workflow::_2008_06::Workflow::Resources[] | 列表： structures containing resource info (for eg. Task template, Group member 或 resource pool, 签审 profiles, quorum etc). |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.6 changeState

**API 版本：** `2008-06`

#### 2.6 changeState

**接口路径：** `Workflow-2008-06-Workflow/changeState`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 在远程站点更改工作流进程或任务的状态。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.changeState`

**请求（input）：**

```json
{
  "stateInput": {
    "state": "",
    "remoteProcessID": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `stateInput` | Teamcenter::Soa::Workflow::_2008_06::Workflow::ChangeStateInputInfo | ChangeStateInputInfo |

**响应（output）：**

```json
{
  "state": "",
  "remoteProcessID": "",
  "parentProcessID": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `state` | Teamcenter::Soa::Workflow::_2008_06::Workflow::stateType | state |
| `remoteProcessID` | std::string | remoteProcessID |
| `parentProcessID` | std::string | parentProcessID |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData |

---

### 2.7 createInstance

**API 版本：** `2008-06`

#### 2.7 createInstance

**接口路径：** `Workflow-2008-06-Workflow/createInstance`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据工作流模板创建流程或子流程实例（支持本地或远程站点）。可指定是否立即启动、附件、流程所有者等。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.createInstance`

**请求（input）：**

```json
{
  "startImmediately": "",
  "observerKey": "",
  "name": "",
  "subject": "",
  "description": "",
  "contextData": {
    "processTemplate": "{{WF_TEMPLATE_NAME}}",
    "processOwner": "",
    "dependencyTask": "",
    "subscribeToEvents": "",
    "subscriptionEventCount": "",
    "subscriptionEventList": [
      ""
    ],
    "remoteParent": "",
    "remoteParentAppguid": "",
    "remoteParentUrl": "",
    "attachmentCount": "",
    "attachments": [
      "{{CREATED_ITEM_UID}}"
    ],
    "attachmentTypes": [],
    "deadlineDate": "0001-01-01T00:00:00",
    "container": "",
    "relationType": "",
    "processAssignmentList": "",
    "processResources": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `startImmediately` | bool | Boolean value to say whether instance created should be immediately started 或 should be put into initial state for later starting by use of "Start" operation. No value implies true. (This argument is currently not sup… |
| `observerKey` | std::string | URI of observer that initiated 工作流进程 或 sub process at a 远程站点. observer is to be notified of events impacting execution of this process instance such as state changes, 及 most notably completion of instance. If not spec… |
| `name` | std::string | Name of remote process 或 sub process instance. |
| `subject` | std::string | A shorter description of purpose of remote process 或 sub process. |
| `description` | std::string | A longer description of purpose of remote process 或 sub process. |
| `contextData` | Teamcenter::Soa::Workflow::_2008_06::Workflow::ContextData | Context-specific data required to create a process 或 sub process at a local 或 a 远程站点 in Teamcenter. |

**响应（output）：**

```json
{
  "instanceKey": "",
  "newProcessDepTask": "",
  "newProcessUrl": "",
  "newProcessDepTaskUrl": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `instanceKey` | std::string | instanceKey. supported in future |
| `newProcessDepTask` | std::string | newProcessDepTask. supported in future |
| `newProcessUrl` | std::string | newProcessUrl. supported in future |
| `newProcessDepTaskUrl` | std::string | newProcessDepTaskUrl. supported in future |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData containing created process 及 errors if any |

---

### 2.8 createOrUpdateHandler

**API 版本：** `2019-06`

#### 2.8 createOrUpdateHandler

**接口路径：** `Workflow-2019-06-Workflow/createOrUpdateHandler`

**API 版本：** `2019-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 新建或更新工作流处理器（EPMHandler）实例，用于 Workflow Designer。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2019_06.Workflow.createOrUpdateHandler`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "handlerName": "",
      "taskTemplate": "",
      "businessRule": "",
      "handlerType": "",
      "handlerToUpdate": "",
      "action": "",
      "ruleQuorum": "",
      "changeExecutionOrder": "",
      "additionalData": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdateHandlerInput[] | A 列表： CreateUpdateHandlerInput stucture represents required inputs for creating a new 处理器 或 upating existing handlers. |

**响应（output）：**

```json
{
  "createdorUpdatedObjects": [
    {
      "clientID": "",
      "handlerObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "ruleObject": {
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
| `createdorUpdatedObjects` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdateHandlerOutput[] | A 列表： CreateUpdateHandlerOutput structure. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData |  service data. |

---

### 2.9 createOrUpdatePAL

**API 版本：** `2019-06`

#### 2.9 createOrUpdatePAL

**接口路径：** `Workflow-2019-06-Workflow/createOrUpdatePAL`

**API 版本：** `2019-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 新建、更新或深拷贝流程分配列表（EPMAssignmentList / PAL），供 Handler 或提交工作流面板使用。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2019_06.Workflow.createOrUpdatePAL`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "palName": "",
      "workflowTemplate": "",
      "palDescription": [
        ""
      ],
      "resourceLists": [
        {
          "taskTemplate": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "templateResources": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "profiles": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "actions": [],
          "revQuorum": "",
          "ackQuorum": ""
        }
      ],
      "additionalData": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdatePALInput[] | A 列表： CreateUpdatePALInput stucture used to update 或 copy EPMAssignmentList 或 to create a new EPMAssignmentList . |

**响应（output）：**

```json
{
  "createdorUpdatedObjects": [
    {
      "clientID": "",
      "palObject": {
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
| `createdorUpdatedObjects` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdatePALOutput[] | A 列表： CreateUpdatePALOutput structure. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData |  service data. |

---

### 2.10 createOrUpdateTemplate

**API 版本：** `2019-06`

#### 2.10 createOrUpdateTemplate

**接口路径：** `Workflow-2019-06-Workflow/createOrUpdateTemplate`

**API 版本：** `2019-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 新建或更新工作流任务模板（EPMTaskTemplate），用于 Workflow Designer。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2019_06.Workflow.createOrUpdateTemplate`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "templateName": "",
      "templateDesc": "",
      "baseTemplate": "",
      "parentTemplate": "",
      "templateToUpdate": "",
      "additionalData": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdateTemplateInput[] | A 列表： CreateUpdateTemplateInput stucture represents required inputs for creating a new task template 或 upating existing task template. |

**响应（output）：**

```json
{
  "createdorUpdatedObjects": [
    {
      "clientID": "",
      "templateObject": {
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
| `createdorUpdatedObjects` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdateTemplateOutput[] | A 列表： CreateUpdateTemplateOutput structure. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData |  service data. |

---

### 2.11 createRemoteWorkflowAsync

**API 版本：** `2014-10`

#### 2.11 createRemoteWorkflowAsync

**接口路径：** `Workflow-2014-10-Workflow/createRemoteWorkflowAsync`

**API 版本：** `2014-10`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 通过 TcIF 异步提交在远程站点创建工作流的请求。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_10.Workflow.createRemoteWorkflowAsync`

**请求（input）：**

```json
{
  "createRemoteWkfInput": {
    "processName": "",
    "processDescription": "",
    "attachmentRelationTypes": [
      ""
    ],
    "processTemplate": "",
    "workflowOwner": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "responsibleParty": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "assignedUserList": [
      ""
    ],
    "dueDate": "0001-01-01T00:00:00",
    "sourceObject": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "site": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "attachments": [
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
| `createRemoteWkfInput` | Teamcenter::Soa::Workflow::_2014_10::Workflow::CreateRemoteWkfInput |  information used for remote workflow creation (e.g. name of 流程模板, workflow owner, responsible party, source object, 远程站点 , 附件, 及 附件 relations). |

**响应（output）：**

```json
"void"
```

---

### 2.12 createWorkflow

**API 版本：** `2014-10`

#### 2.12 createWorkflow

**接口路径：** `Workflow-2014-10-Workflow/createWorkflow`

**API 版本：** `2014-10`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据模板名称、所有者、责任人、附件等创建工作流进程。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_10.Workflow.createWorkflow`

**请求（input）：**

```json
{
  "input": {
    "processName": "",
    "processDescription": "",
    "processTemplate": "",
    "workflowOwner": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "responsibleParty": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "assignedUserList": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "dueDate": "0001-01-01T00:00:00",
    "attachments": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "attachmentRelationTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2014_10::Workflow::CreateWkfInput |  process name, 流程模板 name, 工作流进程 owner, responsible party, assignees, due date, 附件, 及 附件 relations. |

**响应（output）：**

```json
{
  "workflowTask": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "attributes": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `workflowTask` | Teamcenter::BusinessObject | Workflow root task. |
| `attributes` | Teamcenter::Soa::Workflow::_2014_10::Workflow::NameValuePairs | A map (string/string) of workflow root task property names 及 values. (e.g. status, process instructions, task_result). |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data. |

---

### 2.13 delegateSignoff

**API 版本：** `2008-06`

#### 2.13 delegateSignoff

**接口路径：** `Workflow-2008-06-Workflow/delegateSignoff`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 将签审委派给其他组成员（GroupMember）或资源池（ResourcePool）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.delegateSignoff`

**请求（input）：**

```json
{
  "delegatee": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "signoff": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `delegatee` | Teamcenter::BusinessObject |  group memebr 或 a resource pool tag to be delegated to. |
| `signoff` | Teamcenter::Signoff | 签审 object. |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.14 getAllTasks

**API 版本：** `2008-06`

#### 2.14 getAllTasks

**接口路径：** `Workflow-2008-06-Workflow/getAllTasks`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 获取指定工作流进程中的全部任务。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.getAllTasks`

**请求（input）：**

```json
{
  "process": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "state": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `process` | Teamcenter::EPMJob | 工作流进程 object |
| `state` | int | TODO |

**响应（output）：**

```json
{
  "allTasks": [
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
| `allTasks` | Teamcenter::EPMTask[] | allTasks |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data contains any 部分错误. |

---

### 2.15 getAssignmentLists

**API 版本：** `2008-06`

#### 2.15 getAssignmentLists

**接口路径：** `Workflow-2008-06-Workflow/getAssignmentLists`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据名称获取流程分配列表（Process Assignment List）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.getAssignmentLists`

**请求（input）：**

```json
{
  "names": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `names` | std::string[] | A set of process assignment list names |

**响应（output）：**

```json
{
  "assignedLists": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "ownedLists": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "groupLists": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "otherLists": [
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
| `assignedLists` | Teamcenter::EPMAssignmentList[] | assignedLists |
| `ownedLists` | Teamcenter::EPMAssignmentList[] | ownedLists |
| `groupLists` | Teamcenter::EPMAssignmentList[] | groupLists |
| `otherLists` | Teamcenter::EPMAssignmentList[] | otherLists |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data - returns index of input vector if call on that fails |

---

### 2.16 getRegisteredHandlers

**API 版本：** `2019-06`

#### 2.16 getRegisteredHandlers

**接口路径：** `Workflow-2019-06-Workflow/getRegisteredHandlers`

**API 版本：** `2019-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 返回已注册的工作流 Handler 名称列表，供创建 Handler 实例时选择。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2019_06.Workflow.getRegisteredHandlers`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "actionHandlers": [
    ""
  ],
  "ruleHandlers": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `actionHandlers` | std::string[] | A 列表： names of registered action handlers. |
| `ruleHandlers` | std::string[] | A 列表： names of registered rule handlers. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData |  service data. |

---

### 2.17 getResourcePool

**API 版本：** `2008-06`

#### 2.17 getResourcePool

**接口路径：** `Workflow-2008-06-Workflow/getResourcePool`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据组/角色引用获取常规或全部成员资源池（ResourcePool）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.getResourcePool`

**请求（input）：**

```json
{
  "groupRoleRef": [
    {
      "groupTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "roleTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "allowSubGroup": "",
      "isAllMembers": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `groupRoleRef` | Teamcenter::Soa::Workflow::_2008_06::Workflow::GroupRoleRef[] | 列表： GroupRoleRef 结构体，包含 info about Resource Pool being asked for |

**响应（output）：**

```json
{
  "resourcePoolInfo": [
    {
      "groupRoleRef": {
        "groupTag": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "roleTag": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "allowSubGroup": "",
        "isAllMembers": ""
      },
      "resourcePoolTag": {
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
| `resourcePoolInfo` | Teamcenter::Soa::Workflow::_2008_06::Workflow::ResourcePoolInfo[] | resourcePoolInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData |

---

### 2.18 getSupportedHandlerArguments

**API 版本：** `2020-01`

#### 2.18 getSupportedHandlerArguments

**接口路径：** `Workflow-2020-01-Workflow/getSupportedHandlerArguments`

**API 版本：** `2020-01`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 从 `TC_DATA/workflow_handlers/<handler>.json` 读取 Handler 参数提示（必填、可选、互斥、依赖等）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2020_01.Workflow.getSupportedHandlerArguments`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "handlerName": "",
      "additionalData": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2020_01::Workflow::SupportedHandlerArgumentsInput[] | A 列表： SupportedHandlerArgumentsInput stucture that represent input 处理器 name. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "handlerData": "",
      "additionalData": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Workflow::_2020_01::Workflow::SupportedHandlerArgumentsInfoOutput[] | 列表： SupportedHandlerArgumentsInfoOutput structure which contains 处理器 data info. |

---

### 2.19 getWorkflowTemplates

**API 版本：** `2008-06`、`2013-05`（同名多版本，调用时注意 Url 差异）

#### 版本 2008-06

##### 2.19.1 getWorkflowTemplates

**接口路径：** `Workflow-2008-06-Workflow/getWorkflowTemplates`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据目标对象及筛选条件获取可用工作流模板列表。2008-06 与 2013-05 版本参数与筛选逻辑不同，调用时需匹配对应 API 版本。（当前 API 版本：`2008-06`）

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.getWorkflowTemplates`

**请求（input）：**

```json
{
  "targets": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "allOrAssignedCriteria": "SOA_EPM_All"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `targets` | Teamcenter::WorkspaceObject[] | 列表： 目标对象 to get 工作流模板 for |
| `allOrAssignedCriteria` | Teamcenter::Soa::Workflow::_2008_06::Workflow::AllOrAssigned | criteria to get all templates 或 assigned templates. |

**响应（output）：**

```json
{
  "workflowTemplates": [
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
| `workflowTemplates` | Teamcenter::EPMTaskTemplate[] | workflowTemplates |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data contains any 部分错误. |

---

#### 版本 2013-05

##### 2.19.2 getWorkflowTemplates

**接口路径：** `Workflow-2013-05-Workflow/getWorkflowTemplates`

**API 版本：** `2013-05`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据目标对象及筛选条件获取可用工作流模板列表。2008-06 与 2013-05 版本参数与筛选逻辑不同，调用时需匹配对应 API 版本。（当前 API 版本：`2013-05`）

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2013_05.Workflow.getWorkflowTemplates`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "includeUnderConstruction": "",
      "getFiltered": "",
      "targetObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "objectTypes": [
        ""
      ],
      "group": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2013_05::Workflow::GetWorkflowTemplatesInputInfo[] | Structure to define input for 工作流模板. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "templatesOutput": [
    {
      "clientId": "",
      "workflowTemplates": [
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
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据（ServiceData） contains any 部分错误. |
| `templatesOutput` | Teamcenter::Soa::Workflow::_2013_05::Workflow::GetWorkflowTemplatesOutput[] | Complete 列表： 工作流模板 Output. |

---

### 2.20 listDefinitions

**API 版本：** `2008-06`

#### 2.20 listDefinitions

**接口路径：** `Workflow-2008-06-Workflow/listDefinitions`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 按名称、状态等条件列出流程模板定义。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.listDefinitions`

**请求（input）：**

```json
{
  "name": "",
  "templatestatus": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `name` | std::string | name of template to retrieve. This argument is 可选. Provide value null to make it 可选. |
| `templatestatus` | int | TODO |

**响应（output）：**

```json
{
  "output": [
    {
      "definitionkey": "",
      "name": "",
      "description": "",
      "version": "",
      "status": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Workflow::_2008_06::Workflow::DefinitionInfo[] | 数组： DefinitionInfo objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data contains any 部分错误. |

---

### 2.21 performAction

**API 版本：** `2008-06`

#### 2.21 performAction

**接口路径：** `Workflow-2008-06-Workflow/performAction`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 对工作流任务执行操作（分配、启动、完成、跳过、挂起、恢复、撤销、执行、批准、拒绝、提升、降级等）。签审任务仅更新意见时可使用 `EPM_no_action`。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.performAction`

**请求（input）：**

```json
{
  "task": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "action": "SOA_EPM_assign_action",
  "comments": "",
  "password": "",
  "supportingValue": "SOA_EPM_no_decision",
  "supportingObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `task` | Teamcenter::EPMTask | 工作流任务 |
| `action` | Teamcenter::Soa::Workflow::_2008_06::Workflow::SoaEPMAction |  action to be performed on task required. possible values for action are defined in enum SoaEPMAction. They are SOA_EPM_assign_action, SOA_EPM_start_action, SOA_EPM_complete_action, SOA_EPM_skip_action, SOA_EPM_suspen… |
| `comments` | std::string | user comments. This argument is 可选. Provide value null to make it 可选. |
| `password` | std::string | password for secure 签审 action required for secure 签审. This argument is 可选. Provide value null to make it 可选(non secure). |
| `supportingValue` | Teamcenter::Soa::Workflow::_2008_06::Workflow::SoaEPMSupportingValues | this argument can be used to send in decision value 或 result. If task is perform 签审 task, provide decision using this argument. possible values for decision are SOA_EPM_no_decision, SOA_EPM_approve, SOA_EPM_reject. Fo… |
| `supportingObject` | Teamcenter::BusinessObject | If action is assign, provide a user tag 或 a resource pool tag to assign task to. If task is perform 签审 task, provide 签审 tag to set decision on. |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.22 performAction2

**API 版本：** `2012-10`

#### 2.22 performAction2

**接口路径：** `Workflow-2012-10-Workflow/performAction2`

**API 版本：** `2012-10`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 对工作流任务执行操作（performAction 的升级版本，2012-10）。支持 Assign/Start/Complete/Approve/Reject 等。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2012_10.Workflow.performAction2`

**请求（input）：**

```json
{
  "task": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "action": "",
  "comments": "",
  "password": "",
  "supportingValue": "",
  "supportingObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `task` | Teamcenter::EPMTask | 工作流任务 on which action needs to be performed |
| `action` | std::string | Action to be performed on 工作流任务. Possible values for action are 以下: Action Description "SOA_EPM_assign_action" Assign task "SOA_EPM_start_action" Start task "SOA_EPM_complete_action" Mark task as Complete "SOA_EPM_ski… |
| `comments` | std::string | A comment assigned to this task action. This may be an empty string. |
| `password` | std::string |  password for a secure task. value of this parameter is ignored for non-secure tasks. |
| `supportingValue` | std::string | This argument can be used to send in decision value 或 result. If task is perform-签审 task, possible values for decision are: "SOA_EPM_no_decision" "SOA_EPM_approve" "SOA_EPM_reject" Following are result values applicab… |
| `supportingObject` | Teamcenter::BusinessObject | If action is assign , provide a user 或 resource pool to assign task. If task is perform-签审 task, provide 签审 object to set decision. If task is a perform-签审 task 及 action is claim , provide 签审 object to be claimed. |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.23 performAction3

**API 版本：** `2014-06`

#### 2.23 performAction3

**接口路径：** `Workflow-2014-06-Workflow/performAction3`

**API 版本：** `2014-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 对 EPMTask 或 Signoff 执行操作，并支持对目标对象进行数字签名（会话需 HTTPS）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_06.Workflow.performAction3`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "actionableObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "action": "",
      "password": "",
      "supportingValue": "",
      "supportingObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyNameValues": {},
      "signatures": [
        {
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "base64String": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2014_06::Workflow::PerformActionInputInfo[] | A 列表： PerformActionInputInfo structure which contains clientId, EPM 任务 或 签审 business object, action to be performed on an EPM 任务 或 签审 , password for a secure Task, supportingValue which can be used to send in decision… |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.24 performActionWithSignature

**API 版本：** `2014-06`

#### 2.24 performActionWithSignature

**接口路径：** `Workflow-2014-06-Workflow/performActionWithSignature`

**API 版本：** `2014-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 执行工作流任务操作并支持签名，适用于富客户端、瘦客户端及 Office 客户端任务处理。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_06.Workflow.performActionWithSignature`

**请求（input）：**

```json
{
  "task": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "action": "",
  "comments": "",
  "password": "",
  "supportingValue": "",
  "supportingObject": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "signatures": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "base64String": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `task` | Teamcenter::EPMTask | 工作流任务 on which action needs to be performed |
| `action` | std::string | Action to be performed on 工作流任务. Possible values for action are following: Action Description "SOA_EPM_assign_action" Assign task "SOA_EPM_start_action" Start task "SOA_EPM_complete_action" Mark task as Complete "SOA_… |
| `comments` | std::string | A comment assigned to this task action. This may be an empty string. |
| `password` | std::string |  password for secure task. value of this parameter is ignored for non-secured tasks. |
| `supportingValue` | std::string | This argument can be used to send in decision value 或 result. If task is a perform-签审s task, possible values for decision are: "SOA_EPM_no_decision" "SOA_EPM_approve" "SOA_EPM_reject" Folloing are result values applic… |
| `supportingObject` | Teamcenter::BusinessObject | If action is assign, provide a user 或 resource pool to assign task. If task is perform-签审 task, provide 签审 object to set decision. If task is a perform-签审 task 及 action is claim, provide 签审 object to be claimed. |
| `signatures` | Teamcenter::Soa::Workflow::_2014_06::Workflow::ApplySignatureInput[] | 列表： ApplySignatureInput objects, each representing 目标对象 及 its corresponding Base64 string. |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.25 removeAttachments

**API 版本：** `2008-06`

#### 2.25 removeAttachments

**接口路径：** `Workflow-2008-06-Workflow/removeAttachments`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 从工作流任务移除附件。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.removeAttachments`

**请求（input）：**

```json
{
  "task": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "attachments": [
    "{{CREATED_ITEM_UID}}"
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `task` | Teamcenter::EPMTask | 工作流任务 |
| `attachments` | Teamcenter::BusinessObject[] |  列表： 附件 to remove 附件 can be target_objects, reference_objects,release status etc |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.26 removeSignoffs

**API 版本：** `2008-06`

#### 2.26 removeSignoffs

**接口路径：** `Workflow-2008-06-Workflow/removeSignoffs`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 从工作流任务移除签审人。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.removeSignoffs`

**请求（input）：**

```json
{
  "signoffs": [
    {
      "task": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "removeSignoffObjs": [
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
| `signoffs` | Teamcenter::Soa::Workflow::_2008_06::Workflow::RemoveSignoffsInfo[] | 列表： 签审s - 结构体，包含 select 签审 task tag, groupmembers 或 |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.27 setActiveSurrogate

**API 版本：** `2014-06`

#### 2.27 setActiveSurrogate

**接口路径：** `Workflow-2014-06-Workflow/setActiveSurrogate`

**API 版本：** `2014-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 设置/取消当前用户为指定 EPMTask 或 Signoff 的活动代理人，并可转移目标对象的检出状态。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_06.Workflow.setActiveSurrogate`

**请求（input）：**

```json
{
  "input": [
    {
      "taskOrSignoffTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "releaseStandIn": "",
      "transferCheckouts": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2014_06::Workflow::SetActiveSurrogateInputInfo[] | A 列表： SetActive代理人InputInfo structure which 包含 EPM 任务 或 签审 business object, boolean to indicate Stand-In 或 Release operation 及 boolean to indicate if checkout of 目标对象(s) should be transferred 或 not. |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.28 setOutOfOffice

**API 版本：** `2014-06`

#### 2.28 setOutOfOffice

**接口路径：** `Workflow-2014-06-Workflow/setOutOfOffice`

**API 版本：** `2014-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 设置/取消用户外出（Out of Office）及代理人，在指定日期范围内将任务委派给另一用户或资源池。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_06.Workflow.setOutOfOffice`

**请求（input）：**

```json
{
  "fromResource": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "toResource": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "startDate": "0001-01-01T00:00:00",
  "endDate": "0001-01-01T00:00:00"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `fromResource` | Teamcenter::User |  User for whom 外出 will be set/unset. |
| `toResource` | Teamcenter::BusinessObject | A User 或 a 资源池 to be set as 外出 resource. |
| `startDate` | Teamcenter::DateTime |  effective start date of 外出 setting. |
| `endDate` | Teamcenter::DateTime |  effective end date of 外出 setting. Set to null (for C++ use DateTime::getNullDate()) to set 外出 to be indefinite (no end). |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.29 setReleaseStatus

**API 版本：** `2007-06`

#### 2.29 setReleaseStatus

**接口路径：** `Workflow-2007-06-Workflow/setReleaseStatus`

**API 版本：** `2007-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 管理对象的发布状态。支持追加（Append）、删除（Delete）等操作；删除时若状态名为空字符串，将清除该对象的全部发布状态。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2007_06.Workflow.setReleaseStatus`

**请求（input）：**

```json
{
  "input": [
    {
      "operations": [
        {
          "newReleaseStatusTypeName": "",
          "operation": "",
          "existingreleaseStatusTypeName": ""
        }
      ],
      "objects": [
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
| `input` | Teamcenter::Soa::Workflow::_2007_06::Workflow::ReleaseStatusInput[] | A 数组： ReleaseStatusInput structures that control operations performed on objects |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData |

---

### 2.30 setSurrogate

**API 版本：** `2014-06`

#### 2.30 setSurrogate

**接口路径：** `Workflow-2014-06-Workflow/setSurrogate`

**API 版本：** `2014-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 为指定用户设置或取消代理人及生效日期范围。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_06.Workflow.setSurrogate`

**请求（input）：**

```json
{
  "requests": [
    {
      "unset": "",
      "fromResource": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toResource": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "startDate": "0001-01-01T00:00:00",
      "endDate": "0001-01-01T00:00:00"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `requests` | Teamcenter::Soa::Workflow::_2014_06::Workflow::SurrogateInput[] | A 列表： 代理人Input structures which contain original User, 代理人 User, effective start date, 及 end date. |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.31 viewAuditFile

**API 版本：** `2008-06`

#### 2.31 viewAuditFile

**接口路径：** `Workflow-2008-06-Workflow/viewAuditFile`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 查看以文件形式存储的工作流审计信息（审计管理器开启时不可用）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.viewAuditFile`

**请求（input）：**

```json
{
  "auditedObject": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "isSignoffReport": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `auditedObject` | Teamcenter::BusinessObject |  object to get audit info on. E.g. 工作区对象 in process 或 process itself.. |
| `isSignoffReport` | bool | Boolean to indicate if request is for a audit file 或 a 签审 report. true for a 签审 report, false for a audit file |

**响应（output）：**

```json
{
  "auditFiles": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `auditFiles` | std::string[] | auditFiles |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData |

---

---

## 3. 按 API 版本（年-月）归档

按时间线列出各版本契约下的全部接口（便于按版本检索）。

### 3.1 API 版本 2007-06

**操作数：** 1

#### 3.1.1 setReleaseStatus（2007-06）

**接口路径：** `Workflow-2007-06-Workflow/setReleaseStatus`

**API 版本：** `2007-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 管理对象的发布状态。支持追加（Append）、删除（Delete）等操作；删除时若状态名为空字符串，将清除该对象的全部发布状态。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2007_06.Workflow.setReleaseStatus`

**请求（input）：**

```json
{
  "input": [
    {
      "operations": [
        {
          "newReleaseStatusTypeName": "",
          "operation": "",
          "existingreleaseStatusTypeName": ""
        }
      ],
      "objects": [
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
| `input` | Teamcenter::Soa::Workflow::_2007_06::Workflow::ReleaseStatusInput[] | A 数组： ReleaseStatusInput structures that control operations performed on objects |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData |

---

### 3.2 API 版本 2008-06

**操作数：** 15

#### 3.2.1 addAttachments（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/addAttachments`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 向工作流任务添加附件（目标对象）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.addAttachments`

**请求（input）：**

```json
{
  "task": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "attachments": {
    "attachment": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "attachmentType": []
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `task` | Teamcenter::EPMTask | 工作流任务 |
| `attachments` | Teamcenter::Soa::Workflow::_2008_06::Workflow::AttachmentInfo | 结构体，包含 列表： 附件 及 附件 types. 附件 can be target_objects, reference_objects,release status etc 附件 types can be EPM_target_附件, EPM_reference_附件, EPM_release_status_附件 及 EPM_签审_附件 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.2 addSignoffs（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/addSignoffs`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 向工作流任务添加签审人。可添加临时签审、配置 Profile 签审，支持审阅/确认/通知等类型；2015-07 版支持地址列表与必选/可选评审人。注意：2008-06 与 2015-07 为不同 API 版本，参数结构有差异。（当前 API 版本：`2008-06`）

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.addSignoffs`

**请求（input）：**

```json
{
  "signoffs": [
    {
      "task": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "signoffInfo": [
        {
          "signoffMember": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "origin": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "signoffAction": "SOA_EPM_ACTION_UNDEFINED",
          "originType": "SOA_EPM_ORIGIN_UNDEFINED"
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `signoffs` | Teamcenter::Soa::Workflow::_2008_06::Workflow::CreateSignoffs[] | 数组： Create签审s - 结构体，包含 task tag 及 数组： Create签审Info 说明： Create签审Info structure contains information to add adhoc 签审 或 add 签审 based on a profile Case of Adhoc 签审:this is used for case of adhoc 签审 : Provide 签审Member can … |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.3 assignAllTasks（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/assignAllTasks`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 将流程分配列表（PAL）应用到工作流进程，或根据 Resources 结构批量分配任务执行人。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.assignAllTasks`

**请求（input）：**

```json
{
  "process": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "assignmentList": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "resources": [
    {
      "taskTemplate": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "templateResources": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "profiles": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "actions": [],
      "revQuorum": "",
      "ackQuorum": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `process` | Teamcenter::EPMJob |  process to which process assignment list has to be assigned. |
| `assignmentList` | Teamcenter::EPMAssignmentList | assignment list to be applied to process |
| `resources` | Teamcenter::Soa::Workflow::_2008_06::Workflow::Resources[] | 列表： structures containing resource info (for eg. Task template, Group member 或 resource pool, 签审 profiles, quorum etc). |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.4 changeState（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/changeState`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 在远程站点更改工作流进程或任务的状态。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.changeState`

**请求（input）：**

```json
{
  "stateInput": {
    "state": "",
    "remoteProcessID": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `stateInput` | Teamcenter::Soa::Workflow::_2008_06::Workflow::ChangeStateInputInfo | ChangeStateInputInfo |

**响应（output）：**

```json
{
  "state": "",
  "remoteProcessID": "",
  "parentProcessID": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `state` | Teamcenter::Soa::Workflow::_2008_06::Workflow::stateType | state |
| `remoteProcessID` | std::string | remoteProcessID |
| `parentProcessID` | std::string | parentProcessID |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData |

---

#### 3.2.5 createInstance（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/createInstance`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据工作流模板创建流程或子流程实例（支持本地或远程站点）。可指定是否立即启动、附件、流程所有者等。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.createInstance`

**请求（input）：**

```json
{
  "startImmediately": "",
  "observerKey": "",
  "name": "",
  "subject": "",
  "description": "",
  "contextData": {
    "processTemplate": "{{WF_TEMPLATE_NAME}}",
    "processOwner": "",
    "dependencyTask": "",
    "subscribeToEvents": "",
    "subscriptionEventCount": "",
    "subscriptionEventList": [
      ""
    ],
    "remoteParent": "",
    "remoteParentAppguid": "",
    "remoteParentUrl": "",
    "attachmentCount": "",
    "attachments": [
      "{{CREATED_ITEM_UID}}"
    ],
    "attachmentTypes": [],
    "deadlineDate": "0001-01-01T00:00:00",
    "container": "",
    "relationType": "",
    "processAssignmentList": "",
    "processResources": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `startImmediately` | bool | Boolean value to say whether instance created should be immediately started 或 should be put into initial state for later starting by use of "Start" operation. No value implies true. (This argument is currently not sup… |
| `observerKey` | std::string | URI of observer that initiated 工作流进程 或 sub process at a 远程站点. observer is to be notified of events impacting execution of this process instance such as state changes, 及 most notably completion of instance. If not spec… |
| `name` | std::string | Name of remote process 或 sub process instance. |
| `subject` | std::string | A shorter description of purpose of remote process 或 sub process. |
| `description` | std::string | A longer description of purpose of remote process 或 sub process. |
| `contextData` | Teamcenter::Soa::Workflow::_2008_06::Workflow::ContextData | Context-specific data required to create a process 或 sub process at a local 或 a 远程站点 in Teamcenter. |

**响应（output）：**

```json
{
  "instanceKey": "",
  "newProcessDepTask": "",
  "newProcessUrl": "",
  "newProcessDepTaskUrl": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `instanceKey` | std::string | instanceKey. supported in future |
| `newProcessDepTask` | std::string | newProcessDepTask. supported in future |
| `newProcessUrl` | std::string | newProcessUrl. supported in future |
| `newProcessDepTaskUrl` | std::string | newProcessDepTaskUrl. supported in future |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData containing created process 及 errors if any |

---

#### 3.2.6 delegateSignoff（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/delegateSignoff`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 将签审委派给其他组成员（GroupMember）或资源池（ResourcePool）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.delegateSignoff`

**请求（input）：**

```json
{
  "delegatee": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "signoff": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `delegatee` | Teamcenter::BusinessObject |  group memebr 或 a resource pool tag to be delegated to. |
| `signoff` | Teamcenter::Signoff | 签审 object. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.7 getAllTasks（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/getAllTasks`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 获取指定工作流进程中的全部任务。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.getAllTasks`

**请求（input）：**

```json
{
  "process": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "state": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `process` | Teamcenter::EPMJob | 工作流进程 object |
| `state` | int | TODO |

**响应（output）：**

```json
{
  "allTasks": [
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
| `allTasks` | Teamcenter::EPMTask[] | allTasks |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data contains any 部分错误. |

---

#### 3.2.8 getAssignmentLists（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/getAssignmentLists`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据名称获取流程分配列表（Process Assignment List）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.getAssignmentLists`

**请求（input）：**

```json
{
  "names": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `names` | std::string[] | A set of process assignment list names |

**响应（output）：**

```json
{
  "assignedLists": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "ownedLists": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "groupLists": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "otherLists": [
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
| `assignedLists` | Teamcenter::EPMAssignmentList[] | assignedLists |
| `ownedLists` | Teamcenter::EPMAssignmentList[] | ownedLists |
| `groupLists` | Teamcenter::EPMAssignmentList[] | groupLists |
| `otherLists` | Teamcenter::EPMAssignmentList[] | otherLists |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data - returns index of input vector if call on that fails |

---

#### 3.2.9 getResourcePool（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/getResourcePool`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据组/角色引用获取常规或全部成员资源池（ResourcePool）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.getResourcePool`

**请求（input）：**

```json
{
  "groupRoleRef": [
    {
      "groupTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "roleTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "allowSubGroup": "",
      "isAllMembers": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `groupRoleRef` | Teamcenter::Soa::Workflow::_2008_06::Workflow::GroupRoleRef[] | 列表： GroupRoleRef 结构体，包含 info about Resource Pool being asked for |

**响应（output）：**

```json
{
  "resourcePoolInfo": [
    {
      "groupRoleRef": {
        "groupTag": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "roleTag": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "allowSubGroup": "",
        "isAllMembers": ""
      },
      "resourcePoolTag": {
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
| `resourcePoolInfo` | Teamcenter::Soa::Workflow::_2008_06::Workflow::ResourcePoolInfo[] | resourcePoolInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData |

---

#### 3.2.10 getWorkflowTemplates（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/getWorkflowTemplates`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据目标对象及筛选条件获取可用工作流模板列表。2008-06 与 2013-05 版本参数与筛选逻辑不同，调用时需匹配对应 API 版本。（当前 API 版本：`2008-06`）

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.getWorkflowTemplates`

**请求（input）：**

```json
{
  "targets": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "allOrAssignedCriteria": "SOA_EPM_All"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `targets` | Teamcenter::WorkspaceObject[] | 列表： 目标对象 to get 工作流模板 for |
| `allOrAssignedCriteria` | Teamcenter::Soa::Workflow::_2008_06::Workflow::AllOrAssigned | criteria to get all templates 或 assigned templates. |

**响应（output）：**

```json
{
  "workflowTemplates": [
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
| `workflowTemplates` | Teamcenter::EPMTaskTemplate[] | workflowTemplates |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data contains any 部分错误. |

---

#### 3.2.11 listDefinitions（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/listDefinitions`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 按名称、状态等条件列出流程模板定义。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.listDefinitions`

**请求（input）：**

```json
{
  "name": "",
  "templatestatus": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `name` | std::string | name of template to retrieve. This argument is 可选. Provide value null to make it 可选. |
| `templatestatus` | int | TODO |

**响应（output）：**

```json
{
  "output": [
    {
      "definitionkey": "",
      "name": "",
      "description": "",
      "version": "",
      "status": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Workflow::_2008_06::Workflow::DefinitionInfo[] | 数组： DefinitionInfo objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data contains any 部分错误. |

---

#### 3.2.12 performAction（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/performAction`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 对工作流任务执行操作（分配、启动、完成、跳过、挂起、恢复、撤销、执行、批准、拒绝、提升、降级等）。签审任务仅更新意见时可使用 `EPM_no_action`。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.performAction`

**请求（input）：**

```json
{
  "task": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "action": "SOA_EPM_assign_action",
  "comments": "",
  "password": "",
  "supportingValue": "SOA_EPM_no_decision",
  "supportingObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `task` | Teamcenter::EPMTask | 工作流任务 |
| `action` | Teamcenter::Soa::Workflow::_2008_06::Workflow::SoaEPMAction |  action to be performed on task required. possible values for action are defined in enum SoaEPMAction. They are SOA_EPM_assign_action, SOA_EPM_start_action, SOA_EPM_complete_action, SOA_EPM_skip_action, SOA_EPM_suspen… |
| `comments` | std::string | user comments. This argument is 可选. Provide value null to make it 可选. |
| `password` | std::string | password for secure 签审 action required for secure 签审. This argument is 可选. Provide value null to make it 可选(non secure). |
| `supportingValue` | Teamcenter::Soa::Workflow::_2008_06::Workflow::SoaEPMSupportingValues | this argument can be used to send in decision value 或 result. If task is perform 签审 task, provide decision using this argument. possible values for decision are SOA_EPM_no_decision, SOA_EPM_approve, SOA_EPM_reject. Fo… |
| `supportingObject` | Teamcenter::BusinessObject | If action is assign, provide a user tag 或 a resource pool tag to assign task to. If task is perform 签审 task, provide 签审 tag to set decision on. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.13 removeAttachments（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/removeAttachments`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 从工作流任务移除附件。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.removeAttachments`

**请求（input）：**

```json
{
  "task": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "attachments": [
    "{{CREATED_ITEM_UID}}"
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `task` | Teamcenter::EPMTask | 工作流任务 |
| `attachments` | Teamcenter::BusinessObject[] |  列表： 附件 to remove 附件 can be target_objects, reference_objects,release status etc |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.14 removeSignoffs（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/removeSignoffs`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 从工作流任务移除签审人。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.removeSignoffs`

**请求（input）：**

```json
{
  "signoffs": [
    {
      "task": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "removeSignoffObjs": [
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
| `signoffs` | Teamcenter::Soa::Workflow::_2008_06::Workflow::RemoveSignoffsInfo[] | 列表： 签审s - 结构体，包含 select 签审 task tag, groupmembers 或 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.15 viewAuditFile（2008-06）

**接口路径：** `Workflow-2008-06-Workflow/viewAuditFile`

**API 版本：** `2008-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 查看以文件形式存储的工作流审计信息（审计管理器开启时不可用）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2008_06.Workflow.viewAuditFile`

**请求（input）：**

```json
{
  "auditedObject": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "isSignoffReport": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `auditedObject` | Teamcenter::BusinessObject |  object to get audit info on. E.g. 工作区对象 in process 或 process itself.. |
| `isSignoffReport` | bool | Boolean to indicate if request is for a audit file 或 a 签审 report. true for a 签审 report, false for a audit file |

**响应（output）：**

```json
{
  "auditFiles": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `auditFiles` | std::string[] | auditFiles |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData |

---

### 3.3 API 版本 2010-09

**操作数：** 2

#### 3.3.1 applyTemplateToProcesses（2010-09）

**接口路径：** `Workflow-2010-09-Workflow/applyTemplateToProcesses`

**API 版本：** `2010-09`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 将指定模板应用到所有基于该模板旧版本的活动工作流进程（同步）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2010_09.Workflow.applyTemplateToProcesses`

**请求（input）：**

```json
{
  "applyTemplateInput": [
    {
      "clientId": "",
      "processTemplate": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "processingMode": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `applyTemplateInput` | Teamcenter::Soa::Workflow::_2010_09::Workflow::ApplyTemplateInput[] | Templates to be applied to active processes |
| `processingMode` | int | Indicates if request needs to be processed asynchronously. 0 - Indicates synchronous processing. 1 - Indicates asynchronous processing. |

**响应（output）：**

```json
{
  "applyTemplateOutput": [
    {
      "clientId": "",
      "updatedProcesses": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "failedProcesses": [
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
| `applyTemplateOutput` | Teamcenter::Soa::Workflow::_2010_09::Workflow::ApplyTemplateOutput[] | 列表： processes that were updated 及 列表： processes that failed. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data |

---

#### 3.3.2 applyTemplateToProcessesAsync（2010-09）

**接口路径：** `Workflow-2010-09-Workflow/applyTemplateToProcessesAsync`

**API 版本：** `2010-09`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 将指定模板应用到活动工作流进程（异步，无返回值）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2010_09.Workflow.applyTemplateToProcessesAsync`

**请求（input）：**

```json
{
  "applyTemplateInput": [
    {
      "clientId": "",
      "processTemplate": {
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
| `applyTemplateInput` | Teamcenter::Soa::Workflow::_2010_09::Workflow::ApplyTemplateInput[] | Templates to be applied to active processes. |

**响应（output）：**

```json
"void"
```

---

### 3.4 API 版本 2012-10

**操作数：** 1

#### 3.4.1 performAction2（2012-10）

**接口路径：** `Workflow-2012-10-Workflow/performAction2`

**API 版本：** `2012-10`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 对工作流任务执行操作（performAction 的升级版本，2012-10）。支持 Assign/Start/Complete/Approve/Reject 等。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2012_10.Workflow.performAction2`

**请求（input）：**

```json
{
  "task": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "action": "",
  "comments": "",
  "password": "",
  "supportingValue": "",
  "supportingObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `task` | Teamcenter::EPMTask | 工作流任务 on which action needs to be performed |
| `action` | std::string | Action to be performed on 工作流任务. Possible values for action are 以下: Action Description "SOA_EPM_assign_action" Assign task "SOA_EPM_start_action" Start task "SOA_EPM_complete_action" Mark task as Complete "SOA_EPM_ski… |
| `comments` | std::string | A comment assigned to this task action. This may be an empty string. |
| `password` | std::string |  password for a secure task. value of this parameter is ignored for non-secure tasks. |
| `supportingValue` | std::string | This argument can be used to send in decision value 或 result. If task is perform-签审 task, possible values for decision are: "SOA_EPM_no_decision" "SOA_EPM_approve" "SOA_EPM_reject" Following are result values applicab… |
| `supportingObject` | Teamcenter::BusinessObject | If action is assign , provide a user 或 resource pool to assign task. If task is perform-签审 task, provide 签审 object to set decision. If task is a perform-签审 task 及 action is claim , provide 签审 object to be claimed. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.5 API 版本 2013-05

**操作数：** 1

#### 3.5.1 getWorkflowTemplates（2013-05）

**接口路径：** `Workflow-2013-05-Workflow/getWorkflowTemplates`

**API 版本：** `2013-05`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据目标对象及筛选条件获取可用工作流模板列表。2008-06 与 2013-05 版本参数与筛选逻辑不同，调用时需匹配对应 API 版本。（当前 API 版本：`2013-05`）

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2013_05.Workflow.getWorkflowTemplates`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "includeUnderConstruction": "",
      "getFiltered": "",
      "targetObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "objectTypes": [
        ""
      ],
      "group": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2013_05::Workflow::GetWorkflowTemplatesInputInfo[] | Structure to define input for 工作流模板. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "templatesOutput": [
    {
      "clientId": "",
      "workflowTemplates": [
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
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据（ServiceData） contains any 部分错误. |
| `templatesOutput` | Teamcenter::Soa::Workflow::_2013_05::Workflow::GetWorkflowTemplatesOutput[] | Complete 列表： 工作流模板 Output. |

---

### 3.6 API 版本 2014-06

**操作数：** 5

#### 3.6.1 performAction3（2014-06）

**接口路径：** `Workflow-2014-06-Workflow/performAction3`

**API 版本：** `2014-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 对 EPMTask 或 Signoff 执行操作，并支持对目标对象进行数字签名（会话需 HTTPS）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_06.Workflow.performAction3`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "actionableObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "action": "",
      "password": "",
      "supportingValue": "",
      "supportingObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyNameValues": {},
      "signatures": [
        {
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "base64String": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2014_06::Workflow::PerformActionInputInfo[] | A 列表： PerformActionInputInfo structure which contains clientId, EPM 任务 或 签审 business object, action to be performed on an EPM 任务 或 签审 , password for a secure Task, supportingValue which can be used to send in decision… |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.6.2 performActionWithSignature（2014-06）

**接口路径：** `Workflow-2014-06-Workflow/performActionWithSignature`

**API 版本：** `2014-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 执行工作流任务操作并支持签名，适用于富客户端、瘦客户端及 Office 客户端任务处理。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_06.Workflow.performActionWithSignature`

**请求（input）：**

```json
{
  "task": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "action": "",
  "comments": "",
  "password": "",
  "supportingValue": "",
  "supportingObject": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "signatures": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "base64String": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `task` | Teamcenter::EPMTask | 工作流任务 on which action needs to be performed |
| `action` | std::string | Action to be performed on 工作流任务. Possible values for action are following: Action Description "SOA_EPM_assign_action" Assign task "SOA_EPM_start_action" Start task "SOA_EPM_complete_action" Mark task as Complete "SOA_… |
| `comments` | std::string | A comment assigned to this task action. This may be an empty string. |
| `password` | std::string |  password for secure task. value of this parameter is ignored for non-secured tasks. |
| `supportingValue` | std::string | This argument can be used to send in decision value 或 result. If task is a perform-签审s task, possible values for decision are: "SOA_EPM_no_decision" "SOA_EPM_approve" "SOA_EPM_reject" Folloing are result values applic… |
| `supportingObject` | Teamcenter::BusinessObject | If action is assign, provide a user 或 resource pool to assign task. If task is perform-签审 task, provide 签审 object to set decision. If task is a perform-签审 task 及 action is claim, provide 签审 object to be claimed. |
| `signatures` | Teamcenter::Soa::Workflow::_2014_06::Workflow::ApplySignatureInput[] | 列表： ApplySignatureInput objects, each representing 目标对象 及 its corresponding Base64 string. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.6.3 setActiveSurrogate（2014-06）

**接口路径：** `Workflow-2014-06-Workflow/setActiveSurrogate`

**API 版本：** `2014-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 设置/取消当前用户为指定 EPMTask 或 Signoff 的活动代理人，并可转移目标对象的检出状态。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_06.Workflow.setActiveSurrogate`

**请求（input）：**

```json
{
  "input": [
    {
      "taskOrSignoffTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "releaseStandIn": "",
      "transferCheckouts": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2014_06::Workflow::SetActiveSurrogateInputInfo[] | A 列表： SetActive代理人InputInfo structure which 包含 EPM 任务 或 签审 business object, boolean to indicate Stand-In 或 Release operation 及 boolean to indicate if checkout of 目标对象(s) should be transferred 或 not. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.6.4 setOutOfOffice（2014-06）

**接口路径：** `Workflow-2014-06-Workflow/setOutOfOffice`

**API 版本：** `2014-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 设置/取消用户外出（Out of Office）及代理人，在指定日期范围内将任务委派给另一用户或资源池。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_06.Workflow.setOutOfOffice`

**请求（input）：**

```json
{
  "fromResource": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "toResource": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "startDate": "0001-01-01T00:00:00",
  "endDate": "0001-01-01T00:00:00"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `fromResource` | Teamcenter::User |  User for whom 外出 will be set/unset. |
| `toResource` | Teamcenter::BusinessObject | A User 或 a 资源池 to be set as 外出 resource. |
| `startDate` | Teamcenter::DateTime |  effective start date of 外出 setting. |
| `endDate` | Teamcenter::DateTime |  effective end date of 外出 setting. Set to null (for C++ use DateTime::getNullDate()) to set 外出 to be indefinite (no end). |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.6.5 setSurrogate（2014-06）

**接口路径：** `Workflow-2014-06-Workflow/setSurrogate`

**API 版本：** `2014-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 为指定用户设置或取消代理人及生效日期范围。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_06.Workflow.setSurrogate`

**请求（input）：**

```json
{
  "requests": [
    {
      "unset": "",
      "fromResource": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toResource": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "startDate": "0001-01-01T00:00:00",
      "endDate": "0001-01-01T00:00:00"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `requests` | Teamcenter::Soa::Workflow::_2014_06::Workflow::SurrogateInput[] | A 列表： 代理人Input structures which contain original User, 代理人 User, effective start date, 及 end date. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.7 API 版本 2014-10

**操作数：** 2

#### 3.7.1 createRemoteWorkflowAsync（2014-10）

**接口路径：** `Workflow-2014-10-Workflow/createRemoteWorkflowAsync`

**API 版本：** `2014-10`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 通过 TcIF 异步提交在远程站点创建工作流的请求。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_10.Workflow.createRemoteWorkflowAsync`

**请求（input）：**

```json
{
  "createRemoteWkfInput": {
    "processName": "",
    "processDescription": "",
    "attachmentRelationTypes": [
      ""
    ],
    "processTemplate": "",
    "workflowOwner": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "responsibleParty": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "assignedUserList": [
      ""
    ],
    "dueDate": "0001-01-01T00:00:00",
    "sourceObject": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "site": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "attachments": [
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
| `createRemoteWkfInput` | Teamcenter::Soa::Workflow::_2014_10::Workflow::CreateRemoteWkfInput |  information used for remote workflow creation (e.g. name of 流程模板, workflow owner, responsible party, source object, 远程站点 , 附件, 及 附件 relations). |

**响应（output）：**

```json
"void"
```

---

#### 3.7.2 createWorkflow（2014-10）

**接口路径：** `Workflow-2014-10-Workflow/createWorkflow`

**API 版本：** `2014-10`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 根据模板名称、所有者、责任人、附件等创建工作流进程。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2014_10.Workflow.createWorkflow`

**请求（input）：**

```json
{
  "input": {
    "processName": "",
    "processDescription": "",
    "processTemplate": "",
    "workflowOwner": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "responsibleParty": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "assignedUserList": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "dueDate": "0001-01-01T00:00:00",
    "attachments": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "attachmentRelationTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2014_10::Workflow::CreateWkfInput |  process name, 流程模板 name, 工作流进程 owner, responsible party, assignees, due date, 附件, 及 附件 relations. |

**响应（output）：**

```json
{
  "workflowTask": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "attributes": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `workflowTask` | Teamcenter::BusinessObject | Workflow root task. |
| `attributes` | Teamcenter::Soa::Workflow::_2014_10::Workflow::NameValuePairs | A map (string/string) of workflow root task property names 及 values. (e.g. status, process instructions, task_result). |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data. |

---

### 3.8 API 版本 2015-07

**操作数：** 1

#### 3.8.1 addSignoffs（2015-07）

**接口路径：** `Workflow-2015-07-Workflow/addSignoffs`

**API 版本：** `2015-07`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 向工作流任务添加签审人。可添加临时签审、配置 Profile 签审，支持审阅/确认/通知等类型；2015-07 版支持地址列表与必选/可选评审人。注意：2008-06 与 2015-07 为不同 API 版本，参数结构有差异。（当前 API 版本：`2015-07`）

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2015_07.Workflow.addSignoffs`

**请求（input）：**

```json
{
  "signoffs": [
    {
      "task": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "signoffInfo": [
        {
          "signoffMember": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "origin": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "signoffAction": "",
          "originType": "",
          "signoffRequired": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `signoffs` | Teamcenter::Soa::Workflow::_2015_07::Workflow::CreateSignoffs[] | This is a 列表： Create签审s structures which contain Task for which 签审s need to be added 及 列表： Create签审Info 结构体，包含 requisite information to create 签审 object. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.9 API 版本 2019-06

**操作数：** 4

#### 3.9.1 createOrUpdateHandler（2019-06）

**接口路径：** `Workflow-2019-06-Workflow/createOrUpdateHandler`

**API 版本：** `2019-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 新建或更新工作流处理器（EPMHandler）实例，用于 Workflow Designer。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2019_06.Workflow.createOrUpdateHandler`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "handlerName": "",
      "taskTemplate": "",
      "businessRule": "",
      "handlerType": "",
      "handlerToUpdate": "",
      "action": "",
      "ruleQuorum": "",
      "changeExecutionOrder": "",
      "additionalData": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdateHandlerInput[] | A 列表： CreateUpdateHandlerInput stucture represents required inputs for creating a new 处理器 或 upating existing handlers. |

**响应（output）：**

```json
{
  "createdorUpdatedObjects": [
    {
      "clientID": "",
      "handlerObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "ruleObject": {
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
| `createdorUpdatedObjects` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdateHandlerOutput[] | A 列表： CreateUpdateHandlerOutput structure. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData |  service data. |

---

#### 3.9.2 createOrUpdatePAL（2019-06）

**接口路径：** `Workflow-2019-06-Workflow/createOrUpdatePAL`

**API 版本：** `2019-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 新建、更新或深拷贝流程分配列表（EPMAssignmentList / PAL），供 Handler 或提交工作流面板使用。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2019_06.Workflow.createOrUpdatePAL`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "palName": "",
      "workflowTemplate": "",
      "palDescription": [
        ""
      ],
      "resourceLists": [
        {
          "taskTemplate": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "templateResources": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "profiles": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "actions": [],
          "revQuorum": "",
          "ackQuorum": ""
        }
      ],
      "additionalData": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdatePALInput[] | A 列表： CreateUpdatePALInput stucture used to update 或 copy EPMAssignmentList 或 to create a new EPMAssignmentList . |

**响应（output）：**

```json
{
  "createdorUpdatedObjects": [
    {
      "clientID": "",
      "palObject": {
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
| `createdorUpdatedObjects` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdatePALOutput[] | A 列表： CreateUpdatePALOutput structure. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData |  service data. |

---

#### 3.9.3 createOrUpdateTemplate（2019-06）

**接口路径：** `Workflow-2019-06-Workflow/createOrUpdateTemplate`

**API 版本：** `2019-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 新建或更新工作流任务模板（EPMTaskTemplate），用于 Workflow Designer。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2019_06.Workflow.createOrUpdateTemplate`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "templateName": "",
      "templateDesc": "",
      "baseTemplate": "",
      "parentTemplate": "",
      "templateToUpdate": "",
      "additionalData": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdateTemplateInput[] | A 列表： CreateUpdateTemplateInput stucture represents required inputs for creating a new task template 或 upating existing task template. |

**响应（output）：**

```json
{
  "createdorUpdatedObjects": [
    {
      "clientID": "",
      "templateObject": {
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
| `createdorUpdatedObjects` | Teamcenter::Soa::Workflow::_2019_06::Workflow::CreateUpdateTemplateOutput[] | A 列表： CreateUpdateTemplateOutput structure. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData |  service data. |

---

#### 3.9.4 getRegisteredHandlers（2019-06）

**接口路径：** `Workflow-2019-06-Workflow/getRegisteredHandlers`

**API 版本：** `2019-06`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 返回已注册的工作流 Handler 名称列表，供创建 Handler 实例时选择。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2019_06.Workflow.getRegisteredHandlers`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "actionHandlers": [
    ""
  ],
  "ruleHandlers": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `actionHandlers` | std::string[] | A 列表： names of registered action handlers. |
| `ruleHandlers` | std::string[] | A 列表： names of registered rule handlers. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData |  service data. |

---

### 3.10 API 版本 2020-01

**操作数：** 1

#### 3.10.1 getSupportedHandlerArguments（2020-01）

**接口路径：** `Workflow-2020-01-Workflow/getSupportedHandlerArguments`

**API 版本：** `2020-01`  
**Service：** `Workflow`  
**Library：** `Workflow`

**说明：** 从 `TC_DATA/workflow_handlers/<handler>.json` 读取 Handler 参数提示（必填、可选、互斥、依赖等）。

**Soa Inclusion：** `Teamcenter.Soa.Workflow._2020_01.Workflow.getSupportedHandlerArguments`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "handlerName": "",
      "additionalData": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Workflow::_2020_01::Workflow::SupportedHandlerArgumentsInput[] | A 列表： SupportedHandlerArgumentsInput stucture that represent input 处理器 name. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "handlerData": "",
      "additionalData": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Workflow::_2020_01::Workflow::SupportedHandlerArgumentsInfoOutput[] | 列表： SupportedHandlerArgumentsInfoOutput structure which contains 处理器 data info. |

---

---

## 4. 附录

### 操作一览

| API 版本 | 操作 | Url | Soa Inclusion |
|----------|------|-----|---------------|
| 2007-06 | `setReleaseStatus` | `Workflow-2007-06-Workflow/setReleaseStatus` | `Teamcenter.Soa.Workflow._2007_06.Workflow.setReleaseStatus` |
| 2008-06 | `addAttachments` | `Workflow-2008-06-Workflow/addAttachments` | `Teamcenter.Soa.Workflow._2008_06.Workflow.addAttachments` |
| 2008-06 | `addSignoffs` | `Workflow-2008-06-Workflow/addSignoffs` | `Teamcenter.Soa.Workflow._2008_06.Workflow.addSignoffs` |
| 2008-06 | `assignAllTasks` | `Workflow-2008-06-Workflow/assignAllTasks` | `Teamcenter.Soa.Workflow._2008_06.Workflow.assignAllTasks` |
| 2008-06 | `changeState` | `Workflow-2008-06-Workflow/changeState` | `Teamcenter.Soa.Workflow._2008_06.Workflow.changeState` |
| 2008-06 | `createInstance` | `Workflow-2008-06-Workflow/createInstance` | `Teamcenter.Soa.Workflow._2008_06.Workflow.createInstance` |
| 2008-06 | `delegateSignoff` | `Workflow-2008-06-Workflow/delegateSignoff` | `Teamcenter.Soa.Workflow._2008_06.Workflow.delegateSignoff` |
| 2008-06 | `getAllTasks` | `Workflow-2008-06-Workflow/getAllTasks` | `Teamcenter.Soa.Workflow._2008_06.Workflow.getAllTasks` |
| 2008-06 | `getAssignmentLists` | `Workflow-2008-06-Workflow/getAssignmentLists` | `Teamcenter.Soa.Workflow._2008_06.Workflow.getAssignmentLists` |
| 2008-06 | `getResourcePool` | `Workflow-2008-06-Workflow/getResourcePool` | `Teamcenter.Soa.Workflow._2008_06.Workflow.getResourcePool` |
| 2008-06 | `getWorkflowTemplates` | `Workflow-2008-06-Workflow/getWorkflowTemplates` | `Teamcenter.Soa.Workflow._2008_06.Workflow.getWorkflowTemplates` |
| 2008-06 | `listDefinitions` | `Workflow-2008-06-Workflow/listDefinitions` | `Teamcenter.Soa.Workflow._2008_06.Workflow.listDefinitions` |
| 2008-06 | `performAction` | `Workflow-2008-06-Workflow/performAction` | `Teamcenter.Soa.Workflow._2008_06.Workflow.performAction` |
| 2008-06 | `removeAttachments` | `Workflow-2008-06-Workflow/removeAttachments` | `Teamcenter.Soa.Workflow._2008_06.Workflow.removeAttachments` |
| 2008-06 | `removeSignoffs` | `Workflow-2008-06-Workflow/removeSignoffs` | `Teamcenter.Soa.Workflow._2008_06.Workflow.removeSignoffs` |
| 2008-06 | `viewAuditFile` | `Workflow-2008-06-Workflow/viewAuditFile` | `Teamcenter.Soa.Workflow._2008_06.Workflow.viewAuditFile` |
| 2010-09 | `applyTemplateToProcesses` | `Workflow-2010-09-Workflow/applyTemplateToProcesses` | `Teamcenter.Soa.Workflow._2010_09.Workflow.applyTemplateToProcesses` |
| 2010-09 | `applyTemplateToProcessesAsync` | `Workflow-2010-09-Workflow/applyTemplateToProcessesAsync` | `Teamcenter.Soa.Workflow._2010_09.Workflow.applyTemplateToProcessesAsync` |
| 2012-10 | `performAction2` | `Workflow-2012-10-Workflow/performAction2` | `Teamcenter.Soa.Workflow._2012_10.Workflow.performAction2` |
| 2013-05 | `getWorkflowTemplates` | `Workflow-2013-05-Workflow/getWorkflowTemplates` | `Teamcenter.Soa.Workflow._2013_05.Workflow.getWorkflowTemplates` |
| 2014-06 | `performAction3` | `Workflow-2014-06-Workflow/performAction3` | `Teamcenter.Soa.Workflow._2014_06.Workflow.performAction3` |
| 2014-06 | `performActionWithSignature` | `Workflow-2014-06-Workflow/performActionWithSignature` | `Teamcenter.Soa.Workflow._2014_06.Workflow.performActionWithSignature` |
| 2014-06 | `setActiveSurrogate` | `Workflow-2014-06-Workflow/setActiveSurrogate` | `Teamcenter.Soa.Workflow._2014_06.Workflow.setActiveSurrogate` |
| 2014-06 | `setOutOfOffice` | `Workflow-2014-06-Workflow/setOutOfOffice` | `Teamcenter.Soa.Workflow._2014_06.Workflow.setOutOfOffice` |
| 2014-06 | `setSurrogate` | `Workflow-2014-06-Workflow/setSurrogate` | `Teamcenter.Soa.Workflow._2014_06.Workflow.setSurrogate` |
| 2014-10 | `createRemoteWorkflowAsync` | `Workflow-2014-10-Workflow/createRemoteWorkflowAsync` | `Teamcenter.Soa.Workflow._2014_10.Workflow.createRemoteWorkflowAsync` |
| 2014-10 | `createWorkflow` | `Workflow-2014-10-Workflow/createWorkflow` | `Teamcenter.Soa.Workflow._2014_10.Workflow.createWorkflow` |
| 2015-07 | `addSignoffs` | `Workflow-2015-07-Workflow/addSignoffs` | `Teamcenter.Soa.Workflow._2015_07.Workflow.addSignoffs` |
| 2019-06 | `createOrUpdateHandler` | `Workflow-2019-06-Workflow/createOrUpdateHandler` | `Teamcenter.Soa.Workflow._2019_06.Workflow.createOrUpdateHandler` |
| 2019-06 | `createOrUpdatePAL` | `Workflow-2019-06-Workflow/createOrUpdatePAL` | `Teamcenter.Soa.Workflow._2019_06.Workflow.createOrUpdatePAL` |
| 2019-06 | `createOrUpdateTemplate` | `Workflow-2019-06-Workflow/createOrUpdateTemplate` | `Teamcenter.Soa.Workflow._2019_06.Workflow.createOrUpdateTemplate` |
| 2019-06 | `getRegisteredHandlers` | `Workflow-2019-06-Workflow/getRegisteredHandlers` | `Teamcenter.Soa.Workflow._2019_06.Workflow.getRegisteredHandlers` |
| 2020-01 | `getSupportedHandlerArguments` | `Workflow-2020-01-Workflow/getSupportedHandlerArguments` | `Teamcenter.Soa.Workflow._2020_01.Workflow.getSupportedHandlerArguments` |

### 典型流程

**启动工作流：**
1. `getWorkflowTemplates` — 获取可用模板（按目标对象筛选）
2. `createInstance` 或 `createWorkflow` — 创建流程实例
3. `assignAllTasks` — 应用分配列表（可选）

**处理收件箱任务：**
1. `performAction` / `performAction2` / `performAction3` — 执行任务动作
2. `addSignoffs` — 添加签审人（可选）
3. `delegateSignoff` — 委派签审（可选）

**Workflow Designer（2019-06+）：**
1. `getRegisteredHandlers` — 获取已注册 Handler
2. `getSupportedHandlerArguments` — 获取 Handler 参数提示
3. `createOrUpdateTemplate` / `createOrUpdateHandler` / `createOrUpdatePAL`

### 重新生成

```bash
node generate-workflow-doc.js
```
