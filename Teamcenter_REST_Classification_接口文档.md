# Teamcenter SOA API — Classification 接口文档（TC 2512）

> 本文档汇总 **Classification** Library 下全部 **API 版本（年-月）**，按版本与 Service 双向合并。**功能说明（接口级）与参数表（字段级）均已中文化**。
> Teamcenter TC 2512（`structure.js`）：共 **29** 个操作，API 契约版本 **2007-01～2016-09**，共 **8** 个月份版本。
>
> **Url：** `Classification-{Year}-Classification/{operation}`（Service 名恒为 `Classification`）

---

## 目录

1. [API 版本总览](#1-api-版本总览)
2. [按 Service 合并（跨版本）](#2-按-service-合并跨版本)
3. [按 API 版本（年-月）归档](#3-按-api-版本年-月归档)
4. [附录](#4-附录)

---

## 1. API 版本总览

| API 版本 | 操作名 | Url |
|----------|--------|-----|
| **2007-01** | `createClassificationObjects` | `Classification-2007-01-Classification/createClassificationObjects` |
| **2007-01** | `deleteClassificationObjects` | `Classification-2007-01-Classification/deleteClassificationObjects` |
| **2007-01** | `findClassificationObjects` | `Classification-2007-01-Classification/findClassificationObjects` |
| **2007-01** | `findClassifiedObjects` | `Classification-2007-01-Classification/findClassifiedObjects` |
| **2007-01** | `getAttributesForClasses` | `Classification-2007-01-Classification/getAttributesForClasses` |
| **2007-01** | `getChildren` | `Classification-2007-01-Classification/getChildren` |
| **2007-01** | `getClassDescriptions` | `Classification-2007-01-Classification/getClassDescriptions` |
| **2007-01** | `getClassificationObjects` | `Classification-2007-01-Classification/getClassificationObjects` |
| **2007-01** | `getFileIds` | `Classification-2007-01-Classification/getFileIds` |
| **2007-01** | `getKeyLOVs` | `Classification-2007-01-Classification/getKeyLOVs` |
| **2007-01** | `getParents` | `Classification-2007-01-Classification/getParents` |
| **2007-01** | `getPartFamilyTemplates` | `Classification-2007-01-Classification/getPartFamilyTemplates` |
| **2007-01** | `search` | `Classification-2007-01-Classification/search` |
| **2007-01** | `searchByInstanceId` | `Classification-2007-01-Classification/searchByInstanceId` |
| **2007-01** | `searchForClasses` | `Classification-2007-01-Classification/searchForClasses` |
| **2007-01** | `updateClassificationObjects` | `Classification-2007-01-Classification/updateClassificationObjects` |
| **2009-10** | `autoComputeAttributes` | `Classification-2009-10-Classification/autoComputeAttributes` |
| **2009-10** | `createOrUpdateKeyLOVs` | `Classification-2009-10-Classification/createOrUpdateKeyLOVs` |
| **2009-10** | `getAttributesForClasses2` | `Classification-2009-10-Classification/getAttributesForClasses2` |
| **2009-10** | `getKeyLOVs2` | `Classification-2009-10-Classification/getKeyLOVs2` |
| **2011-06** | `deleteChildrenInHierarchy` | `Classification-2011-06-Classification/deleteChildrenInHierarchy` |
| **2011-06** | `getLibraryHierarchy` | `Classification-2011-06-Classification/getLibraryHierarchy` |
| **2011-12** | `getClassificationObjectInfo` | `Classification-2011-12-Classification/getClassificationObjectInfo` |
| **2015-03** | `getKeyLOVsForDependentAttributes` | `Classification-2015-03-Classification/getKeyLOVsForDependentAttributes` |
| **2015-10** | `getClassDefinitions` | `Classification-2015-10-Classification/getClassDefinitions` |
| **2016-03** | `convertValues` | `Classification-2016-03-Classification/convertValues` |
| **2016-03** | `getChildrenExtended` | `Classification-2016-03-Classification/getChildrenExtended` |
| **2016-03** | `searchClassesExtended` | `Classification-2016-03-Classification/searchClassesExtended` |
| **2016-09** | `findValues` | `Classification-2016-09-Classification/findValues` |

| API 版本 | 操作数量 |
|----------|----------|
| 2007-01 | 16 |
| 2009-10 | 4 |
| 2011-06 | 2 |
| 2011-12 | 1 |
| 2015-03 | 1 |
| 2015-10 | 1 |
| 2016-03 | 3 |
| 2016-09 | 1 |

---

## 2. 按 Service 合并（跨版本）

**Service：** Classification（全文仅该服务；不同操作挂接不同年月契约）

### 2.1 分类（Classification）

**涵盖版本：** `2007-01`、`2009-10`、`2011-06`、`2011-12`、`2015-03`、`2015-10`、`2016-03`、`2016-09`  **合计操作：** 29

#### API 版本 2007-01

##### 2.1.1.1 createClassificationObjects

**接口路径：** `Classification-2007-01-Classification/createClassificationObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 根据给定信息创建分类对象 ICO（条目版本上的分类快照），可同时关联被分类的工作区对象。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.createClassificationObjects`

**请求（input）：**

```json
{
  "clsObjs": [
    {
      "clsObjTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "instanceId": "",
      "classId": "",
      "unitBase": "UNSPECIFIED",
      "wsoId": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "properties": [
        {
          "attributeId": "",
          "values": [
            {
              "dbValue": "",
              "displayValue": ""
            }
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjs` | Teamcenter::Soa::Classification::_2007_01::Classification::ClassificationObject[] | 创建 ICO：含属性初值、目标分类类、以及被归档的工作区对象等。 |

**响应（output）：**

```json
{
  "clsObjs": [
    {
      "clsObjTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "instanceId": "",
      "classId": "",
      "unitBase": "UNSPECIFIED",
      "wsoId": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "properties": [
        {
          "attributeId": "",
          "values": [
            {
              "dbValue": "",
              "displayValue": ""
            }
          ]
        }
      ]
    }
  ],
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjs` | Teamcenter::Soa::Classification::_2007_01::Classification::ClassificationObject[] | 本次新建成功的 ICO 汇总。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 同前：分类对象 ID 与错误消息的映射记入 ServiceData 部分错误。 |

---

##### 2.1.1.2 deleteClassificationObjects

**接口路径：** `Classification-2007-01-Classification/deleteClassificationObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 删除指定的分类 ICO 业务对象。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.deleteClassificationObjects`

**请求（input）：**

```json
{
  "clsObjTags": [
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
| `clsObjTags` | Teamcenter::BusinessObject[] | 待物理删除的一组 ICO UID。 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.1.3 findClassificationObjects

**接口路径：** `Classification-2007-01-Classification/findClassificationObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按 ICO 等业务条件查找分类实例（ICO）；与实例 ID、搜索等方法配合。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.findClassificationObjects`

**请求（input）：**

```json
{
  "wsoIds": [
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
| `wsoIds` | Teamcenter::WorkspaceObject[] | 已分类的工作区对象 WSO ID 列表（用于取其关联 ICO）。 |

**响应（output）：**

```json
{
  "icos": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icos` | Teamcenter::Soa::Classification::_2007_01::Classification::WsoIcoMap | `WorkspaceObject` ↔ 对应 ICO 配对表。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将 WorkspaceObject ID 与错误消息关联记入 ServiceData 部分错误。 |

---

##### 2.1.1.4 findClassifiedObjects

**接口路径：** `Classification-2007-01-Classification/findClassifiedObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 由 ICO 反向查找对应的已归类工作区对象（Workspace Object）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.findClassifiedObjects`

**请求（input）：**

```json
{
  "icoTags": [
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
| `icoTags` | Teamcenter::BusinessObject[] | 用作「由 ICO 反查 WSO」的 ICO 业务对象列表。 |

**响应（output）：**

```json
{
  "wsos": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `wsos` | Teamcenter::WorkspaceObject[] | 与给定 ICO 列表对应的已分类工作区对象。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将 WorkspaceObject ID 与错误消息关联记入 ServiceData 部分错误。 |

---

##### 2.1.1.5 getAttributesForClasses

**接口路径：** `Classification-2007-01-Classification/getAttributesForClasses`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按分类类列表获取其可用的分类属性定义（旧版契约）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getAttributesForClasses`

**请求（input）：**

```json
{
  "classIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classIds` | std::string[] | 要查询属性的目标分类类的标识 ID。 |

**响应（output）：**

```json
{
  "attributes": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `attributes` | Teamcenter::Soa::Classification::_2007_01::Classification::StrVClsAttrMap | 类 ID → 该类所包含分类属性定义的映射（无末尾句点写法）。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将「类 ID」与错误信息关联后写入 ServiceData 部分错误。 |

---

##### 2.1.1.6 getChildren

**接口路径：** `Classification-2007-01-Classification/getChildren`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 获取分类层级中给定类的直接子类列表。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getChildren`

**请求（input）：**

```json
{
  "groupOrClassIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `groupOrClassIds` | std::string[] | 在层级上需要拆解下一层子集的类节点或分组 ID。 |

**响应（output）：**

```json
{
  "children": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `children` | Teamcenter::Soa::Classification::_2007_01::Classification::StrVChildDefMap | 输入分类类 ID → 查到的下级子类映射。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 出错时错误与类 ID 成对出现于 ServiceData 部分错误列表。 |

---

##### 2.1.1.7 getClassDescriptions

**接口路径：** `Classification-2007-01-Classification/getClassDescriptions`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 获取一组分类类的描述信息与轻量视图数据。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getClassDescriptions`

**请求（input）：**

```json
{
  "classIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classIds` | std::string[] | 要拉取明细（描述、属性字典等）的类 ID 一览。 |

**响应（output）：**

```json
{
  "descriptions": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `descriptions` | Teamcenter::Soa::Classification::_2007_01::Classification::StrClsDescMap | 输入分类类 ID → 查到的下级子类映射。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 操作中发生的内部异常追加到 partial errors。（原文单词 encounterd 依 Teamcenter API 保持不变） |

---

##### 2.1.1.8 getClassificationObjects

**接口路径：** `Classification-2007-01-Classification/getClassificationObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按 ID 等信息批量抓取 ICO 本体。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getClassificationObjects`

**请求（input）：**

```json
{
  "clsObjTags": [
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
| `clsObjTags` | Teamcenter::BusinessObject[] | `getClassificationObjectInfo` 请求的 ICO 本体。 |

**响应（output）：**

```json
{
  "clsObjs": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjs` | Teamcenter::Soa::Classification::_2007_01::Classification::TagClsObjMap | `TagClsObjMap`：ICO → 服务端解析出的完整节点信息。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将「ICO 分类对象 ID」与错误信息关联写入 ServiceData 部分错误。 |

---

##### 2.1.1.9 getFileIds

**接口路径：** `Classification-2007-01-Classification/getFileIds`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 根据 WSO 与数据集附着关系等信息，解析出分类相关文件的实际文件 ID。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getFileIds`

**请求（input）：**

```json
{
  "criteria": [
    {
      "wsos": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "criteria": {
        "relation": "",
        "datasetType": "",
        "namedRefs": [
          ""
        ]
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `criteria` | Teamcenter::Soa::Classification::_2007_01::Classification::GetFileIdCriteria[] | 指明 WSO、数据集类型、关系及命名引用，用于唯一定位数据集内某一文件并得到 `getFileIds` 所需信息。 |

**响应（output）：**

```json
{
  "ids": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `ids` | Teamcenter::Soa::Classification::_2007_01::Classification::ObjTicketMap | WorkspaceObject 与挂接 Document（文档数据集）拓扑。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 操作中发生的内部异常追加到 partial errors。（原文单词 encounterd 依 Teamcenter API 保持不变） |

---

##### 2.1.1.10 getKeyLOVs

**接口路径：** `Classification-2007-01-Classification/getKeyLOVs`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 读取 Key LOV（键值列表）定义（旧版）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getKeyLOVs`

**请求（input）：**

```json
{
  "keyLOVIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `keyLOVIds` | std::string[] | 要查询定义的 Key LOV ID 列表。Key LOV ID 通常为负整数；在「分类管理」客户端的 Key LOVs 表中「Key/ID」列可见。 |

**响应（output）：**

```json
{
  "keyLOVs": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `keyLOVs` | Teamcenter::Soa::Classification::_2007_01::Classification::StrKeyLOVDefMap | Key LOV 定义详情字典。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败时以指定的 Key LOV ID 关联错误描述，记入 ServiceData 的「部分错误」列表。 |

---

##### 2.1.1.11 getParents

**接口路径：** `Classification-2007-01-Classification/getParents`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 沿分类层级向上回溯父节点链。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getParents`

**请求（input）：**

```json
{
  "childIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `childIds` | std::string[] | 需要查询上一级父类身份的类 ID。 |

**响应（output）：**

```json
{
  "parents": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `parents` | Teamcenter::Soa::Classification::_2007_01::Classification::StrParentVecMap | 对每个输入分类类 ID，返回沿层级向上的父类链。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 操作中发生的内部异常追加到 partial errors。（原文单词 encounterd 依 Teamcenter API 保持不变） |

---

##### 2.1.1.12 getPartFamilyTemplates

**接口路径：** `Classification-2007-01-Classification/getPartFamilyTemplates`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 读取与分类类关联的零件族模板信息。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getPartFamilyTemplates`

**请求（input）：**

```json
{
  "clsClassIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsClassIds` | std::string[] | 需要返回零件族（Part Family）模板数据的分类类 ID 列表。 |

**响应（output）：**

```json
{
  "wsos": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `wsos` | Teamcenter::Soa::Classification::_2007_01::Classification::StringPOMRefVecMap | 零件族模板按类归档的返回值。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 错误与 ServiceData 中部分错误的对应关系列表。 |

---

##### 2.1.1.13 search

**接口路径：** `Classification-2007-01-Classification/search`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按「类 + 属性 + 取值表达式」等条件检索 ICO。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.search`

**请求（input）：**

```json
{
  "searchCriteria": [
    {
      "classIds": [
        ""
      ],
      "searchAttributes": [
        {
          "attributeId": "",
          "query": ""
        }
      ],
      "searchOption": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchCriteria` | Teamcenter::Soa::Classification::_2007_01::Classification::SearchClassAttributes[] | ICO 条件搜索：每项含所属类 ID、属性 ID、及属性取值表达式（如 >=20.00）。 |

**响应（output）：**

```json
{
  "clsObjTags": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjTags` | Teamcenter::Soa::Classification::_2007_01::Classification::StrTagVecMap | 检索关键词与查到对象的业务引用。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 出错时错误信息记入 ServiceData 的「部分错误」列表并联表返回。 |

---

##### 2.1.1.14 searchByInstanceId

**接口路径：** `Classification-2007-01-Classification/searchByInstanceId`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 根据 ICO 等业务对象 UID/模式检索分类对象。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.searchByInstanceId`

**请求（input）：**

```json
{
  "instanceIdQueries": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `instanceIdQueries` | std::string[] | 分类 ICO 的 ID 列表，可使用通配符（如 ICO00*）。 |

**响应（output）：**

```json
{
  "clsObjTags": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjTags` | Teamcenter::Soa::Classification::_2007_01::Classification::StrTagVecMap | `search`/`searchByInstanceId` 等返回的分类 ICO。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将一类或多类 ICO ID 与错误消息关联记入 ServiceData 部分错误。 |

---

##### 2.1.1.15 searchForClasses

**接口路径：** `Classification-2007-01-Classification/searchForClasses`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 在分类管理层级中搜索匹配的类节点定义。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.searchForClasses`

**请求（input）：**

```json
{
  "criteria": [
    {
      "searchAttribute": "CSA_CLASSID",
      "searchString": "",
      "sortOption": "CSO_CLASSID"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `criteria` | Teamcenter::Soa::Classification::_2007_01::Classification::SearchForClassesCriteria[] | 搜索表达式、参与匹配的属性字段与排序配置。 |

**响应（output）：**

```json
{
  "classes": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classes` | Teamcenter::Soa::Classification::_2007_01::Classification::IntClassDefVecMap | 每组搜索条目索引 ⇄ 命中的类的集合。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 操作期间的内部异常追加到 partial errors。（原文 encounterd） |

---

##### 2.1.1.16 updateClassificationObjects

**接口路径：** `Classification-2007-01-Classification/updateClassificationObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 更新已有 ICO 上的分类属性取值或状态。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.updateClassificationObjects`

**请求（input）：**

```json
{
  "clsObjs": [
    {
      "clsObjTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "instanceId": "",
      "classId": "",
      "unitBase": "UNSPECIFIED",
      "wsoId": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "properties": [
        {
          "attributeId": "",
          "values": [
            {
              "dbValue": "",
              "displayValue": ""
            }
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjs` | Teamcenter::Soa::Classification::_2007_01::Classification::ClassificationObject[] | 待修改 ICO 及其需更新的具体内容。 |

**响应（output）：**

```json
{
  "clsObjs": [
    {
      "clsObjTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "instanceId": "",
      "classId": "",
      "unitBase": "UNSPECIFIED",
      "wsoId": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "properties": [
        {
          "attributeId": "",
          "values": [
            {
              "dbValue": "",
              "displayValue": ""
            }
          ]
        }
      ]
    }
  ],
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjs` | Teamcenter::Soa::Classification::_2007_01::Classification::ClassificationObject[] | 本次更新写入后的 ICO。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 同前：分类对象 ID 与错误消息的映射记入 ServiceData 部分错误。 |

---

#### API 版本 2009-10

##### 2.1.2.1 autoComputeAttributes

**接口路径：** `Classification-2009-10-Classification/autoComputeAttributes`

**API 版本：** `2009-10`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按 Load/Create/Edit 模式对 ICO 的属性特性与取值进行服务端自动推演。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2009_10.Classification.autoComputeAttributes`

**请求（input）：**

```json
{
  "icoId": "",
  "wso": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "classId": "",
  "viewId": "",
  "inputAttrs": {},
  "unitSystem": "",
  "mode": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icoId` | std::string | `autoComputeAttributes`：待计算服务端属性时，所指的那一个 ICO（分类实例）的唯一 ID。 |
| `wso` | Teamcenter::WorkspaceObject | 被分类的工作区锚点对象（可选）；NULL 表示独立 ICO（无挂载 WSO）。 |
| `classId` | std::string |  ICO 所属的「分类模板类」或其业务占位类。 |
| `viewId` | std::string | 挂载分类时必须指定的「分类视图」ID（与业务类耦合）。 |
| `inputAttrs` | Teamcenter::Soa::Classification::_2009_10::Classification::AutoComputeAttributesMap | 输入属性映射：取值、附加属性以及与「属性值是否改动」的标志。 |
| `unitSystem` | int | ICO 度量体系：0=公制 Metric；1=英制等非公制。 |
| `mode` | int | 运行模式枚举：Load(0)\|Create(1)\|Edit(2)。Load 模式只演算属性标记（必选/只读/唯一性/复制/隐藏等）；其它模式并行计算取值。 |

**响应（output）：**

```json
{
  "autoComputedAttrs": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `autoComputedAttrs` | Teamcenter::Soa::Classification::_2009_10::Classification::AutoComputeAttributesMap | `AutoComputeAttribute` 配置与触发属性 ID 的引用映射。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 出错时出错项以 ICO（分类实例）对象的 ID 与错误信息关联后写入 ServiceData 部分错误列表。 |

---

##### 2.1.2.2 createOrUpdateKeyLOVs

**接口路径：** `Classification-2009-10-Classification/createOrUpdateKeyLOVs`

**API 版本：** `2009-10`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 新建或批量维护 Key LOV 定义条目。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2009_10.Classification.createOrUpdateKeyLOVs`

**请求（input）：**

```json
{
  "keyLOVsInput": [
    {
      "id": "",
      "name": "",
      "keyLovtag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "options": "",
      "keyLovEntries": [
        {
          "lovKey": "",
          "lovValue": "",
          "deprecatedSatus": ""
        }
      ],
      "owningSite": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "sharedSites": [
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
| `keyLOVsInput` | Teamcenter::Soa::Classification::_2009_10::Classification::KeyLOVDefinition2[] | 新建或更新的 Key LOV 定义数据结构列表。 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.2.3 getAttributesForClasses2

**接口路径：** `Classification-2009-10-Classification/getAttributesForClasses2`

**API 版本：** `2009-10`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 新版：按分类类获取属性定义及相关控制信息。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2009_10.Classification.getAttributesForClasses2`

**请求（input）：**

```json
{
  "classIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classIds` | std::string[] | 要查询属性的目标分类类的标识 ID。 |

**响应（output）：**

```json
{
  "attributes": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `attributes` | Teamcenter::Soa::Classification::_2009_10::Classification::StrVClsAttrMap2 | 类 ID → 该类下全部分类属性的定义快照（本条英文说明末尾带句号，与无前句点条目含义相同）。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将「类 ID」与错误信息关联后写入 ServiceData 部分错误。 |

---

##### 2.1.2.4 getKeyLOVs2

**接口路径：** `Classification-2009-10-Classification/getKeyLOVs2`

**API 版本：** `2009-10`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 新版：检索 Key LOV 定义。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2009_10.Classification.getKeyLOVs2`

**请求（input）：**

```json
{
  "keyLOVIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `keyLOVIds` | std::string[] | 要查询定义的 Key LOV ID 列表。Key LOV ID 通常为负整数；在「分类管理」客户端的 Key LOVs 表中「Key/ID」列可见。 |

**响应（output）：**

```json
{
  "keyLOVs": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `keyLOVs` | Teamcenter::Soa::Classification::_2009_10::Classification::StrKeyLOVDefMap2 | Key LOV（无短横线别名）定义的详情映射。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将 Key LOV ID 与错误消息关联记入 ServiceData 部分错误（原文句末缺少句号）。 |

---

#### API 版本 2011-06

##### 2.1.3.1 deleteChildrenInHierarchy

**接口路径：** `Classification-2011-06-Classification/deleteChildrenInHierarchy`

**API 版本：** `2011-06`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 在满足删除策略的前提下，删除给定类之下的子层级或挂载对象。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2011_06.Classification.deleteChildrenInHierarchy`

**请求（input）：**

```json
{
  "optionsInput": [
    {
      "id": "",
      "theRecurseOption": "",
      "theViewsOption": "",
      "theIcosOption": "",
      "theWSOOption": "",
      "theChildrenOnlyOption": "",
      "theIgnoreOption": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `optionsInput` | Teamcenter::Soa::Classification::_2011_06::Classification::HierarchyInfoAndOptions[] | 删除层级：`HierarchyInfoAndOptions`，包含要清空层级的分类类、需一并删除的业务对象与子项选项。 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.3.2 getLibraryHierarchy

**接口路径：** `Classification-2011-06-Classification/getLibraryHierarchy`

**API 版本：** `2011-06`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按传入分类库取值获取库内的层级拓扑（类树引用）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2011_06.Classification.getLibraryHierarchy`

**请求（input）：**

```json
{
  "libraryValues": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `libraryValues` | std::string[] | `getLibraryHierarchy` 的分类库上下文键（用于裁剪返回树）。 |

**响应（output）：**

```json
{
  "clsInfo": [
    {
      "classDefn": {
        "id": "",
        "parent": "",
        "instanceCount": "",
        "viewCount": "",
        "documents": [
          {
            "documentType": "",
            "ticket": "",
            "originalFileName": ""
          }
        ],
        "name": "",
        "shortName": "",
        "description": "",
        "unitBase": "UNSPECIFIED",
        "options": {
          "isValid": "",
          "isAbstract": "",
          "isGroup": "",
          "isAssembly": ""
        },
        "userData1": "",
        "userData2": "",
        "childCount": ""
      },
      "classBO": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsInfo` | Teamcenter::Soa::Classification::_2011_06::Classification::ClassInfo[] | 当前分类库中符合条件的类引用集合。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 出错时 Key LOV ID 与错误信息成对出现于 ServiceData 部分错误列表。 |

---

#### API 版本 2011-12

##### 2.1.4.1 getClassificationObjectInfo

**接口路径：** `Classification-2011-12-Classification/getClassificationObjectInfo`

**API 版本：** `2011-12`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 读取 ICO 的扩展详情（聚合属性与其它展示信息）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2011_12.Classification.getClassificationObjectInfo`

**请求（input）：**

```json
{
  "icoUids": [
    ""
  ],
  "attributeIds": [],
  "getOptimizedValues": "",
  "fetchDescriptor": "",
  "locale": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icoUids` | std::string[] | 需要展开全部属性及 LOV、描述符快照的 ICO。 |
| `attributeIds` | int[] | 在指定 ICO 上需要读出的若干属性 UID。 |
| `getOptimizedValues` | bool | 是否读取「优化后」的属性显示值（更易读并减少首尾无效零），例如更愿意显示「1 km」而非「1000 m」。 |
| `fetchDescriptor` | bool | 为 true 时同时拉取各项分类属性的属性描述符（元数据）。 |
| `locale` | std::string | 本地化语言环境，用以解读属性字面量与加载属性描述文案。 |

**响应（output）：**

```json
{
  "classificationObjectInfo": {},
  "classAttributeDesc": {},
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classificationObjectInfo` | Teamcenter::Soa::Classification::_2011_12::Classification::ClassificationObjectInfoMap | ICO 与各分类属性的引用向量。 |
| `classAttributeDesc` | Teamcenter::Soa::Classification::_2011_12::Classification::ClassAttributeDescMap | ICO 与其属性描述结构句柄列表。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 出错时出错项以 ICO（分类实例）对象的 ID 与错误信息关联后写入 ServiceData 部分错误列表。 |

---

#### API 版本 2015-03

##### 2.1.5.1 getKeyLOVsForDependentAttributes

**接口路径：** `Classification-2015-03-Classification/getKeyLOVsForDependentAttributes`

**API 版本：** `2015-03`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 为有依赖关系的分类属性拉取可用的 Key LOV 选项集合。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2015_03.Classification.getKeyLOVsForDependentAttributes`

**请求（input）：**

```json
{
  "dependencyAttributeStruct": [
    {
      "classID": "",
      "selectedAttributeID": "",
      "selectedValue": "",
      "attributeValues": [
        {
          "attributeID": "",
          "value": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `dependencyAttributeStruct` | Teamcenter::Soa::Classification::_2015_03::Classification::DependencyAttributeStruct[] | 每条输入：目标类 ID、发生变更的属性及新值、以及界面展示的其它属性与取值。 |

**响应（output）：**

```json
{
  "dependencyKeyLOVs": [
    {
      "attributeID": "",
      "selectedKeys": [
        ""
      ],
      "keyLOVDefinition": {
        "id": "",
        "name": "",
        "keyLovtag": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "options": "",
        "keyLovEntries": [
          {
            "lovKey": "",
            "lovValue": "",
            "deprecatedSatus": ""
          }
        ],
        "owningSite": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "sharedSites": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `dependencyKeyLOVs` | Teamcenter::Soa::Classification::_2015_03::Classification::DependencyKeyLOVDescriptor[] | 待修改的每个属性：属性 ID、从 Key LOV 中选定条目的 Key、以及该 Key LOV 的定义。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 所有异常均归入服务数据的「部分错误」列表。 |

---

#### API 版本 2015-10

##### 2.1.6.1 getClassDefinitions

**接口路径：** `Classification-2015-10-Classification/getClassDefinitions`

**API 版本：** `2015-10`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 返回类或视图的 BMIDE 结构化定义快照（字符串 ID → ClassDef）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2015_10.Classification.getClassDefinitions`

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
| `classIDs` | std::string[] | 分类类的 ID 列表。 |

**响应（output）：**

```json
{
  "classDefinitionMap": {},
  "classAttributesDefinitionMap": {},
  "keyLOVDefinitionMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classDefinitionMap` | Teamcenter::Soa::Classification::_2015_10::Classification::ClassDefinitionMap | 分类类或分类视图 ID 与类定义的对应关系（string/ClassDef）。 |
| `classAttributesDefinitionMap` | Teamcenter::Soa::Classification::_2015_10::Classification::ClassAttributesDefinitionMap | 分类类或视图 ID 与「类属性定义」的映射（string/ClassAttributesDefinition）。 |
| `keyLOVDefinitionMap` | Teamcenter::Soa::Classification::_2015_10::Classification::KeyLOVDefinitionMap | 已使用的分类 Key LOV 与其定义的映射（字符串 ID → KeyLOVDefinition2）。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 所有异常均归入服务数据的「部分错误」列表。 |

---

#### API 版本 2016-03

##### 2.1.7.1 convertValues

**接口路径：** `Classification-2016-03-Classification/convertValues`

**API 版本：** `2016-03`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 在分类度量体系下对某些属性取值做换算或等价转换。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2016_03.Classification.convertValues`

**请求（input）：**

```json
{
  "valueConversionInputs": [
    {
      "inputValues": [
        ""
      ],
      "inputUnit": "",
      "outputUnit": "",
      "outputFormat": {
        "formatType": "",
        "formatModifier1": "",
        "formatModifier2": "",
        "formatLength": ""
      },
      "options": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `valueConversionInputs` | Teamcenter::Soa::Classification::_2016_03::Classification::ValueConversionInput[] | 待执行度量单位或内部存储格式换算的数值集合。 |

**响应（output）：**

```json
{
  "convertedValues": [
    {
      "convertedValues": [
        ""
      ]
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `convertedValues` | Teamcenter::Soa::Classification::_2016_03::Classification::ValueConversionOutput[] | `convertValues` 输出：完成单位换算或等价转换的属性值矩阵。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 数值/单位转换失败时记录在 ServiceData 部分错误列表。 |

---

##### 2.1.7.2 getChildrenExtended

**接口路径：** `Classification-2016-03-Classification/getChildrenExtended`

**API 版本：** `2016-03`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 获取子节点扩展信息（可传按位选项控制父计数、图标等附加数据）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2016_03.Classification.getChildrenExtended`

**请求（input）：**

```json
{
  "classObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "filterForWriteAccess": "",
  "options": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classObjects` | Teamcenter::BusinessObject[] | 需要枚举直接子节点的父类实例。 |
| `filterForWriteAccess` | bool | 为 true 时过滤掉用户对「分类」无写权限的类，不包含在返回值中。 |
| `options` | int | 按位扩展选项（可组合）：1«0 在 ExtendedClassDef 中附带父节点信息；1«1 返回子节点数量；1«2 返回实例数量；1«3 在 BaseClassDef 中返回图标文档；1«4 在 ExtendedClassDef 中返回类图像文档。若原文含「font」等标签，含义与 SOA Api Browser 中 HTML 描述一致。 |

**响应（output）：**

```json
{
  "classDescriptions": [
    {
      "classDescriptions": [
        {
          "classDef": {
            "classID": "",
            "classBO": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "className": "",
            "isAbstract": "",
            "classUnitBase": "",
            "classIconLoaded": "",
            "classIconDocument": {
              "documentType": "",
              "ticket": "",
              "originalFileName": ""
            }
          },
          "parentDefs": [
            {
              "classID": "",
              "classBO": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "className": "",
              "isAbstract": "",
              "classUnitBase": "",
              "classIconLoaded": "",
              "classIconDocument": {
                "documentType": "",
                "ticket": "",
                "originalFileName": ""
              }
            }
          ],
          "classShortName": "",
          "classDescription": "",
          "classUserData1": "",
          "classUserData2": "",
          "classChildCount": "",
          "classInstanceCount": "",
          "classImagesLoaded": "",
          "classImageDocuments": [
            {
              "documentType": "",
              "ticket": "",
              "originalFileName": ""
            }
          ]
        }
      ]
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classDescriptions` | Teamcenter::Soa::Classification::_2016_03::Classification::GetChildrenExtendedOutput[] | 对每个输入父类找到的子分类类列表（合并描述）。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 出错时以小写原文「class」所指的分类类 ID 与错误信息关联，记入 ServiceData 部分错误列表。 |

---

##### 2.1.7.3 searchClassesExtended

**接口路径：** `Classification-2016-03-Classification/searchClassesExtended`

**API 版本：** `2016-03`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 执行增强型分类类检索（含按位选项、写权限筛选等）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2016_03.Classification.searchClassesExtended`

**请求（input）：**

```json
{
  "searchCriterias": [
    {
      "attributeId": "",
      "query": ""
    }
  ],
  "sortAttributes": [],
  "filterForWriteAccess": "",
  "options": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchCriterias` | Teamcenter::Soa::Classification::_2007_01::Classification::SearchAttribute[] | 类搜索条件的结构数组。支持的键：类 ID=-600；类名称=-607；短名称=-608；用户自定义字段=-612/-613；亦可用扩展条件「指定属性」（8 为属性 ID，3 为属性名检索）。 |
| `sortAttributes` | int[] | 排序依据属性 ID=-600/-607/-608/-612/-613 分别对应「类编码、名称、短名、两组用户扩展」。 |
| `filterForWriteAccess` | bool | 为 true 时过滤掉用户对「分类」无写权限的类，不包含在返回值中。 |
| `options` | int | 按位扩展选项（可组合）：1«0 在 ExtendedClassDef 中附带父节点信息；1«1 返回子节点数量；1«2 返回实例数量；1«3 在 BaseClassDef 中返回图标文档；1«4 在 ExtendedClassDef 中返回类图像文档。若原文含「font」等标签，含义与 SOA Api Browser 中 HTML 描述一致。 |

**响应（output）：**

```json
{
  "classDescriptions": [
    {
      "classDescriptions": [
        {
          "classDef": {
            "classID": "",
            "classBO": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "className": "",
            "isAbstract": "",
            "classUnitBase": "",
            "classIconLoaded": "",
            "classIconDocument": {
              "documentType": "",
              "ticket": "",
              "originalFileName": ""
            }
          },
          "parentDefs": [
            {
              "classID": "",
              "classBO": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "className": "",
              "isAbstract": "",
              "classUnitBase": "",
              "classIconLoaded": "",
              "classIconDocument": {
                "documentType": "",
                "ticket": "",
                "originalFileName": ""
              }
            }
          ],
          "classShortName": "",
          "classDescription": "",
          "classUserData1": "",
          "classUserData2": "",
          "classChildCount": "",
          "classInstanceCount": "",
          "classImagesLoaded": "",
          "classImageDocuments": [
            {
              "documentType": "",
              "ticket": "",
              "originalFileName": ""
            }
          ]
        }
      ]
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classDescriptions` | Teamcenter::Soa::Classification::_2016_03::Classification::SearchClassesExtendedOutput[] | 按搜索条件找到的类定义条目列表。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 检索流程中的失败记入 ServiceData 部分错误列表。 |

---

#### API 版本 2016-09

##### 2.1.8.1 findValues

**接口路径：** `Classification-2016-09-Classification/findValues`

**API 版本：** `2016-09`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 为给定上下文查找合规或可选的属性取值集合。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2016_09.Classification.findValues`

**请求（input）：**

```json
{
  "findValueInputs": [
    {
      "attributeID": "",
      "classID": "",
      "searchInBothUnitSystems": "",
      "activeUnitsystem": "",
      "attributeValues": [
        {
          "id": "",
          "value": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `findValueInputs` | Teamcenter::Soa::Classification::_2016_09::Classification::FindValueInput[] | `findValues`：描述待匹配分类属性上下文与取值条件的聚合输入。 |

**响应（output）：**

```json
{
  "findValuesOutputs": [
    {
      "foundValues": [
        {
          "unitSystem": "",
          "value": "",
          "count": ""
        }
      ]
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `findValuesOutputs` | Teamcenter::Soa::Classification::_2016_09::Classification::FindValuesOutput[] | `findValues` 根据输入匹配到的可取枚举/区间值范围。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 整次操作的失败记入 ServiceData 部分错误列表。 |

---

---

## 3. 按 API 版本（年-月）归档

### 3.1 2007-01

**操作数：** 16

##### 3.1.1 createClassificationObjects

**接口路径：** `Classification-2007-01-Classification/createClassificationObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 根据给定信息创建分类对象 ICO（条目版本上的分类快照），可同时关联被分类的工作区对象。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.createClassificationObjects`

**请求（input）：**

```json
{
  "clsObjs": [
    {
      "clsObjTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "instanceId": "",
      "classId": "",
      "unitBase": "UNSPECIFIED",
      "wsoId": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "properties": [
        {
          "attributeId": "",
          "values": [
            {
              "dbValue": "",
              "displayValue": ""
            }
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjs` | Teamcenter::Soa::Classification::_2007_01::Classification::ClassificationObject[] | 创建 ICO：含属性初值、目标分类类、以及被归档的工作区对象等。 |

**响应（output）：**

```json
{
  "clsObjs": [
    {
      "clsObjTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "instanceId": "",
      "classId": "",
      "unitBase": "UNSPECIFIED",
      "wsoId": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "properties": [
        {
          "attributeId": "",
          "values": [
            {
              "dbValue": "",
              "displayValue": ""
            }
          ]
        }
      ]
    }
  ],
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjs` | Teamcenter::Soa::Classification::_2007_01::Classification::ClassificationObject[] | 本次新建成功的 ICO 汇总。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 同前：分类对象 ID 与错误消息的映射记入 ServiceData 部分错误。 |

---

##### 3.1.2 deleteClassificationObjects

**接口路径：** `Classification-2007-01-Classification/deleteClassificationObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 删除指定的分类 ICO 业务对象。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.deleteClassificationObjects`

**请求（input）：**

```json
{
  "clsObjTags": [
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
| `clsObjTags` | Teamcenter::BusinessObject[] | 待物理删除的一组 ICO UID。 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.1.3 findClassificationObjects

**接口路径：** `Classification-2007-01-Classification/findClassificationObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按 ICO 等业务条件查找分类实例（ICO）；与实例 ID、搜索等方法配合。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.findClassificationObjects`

**请求（input）：**

```json
{
  "wsoIds": [
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
| `wsoIds` | Teamcenter::WorkspaceObject[] | 已分类的工作区对象 WSO ID 列表（用于取其关联 ICO）。 |

**响应（output）：**

```json
{
  "icos": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icos` | Teamcenter::Soa::Classification::_2007_01::Classification::WsoIcoMap | `WorkspaceObject` ↔ 对应 ICO 配对表。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将 WorkspaceObject ID 与错误消息关联记入 ServiceData 部分错误。 |

---

##### 3.1.4 findClassifiedObjects

**接口路径：** `Classification-2007-01-Classification/findClassifiedObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 由 ICO 反向查找对应的已归类工作区对象（Workspace Object）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.findClassifiedObjects`

**请求（input）：**

```json
{
  "icoTags": [
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
| `icoTags` | Teamcenter::BusinessObject[] | 用作「由 ICO 反查 WSO」的 ICO 业务对象列表。 |

**响应（output）：**

```json
{
  "wsos": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `wsos` | Teamcenter::WorkspaceObject[] | 与给定 ICO 列表对应的已分类工作区对象。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将 WorkspaceObject ID 与错误消息关联记入 ServiceData 部分错误。 |

---

##### 3.1.5 getAttributesForClasses

**接口路径：** `Classification-2007-01-Classification/getAttributesForClasses`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按分类类列表获取其可用的分类属性定义（旧版契约）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getAttributesForClasses`

**请求（input）：**

```json
{
  "classIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classIds` | std::string[] | 要查询属性的目标分类类的标识 ID。 |

**响应（output）：**

```json
{
  "attributes": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `attributes` | Teamcenter::Soa::Classification::_2007_01::Classification::StrVClsAttrMap | 类 ID → 该类所包含分类属性定义的映射（无末尾句点写法）。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将「类 ID」与错误信息关联后写入 ServiceData 部分错误。 |

---

##### 3.1.6 getChildren

**接口路径：** `Classification-2007-01-Classification/getChildren`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 获取分类层级中给定类的直接子类列表。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getChildren`

**请求（input）：**

```json
{
  "groupOrClassIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `groupOrClassIds` | std::string[] | 在层级上需要拆解下一层子集的类节点或分组 ID。 |

**响应（output）：**

```json
{
  "children": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `children` | Teamcenter::Soa::Classification::_2007_01::Classification::StrVChildDefMap | 输入分类类 ID → 查到的下级子类映射。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 出错时错误与类 ID 成对出现于 ServiceData 部分错误列表。 |

---

##### 3.1.7 getClassDescriptions

**接口路径：** `Classification-2007-01-Classification/getClassDescriptions`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 获取一组分类类的描述信息与轻量视图数据。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getClassDescriptions`

**请求（input）：**

```json
{
  "classIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classIds` | std::string[] | 要拉取明细（描述、属性字典等）的类 ID 一览。 |

**响应（output）：**

```json
{
  "descriptions": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `descriptions` | Teamcenter::Soa::Classification::_2007_01::Classification::StrClsDescMap | 输入分类类 ID → 查到的下级子类映射。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 操作中发生的内部异常追加到 partial errors。（原文单词 encounterd 依 Teamcenter API 保持不变） |

---

##### 3.1.8 getClassificationObjects

**接口路径：** `Classification-2007-01-Classification/getClassificationObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按 ID 等信息批量抓取 ICO 本体。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getClassificationObjects`

**请求（input）：**

```json
{
  "clsObjTags": [
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
| `clsObjTags` | Teamcenter::BusinessObject[] | `getClassificationObjectInfo` 请求的 ICO 本体。 |

**响应（output）：**

```json
{
  "clsObjs": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjs` | Teamcenter::Soa::Classification::_2007_01::Classification::TagClsObjMap | `TagClsObjMap`：ICO → 服务端解析出的完整节点信息。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将「ICO 分类对象 ID」与错误信息关联写入 ServiceData 部分错误。 |

---

##### 3.1.9 getFileIds

**接口路径：** `Classification-2007-01-Classification/getFileIds`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 根据 WSO 与数据集附着关系等信息，解析出分类相关文件的实际文件 ID。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getFileIds`

**请求（input）：**

```json
{
  "criteria": [
    {
      "wsos": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "criteria": {
        "relation": "",
        "datasetType": "",
        "namedRefs": [
          ""
        ]
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `criteria` | Teamcenter::Soa::Classification::_2007_01::Classification::GetFileIdCriteria[] | 指明 WSO、数据集类型、关系及命名引用，用于唯一定位数据集内某一文件并得到 `getFileIds` 所需信息。 |

**响应（output）：**

```json
{
  "ids": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `ids` | Teamcenter::Soa::Classification::_2007_01::Classification::ObjTicketMap | WorkspaceObject 与挂接 Document（文档数据集）拓扑。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 操作中发生的内部异常追加到 partial errors。（原文单词 encounterd 依 Teamcenter API 保持不变） |

---

##### 3.1.10 getKeyLOVs

**接口路径：** `Classification-2007-01-Classification/getKeyLOVs`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 读取 Key LOV（键值列表）定义（旧版）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getKeyLOVs`

**请求（input）：**

```json
{
  "keyLOVIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `keyLOVIds` | std::string[] | 要查询定义的 Key LOV ID 列表。Key LOV ID 通常为负整数；在「分类管理」客户端的 Key LOVs 表中「Key/ID」列可见。 |

**响应（output）：**

```json
{
  "keyLOVs": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `keyLOVs` | Teamcenter::Soa::Classification::_2007_01::Classification::StrKeyLOVDefMap | Key LOV 定义详情字典。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败时以指定的 Key LOV ID 关联错误描述，记入 ServiceData 的「部分错误」列表。 |

---

##### 3.1.11 getParents

**接口路径：** `Classification-2007-01-Classification/getParents`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 沿分类层级向上回溯父节点链。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getParents`

**请求（input）：**

```json
{
  "childIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `childIds` | std::string[] | 需要查询上一级父类身份的类 ID。 |

**响应（output）：**

```json
{
  "parents": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `parents` | Teamcenter::Soa::Classification::_2007_01::Classification::StrParentVecMap | 对每个输入分类类 ID，返回沿层级向上的父类链。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 操作中发生的内部异常追加到 partial errors。（原文单词 encounterd 依 Teamcenter API 保持不变） |

---

##### 3.1.12 getPartFamilyTemplates

**接口路径：** `Classification-2007-01-Classification/getPartFamilyTemplates`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 读取与分类类关联的零件族模板信息。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.getPartFamilyTemplates`

**请求（input）：**

```json
{
  "clsClassIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsClassIds` | std::string[] | 需要返回零件族（Part Family）模板数据的分类类 ID 列表。 |

**响应（output）：**

```json
{
  "wsos": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `wsos` | Teamcenter::Soa::Classification::_2007_01::Classification::StringPOMRefVecMap | 零件族模板按类归档的返回值。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 错误与 ServiceData 中部分错误的对应关系列表。 |

---

##### 3.1.13 search

**接口路径：** `Classification-2007-01-Classification/search`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按「类 + 属性 + 取值表达式」等条件检索 ICO。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.search`

**请求（input）：**

```json
{
  "searchCriteria": [
    {
      "classIds": [
        ""
      ],
      "searchAttributes": [
        {
          "attributeId": "",
          "query": ""
        }
      ],
      "searchOption": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchCriteria` | Teamcenter::Soa::Classification::_2007_01::Classification::SearchClassAttributes[] | ICO 条件搜索：每项含所属类 ID、属性 ID、及属性取值表达式（如 >=20.00）。 |

**响应（output）：**

```json
{
  "clsObjTags": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjTags` | Teamcenter::Soa::Classification::_2007_01::Classification::StrTagVecMap | 检索关键词与查到对象的业务引用。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 出错时错误信息记入 ServiceData 的「部分错误」列表并联表返回。 |

---

##### 3.1.14 searchByInstanceId

**接口路径：** `Classification-2007-01-Classification/searchByInstanceId`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 根据 ICO 等业务对象 UID/模式检索分类对象。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.searchByInstanceId`

**请求（input）：**

```json
{
  "instanceIdQueries": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `instanceIdQueries` | std::string[] | 分类 ICO 的 ID 列表，可使用通配符（如 ICO00*）。 |

**响应（output）：**

```json
{
  "clsObjTags": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjTags` | Teamcenter::Soa::Classification::_2007_01::Classification::StrTagVecMap | `search`/`searchByInstanceId` 等返回的分类 ICO。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将一类或多类 ICO ID 与错误消息关联记入 ServiceData 部分错误。 |

---

##### 3.1.15 searchForClasses

**接口路径：** `Classification-2007-01-Classification/searchForClasses`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 在分类管理层级中搜索匹配的类节点定义。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.searchForClasses`

**请求（input）：**

```json
{
  "criteria": [
    {
      "searchAttribute": "CSA_CLASSID",
      "searchString": "",
      "sortOption": "CSO_CLASSID"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `criteria` | Teamcenter::Soa::Classification::_2007_01::Classification::SearchForClassesCriteria[] | 搜索表达式、参与匹配的属性字段与排序配置。 |

**响应（output）：**

```json
{
  "classes": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classes` | Teamcenter::Soa::Classification::_2007_01::Classification::IntClassDefVecMap | 每组搜索条目索引 ⇄ 命中的类的集合。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 操作期间的内部异常追加到 partial errors。（原文 encounterd） |

---

##### 3.1.16 updateClassificationObjects

**接口路径：** `Classification-2007-01-Classification/updateClassificationObjects`

**API 版本：** `2007-01`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 更新已有 ICO 上的分类属性取值或状态。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2007_01.Classification.updateClassificationObjects`

**请求（input）：**

```json
{
  "clsObjs": [
    {
      "clsObjTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "instanceId": "",
      "classId": "",
      "unitBase": "UNSPECIFIED",
      "wsoId": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "properties": [
        {
          "attributeId": "",
          "values": [
            {
              "dbValue": "",
              "displayValue": ""
            }
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjs` | Teamcenter::Soa::Classification::_2007_01::Classification::ClassificationObject[] | 待修改 ICO 及其需更新的具体内容。 |

**响应（output）：**

```json
{
  "clsObjs": [
    {
      "clsObjTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "instanceId": "",
      "classId": "",
      "unitBase": "UNSPECIFIED",
      "wsoId": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "properties": [
        {
          "attributeId": "",
          "values": [
            {
              "dbValue": "",
              "displayValue": ""
            }
          ]
        }
      ]
    }
  ],
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsObjs` | Teamcenter::Soa::Classification::_2007_01::Classification::ClassificationObject[] | 本次更新写入后的 ICO。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 同前：分类对象 ID 与错误消息的映射记入 ServiceData 部分错误。 |

---

### 3.2 2009-10

**操作数：** 4

##### 3.2.1 autoComputeAttributes

**接口路径：** `Classification-2009-10-Classification/autoComputeAttributes`

**API 版本：** `2009-10`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按 Load/Create/Edit 模式对 ICO 的属性特性与取值进行服务端自动推演。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2009_10.Classification.autoComputeAttributes`

**请求（input）：**

```json
{
  "icoId": "",
  "wso": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "classId": "",
  "viewId": "",
  "inputAttrs": {},
  "unitSystem": "",
  "mode": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icoId` | std::string | `autoComputeAttributes`：待计算服务端属性时，所指的那一个 ICO（分类实例）的唯一 ID。 |
| `wso` | Teamcenter::WorkspaceObject | 被分类的工作区锚点对象（可选）；NULL 表示独立 ICO（无挂载 WSO）。 |
| `classId` | std::string |  ICO 所属的「分类模板类」或其业务占位类。 |
| `viewId` | std::string | 挂载分类时必须指定的「分类视图」ID（与业务类耦合）。 |
| `inputAttrs` | Teamcenter::Soa::Classification::_2009_10::Classification::AutoComputeAttributesMap | 输入属性映射：取值、附加属性以及与「属性值是否改动」的标志。 |
| `unitSystem` | int | ICO 度量体系：0=公制 Metric；1=英制等非公制。 |
| `mode` | int | 运行模式枚举：Load(0)\|Create(1)\|Edit(2)。Load 模式只演算属性标记（必选/只读/唯一性/复制/隐藏等）；其它模式并行计算取值。 |

**响应（output）：**

```json
{
  "autoComputedAttrs": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `autoComputedAttrs` | Teamcenter::Soa::Classification::_2009_10::Classification::AutoComputeAttributesMap | `AutoComputeAttribute` 配置与触发属性 ID 的引用映射。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 出错时出错项以 ICO（分类实例）对象的 ID 与错误信息关联后写入 ServiceData 部分错误列表。 |

---

##### 3.2.2 createOrUpdateKeyLOVs

**接口路径：** `Classification-2009-10-Classification/createOrUpdateKeyLOVs`

**API 版本：** `2009-10`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 新建或批量维护 Key LOV 定义条目。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2009_10.Classification.createOrUpdateKeyLOVs`

**请求（input）：**

```json
{
  "keyLOVsInput": [
    {
      "id": "",
      "name": "",
      "keyLovtag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "options": "",
      "keyLovEntries": [
        {
          "lovKey": "",
          "lovValue": "",
          "deprecatedSatus": ""
        }
      ],
      "owningSite": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "sharedSites": [
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
| `keyLOVsInput` | Teamcenter::Soa::Classification::_2009_10::Classification::KeyLOVDefinition2[] | 新建或更新的 Key LOV 定义数据结构列表。 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.2.3 getAttributesForClasses2

**接口路径：** `Classification-2009-10-Classification/getAttributesForClasses2`

**API 版本：** `2009-10`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 新版：按分类类获取属性定义及相关控制信息。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2009_10.Classification.getAttributesForClasses2`

**请求（input）：**

```json
{
  "classIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classIds` | std::string[] | 要查询属性的目标分类类的标识 ID。 |

**响应（output）：**

```json
{
  "attributes": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `attributes` | Teamcenter::Soa::Classification::_2009_10::Classification::StrVClsAttrMap2 | 类 ID → 该类下全部分类属性的定义快照（本条英文说明末尾带句号，与无前句点条目含义相同）。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将「类 ID」与错误信息关联后写入 ServiceData 部分错误。 |

---

##### 3.2.4 getKeyLOVs2

**接口路径：** `Classification-2009-10-Classification/getKeyLOVs2`

**API 版本：** `2009-10`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 新版：检索 Key LOV 定义。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2009_10.Classification.getKeyLOVs2`

**请求（input）：**

```json
{
  "keyLOVIds": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `keyLOVIds` | std::string[] | 要查询定义的 Key LOV ID 列表。Key LOV ID 通常为负整数；在「分类管理」客户端的 Key LOVs 表中「Key/ID」列可见。 |

**响应（output）：**

```json
{
  "keyLOVs": {},
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `keyLOVs` | Teamcenter::Soa::Classification::_2009_10::Classification::StrKeyLOVDefMap2 | Key LOV（无短横线别名）定义的详情映射。 |
| `data` | Teamcenter::Soa::Server::ServiceData | 失败条目将 Key LOV ID 与错误消息关联记入 ServiceData 部分错误（原文句末缺少句号）。 |

---

### 3.3 2011-06

**操作数：** 2

##### 3.3.1 deleteChildrenInHierarchy

**接口路径：** `Classification-2011-06-Classification/deleteChildrenInHierarchy`

**API 版本：** `2011-06`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 在满足删除策略的前提下，删除给定类之下的子层级或挂载对象。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2011_06.Classification.deleteChildrenInHierarchy`

**请求（input）：**

```json
{
  "optionsInput": [
    {
      "id": "",
      "theRecurseOption": "",
      "theViewsOption": "",
      "theIcosOption": "",
      "theWSOOption": "",
      "theChildrenOnlyOption": "",
      "theIgnoreOption": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `optionsInput` | Teamcenter::Soa::Classification::_2011_06::Classification::HierarchyInfoAndOptions[] | 删除层级：`HierarchyInfoAndOptions`，包含要清空层级的分类类、需一并删除的业务对象与子项选项。 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.3.2 getLibraryHierarchy

**接口路径：** `Classification-2011-06-Classification/getLibraryHierarchy`

**API 版本：** `2011-06`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 按传入分类库取值获取库内的层级拓扑（类树引用）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2011_06.Classification.getLibraryHierarchy`

**请求（input）：**

```json
{
  "libraryValues": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `libraryValues` | std::string[] | `getLibraryHierarchy` 的分类库上下文键（用于裁剪返回树）。 |

**响应（output）：**

```json
{
  "clsInfo": [
    {
      "classDefn": {
        "id": "",
        "parent": "",
        "instanceCount": "",
        "viewCount": "",
        "documents": [
          {
            "documentType": "",
            "ticket": "",
            "originalFileName": ""
          }
        ],
        "name": "",
        "shortName": "",
        "description": "",
        "unitBase": "UNSPECIFIED",
        "options": {
          "isValid": "",
          "isAbstract": "",
          "isGroup": "",
          "isAssembly": ""
        },
        "userData1": "",
        "userData2": "",
        "childCount": ""
      },
      "classBO": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `clsInfo` | Teamcenter::Soa::Classification::_2011_06::Classification::ClassInfo[] | 当前分类库中符合条件的类引用集合。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 出错时 Key LOV ID 与错误信息成对出现于 ServiceData 部分错误列表。 |

---

### 3.4 2011-12

**操作数：** 1

##### 3.4.1 getClassificationObjectInfo

**接口路径：** `Classification-2011-12-Classification/getClassificationObjectInfo`

**API 版本：** `2011-12`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 读取 ICO 的扩展详情（聚合属性与其它展示信息）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2011_12.Classification.getClassificationObjectInfo`

**请求（input）：**

```json
{
  "icoUids": [
    ""
  ],
  "attributeIds": [],
  "getOptimizedValues": "",
  "fetchDescriptor": "",
  "locale": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `icoUids` | std::string[] | 需要展开全部属性及 LOV、描述符快照的 ICO。 |
| `attributeIds` | int[] | 在指定 ICO 上需要读出的若干属性 UID。 |
| `getOptimizedValues` | bool | 是否读取「优化后」的属性显示值（更易读并减少首尾无效零），例如更愿意显示「1 km」而非「1000 m」。 |
| `fetchDescriptor` | bool | 为 true 时同时拉取各项分类属性的属性描述符（元数据）。 |
| `locale` | std::string | 本地化语言环境，用以解读属性字面量与加载属性描述文案。 |

**响应（output）：**

```json
{
  "classificationObjectInfo": {},
  "classAttributeDesc": {},
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classificationObjectInfo` | Teamcenter::Soa::Classification::_2011_12::Classification::ClassificationObjectInfoMap | ICO 与各分类属性的引用向量。 |
| `classAttributeDesc` | Teamcenter::Soa::Classification::_2011_12::Classification::ClassAttributeDescMap | ICO 与其属性描述结构句柄列表。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 出错时出错项以 ICO（分类实例）对象的 ID 与错误信息关联后写入 ServiceData 部分错误列表。 |

---

### 3.5 2015-03

**操作数：** 1

##### 3.5.1 getKeyLOVsForDependentAttributes

**接口路径：** `Classification-2015-03-Classification/getKeyLOVsForDependentAttributes`

**API 版本：** `2015-03`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 为有依赖关系的分类属性拉取可用的 Key LOV 选项集合。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2015_03.Classification.getKeyLOVsForDependentAttributes`

**请求（input）：**

```json
{
  "dependencyAttributeStruct": [
    {
      "classID": "",
      "selectedAttributeID": "",
      "selectedValue": "",
      "attributeValues": [
        {
          "attributeID": "",
          "value": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `dependencyAttributeStruct` | Teamcenter::Soa::Classification::_2015_03::Classification::DependencyAttributeStruct[] | 每条输入：目标类 ID、发生变更的属性及新值、以及界面展示的其它属性与取值。 |

**响应（output）：**

```json
{
  "dependencyKeyLOVs": [
    {
      "attributeID": "",
      "selectedKeys": [
        ""
      ],
      "keyLOVDefinition": {
        "id": "",
        "name": "",
        "keyLovtag": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "options": "",
        "keyLovEntries": [
          {
            "lovKey": "",
            "lovValue": "",
            "deprecatedSatus": ""
          }
        ],
        "owningSite": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "sharedSites": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `dependencyKeyLOVs` | Teamcenter::Soa::Classification::_2015_03::Classification::DependencyKeyLOVDescriptor[] | 待修改的每个属性：属性 ID、从 Key LOV 中选定条目的 Key、以及该 Key LOV 的定义。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 所有异常均归入服务数据的「部分错误」列表。 |

---

### 3.6 2015-10

**操作数：** 1

##### 3.6.1 getClassDefinitions

**接口路径：** `Classification-2015-10-Classification/getClassDefinitions`

**API 版本：** `2015-10`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 返回类或视图的 BMIDE 结构化定义快照（字符串 ID → ClassDef）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2015_10.Classification.getClassDefinitions`

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
| `classIDs` | std::string[] | 分类类的 ID 列表。 |

**响应（output）：**

```json
{
  "classDefinitionMap": {},
  "classAttributesDefinitionMap": {},
  "keyLOVDefinitionMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classDefinitionMap` | Teamcenter::Soa::Classification::_2015_10::Classification::ClassDefinitionMap | 分类类或分类视图 ID 与类定义的对应关系（string/ClassDef）。 |
| `classAttributesDefinitionMap` | Teamcenter::Soa::Classification::_2015_10::Classification::ClassAttributesDefinitionMap | 分类类或视图 ID 与「类属性定义」的映射（string/ClassAttributesDefinition）。 |
| `keyLOVDefinitionMap` | Teamcenter::Soa::Classification::_2015_10::Classification::KeyLOVDefinitionMap | 已使用的分类 Key LOV 与其定义的映射（字符串 ID → KeyLOVDefinition2）。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 所有异常均归入服务数据的「部分错误」列表。 |

---

### 3.7 2016-03

**操作数：** 3

##### 3.7.1 convertValues

**接口路径：** `Classification-2016-03-Classification/convertValues`

**API 版本：** `2016-03`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 在分类度量体系下对某些属性取值做换算或等价转换。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2016_03.Classification.convertValues`

**请求（input）：**

```json
{
  "valueConversionInputs": [
    {
      "inputValues": [
        ""
      ],
      "inputUnit": "",
      "outputUnit": "",
      "outputFormat": {
        "formatType": "",
        "formatModifier1": "",
        "formatModifier2": "",
        "formatLength": ""
      },
      "options": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `valueConversionInputs` | Teamcenter::Soa::Classification::_2016_03::Classification::ValueConversionInput[] | 待执行度量单位或内部存储格式换算的数值集合。 |

**响应（output）：**

```json
{
  "convertedValues": [
    {
      "convertedValues": [
        ""
      ]
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `convertedValues` | Teamcenter::Soa::Classification::_2016_03::Classification::ValueConversionOutput[] | `convertValues` 输出：完成单位换算或等价转换的属性值矩阵。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 数值/单位转换失败时记录在 ServiceData 部分错误列表。 |

---

##### 3.7.2 getChildrenExtended

**接口路径：** `Classification-2016-03-Classification/getChildrenExtended`

**API 版本：** `2016-03`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 获取子节点扩展信息（可传按位选项控制父计数、图标等附加数据）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2016_03.Classification.getChildrenExtended`

**请求（input）：**

```json
{
  "classObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "filterForWriteAccess": "",
  "options": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classObjects` | Teamcenter::BusinessObject[] | 需要枚举直接子节点的父类实例。 |
| `filterForWriteAccess` | bool | 为 true 时过滤掉用户对「分类」无写权限的类，不包含在返回值中。 |
| `options` | int | 按位扩展选项（可组合）：1«0 在 ExtendedClassDef 中附带父节点信息；1«1 返回子节点数量；1«2 返回实例数量；1«3 在 BaseClassDef 中返回图标文档；1«4 在 ExtendedClassDef 中返回类图像文档。若原文含「font」等标签，含义与 SOA Api Browser 中 HTML 描述一致。 |

**响应（output）：**

```json
{
  "classDescriptions": [
    {
      "classDescriptions": [
        {
          "classDef": {
            "classID": "",
            "classBO": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "className": "",
            "isAbstract": "",
            "classUnitBase": "",
            "classIconLoaded": "",
            "classIconDocument": {
              "documentType": "",
              "ticket": "",
              "originalFileName": ""
            }
          },
          "parentDefs": [
            {
              "classID": "",
              "classBO": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "className": "",
              "isAbstract": "",
              "classUnitBase": "",
              "classIconLoaded": "",
              "classIconDocument": {
                "documentType": "",
                "ticket": "",
                "originalFileName": ""
              }
            }
          ],
          "classShortName": "",
          "classDescription": "",
          "classUserData1": "",
          "classUserData2": "",
          "classChildCount": "",
          "classInstanceCount": "",
          "classImagesLoaded": "",
          "classImageDocuments": [
            {
              "documentType": "",
              "ticket": "",
              "originalFileName": ""
            }
          ]
        }
      ]
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classDescriptions` | Teamcenter::Soa::Classification::_2016_03::Classification::GetChildrenExtendedOutput[] | 对每个输入父类找到的子分类类列表（合并描述）。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 出错时以小写原文「class」所指的分类类 ID 与错误信息关联，记入 ServiceData 部分错误列表。 |

---

##### 3.7.3 searchClassesExtended

**接口路径：** `Classification-2016-03-Classification/searchClassesExtended`

**API 版本：** `2016-03`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 执行增强型分类类检索（含按位选项、写权限筛选等）。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2016_03.Classification.searchClassesExtended`

**请求（input）：**

```json
{
  "searchCriterias": [
    {
      "attributeId": "",
      "query": ""
    }
  ],
  "sortAttributes": [],
  "filterForWriteAccess": "",
  "options": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchCriterias` | Teamcenter::Soa::Classification::_2007_01::Classification::SearchAttribute[] | 类搜索条件的结构数组。支持的键：类 ID=-600；类名称=-607；短名称=-608；用户自定义字段=-612/-613；亦可用扩展条件「指定属性」（8 为属性 ID，3 为属性名检索）。 |
| `sortAttributes` | int[] | 排序依据属性 ID=-600/-607/-608/-612/-613 分别对应「类编码、名称、短名、两组用户扩展」。 |
| `filterForWriteAccess` | bool | 为 true 时过滤掉用户对「分类」无写权限的类，不包含在返回值中。 |
| `options` | int | 按位扩展选项（可组合）：1«0 在 ExtendedClassDef 中附带父节点信息；1«1 返回子节点数量；1«2 返回实例数量；1«3 在 BaseClassDef 中返回图标文档；1«4 在 ExtendedClassDef 中返回类图像文档。若原文含「font」等标签，含义与 SOA Api Browser 中 HTML 描述一致。 |

**响应（output）：**

```json
{
  "classDescriptions": [
    {
      "classDescriptions": [
        {
          "classDef": {
            "classID": "",
            "classBO": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "className": "",
            "isAbstract": "",
            "classUnitBase": "",
            "classIconLoaded": "",
            "classIconDocument": {
              "documentType": "",
              "ticket": "",
              "originalFileName": ""
            }
          },
          "parentDefs": [
            {
              "classID": "",
              "classBO": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "className": "",
              "isAbstract": "",
              "classUnitBase": "",
              "classIconLoaded": "",
              "classIconDocument": {
                "documentType": "",
                "ticket": "",
                "originalFileName": ""
              }
            }
          ],
          "classShortName": "",
          "classDescription": "",
          "classUserData1": "",
          "classUserData2": "",
          "classChildCount": "",
          "classInstanceCount": "",
          "classImagesLoaded": "",
          "classImageDocuments": [
            {
              "documentType": "",
              "ticket": "",
              "originalFileName": ""
            }
          ]
        }
      ]
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `classDescriptions` | Teamcenter::Soa::Classification::_2016_03::Classification::SearchClassesExtendedOutput[] | 按搜索条件找到的类定义条目列表。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 检索流程中的失败记入 ServiceData 部分错误列表。 |

---

### 3.8 2016-09

**操作数：** 1

##### 3.8.1 findValues

**接口路径：** `Classification-2016-09-Classification/findValues`

**API 版本：** `2016-09`  
**Service：** `Classification`  
**Library：** `Classification`

**说明：** 为给定上下文查找合规或可选的属性取值集合。

**Soa Inclusion：** `Teamcenter.Soa.Classification._2016_09.Classification.findValues`

**请求（input）：**

```json
{
  "findValueInputs": [
    {
      "attributeID": "",
      "classID": "",
      "searchInBothUnitSystems": "",
      "activeUnitsystem": "",
      "attributeValues": [
        {
          "id": "",
          "value": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `findValueInputs` | Teamcenter::Soa::Classification::_2016_09::Classification::FindValueInput[] | `findValues`：描述待匹配分类属性上下文与取值条件的聚合输入。 |

**响应（output）：**

```json
{
  "findValuesOutputs": [
    {
      "foundValues": [
        {
          "unitSystem": "",
          "value": "",
          "count": ""
        }
      ]
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `findValuesOutputs` | Teamcenter::Soa::Classification::_2016_09::Classification::FindValuesOutput[] | `findValues` 根据输入匹配到的可取枚举/区间值范围。 |
| `svcData` | Teamcenter::Soa::Server::ServiceData | 整次操作的失败记入 ServiceData 部分错误列表。 |

---

---

## 4. 附录

### 合并索引

| API 版本 | 操作 | Url | Soa Inclusion |
|----------|------|-----|---------------|
| 2007-01 | `createClassificationObjects` | `Classification-2007-01-Classification/createClassificationObjects` | `Teamcenter.Soa.Classification._2007_01.Classification.createClassificationObjects` |
| 2007-01 | `deleteClassificationObjects` | `Classification-2007-01-Classification/deleteClassificationObjects` | `Teamcenter.Soa.Classification._2007_01.Classification.deleteClassificationObjects` |
| 2007-01 | `findClassificationObjects` | `Classification-2007-01-Classification/findClassificationObjects` | `Teamcenter.Soa.Classification._2007_01.Classification.findClassificationObjects` |
| 2007-01 | `findClassifiedObjects` | `Classification-2007-01-Classification/findClassifiedObjects` | `Teamcenter.Soa.Classification._2007_01.Classification.findClassifiedObjects` |
| 2007-01 | `getAttributesForClasses` | `Classification-2007-01-Classification/getAttributesForClasses` | `Teamcenter.Soa.Classification._2007_01.Classification.getAttributesForClasses` |
| 2007-01 | `getChildren` | `Classification-2007-01-Classification/getChildren` | `Teamcenter.Soa.Classification._2007_01.Classification.getChildren` |
| 2007-01 | `getClassDescriptions` | `Classification-2007-01-Classification/getClassDescriptions` | `Teamcenter.Soa.Classification._2007_01.Classification.getClassDescriptions` |
| 2007-01 | `getClassificationObjects` | `Classification-2007-01-Classification/getClassificationObjects` | `Teamcenter.Soa.Classification._2007_01.Classification.getClassificationObjects` |
| 2007-01 | `getFileIds` | `Classification-2007-01-Classification/getFileIds` | `Teamcenter.Soa.Classification._2007_01.Classification.getFileIds` |
| 2007-01 | `getKeyLOVs` | `Classification-2007-01-Classification/getKeyLOVs` | `Teamcenter.Soa.Classification._2007_01.Classification.getKeyLOVs` |
| 2007-01 | `getParents` | `Classification-2007-01-Classification/getParents` | `Teamcenter.Soa.Classification._2007_01.Classification.getParents` |
| 2007-01 | `getPartFamilyTemplates` | `Classification-2007-01-Classification/getPartFamilyTemplates` | `Teamcenter.Soa.Classification._2007_01.Classification.getPartFamilyTemplates` |
| 2007-01 | `search` | `Classification-2007-01-Classification/search` | `Teamcenter.Soa.Classification._2007_01.Classification.search` |
| 2007-01 | `searchByInstanceId` | `Classification-2007-01-Classification/searchByInstanceId` | `Teamcenter.Soa.Classification._2007_01.Classification.searchByInstanceId` |
| 2007-01 | `searchForClasses` | `Classification-2007-01-Classification/searchForClasses` | `Teamcenter.Soa.Classification._2007_01.Classification.searchForClasses` |
| 2007-01 | `updateClassificationObjects` | `Classification-2007-01-Classification/updateClassificationObjects` | `Teamcenter.Soa.Classification._2007_01.Classification.updateClassificationObjects` |
| 2009-10 | `autoComputeAttributes` | `Classification-2009-10-Classification/autoComputeAttributes` | `Teamcenter.Soa.Classification._2009_10.Classification.autoComputeAttributes` |
| 2009-10 | `createOrUpdateKeyLOVs` | `Classification-2009-10-Classification/createOrUpdateKeyLOVs` | `Teamcenter.Soa.Classification._2009_10.Classification.createOrUpdateKeyLOVs` |
| 2009-10 | `getAttributesForClasses2` | `Classification-2009-10-Classification/getAttributesForClasses2` | `Teamcenter.Soa.Classification._2009_10.Classification.getAttributesForClasses2` |
| 2009-10 | `getKeyLOVs2` | `Classification-2009-10-Classification/getKeyLOVs2` | `Teamcenter.Soa.Classification._2009_10.Classification.getKeyLOVs2` |
| 2011-06 | `deleteChildrenInHierarchy` | `Classification-2011-06-Classification/deleteChildrenInHierarchy` | `Teamcenter.Soa.Classification._2011_06.Classification.deleteChildrenInHierarchy` |
| 2011-06 | `getLibraryHierarchy` | `Classification-2011-06-Classification/getLibraryHierarchy` | `Teamcenter.Soa.Classification._2011_06.Classification.getLibraryHierarchy` |
| 2011-12 | `getClassificationObjectInfo` | `Classification-2011-12-Classification/getClassificationObjectInfo` | `Teamcenter.Soa.Classification._2011_12.Classification.getClassificationObjectInfo` |
| 2015-03 | `getKeyLOVsForDependentAttributes` | `Classification-2015-03-Classification/getKeyLOVsForDependentAttributes` | `Teamcenter.Soa.Classification._2015_03.Classification.getKeyLOVsForDependentAttributes` |
| 2015-10 | `getClassDefinitions` | `Classification-2015-10-Classification/getClassDefinitions` | `Teamcenter.Soa.Classification._2015_10.Classification.getClassDefinitions` |
| 2016-03 | `convertValues` | `Classification-2016-03-Classification/convertValues` | `Teamcenter.Soa.Classification._2016_03.Classification.convertValues` |
| 2016-03 | `getChildrenExtended` | `Classification-2016-03-Classification/getChildrenExtended` | `Teamcenter.Soa.Classification._2016_03.Classification.getChildrenExtended` |
| 2016-03 | `searchClassesExtended` | `Classification-2016-03-Classification/searchClassesExtended` | `Teamcenter.Soa.Classification._2016_03.Classification.searchClassesExtended` |
| 2016-09 | `findValues` | `Classification-2016-09-Classification/findValues` | `Teamcenter.Soa.Classification._2016_09.Classification.findValues` |

### 重新生成

```bash
node generate-classification-doc.js
```
