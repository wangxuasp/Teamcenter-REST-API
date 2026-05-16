# Teamcenter REST API 接口请求体定义文档

> 所有接口均为 **POST** 方法，请求体格式为 JSON。  
> 公共结构：每个请求体顶层包含 `header`（含 `state` 和 `policy`）与 `body` 两部分。

---

## 目录

1. [认证（Session）](#1-认证session)
2. [查询数据（Get Data）](#2-查询数据get-data)
3. [创建数据（Create Data）](#3-创建数据create-data)
4. [BOM 管理](#4-bom-管理)

---

## 1. 认证（Session）

### 1.1 登录 `login`

**接口路径：** `tc/JsonRestServices/Core-2011-06-Session/login`

**说明：** 用户登录，获取会话 Cookie（含 XSRF-TOKEN）。

```json
{
  "header": {
    "state": {},
    "policy": {}
  },
  "body": {
    "credentials": {
      "user": "{{USER_NAME}}",
      "password": "{{USER_PASSWORD}}",
      "role": "",
      "descrimator": "",
      "locale": "",
      "group": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `user` | string | 用户名 |
| `password` | string | 密码 |
| `role` | string | 角色（可为空） |
| `descrimator` | string | 客户端标识符（注意：原文拼写如此） |
| `locale` | string | 语言区域（如 `zh_CN`，可为空） |
| `group` | string | 用户组（可为空） |

---

## 2. 查询数据（Get Data）

### 2.1 获取会话信息 `getTCSessionInfo`

**接口路径：** `tc/JsonRestServices/Core-2007-01-Session/getTCSessionInfo`

**说明：** 获取当前登录用户的会话信息（用户 UID、HomeFolder UID 等）。

```json
{
  "header": {
    "state": {},
    "policy": {}
  }
}
```

> 无 `body`，仅需 header。

---

### 2.2 获取收藏夹 `getFavorites`

**接口路径：** `tc/JsonRestServices/Core-2008-03-Session/getFavorites`

**说明：** 获取当前用户的收藏对象列表。

```json
{
  "header": {
    "state": {},
    "policy": {}
  }
}
```

---

### 2.3 获取对象属性 `getProperties`

**接口路径：** `tc/JsonRestServices/Core-2006-03-DataManagement/getProperties`

**说明：** 获取指定对象的属性。支持批量对象查询，`attributes` 为空时返回所有属性。

**示例一：获取主文件夹属性**

```json
{
  "header": {
    "state": {},
    "policy": {}
  },
  "body": {
    "objects": [
      {
        "uid": "{{HOME_FOLDER_UID}}",
        "className": "Folder",
        "type": "Fnd0HomeFolder"
      }
    ],
    "attributes": ""
  }
}
```

**示例二：获取用户指定属性**

```json
{
  "header": {
    "state": {},
    "policy": {}
  },
  "body": {
    "objects": [
      {
        "uid": "{{USER_UID}}",
        "className": "User",
        "type": "User"
      }
    ],
    "attributes": ["user_id", "person", "os_username", "last_login_time", "volume", "home_folder"]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `objects[].uid` | string | 对象 UID |
| `objects[].className` | string | 基类名，如 `Folder`、`User` |
| `objects[].type` | string | 具体类型，如 `Fnd0HomeFolder`、`User` |
| `attributes` | string 或 array | 空字符串 `""` = 返回所有属性；数组 = 仅返回指定属性 |

---

### 2.4 获取已保存查询 `getSavedQueries`

**接口路径：** `tc/JsonRestServices/Query-2006-03-SavedQuery/getSavedQueries`

**说明：** 返回系统中所有已保存的查询列表。

```json
{
  "header": {
    "state": {},
    "policy": {}
  }
}
```

---

### 2.5 执行搜索 `performSearch`

**接口路径：** `tc/JsonRestServices/Query-2012-10-Finder/performSearch`

**说明：** 使用指定搜索提供者执行对象搜索。`policy.types` 定义需要返回的属性策略。

```json
{
  "header": {
    "state": {},
    "policy": {
      "useRefCount": false,
      "types": [
        {
          "name": "ItemRevision",
          "properties": [
            { "name": "object_desc" },
            { "name": "item_id" },
            { "name": "item_revision_id" },
            { "name": "object_name" },
            { "name": "creation_date" },
            { "name": "date_released" },
            {
              "name": "release_status_list",
              "modifiers": [{ "name": "withProperties", "Value": "true" }]
            }
          ]
        }
      ]
    }
  },
  "body": {
    "searchInput": {
      "maxToLoad": 500,
      "maxToReturn": 500,
      "providerName": "Awp0SavedQuerySearchProvider",
      "searchCriteria": {
        "queryUID": "{{QUERY_UID}}",
        "searchID": "",
        "typeOfSearch": "ADVANCED_SEARCH",
        "utcOffset": "-420",
        "lastEndIndex": "",
        "totalObjectsFoundReportedToClient": "",
        "ItemID": "*",
        "Type": "ItemRevision"
      },
      "searchFilterFieldSortType": "Priority",
      "startIndex": 0,
      "searchFilterMap6": {},
      "searchSortCriteria": [],
      "attributesToInflate": [],
      "inflateProperties": false,
      "focusObjUid": "",
      "pagingType": ""
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `providerName` | string | 搜索提供者，如 `Awp0SavedQuerySearchProvider`、`Awp0InboxProvider` |
| `maxToLoad` | int | 最大加载数量 |
| `maxToReturn` | int | 最大返回数量 |
| `searchCriteria.typeOfSearch` | string | `ADVANCED_SEARCH` 或 `QUICK_SEARCH` |
| `searchCriteria.queryUID` | string | 已保存查询的 UID |
| `startIndex` | int | 分页起始索引 |

---

### 2.6 获取收件箱 `performSearch`（Inbox）

**接口路径：** `tc/JsonRestServices/Query-2012-10-Finder/performSearch`

**说明：** 同 `performSearch`，但使用 `Awp0InboxProvider` 获取当前用户工作流收件箱任务。

```json
{
  "header": {
    "state": {},
    "policy": { "useRefCount": false, "types": [...] }
  },
  "body": {
    "searchInput": {
      "maxToLoad": 50,
      "maxToReturn": 50,
      "providerName": "Awp0InboxProvider",
      "searchCriteria": {
        "searchInboxContentType": "myTasks",
        "searchString": ""
      },
      "searchFilterFieldSortType": "Priority",
      "startIndex": 0,
      "searchFilterMap6": {},
      "searchSortCriteria": [],
      "attributesToInflate": [],
      "inflateProperties": false,
      "focusObjUid": "",
      "pagingType": ""
    }
  }
}
```

| 字段 | 说明 |
|------|------|
| `providerName` | 固定为 `Awp0InboxProvider` |
| `searchInboxContentType` | `myTasks`（我的任务）等 |

---

## 3. 创建数据（Create Data）

### 3.1 创建文件夹 `createFolders`

**接口路径：** `tc/JsonRestServices/Core-2006-03-DataManagement/createFolders`

```json
{
  "header": {
    "state": {},
    "policy": {}
  },
  "body": {
    "folders": [
      {
        "clientId": "",
        "name": "{{FOLDER_NAME}}",
        "desc": "{{FOLDER_DESC}}"
      }
    ],
    "container": {
      "uid": "{{HOME_FOLDER_UID}}",
      "className": "Folder",
      "type": "Fnd0HomeFolder"
    },
    "relationType": "contents"
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `folders[].name` | string | 文件夹名称 |
| `folders[].desc` | string | 描述 |
| `container.uid` | string | 父容器 UID |
| `relationType` | string | 关系类型，通常为 `contents` |

---

### 3.2 创建 Item `createItems`

**接口路径：** `tc/JsonRestServices/Core-2006-03-DataManagement/createItems`

```json
{
  "header": {
    "state": {},
    "policy": {}
  },
  "body": {
    "properties": [
      {
        "clientId": "",
        "itemId": "",
        "name": "{{ITEM_NAME}}",
        "type": "{{ITEM_TYPE}}",
        "revId": "{{ITEM_REVID}}",
        "uom": "",
        "description": "{{ITEM_DESC}}",
        "extendedAttributes": [
          {
            "objectType": "",
            "attributes": {
              "SampleStringKey": ""
            }
          }
        ]
      }
    ],
    "container": {
      "uid": "{{HOME_FOLDER_UID}}",
      "className": "Folder",
      "type": "Fnd0HomeFolder"
    },
    "relationType": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `properties[].itemId` | string | Item 编号（空则自动生成） |
| `properties[].name` | string | Item 名称 |
| `properties[].type` | string | Item 类型（如 `Item`、自定义类型） |
| `properties[].revId` | string | 版本号（如 `A`） |
| `properties[].extendedAttributes` | array | 扩展属性（可为空数组） |
| `container` | object | 放置位置（通常为 HomeFolder） |

---

### 3.3 创建数据集 `createDatasets`

**接口路径：** `tc/RestServices/Core-2010-04-DataManagement/createDatasets`

**说明：** 注意此接口使用 `RestServices`（非 `JsonRestServices`），且 body 层级直接使用 `input`（无 `body` 包裹）。

```json
{
  "header": {
    "state": {},
    "policy": {}
  },
  "input": [
    {
      "clientId": "",
      "container": {
        "uid": "",
        "type": ""
      },
      "datasetFileInfos": [
        {
          "fileName": "test-pdf-file.pdf",
          "namedReferenceName": "PDF_Reference",
          "isText": false,
          "clientId": "",
          "allowReplace": false
        }
      ],
      "relationType": "",
      "name": "test-pdf-file.pdf",
      "type": "PDF",
      "description": "",
      "datasetId": "",
      "datasetRev": "",
      "toolUsed": "",
      "attrs": [],
      "nrObjectInfos": []
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input[].name` | string | 数据集名称 |
| `input[].type` | string | 数据集类型（如 `PDF`、`UGMASTER`） |
| `input[].datasetFileInfos[].fileName` | string | 文件名 |
| `input[].datasetFileInfos[].namedReferenceName` | string | 命名引用（如 `PDF_Reference`） |
| `input[].datasetFileInfos[].isText` | bool | 是否为文本文件 |

---

### 3.4 上传文件 `fmsupload`

**接口路径：** `fms/fmsupload`

**说明：** 文件上传到 FMS（File Management System），使用 multipart 表单方式提交，无 JSON 请求体。上传成功后返回 FMS Ticket，供后续 commitDatasetFiles 使用。

---

### 3.5 提交数据集文件 `commitDatasetFiles`

**接口路径：** `tc/RestServices/Core-2006-03-FileManagement/commitDatasetFiles`

**说明：** 将已上传到 FMS 的文件与数据集关联提交。

```json
{
  "header": {
    "state": {},
    "policy": {}
  },
  "body": {
    "commitInput": [
      {
        "dataset": {
          "uid": "",
          "type": "{{DATASET_TYPE}}"
        },
        "createNewVersion": false,
        "datasetFileTicketInfos": [
          {
            "datasetFileInfo": {
              "clientId": "",
              "fileName": "{{FILENAME}}",
              "namedReferencedName": "{{DATASET_NAMED_REFERENCE}}",
              "isText": false,
              "allowReplace": false
            },
            "ticket": "{{FMS_TICKET_out}}"
          }
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `dataset.uid` | string | 数据集 UID（createDatasets 返回） |
| `ticket` | string | FMS 上传返回的 Ticket |
| `namedReferencedName` | string | 与 createDatasets 中 `namedReferenceName` 对应 |

---

### 3.6 创建关系 `createRelations`

**接口路径：** `tc/JsonRestServices/Core-2006-03-DataManagement/createRelations`

**说明：** 在主对象与次对象之间建立关系，例如将 Dataset 关联到 ItemRevision。

```json
{
  "header": {
    "state": {},
    "policy": {}
  },
  "body": {
    "input": [
      {
        "primaryObject": {
          "uid": "{{CREATED_ITEMREV_UID_out}}",
          "type": "ItemRevision"
        },
        "secondaryObject": {
          "uid": "{{CREATED_DATASET_UID_out}}",
          "type": "{{DATASET_TYPE}}"
        },
        "relationType": "{{RELATION_TYPE}}",
        "clientId": "",
        "userData": {
          "uid": "",
          "type": ""
        }
      }
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `primaryObject.uid` | string | 主对象 UID（如 ItemRevision） |
| `secondaryObject.uid` | string | 次对象 UID（如 Dataset） |
| `relationType` | string | 关系类型（如 `IMAN_specification`） |

---

### 3.7 启动工作流 `createInstance`

**接口路径：** `tc/JsonRestServices/Workflow-2008-06-Workflow/createInstance`

```json
{
  "header": {
    "state": {},
    "policy": {}
  },
  "body": {
    "startImmediately": true,
    "observerKey": "",
    "name": "工作流名称",
    "subject": "",
    "description": "",
    "contextData": {
      "processTemplate": "{{WF_TEMPLATE_NAME}}",
      "attachmentCount": 1,
      "attachments": ["{{CREATED_ITEM_UID}}"],
      "attachmentTypes": [1],
      "processOwner": "",
      "dependencyTask": "",
      "subscribeToEvents": false,
      "subscriptionEventCount": 0,
      "subscriptionEventList": [],
      "remoteParent": "",
      "remoteParentAppguid": "",
      "remoteParentUrl": "",
      "deadlineDate": "",
      "container": "",
      "relationType": "",
      "processAssignmentList": "",
      "processResources": []
    }
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `startImmediately` | bool | 是否立即启动 |
| `contextData.processTemplate` | string | 工作流模板名称 |
| `contextData.attachments` | array | 附件对象 UID 列表 |
| `contextData.attachmentTypes` | array | 附件类型（1 = Target） |

---

## 4. BOM 管理

BOM 操作需按步骤顺序执行。

### 4.1 根据 ItemID 获取 Item UID `getItemFromId`

**接口路径：** `tc/JsonRestServices/Core-2007-01-DataManagement/getItemFromId`

```json
{
  "header": {
    "state": {},
    "policy": {}
  },
  "body": {
    "infos": [
      {
        "itemId": "{{ROOT_BOM_ITEM_ID}}",
        "revIds": ["A"]
      }
    ],
    "nRev": 1,
    "pref": {}
  }
}
```

| 字段 | 说明 |
|------|------|
| `itemId` | Item 编号 |
| `revIds` | 版本号列表（`A`、`B` 等） |
| `nRev` | 返回最近 N 个版本 |

---

### 4.2 创建 BOM 窗口 `createBOMWindows`

**接口路径：** `tc/JsonRestServices/Cad-2007-01-StructureManagement/createBOMWindows`

**说明：** `header.state` 需要设置 `stateless: true`。

```json
{
  "header": {
    "state": {
      "formatProperties": true,
      "stateless": true,
      "unloadObjects": false,
      "enableServerStateHeaders": true,
      "locale": "en_US"
    },
    "policy": {}
  },
  "body": {
    "info": [
      {
        "clientId": "",
        "item": "{{ROOT_BOM_ITEM_UID_out}}",
        "revRuleConfigInfo": {
          "clientId": "",
          "revRule": "",
          "props": {
            "unitNo": -1,
            "date": "0001-01-01T00:00:00",
            "today": true,
            "endItem": "",
            "endItemRevision": ""
          }
        }
      }
    ]
  }
}
```

| 字段 | 说明 |
|------|------|
| `info[].item` | Item UID（非 ItemRevision） |
| `revRuleConfigInfo.revRule` | 版本规则 UID（空则使用默认） |
| `props.today` | `true` = 使用当天有效性 |

---

### 4.3 展开 BOM `expandPSAllLevels`

**接口路径：** `tc/JsonRestServices/Cad-2007-01-StructureManagement/expandPSAllLevels`

**说明：** 展开 BOM 窗口所有层级，`policy.types` 控制返回哪些属性。

```json
{
  "header": {
    "state": {
      "formatProperties": true,
      "stateless": true,
      "unloadObjects": false,
      "enableServerStateHeaders": true,
      "locale": "en_US"
    },
    "policy": {
      "types": [
        {
          "name": "ItemRevision",
          "properties": [
            { "name": "item_id" },
            { "name": "item_revision_id" },
            { "name": "object_name" },
            { "name": "owning_user" },
            { "name": "last_mod_date" }
          ]
        }
      ]
    }
  },
  "body": {
    "input": {
      "parentBomLines": ["{{ROOT_BOM_ITEM_BOMLine_UID_out}}"],
      "excludeFilter": "None"
    },
    "pref": {
      "expItemRev": false
    }
  }
}
```

| 字段 | 说明 |
|------|------|
| `parentBomLines` | BOM 根行 UID（createBOMWindows 返回） |
| `excludeFilter` | 过滤器（`None` = 不过滤） |
| `pref.expItemRev` | 是否展开 ItemRevision |

---

### 4.4 向 BOM 添加子行 `addOrUpdateChildrenToParentLine`

**接口路径：** `tc/JsonRestServices/Bom-2008-06-StructureManagement/addOrUpdateChildrenToParentLine`

```json
{
  "header": {
    "state": {
      "formatProperties": true,
      "stateless": true,
      "unloadObjects": false,
      "enableServerStateHeaders": true,
      "locale": "en_US"
    },
    "policy": {}
  },
  "body": {
    "inputs": [
      {
        "parentLine": "{{ROOT_BOM_ITEM_BOMLine_UID_out}}",
        "viewType": "",
        "items": [
          {
            "clientId": "",
            "item": "",
            "itemRev": "{{CREATED_ITEMREV_UID_out}}",
            "occType": "",
            "bomline": "",
            "itemLineProperties": {
              "SampleStringKey": ""
            }
          }
        ],
        "itemElements": [
          {
            "clientId": "",
            "itemElement": "",
            "occType": "",
            "itemElementline": "",
            "itemElementLineProperties": {
              "SampleStringKey": ""
            }
          }
        ]
      }
    ]
  }
}
```

| 字段 | 说明 |
|------|------|
| `parentLine` | 父 BOM 行 UID |
| `items[].itemRev` | 要添加的 ItemRevision UID |
| `items[].occType` | 发生类型（可为空） |

---

### 4.5 保存 BOM 窗口 `saveBOMWindows`

**接口路径：** `tc/JsonRestServices/Cad-2008-06-StructureManagement/saveBOMWindows`

```json
{
  "header": {
    "state": {
      "formatProperties": true,
      "stateless": true,
      "unloadObjects": false,
      "enableServerStateHeaders": true,
      "locale": "en_US"
    },
    "policy": {}
  },
  "body": {
    "bomWindows": ["{{ROOT_BOM_ITEM_BOM_WINDOW_UID_out}}"]
  }
}
```

---

### 4.6 关闭 BOM 窗口 `closeBOMWindows`

**接口路径：** `tc/JsonRestServices/Cad-2007-01-StructureManagement/closeBOMWindows`

```json
{
  "header": {
    "state": {
      "formatProperties": true,
      "stateless": true,
      "unloadObjects": false,
      "enableServerStateHeaders": true,
      "locale": "en_US"
    },
    "policy": {}
  },
  "body": {
    "bomWindows": ["{{ROOT_BOM_ITEM_BOM_WINDOW_UID_out}}"]
  }
}
```

---

### 4.7 获取版本规则列表 `getRevisionRules`

**接口路径：** `tc/JsonRestServices/Cad-2007-01-StructureManagement/getRevisionRules`

**说明：** 获取系统中所有可用的版本规则，用于在创建 BOM 窗口时指定 `revRule`。

```json
{
  "header": {
    "state": {
      "formatProperties": true,
      "stateless": true,
      "unloadObjects": false,
      "enableServerStateHeaders": true,
      "locale": "en_US"
    },
    "policy": {
      "types": [
        {
          "name": "RevisionRule",
          "properties": [
            { "name": "object_name" }
          ]
        }
      ]
    }
  }
}
```

---

## 附录：公共字段说明

### header.state 常用字段

| 字段 | 类型 | 说明 |
|------|------|------|
| `formatProperties` | bool | 是否格式化属性值 |
| `stateless` | bool | 无状态模式（BOM 操作需要设为 `true`） |
| `unloadObjects` | bool | 响应后是否卸载对象 |
| `enableServerStateHeaders` | bool | 启用服务器状态头 |
| `locale` | string | 语言区域（如 `en_US`） |

### header.policy 常用字段

| 字段 | 类型 | 说明 |
|------|------|------|
| `types` | array | 指定需要返回属性的对象类型列表 |
| `useRefCount` | bool | 是否使用引用计数 |
| `types[].properties[].modifiers` | array | 属性修饰符，如 `withProperties: true`（关联对象同时返回属性） |

### 典型调用流程

**数据集上传完整流程：**
1. `login` → 获取 Cookie
2. `createItems` → 获取 ItemRevision UID
3. `createDatasets` → 获取 Dataset UID 和 FMS Ticket
4. `fmsupload` → 上传文件，获取新 FMS Ticket
5. `commitDatasetFiles` → 提交文件
6. `createRelations` → 建立 ItemRevision ↔ Dataset 关联

**BOM 查看完整流程：**
1. `login` → 获取 Cookie
2. `getItemFromId` → 获取 Item UID
3. `createBOMWindows` → 获取 BOM Window UID 和 BOMLine UID
4. `expandPSAllLevels` → 展开 BOM 获取所有层级数据
5. `closeBOMWindows` → 关闭 BOM 窗口（释放资源）
