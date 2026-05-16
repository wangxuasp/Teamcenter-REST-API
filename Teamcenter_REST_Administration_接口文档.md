# Teamcenter SOA API — Administration 接口文档（TC 2512）

> 本文档汇总 **Administration** Library 下**全部 API 版本（年-月）**的 SOA 操作，按版本与 Service 双向整理，功能描述及字段说明均为**简体中文**。
> 数据来源：TC 2512 SOA Api Browser（`structure.js`）。
>
> - **API 版本数：** 18 个（`2006-03` ～ `2020-12`）
> - **操作总数：** 49 个
> - **Service 数：** 8 个
> - **Url 格式：** `Administration-{Year}-{Service}/{operation}`

---

## 目录

1. [API 版本总览](#1-api-版本总览)
2. [按 Service 合并（跨版本）](#2-按-service-合并跨版本)
3. [按 API 版本（年-月）归档](#3-按-api-版本年-月归档)
4. [附录](#4-附录)

---

## 1. API 版本总览

Administration 在 TC 2512 中共有 **18** 个年-月版本，部分 Service（如 IRM、UserManagement、PreferenceManagement）跨多个版本持续演进。

| API 版本 | Service | 操作 | 功能摘要 |
|----------|---------|------|---------|
| **2006-03** | IRM | `checkAccessorsPrivileges` | 获取指定 GroupMember 对一组业务对象的访问权限裁决。系统会根据用户、角色、用户组的组合找到对应访问者（acc… |
| **2006-03** | IRM | `getEffectiveACLInfo` | 获取一组业务对象的有效访问控制列表（ACL）信息，展示当前用户对这些对象实际生效的访问控制条目（ACE）。… |
| **2006-03** | IRM | `getExtraProtectionInfo` | 获取指定用户对一组业务对象的附加保护信息，包括哪条命名 ACL、哪个 Accessor 及哪条 AM 规则路径决定了最终… |
| **2006-03** | IRM | `removeAccessor` | 从给定对象中删除指定访问者（accessor）。对象可以是命名 ACL 或 POM 应用对象：若为命名 ACL，则从中删… |
| **2006-03** | IRM | `setPrivileges` | 在指定对象上授予或拒绝一组访问权限给指定访问者。对象可为命名 ACL 或 POM 应用对象；若为 POM 应用对象且对象… |
| **2007-01** | UserManagement | `createDisciplines` | 批量创建 Discipline（学科/专业）对象。若指定了父 Group，则将新建的 Discipline 添加到该组中… |
| **2007-06** | Authorization | `checkAuthorization` | 检查指定用户与用户组组合对一组应用程序或工具的访问授权。规则域（domain）可为 `utility`（工具）或 `ap… |
| **2007-06** | PreferenceManagement | `setPreferences` | 设置会话或非会话偏好设置的值。会话偏好为当前登录用户视角的偏好；非会话偏好（如 Site/Group/Role 级别）需… |
| **2008-03** | IRM | `activateUsers` | 根据可用的 Author 或 Consumer 许可证数量激活指定用户。若许可证不足，返回对应错误码。注意：仅激活用户本… |
| **2008-03** | IRM | `deactivateUsers` | 停用指定用户，并可选地将其所拥有对象的所有权转移给新用户。停用成功的用户在 ServiceData 的 updated … |
| **2008-06** | PreferenceManagement | `lockSitePreferences` | 锁定数据库中存储的 Site 偏好设置，仅供系统管理员使用。锁定非强制但可确保排他性写入。… |
| **2008-06** | PreferenceManagement | `unlockSitePreferences` | 释放 `lockSitePreferences` 设置的 Site 偏好锁定。仅加锁用户可执行解锁。注意：TC 11.6… |
| **2008-12** | Authorization | `checkAuthorizationAccess` | 检查指定用户、用户组和角色三元组合对一组应用程序或工具的访问授权（比 `checkAuthorization` 多了角色… |
| **2010-04** | DisciplineManagement | `getDiscipline` | 根据名称获取 Discipline（专业/学科）业务对象。若找不到对应名称的 Discipline，返回 null。… |
| **2010-04** | IRM | `getAccessorTypes` | 获取 Teamcenter 中所有访问者类型（Accessor Type）的名称列表，如 World、User、Grou… |
| **2010-04** | IRM | `getEffectiveACLInfo2` | `getEffectiveACLInfo` 的增强版，支持批量业务对象输入，并可返回更丰富的有效 ACL 信息（含 AC… |
| **2010-04** | IRM | `getExtraProtectionInfo2` | `getExtraProtectionInfo` 的增强版，返回更详细的附加保护信息，适用于复杂权限路径的溯源分析。… |
| **2010-04** | IRM | `getPrivilegeNames` | 获取 Teamcenter 中全部访问权限的内部名称及对应本地化显示名称，内部名称用于程序调用，显示名称用于界面展示。… |
| **2011-05** | PreferenceManagement | `refreshPreferences` | 刷新服务器缓存中的偏好值，使其与最新值同步。在多会话并发修改同一用户偏好，或管理员修改 Site/Role/Group … |
| **2012-09** | PreferenceManagement | `deletePreferenceDefinitions` | 删除指定偏好的定义及其所有值实例。参数 `deleteAllCustomDefinitions` 已废弃（偏好不再区分 … |
| **2012-09** | PreferenceManagement | `deletePreferencesAtLocations` | 仅删除指定位置（Site/Group/Role/User）的偏好实例，不影响其他位置的值。输入为 `Preference… |
| **2012-09** | PreferenceManagement | `getPreferences` | 按当前登录用户及应用上下文检索指定名称的偏好值；若当前上下文无值则回退到默认上下文。名称列表为空或首元素为 `*` 时返… |
| **2012-09** | PreferenceManagement | `getPreferencesAtLocations` | 按指定名称和位置（Site/Group/Role/User）精确检索偏好值，不受应用上下文影响，适合管理场景。… |
| **2012-09** | PreferenceManagement | `importPreferencesAtLocationDryRun` | 模拟（试运行）将偏好文件导入指定位置，不实际写入，仅返回导入结果预览，供确认后再执行真正导入。… |
| **2012-09** | PreferenceManagement | `importPreferencesAtLocations` | 将偏好文件导入指定位置（Site/Group/Role/User）。Site 级别仅系统管理员可操作；Group/Rol… |
| **2012-09** | PreferenceManagement | `removeStalePreferenceInstancesAtLocations` | 删除指定位置的过期偏好实例（与 preference manager 工具的清理模式等效）。实际已被工具替代，此 SOA… |
| **2012-09** | PreferenceManagement | `setPreferences2` | 允许当前登录用户为自身设置偏好值。仅当偏好已在系统中定义且保护范围允许该用户修改时才能成功，否则返回对应错误。… |
| **2012-09** | PreferenceManagement | `setPreferencesAtLocations` | 按指定位置（Site/Group/Role/User）设置偏好值。Site 级别需管理员权限；Group/Role 级别… |
| **2012-09** | PreferenceManagement | `setPreferencesDefinition` | 允许系统管理员创建新偏好的定义或修改已有定义。若偏好不存在则创建；若已存在则修改定义和值（若提供了值）。… |
| **2012-09** | UserManagement | `getUserGroupMembers` | 批量获取指定用户的所有 GroupMember 信息，包括关联的 Group、Role、User 对象，以及状态、组管理… |
| **2012-09** | UserManagement | `setGroupMemberProperties` | 批量更新一个或多个 GroupMember 的属性，可更新：`membership_data_source`、`ga`（… |
| **2012-10** | IRM | `getAMImpactedObjects` | 列出由于访问管理器（AM）规则树变更而导致读取权限受影响的业务对象。仅统计自上次调用本接口以来发生的变更。通常由后台服务… |
| **2012-10** | IRM | `getSessionValues` | 以键值对 Map 的形式获取当前会话的所有信息，包括用户（user）、角色（roles）、组（groups）、项目团队（… |
| **2014-10** | UserManagement | `makeUser` | 在 TC 服务器上以当前会话用户的身份执行 `make_user` 实用程序。支持命令行参数和批处理输入文件（通过 FM… |
| **2015-03** | UserManagement | `setUserProfileProperties` | 设置指定用户的 `Fnd0CustomUserProfile` 对象上的属性。若该 Profile 不存在则自动创建，并… |
| **2015-07** | UserManagement | `createOrUpdateUser` | 批量创建或更新 User 对象。若用户不存在则创建，否则更新。需要系统管理员权限。若输入中的 Person 对象不存在，… |
| **2016-03** | UserManagement | `deleteUser` | 从 Teamcenter 中删除 User 对象。可选择同时删除其拥有的对象，或将所有权转移给指定的新用户。需要系统管理… |
| **2016-10** | UserManagement | `getCurrentCountryPageInfo` | 获取当前国家选择页面的配置，包括可选国家列表、默认显示国家及可自定义的保密声明文字。供 RAC 和 AW 客户端渲染国家… |
| **2016-10** | UserManagement | `saveAndValidateCurrentCountry` | 保存当前会话用户选择的国家，并校验该用户是否违反全球许可协议。即使校验失败，国家仍会被保存。此操作不可传入 null 值… |
| **2017-05** | GroupManagement | `addChildGroups` | 向指定 Group 对象添加子组。如果子组不存在则先创建再添加。新建的 Group 对象在 ServiceData 的 … |
| **2017-05** | RoleManagement | `addRolesToGroup` | 向指定 Group 对象添加角色（Role）。若角色不存在则先创建。新建角色在 ServiceData 的 create… |
| **2017-05** | RoleManagement | `removeRolesFromGroup` | 从指定 Group 对象中移除指定角色（Role）。被修改的 Group 对象在 ServiceData 的 modif… |
| **2017-05** | UserManagement | `addUsersAsGroupMembers` | 将用户（新建或已有）作为 GroupMember 添加到指定 Group 和 Role 下。若用户不存在则先创建。需要系… |
| **2017-05** | UserManagement | `removeGroupMembers` | 从指定 Group 和 Role 下移除 GroupMember。需要系统管理员或组管理员权限。输入不可包含 null … |
| **2018-11** | IRM | `getSessionInfoFromTicket` | 凭借 `getSessionInfoTicket` 返回的加密 Ticket 字符串，还原并返回会话信息（用户、组、角色… |
| **2018-11** | IRM | `getSessionInfoTicket` | 将当前会话的用户、组、会话信息、站点标识和过期时间打包成加密字符串（Ticket）返回，供无用户概念的系统（如 VDS）… |
| **2018-11** | OrganizationManagement | `getUserConsentStatement` | 返回当前登录用户所在区域（locale）的用户同意声明（GDPR）。若该区域无对应声明，则返回主区域（master lo… |
| **2018-11** | OrganizationManagement | `recordUserConsent` | 记录用户对通用数据保护条例（GDPR）的同意操作。若底层函数调用出现问题，可能返回部分错误（partial errors… |
| **2020-12** | PreferenceManagement | `refreshPreferences2` | `refreshPreferences` 的增强版：先刷新指定偏好的服务器缓存，再按当前用户和应用上下文返回最新值。支持… |

### 版本—Service 统计

| API 版本 | Service | 操作数 |
|----------|---------|--------|
| 2006-03 | IRM | 5 |
| 2007-01 | UserManagement | 1 |
| 2007-06 | Authorization、PreferenceManagement | 2 |
| 2008-03 | IRM | 2 |
| 2008-06 | PreferenceManagement | 2 |
| 2008-12 | Authorization | 1 |
| 2010-04 | DisciplineManagement、IRM | 5 |
| 2011-05 | PreferenceManagement | 1 |
| 2012-09 | PreferenceManagement、UserManagement | 12 |
| 2012-10 | IRM | 2 |
| 2014-10 | UserManagement | 1 |
| 2015-03 | UserManagement | 1 |
| 2015-07 | UserManagement | 1 |
| 2016-03 | UserManagement | 1 |
| 2016-10 | UserManagement | 2 |
| 2017-05 | GroupManagement、RoleManagement、UserManagement | 5 |
| 2018-11 | IRM、OrganizationManagement | 4 |
| 2020-12 | PreferenceManagement | 1 |

---

## 2. 按 Service 合并（跨版本）

同一 Service 下按 API 版本（年-月）升序列出全部操作；调用时需使用对应版本的 Url。

### 2.1 访问授权（Authorization）

**涵盖 API 版本：** `2007-06`、`2008-12`  
**操作数：** 2

#### 版本 2007-06

##### 2.1.1.1 checkAuthorization

**接口路径：** `Administration-2007-06-Authorization/checkAuthorization`

**API 版本：** `2007-06`  
**Service：** `Authorization`  
**Library：** `Administration`

**功能说明：** 检查指定用户与用户组组合对一组应用程序或工具的访问授权。规则域（domain）可为 `utility`（工具）或 `application`（应用）。返回每个输入名称对应的授权结果。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2007_06.Authorization.checkAuthorization`

**请求（input）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "group": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "inputNames": [
    {
      "name": "String",
      "ruleDomain": "String"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `user` | Teamcenter::User | 用户业务对象 |
| `group` | Teamcenter::Group | 用户组业务对象 |
| `inputNames` | Teamcenter::Soa::Administration::_2007_06::Authorization::NameInfo[] | 需要检查授权的应用程序或工具名称列表 |

**响应（output）：**

```json
{
  "output": [
    {
      "name": "String",
      "ruleDomain": "String",
      "verdict": false
    }
  ],
  "partialErrors": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Administration::_2007_06::Authorization::NameAuthorizationResponse[] | A list of NameAuthorizationResponse objects one for each of the given application or utility. |
| `partialErrors` | Teamcenter::Soa::Server::ServiceData | 操作过程中的部分错误信息 |

---

#### 版本 2008-12

##### 2.1.2.1 checkAuthorizationAccess

**接口路径：** `Administration-2008-12-Authorization/checkAuthorizationAccess`

**API 版本：** `2008-12`  
**Service：** `Authorization`  
**Library：** `Administration`

**功能说明：** 检查指定用户、用户组和角色三元组合对一组应用程序或工具的访问授权（比 `checkAuthorization` 多了角色维度）。返回每个输入名称的授权结果。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2008_12.Authorization.checkAuthorizationAccess`

**请求（input）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "group": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "role": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "inputNames": [
    {
      "name": "String",
      "ruleDomain": "String"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `user` | Teamcenter::User | 用户业务对象 |
| `group` | Teamcenter::Group | 用户组业务对象 |
| `role` | Teamcenter::Role | 角色业务对象 |
| `inputNames` | Teamcenter::Soa::Administration::_2007_06::Authorization::NameInfo[] | 需要检查授权的应用程序或工具名称列表 |

**响应（output）：**

```json
{
  "output": [
    {
      "name": "String",
      "ruleDomain": "String",
      "verdict": false
    }
  ],
  "partialErrors": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Administration::_2007_06::Authorization::NameAuthorizationResponse[] | A list of NameAuthorizationResponse objects one for each of the given application or utility. |
| `partialErrors` | Teamcenter::Soa::Server::ServiceData | 操作过程中的部分错误信息 |

---

### 2.2 学科管理（DisciplineManagement）

**涵盖 API 版本：** `2010-04`  
**操作数：** 1

#### 版本 2010-04

##### 2.2.1.1 getDiscipline

**接口路径：** `Administration-2010-04-DisciplineManagement/getDiscipline`

**API 版本：** `2010-04`  
**Service：** `DisciplineManagement`  
**Library：** `Administration`

**功能说明：** 根据名称获取 Discipline（专业/学科）业务对象。若找不到对应名称的 Discipline，返回 null。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2010_04.DisciplineManagement.getDiscipline`

**请求（input）：**

```json
{
  "disciplineName": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `disciplineName` | std::string | Discipline 对象名称 |

**响应（output）：**

```json
{
  "discipline": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `discipline` | Teamcenter::Discipline | 返回的 Discipline 业务对象 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

### 2.3 组管理（GroupManagement）

**涵盖 API 版本：** `2017-05`  
**操作数：** 1

#### 版本 2017-05

##### 2.3.1.1 addChildGroups

**接口路径：** `Administration-2017-05-GroupManagement/addChildGroups`

**API 版本：** `2017-05`  
**Service：** `GroupManagement`  
**Library：** `Administration`

**功能说明：** 向指定 Group 对象添加子组。如果子组不存在则先创建再添加。新建的 Group 对象在 ServiceData 的 created 列表中返回，被修改的父组在 modified 列表中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2017_05.GroupManagement.addChildGroups`

**请求（input）：**

```json
{
  "childGroupsToGroupStructs": [
    {
      "clientId": "String",
      "groupsToAdd": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "groupsToCreateAndAdd": [
        {
          "name": "String",
          "description": "String",
          "privilege": false,
          "localVolume": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "security": "String",
          "volume": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "parentGroup": {
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
| `childGroupsToGroupStructs` | Teamcenter::Soa::Administration::_2017_05::GroupManagement::AddChildGroupsToGroupStructure[] | 父组与子组关系列表，子组可新建或已有 |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.4 信息权限管理（IRM）

**涵盖 API 版本：** `2006-03`、`2008-03`、`2010-04`、`2012-10`、`2018-11`  
**操作数：** 15

#### 版本 2006-03

##### 2.4.1.1 checkAccessorsPrivileges

**接口路径：** `Administration-2006-03-IRM/checkAccessorsPrivileges`

**API 版本：** `2006-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 获取指定 GroupMember 对一组业务对象的访问权限裁决。系统会根据用户、角色、用户组的组合找到对应访问者（accessor），再依据访问控制规则返回每个权限的授权结果。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2006_03.IRM.checkAccessorsPrivileges`

**请求（input）：**

```json
{
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "privilegeNames": [
    "String"
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `groupMember` | Teamcenter::BusinessObject | 要检查权限的 GroupMember 业务对象 |
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |
| `privilegeNames` | std::string[] | 需要检查的权限名称列表 |

**响应（output）：**

```json
{
  "privilegeReports": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "privilegeInfos": [
        {
          "privilegeName": "String",
          "verdict": false
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `privilegeReports` | Teamcenter::Soa::Administration::_2006_03::IRM::PrivilegeReport[] | A list of PrivilegeReport objects one for each of the given business object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 2.4.1.2 getEffectiveACLInfo

**接口路径：** `Administration-2006-03-IRM/getEffectiveACLInfo`

**API 版本：** `2006-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 获取一组业务对象的有效访问控制列表（ACL）信息，展示当前用户对这些对象实际生效的访问控制条目（ACE）。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2006_03.IRM.getEffectiveACLInfo`

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
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |

**响应（output）：**

```json
{
  "aclInfoList": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "aclInfos": [
        {
          "grantedNames": [
            "String"
          ],
          "revokedNames": [
            "String"
          ],
          "accessorType": "String",
          "accessorId": "String",
          "namedACL": "String"
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `aclInfoList` | Teamcenter::Soa::Administration::_2006_03::IRM::ACLInfos[] | List of derived Effective ACL reports for each of the given business objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 2.4.1.3 getExtraProtectionInfo

**接口路径：** `Administration-2006-03-IRM/getExtraProtectionInfo`

**API 版本：** `2006-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 获取指定用户对一组业务对象的附加保护信息，包括哪条命名 ACL、哪个 Accessor 及哪条 AM 规则路径决定了最终权限结论。用于排查权限问题。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2006_03.IRM.getExtraProtectionInfo`

**请求（input）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
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
| `user` | Teamcenter::User | 用户业务对象 |
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |

**响应（output）：**

```json
{
  "protectionReports": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "protections": [
        {
          "privilege": "String",
          "verdict": false,
          "rules": [
            "String"
          ],
          "ruleEvaluation": [
            "String"
          ],
          "acl": "String",
          "accessorType": "String",
          "accessorId": "String"
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `protectionReports` | Teamcenter::Soa::Administration::_2006_03::IRM::ProtectionReport[] | List of extra protection report objects one for each of the given business objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 2.4.1.4 removeAccessor

**接口路径：** `Administration-2006-03-IRM/removeAccessor`

**API 版本：** `2006-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 从给定对象中删除指定访问者（accessor）。对象可以是命名 ACL 或 POM 应用对象：若为命名 ACL，则从中删除对应 ACE；若为 POM 应用对象，则从对象级 ACL 中删除该 ACE。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2006_03.IRM.removeAccessor`

**请求（input）：**

```json
{
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "accessorType": "String",
  "accessorId": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |
| `accessorType` | std::string | 访问者类型（如 User、Group、Role、World） |
| `accessorId` | std::string | 访问者标识符 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.4.1.5 setPrivileges

**接口路径：** `Administration-2006-03-IRM/setPrivileges`

**API 版本：** `2006-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 在指定对象上授予或拒绝一组访问权限给指定访问者。对象可为命名 ACL 或 POM 应用对象；若为 POM 应用对象且对象级 ACL 不存在则自动创建。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2006_03.IRM.setPrivileges`

**请求（input）：**

```json
{
  "privilegeSettings": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "grant": [
        "String"
      ],
      "revoke": [
        "String"
      ],
      "unset": [
        "String"
      ]
    }
  ],
  "accessorType": "String",
  "accessorId": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `privilegeSettings` | Teamcenter::Soa::Administration::_2006_03::IRM::PrivilegeSettingInput[] | 权限设置信息列表（对象 + 权限名称 + 授予/拒绝） |
| `accessorType` | std::string | 访问者类型（如 User、Group、Role、World） |
| `accessorId` | std::string | 访问者标识符 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2008-03

##### 2.4.2.1 activateUsers

**接口路径：** `Administration-2008-03-IRM/activateUsers`

**API 版本：** `2008-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 根据可用的 Author 或 Consumer 许可证数量激活指定用户。若许可证不足，返回对应错误码。注意：仅激活用户本身，不激活其 GroupMember。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2008_03.IRM.activateUsers`

**请求（input）：**

```json
{
  "activateUser": [
    {
      "licenseLevel": 0,
      "targetUser": {
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
| `activateUser` | Teamcenter::Soa::Administration::_2008_03::IRM::ActivateUserInput[] | 需要激活的用户信息列表 |

**响应（output）：**

```json
{
  "licStatus": [
    {
      "numPurchasedLicenses": 0,
      "numUsedLicenses": 0
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `licStatus` | Teamcenter::Soa::Administration::_2008_03::IRM::LicenseStatus[] | List of LicenseStatus objects, one for each ActivateUserInput object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 2.4.2.2 deactivateUsers

**接口路径：** `Administration-2008-03-IRM/deactivateUsers`

**API 版本：** `2008-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 停用指定用户，并可选地将其所拥有对象的所有权转移给新用户。停用成功的用户在 ServiceData 的 updated 列表中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2008_03.IRM.deactivateUsers`

**请求（input）：**

```json
{
  "deactivateUser": [
    {
      "targetUser": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newUser": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newGroup": {
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
| `deactivateUser` | Teamcenter::Soa::Administration::_2008_03::IRM::DeactivateUserInput[] | 需要停用的用户信息列表，可包含所有权转移目标用户 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2010-04

##### 2.4.3.1 getAccessorTypes

**接口路径：** `Administration-2010-04-IRM/getAccessorTypes`

**API 版本：** `2010-04`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 获取 Teamcenter 中所有访问者类型（Accessor Type）的名称列表，如 World、User、Group、Role 等，用于在访问管理器（AM）中配置 ACL。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2010_04.IRM.getAccessorTypes`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "accessorTypeNameInfos": [
    {
      "internalName": "String",
      "displayName": "String"
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `accessorTypeNameInfos` | Teamcenter::Soa::Administration::_2010_04::IRM::DisplayNameInfo[] | List of DisplayNameInfo objects containing the internal name and corresponding display name for each of the Accessor Types in Teamcenter. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 2.4.3.2 getEffectiveACLInfo2

**接口路径：** `Administration-2010-04-IRM/getEffectiveACLInfo2`

**API 版本：** `2010-04`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** `getEffectiveACLInfo` 的增强版，支持批量业务对象输入，并可返回更丰富的有效 ACL 信息（含 ACE 详情）。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2010_04.IRM.getEffectiveACLInfo2`

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
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |

**响应（output）：**

```json
{
  "aclInfosList": [
    {
      "workSpaceObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "aclInfos": [
        {
          "grantedPrivsInfo": [
            {
              "internalName": "String",
              "displayName": "String"
            }
          ],
          "revokedPrivsInfo": [
            {
              "internalName": "String",
              "displayName": "String"
            }
          ],
          "accessorTypeNameInfo": {
            "internalName": "String",
            "displayName": "String"
          },
          "accessorIdInfo": {
            "internalName": "String",
            "displayName": "String"
          },
          "aclNameInfo": {
            "internalName": "String",
            "displayName": "String"
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
| `aclInfosList` | Teamcenter::Soa::Administration::_2010_04::IRM::ACLInfos[] | List of derived Effective ACL reports for each of the given business objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 2.4.3.3 getExtraProtectionInfo2

**接口路径：** `Administration-2010-04-IRM/getExtraProtectionInfo2`

**API 版本：** `2010-04`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** `getExtraProtectionInfo` 的增强版，返回更详细的附加保护信息，适用于复杂权限路径的溯源分析。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2010_04.IRM.getExtraProtectionInfo2`

**请求（input）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
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
| `user` | Teamcenter::User | 用户业务对象 |
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |

**响应（output）：**

```json
{
  "extraProtectionReports": [
    {
      "workSpaceObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "extraProtectionInfos": [
        {
          "privilegeNameInfo": {
            "internalName": "String",
            "displayName": "String"
          },
          "verdict": false,
          "rules": [
            "String"
          ],
          "ruleEvaluation": [
            "String"
          ],
          "aclNameInfo": {
            "internalName": "String",
            "displayName": "String"
          },
          "accessorTypeNameInfo": {
            "internalName": "String",
            "displayName": "String"
          },
          "accessorIdInfo": {
            "internalName": "String",
            "displayName": "String"
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
| `extraProtectionReports` | Teamcenter::Soa::Administration::_2010_04::IRM::ExtraProtectionInfoReport[] | List of extra protection report objects one for each of the given business objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 2.4.3.4 getPrivilegeNames

**接口路径：** `Administration-2010-04-IRM/getPrivilegeNames`

**API 版本：** `2010-04`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 获取 Teamcenter 中全部访问权限的内部名称及对应本地化显示名称，内部名称用于程序调用，显示名称用于界面展示。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2010_04.IRM.getPrivilegeNames`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "privNameInfos": [
    {
      "internalName": "String",
      "displayName": "String"
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `privNameInfos` | Teamcenter::Soa::Administration::_2010_04::IRM::DisplayNameInfo[] | A list of DisplayNameInfo objects that holds internal name and display names of each Teamcenter privilege objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

#### 版本 2012-10

##### 2.4.4.1 getAMImpactedObjects

**接口路径：** `Administration-2012-10-IRM/getAMImpactedObjects`

**API 版本：** `2012-10`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 列出由于访问管理器（AM）规则树变更而导致读取权限受影响的业务对象。仅统计自上次调用本接口以来发生的变更。通常由后台服务定期调用，供索引更新使用。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_10.IRM.getAMImpactedObjects`

**请求（input）：**

```json
{
  "filterByIndexedStatus": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `filterByIndexedStatus` | bool | 是否按已索引状态过滤返回对象 |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "isImpactGlobal": false,
  "impactedUids": [
    "String"
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |
| `isImpactGlobal` | bool | isImpactGlobal |
| `impactedUids` | std::string[] | impactedUids |

---

##### 2.4.4.2 getSessionValues

**接口路径：** `Administration-2012-10-IRM/getSessionValues`

**API 版本：** `2012-10`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 以键值对 Map 的形式获取当前会话的所有信息，包括用户（user）、角色（roles）、组（groups）、项目团队（project teams）和许可证（licenses）等会话属性。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_10.IRM.getSessionValues`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "sessionValues": {
    "SampleStringKey": "String"
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `sessionValues` | Teamcenter::Soa::Administration::_2012_10::IRM::SessionValuesMap | A map of key-value pairs that holds the session keys and the matching session values from Read Expression string. |

---

#### 版本 2018-11

##### 2.4.5.1 getSessionInfoFromTicket

**接口路径：** `Administration-2018-11-IRM/getSessionInfoFromTicket`

**API 版本：** `2018-11`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 凭借 `getSessionInfoTicket` 返回的加密 Ticket 字符串，还原并返回会话信息（用户、组、角色、项目团队、许可证等键值对）。Ticket 有效期内可重复使用。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2018_11.IRM.getSessionInfoFromTicket`

**请求（input）：**

```json
{
  "sessionInfoTicket": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `sessionInfoTicket` | std::string | 由 getSessionInfoTicket 返回的加密会话票据字符串 |

**响应（output）：**

```json
{
  "userInfo": {
    "SampleStringKey": "String"
  },
  "sessionValues": {
    "SampleStringKey": "String"
  },
  "siteId": 0,
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userInfo` | Teamcenter::Soa::Administration::_2018_11::IRM::UserInfo | User login information, like: userId, userUid, groupName, groupUid, roleName, roleUid, projectId, projectUid |
| `sessionValues` | Teamcenter::Soa::Administration::_2018_11::IRM::SessionValuesMap2 | sessionValues |
| `siteId` | int | Site identifier that generated the ticket. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 2.4.5.2 getSessionInfoTicket

**接口路径：** `Administration-2018-11-IRM/getSessionInfoTicket`

**API 版本：** `2018-11`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 将当前会话的用户、组、会话信息、站点标识和过期时间打包成加密字符串（Ticket）返回，供无用户概念的系统（如 VDS）以此 Ticket 向 TC 查询会话信息。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2018_11.IRM.getSessionInfoTicket`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "sessionInfoTicket": "String",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `sessionInfoTicket` | std::string | 由 getSessionInfoTicket 返回的加密会话票据字符串 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

### 2.5 组织管理（OrganizationManagement）

**涵盖 API 版本：** `2018-11`  
**操作数：** 2

#### 版本 2018-11

##### 2.5.1.1 getUserConsentStatement

**接口路径：** `Administration-2018-11-OrganizationManagement/getUserConsentStatement`

**API 版本：** `2018-11`  
**Service：** `OrganizationManagement`  
**Library：** `Administration`

**功能说明：** 返回当前登录用户所在区域（locale）的用户同意声明（GDPR）。若该区域无对应声明，则返回主区域（master locale）的声明。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2018_11.OrganizationManagement.getUserConsentStatement`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "consentStatement": "String",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `consentStatement` | std::string | 返回的用户同意声明文本 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 2.5.1.2 recordUserConsent

**接口路径：** `Administration-2018-11-OrganizationManagement/recordUserConsent`

**API 版本：** `2018-11`  
**Service：** `OrganizationManagement`  
**Library：** `Administration`

**功能说明：** 记录用户对通用数据保护条例（GDPR）的同意操作。若底层函数调用出现问题，可能返回部分错误（partial errors）。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2018_11.OrganizationManagement.recordUserConsent`

**请求（input）：**

```json
{
  "userConsent": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userConsent` | bool | 用户同意信息，包含同意声明版本等 |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.6 偏好设置管理（PreferenceManagement）

**涵盖 API 版本：** `2007-06`、`2008-06`、`2011-05`、`2012-09`、`2020-12`  
**操作数：** 15

#### 版本 2007-06

##### 2.6.1.1 setPreferences

**接口路径：** `Administration-2007-06-PreferenceManagement/setPreferences`

**API 版本：** `2007-06`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 设置会话或非会话偏好设置的值。会话偏好为当前登录用户视角的偏好；非会话偏好（如 Site/Group/Role 级别）需指定目标对象，且需要相应管理权限。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2007_06.PreferenceManagement.setPreferences`

**请求（input）：**

```json
{
  "setPrefInput": [
    {
      "preferenceScope": "String",
      "inputPrefs": {
        "prefsInfo": [
          {
            "preferenceDefinition": {
              "preferenceName": "String",
              "preferenceCategory": "String",
              "preferenceDescription": "String",
              "preferenceScope": "String",
              "preferenceType": "String",
              "isArray": false,
              "isDisabled": false
            },
            "contextInformation": [
              {
                "contextName": "String",
                "value": [
                  "String"
                ]
              }
            ]
          }
        ]
      },
      "object": {
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
| `setPrefInput` | Teamcenter::Soa::Administration::_2007_06::PreferenceManagement::PreferencesSetInput[] | 偏好设置输入列表，每项包含名称、值和位置信息 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2008-06

##### 2.6.2.1 lockSitePreferences

**接口路径：** `Administration-2008-06-PreferenceManagement/lockSitePreferences`

**API 版本：** `2008-06`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 锁定数据库中存储的 Site 偏好设置，仅供系统管理员使用。锁定非强制但可确保排他性写入。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2008_06.PreferenceManagement.lockSitePreferences`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
"bool"
```

---

##### 2.6.2.2 unlockSitePreferences

**接口路径：** `Administration-2008-06-PreferenceManagement/unlockSitePreferences`

**API 版本：** `2008-06`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 释放 `lockSitePreferences` 设置的 Site 偏好锁定。仅加锁用户可执行解锁。注意：TC 11.6 起偏好存储已从 XML 迁移至数据库，此操作行为可能有所变化。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2008_06.PreferenceManagement.unlockSitePreferences`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
"bool"
```

---

#### 版本 2011-05

##### 2.6.3.1 refreshPreferences

**接口路径：** `Administration-2011-05-PreferenceManagement/refreshPreferences`

**API 版本：** `2011-05`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 刷新服务器缓存中的偏好值，使其与最新值同步。在多会话并发修改同一用户偏好，或管理员修改 Site/Role/Group 偏好时使用。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2011_05.PreferenceManagement.refreshPreferences`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
"bool"
```

---

#### 版本 2012-09

##### 2.6.4.1 deletePreferenceDefinitions

**接口路径：** `Administration-2012-09-PreferenceManagement/deletePreferenceDefinitions`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 删除指定偏好的定义及其所有值实例。参数 `deleteAllCustomDefinitions` 已废弃（偏好不再区分 Custom/COTS）。操作结果在 ServiceData 中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.deletePreferenceDefinitions`

**请求（input）：**

```json
{
  "preferenceNames": [
    "String"
  ],
  "deleteAllCustomDefinitions": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `preferenceNames` | std::string[] | 偏好名称列表；为空或首元素为 * 时返回全部偏好 |
| `deleteAllCustomDefinitions` | bool | （已废弃）是否删除全部自定义定义，现在无效 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.6.4.2 deletePreferencesAtLocations

**接口路径：** `Administration-2012-09-PreferenceManagement/deletePreferencesAtLocations`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 仅删除指定位置（Site/Group/Role/User）的偏好实例，不影响其他位置的值。输入为 `PreferencesAtLocationIn` 列表。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.deletePreferencesAtLocations`

**请求（input）：**

```json
{
  "deletePreferencesAtLocationIn": [
    {
      "location": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "location": "String"
      },
      "preferenceNames": [
        "String"
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `deletePreferencesAtLocationIn` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::PreferencesAtLocationIn[] | 需要删除的偏好及其位置列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.6.4.3 getPreferences

**接口路径：** `Administration-2012-09-PreferenceManagement/getPreferences`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 按当前登录用户及应用上下文检索指定名称的偏好值；若当前上下文无值则回退到默认上下文。名称列表为空或首元素为 `*` 时返回全部偏好。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.getPreferences`

**请求（input）：**

```json
{
  "preferenceNames": [
    "String"
  ],
  "includePreferenceDescriptions": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `preferenceNames` | std::string[] | 偏好名称列表；为空或首元素为 * 时返回全部偏好 |
| `includePreferenceDescriptions` | bool | 是否在结果中包含偏好描述信息 |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "response": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": {
        "values": [
          "String"
        ],
        "valueOrigination": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `data` | Teamcenter::Soa::Server::ServiceData | Contains the partial errors in the same order as in the input list. |
| `response` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::CompletePreference[] | A list of complete preference information. Each structure holds all the preference definition ( PreferenceDefinition structure) and its values ( Prefe |

---

##### 2.6.4.4 getPreferencesAtLocations

**接口路径：** `Administration-2012-09-PreferenceManagement/getPreferencesAtLocations`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 按指定名称和位置（Site/Group/Role/User）精确检索偏好值，不受应用上下文影响，适合管理场景。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.getPreferencesAtLocations`

**请求（input）：**

```json
{
  "getPreferenceAtLocationIn": [
    {
      "location": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "location": "String"
      },
      "preferenceNames": [
        "String"
      ]
    }
  ],
  "includePreferenceDescriptions": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `getPreferenceAtLocationIn` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::PreferencesAtLocationIn[] | 按位置查询偏好的输入结构列表 |
| `includePreferenceDescriptions` | bool | 是否在结果中包含偏好描述信息 |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "responses": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": {
        "values": [
          "String"
        ],
        "valueOrigination": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `data` | Teamcenter::Soa::Server::ServiceData | Partial errors. Each partial error will contain the index of the related input data. |
| `responses` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::CompletePreference[] | The preference description and category for the locations OOTB (out-of-the-box), Overlay or Site. In the other cases, those strings will be empty. |

---

##### 2.6.4.5 importPreferencesAtLocationDryRun

**接口路径：** `Administration-2012-09-PreferenceManagement/importPreferencesAtLocationDryRun`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 模拟（试运行）将偏好文件导入指定位置，不实际写入，仅返回导入结果预览，供确认后再执行真正导入。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.importPreferencesAtLocationDryRun`

**请求（input）：**

```json
{
  "importPreferences": {
    "location": {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "location": "String"
    },
    "fileTicket": "String",
    "categoryNames": [
      "String"
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `importPreferences` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::ImportPreferencesAtLocationDryRunIn | 试运行导入的偏好文件信息及目标位置 |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "dbImpactedPreferences": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": {
        "values": [
          "String"
        ],
        "valueOrigination": "String"
      }
    }
  ],
  "conflictingPreferencesFromFile": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": {
        "values": [
          "String"
        ],
        "valueOrigination": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |
| `dbImpactedPreferences` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::CompletePreference[] | List of preferences in the database that would be impacted by the import. |
| `conflictingPreferencesFromFile` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::CompletePreference[] | Llist of preferences from the input file, for which conflict will arise. Conflicts are cases in which either the preference already exists in the data |

---

##### 2.6.4.6 importPreferencesAtLocations

**接口路径：** `Administration-2012-09-PreferenceManagement/importPreferencesAtLocations`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 将偏好文件导入指定位置（Site/Group/Role/User）。Site 级别仅系统管理员可操作；Group/Role 级别需要对应管理权限；User 级别仅用户本人可操作。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.importPreferencesAtLocations`

**请求（input）：**

```json
{
  "importPreferenceIn": {
    "locations": [
      {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "location": "String"
      }
    ],
    "fileTicket": "String",
    "categoryNames": [
      "String"
    ],
    "importAction": "String"
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `importPreferenceIn` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::ImportPreferencesAtLocationsIn | 正式导入的偏好文件信息及目标位置列表 |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "fileTicket": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |
| `fileTicket` | std::string | A ticket of a file in the transient volume uploaded by the client. The content of the file will depend on the calling operation, and it will be specif |

---

##### 2.6.4.7 removeStalePreferenceInstancesAtLocations

**接口路径：** `Administration-2012-09-PreferenceManagement/removeStalePreferenceInstancesAtLocations`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 删除指定位置的过期偏好实例（与 preference manager 工具的清理模式等效）。实际已被工具替代，此 SOA 操作不产生错误，ServiceData 始终为空。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.removeStalePreferenceInstancesAtLocations`

**请求（input）：**

```json
{
  "locations": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "location": "String"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `locations` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::PreferenceLocation[] | 偏好位置列表（Site/Group/Role/User） |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.6.4.8 setPreferences2

**接口路径：** `Administration-2012-09-PreferenceManagement/setPreferences2`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 允许当前登录用户为自身设置偏好值。仅当偏好已在系统中定义且保护范围允许该用户修改时才能成功，否则返回对应错误。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.setPreferences2`

**请求（input）：**

```json
{
  "preferenceInput": [
    {
      "preferenceName": "String",
      "values": [
        "String"
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `preferenceInput` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::SetPreferences2In[] | 偏好定义或值的输入信息列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.6.4.9 setPreferencesAtLocations

**接口路径：** `Administration-2012-09-PreferenceManagement/setPreferencesAtLocations`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 按指定位置（Site/Group/Role/User）设置偏好值。Site 级别需管理员权限；Group/Role 级别需相应管理权限；User 级别需是本人。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.setPreferencesAtLocations`

**请求（input）：**

```json
{
  "setPreferenceIn": [
    {
      "location": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "location": "String"
      },
      "preferenceInputs": {
        "preferenceName": "String",
        "values": [
          "String"
        ]
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `setPreferenceIn` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::SetPreferencesAtLocationsIn[] | 按位置设置偏好的输入结构列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.6.4.10 setPreferencesDefinition

**接口路径：** `Administration-2012-09-PreferenceManagement/setPreferencesDefinition`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 允许系统管理员创建新偏好的定义或修改已有定义。若偏好不存在则创建；若已存在则修改定义和值（若提供了值）。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.setPreferencesDefinition`

**请求（input）：**

```json
{
  "preferenceInput": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": [
        "String"
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `preferenceInput` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::SetPreferencesDefinitionIn[] | 偏好定义或值的输入信息列表 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2020-12

##### 2.6.5.1 refreshPreferences2

**接口路径：** `Administration-2020-12-PreferenceManagement/refreshPreferences2`

**API 版本：** `2020-12`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** `refreshPreferences` 的增强版：先刷新指定偏好的服务器缓存，再按当前用户和应用上下文返回最新值。支持按名称列表精确刷新。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2020_12.PreferenceManagement.refreshPreferences2`

**请求（input）：**

```json
{
  "preferenceNames": [
    "String"
  ],
  "includePreferenceDescriptions": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `preferenceNames` | std::string[] | 偏好名称列表；为空或首元素为 * 时返回全部偏好 |
| `includePreferenceDescriptions` | bool | 是否在结果中包含偏好描述信息 |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "response": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": {
        "values": [
          "String"
        ],
        "valueOrigination": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `data` | Teamcenter::Soa::Server::ServiceData | Contains the partial errors in the same order as in the input list. |
| `response` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::CompletePreference[] | A list of complete preference information. Each structure holds all the preference definition ( PreferenceDefinition structure) and its values ( Prefe |

---

### 2.7 角色管理（RoleManagement）

**涵盖 API 版本：** `2017-05`  
**操作数：** 2

#### 版本 2017-05

##### 2.7.1.1 addRolesToGroup

**接口路径：** `Administration-2017-05-RoleManagement/addRolesToGroup`

**API 版本：** `2017-05`  
**Service：** `RoleManagement`  
**Library：** `Administration`

**功能说明：** 向指定 Group 对象添加角色（Role）。若角色不存在则先创建。新建角色在 ServiceData 的 created 列表中返回，被修改的 Group 在 modified 列表中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2017_05.RoleManagement.addRolesToGroup`

**请求（input）：**

```json
{
  "roleGroupStructs": [
    {
      "clientId": "String",
      "rolesToAdd": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "rolesToCreateAndAdd": [
        {
          "roleName": "String",
          "roleDescription": "String"
        }
      ],
      "grp": {
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
| `roleGroupStructs` | Teamcenter::Soa::Administration::_2017_05::RoleManagement::AddRolesToGroupStructure[] | 角色与组的关联关系列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.7.1.2 removeRolesFromGroup

**接口路径：** `Administration-2017-05-RoleManagement/removeRolesFromGroup`

**API 版本：** `2017-05`  
**Service：** `RoleManagement`  
**Library：** `Administration`

**功能说明：** 从指定 Group 对象中移除指定角色（Role）。被修改的 Group 对象在 ServiceData 的 modified 列表中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2017_05.RoleManagement.removeRolesFromGroup`

**请求（input）：**

```json
{
  "roleGroupStructs": [
    {
      "roles": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "grp": {
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
| `roleGroupStructs` | Teamcenter::Soa::Administration::_2017_05::RoleManagement::RoleGroupStructure[] | 角色与组的关联关系列表 |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.8 用户管理（UserManagement）

**涵盖 API 版本：** `2007-01`、`2012-09`、`2014-10`、`2015-03`、`2015-07`、`2016-03`、`2016-10`、`2017-05`  
**操作数：** 11

#### 版本 2007-01

##### 2.8.1.1 createDisciplines

**接口路径：** `Administration-2007-01-UserManagement/createDisciplines`

**API 版本：** `2007-01`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 批量创建 Discipline（学科/专业）对象。若指定了父 Group，则将新建的 Discipline 添加到该组中。需要系统管理员或组管理员权限。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2007_01.UserManagement.createDisciplines`

**请求（input）：**

```json
{
  "disciplines": [
    {
      "discipline": {
        "clientId": "String",
        "name": "String",
        "description": "String",
        "defaultRate": 0,
        "levels": [
          {
            "levelName": "String",
            "levelNumber": 0
          }
        ],
        "users": [
          {
            "user": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "levelName": "String"
          }
        ]
      },
      "group": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "role": {
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
| `disciplines` | Teamcenter::Soa::Administration::_2007_01::UserManagement::CreateDisciplinesIn[] | 需要创建的 Discipline 信息列表 |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "String",
      "discipline": {
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
| `output` | Teamcenter::Soa::Administration::_2007_01::UserManagement::CreateDisciplinesOutput[] | List of CreateDisciplinesOutput objects, one for each CreateDisciplinesIn object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

#### 版本 2012-09

##### 2.8.2.1 getUserGroupMembers

**接口路径：** `Administration-2012-09-UserManagement/getUserGroupMembers`

**API 版本：** `2012-09`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 批量获取指定用户的所有 GroupMember 信息，包括关联的 Group、Role、User 对象，以及状态、组管理员权限、默认角色标志等。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.UserManagement.getUserGroupMembers`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "includeInactive": false,
      "includeUser": false,
      "clientId": "String"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputObjects` | Teamcenter::Soa::Administration::_2012_09::UserManagement::GetUserGroupMembersInputData[] | 输入对象列表 |

**响应（output）：**

```json
{
  "outputs": [
    {
      "clientId": "String",
      "memebrs": [
        {
          "group": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "roleUsers": [
            {
              "role": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "user": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "isActive": false,
              "isDefaultRole": false,
              "isGroupAdmin": false
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
| `outputs` | Teamcenter::Soa::Administration::_2012_09::UserManagement::GetUserGroupMembersOutput[] | List of group member information, one for each User object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 2.8.2.2 setGroupMemberProperties

**接口路径：** `Administration-2012-09-UserManagement/setGroupMemberProperties`

**API 版本：** `2012-09`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 批量更新一个或多个 GroupMember 的属性，可更新：`membership_data_source`、`ga`（组管理员）、`default_role`（默认角色）、`status`（状态）。修改后的 GroupMember 在 ServiceData updated 列表中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.UserManagement.setGroupMemberProperties`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "groupMember": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "groupMemberPropValuesMap": {
        "SampleStringKey": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputObjects` | Teamcenter::Soa::Administration::_2012_09::UserManagement::GroupMemberInput[] | 输入对象列表 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2014-10

##### 2.8.3.1 makeUser

**接口路径：** `Administration-2014-10-UserManagement/makeUser`

**API 版本：** `2014-10`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 在 TC 服务器上以当前会话用户的身份执行 `make_user` 实用程序。支持命令行参数和批处理输入文件（通过 FMS Ticket 上传）。返回执行状态和可选的标准输出/错误输出。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2014_10.UserManagement.makeUser`

**请求（input）：**

```json
{
  "arguments": [
    "String"
  ],
  "batchFileFmsTicket": "String",
  "enableStandardOutput": false,
  "enableStandardError": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arguments` | std::string[] | make_user 工具的命令行参数 |
| `batchFileFmsTicket` | std::string | 批处理输入文件的 FMS Ticket（通过 fmsupload 上传后获取） |
| `enableStandardOutput` | bool | 是否返回标准输出（stdout）内容 |
| `enableStandardError` | bool | 是否返回标准错误（stderr）内容 |

**响应（output）：**

```json
{
  "commandStatus": 0,
  "standardOutputFmsTicket": "String",
  "standardErrorFmsTicket": "String",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `commandStatus` | int | The make_user command completion status (0 - Success, 1 - Failure). See the make_user utility documentation for details. |
| `standardOutputFmsTicket` | std::string | FMS ticket for the make_user standard output. This element is empty if the enableStandardOutput parameter for the operation is false. |
| `standardErrorFmsTicket` | std::string | FMS ticket for the make_user standard error. This element is empty if the enableStandardError parameter for the operation is false. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

#### 版本 2015-03

##### 2.8.4.1 setUserProfileProperties

**接口路径：** `Administration-2015-03-UserManagement/setUserProfileProperties`

**API 版本：** `2015-03`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 设置指定用户的 `Fnd0CustomUserProfile` 对象上的属性。若该 Profile 不存在则自动创建，并将 User 的 `fnd0custom_user_profile` 属性指向新建对象。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2015_03.UserManagement.setUserProfileProperties`

**请求（input）：**

```json
{
  "userProfileInputs": [
    {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyMap": {
        "SampleStringKey": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userProfileInputs` | Teamcenter::Soa::Administration::_2015_03::UserManagement::UserProfileProperties[] | 用户 Profile 属性设置输入列表 |

**响应（output）：**

```json
{
  "userProfileMap": {
    "SampleIModelObjectKey": "IModelObject"
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userProfileMap` | Teamcenter::Soa::Administration::_2015_03::UserManagement::UserProfileMap | User and its corresponding Fnd0CustomUserProfile object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

#### 版本 2015-07

##### 2.8.5.1 createOrUpdateUser

**接口路径：** `Administration-2015-07-UserManagement/createOrUpdateUser`

**API 版本：** `2015-07`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 批量创建或更新 User 对象。若用户不存在则创建，否则更新。需要系统管理员权限。若输入中的 Person 对象不存在，会先创建 Person 再创建 User。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2015_07.UserManagement.createOrUpdateUser`

**请求（input）：**

```json
{
  "userInputs": [
    {
      "userId": "String",
      "person": "String",
      "password": "String",
      "defaultGroup": "String",
      "newOwner": "String",
      "newOwningGroup": "String",
      "userPropertyMap": {
        "SampleStringKey": "String"
      },
      "userAddlPropertyMap": {
        "SampleStringKey": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userInputs` | Teamcenter::Soa::Administration::_2015_07::UserManagement::CreateOrUpdateUserInputs[] | 用户创建或更新的输入信息列表 |

**响应（output）：**

```json
{
  "userObjectMap": {
    "SampleStringKey": {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "person": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "profile": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userObjectMap` | Teamcenter::Soa::Administration::_2015_07::UserManagement::UserObjectsMap | User Id and its corresponding UserObjectStructure which contains User , Person and Fnd0CustomUserProfile objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

#### 版本 2016-03

##### 2.8.6.1 deleteUser

**接口路径：** `Administration-2016-03-UserManagement/deleteUser`

**API 版本：** `2016-03`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 从 Teamcenter 中删除 User 对象。可选择同时删除其拥有的对象，或将所有权转移给指定的新用户。需要系统管理员权限。返回成功删除的用户 UID 列表。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2016_03.UserManagement.deleteUser`

**请求（input）：**

```json
{
  "userInput": [
    {
      "userId": "String",
      "newOwningUser": "String",
      "newOwningGroup": "String",
      "deleteObjects": false
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userInput` | Teamcenter::Soa::Administration::_2016_03::UserManagement::DeleteUsersInput[] | 用户删除操作的输入信息 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2016-10

##### 2.8.7.1 getCurrentCountryPageInfo

**接口路径：** `Administration-2016-10-UserManagement/getCurrentCountryPageInfo`

**API 版本：** `2016-10`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 获取当前国家选择页面的配置，包括可选国家列表、默认显示国家及可自定义的保密声明文字。供 RAC 和 AW 客户端渲染国家选择界面使用。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2016_10.UserManagement.getCurrentCountryPageInfo`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "displayCountries": {
    "SampleStringKey": "String"
  },
  "extraInfoOut": {
    "SampleStringKey": "String"
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `displayCountries` | Teamcenter::Soa::Administration::_2016_10::UserManagement::ExtraMappedInfo | Map of key/value pairs (string, string) representing the selectable countries the user may choose when filling out the current country selection page. |
| `extraInfoOut` | Teamcenter::Soa::Administration::_2016_10::UserManagement::ExtraMappedInfo | Map of key/value pairs (string, string). Key: initialCountry . The initial value displayed in the current country pick list. The format is ISO 3166-1  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 2.8.7.2 saveAndValidateCurrentCountry

**接口路径：** `Administration-2016-10-UserManagement/saveAndValidateCurrentCountry`

**API 版本：** `2016-10`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 保存当前会话用户选择的国家，并校验该用户是否违反全球许可协议。即使校验失败，国家仍会被保存。此操作不可传入 null 值。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2016_10.UserManagement.saveAndValidateCurrentCountry`

**请求（input）：**

```json
{
  "selectedcountry": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `selectedcountry` | std::string | 用户选择的国家代码 |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2017-05

##### 2.8.8.1 addUsersAsGroupMembers

**接口路径：** `Administration-2017-05-UserManagement/addUsersAsGroupMembers`

**API 版本：** `2017-05`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 将用户（新建或已有）作为 GroupMember 添加到指定 Group 和 Role 下。若用户不存在则先创建。需要系统管理员或组管理员权限。Role 对象不存在时返回错误。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2017_05.UserManagement.addUsersAsGroupMembers`

**请求（input）：**

```json
{
  "userRoleGroupStructs": [
    {
      "clientId": "String",
      "usersToAdd": [
        {
          "user": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "userAttributes": {
            "isGroupAdmin": false,
            "status": false,
            "isDefaultRole": false
          }
        }
      ],
      "usersToCreateAndAdd": [
        {
          "user": {
            "userId": "String",
            "person": "String",
            "password": "String",
            "defaultGroup": "String",
            "newOwner": "String",
            "newOwningGroup": "String",
            "userPropertyMap": {
              "SampleStringKey": "String"
            },
            "userAddlPropertyMap": {
              "SampleStringKey": "String"
            }
          },
          "userAttributes": {
            "isGroupAdmin": false,
            "status": false,
            "isDefaultRole": false
          }
        }
      ],
      "grp": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "role": {
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
| `userRoleGroupStructs` | Teamcenter::Soa::Administration::_2017_05::UserManagement::AddUsersAsGroupMembersStructure[] | 用户、角色、组的关联关系列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.8.8.2 removeGroupMembers

**接口路径：** `Administration-2017-05-UserManagement/removeGroupMembers`

**API 版本：** `2017-05`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 从指定 Group 和 Role 下移除 GroupMember。需要系统管理员或组管理员权限。输入不可包含 null 的 User、Group 或 Role。结果以结构体列表形式返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2017_05.UserManagement.removeGroupMembers`

**请求（input）：**

```json
{
  "userRoleGroupStructs": [
    {
      "users": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "grp": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "role": {
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
| `userRoleGroupStructs` | Teamcenter::Soa::Administration::_2017_05::UserManagement::UserRoleGroupStructure[] | 用户、角色、组的关联关系列表 |

**响应（output）：**

```json
{
  "userRoleGrpStructs": [
    {
      "users": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "grp": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "role": {
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
| `userRoleGrpStructs` | Teamcenter::Soa::Administration::_2017_05::UserManagement::UserRoleGroupStructure[] | A list of structures of User and associated Role and Group objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

---

## 3. 按 API 版本（年-月）归档

按时间顺序列出各版本下的接口，便于了解 Administration API 的演进历史。

### 3.1 API 版本 2006-03

**Service：** IRM  **操作数：** 5

##### 3.1.1 checkAccessorsPrivileges

**接口路径：** `Administration-2006-03-IRM/checkAccessorsPrivileges`

**API 版本：** `2006-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 获取指定 GroupMember 对一组业务对象的访问权限裁决。系统会根据用户、角色、用户组的组合找到对应访问者（accessor），再依据访问控制规则返回每个权限的授权结果。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2006_03.IRM.checkAccessorsPrivileges`

**请求（input）：**

```json
{
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "privilegeNames": [
    "String"
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `groupMember` | Teamcenter::BusinessObject | 要检查权限的 GroupMember 业务对象 |
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |
| `privilegeNames` | std::string[] | 需要检查的权限名称列表 |

**响应（output）：**

```json
{
  "privilegeReports": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "privilegeInfos": [
        {
          "privilegeName": "String",
          "verdict": false
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `privilegeReports` | Teamcenter::Soa::Administration::_2006_03::IRM::PrivilegeReport[] | A list of PrivilegeReport objects one for each of the given business object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.1.2 getEffectiveACLInfo

**接口路径：** `Administration-2006-03-IRM/getEffectiveACLInfo`

**API 版本：** `2006-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 获取一组业务对象的有效访问控制列表（ACL）信息，展示当前用户对这些对象实际生效的访问控制条目（ACE）。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2006_03.IRM.getEffectiveACLInfo`

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
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |

**响应（output）：**

```json
{
  "aclInfoList": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "aclInfos": [
        {
          "grantedNames": [
            "String"
          ],
          "revokedNames": [
            "String"
          ],
          "accessorType": "String",
          "accessorId": "String",
          "namedACL": "String"
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `aclInfoList` | Teamcenter::Soa::Administration::_2006_03::IRM::ACLInfos[] | List of derived Effective ACL reports for each of the given business objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.1.3 getExtraProtectionInfo

**接口路径：** `Administration-2006-03-IRM/getExtraProtectionInfo`

**API 版本：** `2006-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 获取指定用户对一组业务对象的附加保护信息，包括哪条命名 ACL、哪个 Accessor 及哪条 AM 规则路径决定了最终权限结论。用于排查权限问题。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2006_03.IRM.getExtraProtectionInfo`

**请求（input）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
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
| `user` | Teamcenter::User | 用户业务对象 |
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |

**响应（output）：**

```json
{
  "protectionReports": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "protections": [
        {
          "privilege": "String",
          "verdict": false,
          "rules": [
            "String"
          ],
          "ruleEvaluation": [
            "String"
          ],
          "acl": "String",
          "accessorType": "String",
          "accessorId": "String"
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `protectionReports` | Teamcenter::Soa::Administration::_2006_03::IRM::ProtectionReport[] | List of extra protection report objects one for each of the given business objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.1.4 removeAccessor

**接口路径：** `Administration-2006-03-IRM/removeAccessor`

**API 版本：** `2006-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 从给定对象中删除指定访问者（accessor）。对象可以是命名 ACL 或 POM 应用对象：若为命名 ACL，则从中删除对应 ACE；若为 POM 应用对象，则从对象级 ACL 中删除该 ACE。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2006_03.IRM.removeAccessor`

**请求（input）：**

```json
{
  "objects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "accessorType": "String",
  "accessorId": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |
| `accessorType` | std::string | 访问者类型（如 User、Group、Role、World） |
| `accessorId` | std::string | 访问者标识符 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.1.5 setPrivileges

**接口路径：** `Administration-2006-03-IRM/setPrivileges`

**API 版本：** `2006-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 在指定对象上授予或拒绝一组访问权限给指定访问者。对象可为命名 ACL 或 POM 应用对象；若为 POM 应用对象且对象级 ACL 不存在则自动创建。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2006_03.IRM.setPrivileges`

**请求（input）：**

```json
{
  "privilegeSettings": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "grant": [
        "String"
      ],
      "revoke": [
        "String"
      ],
      "unset": [
        "String"
      ]
    }
  ],
  "accessorType": "String",
  "accessorId": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `privilegeSettings` | Teamcenter::Soa::Administration::_2006_03::IRM::PrivilegeSettingInput[] | 权限设置信息列表（对象 + 权限名称 + 授予/拒绝） |
| `accessorType` | std::string | 访问者类型（如 User、Group、Role、World） |
| `accessorId` | std::string | 访问者标识符 |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.2 API 版本 2007-01

**Service：** UserManagement  **操作数：** 1

##### 3.2.1 createDisciplines

**接口路径：** `Administration-2007-01-UserManagement/createDisciplines`

**API 版本：** `2007-01`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 批量创建 Discipline（学科/专业）对象。若指定了父 Group，则将新建的 Discipline 添加到该组中。需要系统管理员或组管理员权限。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2007_01.UserManagement.createDisciplines`

**请求（input）：**

```json
{
  "disciplines": [
    {
      "discipline": {
        "clientId": "String",
        "name": "String",
        "description": "String",
        "defaultRate": 0,
        "levels": [
          {
            "levelName": "String",
            "levelNumber": 0
          }
        ],
        "users": [
          {
            "user": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "levelName": "String"
          }
        ]
      },
      "group": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "role": {
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
| `disciplines` | Teamcenter::Soa::Administration::_2007_01::UserManagement::CreateDisciplinesIn[] | 需要创建的 Discipline 信息列表 |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "String",
      "discipline": {
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
| `output` | Teamcenter::Soa::Administration::_2007_01::UserManagement::CreateDisciplinesOutput[] | List of CreateDisciplinesOutput objects, one for each CreateDisciplinesIn object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

### 3.3 API 版本 2007-06

**Service：** Authorization、PreferenceManagement  **操作数：** 2

##### 3.3.1 checkAuthorization

**接口路径：** `Administration-2007-06-Authorization/checkAuthorization`

**API 版本：** `2007-06`  
**Service：** `Authorization`  
**Library：** `Administration`

**功能说明：** 检查指定用户与用户组组合对一组应用程序或工具的访问授权。规则域（domain）可为 `utility`（工具）或 `application`（应用）。返回每个输入名称对应的授权结果。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2007_06.Authorization.checkAuthorization`

**请求（input）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "group": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "inputNames": [
    {
      "name": "String",
      "ruleDomain": "String"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `user` | Teamcenter::User | 用户业务对象 |
| `group` | Teamcenter::Group | 用户组业务对象 |
| `inputNames` | Teamcenter::Soa::Administration::_2007_06::Authorization::NameInfo[] | 需要检查授权的应用程序或工具名称列表 |

**响应（output）：**

```json
{
  "output": [
    {
      "name": "String",
      "ruleDomain": "String",
      "verdict": false
    }
  ],
  "partialErrors": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Administration::_2007_06::Authorization::NameAuthorizationResponse[] | A list of NameAuthorizationResponse objects one for each of the given application or utility. |
| `partialErrors` | Teamcenter::Soa::Server::ServiceData | 操作过程中的部分错误信息 |

---

##### 3.3.2 setPreferences

**接口路径：** `Administration-2007-06-PreferenceManagement/setPreferences`

**API 版本：** `2007-06`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 设置会话或非会话偏好设置的值。会话偏好为当前登录用户视角的偏好；非会话偏好（如 Site/Group/Role 级别）需指定目标对象，且需要相应管理权限。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2007_06.PreferenceManagement.setPreferences`

**请求（input）：**

```json
{
  "setPrefInput": [
    {
      "preferenceScope": "String",
      "inputPrefs": {
        "prefsInfo": [
          {
            "preferenceDefinition": {
              "preferenceName": "String",
              "preferenceCategory": "String",
              "preferenceDescription": "String",
              "preferenceScope": "String",
              "preferenceType": "String",
              "isArray": false,
              "isDisabled": false
            },
            "contextInformation": [
              {
                "contextName": "String",
                "value": [
                  "String"
                ]
              }
            ]
          }
        ]
      },
      "object": {
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
| `setPrefInput` | Teamcenter::Soa::Administration::_2007_06::PreferenceManagement::PreferencesSetInput[] | 偏好设置输入列表，每项包含名称、值和位置信息 |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.4 API 版本 2008-03

**Service：** IRM  **操作数：** 2

##### 3.4.1 activateUsers

**接口路径：** `Administration-2008-03-IRM/activateUsers`

**API 版本：** `2008-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 根据可用的 Author 或 Consumer 许可证数量激活指定用户。若许可证不足，返回对应错误码。注意：仅激活用户本身，不激活其 GroupMember。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2008_03.IRM.activateUsers`

**请求（input）：**

```json
{
  "activateUser": [
    {
      "licenseLevel": 0,
      "targetUser": {
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
| `activateUser` | Teamcenter::Soa::Administration::_2008_03::IRM::ActivateUserInput[] | 需要激活的用户信息列表 |

**响应（output）：**

```json
{
  "licStatus": [
    {
      "numPurchasedLicenses": 0,
      "numUsedLicenses": 0
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `licStatus` | Teamcenter::Soa::Administration::_2008_03::IRM::LicenseStatus[] | List of LicenseStatus objects, one for each ActivateUserInput object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.4.2 deactivateUsers

**接口路径：** `Administration-2008-03-IRM/deactivateUsers`

**API 版本：** `2008-03`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 停用指定用户，并可选地将其所拥有对象的所有权转移给新用户。停用成功的用户在 ServiceData 的 updated 列表中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2008_03.IRM.deactivateUsers`

**请求（input）：**

```json
{
  "deactivateUser": [
    {
      "targetUser": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newUser": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newGroup": {
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
| `deactivateUser` | Teamcenter::Soa::Administration::_2008_03::IRM::DeactivateUserInput[] | 需要停用的用户信息列表，可包含所有权转移目标用户 |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.5 API 版本 2008-06

**Service：** PreferenceManagement  **操作数：** 2

##### 3.5.1 lockSitePreferences

**接口路径：** `Administration-2008-06-PreferenceManagement/lockSitePreferences`

**API 版本：** `2008-06`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 锁定数据库中存储的 Site 偏好设置，仅供系统管理员使用。锁定非强制但可确保排他性写入。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2008_06.PreferenceManagement.lockSitePreferences`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
"bool"
```

---

##### 3.5.2 unlockSitePreferences

**接口路径：** `Administration-2008-06-PreferenceManagement/unlockSitePreferences`

**API 版本：** `2008-06`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 释放 `lockSitePreferences` 设置的 Site 偏好锁定。仅加锁用户可执行解锁。注意：TC 11.6 起偏好存储已从 XML 迁移至数据库，此操作行为可能有所变化。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2008_06.PreferenceManagement.unlockSitePreferences`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
"bool"
```

---

### 3.6 API 版本 2008-12

**Service：** Authorization  **操作数：** 1

##### 3.6.1 checkAuthorizationAccess

**接口路径：** `Administration-2008-12-Authorization/checkAuthorizationAccess`

**API 版本：** `2008-12`  
**Service：** `Authorization`  
**Library：** `Administration`

**功能说明：** 检查指定用户、用户组和角色三元组合对一组应用程序或工具的访问授权（比 `checkAuthorization` 多了角色维度）。返回每个输入名称的授权结果。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2008_12.Authorization.checkAuthorizationAccess`

**请求（input）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "group": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "role": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "inputNames": [
    {
      "name": "String",
      "ruleDomain": "String"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `user` | Teamcenter::User | 用户业务对象 |
| `group` | Teamcenter::Group | 用户组业务对象 |
| `role` | Teamcenter::Role | 角色业务对象 |
| `inputNames` | Teamcenter::Soa::Administration::_2007_06::Authorization::NameInfo[] | 需要检查授权的应用程序或工具名称列表 |

**响应（output）：**

```json
{
  "output": [
    {
      "name": "String",
      "ruleDomain": "String",
      "verdict": false
    }
  ],
  "partialErrors": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `output` | Teamcenter::Soa::Administration::_2007_06::Authorization::NameAuthorizationResponse[] | A list of NameAuthorizationResponse objects one for each of the given application or utility. |
| `partialErrors` | Teamcenter::Soa::Server::ServiceData | 操作过程中的部分错误信息 |

---

### 3.7 API 版本 2010-04

**Service：** DisciplineManagement、IRM  **操作数：** 5

##### 3.7.1 getDiscipline

**接口路径：** `Administration-2010-04-DisciplineManagement/getDiscipline`

**API 版本：** `2010-04`  
**Service：** `DisciplineManagement`  
**Library：** `Administration`

**功能说明：** 根据名称获取 Discipline（专业/学科）业务对象。若找不到对应名称的 Discipline，返回 null。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2010_04.DisciplineManagement.getDiscipline`

**请求（input）：**

```json
{
  "disciplineName": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `disciplineName` | std::string | Discipline 对象名称 |

**响应（output）：**

```json
{
  "discipline": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `discipline` | Teamcenter::Discipline | 返回的 Discipline 业务对象 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.7.2 getAccessorTypes

**接口路径：** `Administration-2010-04-IRM/getAccessorTypes`

**API 版本：** `2010-04`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 获取 Teamcenter 中所有访问者类型（Accessor Type）的名称列表，如 World、User、Group、Role 等，用于在访问管理器（AM）中配置 ACL。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2010_04.IRM.getAccessorTypes`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "accessorTypeNameInfos": [
    {
      "internalName": "String",
      "displayName": "String"
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `accessorTypeNameInfos` | Teamcenter::Soa::Administration::_2010_04::IRM::DisplayNameInfo[] | List of DisplayNameInfo objects containing the internal name and corresponding display name for each of the Accessor Types in Teamcenter. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.7.3 getEffectiveACLInfo2

**接口路径：** `Administration-2010-04-IRM/getEffectiveACLInfo2`

**API 版本：** `2010-04`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** `getEffectiveACLInfo` 的增强版，支持批量业务对象输入，并可返回更丰富的有效 ACL 信息（含 ACE 详情）。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2010_04.IRM.getEffectiveACLInfo2`

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
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |

**响应（output）：**

```json
{
  "aclInfosList": [
    {
      "workSpaceObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "aclInfos": [
        {
          "grantedPrivsInfo": [
            {
              "internalName": "String",
              "displayName": "String"
            }
          ],
          "revokedPrivsInfo": [
            {
              "internalName": "String",
              "displayName": "String"
            }
          ],
          "accessorTypeNameInfo": {
            "internalName": "String",
            "displayName": "String"
          },
          "accessorIdInfo": {
            "internalName": "String",
            "displayName": "String"
          },
          "aclNameInfo": {
            "internalName": "String",
            "displayName": "String"
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
| `aclInfosList` | Teamcenter::Soa::Administration::_2010_04::IRM::ACLInfos[] | List of derived Effective ACL reports for each of the given business objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.7.4 getExtraProtectionInfo2

**接口路径：** `Administration-2010-04-IRM/getExtraProtectionInfo2`

**API 版本：** `2010-04`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** `getExtraProtectionInfo` 的增强版，返回更详细的附加保护信息，适用于复杂权限路径的溯源分析。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2010_04.IRM.getExtraProtectionInfo2`

**请求（input）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
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
| `user` | Teamcenter::User | 用户业务对象 |
| `objects` | Teamcenter::BusinessObject[] | 目标业务对象列表 |

**响应（output）：**

```json
{
  "extraProtectionReports": [
    {
      "workSpaceObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "extraProtectionInfos": [
        {
          "privilegeNameInfo": {
            "internalName": "String",
            "displayName": "String"
          },
          "verdict": false,
          "rules": [
            "String"
          ],
          "ruleEvaluation": [
            "String"
          ],
          "aclNameInfo": {
            "internalName": "String",
            "displayName": "String"
          },
          "accessorTypeNameInfo": {
            "internalName": "String",
            "displayName": "String"
          },
          "accessorIdInfo": {
            "internalName": "String",
            "displayName": "String"
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
| `extraProtectionReports` | Teamcenter::Soa::Administration::_2010_04::IRM::ExtraProtectionInfoReport[] | List of extra protection report objects one for each of the given business objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.7.5 getPrivilegeNames

**接口路径：** `Administration-2010-04-IRM/getPrivilegeNames`

**API 版本：** `2010-04`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 获取 Teamcenter 中全部访问权限的内部名称及对应本地化显示名称，内部名称用于程序调用，显示名称用于界面展示。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2010_04.IRM.getPrivilegeNames`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "privNameInfos": [
    {
      "internalName": "String",
      "displayName": "String"
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `privNameInfos` | Teamcenter::Soa::Administration::_2010_04::IRM::DisplayNameInfo[] | A list of DisplayNameInfo objects that holds internal name and display names of each Teamcenter privilege objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

### 3.8 API 版本 2011-05

**Service：** PreferenceManagement  **操作数：** 1

##### 3.8.1 refreshPreferences

**接口路径：** `Administration-2011-05-PreferenceManagement/refreshPreferences`

**API 版本：** `2011-05`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 刷新服务器缓存中的偏好值，使其与最新值同步。在多会话并发修改同一用户偏好，或管理员修改 Site/Role/Group 偏好时使用。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2011_05.PreferenceManagement.refreshPreferences`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
"bool"
```

---

### 3.9 API 版本 2012-09

**Service：** PreferenceManagement、UserManagement  **操作数：** 12

##### 3.9.1 deletePreferenceDefinitions

**接口路径：** `Administration-2012-09-PreferenceManagement/deletePreferenceDefinitions`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 删除指定偏好的定义及其所有值实例。参数 `deleteAllCustomDefinitions` 已废弃（偏好不再区分 Custom/COTS）。操作结果在 ServiceData 中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.deletePreferenceDefinitions`

**请求（input）：**

```json
{
  "preferenceNames": [
    "String"
  ],
  "deleteAllCustomDefinitions": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `preferenceNames` | std::string[] | 偏好名称列表；为空或首元素为 * 时返回全部偏好 |
| `deleteAllCustomDefinitions` | bool | （已废弃）是否删除全部自定义定义，现在无效 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.9.2 deletePreferencesAtLocations

**接口路径：** `Administration-2012-09-PreferenceManagement/deletePreferencesAtLocations`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 仅删除指定位置（Site/Group/Role/User）的偏好实例，不影响其他位置的值。输入为 `PreferencesAtLocationIn` 列表。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.deletePreferencesAtLocations`

**请求（input）：**

```json
{
  "deletePreferencesAtLocationIn": [
    {
      "location": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "location": "String"
      },
      "preferenceNames": [
        "String"
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `deletePreferencesAtLocationIn` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::PreferencesAtLocationIn[] | 需要删除的偏好及其位置列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.9.3 getPreferences

**接口路径：** `Administration-2012-09-PreferenceManagement/getPreferences`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 按当前登录用户及应用上下文检索指定名称的偏好值；若当前上下文无值则回退到默认上下文。名称列表为空或首元素为 `*` 时返回全部偏好。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.getPreferences`

**请求（input）：**

```json
{
  "preferenceNames": [
    "String"
  ],
  "includePreferenceDescriptions": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `preferenceNames` | std::string[] | 偏好名称列表；为空或首元素为 * 时返回全部偏好 |
| `includePreferenceDescriptions` | bool | 是否在结果中包含偏好描述信息 |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "response": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": {
        "values": [
          "String"
        ],
        "valueOrigination": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `data` | Teamcenter::Soa::Server::ServiceData | Contains the partial errors in the same order as in the input list. |
| `response` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::CompletePreference[] | A list of complete preference information. Each structure holds all the preference definition ( PreferenceDefinition structure) and its values ( Prefe |

---

##### 3.9.4 getPreferencesAtLocations

**接口路径：** `Administration-2012-09-PreferenceManagement/getPreferencesAtLocations`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 按指定名称和位置（Site/Group/Role/User）精确检索偏好值，不受应用上下文影响，适合管理场景。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.getPreferencesAtLocations`

**请求（input）：**

```json
{
  "getPreferenceAtLocationIn": [
    {
      "location": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "location": "String"
      },
      "preferenceNames": [
        "String"
      ]
    }
  ],
  "includePreferenceDescriptions": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `getPreferenceAtLocationIn` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::PreferencesAtLocationIn[] | 按位置查询偏好的输入结构列表 |
| `includePreferenceDescriptions` | bool | 是否在结果中包含偏好描述信息 |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "responses": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": {
        "values": [
          "String"
        ],
        "valueOrigination": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `data` | Teamcenter::Soa::Server::ServiceData | Partial errors. Each partial error will contain the index of the related input data. |
| `responses` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::CompletePreference[] | The preference description and category for the locations OOTB (out-of-the-box), Overlay or Site. In the other cases, those strings will be empty. |

---

##### 3.9.5 importPreferencesAtLocationDryRun

**接口路径：** `Administration-2012-09-PreferenceManagement/importPreferencesAtLocationDryRun`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 模拟（试运行）将偏好文件导入指定位置，不实际写入，仅返回导入结果预览，供确认后再执行真正导入。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.importPreferencesAtLocationDryRun`

**请求（input）：**

```json
{
  "importPreferences": {
    "location": {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "location": "String"
    },
    "fileTicket": "String",
    "categoryNames": [
      "String"
    ]
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `importPreferences` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::ImportPreferencesAtLocationDryRunIn | 试运行导入的偏好文件信息及目标位置 |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "dbImpactedPreferences": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": {
        "values": [
          "String"
        ],
        "valueOrigination": "String"
      }
    }
  ],
  "conflictingPreferencesFromFile": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": {
        "values": [
          "String"
        ],
        "valueOrigination": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |
| `dbImpactedPreferences` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::CompletePreference[] | List of preferences in the database that would be impacted by the import. |
| `conflictingPreferencesFromFile` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::CompletePreference[] | Llist of preferences from the input file, for which conflict will arise. Conflicts are cases in which either the preference already exists in the data |

---

##### 3.9.6 importPreferencesAtLocations

**接口路径：** `Administration-2012-09-PreferenceManagement/importPreferencesAtLocations`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 将偏好文件导入指定位置（Site/Group/Role/User）。Site 级别仅系统管理员可操作；Group/Role 级别需要对应管理权限；User 级别仅用户本人可操作。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.importPreferencesAtLocations`

**请求（input）：**

```json
{
  "importPreferenceIn": {
    "locations": [
      {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "location": "String"
      }
    ],
    "fileTicket": "String",
    "categoryNames": [
      "String"
    ],
    "importAction": "String"
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `importPreferenceIn` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::ImportPreferencesAtLocationsIn | 正式导入的偏好文件信息及目标位置列表 |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "fileTicket": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |
| `fileTicket` | std::string | A ticket of a file in the transient volume uploaded by the client. The content of the file will depend on the calling operation, and it will be specif |

---

##### 3.9.7 removeStalePreferenceInstancesAtLocations

**接口路径：** `Administration-2012-09-PreferenceManagement/removeStalePreferenceInstancesAtLocations`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 删除指定位置的过期偏好实例（与 preference manager 工具的清理模式等效）。实际已被工具替代，此 SOA 操作不产生错误，ServiceData 始终为空。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.removeStalePreferenceInstancesAtLocations`

**请求（input）：**

```json
{
  "locations": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "location": "String"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `locations` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::PreferenceLocation[] | 偏好位置列表（Site/Group/Role/User） |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.9.8 setPreferences2

**接口路径：** `Administration-2012-09-PreferenceManagement/setPreferences2`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 允许当前登录用户为自身设置偏好值。仅当偏好已在系统中定义且保护范围允许该用户修改时才能成功，否则返回对应错误。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.setPreferences2`

**请求（input）：**

```json
{
  "preferenceInput": [
    {
      "preferenceName": "String",
      "values": [
        "String"
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `preferenceInput` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::SetPreferences2In[] | 偏好定义或值的输入信息列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.9.9 setPreferencesAtLocations

**接口路径：** `Administration-2012-09-PreferenceManagement/setPreferencesAtLocations`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 按指定位置（Site/Group/Role/User）设置偏好值。Site 级别需管理员权限；Group/Role 级别需相应管理权限；User 级别需是本人。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.setPreferencesAtLocations`

**请求（input）：**

```json
{
  "setPreferenceIn": [
    {
      "location": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "location": "String"
      },
      "preferenceInputs": {
        "preferenceName": "String",
        "values": [
          "String"
        ]
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `setPreferenceIn` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::SetPreferencesAtLocationsIn[] | 按位置设置偏好的输入结构列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.9.10 setPreferencesDefinition

**接口路径：** `Administration-2012-09-PreferenceManagement/setPreferencesDefinition`

**API 版本：** `2012-09`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** 允许系统管理员创建新偏好的定义或修改已有定义。若偏好不存在则创建；若已存在则修改定义和值（若提供了值）。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.setPreferencesDefinition`

**请求（input）：**

```json
{
  "preferenceInput": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": [
        "String"
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `preferenceInput` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::SetPreferencesDefinitionIn[] | 偏好定义或值的输入信息列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.9.11 getUserGroupMembers

**接口路径：** `Administration-2012-09-UserManagement/getUserGroupMembers`

**API 版本：** `2012-09`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 批量获取指定用户的所有 GroupMember 信息，包括关联的 Group、Role、User 对象，以及状态、组管理员权限、默认角色标志等。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.UserManagement.getUserGroupMembers`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "includeInactive": false,
      "includeUser": false,
      "clientId": "String"
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputObjects` | Teamcenter::Soa::Administration::_2012_09::UserManagement::GetUserGroupMembersInputData[] | 输入对象列表 |

**响应（output）：**

```json
{
  "outputs": [
    {
      "clientId": "String",
      "memebrs": [
        {
          "group": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "roleUsers": [
            {
              "role": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "user": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "isActive": false,
              "isDefaultRole": false,
              "isGroupAdmin": false
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
| `outputs` | Teamcenter::Soa::Administration::_2012_09::UserManagement::GetUserGroupMembersOutput[] | List of group member information, one for each User object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.9.12 setGroupMemberProperties

**接口路径：** `Administration-2012-09-UserManagement/setGroupMemberProperties`

**API 版本：** `2012-09`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 批量更新一个或多个 GroupMember 的属性，可更新：`membership_data_source`、`ga`（组管理员）、`default_role`（默认角色）、`status`（状态）。修改后的 GroupMember 在 ServiceData updated 列表中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_09.UserManagement.setGroupMemberProperties`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "groupMember": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "groupMemberPropValuesMap": {
        "SampleStringKey": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `inputObjects` | Teamcenter::Soa::Administration::_2012_09::UserManagement::GroupMemberInput[] | 输入对象列表 |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.10 API 版本 2012-10

**Service：** IRM  **操作数：** 2

##### 3.10.1 getAMImpactedObjects

**接口路径：** `Administration-2012-10-IRM/getAMImpactedObjects`

**API 版本：** `2012-10`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 列出由于访问管理器（AM）规则树变更而导致读取权限受影响的业务对象。仅统计自上次调用本接口以来发生的变更。通常由后台服务定期调用，供索引更新使用。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_10.IRM.getAMImpactedObjects`

**请求（input）：**

```json
{
  "filterByIndexedStatus": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `filterByIndexedStatus` | bool | 是否按已索引状态过滤返回对象 |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "isImpactGlobal": false,
  "impactedUids": [
    "String"
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |
| `isImpactGlobal` | bool | isImpactGlobal |
| `impactedUids` | std::string[] | impactedUids |

---

##### 3.10.2 getSessionValues

**接口路径：** `Administration-2012-10-IRM/getSessionValues`

**API 版本：** `2012-10`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 以键值对 Map 的形式获取当前会话的所有信息，包括用户（user）、角色（roles）、组（groups）、项目团队（project teams）和许可证（licenses）等会话属性。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2012_10.IRM.getSessionValues`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "sessionValues": {
    "SampleStringKey": "String"
  }
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `sessionValues` | Teamcenter::Soa::Administration::_2012_10::IRM::SessionValuesMap | A map of key-value pairs that holds the session keys and the matching session values from Read Expression string. |

---

### 3.11 API 版本 2014-10

**Service：** UserManagement  **操作数：** 1

##### 3.11.1 makeUser

**接口路径：** `Administration-2014-10-UserManagement/makeUser`

**API 版本：** `2014-10`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 在 TC 服务器上以当前会话用户的身份执行 `make_user` 实用程序。支持命令行参数和批处理输入文件（通过 FMS Ticket 上传）。返回执行状态和可选的标准输出/错误输出。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2014_10.UserManagement.makeUser`

**请求（input）：**

```json
{
  "arguments": [
    "String"
  ],
  "batchFileFmsTicket": "String",
  "enableStandardOutput": false,
  "enableStandardError": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `arguments` | std::string[] | make_user 工具的命令行参数 |
| `batchFileFmsTicket` | std::string | 批处理输入文件的 FMS Ticket（通过 fmsupload 上传后获取） |
| `enableStandardOutput` | bool | 是否返回标准输出（stdout）内容 |
| `enableStandardError` | bool | 是否返回标准错误（stderr）内容 |

**响应（output）：**

```json
{
  "commandStatus": 0,
  "standardOutputFmsTicket": "String",
  "standardErrorFmsTicket": "String",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `commandStatus` | int | The make_user command completion status (0 - Success, 1 - Failure). See the make_user utility documentation for details. |
| `standardOutputFmsTicket` | std::string | FMS ticket for the make_user standard output. This element is empty if the enableStandardOutput parameter for the operation is false. |
| `standardErrorFmsTicket` | std::string | FMS ticket for the make_user standard error. This element is empty if the enableStandardError parameter for the operation is false. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

### 3.12 API 版本 2015-03

**Service：** UserManagement  **操作数：** 1

##### 3.12.1 setUserProfileProperties

**接口路径：** `Administration-2015-03-UserManagement/setUserProfileProperties`

**API 版本：** `2015-03`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 设置指定用户的 `Fnd0CustomUserProfile` 对象上的属性。若该 Profile 不存在则自动创建，并将 User 的 `fnd0custom_user_profile` 属性指向新建对象。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2015_03.UserManagement.setUserProfileProperties`

**请求（input）：**

```json
{
  "userProfileInputs": [
    {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyMap": {
        "SampleStringKey": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userProfileInputs` | Teamcenter::Soa::Administration::_2015_03::UserManagement::UserProfileProperties[] | 用户 Profile 属性设置输入列表 |

**响应（output）：**

```json
{
  "userProfileMap": {
    "SampleIModelObjectKey": "IModelObject"
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userProfileMap` | Teamcenter::Soa::Administration::_2015_03::UserManagement::UserProfileMap | User and its corresponding Fnd0CustomUserProfile object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

### 3.13 API 版本 2015-07

**Service：** UserManagement  **操作数：** 1

##### 3.13.1 createOrUpdateUser

**接口路径：** `Administration-2015-07-UserManagement/createOrUpdateUser`

**API 版本：** `2015-07`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 批量创建或更新 User 对象。若用户不存在则创建，否则更新。需要系统管理员权限。若输入中的 Person 对象不存在，会先创建 Person 再创建 User。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2015_07.UserManagement.createOrUpdateUser`

**请求（input）：**

```json
{
  "userInputs": [
    {
      "userId": "String",
      "person": "String",
      "password": "String",
      "defaultGroup": "String",
      "newOwner": "String",
      "newOwningGroup": "String",
      "userPropertyMap": {
        "SampleStringKey": "String"
      },
      "userAddlPropertyMap": {
        "SampleStringKey": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userInputs` | Teamcenter::Soa::Administration::_2015_07::UserManagement::CreateOrUpdateUserInputs[] | 用户创建或更新的输入信息列表 |

**响应（output）：**

```json
{
  "userObjectMap": {
    "SampleStringKey": {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "person": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "profile": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userObjectMap` | Teamcenter::Soa::Administration::_2015_07::UserManagement::UserObjectsMap | User Id and its corresponding UserObjectStructure which contains User , Person and Fnd0CustomUserProfile objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

### 3.14 API 版本 2016-03

**Service：** UserManagement  **操作数：** 1

##### 3.14.1 deleteUser

**接口路径：** `Administration-2016-03-UserManagement/deleteUser`

**API 版本：** `2016-03`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 从 Teamcenter 中删除 User 对象。可选择同时删除其拥有的对象，或将所有权转移给指定的新用户。需要系统管理员权限。返回成功删除的用户 UID 列表。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2016_03.UserManagement.deleteUser`

**请求（input）：**

```json
{
  "userInput": [
    {
      "userId": "String",
      "newOwningUser": "String",
      "newOwningGroup": "String",
      "deleteObjects": false
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userInput` | Teamcenter::Soa::Administration::_2016_03::UserManagement::DeleteUsersInput[] | 用户删除操作的输入信息 |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.15 API 版本 2016-10

**Service：** UserManagement  **操作数：** 2

##### 3.15.1 getCurrentCountryPageInfo

**接口路径：** `Administration-2016-10-UserManagement/getCurrentCountryPageInfo`

**API 版本：** `2016-10`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 获取当前国家选择页面的配置，包括可选国家列表、默认显示国家及可自定义的保密声明文字。供 RAC 和 AW 客户端渲染国家选择界面使用。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2016_10.UserManagement.getCurrentCountryPageInfo`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "displayCountries": {
    "SampleStringKey": "String"
  },
  "extraInfoOut": {
    "SampleStringKey": "String"
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `displayCountries` | Teamcenter::Soa::Administration::_2016_10::UserManagement::ExtraMappedInfo | Map of key/value pairs (string, string) representing the selectable countries the user may choose when filling out the current country selection page. |
| `extraInfoOut` | Teamcenter::Soa::Administration::_2016_10::UserManagement::ExtraMappedInfo | Map of key/value pairs (string, string). Key: initialCountry . The initial value displayed in the current country pick list. The format is ISO 3166-1  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.15.2 saveAndValidateCurrentCountry

**接口路径：** `Administration-2016-10-UserManagement/saveAndValidateCurrentCountry`

**API 版本：** `2016-10`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 保存当前会话用户选择的国家，并校验该用户是否违反全球许可协议。即使校验失败，国家仍会被保存。此操作不可传入 null 值。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2016_10.UserManagement.saveAndValidateCurrentCountry`

**请求（input）：**

```json
{
  "selectedcountry": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `selectedcountry` | std::string | 用户选择的国家代码 |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.16 API 版本 2017-05

**Service：** GroupManagement、RoleManagement、UserManagement  **操作数：** 5

##### 3.16.1 addChildGroups

**接口路径：** `Administration-2017-05-GroupManagement/addChildGroups`

**API 版本：** `2017-05`  
**Service：** `GroupManagement`  
**Library：** `Administration`

**功能说明：** 向指定 Group 对象添加子组。如果子组不存在则先创建再添加。新建的 Group 对象在 ServiceData 的 created 列表中返回，被修改的父组在 modified 列表中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2017_05.GroupManagement.addChildGroups`

**请求（input）：**

```json
{
  "childGroupsToGroupStructs": [
    {
      "clientId": "String",
      "groupsToAdd": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "groupsToCreateAndAdd": [
        {
          "name": "String",
          "description": "String",
          "privilege": false,
          "localVolume": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "security": "String",
          "volume": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "parentGroup": {
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
| `childGroupsToGroupStructs` | Teamcenter::Soa::Administration::_2017_05::GroupManagement::AddChildGroupsToGroupStructure[] | 父组与子组关系列表，子组可新建或已有 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.16.2 addRolesToGroup

**接口路径：** `Administration-2017-05-RoleManagement/addRolesToGroup`

**API 版本：** `2017-05`  
**Service：** `RoleManagement`  
**Library：** `Administration`

**功能说明：** 向指定 Group 对象添加角色（Role）。若角色不存在则先创建。新建角色在 ServiceData 的 created 列表中返回，被修改的 Group 在 modified 列表中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2017_05.RoleManagement.addRolesToGroup`

**请求（input）：**

```json
{
  "roleGroupStructs": [
    {
      "clientId": "String",
      "rolesToAdd": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "rolesToCreateAndAdd": [
        {
          "roleName": "String",
          "roleDescription": "String"
        }
      ],
      "grp": {
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
| `roleGroupStructs` | Teamcenter::Soa::Administration::_2017_05::RoleManagement::AddRolesToGroupStructure[] | 角色与组的关联关系列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.16.3 removeRolesFromGroup

**接口路径：** `Administration-2017-05-RoleManagement/removeRolesFromGroup`

**API 版本：** `2017-05`  
**Service：** `RoleManagement`  
**Library：** `Administration`

**功能说明：** 从指定 Group 对象中移除指定角色（Role）。被修改的 Group 对象在 ServiceData 的 modified 列表中返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2017_05.RoleManagement.removeRolesFromGroup`

**请求（input）：**

```json
{
  "roleGroupStructs": [
    {
      "roles": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "grp": {
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
| `roleGroupStructs` | Teamcenter::Soa::Administration::_2017_05::RoleManagement::RoleGroupStructure[] | 角色与组的关联关系列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.16.4 addUsersAsGroupMembers

**接口路径：** `Administration-2017-05-UserManagement/addUsersAsGroupMembers`

**API 版本：** `2017-05`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 将用户（新建或已有）作为 GroupMember 添加到指定 Group 和 Role 下。若用户不存在则先创建。需要系统管理员或组管理员权限。Role 对象不存在时返回错误。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2017_05.UserManagement.addUsersAsGroupMembers`

**请求（input）：**

```json
{
  "userRoleGroupStructs": [
    {
      "clientId": "String",
      "usersToAdd": [
        {
          "user": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "userAttributes": {
            "isGroupAdmin": false,
            "status": false,
            "isDefaultRole": false
          }
        }
      ],
      "usersToCreateAndAdd": [
        {
          "user": {
            "userId": "String",
            "person": "String",
            "password": "String",
            "defaultGroup": "String",
            "newOwner": "String",
            "newOwningGroup": "String",
            "userPropertyMap": {
              "SampleStringKey": "String"
            },
            "userAddlPropertyMap": {
              "SampleStringKey": "String"
            }
          },
          "userAttributes": {
            "isGroupAdmin": false,
            "status": false,
            "isDefaultRole": false
          }
        }
      ],
      "grp": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "role": {
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
| `userRoleGroupStructs` | Teamcenter::Soa::Administration::_2017_05::UserManagement::AddUsersAsGroupMembersStructure[] | 用户、角色、组的关联关系列表 |

**响应（output）：**

```json
"IServiceData"
```

---

##### 3.16.5 removeGroupMembers

**接口路径：** `Administration-2017-05-UserManagement/removeGroupMembers`

**API 版本：** `2017-05`  
**Service：** `UserManagement`  
**Library：** `Administration`

**功能说明：** 从指定 Group 和 Role 下移除 GroupMember。需要系统管理员或组管理员权限。输入不可包含 null 的 User、Group 或 Role。结果以结构体列表形式返回。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2017_05.UserManagement.removeGroupMembers`

**请求（input）：**

```json
{
  "userRoleGroupStructs": [
    {
      "users": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "grp": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "role": {
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
| `userRoleGroupStructs` | Teamcenter::Soa::Administration::_2017_05::UserManagement::UserRoleGroupStructure[] | 用户、角色、组的关联关系列表 |

**响应（output）：**

```json
{
  "userRoleGrpStructs": [
    {
      "users": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "grp": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "role": {
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
| `userRoleGrpStructs` | Teamcenter::Soa::Administration::_2017_05::UserManagement::UserRoleGroupStructure[] | A list of structures of User and associated Role and Group objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

### 3.17 API 版本 2018-11

**Service：** IRM、OrganizationManagement  **操作数：** 4

##### 3.17.1 getSessionInfoFromTicket

**接口路径：** `Administration-2018-11-IRM/getSessionInfoFromTicket`

**API 版本：** `2018-11`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 凭借 `getSessionInfoTicket` 返回的加密 Ticket 字符串，还原并返回会话信息（用户、组、角色、项目团队、许可证等键值对）。Ticket 有效期内可重复使用。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2018_11.IRM.getSessionInfoFromTicket`

**请求（input）：**

```json
{
  "sessionInfoTicket": "String"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `sessionInfoTicket` | std::string | 由 getSessionInfoTicket 返回的加密会话票据字符串 |

**响应（output）：**

```json
{
  "userInfo": {
    "SampleStringKey": "String"
  },
  "sessionValues": {
    "SampleStringKey": "String"
  },
  "siteId": 0,
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userInfo` | Teamcenter::Soa::Administration::_2018_11::IRM::UserInfo | User login information, like: userId, userUid, groupName, groupUid, roleName, roleUid, projectId, projectUid |
| `sessionValues` | Teamcenter::Soa::Administration::_2018_11::IRM::SessionValuesMap2 | sessionValues |
| `siteId` | int | Site identifier that generated the ticket. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.17.2 getSessionInfoTicket

**接口路径：** `Administration-2018-11-IRM/getSessionInfoTicket`

**API 版本：** `2018-11`  
**Service：** `IRM`  
**Library：** `Administration`

**功能说明：** 将当前会话的用户、组、会话信息、站点标识和过期时间打包成加密字符串（Ticket）返回，供无用户概念的系统（如 VDS）以此 Ticket 向 TC 查询会话信息。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2018_11.IRM.getSessionInfoTicket`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "sessionInfoTicket": "String",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `sessionInfoTicket` | std::string | 由 getSessionInfoTicket 返回的加密会话票据字符串 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.17.3 getUserConsentStatement

**接口路径：** `Administration-2018-11-OrganizationManagement/getUserConsentStatement`

**API 版本：** `2018-11`  
**Service：** `OrganizationManagement`  
**Library：** `Administration`

**功能说明：** 返回当前登录用户所在区域（locale）的用户同意声明（GDPR）。若该区域无对应声明，则返回主区域（master locale）的声明。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2018_11.OrganizationManagement.getUserConsentStatement`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "consentStatement": "String",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `consentStatement` | std::string | 返回的用户同意声明文本 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData，包含创建/修改/删除对象列表及错误信息 |

---

##### 3.17.4 recordUserConsent

**接口路径：** `Administration-2018-11-OrganizationManagement/recordUserConsent`

**API 版本：** `2018-11`  
**Service：** `OrganizationManagement`  
**Library：** `Administration`

**功能说明：** 记录用户对通用数据保护条例（GDPR）的同意操作。若底层函数调用出现问题，可能返回部分错误（partial errors）。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2018_11.OrganizationManagement.recordUserConsent`

**请求（input）：**

```json
{
  "userConsent": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `userConsent` | bool | 用户同意信息，包含同意声明版本等 |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.18 API 版本 2020-12

**Service：** PreferenceManagement  **操作数：** 1

##### 3.18.1 refreshPreferences2

**接口路径：** `Administration-2020-12-PreferenceManagement/refreshPreferences2`

**API 版本：** `2020-12`  
**Service：** `PreferenceManagement`  
**Library：** `Administration`

**功能说明：** `refreshPreferences` 的增强版：先刷新指定偏好的服务器缓存，再按当前用户和应用上下文返回最新值。支持按名称列表精确刷新。

**Soa Inclusion：** `Teamcenter.Soa.Administration._2020_12.PreferenceManagement.refreshPreferences2`

**请求（input）：**

```json
{
  "preferenceNames": [
    "String"
  ],
  "includePreferenceDescriptions": false
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `preferenceNames` | std::string[] | 偏好名称列表；为空或首元素为 * 时返回全部偏好 |
| `includePreferenceDescriptions` | bool | 是否在结果中包含偏好描述信息 |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "response": [
    {
      "definition": {
        "name": "String",
        "category": "String",
        "description": "String",
        "type": 0,
        "isArray": false,
        "isDisabled": false,
        "protectionScope": "String",
        "isEnvEnabled": false,
        "isOOTBPreference": false
      },
      "values": {
        "values": [
          "String"
        ],
        "valueOrigination": "String"
      }
    }
  ]
}
```

| 字段 | 类型 | 说明 |
|------|------|------|
| `data` | Teamcenter::Soa::Server::ServiceData | Contains the partial errors in the same order as in the input list. |
| `response` | Teamcenter::Soa::Administration::_2012_09::PreferenceManagement::CompletePreference[] | A list of complete preference information. Each structure holds all the preference definition ( PreferenceDefinition structure) and its values ( Prefe |

---

---

## 4. 附录

### 全量操作索引

| API 版本 | Service | 操作 | Url | Soa Inclusion |
|----------|---------|------|-----|---------------|
| 2006-03 | IRM | `checkAccessorsPrivileges` | `Administration-2006-03-IRM/checkAccessorsPrivileges` | `Teamcenter.Soa.Administration._2006_03.IRM.checkAccessorsPrivileges` |
| 2006-03 | IRM | `getEffectiveACLInfo` | `Administration-2006-03-IRM/getEffectiveACLInfo` | `Teamcenter.Soa.Administration._2006_03.IRM.getEffectiveACLInfo` |
| 2006-03 | IRM | `getExtraProtectionInfo` | `Administration-2006-03-IRM/getExtraProtectionInfo` | `Teamcenter.Soa.Administration._2006_03.IRM.getExtraProtectionInfo` |
| 2006-03 | IRM | `removeAccessor` | `Administration-2006-03-IRM/removeAccessor` | `Teamcenter.Soa.Administration._2006_03.IRM.removeAccessor` |
| 2006-03 | IRM | `setPrivileges` | `Administration-2006-03-IRM/setPrivileges` | `Teamcenter.Soa.Administration._2006_03.IRM.setPrivileges` |
| 2007-01 | UserManagement | `createDisciplines` | `Administration-2007-01-UserManagement/createDisciplines` | `Teamcenter.Soa.Administration._2007_01.UserManagement.createDisciplines` |
| 2007-06 | Authorization | `checkAuthorization` | `Administration-2007-06-Authorization/checkAuthorization` | `Teamcenter.Soa.Administration._2007_06.Authorization.checkAuthorization` |
| 2007-06 | PreferenceManagement | `setPreferences` | `Administration-2007-06-PreferenceManagement/setPreferences` | `Teamcenter.Soa.Administration._2007_06.PreferenceManagement.setPreferences` |
| 2008-03 | IRM | `activateUsers` | `Administration-2008-03-IRM/activateUsers` | `Teamcenter.Soa.Administration._2008_03.IRM.activateUsers` |
| 2008-03 | IRM | `deactivateUsers` | `Administration-2008-03-IRM/deactivateUsers` | `Teamcenter.Soa.Administration._2008_03.IRM.deactivateUsers` |
| 2008-06 | PreferenceManagement | `lockSitePreferences` | `Administration-2008-06-PreferenceManagement/lockSitePreferences` | `Teamcenter.Soa.Administration._2008_06.PreferenceManagement.lockSitePreferences` |
| 2008-06 | PreferenceManagement | `unlockSitePreferences` | `Administration-2008-06-PreferenceManagement/unlockSitePreferences` | `Teamcenter.Soa.Administration._2008_06.PreferenceManagement.unlockSitePreferences` |
| 2008-12 | Authorization | `checkAuthorizationAccess` | `Administration-2008-12-Authorization/checkAuthorizationAccess` | `Teamcenter.Soa.Administration._2008_12.Authorization.checkAuthorizationAccess` |
| 2010-04 | DisciplineManagement | `getDiscipline` | `Administration-2010-04-DisciplineManagement/getDiscipline` | `Teamcenter.Soa.Administration._2010_04.DisciplineManagement.getDiscipline` |
| 2010-04 | IRM | `getAccessorTypes` | `Administration-2010-04-IRM/getAccessorTypes` | `Teamcenter.Soa.Administration._2010_04.IRM.getAccessorTypes` |
| 2010-04 | IRM | `getEffectiveACLInfo2` | `Administration-2010-04-IRM/getEffectiveACLInfo2` | `Teamcenter.Soa.Administration._2010_04.IRM.getEffectiveACLInfo2` |
| 2010-04 | IRM | `getExtraProtectionInfo2` | `Administration-2010-04-IRM/getExtraProtectionInfo2` | `Teamcenter.Soa.Administration._2010_04.IRM.getExtraProtectionInfo2` |
| 2010-04 | IRM | `getPrivilegeNames` | `Administration-2010-04-IRM/getPrivilegeNames` | `Teamcenter.Soa.Administration._2010_04.IRM.getPrivilegeNames` |
| 2011-05 | PreferenceManagement | `refreshPreferences` | `Administration-2011-05-PreferenceManagement/refreshPreferences` | `Teamcenter.Soa.Administration._2011_05.PreferenceManagement.refreshPreferences` |
| 2012-09 | PreferenceManagement | `deletePreferenceDefinitions` | `Administration-2012-09-PreferenceManagement/deletePreferenceDefinitions` | `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.deletePreferenceDefinitions` |
| 2012-09 | PreferenceManagement | `deletePreferencesAtLocations` | `Administration-2012-09-PreferenceManagement/deletePreferencesAtLocations` | `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.deletePreferencesAtLocations` |
| 2012-09 | PreferenceManagement | `getPreferences` | `Administration-2012-09-PreferenceManagement/getPreferences` | `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.getPreferences` |
| 2012-09 | PreferenceManagement | `getPreferencesAtLocations` | `Administration-2012-09-PreferenceManagement/getPreferencesAtLocations` | `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.getPreferencesAtLocations` |
| 2012-09 | PreferenceManagement | `importPreferencesAtLocationDryRun` | `Administration-2012-09-PreferenceManagement/importPreferencesAtLocationDryRun` | `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.importPreferencesAtLocationDryRun` |
| 2012-09 | PreferenceManagement | `importPreferencesAtLocations` | `Administration-2012-09-PreferenceManagement/importPreferencesAtLocations` | `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.importPreferencesAtLocations` |
| 2012-09 | PreferenceManagement | `removeStalePreferenceInstancesAtLocations` | `Administration-2012-09-PreferenceManagement/removeStalePreferenceInstancesAtLocations` | `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.removeStalePreferenceInstancesAtLocations` |
| 2012-09 | PreferenceManagement | `setPreferences2` | `Administration-2012-09-PreferenceManagement/setPreferences2` | `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.setPreferences2` |
| 2012-09 | PreferenceManagement | `setPreferencesAtLocations` | `Administration-2012-09-PreferenceManagement/setPreferencesAtLocations` | `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.setPreferencesAtLocations` |
| 2012-09 | PreferenceManagement | `setPreferencesDefinition` | `Administration-2012-09-PreferenceManagement/setPreferencesDefinition` | `Teamcenter.Soa.Administration._2012_09.PreferenceManagement.setPreferencesDefinition` |
| 2012-09 | UserManagement | `getUserGroupMembers` | `Administration-2012-09-UserManagement/getUserGroupMembers` | `Teamcenter.Soa.Administration._2012_09.UserManagement.getUserGroupMembers` |
| 2012-09 | UserManagement | `setGroupMemberProperties` | `Administration-2012-09-UserManagement/setGroupMemberProperties` | `Teamcenter.Soa.Administration._2012_09.UserManagement.setGroupMemberProperties` |
| 2012-10 | IRM | `getAMImpactedObjects` | `Administration-2012-10-IRM/getAMImpactedObjects` | `Teamcenter.Soa.Administration._2012_10.IRM.getAMImpactedObjects` |
| 2012-10 | IRM | `getSessionValues` | `Administration-2012-10-IRM/getSessionValues` | `Teamcenter.Soa.Administration._2012_10.IRM.getSessionValues` |
| 2014-10 | UserManagement | `makeUser` | `Administration-2014-10-UserManagement/makeUser` | `Teamcenter.Soa.Administration._2014_10.UserManagement.makeUser` |
| 2015-03 | UserManagement | `setUserProfileProperties` | `Administration-2015-03-UserManagement/setUserProfileProperties` | `Teamcenter.Soa.Administration._2015_03.UserManagement.setUserProfileProperties` |
| 2015-07 | UserManagement | `createOrUpdateUser` | `Administration-2015-07-UserManagement/createOrUpdateUser` | `Teamcenter.Soa.Administration._2015_07.UserManagement.createOrUpdateUser` |
| 2016-03 | UserManagement | `deleteUser` | `Administration-2016-03-UserManagement/deleteUser` | `Teamcenter.Soa.Administration._2016_03.UserManagement.deleteUser` |
| 2016-10 | UserManagement | `getCurrentCountryPageInfo` | `Administration-2016-10-UserManagement/getCurrentCountryPageInfo` | `Teamcenter.Soa.Administration._2016_10.UserManagement.getCurrentCountryPageInfo` |
| 2016-10 | UserManagement | `saveAndValidateCurrentCountry` | `Administration-2016-10-UserManagement/saveAndValidateCurrentCountry` | `Teamcenter.Soa.Administration._2016_10.UserManagement.saveAndValidateCurrentCountry` |
| 2017-05 | GroupManagement | `addChildGroups` | `Administration-2017-05-GroupManagement/addChildGroups` | `Teamcenter.Soa.Administration._2017_05.GroupManagement.addChildGroups` |
| 2017-05 | RoleManagement | `addRolesToGroup` | `Administration-2017-05-RoleManagement/addRolesToGroup` | `Teamcenter.Soa.Administration._2017_05.RoleManagement.addRolesToGroup` |
| 2017-05 | RoleManagement | `removeRolesFromGroup` | `Administration-2017-05-RoleManagement/removeRolesFromGroup` | `Teamcenter.Soa.Administration._2017_05.RoleManagement.removeRolesFromGroup` |
| 2017-05 | UserManagement | `addUsersAsGroupMembers` | `Administration-2017-05-UserManagement/addUsersAsGroupMembers` | `Teamcenter.Soa.Administration._2017_05.UserManagement.addUsersAsGroupMembers` |
| 2017-05 | UserManagement | `removeGroupMembers` | `Administration-2017-05-UserManagement/removeGroupMembers` | `Teamcenter.Soa.Administration._2017_05.UserManagement.removeGroupMembers` |
| 2018-11 | IRM | `getSessionInfoFromTicket` | `Administration-2018-11-IRM/getSessionInfoFromTicket` | `Teamcenter.Soa.Administration._2018_11.IRM.getSessionInfoFromTicket` |
| 2018-11 | IRM | `getSessionInfoTicket` | `Administration-2018-11-IRM/getSessionInfoTicket` | `Teamcenter.Soa.Administration._2018_11.IRM.getSessionInfoTicket` |
| 2018-11 | OrganizationManagement | `getUserConsentStatement` | `Administration-2018-11-OrganizationManagement/getUserConsentStatement` | `Teamcenter.Soa.Administration._2018_11.OrganizationManagement.getUserConsentStatement` |
| 2018-11 | OrganizationManagement | `recordUserConsent` | `Administration-2018-11-OrganizationManagement/recordUserConsent` | `Teamcenter.Soa.Administration._2018_11.OrganizationManagement.recordUserConsent` |
| 2020-12 | PreferenceManagement | `refreshPreferences2` | `Administration-2020-12-PreferenceManagement/refreshPreferences2` | `Teamcenter.Soa.Administration._2020_12.PreferenceManagement.refreshPreferences2` |

### 典型调用流程

**偏好管理（查询 → 修改）：**
1. `getPreferences` — 获取当前用户可见的偏好值
2. `setPreferences2` — 更新当前用户的偏好值
3. `refreshPreferences2` — 刷新缓存并验证最新值

**用户生命周期管理：**
1. `createOrUpdateUser` — 创建或更新用户（需系统管理员）
2. `addUsersAsGroupMembers` — 将用户加入指定组/角色
3. `activateUsers` — 激活用户（按许可证检查）
4. `setGroupMemberProperties` — 配置 GroupMember 属性
5. `deleteUser` — 删除用户并转移对象所有权

**权限检查（IRM）：**
1. `getAccessorTypes` — 获取所有 Accessor 类型
2. `getPrivilegeNames` — 获取所有权限名称
3. `getEffectiveACLInfo2` — 获取业务对象有效 ACL
4. `checkAccessorsPrivileges` — 检查 GroupMember 权限裁决

### 重新生成

```bash
node generate-admin-doc.js
```
