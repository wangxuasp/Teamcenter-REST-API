# Teamcenter SOA API — Query 接口文档（TC 2512）

> 本文档汇总 **Query** Library 下**全部 API 版本（年-月）**的 SOA 操作，已按版本与 Service 双向合并整理。
> 功能说明与**参数说明均为简体中文**（参数说明由原文自动翻译并校正）。
> 数据来源：TC 2512 SOA Api Browser（`structure.js`）。
>
> - **API 版本数：** 13 个
> - **操作总数：** 22 个（含 2 个多版本操作）
> - **Url 格式：** `Query-{Year}-{Service}/{operation}`

---

## 目录

1. [API 版本总览](#1-api-版本总览)
2. [按 Service 合并（跨版本）](#2-按-service-合并跨版本)
3. [按 API 版本（年-月）归档](#3-按-api-版本年-月归档)
4. [附录](#4-附录)

---

## 1. API 版本总览

Query 库包含 **SavedQuery**（已保存查询/简单搜索）与 **Finder**（搜索路由/分组）两类 Service，部分操作存在多个年-月版本契约。

| API 版本 | Service | 操作 | Url |
|----------|---------|------|-----|
| **2006-03** | SavedQuery | `describeSavedQueries` | `Query-2006-03-SavedQuery/describeSavedQueries` |
| **2006-03** | SavedQuery | `executeSavedQuery` | `Query-2006-03-SavedQuery/executeSavedQuery` |
| **2006-03** | SavedQuery | `getSavedQueries` | `Query-2006-03-SavedQuery/getSavedQueries` |
| **2007-01** | SavedQuery | `deleteQueryCriterias` | `Query-2007-01-SavedQuery/deleteQueryCriterias` |
| **2007-01** | SavedQuery | `reorderSavedQueryCriterias` | `Query-2007-01-SavedQuery/reorderSavedQueryCriterias` |
| **2007-01** | SavedQuery | `retrieveQueryCriterias` | `Query-2007-01-SavedQuery/retrieveQueryCriterias` |
| **2007-01** | SavedQuery | `saveQueryCriterias` | `Query-2007-01-SavedQuery/saveQueryCriterias` |
| **2007-06** | Finder | `findWorkspaceObjects` | `Query-2007-06-Finder/findWorkspaceObjects` |
| **2007-06** | SavedQuery | `executeSavedQueries` | `Query-2007-06-SavedQuery/executeSavedQueries` |
| **2007-06** | SavedQuery | `retrieveSearchCriteria` | `Query-2007-06-SavedQuery/retrieveSearchCriteria` |
| **2007-06** | SavedQuery | `saveSearchCriteria` | `Query-2007-06-SavedQuery/saveSearchCriteria` |
| **2007-09** | SavedQuery | `executeSavedQueries` | `Query-2007-09-SavedQuery/executeSavedQueries` |
| **2008-06** | SavedQuery | `executeSavedQueries` | `Query-2008-06-SavedQuery/executeSavedQueries` |
| **2010-04** | SavedQuery | `findSavedQueries` | `Query-2010-04-SavedQuery/findSavedQueries` |
| **2010-09** | SavedQuery | `executeBusinessObjectQueries` | `Query-2010-09-SavedQuery/executeBusinessObjectQueries` |
| **2012-10** | Finder | `performSearch` | `Query-2012-10-Finder/performSearch` |
| **2013-05** | SavedQuery | `createSavedQueries` | `Query-2013-05-SavedQuery/createSavedQueries` |
| **2014-11** | Finder | `groupObjectsByProperties` | `Query-2014-11-Finder/groupObjectsByProperties` |
| **2014-11** | Finder | `performSearch` | `Query-2014-11-Finder/performSearch` |
| **2018-11** | SavedQuery | `executeBOQueriesWithContext` | `Query-2018-11-SavedQuery/executeBOQueriesWithContext` |
| **2019-06** | SavedQuery | `executeBOQueriesWithSort` | `Query-2019-06-SavedQuery/executeBOQueriesWithSort` |
| **2020-04** | SavedQuery | `executeBOQueriesWithSortAndContext` | `Query-2020-04-SavedQuery/executeBOQueriesWithSortAndContext` |

### 版本—Service 对照

| API 版本 | 包含的 Service | 操作数 |
|----------|----------------|--------|
| 2006-03 | SavedQuery | 3 |
| 2007-01 | SavedQuery | 4 |
| 2007-06 | Finder、SavedQuery | 4 |
| 2007-09 | SavedQuery | 1 |
| 2008-06 | SavedQuery | 1 |
| 2010-04 | SavedQuery | 1 |
| 2010-09 | SavedQuery | 1 |
| 2012-10 | Finder | 1 |
| 2013-05 | SavedQuery | 1 |
| 2014-11 | Finder | 2 |
| 2018-11 | SavedQuery | 1 |
| 2019-06 | SavedQuery | 1 |
| 2020-04 | SavedQuery | 1 |

### 多版本操作说明

| 操作 | 可用 API 版本 | 说明 |
|------|---------------|------|
| `executeSavedQueries` | `2007-06`、`2007-09`、`2008-06` | 调用时必须使用对应版本的 Url |
| `performSearch` | `2012-10`、`2014-11` | 调用时必须使用对应版本的 Url |

---

## 2. 按 Service 合并（跨版本）

同一 Service 下按 **API 版本（年-月）** 分组；同名多版本操作分别列出。

### 2.1 查找器（Finder）

**涵盖 API 版本：** `2007-06`、`2012-10`、`2014-11`  
**操作数：** 4

#### 版本 2007-06

##### 2.1.1.1 findWorkspaceObjects

**接口路径：** `Query-2007-06-Finder/findWorkspaceObjects`

**API 版本：** `2007-06`  
**Service：** `Finder`  
**Library：** `Query`

**说明：** 通过 WSOFindSet 集合在数据库中查询 WorkspaceObject；每个 FindSet 满足条件时生成对应输出及对象 tag。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_06.Finder.findWorkspaceObjects`

**请求（input）：**

```json
{
  "findList": [
    {
      "criterias": [
        {
          "objectType": "",
          "objectName": "",
          "scope": "WSO_scope_All",
          "owner": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "group": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createdBefore": "0001-01-01T00:00:00",
          "modifiedBefore": "0001-01-01T00:00:00",
          "releasedBefore": "0001-01-01T00:00:00",
          "createdAfter": "0001-01-01T00:00:00",
          "modifiedAfter": "0001-01-01T00:00:00",
          "releasedAfter": "0001-01-01T00:00:00"
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `findList` | Teamcenter::Soa::Query::_2007_06::Finder::WSOFindSet[] | A WSOFindSet used to find workspace objects. |

**响应（output）：**

```json
{
  "outputList": [
    {
      "findSetIndex": "",
      "foundObjects": [
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
| `outputList` | Teamcenter::Soa::Query::_2007_06::Finder::FindWorkspaceObjectsOutput[] | A found workspace objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 版本 2012-10

##### 2.1.2.1 performSearch

**接口路径：** `Query-2012-10-Finder/performSearch`

**API 版本：** `2012-10`  
**Service：** `Finder`  
**Library：** `Query`

**说明：** 将搜索请求路由到指定 providerName 的搜索提供者（2012-10 版契约）。

**Soa Inclusion：** `Teamcenter.Soa.Query._2012_10.Finder.performSearch`

**请求（input）：**

```json
{
  "searchInput": {
    "providerName": "Awp0SavedQuerySearchProvider",
    "searchCriteria": {},
    "startIndex": "",
    "maxToReturn": "",
    "maxToLoad": "",
    "searchFilterMap": {},
    "searchSortCriteria": [
      {
        "fieldName": "",
        "sortDirection": "ASC"
      }
    ],
    "searchFilterFieldSortType": "Alphabetical",
    "attributesToInflate": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchInput` | Teamcenter::Soa::Query::_2012_10::Finder::SearchInput | 搜索输入参数，含 providerName、searchCriteria、分页与排序等。 |

**响应（output）：**

```json
{
  "searchResults": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "totalFound": "",
  "totalLoaded": "",
  "searchFilterMap": {},
  "searchFilterCategories": [
    {
      "internalName": "",
      "displayName": "",
      "defaultFilterValueDisplayCount": ""
    }
  ],
  "defaultFilterFieldDisplayCount": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchResults` | Teamcenter::BusinessObject[] | 执行搜索后返回的业务对象列表。 |
| `totalFound` | int | 搜索命中的业务对象总数。 |
| `totalLoaded` | int | 本次实际加载的业务对象数量。 |
| `searchFilterMap` | Teamcenter::Soa::Query::_2012_10::Finder::SearchFilterMap | 按搜索过滤器字段分组的过滤器映射（字符串 → SearchFilter 列表）。 |
| `searchFilterCategories` | Teamcenter::Soa::Query::_2012_10::Finder::SearchFilterField[] | 按过滤器优先级排序的搜索过滤器分类列表。 |
| `defaultFilterFieldDisplayCount` | int | 默认显示的搜索过滤器分类数量。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 版本 2014-11

##### 2.1.3.1 groupObjectsByProperties

**接口路径：** `Query-2014-11-Finder/groupObjectsByProperties`

**API 版本：** `2014-11`  
**Service：** `Finder`  
**Library：** `Query`

**说明：** 按属性将业务对象分类到分组：输入 ObjectPropertyGroupInput，指定内部属性名、分组值及待分类对象列表。

**Soa Inclusion：** `Teamcenter.Soa.Query._2014_11.Finder.groupObjectsByProperties`

**请求（input）：**

```json
{
  "objectPropertyGroupInputList": [
    {
      "internalPropertyName": "",
      "propertyValues": [
        {
          "propertyGroupID": "",
          "startValue": "",
          "endValue": ""
        }
      ],
      "objectList": [
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
| `objectPropertyGroupInputList` | Teamcenter::Soa::Query::_2014_11::Finder::ObjectPropertyGroupInput[] | containing ObjectPropertyGroupInput objects that represents property name and property value information to group a input 业务对象 |

**响应（output）：**

```json
{
  "groupedObjectsList": [
    {
      "internalPropertyName": "",
      "groupedObjectsMap": {},
      "unmatchedObjectList": [
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
| `groupedObjectsList` | Teamcenter::Soa::Query::_2014_11::Finder::ObjectsGroupedByProperty[] | ObjectPropertyGrouping objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

##### 2.1.3.2 performSearch

**接口路径：** `Query-2014-11-Finder/performSearch`

**API 版本：** `2014-11`  
**Service：** `Finder`  
**Library：** `Query`

**说明：** 将搜索请求路由到指定 providerName 的搜索提供者（2014-11 版契约，支持自定义提供者扩展）。

**Soa Inclusion：** `Teamcenter.Soa.Query._2014_11.Finder.performSearch`

**请求（input）：**

```json
{
  "searchInput": {
    "providerName": "Awp0SavedQuerySearchProvider",
    "searchCriteria": {},
    "startIndex": "",
    "maxToReturn": "",
    "maxToLoad": "",
    "searchFilterMap": {},
    "searchSortCriteria": [
      {
        "fieldName": "",
        "sortDirection": "ASC"
      }
    ],
    "searchFilterFieldSortType": "",
    "attributesToInflate": [
      ""
    ],
    "internalPropertyName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchInput` | Teamcenter::Soa::Query::_2014_11::Finder::SearchInput2 | 搜索输入参数，含 providerName、searchCriteria、分页与排序等。 |

**响应（output）：**

```json
{
  "searchResults": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "totalFound": "",
  "totalLoaded": "",
  "searchFilterMap": {},
  "searchFilterCategories": [
    {
      "internalName": "",
      "displayName": "",
      "defaultFilterValueDisplayCount": ""
    }
  ],
  "defaultFilterFieldDisplayCount": "",
  "serviceData": "IServiceData",
  "objectsGroupedByProperty": {
    "internalPropertyName": "",
    "groupedObjectsMap": {},
    "unmatchedObjectList": [
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
| `searchResults` | Teamcenter::BusinessObject[] | 执行搜索后返回的业务对象列表。 |
| `totalFound` | int | 搜索命中的业务对象总数。 |
| `totalLoaded` | int | 本次实际加载的业务对象数量。 |
| `searchFilterMap` | Teamcenter::Soa::Query::_2014_11::Finder::SearchFilterMap2 | 按搜索过滤器字段分组的过滤器映射（字符串 → SearchFilter 列表）。 |
| `searchFilterCategories` | Teamcenter::Soa::Query::_2012_10::Finder::SearchFilterField[] | 按过滤器优先级排序的搜索过滤器分类列表。 |
| `defaultFilterFieldDisplayCount` | int | 默认显示的搜索过滤器分类数量。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |
| `objectsGroupedByProperty` | Teamcenter::Soa::Query::_2014_11::Finder::ObjectsGroupedByProperty | structure containing an internal property name and a map of objects to property group id. It also contains a unmatched objects which don't match any group. |

---

### 2.2 已保存查询（SavedQuery）

**涵盖 API 版本：** `2006-03`、`2007-01`、`2007-06`、`2007-09`、`2008-06`、`2010-04`、`2010-09`、`2013-05`、`2018-11`、`2019-06`、`2020-04`  
**操作数：** 18

#### 版本 2006-03

##### 2.2.1.1 describeSavedQueries

**接口路径：** `Query-2006-03-SavedQuery/describeSavedQueries`

**API 版本：** `2006-03`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 返回输入的已保存查询的详细描述，包括各子句的属性名、条目名、运算、逻辑运算、LOV 及属性类型等完整子句信息。

**Soa Inclusion：** `Teamcenter.Soa.Query._2006_03.SavedQuery.describeSavedQueries`

**请求（input）：**

```json
{
  "queries": [
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
| `queries` | Teamcenter::ImanQuery[] | 待执行的已保存查询列表。 |

**响应（output）：**

```json
{
  "fieldLists": [
    {
      "fields": [
        {
          "attributeName": "",
          "entryName": "",
          "logicalOperation": "",
          "mathOperation": "",
          "value": "",
          "lov": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "attributeType": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `fieldLists` | Teamcenter::Soa::Query::_2006_03::SavedQuery::SavedQueryFieldListObject[] | A fields 各 input query. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

##### 2.2.1.2 executeSavedQuery

**接口路径：** `Query-2006-03-SavedQuery/executeSavedQuery`

**API 版本：** `2006-03`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 按输入的查询条目与取值执行单条已保存查询；可限制返回条数，并返回实际找到的对象数量。

**Soa Inclusion：** `Teamcenter.Soa.Query._2006_03.SavedQuery.executeSavedQuery`

**请求（input）：**

```json
{
  "query": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "entries": [
    ""
  ],
  "values": [
    ""
  ],
  "limit": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `query` | Teamcenter::ImanQuery | 已保存查询对象或查询定义。 |
| `entries` | std::string[] | 查询条目名称列表。 |
| `values` | std::string[] | 查询条目对应的取值列表。 |
| `limit` | int | 返回结果数量上限；0 表示不限制。 |

**响应（output）：**

```json
{
  "nFound": "",
  "objects": [
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
| `nFound` | int | number of objects found by query. |
| `objects` | Teamcenter::BusinessObject[] | objects returned. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

##### 2.2.1.3 getSavedQueries

**接口路径：** `Query-2006-03-SavedQuery/getSavedQueries`

**API 版本：** `2006-03`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 获取系统中全部已保存查询的列表，包含查询标识、名称与描述等信息。常用于搜索视图或 Query Builder 加载可用查询。

**Soa Inclusion：** `Teamcenter.Soa.Query._2006_03.SavedQuery.getSavedQueries`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "queries": [
    {
      "query": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "name": "",
      "description": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `queries` | Teamcenter::Soa::Query::_2006_03::SavedQuery::SavedQueryObject[] | 待执行的已保存查询列表。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 版本 2007-01

##### 2.2.2.1 deleteQueryCriterias

**接口路径：** `Query-2007-01-SavedQuery/deleteQueryCriterias`

**API 版本：** `2007-01`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 按名称删除指定的已保存搜索条件（My Saved Searches）。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_01.SavedQuery.deleteQueryCriterias`

**请求（input）：**

```json
{
  "queryCriteriaNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `queryCriteriaNames` | std::string[] | A saved search names to delete. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.2.2.2 reorderSavedQueryCriterias

**接口路径：** `Query-2007-01-SavedQuery/reorderSavedQueryCriterias`

**API 版本：** `2007-01`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 调整「我的已保存搜索」列表中查询条件的顺序；输入列表须为已存在的条件名称。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_01.SavedQuery.reorderSavedQueryCriterias`

**请求（input）：**

```json
{
  "queryCriteriaNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `queryCriteriaNames` | std::string[] | - query criteria names 含new order. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.2.2.3 retrieveQueryCriterias

**接口路径：** `Query-2007-01-SavedQuery/retrieveQueryCriterias`

**API 版本：** `2007-01`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 按搜索名称检索已保存搜索的详细信息。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_01.SavedQuery.retrieveQueryCriterias`

**请求（input）：**

```json
{
  "queryCriteriaNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `queryCriteriaNames` | std::string[] | A search names 用于which to retrieve information. |

**响应（output）：**

```json
{
  "output": [
    {
      "searchName": "",
      "queryName": "",
      "keys": [
        ""
      ],
      "values": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Query::_2007_01::SavedQuery::SaveQueryCriteriaInfo[] | SaveQueryCriteriaInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

##### 2.2.2.4 saveQueryCriterias

**接口路径：** `Query-2007-01-SavedQuery/saveQueryCriterias`

**API 版本：** `2007-01`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 保存已保存搜索：包含搜索名称、查询名、条目名与条目值等；校验名称与键值对合法性。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_01.SavedQuery.saveQueryCriterias`

**请求（input）：**

```json
{
  "queryCriterias": [
    {
      "searchName": "",
      "queryName": "",
      "keys": [
        ""
      ],
      "values": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `queryCriterias` | Teamcenter::Soa::Query::_2007_01::SavedQuery::SaveQueryCriteriaInfo[] | A SaveQueryCriteriaInfo representing saved searches to be saved to 数据库. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2007-06

##### 2.2.3.1 executeSavedQueries

**接口路径：** `Query-2007-06-SavedQuery/executeSavedQueries`

**API 版本：** `2007-06`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 批量执行已保存查询（类型：本地查询 QRY_RUN_BY_TC、用户退出 QRY_RUN_BY_USER_EXIT、关键字 QRY_RUN_BY_KEYWORD_SEARCH 等）。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_06.SavedQuery.executeSavedQueries`

**请求（input）：**

```json
{
  "input": [
    {
      "query": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "entries": [
        ""
      ],
      "values": [
        ""
      ],
      "limitList": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "limitListCount": "",
      "maxNumToReturn": "",
      "resultsType": "",
      "maxNumToInflate": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Query::_2007_06::SavedQuery::SavedQueryInput[] | A set of QueryInput data structures. |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "numOfObjects": "",
      "objectsRelMap": [],
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
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_06::SavedQuery::SavedQueryResults[] | A set of SavedQueryResults data structures |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

##### 2.2.3.2 retrieveSearchCriteria

**接口路径：** `Query-2007-06-SavedQuery/retrieveSearchCriteria`

**API 版本：** `2007-06`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 按已保存搜索名称检索对应的搜索条件条目信息。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_06.SavedQuery.retrieveSearchCriteria`

**请求（input）：**

```json
{
  "searchNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchNames` | std::string[] | A set of saved search names 用于which their corresponding 搜索条件 are to be retrieved. |

**响应（output）：**

```json
{
  "output": [
    {
      "searchName": "",
      "queryName": "",
      "keys": [
        ""
      ],
      "values": [
        ""
      ],
      "resultsType": "",
      "virtualFolderPath": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Query::_2007_06::SavedQuery::SaveSearchCriteriaInfo[] | A SavedSearchCriteriaInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

##### 2.2.3.3 saveSearchCriteria

**接口路径：** `Query-2007-06-SavedQuery/saveSearchCriteria`

**API 版本：** `2007-06`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 保存一组搜索条件到「我的已保存搜索」集合；部分错误通过搜索名称引用。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_06.SavedQuery.saveSearchCriteria`

**请求（input）：**

```json
{
  "searchCriteria": [
    {
      "searchName": "",
      "queryName": "",
      "keys": [
        ""
      ],
      "values": [
        ""
      ],
      "resultsType": "",
      "virtualFolderPath": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchCriteria` | Teamcenter::Soa::Query::_2007_06::SavedQuery::SaveSearchCriteriaInfo[] | 搜索条件键值对，依提供者不同而不同。 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2007-09

##### 2.2.4.1 executeSavedQueries

**接口路径：** `Query-2007-09-SavedQuery/executeSavedQueries`

**API 版本：** `2007-09`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 批量执行已保存查询（类型：QRY_RUN_BY_TC、QRY_RUN_BY_KEYWORD_SEARCH）；支持平面模式与层级模式两种结果返回方式。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_09.SavedQuery.executeSavedQueries`

**请求（input）：**

```json
{
  "input": [
    {
      "query": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "entries": [
        ""
      ],
      "values": [
        ""
      ],
      "limitList": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "maxNumToReturn": "",
      "resultsType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryInput[] | A set of QueryInput data structures. |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 版本 2008-06

##### 2.2.5.1 executeSavedQueries

**接口路径：** `Query-2008-06-SavedQuery/executeSavedQueries`

**API 版本：** `2008-06`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 批量执行已保存查询（类型：本地查询、用户查询 QRY_RUN_BY_USER_QUERY、关键字搜索等）；支持平面/层级结果模式。

**Soa Inclusion：** `Teamcenter.Soa.Query._2008_06.SavedQuery.executeSavedQueries`

**请求（input）：**

```json
{
  "input": [
    {
      "query": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "entries": [
        ""
      ],
      "values": [
        ""
      ],
      "limitList": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "maxNumToReturn": "",
      "resultsType": "",
      "requestId": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Query::_2008_06::SavedQuery::QueryInput[] | A set of QueryInput data structures. |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 版本 2010-04

##### 2.2.6.1 findSavedQueries

**接口路径：** `Query-2010-04-SavedQuery/findSavedQueries`

**API 版本：** `2010-04`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 按名称、描述等条件查找已保存查询，支持名称/描述单独或组合匹配。

**Soa Inclusion：** `Teamcenter.Soa.Query._2010_04.SavedQuery.findSavedQueries`

**请求（input）：**

```json
{
  "inputCriteria": [
    {
      "queryNames": [
        ""
      ],
      "queryDescs": [
        ""
      ],
      "queryType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputCriteria` | Teamcenter::Soa::Query::_2010_04::SavedQuery::FindSavedQueriesCriteriaInput[] | Structure that contains input criteria required to find 已保存查询. |

**响应（output）：**

```json
{
  "savedQueries": [
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
| `savedQueries` | Teamcenter::ImanQuery[] | A 已保存查询 objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 版本 2010-09

##### 2.2.7.1 executeBusinessObjectQueries

**接口路径：** `Query-2010-09-SavedQuery/executeBusinessObjectQueries`

**API 版本：** `2010-09`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 执行业务对象简单搜索（Simple Search）并返回结果集及 ServiceData；部分错误通过索引引用。

**Soa Inclusion：** `Teamcenter.Soa.Query._2010_09.SavedQuery.executeBusinessObjectQueries`

**请求（input）：**

```json
{
  "inputs": [
    {
      "typeName": "",
      "clauses": [
        {
          "propName": "",
          "propValue": "",
          "mathOperator": "",
          "logicOperator": ""
        }
      ],
      "maxNumToReturn": "",
      "requestId": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Query::_2010_09::SavedQuery::BusinessObjectQueryInput[] | 业务对象 query inputs |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 版本 2013-05

##### 2.2.8.1 createSavedQueries

**接口路径：** `Query-2013-05-SavedQuery/createSavedQueries`

**API 版本：** `2013-05`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 根据输入属性结构批量创建已保存查询；新对象加入 ServiceData 的 Created 列表，失败信息通过 clientId 关联。

**Soa Inclusion：** `Teamcenter.Soa.Query._2013_05.SavedQuery.createSavedQueries`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "queryName": "",
      "queryDesc": "",
      "queryClass": "",
      "queryClauses": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Query::_2013_05::SavedQuery::SavedQueryProperties[] | A 已保存查询 is created 各 SavedQueryProperties in list. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2018-11

##### 2.2.9.1 executeBOQueriesWithContext

**接口路径：** `Query-2018-11-SavedQuery/executeBOQueriesWithContext`

**API 版本：** `2018-11`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 在上下文条件下执行业务对象简单搜索，支持 Logical Object 等实例查询，可指定类型、子句与最大返回数。

**Soa Inclusion：** `Teamcenter.Soa.Query._2018_11.SavedQuery.executeBOQueriesWithContext`

**请求（input）：**

```json
{
  "inputs": [
    {
      "boTypeName": "",
      "clauses": [
        {
          "propName": "",
          "propValue": "",
          "mathOperator": "",
          "logicOperator": ""
        }
      ],
      "maxNumToReturn": "",
      "requestId": "",
      "clientId": "",
      "configurationContextMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Query::_2018_11::SavedQuery::BusinessObjectQueryInput2[] | Execute 业务对象 searches (简单搜索) and return 搜索结果. A map of property name and ConfigurationContext pairs has been added to BusinessObjectQueryInput2 structure to support configuration context on Included 逻辑对象（Logical Object） … |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 版本 2019-06

##### 2.2.10.1 executeBOQueriesWithSort

**接口路径：** `Query-2019-06-SavedQuery/executeBOQueriesWithSort`

**API 版本：** `2019-06`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 执行业务对象查询并支持排序选项，返回查询结果集；失败时返回部分错误（如无效属性等）。

**Soa Inclusion：** `Teamcenter.Soa.Query._2019_06.SavedQuery.executeBOQueriesWithSort`

**请求（input）：**

```json
{
  "inputs": [
    {
      "boTypeName": "",
      "clauses": [
        {
          "propName": "",
          "propValue": "",
          "mathOperator": "",
          "logicOperator": ""
        }
      ],
      "sortOptions": [
        {
          "sortAttribute": "",
          "sortOrder": "AscendingOrder"
        }
      ],
      "maxNumToReturn": "",
      "requestId": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Query::_2019_06::SavedQuery::BusinessObjectQueryInput3[] | 业务对象 query inputs. |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 版本 2020-04

##### 2.2.11.1 executeBOQueriesWithSortAndContext

**接口路径：** `Query-2020-04-SavedQuery/executeBOQueriesWithSortAndContext`

**API 版本：** `2020-04`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 在上下文条件下执行业务对象简单搜索，支持排序、类型、子句与最大返回数等配置。

**Soa Inclusion：** `Teamcenter.Soa.Query._2020_04.SavedQuery.executeBOQueriesWithSortAndContext`

**请求（input）：**

```json
{
  "inputs": [
    {
      "boTypeName": "",
      "clauses": [
        {
          "propName": "",
          "propValue": "",
          "mathOperator": "",
          "logicOperator": ""
        }
      ],
      "sortOptions": [
        {
          "sortAttribute": "",
          "sortOrder": "AscendingOrder"
        }
      ],
      "maxNumToReturn": "",
      "requestId": "",
      "clientId": "",
      "configurationContextMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Query::_2020_04::SavedQuery::BusinessObjectQueryInput4[] | 业务对象 query inputs. |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

---

## 3. 按 API 版本（年-月）归档

按时间线列出各版本契约下的全部接口（与第 2 节一致，便于按版本检索）。

### 3.1 API 版本 2006-03

**Service：** SavedQuery  **操作数：** 3

#### 3.1.1 describeSavedQueries（2006-03）

**接口路径：** `Query-2006-03-SavedQuery/describeSavedQueries`

**API 版本：** `2006-03`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 返回输入的已保存查询的详细描述，包括各子句的属性名、条目名、运算、逻辑运算、LOV 及属性类型等完整子句信息。

**Soa Inclusion：** `Teamcenter.Soa.Query._2006_03.SavedQuery.describeSavedQueries`

**请求（input）：**

```json
{
  "queries": [
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
| `queries` | Teamcenter::ImanQuery[] | 待执行的已保存查询列表。 |

**响应（output）：**

```json
{
  "fieldLists": [
    {
      "fields": [
        {
          "attributeName": "",
          "entryName": "",
          "logicalOperation": "",
          "mathOperation": "",
          "value": "",
          "lov": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "attributeType": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `fieldLists` | Teamcenter::Soa::Query::_2006_03::SavedQuery::SavedQueryFieldListObject[] | A fields 各 input query. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 3.1.2 executeSavedQuery（2006-03）

**接口路径：** `Query-2006-03-SavedQuery/executeSavedQuery`

**API 版本：** `2006-03`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 按输入的查询条目与取值执行单条已保存查询；可限制返回条数，并返回实际找到的对象数量。

**Soa Inclusion：** `Teamcenter.Soa.Query._2006_03.SavedQuery.executeSavedQuery`

**请求（input）：**

```json
{
  "query": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "entries": [
    ""
  ],
  "values": [
    ""
  ],
  "limit": ""
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `query` | Teamcenter::ImanQuery | 已保存查询对象或查询定义。 |
| `entries` | std::string[] | 查询条目名称列表。 |
| `values` | std::string[] | 查询条目对应的取值列表。 |
| `limit` | int | 返回结果数量上限；0 表示不限制。 |

**响应（output）：**

```json
{
  "nFound": "",
  "objects": [
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
| `nFound` | int | number of objects found by query. |
| `objects` | Teamcenter::BusinessObject[] | objects returned. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 3.1.3 getSavedQueries（2006-03）

**接口路径：** `Query-2006-03-SavedQuery/getSavedQueries`

**API 版本：** `2006-03`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 获取系统中全部已保存查询的列表，包含查询标识、名称与描述等信息。常用于搜索视图或 Query Builder 加载可用查询。

**Soa Inclusion：** `Teamcenter.Soa.Query._2006_03.SavedQuery.getSavedQueries`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "queries": [
    {
      "query": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "name": "",
      "description": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `queries` | Teamcenter::Soa::Query::_2006_03::SavedQuery::SavedQueryObject[] | 待执行的已保存查询列表。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

### 3.2 API 版本 2007-01

**Service：** SavedQuery  **操作数：** 4

#### 3.2.1 deleteQueryCriterias（2007-01）

**接口路径：** `Query-2007-01-SavedQuery/deleteQueryCriterias`

**API 版本：** `2007-01`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 按名称删除指定的已保存搜索条件（My Saved Searches）。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_01.SavedQuery.deleteQueryCriterias`

**请求（input）：**

```json
{
  "queryCriteriaNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `queryCriteriaNames` | std::string[] | A saved search names to delete. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.2 reorderSavedQueryCriterias（2007-01）

**接口路径：** `Query-2007-01-SavedQuery/reorderSavedQueryCriterias`

**API 版本：** `2007-01`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 调整「我的已保存搜索」列表中查询条件的顺序；输入列表须为已存在的条件名称。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_01.SavedQuery.reorderSavedQueryCriterias`

**请求（input）：**

```json
{
  "queryCriteriaNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `queryCriteriaNames` | std::string[] | - query criteria names 含new order. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.3 retrieveQueryCriterias（2007-01）

**接口路径：** `Query-2007-01-SavedQuery/retrieveQueryCriterias`

**API 版本：** `2007-01`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 按搜索名称检索已保存搜索的详细信息。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_01.SavedQuery.retrieveQueryCriterias`

**请求（input）：**

```json
{
  "queryCriteriaNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `queryCriteriaNames` | std::string[] | A search names 用于which to retrieve information. |

**响应（output）：**

```json
{
  "output": [
    {
      "searchName": "",
      "queryName": "",
      "keys": [
        ""
      ],
      "values": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Query::_2007_01::SavedQuery::SaveQueryCriteriaInfo[] | SaveQueryCriteriaInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 3.2.4 saveQueryCriterias（2007-01）

**接口路径：** `Query-2007-01-SavedQuery/saveQueryCriterias`

**API 版本：** `2007-01`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 保存已保存搜索：包含搜索名称、查询名、条目名与条目值等；校验名称与键值对合法性。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_01.SavedQuery.saveQueryCriterias`

**请求（input）：**

```json
{
  "queryCriterias": [
    {
      "searchName": "",
      "queryName": "",
      "keys": [
        ""
      ],
      "values": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `queryCriterias` | Teamcenter::Soa::Query::_2007_01::SavedQuery::SaveQueryCriteriaInfo[] | A SaveQueryCriteriaInfo representing saved searches to be saved to 数据库. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.3 API 版本 2007-06

**Service：** Finder、SavedQuery  **操作数：** 4

#### 3.3.1 findWorkspaceObjects（2007-06）

**接口路径：** `Query-2007-06-Finder/findWorkspaceObjects`

**API 版本：** `2007-06`  
**Service：** `Finder`  
**Library：** `Query`

**说明：** 通过 WSOFindSet 集合在数据库中查询 WorkspaceObject；每个 FindSet 满足条件时生成对应输出及对象 tag。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_06.Finder.findWorkspaceObjects`

**请求（input）：**

```json
{
  "findList": [
    {
      "criterias": [
        {
          "objectType": "",
          "objectName": "",
          "scope": "WSO_scope_All",
          "owner": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "group": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createdBefore": "0001-01-01T00:00:00",
          "modifiedBefore": "0001-01-01T00:00:00",
          "releasedBefore": "0001-01-01T00:00:00",
          "createdAfter": "0001-01-01T00:00:00",
          "modifiedAfter": "0001-01-01T00:00:00",
          "releasedAfter": "0001-01-01T00:00:00"
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `findList` | Teamcenter::Soa::Query::_2007_06::Finder::WSOFindSet[] | A WSOFindSet used to find workspace objects. |

**响应（output）：**

```json
{
  "outputList": [
    {
      "findSetIndex": "",
      "foundObjects": [
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
| `outputList` | Teamcenter::Soa::Query::_2007_06::Finder::FindWorkspaceObjectsOutput[] | A found workspace objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 3.3.2 executeSavedQueries（2007-06）

**接口路径：** `Query-2007-06-SavedQuery/executeSavedQueries`

**API 版本：** `2007-06`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 批量执行已保存查询（类型：本地查询 QRY_RUN_BY_TC、用户退出 QRY_RUN_BY_USER_EXIT、关键字 QRY_RUN_BY_KEYWORD_SEARCH 等）。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_06.SavedQuery.executeSavedQueries`

**请求（input）：**

```json
{
  "input": [
    {
      "query": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "entries": [
        ""
      ],
      "values": [
        ""
      ],
      "limitList": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "limitListCount": "",
      "maxNumToReturn": "",
      "resultsType": "",
      "maxNumToInflate": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Query::_2007_06::SavedQuery::SavedQueryInput[] | A set of QueryInput data structures. |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "numOfObjects": "",
      "objectsRelMap": [],
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
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_06::SavedQuery::SavedQueryResults[] | A set of SavedQueryResults data structures |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 3.3.3 retrieveSearchCriteria（2007-06）

**接口路径：** `Query-2007-06-SavedQuery/retrieveSearchCriteria`

**API 版本：** `2007-06`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 按已保存搜索名称检索对应的搜索条件条目信息。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_06.SavedQuery.retrieveSearchCriteria`

**请求（input）：**

```json
{
  "searchNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchNames` | std::string[] | A set of saved search names 用于which their corresponding 搜索条件 are to be retrieved. |

**响应（output）：**

```json
{
  "output": [
    {
      "searchName": "",
      "queryName": "",
      "keys": [
        ""
      ],
      "values": [
        ""
      ],
      "resultsType": "",
      "virtualFolderPath": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Query::_2007_06::SavedQuery::SaveSearchCriteriaInfo[] | A SavedSearchCriteriaInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 3.3.4 saveSearchCriteria（2007-06）

**接口路径：** `Query-2007-06-SavedQuery/saveSearchCriteria`

**API 版本：** `2007-06`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 保存一组搜索条件到「我的已保存搜索」集合；部分错误通过搜索名称引用。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_06.SavedQuery.saveSearchCriteria`

**请求（input）：**

```json
{
  "searchCriteria": [
    {
      "searchName": "",
      "queryName": "",
      "keys": [
        ""
      ],
      "values": [
        ""
      ],
      "resultsType": "",
      "virtualFolderPath": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchCriteria` | Teamcenter::Soa::Query::_2007_06::SavedQuery::SaveSearchCriteriaInfo[] | 搜索条件键值对，依提供者不同而不同。 |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.4 API 版本 2007-09

**Service：** SavedQuery  **操作数：** 1

#### 3.4.1 executeSavedQueries（2007-09）

**接口路径：** `Query-2007-09-SavedQuery/executeSavedQueries`

**API 版本：** `2007-09`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 批量执行已保存查询（类型：QRY_RUN_BY_TC、QRY_RUN_BY_KEYWORD_SEARCH）；支持平面模式与层级模式两种结果返回方式。

**Soa Inclusion：** `Teamcenter.Soa.Query._2007_09.SavedQuery.executeSavedQueries`

**请求（input）：**

```json
{
  "input": [
    {
      "query": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "entries": [
        ""
      ],
      "values": [
        ""
      ],
      "limitList": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "maxNumToReturn": "",
      "resultsType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryInput[] | A set of QueryInput data structures. |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

### 3.5 API 版本 2008-06

**Service：** SavedQuery  **操作数：** 1

#### 3.5.1 executeSavedQueries（2008-06）

**接口路径：** `Query-2008-06-SavedQuery/executeSavedQueries`

**API 版本：** `2008-06`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 批量执行已保存查询（类型：本地查询、用户查询 QRY_RUN_BY_USER_QUERY、关键字搜索等）；支持平面/层级结果模式。

**Soa Inclusion：** `Teamcenter.Soa.Query._2008_06.SavedQuery.executeSavedQueries`

**请求（input）：**

```json
{
  "input": [
    {
      "query": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "entries": [
        ""
      ],
      "values": [
        ""
      ],
      "limitList": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "maxNumToReturn": "",
      "resultsType": "",
      "requestId": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `input` | Teamcenter::Soa::Query::_2008_06::SavedQuery::QueryInput[] | A set of QueryInput data structures. |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

### 3.6 API 版本 2010-04

**Service：** SavedQuery  **操作数：** 1

#### 3.6.1 findSavedQueries（2010-04）

**接口路径：** `Query-2010-04-SavedQuery/findSavedQueries`

**API 版本：** `2010-04`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 按名称、描述等条件查找已保存查询，支持名称/描述单独或组合匹配。

**Soa Inclusion：** `Teamcenter.Soa.Query._2010_04.SavedQuery.findSavedQueries`

**请求（input）：**

```json
{
  "inputCriteria": [
    {
      "queryNames": [
        ""
      ],
      "queryDescs": [
        ""
      ],
      "queryType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputCriteria` | Teamcenter::Soa::Query::_2010_04::SavedQuery::FindSavedQueriesCriteriaInput[] | Structure that contains input criteria required to find 已保存查询. |

**响应（output）：**

```json
{
  "savedQueries": [
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
| `savedQueries` | Teamcenter::ImanQuery[] | A 已保存查询 objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

### 3.7 API 版本 2010-09

**Service：** SavedQuery  **操作数：** 1

#### 3.7.1 executeBusinessObjectQueries（2010-09）

**接口路径：** `Query-2010-09-SavedQuery/executeBusinessObjectQueries`

**API 版本：** `2010-09`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 执行业务对象简单搜索（Simple Search）并返回结果集及 ServiceData；部分错误通过索引引用。

**Soa Inclusion：** `Teamcenter.Soa.Query._2010_09.SavedQuery.executeBusinessObjectQueries`

**请求（input）：**

```json
{
  "inputs": [
    {
      "typeName": "",
      "clauses": [
        {
          "propName": "",
          "propValue": "",
          "mathOperator": "",
          "logicOperator": ""
        }
      ],
      "maxNumToReturn": "",
      "requestId": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Query::_2010_09::SavedQuery::BusinessObjectQueryInput[] | 业务对象 query inputs |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

### 3.8 API 版本 2012-10

**Service：** Finder  **操作数：** 1

#### 3.8.1 performSearch（2012-10）

**接口路径：** `Query-2012-10-Finder/performSearch`

**API 版本：** `2012-10`  
**Service：** `Finder`  
**Library：** `Query`

**说明：** 将搜索请求路由到指定 providerName 的搜索提供者（2012-10 版契约）。

**Soa Inclusion：** `Teamcenter.Soa.Query._2012_10.Finder.performSearch`

**请求（input）：**

```json
{
  "searchInput": {
    "providerName": "Awp0SavedQuerySearchProvider",
    "searchCriteria": {},
    "startIndex": "",
    "maxToReturn": "",
    "maxToLoad": "",
    "searchFilterMap": {},
    "searchSortCriteria": [
      {
        "fieldName": "",
        "sortDirection": "ASC"
      }
    ],
    "searchFilterFieldSortType": "Alphabetical",
    "attributesToInflate": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchInput` | Teamcenter::Soa::Query::_2012_10::Finder::SearchInput | 搜索输入参数，含 providerName、searchCriteria、分页与排序等。 |

**响应（output）：**

```json
{
  "searchResults": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "totalFound": "",
  "totalLoaded": "",
  "searchFilterMap": {},
  "searchFilterCategories": [
    {
      "internalName": "",
      "displayName": "",
      "defaultFilterValueDisplayCount": ""
    }
  ],
  "defaultFilterFieldDisplayCount": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchResults` | Teamcenter::BusinessObject[] | 执行搜索后返回的业务对象列表。 |
| `totalFound` | int | 搜索命中的业务对象总数。 |
| `totalLoaded` | int | 本次实际加载的业务对象数量。 |
| `searchFilterMap` | Teamcenter::Soa::Query::_2012_10::Finder::SearchFilterMap | 按搜索过滤器字段分组的过滤器映射（字符串 → SearchFilter 列表）。 |
| `searchFilterCategories` | Teamcenter::Soa::Query::_2012_10::Finder::SearchFilterField[] | 按过滤器优先级排序的搜索过滤器分类列表。 |
| `defaultFilterFieldDisplayCount` | int | 默认显示的搜索过滤器分类数量。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

### 3.9 API 版本 2013-05

**Service：** SavedQuery  **操作数：** 1

#### 3.9.1 createSavedQueries（2013-05）

**接口路径：** `Query-2013-05-SavedQuery/createSavedQueries`

**API 版本：** `2013-05`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 根据输入属性结构批量创建已保存查询；新对象加入 ServiceData 的 Created 列表，失败信息通过 clientId 关联。

**Soa Inclusion：** `Teamcenter.Soa.Query._2013_05.SavedQuery.createSavedQueries`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "queryName": "",
      "queryDesc": "",
      "queryClass": "",
      "queryClauses": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Query::_2013_05::SavedQuery::SavedQueryProperties[] | A 已保存查询 is created 各 SavedQueryProperties in list. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.10 API 版本 2014-11

**Service：** Finder  **操作数：** 2

#### 3.10.1 groupObjectsByProperties（2014-11）

**接口路径：** `Query-2014-11-Finder/groupObjectsByProperties`

**API 版本：** `2014-11`  
**Service：** `Finder`  
**Library：** `Query`

**说明：** 按属性将业务对象分类到分组：输入 ObjectPropertyGroupInput，指定内部属性名、分组值及待分类对象列表。

**Soa Inclusion：** `Teamcenter.Soa.Query._2014_11.Finder.groupObjectsByProperties`

**请求（input）：**

```json
{
  "objectPropertyGroupInputList": [
    {
      "internalPropertyName": "",
      "propertyValues": [
        {
          "propertyGroupID": "",
          "startValue": "",
          "endValue": ""
        }
      ],
      "objectList": [
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
| `objectPropertyGroupInputList` | Teamcenter::Soa::Query::_2014_11::Finder::ObjectPropertyGroupInput[] | containing ObjectPropertyGroupInput objects that represents property name and property value information to group a input 业务对象 |

**响应（output）：**

```json
{
  "groupedObjectsList": [
    {
      "internalPropertyName": "",
      "groupedObjectsMap": {},
      "unmatchedObjectList": [
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
| `groupedObjectsList` | Teamcenter::Soa::Query::_2014_11::Finder::ObjectsGroupedByProperty[] | ObjectPropertyGrouping objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

#### 3.10.2 performSearch（2014-11）

**接口路径：** `Query-2014-11-Finder/performSearch`

**API 版本：** `2014-11`  
**Service：** `Finder`  
**Library：** `Query`

**说明：** 将搜索请求路由到指定 providerName 的搜索提供者（2014-11 版契约，支持自定义提供者扩展）。

**Soa Inclusion：** `Teamcenter.Soa.Query._2014_11.Finder.performSearch`

**请求（input）：**

```json
{
  "searchInput": {
    "providerName": "Awp0SavedQuerySearchProvider",
    "searchCriteria": {},
    "startIndex": "",
    "maxToReturn": "",
    "maxToLoad": "",
    "searchFilterMap": {},
    "searchSortCriteria": [
      {
        "fieldName": "",
        "sortDirection": "ASC"
      }
    ],
    "searchFilterFieldSortType": "",
    "attributesToInflate": [
      ""
    ],
    "internalPropertyName": ""
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `searchInput` | Teamcenter::Soa::Query::_2014_11::Finder::SearchInput2 | 搜索输入参数，含 providerName、searchCriteria、分页与排序等。 |

**响应（output）：**

```json
{
  "searchResults": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "totalFound": "",
  "totalLoaded": "",
  "searchFilterMap": {},
  "searchFilterCategories": [
    {
      "internalName": "",
      "displayName": "",
      "defaultFilterValueDisplayCount": ""
    }
  ],
  "defaultFilterFieldDisplayCount": "",
  "serviceData": "IServiceData",
  "objectsGroupedByProperty": {
    "internalPropertyName": "",
    "groupedObjectsMap": {},
    "unmatchedObjectList": [
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
| `searchResults` | Teamcenter::BusinessObject[] | 执行搜索后返回的业务对象列表。 |
| `totalFound` | int | 搜索命中的业务对象总数。 |
| `totalLoaded` | int | 本次实际加载的业务对象数量。 |
| `searchFilterMap` | Teamcenter::Soa::Query::_2014_11::Finder::SearchFilterMap2 | 按搜索过滤器字段分组的过滤器映射（字符串 → SearchFilter 列表）。 |
| `searchFilterCategories` | Teamcenter::Soa::Query::_2012_10::Finder::SearchFilterField[] | 按过滤器优先级排序的搜索过滤器分类列表。 |
| `defaultFilterFieldDisplayCount` | int | 默认显示的搜索过滤器分类数量。 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |
| `objectsGroupedByProperty` | Teamcenter::Soa::Query::_2014_11::Finder::ObjectsGroupedByProperty | structure containing an internal property name and a map of objects to property group id. It also contains a unmatched objects which don't match any group. |

---

### 3.11 API 版本 2018-11

**Service：** SavedQuery  **操作数：** 1

#### 3.11.1 executeBOQueriesWithContext（2018-11）

**接口路径：** `Query-2018-11-SavedQuery/executeBOQueriesWithContext`

**API 版本：** `2018-11`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 在上下文条件下执行业务对象简单搜索，支持 Logical Object 等实例查询，可指定类型、子句与最大返回数。

**Soa Inclusion：** `Teamcenter.Soa.Query._2018_11.SavedQuery.executeBOQueriesWithContext`

**请求（input）：**

```json
{
  "inputs": [
    {
      "boTypeName": "",
      "clauses": [
        {
          "propName": "",
          "propValue": "",
          "mathOperator": "",
          "logicOperator": ""
        }
      ],
      "maxNumToReturn": "",
      "requestId": "",
      "clientId": "",
      "configurationContextMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Query::_2018_11::SavedQuery::BusinessObjectQueryInput2[] | Execute 业务对象 searches (简单搜索) and return 搜索结果. A map of property name and ConfigurationContext pairs has been added to BusinessObjectQueryInput2 structure to support configuration context on Included 逻辑对象（Logical Object） … |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

### 3.12 API 版本 2019-06

**Service：** SavedQuery  **操作数：** 1

#### 3.12.1 executeBOQueriesWithSort（2019-06）

**接口路径：** `Query-2019-06-SavedQuery/executeBOQueriesWithSort`

**API 版本：** `2019-06`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 执行业务对象查询并支持排序选项，返回查询结果集；失败时返回部分错误（如无效属性等）。

**Soa Inclusion：** `Teamcenter.Soa.Query._2019_06.SavedQuery.executeBOQueriesWithSort`

**请求（input）：**

```json
{
  "inputs": [
    {
      "boTypeName": "",
      "clauses": [
        {
          "propName": "",
          "propValue": "",
          "mathOperator": "",
          "logicOperator": ""
        }
      ],
      "sortOptions": [
        {
          "sortAttribute": "",
          "sortOrder": "AscendingOrder"
        }
      ],
      "maxNumToReturn": "",
      "requestId": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Query::_2019_06::SavedQuery::BusinessObjectQueryInput3[] | 业务对象 query inputs. |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

### 3.13 API 版本 2020-04

**Service：** SavedQuery  **操作数：** 1

#### 3.13.1 executeBOQueriesWithSortAndContext（2020-04）

**接口路径：** `Query-2020-04-SavedQuery/executeBOQueriesWithSortAndContext`

**API 版本：** `2020-04`  
**Service：** `SavedQuery`  
**Library：** `Query`

**说明：** 在上下文条件下执行业务对象简单搜索，支持排序、类型、子句与最大返回数等配置。

**Soa Inclusion：** `Teamcenter.Soa.Query._2020_04.SavedQuery.executeBOQueriesWithSortAndContext`

**请求（input）：**

```json
{
  "inputs": [
    {
      "boTypeName": "",
      "clauses": [
        {
          "propName": "",
          "propValue": "",
          "mathOperator": "",
          "logicOperator": ""
        }
      ],
      "sortOptions": [
        {
          "sortAttribute": "",
          "sortOrder": "AscendingOrder"
        }
      ],
      "maxNumToReturn": "",
      "requestId": "",
      "clientId": "",
      "configurationContextMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputs` | Teamcenter::Soa::Query::_2020_04::SavedQuery::BusinessObjectQueryInput4[] | 业务对象 query inputs. |

**响应（output）：**

```json
{
  "arrayOfResults": [
    {
      "objectsRelMap": [],
      "objectUIDS": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arrayOfResults` | Teamcenter::Soa::Query::_2007_09::SavedQuery::QueryResults[] | A set of QueryResults data structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | 服务数据对象，含部分错误等信息。 |

---

---

## 4. 附录

### 操作一览（合并索引）

| API 版本 | Service | 操作 | Url | Soa Inclusion |
|----------|---------|------|-----|---------------|
| 2006-03 | SavedQuery | `describeSavedQueries` | `Query-2006-03-SavedQuery/describeSavedQueries` | `Teamcenter.Soa.Query._2006_03.SavedQuery.describeSavedQueries` |
| 2006-03 | SavedQuery | `executeSavedQuery` | `Query-2006-03-SavedQuery/executeSavedQuery` | `Teamcenter.Soa.Query._2006_03.SavedQuery.executeSavedQuery` |
| 2006-03 | SavedQuery | `getSavedQueries` | `Query-2006-03-SavedQuery/getSavedQueries` | `Teamcenter.Soa.Query._2006_03.SavedQuery.getSavedQueries` |
| 2007-01 | SavedQuery | `deleteQueryCriterias` | `Query-2007-01-SavedQuery/deleteQueryCriterias` | `Teamcenter.Soa.Query._2007_01.SavedQuery.deleteQueryCriterias` |
| 2007-01 | SavedQuery | `reorderSavedQueryCriterias` | `Query-2007-01-SavedQuery/reorderSavedQueryCriterias` | `Teamcenter.Soa.Query._2007_01.SavedQuery.reorderSavedQueryCriterias` |
| 2007-01 | SavedQuery | `retrieveQueryCriterias` | `Query-2007-01-SavedQuery/retrieveQueryCriterias` | `Teamcenter.Soa.Query._2007_01.SavedQuery.retrieveQueryCriterias` |
| 2007-01 | SavedQuery | `saveQueryCriterias` | `Query-2007-01-SavedQuery/saveQueryCriterias` | `Teamcenter.Soa.Query._2007_01.SavedQuery.saveQueryCriterias` |
| 2007-06 | Finder | `findWorkspaceObjects` | `Query-2007-06-Finder/findWorkspaceObjects` | `Teamcenter.Soa.Query._2007_06.Finder.findWorkspaceObjects` |
| 2007-06 | SavedQuery | `executeSavedQueries` | `Query-2007-06-SavedQuery/executeSavedQueries` | `Teamcenter.Soa.Query._2007_06.SavedQuery.executeSavedQueries` |
| 2007-06 | SavedQuery | `retrieveSearchCriteria` | `Query-2007-06-SavedQuery/retrieveSearchCriteria` | `Teamcenter.Soa.Query._2007_06.SavedQuery.retrieveSearchCriteria` |
| 2007-06 | SavedQuery | `saveSearchCriteria` | `Query-2007-06-SavedQuery/saveSearchCriteria` | `Teamcenter.Soa.Query._2007_06.SavedQuery.saveSearchCriteria` |
| 2007-09 | SavedQuery | `executeSavedQueries` | `Query-2007-09-SavedQuery/executeSavedQueries` | `Teamcenter.Soa.Query._2007_09.SavedQuery.executeSavedQueries` |
| 2008-06 | SavedQuery | `executeSavedQueries` | `Query-2008-06-SavedQuery/executeSavedQueries` | `Teamcenter.Soa.Query._2008_06.SavedQuery.executeSavedQueries` |
| 2010-04 | SavedQuery | `findSavedQueries` | `Query-2010-04-SavedQuery/findSavedQueries` | `Teamcenter.Soa.Query._2010_04.SavedQuery.findSavedQueries` |
| 2010-09 | SavedQuery | `executeBusinessObjectQueries` | `Query-2010-09-SavedQuery/executeBusinessObjectQueries` | `Teamcenter.Soa.Query._2010_09.SavedQuery.executeBusinessObjectQueries` |
| 2012-10 | Finder | `performSearch` | `Query-2012-10-Finder/performSearch` | `Teamcenter.Soa.Query._2012_10.Finder.performSearch` |
| 2013-05 | SavedQuery | `createSavedQueries` | `Query-2013-05-SavedQuery/createSavedQueries` | `Teamcenter.Soa.Query._2013_05.SavedQuery.createSavedQueries` |
| 2014-11 | Finder | `groupObjectsByProperties` | `Query-2014-11-Finder/groupObjectsByProperties` | `Teamcenter.Soa.Query._2014_11.Finder.groupObjectsByProperties` |
| 2014-11 | Finder | `performSearch` | `Query-2014-11-Finder/performSearch` | `Teamcenter.Soa.Query._2014_11.Finder.performSearch` |
| 2018-11 | SavedQuery | `executeBOQueriesWithContext` | `Query-2018-11-SavedQuery/executeBOQueriesWithContext` | `Teamcenter.Soa.Query._2018_11.SavedQuery.executeBOQueriesWithContext` |
| 2019-06 | SavedQuery | `executeBOQueriesWithSort` | `Query-2019-06-SavedQuery/executeBOQueriesWithSort` | `Teamcenter.Soa.Query._2019_06.SavedQuery.executeBOQueriesWithSort` |
| 2020-04 | SavedQuery | `executeBOQueriesWithSortAndContext` | `Query-2020-04-SavedQuery/executeBOQueriesWithSortAndContext` | `Teamcenter.Soa.Query._2020_04.SavedQuery.executeBOQueriesWithSortAndContext` |

### 典型流程

**高级搜索（Saved Query）：**
1. `getSavedQueries` — 获取已保存查询列表
2. `performSearch`（`providerName`: `Awp0SavedQuerySearchProvider`）— 执行搜索

**收件箱任务：**
1. `performSearch`（`providerName`: `Awp0InboxProvider`）— 获取当前用户任务

**简单搜索（业务对象）：**
1. `executeBusinessObjectQueries` 或 `executeBOQueriesWithSortAndContext`

### 重新生成

```bash
node generate-query-doc.js
```
