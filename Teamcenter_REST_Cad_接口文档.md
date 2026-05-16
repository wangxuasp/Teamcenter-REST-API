# Teamcenter SOA API — Cad 接口文档（TC 2512）

> 本文档汇总 **Cad** Library 下**全部 API 版本（年-月）**的 SOA 操作，已按版本与 Service 双向合并整理。
> 数据来源：TC 2512 SOA Api Browser（`structure.js`）。
>
> - **API 版本数：** 21 个（`2007-01` ～ `2025-06`）
> - **操作条目数：** 70 个（含同名操作的多版本定义 **8** 组）
> - **独立操作名：** 50 个
> - **Url 格式：** `Cad-{Year}-{Service}/{operation}`

---

## 目录

1. [API 版本总览](#1-api-版本总览)
2. [按 Service 合并（跨版本）](#2-按-service-合并跨版本)
3. [按 API 版本（年-月）归档](#3-按-api-版本年-月归档)
4. [同名操作多版本对照](#4-同名操作多版本对照)
5. [附录](#5-附录)

---

## 1. API 版本总览

Cad 库涵盖 **3** 个 Service、**21** 个年-月 API 契约；StructureManagement 跨版本最多，部分操作在多个版本中并存（接口签名可能不同）。

| API 版本 | Service | 操作 | Url |
|----------|---------|------|-----|
| **2007-01** | DataManagement | `createOrUpdateParts` | `Cad-2007-01-DataManagement/createOrUpdateParts` |
| **2007-01** | DataManagement | `createOrUpdateRelations` | `Cad-2007-01-DataManagement/createOrUpdateRelations` |
| **2007-01** | DataManagement | `expandFoldersForCAD` | `Cad-2007-01-DataManagement/expandFoldersForCAD` |
| **2007-01** | DataManagement | `expandGRMRelations` | `Cad-2007-01-DataManagement/expandGRMRelations` |
| **2007-01** | DataManagement | `expandPrimaryObjects` | `Cad-2007-01-DataManagement/expandPrimaryObjects` |
| **2007-01** | DataManagement | `generateAlternateIds` | `Cad-2007-01-DataManagement/generateAlternateIds` |
| **2007-01** | DataManagement | `getAllAttrMappings` | `Cad-2007-01-DataManagement/getAllAttrMappings` |
| **2007-01** | DataManagement | `getAttrMappingsForDatasetType` | `Cad-2007-01-DataManagement/getAttrMappingsForDatasetType` |
| **2007-01** | DataManagement | `getAvailableTypes` | `Cad-2007-01-DataManagement/getAvailableTypes` |
| **2007-01** | DataManagement | `resolveAttrMappingsForDataset` | `Cad-2007-01-DataManagement/resolveAttrMappingsForDataset` |
| **2007-01** | StructureManagement | `closeBOMWindows` | `Cad-2007-01-StructureManagement/closeBOMWindows` |
| **2007-01** | StructureManagement | `createBOMWindows` | `Cad-2007-01-StructureManagement/createBOMWindows` |
| **2007-01** | StructureManagement | `createOrUpdateAbsoluteStructure` | `Cad-2007-01-StructureManagement/createOrUpdateAbsoluteStructure` |
| **2007-01** | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2007-01-StructureManagement/createOrUpdateRelativeStructure` |
| **2007-01** | StructureManagement | `deleteAssemblyArrangements` | `Cad-2007-01-StructureManagement/deleteAssemblyArrangements` |
| **2007-01** | StructureManagement | `deleteRelativeStructure` | `Cad-2007-01-StructureManagement/deleteRelativeStructure` |
| **2007-01** | StructureManagement | `expandPSAllLevels` | `Cad-2007-01-StructureManagement/expandPSAllLevels` |
| **2007-01** | StructureManagement | `expandPSOneLevel` | `Cad-2007-01-StructureManagement/expandPSOneLevel` |
| **2007-01** | StructureManagement | `getRevisionRules` | `Cad-2007-01-StructureManagement/getRevisionRules` |
| **2007-01** | StructureManagement | `getVariantRules` | `Cad-2007-01-StructureManagement/getVariantRules` |
| **2007-06** | StructureManagement | `createOrUpdateClassicOptions` | `Cad-2007-06-StructureManagement/createOrUpdateClassicOptions` |
| **2007-06** | StructureManagement | `createOrUpdateVariantConditions` | `Cad-2007-06-StructureManagement/createOrUpdateVariantConditions` |
| **2007-06** | StructureManagement | `deleteClassicOptions` | `Cad-2007-06-StructureManagement/deleteClassicOptions` |
| **2007-06** | StructureManagement | `deleteVariantConditions` | `Cad-2007-06-StructureManagement/deleteVariantConditions` |
| **2007-06** | StructureManagement | `getConfiguredItemRevision` | `Cad-2007-06-StructureManagement/getConfiguredItemRevision` |
| **2007-09** | StructureManagement | `createOrUpdateVariantConditions2` | `Cad-2007-09-StructureManagement/createOrUpdateVariantConditions2` |
| **2007-12** | DataManagement | `createOrUpdateParts` | `Cad-2007-12-DataManagement/createOrUpdateParts` |
| **2007-12** | StructureManagement | `createOrUpdateAbsoluteStructure` | `Cad-2007-12-StructureManagement/createOrUpdateAbsoluteStructure` |
| **2007-12** | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2007-12-StructureManagement/createOrUpdateRelativeStructure` |
| **2007-12** | StructureManagement | `deleteAssemblyArrangements` | `Cad-2007-12-StructureManagement/deleteAssemblyArrangements` |
| **2007-12** | StructureManagement | `deleteRelativeStructure` | `Cad-2007-12-StructureManagement/deleteRelativeStructure` |
| **2007-12** | StructureManagement | `queryClassicOptions` | `Cad-2007-12-StructureManagement/queryClassicOptions` |
| **2007-12** | StructureManagement | `queryVariantConditions` | `Cad-2007-12-StructureManagement/queryVariantConditions` |
| **2008-03** | DataManagement | `createOrUpdateParts` | `Cad-2008-03-DataManagement/createOrUpdateParts` |
| **2008-03** | DataManagement | `resolveAttrMappings` | `Cad-2008-03-DataManagement/resolveAttrMappings` |
| **2008-03** | StructureManagement | `askChildPathBOMLines` | `Cad-2008-03-StructureManagement/askChildPathBOMLines` |
| **2008-06** | DataManagement | `createOrUpdateParts` | `Cad-2008-06-DataManagement/createOrUpdateParts` |
| **2008-06** | DataManagement | `expandFoldersForCAD` | `Cad-2008-06-DataManagement/expandFoldersForCAD` |
| **2008-06** | StructureManagement | `createOrUpdateAbsoluteStructure` | `Cad-2008-06-StructureManagement/createOrUpdateAbsoluteStructure` |
| **2008-06** | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2008-06-StructureManagement/createOrUpdateRelativeStructure` |
| **2008-06** | StructureManagement | `createVariantRules` | `Cad-2008-06-StructureManagement/createVariantRules` |
| **2008-06** | StructureManagement | `deleteRelativeStructure` | `Cad-2008-06-StructureManagement/deleteRelativeStructure` |
| **2008-06** | StructureManagement | `expandPSAllLevels` | `Cad-2008-06-StructureManagement/expandPSAllLevels` |
| **2008-06** | StructureManagement | `expandPSOneLevel` | `Cad-2008-06-StructureManagement/expandPSOneLevel` |
| **2008-06** | StructureManagement | `getAbsoluteStructureData` | `Cad-2008-06-StructureManagement/getAbsoluteStructureData` |
| **2008-06** | StructureManagement | `reconfigureBOMWindows` | `Cad-2008-06-StructureManagement/reconfigureBOMWindows` |
| **2008-06** | StructureManagement | `saveBOMWindows` | `Cad-2008-06-StructureManagement/saveBOMWindows` |
| **2009-04** | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2009-04-StructureManagement/createOrUpdateRelativeStructure` |
| **2010-09** | DataManagement | `createOrUpdateParts` | `Cad-2010-09-DataManagement/createOrUpdateParts` |
| **2011-06** | DataManagement | `getAllAttrMappings2` | `Cad-2011-06-DataManagement/getAllAttrMappings2` |
| **2012-09** | DataManagement | `createOrUpdateParts` | `Cad-2012-09-DataManagement/createOrUpdateParts` |
| **2013-05** | StructureManagement | `askChildPathBOMLines2` | `Cad-2013-05-StructureManagement/askChildPathBOMLines2` |
| **2013-05** | StructureManagement | `createBOMWindows2` | `Cad-2013-05-StructureManagement/createBOMWindows2` |
| **2013-05** | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2013-05-StructureManagement/createOrUpdateRelativeStructure` |
| **2014-10** | DataManagement | `getAttrMappings` | `Cad-2014-10-DataManagement/getAttrMappings` |
| **2016-03** | DataManagement | `createOrUpdateModelViewPalette` | `Cad-2016-03-DataManagement/createOrUpdateModelViewPalette` |
| **2016-03** | DataManagement | `createOrUpdateModelViewProxies` | `Cad-2016-03-DataManagement/createOrUpdateModelViewProxies` |
| **2016-03** | StructureManagement | `findModelViewsInStructure` | `Cad-2016-03-StructureManagement/findModelViewsInStructure` |
| **2016-09** | StructureManagement | `continueFindModelViews` | `Cad-2016-09-StructureManagement/continueFindModelViews` |
| **2016-09** | StructureManagement | `continueReconcilePalette` | `Cad-2016-09-StructureManagement/continueReconcilePalette` |
| **2016-09** | StructureManagement | `startFindModelViews` | `Cad-2016-09-StructureManagement/startFindModelViews` |
| **2016-09** | StructureManagement | `startReconcilePalette` | `Cad-2016-09-StructureManagement/startReconcilePalette` |
| **2018-06** | StructureManagement | `writeAssemblyConfigurationDetails` | `Cad-2018-06-StructureManagement/writeAssemblyConfigurationDetails` |
| **2019-06** | StructureManagement | `createOrReConfigureBOMWindows` | `Cad-2019-06-StructureManagement/createOrReConfigureBOMWindows` |
| **2020-01** | AppSessionManagement | `createOrUpdateSavedSession` | `Cad-2020-01-AppSessionManagement/createOrUpdateSavedSession` |
| **2020-01** | AppSessionManagement | `openSavedSession` | `Cad-2020-01-AppSessionManagement/openSavedSession` |
| **2023-06** | StructureManagement | `expandPSOneLevel2` | `Cad-2023-06-StructureManagement/expandPSOneLevel2` |
| **2023-12** | StructureManagement | `createOrUpdateAbsoluteStructure` | `Cad-2023-12-StructureManagement/createOrUpdateAbsoluteStructure` |
| **2024-12** | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2024-12-StructureManagement/createOrUpdateRelativeStructure` |
| **2025-06** | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2025-06-StructureManagement/createOrUpdateRelativeStructure` |

### 版本—Service 对照

| API 版本 | 包含的 Service | 操作数 |
|----------|----------------|--------|
| 2007-01 | DataManagement、StructureManagement | 20 |
| 2007-06 | StructureManagement | 5 |
| 2007-09 | StructureManagement | 1 |
| 2007-12 | DataManagement、StructureManagement | 7 |
| 2008-03 | DataManagement、StructureManagement | 3 |
| 2008-06 | DataManagement、StructureManagement | 11 |
| 2009-04 | StructureManagement | 1 |
| 2010-09 | DataManagement | 1 |
| 2011-06 | DataManagement | 1 |
| 2012-09 | DataManagement | 1 |
| 2013-05 | StructureManagement | 3 |
| 2014-10 | DataManagement | 1 |
| 2016-03 | DataManagement、StructureManagement | 3 |
| 2016-09 | StructureManagement | 4 |
| 2018-06 | StructureManagement | 1 |
| 2019-06 | StructureManagement | 1 |
| 2020-01 | AppSessionManagement | 2 |
| 2023-06 | StructureManagement | 1 |
| 2023-12 | StructureManagement | 1 |
| 2024-12 | StructureManagement | 1 |
| 2025-06 | StructureManagement | 1 |

### Service—版本覆盖

| Service | 涵盖 API 版本 | 操作条目数 |
|---------|---------------|------------|
| AppSessionManagement | 2020-01 | 2 |
| DataManagement | 2007-01、2007-12、2008-03、2008-06、2010-09、2011-06、2012-09、2014-10、2016-03 | 21 |
| StructureManagement | 2007-01、2007-06、2007-09、2007-12、2008-03、2008-06、2009-04、2013-05、2016-03、2016-09、2018-06、2019-06、2023-06、2023-12、2024-12、2025-06 | 47 |

---

## 2. 按 Service 合并（跨版本）

同一 Service 下按 **API 版本（年-月）** 分组；同名操作若存在于多个版本，在各版本小节中分别列出。

### 2.1 应用会话管理（AppSessionManagement）

**涵盖 API 版本：** `2020-01`  
**操作条目数：** 2

#### 版本 2020-01

##### 2.1.1.1 createOrUpdateSavedSession

**接口路径：** `Cad-2020-01-AppSessionManagement/createOrUpdateSavedSession`

**API 版本：** `2020-01`  
**Service：** `AppSessionManagement`  
**Library：** `Cad`

**说明：** 创建或更新已保存会话（Saved Session）数据模型，记录产品结构配置规则、非结构对象引用等，供 CAD 集成会话恢复使用。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2020_01.AppSessionManagement.createOrUpdateSavedSession`

**请求（input）：**

```json
{
  "sessionsToCreateOrUpdate": [
    {
      "clientId": "",
      "sessionToCreateOrUpdate": {
        "objectToCreate": {
          "creInp": {
            "boName": "",
            "propertyNameValues": {},
            "compoundCreateInput": {}
          },
          "relationName": "",
          "relateToObject": {
            "uid": "",
            "type": "",
            "className": ""
          }
        },
        "objectToUpdate": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lmdOfObject": "0001-01-01T00:00:00",
        "overwriteForLastModDate": "",
        "objectPropsToUpdate": {}
      },
      "attachObjectsToSession": [
        {
          "clientId": "",
          "baseObjectToCreateOrUpdate": {
            "objectToCreate": {
              "creInp": {
                "boName": "",
                "propertyNameValues": {},
                "compoundCreateInput": {}
              },
              "relationName": "",
              "relateToObject": {
                "uid": "",
                "type": "",
                "className": ""
              }
            },
            "objectToUpdate": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "lmdOfObject": "0001-01-01T00:00:00",
            "overwriteForLastModDate": "",
            "objectPropsToUpdate": {}
          },
          "relationName": "",
          "additionalProps": {},
          "recipe": {
            "structureContextIdentifier": {
              "product": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomViewType": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "configInfo": {
                "revRuleConfigInfo": {
                  "revRule": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "unitNo": "",
                  "date": "0001-01-01T00:00:00",
                  "today": "",
                  "endItem": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "endItemRevision": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "overrideFolders": [
                    {
                      "ruleEntry": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "folder": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    }
                  ]
                },
                "variantRulesOrOptionSets": [
                  {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                ],
                "activeAssemblyArrangement": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "configContext": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "bomWinPropFlagMap": {},
                "effGrpRevList": [
                  {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                ]
              },
              "configOptions": {}
            },
            "occurrenceLists": [
              {
                "resultContext": "",
                "resultObjects": {
                  "lines": [
                    {
                      "uid": "",
                      "type": "",
                      "className": ""
                    }
                  ],
                  "compositePathIdentifiers": [
                    {
                      "pathIdentifiers": [
                        {
                          "identifierPropertyName": "",
                          "resultPathIdentifiers": [
                            ""
                          ]
                        }
                      ]
                    }
                  ]
                }
              }
            ],
            "searchRecipe": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "staticStructureFile": {
              "uid": "",
              "type": "",
              "className": ""
            }
          }
        }
      ],
      "productAndConfigsToCreate": [
        {
          "clientId": "",
          "objsAttachInfos": [
            {
              "clientId": "",
              "baseObjectToCreateOrUpdate": {
                "objectToCreate": {
                  "creInp": {
                    "boName": "",
                    "propertyNameValues": {},
                    "compoundCreateInput": {}
                  },
                  "relationName": "",
                  "relateToObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                },
                "objectToUpdate": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "lmdOfObject": "0001-01-01T00:00:00",
                "overwriteForLastModDate": "",
                "objectPropsToUpdate": {}
              },
              "relationName": "",
              "additionalProps": {},
              "recipe": {
                "structureContextIdentifier": {
                  "product": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "bomViewType": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "configInfo": {
                    "revRuleConfigInfo": {
                      "revRule": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "unitNo": "",
                      "date": "0001-01-01T00:00:00",
                      "today": "",
                      "endItem": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "endItemRevision": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "overrideFolders": [
                        {
                          "ruleEntry": {
                            "uid": "",
                            "type": "",
                            "className": ""
                          },
                          "folder": {
                            "uid": "",
                            "type": "",
                            "className": ""
                          }
                        }
                      ]
                    },
                    "variantRulesOrOptionSets": [
                      {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    ],
                    "activeAssemblyArrangement": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "configContext": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "bomWinPropFlagMap": {},
                    "effGrpRevList": [
                      {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    ]
                  },
                  "configOptions": {}
                },
                "occurrenceLists": [
                  {
                    "resultContext": "",
                    "resultObjects": {
                      "lines": [
                        {
                          "uid": "",
                          "type": "",
                          "className": ""
                        }
                      ],
                      "compositePathIdentifiers": [
                        {
                          "pathIdentifiers": [
                            {
                              "identifierPropertyName": "",
                              "resultPathIdentifiers": [
                                ""
                              ]
                            }
                          ]
                        }
                      ]
                    }
                  }
                ],
                "searchRecipe": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "staticStructureFile": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ],
          "productSessionDataAttachInfos": [
            {
              "clientId": "",
              "sessionData": {
                "objectToCreate": {
                  "creInp": {
                    "boName": "",
                    "propertyNameValues": {},
                    "compoundCreateInput": {}
                  },
                  "relationName": "",
                  "relateToObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                },
                "objectToUpdate": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "lmdOfObject": "0001-01-01T00:00:00",
                "overwriteForLastModDate": "",
                "objectPropsToUpdate": {}
              }
            }
          ],
          "structureRecipe": {
            "structureContextIdentifier": {
              "product": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomViewType": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "configInfo": {
                "revRuleConfigInfo": {
                  "revRule": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "unitNo": "",
                  "date": "0001-01-01T00:00:00",
                  "today": "",
                  "endItem": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "endItemRevision": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "overrideFolders": [
                    {
                      "ruleEntry": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "folder": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    }
                  ]
                },
                "variantRulesOrOptionSets": [
                  {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                ],
                "activeAssemblyArrangement": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "configContext": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "bomWinPropFlagMap": {},
                "effGrpRevList": [
                  {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                ]
              },
              "configOptions": {}
            },
            "occurrenceLists": [
              {
                "resultContext": "",
                "resultObjects": {
                  "lines": [
                    {
                      "uid": "",
                      "type": "",
                      "className": ""
                    }
                  ],
                  "compositePathIdentifiers": [
                    {
                      "pathIdentifiers": [
                        {
                          "identifierPropertyName": "",
                          "resultPathIdentifiers": [
                            ""
                          ]
                        }
                      ]
                    }
                  ]
                }
              }
            ],
            "searchRecipe": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "staticStructureFile": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "structureRecipeProps": {}
        }
      ],
      "productAndConfigsToUpdate": [
        {
          "stableId": "",
          "objsAttachInfos": [
            {
              "clientId": "",
              "baseObjectToCreateOrUpdate": {
                "objectToCreate": {
                  "creInp": {
                    "boName": "",
                    "propertyNameValues": {},
                    "compoundCreateInput": {}
                  },
                  "relationName": "",
                  "relateToObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                },
                "objectToUpdate": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "lmdOfObject": "0001-01-01T00:00:00",
                "overwriteForLastModDate": "",
                "objectPropsToUpdate": {}
              },
              "relationName": "",
              "additionalProps": {},
              "recipe": {
                "structureContextIdentifier": {
                  "product": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "bomViewType": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "configInfo": {
                    "revRuleConfigInfo": {
                      "revRule": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "unitNo": "",
                      "date": "0001-01-01T00:00:00",
                      "today": "",
                      "endItem": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "endItemRevision": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "overrideFolders": [
                        {
                          "ruleEntry": {
                            "uid": "",
                            "type": "",
                            "className": ""
                          },
                          "folder": {
                            "uid": "",
                            "type": "",
                            "className": ""
                          }
                        }
                      ]
                    },
                    "variantRulesOrOptionSets": [
                      {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    ],
                    "activeAssemblyArrangement": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "configContext": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "bomWinPropFlagMap": {},
                    "effGrpRevList": [
                      {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    ]
                  },
                  "configOptions": {}
                },
                "occurrenceLists": [
                  {
                    "resultContext": "",
                    "resultObjects": {
                      "lines": [
                        {
                          "uid": "",
                          "type": "",
                          "className": ""
                        }
                      ],
                      "compositePathIdentifiers": [
                        {
                          "pathIdentifiers": [
                            {
                              "identifierPropertyName": "",
                              "resultPathIdentifiers": [
                                ""
                              ]
                            }
                          ]
                        }
                      ]
                    }
                  }
                ],
                "searchRecipe": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "staticStructureFile": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ],
          "productSessionDataAttachInfos": [
            {
              "clientId": "",
              "sessionData": {
                "objectToCreate": {
                  "creInp": {
                    "boName": "",
                    "propertyNameValues": {},
                    "compoundCreateInput": {}
                  },
                  "relationName": "",
                  "relateToObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                },
                "objectToUpdate": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "lmdOfObject": "0001-01-01T00:00:00",
                "overwriteForLastModDate": "",
                "objectPropsToUpdate": {}
              }
            }
          ],
          "detachObjects": [
            ""
          ],
          "structureRecipeProps": {}
        }
      ],
      "productSessionDataAttachInfos": [
        {
          "clientId": "",
          "sessionData": {
            "objectToCreate": {
              "creInp": {
                "boName": "",
                "propertyNameValues": {},
                "compoundCreateInput": {}
              },
              "relationName": "",
              "relateToObject": {
                "uid": "",
                "type": "",
                "className": ""
              }
            },
            "objectToUpdate": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "lmdOfObject": "0001-01-01T00:00:00",
            "overwriteForLastModDate": "",
            "objectPropsToUpdate": {}
          }
        }
      ],
      "detachObjectOrProductsFromSession": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sessionsToCreateOrUpdate` | Teamcenter::Soa::Cad::_2020_01::AppSessionManagement::SessionInfo[] | A list of <font face="courier" height="10">SessionInfo</font> data structures. Each of the struct element is identified by a unique identifier assigned by the c |

**响应（output）：**

```json
{
  "sessionOutputs": [
    {
      "clientId": "",
      "sessionObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "baseObjectAttachOutputs": [
        {
          "clientId": "",
          "stableId": "",
          "baseObject": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "recipeOfOpenedProductOutputs": [
        {
          "clientId": "",
          "relativeToSessionStableId": "",
          "recipeObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "baseObjectAttachOutputs": [
            {
              "clientId": "",
              "stableId": "",
              "baseObject": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "productSessionDataAttachOutputs": [
            {
              "clientId": "",
              "stableId": "",
              "baseObject": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "productSessionDataAttachOutputs": [
        {
          "clientId": "",
          "stableId": "",
          "baseObject": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sessionOutputs` | Teamcenter::Soa::Cad::_2020_01::AppSessionManagement::CreateOrUpdateSessionOutput[] | A list of objects that were associated to the session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">ServiceData</font> that contains the partial errors if any. |

---

##### 2.1.1.2 openSavedSession

**接口路径：** `Cad-2020-01-AppSessionManagement/openSavedSession`

**API 版本：** `2020-01`  
**Service：** `AppSessionManagement`  
**Library：** `Cad`

**说明：** 打开此前通过 createOrUpdateSavedSession 保存的会话，加载其中的文档与产品结构。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2020_01.AppSessionManagement.openSavedSession`

**请求（input）：**

```json
{
  "sessionsToOpen": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "filter": {
    "relAndTypesFilter": [
      {
        "stableId": "",
        "relationName": "",
        "relatedObjAndNamedRefs": [
          {
            "objectTypeName": "",
            "namedReferenceNames": [
              ""
            ]
          }
        ],
        "namedRefHandler": ""
      }
    ],
    "productStructureFilter": {
      "productStructure": "",
      "outputFilters": {},
      "relativeToSessionStableIds": [
        ""
      ],
      "additionalPropsOnBOMWindow": {}
    },
    "productSessionDataFilter": {
      "stableIds": [
        ""
      ],
      "productSessionDataTypeNames": [
        ""
      ]
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sessionsToOpen` | Teamcenter::BusinessObject[] | A list of <font face="courier" height="10">Teamcenter::BusinessObject</font> session object that are to be opened. Valid session object is <b>Fnd0AppSession</b> |
| `filter` | Teamcenter::Soa::Cad::_2020_01::AppSessionManagement::OpenSavedSessionFilter | The filter to apply on the type of object and product structures that the client application is interested in opening. |

**响应（output）：**

```json
{
  "sessionOutputs": [
    {
      "sessionObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "sessionProductStructures": [
        {
          "stableId": "",
          "bomWindow": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "recipeObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationProperties": {},
          "staticStructureFileTicket": "",
          "relatedObjectInfos": [
            {
              "stableId": "",
              "relatedObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomWindow": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "recipeObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "relationProperties": {},
              "namedRefList": [
                {
                  "namedReferenceType": "",
                  "namedReferenceName": "",
                  "referenceObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "fileTicket": ""
                }
              ]
            }
          ],
          "productSessionDataObjects": [
            {
              "stableId": "",
              "productSessionDataObject": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "relatedObjectInfos": [
        {
          "stableId": "",
          "relatedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "bomWindow": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "recipeObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationProperties": {},
          "namedRefList": [
            {
              "namedReferenceType": "",
              "namedReferenceName": "",
              "referenceObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "fileTicket": ""
            }
          ]
        }
      ],
      "productSessionDataObjects": [
        {
          "stableId": "",
          "productSessionDataObject": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sessionOutputs` | Teamcenter::Soa::Cad::_2020_01::AppSessionManagement::OpenSessionOutput[] | A list of objects and product structures that were associated to the session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">ServiceData</font> that contains the partial errors if any. |

---

### 2.2 数据管理（DataManagement）

**涵盖 API 版本：** `2007-01`、`2007-12`、`2008-03`、`2008-06`、`2010-09`、`2011-06`、`2012-09`、`2014-10`、`2016-03`  
**操作条目数：** 21

#### 版本 2007-01

##### 2.2.1.1 createOrUpdateParts

**接口路径：** `Cad-2007-01-DataManagement/createOrUpdateParts`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "attrList": [
            {
              "name": "",
              "value": ""
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "value": ""
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": ""
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "name": "",
          "description": "",
          "type": "",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": "",
          "createNewVersion": "",
          "namedReferencePreference": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::DataManagement::PartInfo[] | A list of PartInfo structures |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": ""
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

##### 2.2.1.2 createOrUpdateRelations

**接口路径：** `Cad-2007-01-DataManagement/createOrUpdateRelations`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 在已有 Teamcenter 对象之间创建或更新 GRM（一般关系模型）关系。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.createOrUpdateRelations`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "relationType": "",
      "primaryObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "secondaryObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relation": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "userData": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "complete": "",
  "pref": {
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdateRelationsInfo[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>CreateOrUpdateRelationsInfo</font> |
| `complete` | bool | A flag to check whether any existing relations that pass the filter needs to be deleted. |
| `pref` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdateRelationsPref | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>RelationAndTypesFilter2</font> structure. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "relation": {
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
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdateRelationsOutput[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>CreateOrUpdateRelationsOutput</font> |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created or updated by the service and error information. Errors are identified by the <font face=&quot;cou |

---

##### 2.2.1.3 expandFoldersForCAD

**接口路径：** `Cad-2007-01-DataManagement/expandFoldersForCAD`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 为 CAD 客户端按文件夹层次展开对象，返回可在 CAD 环境中打开/集成的对象列表。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.expandFoldersForCAD`

**请求（input）：**

```json
{
  "folders": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "pref": {
    "expItemRev": "",
    "latestNRevs": "",
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `folders` | Teamcenter::Folder[] | A list of input TcEng folders |
| `pref` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandFolderForCADPref | Filter and expand preferences |

**响应（output）：**

```json
{
  "output": [
    {
      "inputFolder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "fstlvlFolders": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "itemsOutput": [
        {
          "outputItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevsOutput": [
            {
              "outputItemRevs": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "outputDatasets": [
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
      "itemRevsOutput": [
        {
          "outputItemRevs": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "outputDatasets": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandFoldersForCADOutput[] | A list of ExpandFoldersForCADOutput which has information about the input folder and folders, items and itemRevs output found under this folder |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and service errors/failure information |

---

##### 2.2.1.4 expandGRMRelations

**接口路径：** `Cad-2007-01-DataManagement/expandGRMRelations`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 按给定关系名称与对方对象类型过滤，展开输入对象的 GRM 关联从属对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.expandGRMRelations`

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
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of object references of objects of interest |
| `pref` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandGRMRelationsPref | A ExpandGRMRelationsPref structure |

**响应（output）：**

```json
{
  "output": [
    {
      "inputObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "otherSideObjData": [
        {
          "otherSideObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "relationName": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandGRMRelationsOutput[] | A list of ExpandGRMRelationsOutput which has information about the input object and it's filtered related object list |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and service errors/failure information |

---

##### 2.2.1.5 expandPrimaryObjects

**接口路径：** `Cad-2007-01-DataManagement/expandPrimaryObjects`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 按给定关系名称与对方对象类型过滤，展开输入对象的主对象侧关联对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.expandPrimaryObjects`

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
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of input TcEng object references and filter and expand preferences |
| `pref` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandPrimaryObjectsPref | A ExpandPrimaryObjectsPref structure |

**响应（output）：**

```json
{
  "output": [
    {
      "inputObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "otherSideObjData": [
        {
          "otherSideObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "relationName": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandPrimaryObjectsOutput[] | A list of ExpandPrimaryObjectsOutput |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | SOA framework object containing objects that were found by the service and service errors/failure information |

---

##### 2.2.1.6 generateAlternateIds

**接口路径：** `Cad-2007-01-DataManagement/generateAlternateIds`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 生成备用编号（Alternate ID）列表。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.generateAlternateIds`

**请求（input）：**

```json
{
  "input": [
    {
      "idContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "pattern": "",
      "altIdType": "",
      "parentAltId": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "count": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2007_01::DataManagement::GenerateAlternateIdsProperties[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>GenerateAlternateIdsProperties</font>. |

**响应（output）：**

```json
{
  "inputIndexToAltId": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputIndexToAltId` | Teamcenter::Soa::Cad::_2007_01::DataManagement::IndexToAltId | Key is the index of the input, data is a list of alternate IDs generated. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data contains any partial errors and exceptions. No objects are created, deleted, modified or returned by this service. |

---

##### 2.2.1.7 getAllAttrMappings

**接口路径：** `Cad-2007-01-DataManagement/getAllAttrMappings`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 获取全部 CAD 属性映射（Attribute Mapping）定义。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.getAllAttrMappings`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "attrMappingInfos": [
    {
      "cadAttrMappingDefinition": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propDesc": {
        "propName": "",
        "displayName": "",
        "isModifiable": "",
        "attachedSpecifier": "",
        "maxLength": "",
        "interdependentProps": [
          ""
        ],
        "defaultValue": "",
        "propValueType": "",
        "propType": "",
        "isDisplayable": "",
        "isArray": "",
        "lov": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isRequired": "",
        "isEnabled": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `attrMappingInfos` | Teamcenter::Soa::Cad::_2007_01::DataManagement::AttrMappingInfo[] | A list of AttrMappingInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. CadAttrMappingDefinitio |

---

##### 2.2.1.8 getAttrMappingsForDatasetType

**接口路径：** `Cad-2007-01-DataManagement/getAttrMappingsForDatasetType`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 获取指定数据集类型（及 Item 类型组合）的 CAD 属性映射定义。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.getAttrMappingsForDatasetType`

**请求（input）：**

```json
{
  "info": [
    {
      "datasetTypeName": "",
      "itemTypeName": "",
      "exact": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::DataManagement::GetAttrMappingsForDatasetTypeCriteria[] | A list of dataset and item types used to get a specific set of attribute mapping definitions from the all of the attribute mapping definitions in Teamcenter. |

**响应（output）：**

```json
{
  "output": [
    {
      "criteria": {
        "datasetTypeName": "",
        "itemTypeName": "",
        "exact": ""
      },
      "attrMappingInfos": [
        {
          "cadAttrMappingDefinition": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "propDesc": {
            "propName": "",
            "displayName": "",
            "isModifiable": "",
            "attachedSpecifier": "",
            "maxLength": "",
            "interdependentProps": [
              ""
            ],
            "defaultValue": "",
            "propValueType": "",
            "propType": "",
            "isDisplayable": "",
            "isArray": "",
            "lov": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "isRequired": "",
            "isEnabled": ""
          }
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::GetAttrMappingsForDatasetTypeOutput[] | A list of input dataset and item type criteria and the found attribute mapping definitions. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

##### 2.2.1.9 getAvailableTypes

**接口路径：** `Cad-2007-01-DataManagement/getAvailableTypes`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 根据输入类名查询其实现/可用的业务对象类型列表。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.getAvailableTypes`

**请求（input）：**

```json
{
  "classes": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `classes` | std::string[] | A list of the classes to return subtypes for |

**响应（output）：**

```json
{
  "inputClassToTypes": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputClassToTypes` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ClassToTypesMap | Map where the key is the class type and the value is a list of strings representing the types available for the class. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains objects that are returned by the service, and error information. The actual type objects are returned as <font face=&quot;courier&quot; height=&quot;10 |

---

##### 2.2.1.10 resolveAttrMappingsForDataset

**接口路径：** `Cad-2007-01-DataManagement/resolveAttrMappingsForDataset`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 解析一个或多个数据集上的 CAD 属性映射，返回映射后的属性值。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.resolveAttrMappingsForDataset`

**请求（input）：**

```json
{
  "info": [
    {
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "cadAttrMappingDefinitions": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ResolveAttrMappingsForDatasetInfo[] | An array of <font face=&quot;courier&quot; height=&quot;10&quot;>ResolveAttrMappingsForDatasetInfo</font> structures each containing a <b>Dataset</b> object ref |

**响应（output）：**

```json
{
  "output": [
    {
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "mappedProperties": [
        {
          "attrTitle": "",
          "datasetTypeName": "",
          "itemTypeName": "",
          "resolvedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "resolvedPropertyName": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ResolveAttrMappingsForDatasetOutput[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>ResolveAttrMappingsForDatasetOutput</font> |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font> contains any partial errors and exceptions.<br />The objects holding the mapped attribut |

---

#### 版本 2007-12

##### 2.2.2.1 createOrUpdateParts

**接口路径：** `Cad-2007-12-DataManagement/createOrUpdateParts`

**API 版本：** `2007-12`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "value": ""
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "value": ""
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": ""
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_12::DataManagement::PartInfo2[] | A list of PartInfo2 structures |
| `pref` | Teamcenter::Soa::Cad::_2007_12::DataManagement::CreateOrUpdatePartsPref | A Struct which contains information whether dataset needs to be modified, if input last modified date is different from actual. |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": ""
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

#### 版本 2008-03

##### 2.2.3.1 createOrUpdateParts

**接口路径：** `Cad-2008-03-DataManagement/createOrUpdateParts`

**API 版本：** `2008-03`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_03.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "value": ""
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "value": ""
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": ""
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_03::DataManagement::PartInfo3[] | A list of PartInfo3 structures |
| `pref` | Teamcenter::Soa::Cad::_2007_12::DataManagement::CreateOrUpdatePartsPref | A Struct which contains information whether dataset needs to be modified, if input last modified date is different from actual. |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": ""
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

##### 2.2.3.2 resolveAttrMappings

**接口路径：** `Cad-2008-03-DataManagement/resolveAttrMappings`

**API 版本：** `2008-03`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 解析并返回 ItemRevision 或数据集上配置的 CAD 属性映射结果（属性值）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_03.DataManagement.resolveAttrMappings`

**请求（input）：**

```json
{
  "info": [
    {
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "mappingDefinitionInfos": [
        {
          "clientId": "",
          "cadAttrMappingDefinition": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_03::DataManagement::ResolveAttrMappingsInfo[] | An array of ResolveAttrMappingsInfo structures each containing a <b>Dataset</b> object reference, an optional item revision, and a list of corresponding CAD Att |

**响应（output）：**

```json
{
  "resolvedMappingsMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `resolvedMappingsMap` | Teamcenter::Soa::Cad::_2008_03::DataManagement::ResolveAttrMappingsOutputMap | Member of type <font face=&quot;courier&quot; height=&quot;10&quot;>ResolveAttrMappingsOutputMap</font>. This is a map containing the successfully mapped proper |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data contains any partial errors and exceptions. The objects holding the mapped attributes, resulting from successfully resolved mappings, are returned  |

---

#### 版本 2008-06

##### 2.2.4.1 createOrUpdateParts

**接口路径：** `Cad-2008-06-DataManagement/createOrUpdateParts`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "partInput": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": "",
              "boundingBoxesAvailable": "",
              "boundingBoxes": [
                {
                  "xmin": "",
                  "ymin": "",
                  "zmin": "",
                  "xmax": "",
                  "ymax": "",
                  "zmax": ""
                }
              ]
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `partInput` | Teamcenter::Soa::Cad::_2008_06::DataManagement::PartInfo[] | A list of PartInfo structures |
| `pref` | Teamcenter::Soa::Cad::_2007_12::DataManagement::CreateOrUpdatePartsPref | A Struct which contains information whether dataset needs to be modified, if input last modified date is different from actual |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": "",
                    "boundingBoxesAvailable": "",
                    "boundingBoxes": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

##### 2.2.4.2 expandFoldersForCAD

**接口路径：** `Cad-2008-06-DataManagement/expandFoldersForCAD`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 为 CAD 客户端按文件夹层次展开对象，返回可在 CAD 环境中打开/集成的对象列表。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.DataManagement.expandFoldersForCAD`

**请求（input）：**

```json
{
  "folders": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "pref": {
    "expItemRev": "",
    "latestNRevs": "",
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ],
    "contentTypesFilter": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `folders` | Teamcenter::Folder[] | A list of folders to expand. |
| `pref` | Teamcenter::Soa::Cad::_2008_06::DataManagement::ExpandFolderForCADPref2 | Filter and expand preferences |

**响应（output）：**

```json
{
  "output": [
    {
      "inputFolder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "fstlvlFolders": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "itemsOutput": [
        {
          "outputItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevsOutput": [
            {
              "outputItemRevs": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "outputDatasets": [
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
      "itemRevsOutput": [
        {
          "outputItemRevs": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "outputDatasets": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ],
      "contents": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::DataManagement::ExpandFoldersForCADOutput2[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>ExpandFoldersForCADOutput2</font> which has information about the input folder and folders, items |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains the folders, items, items revisions, datasets, and other object types in the list of plain objects. <br />Error information returned is identified by t |

---

#### 版本 2010-09

##### 2.2.5.1 createOrUpdateParts

**接口路径：** `Cad-2010-09-DataManagement/createOrUpdateParts`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2010_09.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "partInput": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": "",
              "boundingBoxesAvailable": "",
              "destinationVolume": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boundingBoxes": [
                {
                  "xmin": "",
                  "ymin": "",
                  "zmin": "",
                  "xmax": "",
                  "ymax": "",
                  "zmax": ""
                }
              ]
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "datasetTool": "",
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `partInput` | Teamcenter::Soa::Cad::_2010_09::DataManagement::PartInfo[] | A list of PartInfo structures |
| `pref` | Teamcenter::Soa::Cad::_2007_12::DataManagement::CreateOrUpdatePartsPref | A Struct which contains information whether dataset needs to be modified, if input last modified date is different from actual |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": "",
                    "boundingBoxesAvailable": "",
                    "boundingBoxes": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

#### 版本 2011-06

##### 2.2.6.1 getAllAttrMappings2

**接口路径：** `Cad-2011-06-DataManagement/getAllAttrMappings2`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 获取全部 CAD 属性映射定义（增强版接口，支持按数据集/Item 类型过滤）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2011_06.DataManagement.getAllAttrMappings2`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "attrMappingInfos": [
    {
      "cadAttrMappingDefinition": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propDesc": {
        "propName": "",
        "displayName": "",
        "isModifiable": "",
        "attachedSpecifier": "",
        "maxLength": "",
        "lovAttachmentsCategory": "",
        "interdependentProps": [
          ""
        ],
        "defaultValue": "",
        "propValueType": "",
        "propType": "",
        "isDisplayable": "",
        "isArray": "",
        "lov": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isRequired": "",
        "isEnabled": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `attrMappingInfos` | Teamcenter::Soa::Cad::_2011_06::DataManagement::AttrMappingInfo[] | A list of attribute mapping information. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

#### 版本 2012-09

##### 2.2.7.1 createOrUpdateParts

**接口路径：** `Cad-2012-09-DataManagement/createOrUpdateParts`

**API 版本：** `2012-09`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2012_09.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "partInput": [
    {
      "clientId": "",
      "itemInput": {
        "createOrUpdateInput": {
          "boName": "",
          "boReference": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "boolProps": {},
          "boolArrayProps": {},
          "dateProps": {},
          "dateArrayProps": {},
          "tagProps": {},
          "tagArrayProps": {},
          "compoundCreateOrUpdateInput": {},
          "stringProps": {},
          "stringArrayProps": {},
          "doubleProps": {},
          "doubleArrayProps": {},
          "floatProps": {},
          "floatArrayProps": {},
          "intProps": {},
          "intArrayProps": {}
        },
        "itemExtraObject": [
          {
            "clientId": "",
            "createOrUpdateInput": {
              "boName": "",
              "boReference": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boolProps": {},
              "boolArrayProps": {},
              "dateProps": {},
              "dateArrayProps": {},
              "tagProps": {},
              "tagArrayProps": {},
              "compoundCreateOrUpdateInput": {},
              "stringProps": {},
              "stringArrayProps": {},
              "doubleProps": {},
              "doubleArrayProps": {},
              "floatProps": {},
              "floatArrayProps": {},
              "intProps": {},
              "intArrayProps": {}
            },
            "relationTypeName": ""
          }
        ],
        "itemRevisionExtraObject": [
          {
            "clientId": "",
            "createOrUpdateInput": {
              "boName": "",
              "boReference": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boolProps": {},
              "boolArrayProps": {},
              "dateProps": {},
              "dateArrayProps": {},
              "tagProps": {},
              "tagArrayProps": {},
              "compoundCreateOrUpdateInput": {},
              "stringProps": {},
              "stringArrayProps": {},
              "doubleProps": {},
              "doubleArrayProps": {},
              "floatProps": {},
              "floatArrayProps": {},
              "intProps": {},
              "intArrayProps": {}
            },
            "relationTypeName": ""
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "datasetInput": [
        {
          "clientId": "",
          "createOrUpdateInput": {
            "boName": "",
            "boReference": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "boolProps": {},
            "boolArrayProps": {},
            "dateProps": {},
            "dateArrayProps": {},
            "tagProps": {},
            "tagArrayProps": {},
            "compoundCreateOrUpdateInput": {},
            "stringProps": {},
            "stringArrayProps": {},
            "doubleProps": {},
            "doubleArrayProps": {},
            "floatProps": {},
            "floatArrayProps": {},
            "intProps": {},
            "intArrayProps": {}
          },
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": "",
              "boundingBoxesAvailable": "",
              "destinationVolume": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boundingBoxes": [
                {
                  "xmin": "",
                  "ymin": "",
                  "zmin": "",
                  "xmax": "",
                  "ymax": "",
                  "zmax": ""
                }
              ]
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "createOrUpdateInput": {
                "boName": "",
                "boReference": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boolProps": {},
                "boolArrayProps": {},
                "dateProps": {},
                "dateArrayProps": {},
                "tagProps": {},
                "tagArrayProps": {},
                "compoundCreateOrUpdateInput": {},
                "stringProps": {},
                "stringArrayProps": {},
                "doubleProps": {},
                "doubleArrayProps": {},
                "floatProps": {},
                "floatArrayProps": {},
                "intProps": {},
                "intArrayProps": {}
              },
              "namedReferenceName": "",
              "namedReferenceType": ""
            }
          ],
          "basisName": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "itemRevRelationName": "",
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "mappingAttributes": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "extraObject": [
            {
              "clientId": "",
              "createOrUpdateInput": {
                "boName": "",
                "boReference": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boolProps": {},
                "boolArrayProps": {},
                "dateProps": {},
                "dateArrayProps": {},
                "tagProps": {},
                "tagArrayProps": {},
                "compoundCreateOrUpdateInput": {},
                "stringProps": {},
                "stringArrayProps": {},
                "doubleProps": {},
                "doubleArrayProps": {},
                "floatProps": {},
                "floatArrayProps": {},
                "intProps": {},
                "intArrayProps": {}
              },
              "relationTypeName": ""
            }
          ]
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `partInput` | Teamcenter::Soa::Cad::_2012_09::DataManagement::PartInfo[] | A list of <font face="courier" height="10">PartInfo</font> structures |
| `pref` | Teamcenter::Soa::Cad::_2007_12::DataManagement::CreateOrUpdatePartsPref | A Struct which contains information whether dataset needs to be modified, if input last modified date is different from actual |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": "",
                    "boundingBoxesAvailable": "",
                    "boundingBoxes": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

#### 版本 2014-10

##### 2.2.8.1 getAttrMappings

**接口路径：** `Cad-2014-10-DataManagement/getAttrMappings`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 按输入过滤条件获取 CAD 属性映射定义（可限定数据集类型与 Item 类型组合）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2014_10.DataManagement.getAttrMappings`

**请求（input）：**

```json
{
  "filter": [
    {
      "itemTypeName": "",
      "datasetTypeName": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `filter` | Teamcenter::Soa::Cad::_2014_10::DataManagement::GetAttrMappingsFilter[] | The input filter for narrowing the attribute mapping definitions returned in the response. All of the attribute mappings defined in Teamcenter are returned when |

**响应（output）：**

```json
{
  "attrMappingInfos": [
    {
      "cadAttrMappingDefinition": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propDescInfo": {
        "boTypeName": "",
        "propDescName": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `attrMappingInfos` | Teamcenter::Soa::Cad::_2014_10::DataManagement::AttrMappingInfo[] | A list of attribute mapping information. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">ServiceData</font>. This operation will populate the ServiceData plain objects with <b>CadAttrMappingDefinition</b> objects |

---

#### 版本 2016-03

##### 2.2.9.1 createOrUpdateModelViewPalette

**接口路径：** `Cad-2016-03-DataManagement/createOrUpdateModelViewPalette`

**API 版本：** `2016-03`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 创建、更新或删除模型视图面板（Fnd0ModelViewPalette）及其分组。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_03.DataManagement.createOrUpdateModelViewPalette`

**请求（input）：**

```json
{
  "mvPaletteInfo": [
    {
      "clientId": "",
      "disclosure": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "boType": "",
      "paletteToUpdate": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attrListForPalette": [
        {
          "name": "",
          "values": [
            ""
          ]
        }
      ],
      "groupsAndProxies": [
        {
          "clientId": "",
          "boType": "",
          "modelViewGroupForUpdate": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "attrListForGroup": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "proxiesInGroup": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "newOrderSequenceNumber": []
        }
      ],
      "paletteIsComplete": "",
      "groupsToDelete": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "deletePalette": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `mvPaletteInfo` | Teamcenter::Soa::Cad::_2016_03::DataManagement::ModelViewPaletteInfo[] | The model view palette information describing the details of the palette (<b>Fnd0ModelViewPalette</b>) and model view groups (<b>Fnd0ModelViewGroup</b>) to be c |

**响应（output）：**

```json
{
  "clientIDMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `clientIDMap` | Teamcenter::Soa::Cad::_2016_03::DataManagement::StringToBoMap | Map(string, <b>Fnd0ModelViewPalette</b> or <b>Fnd0ModelViewGroup</b>) of the various input <font face="courier" height="10">clientId</font> to corresponding obj |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains a list of added, updated, or deleted objects.  Also contains list of any errors which occurred within the call. |

---

##### 2.2.9.2 createOrUpdateModelViewProxies

**接口路径：** `Cad-2016-03-DataManagement/createOrUpdateModelViewProxies`

**API 版本：** `2016-03`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 创建、更新或删除一组模型视图代理（Fnd0ModelViewProxy）对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_03.DataManagement.createOrUpdateModelViewProxies`

**请求（input）：**

```json
{
  "mvProxyInfos": [
    {
      "clientId": "",
      "modelView": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "boType": "",
      "deleteProxy": "",
      "owningModel": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attrList": [
        {
          "name": "",
          "values": [
            ""
          ]
        }
      ],
      "thumbnailFile": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "hiresImageFile": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "guardObjLastModifiedDate": "",
      "objLastModifiedDateGuard": "0001-01-01T00:00:00"
    }
  ],
  "updatedOwningModels": [
    {
      "owningModel": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "cadLastModifiedDate": "0001-01-01T00:00:00",
      "owningDataset": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `mvProxyInfos` | Teamcenter::Soa::Cad::_2016_03::DataManagement::ModelViewProxyInfo[] | The input list of model view proxy information describing the details of the proxies to be created or updated. |
| `updatedOwningModels` | Teamcenter::Soa::Cad::_2016_03::DataManagement::OwningModelAndCadLmd[] | The input list of model view owners which have had their CAD model views updated. After <font face="courier" height="10">mvProxyInfos</font> has been processed, |

**响应（output）：**

```json
{
  "clientIDMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `clientIDMap` | Teamcenter::Soa::Cad::_2016_03::DataManagement::StringToBoMap | Map (string, <b>Fnd0ModelViewProxy</b>) of the various input client IDs to corresponding objects (<b>Fnd0ModelViewProxy</b>) that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains a list of added, updated, or deleted objects.  Also contains list of any errors which occurred within the call. |

---

### 2.3 结构管理（StructureManagement）

**涵盖 API 版本：** `2007-01`、`2007-06`、`2007-09`、`2007-12`、`2008-03`、`2008-06`、`2009-04`、`2013-05`、`2016-03`、`2016-09`、`2018-06`、`2019-06`、`2023-06`、`2023-12`、`2024-12`、`2025-06`  
**操作条目数：** 47

#### 版本 2007-01

##### 2.3.1.1 closeBOMWindows

**接口路径：** `Cad-2007-01-StructureManagement/closeBOMWindows`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 关闭一个或多个 BOM 窗口，释放服务器端产品结构资源。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.closeBOMWindows`

**请求（input）：**

```json
{
  "bomWindows": [
    "{{ROOT_BOM_ITEM_BOM_WINDOW_UID}}"
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `bomWindows` | Teamcenter::BOMWindow[] | The BOMWindow to close |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, Servi |

---

##### 2.3.1.2 createBOMWindows

**接口路径：** `Cad-2007-01-StructureManagement/createBOMWindows`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 为指定 Item 创建 BOM 窗口，将对应 ItemRevision 设为顶行，返回 BOM 窗口 UID 与根 BOMLine；BOM 操作建议使用无状态（stateless）连接。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.createBOMWindows`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "item": "{{ROOT_BOM_ITEM_UID}}",
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomView": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revRuleConfigInfo": {
        "clientId": "",
        "revRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "props": {
          "unitNo": "",
          "date": "0001-01-01T00:00:00",
          "today": "",
          "endItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "endItemRevision": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "overrideFolders": [
            {
              "ruleEntry": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "folder": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      },
      "objectForConfigure": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "activeAssemblyArrangement": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateBOMWindowsInfo[] | Input is an item or item Revision object |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "bomWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomLine": {
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
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateBOMWindowsOutput[] | List of CreateBOMWindowsOutput which contains created BOMWindow object and top line BOMLine object representing the item or item revision along with the client  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, Servi |

---

##### 2.3.1.3 createOrUpdateAbsoluteStructure

**接口路径：** `Cad-2007-01-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新绝对坐标系下的产品结构（绝对变换/绝对定位语义）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "info": [
    {
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "clientIdOfUsedArrangement": "",
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            }
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "isDefault": "",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "clientIdOfUsedArrangement": "",
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateOrUpdateAbsoluteStructureInfo[] | List of input structures that defines all the occurrence for a given parent |
| `bomViewTypeName` | std::string | Type of BOMView |
| `complete` | bool | Flag that if true signifies that the structure represented in the input is the full representation of the structure under the input parent. Any other structure  |
| `pref` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateOrUpdateAbsoluteStructurePref | preference structure specific for this service |

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccOutput` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToAbsOccMap | Map of input clientId for the absolute occurrence to created/updated/found absolute occurrence |
| `asmArrOutput` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToAsmArrMap | Map of input client id to created/updated/found AssemblyArrangement |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData contains any other created (AbsOccData, AbsOccDataQualifier), updated (like BVR), relevant related, or deleted objects from this operation. |

---

##### 2.3.1.4 createOrUpdateRelativeStructure

**接口路径：** `Cad-2007-01-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ],
      "precise": ""
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "cadOccIdAttrName": "",
    "itemTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateOrUpdateRelativeStructureInfo[] | List of input structures that defines all the occurrence for a given parent |
| `bomViewTypeName` | std::string | Type of BOMView to create |
| `complete` | bool | Flag that if true signifies that the structure represented in the input is the full representation of the structure under the input parent.  Any other structure |
| `pref` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateOrUpdateRelativeStructurePref | Preference structure specific for this service |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToPSOccurrenceThreadMap | Member of type ClientIdToPSOccurrenceThreadMap |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Mwmber of type Teamcenter::Soa::Server::ServiceData serviceData |

---

##### 2.3.1.5 deleteAssemblyArrangements

**接口路径：** `Cad-2007-01-StructureManagement/deleteAssemblyArrangements`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除装配配置（Assembly Arrangement）相关结构数据。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.deleteAssemblyArrangements`

**请求（input）：**

```json
{
  "info": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "arrangements": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "bomViewTypeName": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::DeleteAssemblyArrangementsInfo[] | Input is bvr and list of assembly arrangements to delete |
| `bomViewTypeName` | std::string | The BOM view type name |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

##### 2.3.1.6 deleteRelativeStructure

**接口路径：** `Cad-2007-01-StructureManagement/deleteRelativeStructure`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除相对产品结构中的指定结构关系或子结构。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.deleteRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        ""
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::DeleteRelativeStructureInfo[] | List input of structures that defines the parent and first level children to be deleted. |
| `bomViewTypeName` | std::string | Qualifies the specified parent item revision(s) to identify a unique BOM view revision. |
| `pref` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::DeleteRelativeStructurePref | Preference structure specific for this service |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

##### 2.3.1.7 expandPSAllLevels

**接口路径：** `Cad-2007-01-StructureManagement/expandPSAllLevels`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 从产品结构（PS）指定父 BOMLine 递归展开全部层级，返回完整 BOM 树。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.expandPSAllLevels`

**请求（input）：**

```json
{
  "input": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSAllLevelsInfo | of  ExpandPSAllLevelsInfo which contains parent bom lines and a filter of the type of bom lines to exclude. |
| `pref` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSAllLevelsPref | of a ExpandPSAllLevelsPref which contains a list of relation name and the types of objects of the given relation to return along with the children. |

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemRevOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentDatasets": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "datasets": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSAllLevelsOutput[] | List of ExpandPSAllLevelsOutput which contains ExpandPSParentData and list of ExpandPSData |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, all o |

---

##### 2.3.1.8 expandPSOneLevel

**接口路径：** `Cad-2007-01-StructureManagement/expandPSOneLevel`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 从产品结构父 BOMLine 仅展开下一层子 BOMLine。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.expandPSOneLevel`

**请求（input）：**

```json
{
  "input": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSOneLevelInfo | of  ExpandPSOneLevelInfo which contains parent bom lines and a filter of the type of bom lines to exclude. |
| `pref` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSOneLevelPref | of a ExpandPSOneLevelPref which contains a list of relation name and the types of objects of the given relation to return along with the children. |

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemRevOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentDatasets": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "datasets": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSOneLevelOutput[] | List of ExpandPSOneLevelOutput which contains ExpandPSParentData and list of ExpandPSData |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, all o |

---

##### 2.3.1.9 getRevisionRules

**接口路径：** `Cad-2007-01-StructureManagement/getRevisionRules`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 获取系统可用的版本规则（Revision Rule）列表，用于 BOM 有效性配置。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.getRevisionRules`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "output": [
    {
      "revRule": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "hasValueStatus": {},
      "overrideFolders": [
        {
          "ruleEntry": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "folder": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::RevisionRuleInfo[] | List of RevisionRuleInfo which contains Revision rule, configure attribute status along with override information |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error |

---

##### 2.3.1.10 getVariantRules

**接口路径：** `Cad-2007-01-StructureManagement/getVariantRules`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 获取变型规则（Variant Rule）及相关配置信息。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.getVariantRules`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `itemRevs` | Teamcenter::ItemRevision[] | List of object references of ItemRevisions to get variant rules for |

**响应（output）：**

```json
{
  "inputItemRevToVarRules": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputItemRevToVarRules` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ItemRevisionToVariantRulesMap | Holds map of itemRevision to list of VariantRules. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData |

---

#### 版本 2007-06

##### 2.3.2.1 createOrUpdateClassicOptions

**接口路径：** `Cad-2007-06-StructureManagement/createOrUpdateClassicOptions`

**API 版本：** `2007-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新经典变型选项（Classic Option）及其选项值，并声明到 ItemRevision。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_06.StructureManagement.createOrUpdateClassicOptions`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "clientId": "",
      "operation": "CreateOption",
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "options": [
        {
          "optionName": "",
          "optionDesc": "",
          "values": [
            ""
          ],
          "existingValues": [
            ""
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputObjects` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::CreateUpdateClassicOptionsInput[] | Refers to the list of CreateUpdateClassicOptionsInput struct, which are used to create a new variant option or update an existing variant option. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.2.2 createOrUpdateVariantConditions

**接口路径：** `Cad-2007-06-StructureManagement/createOrUpdateVariantConditions`

**API 版本：** `2007-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 为 BOMLine 创建或更新变型条件（load_if 类型的变型表达式）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_06.StructureManagement.createOrUpdateVariantConditions`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "clientId": "",
      "operation": "Create",
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "variantCondInfo": [
        {
          "optionName": "",
          "joinOperator": "AND",
          "compOperator": "EQ",
          "value": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputObjects` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::CreateOrUpdateVariantCondInput[] | This has the list of <font face="courier" height="10">CreateOrUpdateVariantCondInput</font> struct, which are used to create a new variant condition or update a |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.2.3 deleteClassicOptions

**接口路径：** `Cad-2007-06-StructureManagement/deleteClassicOptions`

**API 版本：** `2007-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除经典变型选项及其全部关联选项值。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_06.StructureManagement.deleteClassicOptions`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "clientId": "",
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "optionNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputObjects` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::DelClassicOptionsInput[] | A list of DelClassicOptionsInput structures, each of which contains a bomline tag, and list of options. If the option exists then it will be deleted. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.2.4 deleteVariantConditions

**接口路径：** `Cad-2007-06-StructureManagement/deleteVariantConditions`

**API 版本：** `2007-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除 BOMLine 上关联的变型条件（load_if）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_06.StructureManagement.deleteVariantConditions`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "clientId": "",
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputObjects` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::DeleteVariantCondInput[] | Consists of the clientId and the BOMLine for which we need to delete the variant Condition |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.3.2.5 getConfiguredItemRevision

**接口路径：** `Cad-2007-06-StructureManagement/getConfiguredItemRevision`

**API 版本：** `2007-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 按指定版本规则配置后，解析 Item/ItemRevision 对应的有效版本。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_06.StructureManagement.getConfiguredItemRevision`

**请求（input）：**

```json
{
  "inputs": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revRule": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::GetConfiguredItemRevisionInfo[] | A list of GetConfiguredItemRevisionInfo structures, each of which contain a item or item revision object and revision rule. |

**响应（output）：**

```json
{
  "output": [
    {
      "inputInfo": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revRule": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "configuredItemRev": {
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
| `output` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::GetConfiguredItemRevisionOutput[] | A List of type GetConfiguredItemRevisionOutput |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing plain objects and error information. |

---

#### 版本 2007-09

##### 2.3.3.1 createOrUpdateVariantConditions2

**接口路径：** `Cad-2007-09-StructureManagement/createOrUpdateVariantConditions2`

**API 版本：** `2007-09`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新变型条件（增强版接口）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_09.StructureManagement.createOrUpdateVariantConditions2`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "clientId": "",
      "operation": "Create",
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "variantCondInfo": [
        {
          "optionName": "",
          "itemId": "",
          "joinOperator": "AND",
          "compOperator": "EQ",
          "value": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputObjects` | Teamcenter::Soa::Cad::_2007_09::StructureManagement::CreateOrUpdateVariantCondInput[] | This has the list of <font face="courier" height="10">CreateOrUpdateVariantCondInput</font> struct, which are used to create a new variant condition or update a |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2007-12

##### 2.3.4.1 createOrUpdateAbsoluteStructure

**接口路径：** `Cad-2007-12-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新绝对坐标系下的产品结构（绝对变换/绝对定位语义）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "info": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "clientIdOfUsedArrangement": "",
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            }
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "isDefault": "",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "clientIdOfUsedArrangement": "",
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::CreateOrUpdateAbsoluteStructureInfo2[] | List of input structures that defines all the occurrence for a given parent |
| `bomViewTypeName` | std::string | Type of BOMView |
| `complete` | bool | flag that if true signifies that the structure represented in the input is the full representation of the structure under the input parent. Any other structure  |
| `pref` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::CreateOrUpdateAbsoluteStructurePref2 | preference structure specific for this service |

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccOutput` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToAbsOccMap | Map of input clientId for the absolute occurrence to created/updated/found absolute occurrence |
| `asmArrOutput` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToAsmArrMap | Map of input client id to created/updated/found AssemblyArrangement |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData contains any other created (AbsOccData, AbsOccDataQualifier), updated (like BVR), relevant related, or deleted objects from this operation. |

---

##### 2.3.4.2 createOrUpdateRelativeStructure

**接口路径：** `Cad-2007-12-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ],
      "precise": ""
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": "",
    "itemTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::CreateOrUpdateRelativeStructureInfo2[] | List of input structures that defines all the occurrence for a given parent |
| `bomViewTypeName` | std::string | Type of BOMView to create |
| `complete` | bool | Flag that if true signifies that the structure represented in the input is the full representation of the structure under the input parent.  Any other structure |
| `pref` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::CreateOrUpdateRelativeStructurePref2 | Preference structure specific for this service |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToPSOccurrenceThreadMap | Member of type ClientIdToPSOccurrenceThreadMap |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Mwmber of type Teamcenter::Soa::Server::ServiceData serviceData |

---

##### 2.3.4.3 deleteAssemblyArrangements

**接口路径：** `Cad-2007-12-StructureManagement/deleteAssemblyArrangements`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除装配配置（Assembly Arrangement）相关结构数据。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.deleteAssemblyArrangements`

**请求（input）：**

```json
{
  "info": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "arrangements": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::DeleteAssemblyArrangementsInfo2[] | List of item revisions and the assembly arrangements to delete from the found BOM view revision. |
| `bomViewTypeName` | std::string | The BOM view type used to find the existing BOM view object. |
| `pref` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::DeleteAssemblyArrangementsPref | The structure for setting specific preference input used by this operation. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

##### 2.3.4.4 deleteRelativeStructure

**接口路径：** `Cad-2007-12-StructureManagement/deleteRelativeStructure`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除相对产品结构中的指定结构关系或子结构。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.deleteRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        ""
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::DeleteRelativeStructureInfo2[] | List input of structures that defines the parent and first level children to be deleted. |
| `bomViewTypeName` | std::string | Qualifies the specified parent item revision(s) to identify a unique BOM   view revision. |
| `pref` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::DeleteRelativeStructurePref2 | Preference structure specific for this service |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

##### 2.3.4.5 queryClassicOptions

**接口路径：** `Cad-2007-12-StructureManagement/queryClassicOptions`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 查询 ItemRevision 上已定义的经典变型选项。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.queryClassicOptions`

**请求（input）：**

```json
{
  "inputRevisions": [
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
| `inputRevisions` | Teamcenter::ItemRevision[] | This is list of <b>ItemRevision</b> object on which variant options are to be queried. |

**响应（output）：**

```json
{
  "itemRevisionOptionData": [
    {
      "itemRevision": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "optionData": [
        {
          "optionName": "",
          "optionDesc": "",
          "values": [
            ""
          ],
          "existingValues": [
            ""
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `itemRevisionOptionData` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::ClassicOptionData[] | Refers to a list of <font face="courier" height="10">ClassicOptionData</font> struct, which has <b>ItemRevision</b> and corresponding classic variant option lis |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the service operation, plain objects, and error information. |

---

##### 2.3.4.6 queryVariantConditions

**接口路径：** `Cad-2007-12-StructureManagement/queryVariantConditions`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 查询 BOMLine 上的变型条件值。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.queryVariantConditions`

**请求（input）：**

```json
{
  "inputBomLines": [
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
| `inputBomLines` | Teamcenter::BOMLine[] | This has the list of <b>BOMLine</b> objects, on which variant condition are defined. |

**响应（output）：**

```json
{
  "variantConditions": [
    {
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "conditionClauses": [
        {
          "optionName": "",
          "itemId": "",
          "joinOperator": "AND",
          "compOperator": "EQ",
          "value": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `variantConditions` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::BomLineVariantCondition[] | Refers to a list of <font face="courier" height="10">BomLineVariantCondition</font> struct objects, contains the variant condition on <b>BOMLine</b> object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

#### 版本 2008-03

##### 2.3.5.1 askChildPathBOMLines

**接口路径：** `Cad-2008-03-StructureManagement/askChildPathBOMLines`

**API 版本：** `2008-03`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 根据 PS 发生线程（Occurrence Thread）链描述的子路径，返回对应的 BOMLine 对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_03.StructureManagement.askChildPathBOMLines`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "parentBomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "useAsStable": "",
      "childPaths": [
        {
          "clientId": "",
          "childPath": [
            ""
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2008_03::StructureManagement::AskChildPathBOMLinesInfo[] | Specifies sets of product structure information each containing parent BOM line, based on a BOM Window opened by the client, and one or more child paths specifi |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_03::StructureManagement::AskChildPathBOMLineMap | A map of input PS Occurrence Thread UIDs to BOMLines. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing plain objects, and error information. |

---

#### 版本 2008-06

##### 2.3.6.1 createOrUpdateAbsoluteStructure

**接口路径：** `Cad-2008-06-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新绝对坐标系下的产品结构（绝对变换/绝对定位语义）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "absOccInfos": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "boundingBoxInfo": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boundingBoxVector": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "datasetAttachments": [
              {
                "clientId": "",
                "datasetInfo": {
                  "clientId": "",
                  "dataset": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "namedReferencePreference": "",
                  "dataList": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ],
                  "datasetFileInfos": [
                    {
                      "clientId": "",
                      "fileName": "",
                      "namedReferencedName": "",
                      "isText": "",
                      "allowReplace": "",
                      "boundingBoxesAvailable": "",
                      "boundingBoxes": [
                        {
                          "xmin": "",
                          "ymin": "",
                          "zmin": "",
                          "xmax": "",
                          "ymax": "",
                          "zmax": ""
                        }
                      ]
                    }
                  ],
                  "namedReferenceObjectInfos": [
                    {
                      "clientId": "",
                      "object": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "namedReferenceName": "",
                      "typeName": "",
                      "dataNameValuePairs": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ]
                    }
                  ],
                  "name": "",
                  "basisName": "",
                  "description": "",
                  "type": "",
                  "lastModifiedOfDataset": "0001-01-01T00:00:00",
                  "id": "",
                  "datasetRev": "",
                  "createNewVersion": ""
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "formAttachments": [
              {
                "clientId": "",
                "formInfo": {
                  "formObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "name": "",
                  "description": "",
                  "formType": "",
                  "attributes": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ]
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "clientIdOfUsedArrangement": ""
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "isDefault": "",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "clientIdOfUsedArrangement": "",
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "overridesToSynchronize": [
      ""
    ],
    "relationFilters": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ],
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccInfos` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateOrUpdateAbsoluteStructureInfo3[] | List of information related to the absolute occurrences that need to be created or updated. |
| `bomViewTypeName` | std::string | The BOM view (BV) type used to find the existing BOM view. |
| `complete` | bool | Flag that if true signifies that the absolute occurrences represented in <font face=&quot;courier&quot; height=&quot;10&quot;>absOccInfos</font> are the full re |
| `pref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateOrUpdateAbsoluteStructurePref3 | The structure for setting specific preference input used by this operation. |

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrangementOutput": {},
  "formOutput": {},
  "datasetOutput": [
    {
      "clientId": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "commitInfo": [
        {
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "datasetFileTicketInfos": [
            {
              "datasetFileInfo": {
                "clientId": "",
                "fileName": "",
                "namedReferencedName": "",
                "isText": "",
                "allowReplace": "",
                "boundingBoxesAvailable": "",
                "boundingBoxes": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              },
              "ticket": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToAbsOccMap2 | A map (string, <b>AbsOccurrence</b>) of input clientId to the created, updated or found absolute occurrence. |
| `asmArrangementOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToAsmArrangementMap | A map (string, list of <b>AssemblyArrangement</b>) of input clientId to the created or updated assembly arrangement. |
| `formOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToFormMap | A map (string, <b>Form</b>) of input clientId to the created form. |
| `datasetOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::DatasetOutput[] | A list of created or updated <b>Dataset</b>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData. This operation will populate the ServiceData with created or updated PSOccurrence objects, <b>AssemblyArrangement</b> objects, <b>Dataset</b> o |

---

##### 2.3.6.2 createOrUpdateRelativeStructure

**接口路径：** `Cad-2008-06-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ],
      "precise": ""
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateOrUpdateRelativeStructureInfo3[] | List of input structures that defines all the occurrence for a given parent |
| `bomViewTypeName` | std::string | Type of BOMView to create |
| `complete` | bool | Flag that if true signifies that the structure represented in the input is the full representation of the structure under the input parent. Any other structure  |
| `pref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateOrUpdateRelativeStructurePref3 | Preference structure specific for this service |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToPSOccurrenceThreadMap | Member of type ClientIdToPSOccurrenceThreadMap |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Mwmber of type Teamcenter::Soa::Server::ServiceData serviceData |

---

##### 2.3.6.3 createVariantRules

**接口路径：** `Cad-2008-06-StructureManagement/createVariantRules`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 为经典变型选项创建已保存的变型规则（VariantRule）对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.createVariantRules`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "vruleName": "",
      "vruleDescription": "",
      "rev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relation": "",
      "options": [
        {
          "optionName": "",
          "optionValue": "",
          "assocRev": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateVariantRulesInfo[] | This has the list of <font face="courier" height="10">CreateVariantRulesInfo</font> struct, which are used to create a new <b>VariantRule</b> object. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "output": [
    {
      "clientId": "",
      "vrule": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the service and error information if any. |
| `output` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::VariantRulesOutput[] | Refers to a list of <font face="courier" height="10">VariantRulesOutput</font> struct objects, which in turn refers to newly created <b>VariantRule</b> objects. |

---

##### 2.3.6.4 deleteRelativeStructure

**接口路径：** `Cad-2008-06-StructureManagement/deleteRelativeStructure`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除相对产品结构中的指定结构关系或子结构。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.deleteRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        ""
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::DeleteRelativeStructureInfo3[] | List of input structures that specify the parent and first level children to be deleted. |
| `bomViewTypeName` | std::string | The BOM view<b> </b>(BV) type used to find the existing BOM view. |
| `pref` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::DeleteRelativeStructurePref2 | The structure for setting specific preference input used by this operation. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

##### 2.3.6.5 expandPSAllLevels

**接口路径：** `Cad-2008-06-StructureManagement/expandPSAllLevels`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 从产品结构（PS）指定父 BOMLine 递归展开全部层级，返回完整 BOM 树。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.expandPSAllLevels`

**请求（input）：**

```json
{
  "info": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None2"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relatedObjAndNamedRefs": [
          {
            "objectTypeName": "",
            "namedReferenceNames": [
              ""
            ]
          }
        ],
        "namedRefHandler": "UseNamedRefsList"
      }
    ],
    "includeOccurrenceTypes": [
      ""
    ],
    "excludeOccurrenceTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSAllLevelsInfo | Input of ExpandPSAllLevelsInfo which contains parent bom lines and a filter of the type of bom lines to exclude. |
| `pref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSAllLevelsPref | of a ExpandPSAllLevelsPref which contains a list of relation name and the types of objects of the given relation to return along with the children. |

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "objectOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentRelatedObjects": [
          {
            "relatedObject": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "namedRefList": [
              {
                "namedReferenceType": "",
                "namedReferenceName": "",
                "referenceObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "fileTicket": ""
              }
            ]
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "objectOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relatedObjects": [
            {
              "relatedObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedRefList": [
                {
                  "namedReferenceType": "",
                  "namedReferenceName": "",
                  "referenceObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "fileTicket": ""
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSAllLevelsOutput[] | List of ExpandPSAllLevelsOutput1 which contains ExpandPSParentData and list of ExpandPSData |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, all o |

---

##### 2.3.6.6 expandPSOneLevel

**接口路径：** `Cad-2008-06-StructureManagement/expandPSOneLevel`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 从产品结构父 BOMLine 仅展开下一层子 BOMLine。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.expandPSOneLevel`

**请求（input）：**

```json
{
  "info": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None2"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relatedObjAndNamedRefs": [
          {
            "objectTypeName": "",
            "namedReferenceNames": [
              ""
            ]
          }
        ],
        "namedRefHandler": "UseNamedRefsList"
      }
    ],
    "includeOccurrenceTypes": [
      ""
    ],
    "excludeOccurrenceTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSOneLevelInfo | The list of parent BOM lines to expand, a filter that describes what child BOM lines are excluded in the expansion, and a filter that describes what named refer |
| `pref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSOneLevelPref | A flag for expanding BOM line object further and a list describing the relation name, related object type and named references that help define the expansion cr |

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "objectOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentRelatedObjects": [
          {
            "relatedObject": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "namedRefList": [
              {
                "namedReferenceType": "",
                "namedReferenceName": "",
                "referenceObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "fileTicket": ""
              }
            ]
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "objectOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relatedObjects": [
            {
              "relatedObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedRefList": [
                {
                  "namedReferenceType": "",
                  "namedReferenceName": "",
                  "referenceObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "fileTicket": ""
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSOneLevelOutput[] | List of ExpandPSOneLevelOutput structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, all o |

---

##### 2.3.6.7 getAbsoluteStructureData

**接口路径：** `Cad-2008-06-StructureManagement/getAbsoluteStructureData`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 获取已配置结构完全展开后的绝对结构数据（全展开 PS）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.getAbsoluteStructureData`

**请求（input）：**

```json
{
  "absOccDataQualInfos": [
    {
      "qualifyingBVR": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "upperQualifier": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "absOccDataPref": {
    "relationFilterInfos": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ],
    "qualifierFilter": "None"
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccDataQualInfos` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::AbsOccQualifierInfo[] | List of qualifying information for overrides |
| `absOccDataPref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::AbsOccDataPref | Preference on which relation overrides to expand and the preferred objects of type to return |

**响应（output）：**

```json
{
  "overrides": [
    {
      "occThreadPaths": [
        {
          "apn": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occThreadPath": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ],
      "dataOverrideInfo": {
        "overrideData": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "expandedOverrides": [
          {
            "relationName": "",
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
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `overrides` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::AbsOccStructureDataInfo[] | List of overrides |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains populated plain object list and partial errors. |

---

##### 2.3.6.8 reconfigureBOMWindows

**接口路径：** `Cad-2008-06-StructureManagement/reconfigureBOMWindows`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 按新的有效性、变型或版本规则等配置重新配置已有 BOM 窗口。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.reconfigureBOMWindows`

**请求（input）：**

```json
{
  "info": [
    {
      "clientID": "",
      "bomWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectForConfigure": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revRuleConfigInfo": {
        "clientId": "",
        "revRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "props": {
          "unitNo": "",
          "date": "0001-01-01T00:00:00",
          "today": "",
          "endItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "endItemRevision": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "overrideFolders": [
            {
              "ruleEntry": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "folder": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ReconfigureBOMWindowsInfo[] | This contains a list of <font face="courier" height="10">ReconfigureBOMWindowsInfo</font> struct objects which has <b>BOMWindow</b> objects and corresponding <b |

**响应（output）：**

```json
{
  "output": [
    {
      "clientID": "",
      "bomWindow": {
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
| `output` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ReconfigureBOMWindowsOutput[] | This contains list of <font face="courier" height="10">ReconfigureBOMWindowsOutput</font> struct object, which returns the <b>BOMWindow</b> which has updated co |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the service and error information if any. |

---

##### 2.3.6.9 saveBOMWindows

**接口路径：** `Cad-2008-06-StructureManagement/saveBOMWindows`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 保存 BOM 窗口中的结构修改（新增/更新/删除的 BOM 行等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.saveBOMWindows`

**请求（input）：**

```json
{
  "bomWindows": [
    "{{ROOT_BOM_ITEM_BOM_WINDOW_UID}}"
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `bomWindows` | Teamcenter::BOMWindow[] | References to the <b>BOMWindow</b> business objects that need to be saved after structure modifications. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any failures will be returned in the ServiceData list of partial errors. |

---

#### 版本 2009-04

##### 2.3.7.1 createOrUpdateRelativeStructure

**接口路径：** `Cad-2009-04-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2009-04`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2009_04.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::CreateOrUpdateRelativeStructureInfo[] | List of input structures that specify all the children to be added to the specified parent assembly. |
| `pref` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::CreateOrUpdateRelativeStructurePref | The structure for setting specific preference input used by this operation. |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::ClientIdToOccurrenceMap | Map of client IDs to <font face=&quot;courier&quot; height=&quot;10&quot;>MappedReturnData</font>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

#### 版本 2013-05

##### 2.3.8.1 askChildPathBOMLines2

**接口路径：** `Cad-2013-05-StructureManagement/askChildPathBOMLines2`

**API 版本：** `2013-05`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 根据子路径查询 BOMLine（增强版，支持批量路径输入）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2013_05.StructureManagement.askChildPathBOMLines2`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "parentBomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "useAsStable": "",
      "childPaths": [
        {
          "clientId": "",
          "childPath": [
            ""
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2008_03::StructureManagement::AskChildPathBOMLinesInfo[] | Specifies sets of product structure information each containing parent <b>BOMLine</b> object, based on a BOM window opened by the client and one or more child p |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2013_05::StructureManagement::AskChildPathClientIdToBOMLineMap | A map of input Client ID to a vector of structure containing the input child path and its corresponding <b>BOMLine</b> object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing plain objects and error information. |

---

##### 2.3.8.2 createBOMWindows2

**接口路径：** `Cad-2013-05-StructureManagement/createBOMWindows2`

**API 版本：** `2013-05`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建 BOM 窗口（增强版）：支持批量输入 ItemRevision 作为顶行，返回多个窗口信息。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2013_05.StructureManagement.createBOMWindows2`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "item": "{{ROOT_BOM_ITEM_UID}}",
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomView": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revRuleConfigInfo": {
        "clientId": "",
        "revRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "props": {
          "unitNo": "",
          "date": "0001-01-01T00:00:00",
          "today": "",
          "endItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "endItemRevision": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "overrideFolders": [
            {
              "ruleEntry": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "folder": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      },
      "objectsForConfigure": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "activeAssemblyArrangement": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "configContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomWinPropFlagMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2013_05::StructureManagement::CreateWindowsInfo2[] | list of objects containing window creation information |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "bomWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomLine": {
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
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateBOMWindowsOutput[] | List of CreateBOMWindowsOutput which contains created BOMWindow object and top line BOMLine object representing the item or item revision along with the client  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, Servi |

---

##### 2.3.8.3 createOrUpdateRelativeStructure

**接口路径：** `Cad-2013-05-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2013-05`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2013_05.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "childBomViewTypeName": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "moveInfo": {
              "commonParent": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "sourceAssembly": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "occThreadPathToBeMoved": [
                ""
              ],
              "occThreadPathTargetParent": [
                {
                  "parent": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "idType": "OccurrenceThread",
                  "id": "",
                  "isNew": ""
                }
              ]
            }
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2013_05::StructureManagement::CreateOrUpdateRelativeStructureInfo4[] | List of input structures that defines all the occurrence for a given parent. |
| `pref` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::CreateOrUpdateRelativeStructurePref | Preference structure specific for this service. |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::ClientIdToOccurrenceMap | Map of client IDs to <font face=&quot;courier&quot; height=&quot;10&quot;>MappedReturnData</font>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

#### 版本 2016-03

##### 2.3.9.1 findModelViewsInStructure

**接口路径：** `Cad-2016-03-StructureManagement/findModelViewsInStructure`

**API 版本：** `2016-03`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 在指定产品结构中查找关联的模型视图代理对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_03.StructureManagement.findModelViewsInStructure`

**请求（input）：**

```json
{
  "disclosure": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "structureScope": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "configurationContext": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "withDisclosureIntent": [
    ""
  ],
  "options": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `disclosure` | Teamcenter::BusinessObject | The use of this value is required  for update cases where the <i>compareWithMVList</i> option is set to true and <font face="courier" height="10">structureScope |
| `structureScope` | Teamcenter::BusinessObject[] | A list of one or more structures to search for model view proxy objects. If a single root assembly or workset(<b>Cpd0Workset</b>) is given, the entire structure |
| `configurationContext` | Teamcenter::ConfigurationContext | A reference to a configuration context object. Used to configure the children of the expanding structure by revision rules, effectivity, and variants. |
| `withDisclosureIntent` | std::string[] | A list of string values to match against candidate model view proxies. Only model view proxies that have any of the specified disclosure intent attribute (<b>fn |
| `options` | Teamcenter::Soa::Cad::_2016_03::StructureManagement::BoolMap | A set of optional flags. Supported options are: "compareWithMVList", "skipBackgroundScope", "doNotExpandStructureScope", "skipDirectDisclosedObject<i>" </i>or " |

**响应（output）：**

```json
{
  "modelViewsByStructureNodes": [
    {
      "structureNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "resultingViews": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "csIdContextOccurrence": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clonestableId": [
        ""
      ]
    }
  ],
  "unfoundFromModelViewList": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "possibleMatching": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `modelViewsByStructureNodes` | Teamcenter::Soa::Cad::_2016_03::StructureManagement::StructureNodeResults[] | A list of proxy objects found for various nodes in the structure - the structure nodes may be bomlines, item revisions or design elements depending on the type  |
| `unfoundFromModelViewList` | Teamcenter::Fnd0ModelViewProxy[] | The model view proxy objects (<b>Fnd0ModelViewProxy</b>) that are currently associated to the specified disclosure but are not found in the given <font face="co |
| `possibleMatching` | Teamcenter::Soa::Cad::_2016_03::StructureManagement::BoToBoMap | Map (<b>Fnd0ModelViewProxy</b>, <b>Fnd0ModelViewProxy</b>) of possible matching proxies that are equivalent. The keys are proxies in an associated MVList (assoc |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains a list of any errors which occurred during the operation. |

---

#### 版本 2016-09

##### 2.3.10.1 continueFindModelViews

**接口路径：** `Cad-2016-09-StructureManagement/continueFindModelViews`

**API 版本：** `2016-09`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 继续由 startFindModelViews 发起的模型视图搜索。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_09.StructureManagement.continueFindModelViews`

**请求（input）：**

```json
{
  "searchID": "",
  "stopFind": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `searchID` | std::string | A unique identifier passed by the client in order to identify the find partial results to continue searching from where the previous operation (whether <b>start |
| `stopFind` | bool | If true, the find associated to the input <font face="courier" height="10">searchID</font> will be terminated instead of returning any further results. If false |

**响应（output）：**

```json
{
  "modelViewsByStructureNodes": [
    {
      "structureNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "resultingViews": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "csIdContextOccurrence": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clonestableId": [
        ""
      ]
    }
  ],
  "finished": "",
  "structureNodesSearched": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `modelViewsByStructureNodes` | Teamcenter::Soa::Cad::_2016_03::StructureManagement::StructureNodeResults[] | A list of  proxy objects found for various  nodes in the structure - the structure nodes may be bomlines, item revisions or design elements depending on the typ |
| `finished` | bool | Flag to indicate if the find operation is complete or if there is more content or structure to be searched. If false, then the <b>continueFindModelViews</b> ope |
| `structureNodesSearched` | int | Total number of structure nodes ( <b>BomLines</b> or Design Elements) which were so far searched for model views. This shows how large the structure is as the s |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains a list of any errors which occurred during the operation. |

---

##### 2.3.10.2 continueReconcilePalette

**接口路径：** `Cad-2016-09-StructureManagement/continueReconcilePalette`

**API 版本：** `2016-09`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 继续模型视图面板与产品结构的协调过程。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_09.StructureManagement.continueReconcilePalette`

**请求（input）：**

```json
{
  "reconcilePaletteInput": {
    "clientID": "",
    "mvProxiesOrMvGroups": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "stopReconcile": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `reconcilePaletteInput` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::NextReconcilePaletteInput | Input that contains the reconciliation state identifier and the <b>Fnd0ModelViewProxy</b> if they have to prioritized for reconciliation. |

**响应（output）：**

```json
{
  "palMVPReconcileInfos": [
    {
      "paletteMVP": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "reconcileInfos": [
        {
          "candidateMVP": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "reconcileActionEnum": "",
          "reconcileAction": "",
          "reconcileReason": "",
          "candidateStructNodeInfos": [
            {
              "structNode": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cloneStableIdChain": [
                ""
              ],
              "csIdContextOccurrence": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ]
    }
  ],
  "clientID": "",
  "finished": "",
  "configurationMisMatch": "",
  "origConfigInfo": {
    "configWindow": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revisionRule": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revRuleConfigEntriesAsStrings": [
      ""
    ],
    "configOptions": [
      {
        "optionName": "",
        "boolValues": [],
        "doubleValues": [],
        "intValues": [],
        "strValues": [
          ""
        ],
        "dateValues": [
          "0001-01-01T00:00:00"
        ],
        "refValues": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    ],
    "variantRules": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "reconcileConfigInfo": {
    "configWindow": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revisionRule": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revRuleConfigEntriesAsStrings": [
      ""
    ],
    "configOptions": [
      {
        "optionName": "",
        "boolValues": [],
        "doubleValues": [],
        "intValues": [],
        "strValues": [
          ""
        ],
        "dateValues": [
          "0001-01-01T00:00:00"
        ],
        "refValues": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    ],
    "variantRules": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "estimatedMVPsLeft": "",
  "percentComplete": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `palMVPReconcileInfos` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::PaletteModelViewProxyReconcileInfo[] | A list of <font face="courier" height="10">PaletteModelViewProxyReconcileInfo</font>, one for each <b>Fnd0ModelViewProxy</b>  on the <b>Fnd0ModelViewPalette</b> |
| `clientID` | std::string | A unique clientId passed by the client to correlate multiple subsequent <font face="courier" height="10">continueReconcilePalette</font> operations . |
| `finished` | bool | True if the reconciliation is complete. |
| `configurationMisMatch` | bool | Returned as true during <font face="courier" height="10">startReconcilePalette</font> if there is a configuration mismatch between the product configuration ass |
| `origConfigInfo` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::ConfigurationDisplayInfo | The configuration information that is associated to the <b>Fnd0ModelViewPalette</b>, presented in a form that can be directly displayed to the user. |
| `reconcileConfigInfo` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::ConfigurationDisplayInfo | The configuration information for the current structure that is used for reconciliation. |
| `estimatedMVPsLeft` | int | The number of <b>Fnd0ModelViewProxy</b> objects remaining to be reconciled. |
| `percentComplete` | double | The percentage of total <b>Fnd0ModelViewProxy</b> objects on the <b>Fnd0ModelViewPalette</b> where reconciliation is complete. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">ServiceData</font> is used to communicate partial errors to the client. |

---

##### 2.3.10.3 startFindModelViews

**接口路径：** `Cad-2016-09-StructureManagement/startFindModelViews`

**API 版本：** `2016-09`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 启动模型视图搜索（大批量时分页，需配合 continueFindModelViews）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_09.StructureManagement.startFindModelViews`

**请求（input）：**

```json
{
  "findInput": {
    "searchID": "",
    "disclosure": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "startingScopes": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "configurationContext": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "withDisclosureIntents": [
      ""
    ],
    "options": {}
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `findInput` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::FindModelViewsInput | The inputs needed to start a find operation on one or more objects that support model views. |

**响应（output）：**

```json
{
  "modelViewsByStructureNodes": [
    {
      "structureNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "resultingViews": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "csIdContextOccurrence": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clonestableId": [
        ""
      ]
    }
  ],
  "finished": "",
  "structureNodesSearched": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `modelViewsByStructureNodes` | Teamcenter::Soa::Cad::_2016_03::StructureManagement::StructureNodeResults[] | A list of  proxy objects found for various  nodes in the structure - the structure nodes may be bomlines, item revisions or design elements depending on the typ |
| `finished` | bool | Flag to indicate if the find operation is complete or if there is more content or structure to be searched. If false, then the <b>continueFindModelViews</b> ope |
| `structureNodesSearched` | int | Total number of structure nodes ( <b>BomLines</b> or Design Elements) which were so far searched for model views. This shows how large the structure is as the s |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains a list of any errors which occurred during the operation. |

---

##### 2.3.10.4 startReconcilePalette

**接口路径：** `Cad-2016-09-StructureManagement/startReconcilePalette`

**API 版本：** `2016-09`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 开始对模型视图面板中的代理引用与产品结构进行协调（Reconcile）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_09.StructureManagement.startReconcilePalette`

**请求（input）：**

```json
{
  "reconcilePaletteInput": {
    "clientID": "",
    "paletteOrDisclosingObject": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "mvProxiesOrMvGroups": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "doEntirePalette": "",
    "configRecipe": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `reconcilePaletteInput` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::ReconcilePaletteInput | Input that contains the <b>Fnd0ModelViewPalette</b> or <b>Fnd0ModelViewProxy</b> that needs to be reconciled and the configuration information. |

**响应（output）：**

```json
{
  "palMVPReconcileInfos": [
    {
      "paletteMVP": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "reconcileInfos": [
        {
          "candidateMVP": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "reconcileActionEnum": "",
          "reconcileAction": "",
          "reconcileReason": "",
          "candidateStructNodeInfos": [
            {
              "structNode": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cloneStableIdChain": [
                ""
              ],
              "csIdContextOccurrence": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ]
    }
  ],
  "clientID": "",
  "finished": "",
  "configurationMisMatch": "",
  "origConfigInfo": {
    "configWindow": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revisionRule": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revRuleConfigEntriesAsStrings": [
      ""
    ],
    "configOptions": [
      {
        "optionName": "",
        "boolValues": [],
        "doubleValues": [],
        "intValues": [],
        "strValues": [
          ""
        ],
        "dateValues": [
          "0001-01-01T00:00:00"
        ],
        "refValues": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    ],
    "variantRules": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "reconcileConfigInfo": {
    "configWindow": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revisionRule": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revRuleConfigEntriesAsStrings": [
      ""
    ],
    "configOptions": [
      {
        "optionName": "",
        "boolValues": [],
        "doubleValues": [],
        "intValues": [],
        "strValues": [
          ""
        ],
        "dateValues": [
          "0001-01-01T00:00:00"
        ],
        "refValues": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    ],
    "variantRules": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "estimatedMVPsLeft": "",
  "percentComplete": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `palMVPReconcileInfos` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::PaletteModelViewProxyReconcileInfo[] | A list of <font face="courier" height="10">PaletteModelViewProxyReconcileInfo</font>, one for each <b>Fnd0ModelViewProxy</b>  on the <b>Fnd0ModelViewPalette</b> |
| `clientID` | std::string | A unique clientId passed by the client to correlate multiple subsequent <font face="courier" height="10">continueReconcilePalette</font> operations . |
| `finished` | bool | True if the reconciliation is complete. |
| `configurationMisMatch` | bool | Returned as true during <font face="courier" height="10">startReconcilePalette</font> if there is a configuration mismatch between the product configuration ass |
| `origConfigInfo` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::ConfigurationDisplayInfo | The configuration information that is associated to the <b>Fnd0ModelViewPalette</b>, presented in a form that can be directly displayed to the user. |
| `reconcileConfigInfo` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::ConfigurationDisplayInfo | The configuration information for the current structure that is used for reconciliation. |
| `estimatedMVPsLeft` | int | The number of <b>Fnd0ModelViewProxy</b> objects remaining to be reconciled. |
| `percentComplete` | double | The percentage of total <b>Fnd0ModelViewProxy</b> objects on the <b>Fnd0ModelViewPalette</b> where reconciliation is complete. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">ServiceData</font> is used to communicate partial errors to the client. |

---

#### 版本 2018-06

##### 2.3.11.1 writeAssemblyConfigurationDetails

**接口路径：** `Cad-2018-06-StructureManagement/writeAssemblyConfigurationDetails`

**API 版本：** `2018-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 写入装配配置明细（Assembly Configuration Details）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2018_06.StructureManagement.writeAssemblyConfigurationDetails`

**请求（input）：**

```json
{
  "bomWindow": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "optionSetName": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `bomWindow` | Teamcenter::BusinessObject | The BOM Window of the structure and its children whose content will be written to the XML file. |
| `optionSetName` | std::string | The name of the Teamcenter Import/Export Option Set to be used to process/traverse the Product Structure of the input bomWindow. |

**响应（output）：**

```json
{
  "readFileTicketForStructureData": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `readFileTicketForStructureData` | std::string | This is the FMS read file ticket for the TC XML data file written to the transient volume. The TC XML file can be downloaded using this ticket. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This service data contains any partial errors which may have been encountered during processing. The partial error client Ids match the client Id for the input  |

---

#### 版本 2019-06

##### 2.3.12.1 createOrReConfigureBOMWindows

**接口路径：** `Cad-2019-06-StructureManagement/createOrReConfigureBOMWindows`

**API 版本：** `2019-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或按新配置重新配置 BOM 窗口（含有效性、变型等配置上下文）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2019_06.StructureManagement.createOrReConfigureBOMWindows`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "bomWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomWinPropFlagMap": {},
      "item": "{{ROOT_BOM_ITEM_UID}}",
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomView": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revRuleConfigInfo": {
        "clientId": "",
        "revRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "props": {
          "unitNo": "",
          "date": "0001-01-01T00:00:00",
          "today": "",
          "endItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "endItemRevision": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "overrideFolders": [
            {
              "ruleEntry": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "folder": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      },
      "objectsForConfigure": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "activeAssemblyArrangement": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "configContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "effGrpRevList": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2019_06::StructureManagement::CreateWindowsInfo3[] | A list of objects containing window creation information. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "bomWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomLine": {
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
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateBOMWindowsOutput[] | List of CreateBOMWindowsOutput which contains created BOMWindow object and top line BOMLine object representing the item or item revision along with the client  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, Servi |

---

#### 版本 2023-06

##### 2.3.13.1 expandPSOneLevel2

**接口路径：** `Cad-2023-06-StructureManagement/expandPSOneLevel2`

**API 版本：** `2023-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 展开产品结构一层（增强版接口，返回结构有所扩展）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2023_06.StructureManagement.expandPSOneLevel2`

**请求（input）：**

```json
{
  "info": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None2"
  },
  "prefs": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relatedObjAndNamedRefs": [
          {
            "objectTypeName": "",
            "namedReferenceNames": [
              ""
            ]
          }
        ],
        "namedRefHandler": "UseNamedRefsList"
      }
    ],
    "includeOccurrenceTypes": [
      ""
    ],
    "excludeOccurrenceTypes": [
      ""
    ],
    "expandSettings": {}
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSOneLevelInfo | A list of parent <b>BOMLine</b> objects to expand, a filter that describes what child <b>BOMLine</b> objects are excluded in the expansion, and a filter that de |
| `prefs` | Teamcenter::Soa::Cad::_2023_06::StructureManagement::ExpandPSOneLevelPref | Contains a flag for expanding <b>BOMLine</b> object further and a list describing the relation name, related object type and named references that help define t |

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "objectOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentRelatedObjects": [
          {
            "relatedObject": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "namedRefList": [
              {
                "namedReferenceType": "",
                "namedReferenceName": "",
                "referenceObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "fileTicket": ""
              }
            ]
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "objectOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relatedObjects": [
            {
              "relatedObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedRefList": [
                {
                  "namedReferenceType": "",
                  "namedReferenceName": "",
                  "referenceObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "fileTicket": ""
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSOneLevelOutput[] | List of ExpandPSOneLevelOutput structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, all o |

---

#### 版本 2023-12

##### 2.3.14.1 createOrUpdateAbsoluteStructure

**接口路径：** `Cad-2023-12-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2023-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新绝对坐标系下的产品结构（绝对变换/绝对定位语义）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2023_12.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "absOccInfos": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "boundingBoxInfo": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boundingBoxVector": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "datasetAttachments": [
              {
                "clientId": "",
                "datasetInfo": {
                  "clientId": "",
                  "dataset": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "namedReferencePreference": "",
                  "dataList": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ],
                  "datasetFileInfos": [
                    {
                      "clientId": "",
                      "fileName": "",
                      "namedReferencedName": "",
                      "isText": "",
                      "allowReplace": "",
                      "boundingBoxesAvailable": "",
                      "boundingBoxes": [
                        {
                          "xmin": "",
                          "ymin": "",
                          "zmin": "",
                          "xmax": "",
                          "ymax": "",
                          "zmax": ""
                        }
                      ]
                    }
                  ],
                  "namedReferenceObjectInfos": [
                    {
                      "clientId": "",
                      "object": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "namedReferenceName": "",
                      "typeName": "",
                      "dataNameValuePairs": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ]
                    }
                  ],
                  "name": "",
                  "basisName": "",
                  "description": "",
                  "type": "",
                  "lastModifiedOfDataset": "0001-01-01T00:00:00",
                  "id": "",
                  "datasetRev": "",
                  "createNewVersion": ""
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "formAttachments": [
              {
                "clientId": "",
                "formInfo": {
                  "formObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "name": "",
                  "description": "",
                  "formType": "",
                  "attributes": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ]
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "clientIdOfUsedArrangement": ""
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "arrangementType": "isDefault",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boundingBoxInfo": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "boundingBoxVector": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  }
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "overrideObject": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "overrideObject": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "datasetAttachments": [
                  {
                    "clientId": "",
                    "datasetInfo": {
                      "clientId": "",
                      "dataset": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "namedReferencePreference": "",
                      "dataList": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ],
                      "datasetFileInfos": [
                        {
                          "clientId": "",
                          "fileName": "",
                          "namedReferencedName": "",
                          "isText": "",
                          "allowReplace": "",
                          "boundingBoxesAvailable": "",
                          "boundingBoxes": [
                            {
                              "xmin": "",
                              "ymin": "",
                              "zmin": "",
                              "xmax": "",
                              "ymax": "",
                              "zmax": ""
                            }
                          ]
                        }
                      ],
                      "namedReferenceObjectInfos": [
                        {
                          "clientId": "",
                          "object": {
                            "uid": "",
                            "type": "",
                            "className": ""
                          },
                          "namedReferenceName": "",
                          "typeName": "",
                          "dataNameValuePairs": [
                            {
                              "name": "",
                              "values": [
                                ""
                              ]
                            }
                          ]
                        }
                      ],
                      "name": "",
                      "basisName": "",
                      "description": "",
                      "type": "",
                      "lastModifiedOfDataset": "0001-01-01T00:00:00",
                      "id": "",
                      "datasetRev": "",
                      "createNewVersion": ""
                    },
                    "relationTypeName": "",
                    "createIfFound": ""
                  }
                ],
                "formAttachments": [
                  {
                    "clientId": "",
                    "formInfo": {
                      "formObject": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "name": "",
                      "description": "",
                      "formType": "",
                      "attributes": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ]
                    },
                    "relationTypeName": "",
                    "createIfFound": ""
                  }
                ],
                "clientIdOfUsedArrangement": ""
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": "",
    "overridesToSynchronize": [
      ""
    ],
    "relationFilters": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ],
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccInfos` | Teamcenter::Soa::Cad::_2023_12::StructureManagement::CreateOrUpdateAbsoluteStructureInfo4[] | List of information related to the absolute occurrences that need to be created or updated. |
| `bomViewTypeName` | std::string | The BOM view (BV) type used to find the existing BOM view. |
| `pref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateOrUpdateAbsoluteStructurePref3 | The structure for setting specific preference input used by this operation. |

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrangementOutput": {},
  "formOutput": {},
  "datasetOutput": [
    {
      "clientId": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "commitInfo": [
        {
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "datasetFileTicketInfos": [
            {
              "datasetFileInfo": {
                "clientId": "",
                "fileName": "",
                "namedReferencedName": "",
                "isText": "",
                "allowReplace": "",
                "boundingBoxesAvailable": "",
                "boundingBoxes": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              },
              "ticket": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToAbsOccMap2 | A map (string, <b>AbsOccurrence</b>) of input clientId to the created, updated or found absolute occurrence. |
| `asmArrangementOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToAsmArrangementMap | A map (string, list of <b>AssemblyArrangement</b>) of input clientId to the created or updated assembly arrangement. |
| `formOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToFormMap | A map (string, <b>Form</b>) of input clientId to the created form. |
| `datasetOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::DatasetOutput[] | A list of created or updated <b>Dataset</b>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData. This operation will populate the ServiceData with created or updated PSOccurrence objects, <b>AssemblyArrangement</b> objects, <b>Dataset</b> o |

---

#### 版本 2024-12

##### 2.3.15.1 createOrUpdateRelativeStructure

**接口路径：** `Cad-2024-12-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2024-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2024_12.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "childBomViewTypeName": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "usageRevisionType": "",
            "moveInfo": {
              "commonParent": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "sourceAssembly": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "occThreadPathToBeMoved": [
                ""
              ],
              "occThreadPathTargetParent": [
                {
                  "parent": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "idType": "OccurrenceThread",
                  "id": "",
                  "isNew": ""
                }
              ]
            }
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2024_12::StructureManagement::CreateOrUpdateRelativeStructureInfo5[] | A list of input structures that defines all the occurrence for a given parent. |
| `pref` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::CreateOrUpdateRelativeStructurePref | Preference structure specific for this service. |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2024_12::StructureManagement::ClientIdToOccurrenceMap2 | A map(std::string, <font face="courier" height="10">MappedReturnData2</font>) of client IDs to <font face="courier" height="10">MappedReturnData2</font>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">ServiceData</font>. This operation will populate the <font face="courier" height="10">ServiceData</font> with created occur |

---

#### 版本 2025-06

##### 2.3.16.1 createOrUpdateRelativeStructure

**接口路径：** `Cad-2025-06-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2025-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2025_06.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "childBomViewTypeName": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "usageRevisionType": "",
            "preAllocatedPsOccThreadUid": "",
            "moveInfo": {
              "commonParent": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "sourceAssembly": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "occThreadPathToBeMoved": [
                ""
              ],
              "occThreadPathTargetParent": [
                {
                  "parent": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "idType": "OccurrenceThread",
                  "id": "",
                  "isNew": ""
                }
              ]
            }
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2025_06::StructureManagement::CreateOrUpdateRelativeStructureInfo6[] | A list of input structures that defines all the occurrence for a given parent. |
| `pref` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::CreateOrUpdateRelativeStructurePref | Preference structure specific for this service. |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2024_12::StructureManagement::ClientIdToOccurrenceMap2 | A map(std::string, <font face="courier" height="10">MappedReturnData2</font>) of client IDs to <font face="courier" height="10">MappedReturnData2</font>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">ServiceData</font>. This operation will populate the <font face="courier" height="10">ServiceData</font> with created occur |

---

---

## 3. 按 API 版本（年-月）归档

按时间线列出各版本契约下的全部接口（与第 2 节内容一致，便于按版本检索）。

### 3.1 API 版本 2007-01

**Service：** DataManagement、StructureManagement  **操作数：** 20

#### 3.1.1 createOrUpdateParts（2007-01）

**接口路径：** `Cad-2007-01-DataManagement/createOrUpdateParts`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "attrList": [
            {
              "name": "",
              "value": ""
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "value": ""
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": ""
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "name": "",
          "description": "",
          "type": "",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": "",
          "createNewVersion": "",
          "namedReferencePreference": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::DataManagement::PartInfo[] | A list of PartInfo structures |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": ""
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

#### 3.1.2 createOrUpdateRelations（2007-01）

**接口路径：** `Cad-2007-01-DataManagement/createOrUpdateRelations`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 在已有 Teamcenter 对象之间创建或更新 GRM（一般关系模型）关系。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.createOrUpdateRelations`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "relationType": "",
      "primaryObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "secondaryObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relation": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "userData": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "complete": "",
  "pref": {
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdateRelationsInfo[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>CreateOrUpdateRelationsInfo</font> |
| `complete` | bool | A flag to check whether any existing relations that pass the filter needs to be deleted. |
| `pref` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdateRelationsPref | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>RelationAndTypesFilter2</font> structure. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "relation": {
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
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdateRelationsOutput[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>CreateOrUpdateRelationsOutput</font> |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created or updated by the service and error information. Errors are identified by the <font face=&quot;cou |

---

#### 3.1.3 expandFoldersForCAD（2007-01）

**接口路径：** `Cad-2007-01-DataManagement/expandFoldersForCAD`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 为 CAD 客户端按文件夹层次展开对象，返回可在 CAD 环境中打开/集成的对象列表。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.expandFoldersForCAD`

**请求（input）：**

```json
{
  "folders": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "pref": {
    "expItemRev": "",
    "latestNRevs": "",
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `folders` | Teamcenter::Folder[] | A list of input TcEng folders |
| `pref` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandFolderForCADPref | Filter and expand preferences |

**响应（output）：**

```json
{
  "output": [
    {
      "inputFolder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "fstlvlFolders": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "itemsOutput": [
        {
          "outputItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevsOutput": [
            {
              "outputItemRevs": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "outputDatasets": [
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
      "itemRevsOutput": [
        {
          "outputItemRevs": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "outputDatasets": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandFoldersForCADOutput[] | A list of ExpandFoldersForCADOutput which has information about the input folder and folders, items and itemRevs output found under this folder |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and service errors/failure information |

---

#### 3.1.4 expandGRMRelations（2007-01）

**接口路径：** `Cad-2007-01-DataManagement/expandGRMRelations`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 按给定关系名称与对方对象类型过滤，展开输入对象的 GRM 关联从属对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.expandGRMRelations`

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
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of object references of objects of interest |
| `pref` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandGRMRelationsPref | A ExpandGRMRelationsPref structure |

**响应（output）：**

```json
{
  "output": [
    {
      "inputObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "otherSideObjData": [
        {
          "otherSideObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "relationName": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandGRMRelationsOutput[] | A list of ExpandGRMRelationsOutput which has information about the input object and it's filtered related object list |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and service errors/failure information |

---

#### 3.1.5 expandPrimaryObjects（2007-01）

**接口路径：** `Cad-2007-01-DataManagement/expandPrimaryObjects`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 按给定关系名称与对方对象类型过滤，展开输入对象的主对象侧关联对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.expandPrimaryObjects`

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
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of input TcEng object references and filter and expand preferences |
| `pref` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandPrimaryObjectsPref | A ExpandPrimaryObjectsPref structure |

**响应（output）：**

```json
{
  "output": [
    {
      "inputObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "otherSideObjData": [
        {
          "otherSideObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "relationName": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ExpandPrimaryObjectsOutput[] | A list of ExpandPrimaryObjectsOutput |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | SOA framework object containing objects that were found by the service and service errors/failure information |

---

#### 3.1.6 generateAlternateIds（2007-01）

**接口路径：** `Cad-2007-01-DataManagement/generateAlternateIds`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 生成备用编号（Alternate ID）列表。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.generateAlternateIds`

**请求（input）：**

```json
{
  "input": [
    {
      "idContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "pattern": "",
      "altIdType": "",
      "parentAltId": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "count": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2007_01::DataManagement::GenerateAlternateIdsProperties[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>GenerateAlternateIdsProperties</font>. |

**响应（output）：**

```json
{
  "inputIndexToAltId": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputIndexToAltId` | Teamcenter::Soa::Cad::_2007_01::DataManagement::IndexToAltId | Key is the index of the input, data is a list of alternate IDs generated. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data contains any partial errors and exceptions. No objects are created, deleted, modified or returned by this service. |

---

#### 3.1.7 getAllAttrMappings（2007-01）

**接口路径：** `Cad-2007-01-DataManagement/getAllAttrMappings`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 获取全部 CAD 属性映射（Attribute Mapping）定义。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.getAllAttrMappings`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "attrMappingInfos": [
    {
      "cadAttrMappingDefinition": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propDesc": {
        "propName": "",
        "displayName": "",
        "isModifiable": "",
        "attachedSpecifier": "",
        "maxLength": "",
        "interdependentProps": [
          ""
        ],
        "defaultValue": "",
        "propValueType": "",
        "propType": "",
        "isDisplayable": "",
        "isArray": "",
        "lov": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isRequired": "",
        "isEnabled": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `attrMappingInfos` | Teamcenter::Soa::Cad::_2007_01::DataManagement::AttrMappingInfo[] | A list of AttrMappingInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. CadAttrMappingDefinitio |

---

#### 3.1.8 getAttrMappingsForDatasetType（2007-01）

**接口路径：** `Cad-2007-01-DataManagement/getAttrMappingsForDatasetType`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 获取指定数据集类型（及 Item 类型组合）的 CAD 属性映射定义。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.getAttrMappingsForDatasetType`

**请求（input）：**

```json
{
  "info": [
    {
      "datasetTypeName": "",
      "itemTypeName": "",
      "exact": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::DataManagement::GetAttrMappingsForDatasetTypeCriteria[] | A list of dataset and item types used to get a specific set of attribute mapping definitions from the all of the attribute mapping definitions in Teamcenter. |

**响应（output）：**

```json
{
  "output": [
    {
      "criteria": {
        "datasetTypeName": "",
        "itemTypeName": "",
        "exact": ""
      },
      "attrMappingInfos": [
        {
          "cadAttrMappingDefinition": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "propDesc": {
            "propName": "",
            "displayName": "",
            "isModifiable": "",
            "attachedSpecifier": "",
            "maxLength": "",
            "interdependentProps": [
              ""
            ],
            "defaultValue": "",
            "propValueType": "",
            "propType": "",
            "isDisplayable": "",
            "isArray": "",
            "lov": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "isRequired": "",
            "isEnabled": ""
          }
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::GetAttrMappingsForDatasetTypeOutput[] | A list of input dataset and item type criteria and the found attribute mapping definitions. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

#### 3.1.9 getAvailableTypes（2007-01）

**接口路径：** `Cad-2007-01-DataManagement/getAvailableTypes`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 根据输入类名查询其实现/可用的业务对象类型列表。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.getAvailableTypes`

**请求（input）：**

```json
{
  "classes": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `classes` | std::string[] | A list of the classes to return subtypes for |

**响应（output）：**

```json
{
  "inputClassToTypes": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputClassToTypes` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ClassToTypesMap | Map where the key is the class type and the value is a list of strings representing the types available for the class. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains objects that are returned by the service, and error information. The actual type objects are returned as <font face=&quot;courier&quot; height=&quot;10 |

---

#### 3.1.10 resolveAttrMappingsForDataset（2007-01）

**接口路径：** `Cad-2007-01-DataManagement/resolveAttrMappingsForDataset`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 解析一个或多个数据集上的 CAD 属性映射，返回映射后的属性值。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.resolveAttrMappingsForDataset`

**请求（input）：**

```json
{
  "info": [
    {
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "cadAttrMappingDefinitions": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ResolveAttrMappingsForDatasetInfo[] | An array of <font face=&quot;courier&quot; height=&quot;10&quot;>ResolveAttrMappingsForDatasetInfo</font> structures each containing a <b>Dataset</b> object ref |

**响应（output）：**

```json
{
  "output": [
    {
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "mappedProperties": [
        {
          "attrTitle": "",
          "datasetTypeName": "",
          "itemTypeName": "",
          "resolvedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "resolvedPropertyName": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::ResolveAttrMappingsForDatasetOutput[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>ResolveAttrMappingsForDatasetOutput</font> |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font> contains any partial errors and exceptions.<br />The objects holding the mapped attribut |

---

#### 3.1.11 closeBOMWindows（2007-01）

**接口路径：** `Cad-2007-01-StructureManagement/closeBOMWindows`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 关闭一个或多个 BOM 窗口，释放服务器端产品结构资源。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.closeBOMWindows`

**请求（input）：**

```json
{
  "bomWindows": [
    "{{ROOT_BOM_ITEM_BOM_WINDOW_UID}}"
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `bomWindows` | Teamcenter::BOMWindow[] | The BOMWindow to close |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, Servi |

---

#### 3.1.12 createBOMWindows（2007-01）

**接口路径：** `Cad-2007-01-StructureManagement/createBOMWindows`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 为指定 Item 创建 BOM 窗口，将对应 ItemRevision 设为顶行，返回 BOM 窗口 UID 与根 BOMLine；BOM 操作建议使用无状态（stateless）连接。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.createBOMWindows`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "item": "{{ROOT_BOM_ITEM_UID}}",
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomView": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revRuleConfigInfo": {
        "clientId": "",
        "revRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "props": {
          "unitNo": "",
          "date": "0001-01-01T00:00:00",
          "today": "",
          "endItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "endItemRevision": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "overrideFolders": [
            {
              "ruleEntry": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "folder": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      },
      "objectForConfigure": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "activeAssemblyArrangement": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateBOMWindowsInfo[] | Input is an item or item Revision object |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "bomWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomLine": {
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
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateBOMWindowsOutput[] | List of CreateBOMWindowsOutput which contains created BOMWindow object and top line BOMLine object representing the item or item revision along with the client  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, Servi |

---

#### 3.1.13 createOrUpdateAbsoluteStructure（2007-01）

**接口路径：** `Cad-2007-01-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新绝对坐标系下的产品结构（绝对变换/绝对定位语义）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "info": [
    {
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "clientIdOfUsedArrangement": "",
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            }
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "isDefault": "",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "clientIdOfUsedArrangement": "",
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateOrUpdateAbsoluteStructureInfo[] | List of input structures that defines all the occurrence for a given parent |
| `bomViewTypeName` | std::string | Type of BOMView |
| `complete` | bool | Flag that if true signifies that the structure represented in the input is the full representation of the structure under the input parent. Any other structure  |
| `pref` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateOrUpdateAbsoluteStructurePref | preference structure specific for this service |

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccOutput` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToAbsOccMap | Map of input clientId for the absolute occurrence to created/updated/found absolute occurrence |
| `asmArrOutput` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToAsmArrMap | Map of input client id to created/updated/found AssemblyArrangement |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData contains any other created (AbsOccData, AbsOccDataQualifier), updated (like BVR), relevant related, or deleted objects from this operation. |

---

#### 3.1.14 createOrUpdateRelativeStructure（2007-01）

**接口路径：** `Cad-2007-01-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ],
      "precise": ""
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "cadOccIdAttrName": "",
    "itemTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateOrUpdateRelativeStructureInfo[] | List of input structures that defines all the occurrence for a given parent |
| `bomViewTypeName` | std::string | Type of BOMView to create |
| `complete` | bool | Flag that if true signifies that the structure represented in the input is the full representation of the structure under the input parent.  Any other structure |
| `pref` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateOrUpdateRelativeStructurePref | Preference structure specific for this service |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToPSOccurrenceThreadMap | Member of type ClientIdToPSOccurrenceThreadMap |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Mwmber of type Teamcenter::Soa::Server::ServiceData serviceData |

---

#### 3.1.15 deleteAssemblyArrangements（2007-01）

**接口路径：** `Cad-2007-01-StructureManagement/deleteAssemblyArrangements`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除装配配置（Assembly Arrangement）相关结构数据。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.deleteAssemblyArrangements`

**请求（input）：**

```json
{
  "info": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "arrangements": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "bomViewTypeName": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::DeleteAssemblyArrangementsInfo[] | Input is bvr and list of assembly arrangements to delete |
| `bomViewTypeName` | std::string | The BOM view type name |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

#### 3.1.16 deleteRelativeStructure（2007-01）

**接口路径：** `Cad-2007-01-StructureManagement/deleteRelativeStructure`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除相对产品结构中的指定结构关系或子结构。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.deleteRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        ""
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::DeleteRelativeStructureInfo[] | List input of structures that defines the parent and first level children to be deleted. |
| `bomViewTypeName` | std::string | Qualifies the specified parent item revision(s) to identify a unique BOM view revision. |
| `pref` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::DeleteRelativeStructurePref | Preference structure specific for this service |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

#### 3.1.17 expandPSAllLevels（2007-01）

**接口路径：** `Cad-2007-01-StructureManagement/expandPSAllLevels`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 从产品结构（PS）指定父 BOMLine 递归展开全部层级，返回完整 BOM 树。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.expandPSAllLevels`

**请求（input）：**

```json
{
  "input": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSAllLevelsInfo | of  ExpandPSAllLevelsInfo which contains parent bom lines and a filter of the type of bom lines to exclude. |
| `pref` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSAllLevelsPref | of a ExpandPSAllLevelsPref which contains a list of relation name and the types of objects of the given relation to return along with the children. |

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemRevOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentDatasets": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "datasets": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSAllLevelsOutput[] | List of ExpandPSAllLevelsOutput which contains ExpandPSParentData and list of ExpandPSData |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, all o |

---

#### 3.1.18 expandPSOneLevel（2007-01）

**接口路径：** `Cad-2007-01-StructureManagement/expandPSOneLevel`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 从产品结构父 BOMLine 仅展开下一层子 BOMLine。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.expandPSOneLevel`

**请求（input）：**

```json
{
  "input": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSOneLevelInfo | of  ExpandPSOneLevelInfo which contains parent bom lines and a filter of the type of bom lines to exclude. |
| `pref` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSOneLevelPref | of a ExpandPSOneLevelPref which contains a list of relation name and the types of objects of the given relation to return along with the children. |

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemRevOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentDatasets": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "datasets": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ExpandPSOneLevelOutput[] | List of ExpandPSOneLevelOutput which contains ExpandPSParentData and list of ExpandPSData |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, all o |

---

#### 3.1.19 getRevisionRules（2007-01）

**接口路径：** `Cad-2007-01-StructureManagement/getRevisionRules`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 获取系统可用的版本规则（Revision Rule）列表，用于 BOM 有效性配置。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.getRevisionRules`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "output": [
    {
      "revRule": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "hasValueStatus": {},
      "overrideFolders": [
        {
          "ruleEntry": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "folder": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::RevisionRuleInfo[] | List of RevisionRuleInfo which contains Revision rule, configure attribute status along with override information |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error |

---

#### 3.1.20 getVariantRules（2007-01）

**接口路径：** `Cad-2007-01-StructureManagement/getVariantRules`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 获取变型规则（Variant Rule）及相关配置信息。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.getVariantRules`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `itemRevs` | Teamcenter::ItemRevision[] | List of object references of ItemRevisions to get variant rules for |

**响应（output）：**

```json
{
  "inputItemRevToVarRules": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputItemRevToVarRules` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ItemRevisionToVariantRulesMap | Holds map of itemRevision to list of VariantRules. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData |

---

### 3.2 API 版本 2007-06

**Service：** StructureManagement  **操作数：** 5

#### 3.2.1 createOrUpdateClassicOptions（2007-06）

**接口路径：** `Cad-2007-06-StructureManagement/createOrUpdateClassicOptions`

**API 版本：** `2007-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新经典变型选项（Classic Option）及其选项值，并声明到 ItemRevision。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_06.StructureManagement.createOrUpdateClassicOptions`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "clientId": "",
      "operation": "CreateOption",
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "options": [
        {
          "optionName": "",
          "optionDesc": "",
          "values": [
            ""
          ],
          "existingValues": [
            ""
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputObjects` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::CreateUpdateClassicOptionsInput[] | Refers to the list of CreateUpdateClassicOptionsInput struct, which are used to create a new variant option or update an existing variant option. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.2 createOrUpdateVariantConditions（2007-06）

**接口路径：** `Cad-2007-06-StructureManagement/createOrUpdateVariantConditions`

**API 版本：** `2007-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 为 BOMLine 创建或更新变型条件（load_if 类型的变型表达式）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_06.StructureManagement.createOrUpdateVariantConditions`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "clientId": "",
      "operation": "Create",
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "variantCondInfo": [
        {
          "optionName": "",
          "joinOperator": "AND",
          "compOperator": "EQ",
          "value": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputObjects` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::CreateOrUpdateVariantCondInput[] | This has the list of <font face="courier" height="10">CreateOrUpdateVariantCondInput</font> struct, which are used to create a new variant condition or update a |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.3 deleteClassicOptions（2007-06）

**接口路径：** `Cad-2007-06-StructureManagement/deleteClassicOptions`

**API 版本：** `2007-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除经典变型选项及其全部关联选项值。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_06.StructureManagement.deleteClassicOptions`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "clientId": "",
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "optionNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputObjects` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::DelClassicOptionsInput[] | A list of DelClassicOptionsInput structures, each of which contains a bomline tag, and list of options. If the option exists then it will be deleted. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.4 deleteVariantConditions（2007-06）

**接口路径：** `Cad-2007-06-StructureManagement/deleteVariantConditions`

**API 版本：** `2007-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除 BOMLine 上关联的变型条件（load_if）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_06.StructureManagement.deleteVariantConditions`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "clientId": "",
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputObjects` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::DeleteVariantCondInput[] | Consists of the clientId and the BOMLine for which we need to delete the variant Condition |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.5 getConfiguredItemRevision（2007-06）

**接口路径：** `Cad-2007-06-StructureManagement/getConfiguredItemRevision`

**API 版本：** `2007-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 按指定版本规则配置后，解析 Item/ItemRevision 对应的有效版本。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_06.StructureManagement.getConfiguredItemRevision`

**请求（input）：**

```json
{
  "inputs": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revRule": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::GetConfiguredItemRevisionInfo[] | A list of GetConfiguredItemRevisionInfo structures, each of which contain a item or item revision object and revision rule. |

**响应（output）：**

```json
{
  "output": [
    {
      "inputInfo": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revRule": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "configuredItemRev": {
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
| `output` | Teamcenter::Soa::Cad::_2007_06::StructureManagement::GetConfiguredItemRevisionOutput[] | A List of type GetConfiguredItemRevisionOutput |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing plain objects and error information. |

---

### 3.3 API 版本 2007-09

**Service：** StructureManagement  **操作数：** 1

#### 3.3.1 createOrUpdateVariantConditions2（2007-09）

**接口路径：** `Cad-2007-09-StructureManagement/createOrUpdateVariantConditions2`

**API 版本：** `2007-09`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新变型条件（增强版接口）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_09.StructureManagement.createOrUpdateVariantConditions2`

**请求（input）：**

```json
{
  "inputObjects": [
    {
      "clientId": "",
      "operation": "Create",
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "variantCondInfo": [
        {
          "optionName": "",
          "itemId": "",
          "joinOperator": "AND",
          "compOperator": "EQ",
          "value": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputObjects` | Teamcenter::Soa::Cad::_2007_09::StructureManagement::CreateOrUpdateVariantCondInput[] | This has the list of <font face="courier" height="10">CreateOrUpdateVariantCondInput</font> struct, which are used to create a new variant condition or update a |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.4 API 版本 2007-12

**Service：** DataManagement、StructureManagement  **操作数：** 7

#### 3.4.1 createOrUpdateParts（2007-12）

**接口路径：** `Cad-2007-12-DataManagement/createOrUpdateParts`

**API 版本：** `2007-12`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "value": ""
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "value": ""
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": ""
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_12::DataManagement::PartInfo2[] | A list of PartInfo2 structures |
| `pref` | Teamcenter::Soa::Cad::_2007_12::DataManagement::CreateOrUpdatePartsPref | A Struct which contains information whether dataset needs to be modified, if input last modified date is different from actual. |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": ""
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

#### 3.4.2 createOrUpdateAbsoluteStructure（2007-12）

**接口路径：** `Cad-2007-12-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新绝对坐标系下的产品结构（绝对变换/绝对定位语义）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "info": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "clientIdOfUsedArrangement": "",
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            }
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "isDefault": "",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "clientIdOfUsedArrangement": "",
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::CreateOrUpdateAbsoluteStructureInfo2[] | List of input structures that defines all the occurrence for a given parent |
| `bomViewTypeName` | std::string | Type of BOMView |
| `complete` | bool | flag that if true signifies that the structure represented in the input is the full representation of the structure under the input parent. Any other structure  |
| `pref` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::CreateOrUpdateAbsoluteStructurePref2 | preference structure specific for this service |

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccOutput` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToAbsOccMap | Map of input clientId for the absolute occurrence to created/updated/found absolute occurrence |
| `asmArrOutput` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToAsmArrMap | Map of input client id to created/updated/found AssemblyArrangement |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData contains any other created (AbsOccData, AbsOccDataQualifier), updated (like BVR), relevant related, or deleted objects from this operation. |

---

#### 3.4.3 createOrUpdateRelativeStructure（2007-12）

**接口路径：** `Cad-2007-12-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ],
      "precise": ""
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": "",
    "itemTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::CreateOrUpdateRelativeStructureInfo2[] | List of input structures that defines all the occurrence for a given parent |
| `bomViewTypeName` | std::string | Type of BOMView to create |
| `complete` | bool | Flag that if true signifies that the structure represented in the input is the full representation of the structure under the input parent.  Any other structure |
| `pref` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::CreateOrUpdateRelativeStructurePref2 | Preference structure specific for this service |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToPSOccurrenceThreadMap | Member of type ClientIdToPSOccurrenceThreadMap |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Mwmber of type Teamcenter::Soa::Server::ServiceData serviceData |

---

#### 3.4.4 deleteAssemblyArrangements（2007-12）

**接口路径：** `Cad-2007-12-StructureManagement/deleteAssemblyArrangements`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除装配配置（Assembly Arrangement）相关结构数据。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.deleteAssemblyArrangements`

**请求（input）：**

```json
{
  "info": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "arrangements": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::DeleteAssemblyArrangementsInfo2[] | List of item revisions and the assembly arrangements to delete from the found BOM view revision. |
| `bomViewTypeName` | std::string | The BOM view type used to find the existing BOM view object. |
| `pref` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::DeleteAssemblyArrangementsPref | The structure for setting specific preference input used by this operation. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

#### 3.4.5 deleteRelativeStructure（2007-12）

**接口路径：** `Cad-2007-12-StructureManagement/deleteRelativeStructure`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除相对产品结构中的指定结构关系或子结构。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.deleteRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        ""
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::DeleteRelativeStructureInfo2[] | List input of structures that defines the parent and first level children to be deleted. |
| `bomViewTypeName` | std::string | Qualifies the specified parent item revision(s) to identify a unique BOM   view revision. |
| `pref` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::DeleteRelativeStructurePref2 | Preference structure specific for this service |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

#### 3.4.6 queryClassicOptions（2007-12）

**接口路径：** `Cad-2007-12-StructureManagement/queryClassicOptions`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 查询 ItemRevision 上已定义的经典变型选项。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.queryClassicOptions`

**请求（input）：**

```json
{
  "inputRevisions": [
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
| `inputRevisions` | Teamcenter::ItemRevision[] | This is list of <b>ItemRevision</b> object on which variant options are to be queried. |

**响应（output）：**

```json
{
  "itemRevisionOptionData": [
    {
      "itemRevision": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "optionData": [
        {
          "optionName": "",
          "optionDesc": "",
          "values": [
            ""
          ],
          "existingValues": [
            ""
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `itemRevisionOptionData` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::ClassicOptionData[] | Refers to a list of <font face="courier" height="10">ClassicOptionData</font> struct, which has <b>ItemRevision</b> and corresponding classic variant option lis |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the service operation, plain objects, and error information. |

---

#### 3.4.7 queryVariantConditions（2007-12）

**接口路径：** `Cad-2007-12-StructureManagement/queryVariantConditions`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 查询 BOMLine 上的变型条件值。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.queryVariantConditions`

**请求（input）：**

```json
{
  "inputBomLines": [
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
| `inputBomLines` | Teamcenter::BOMLine[] | This has the list of <b>BOMLine</b> objects, on which variant condition are defined. |

**响应（output）：**

```json
{
  "variantConditions": [
    {
      "bomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "conditionClauses": [
        {
          "optionName": "",
          "itemId": "",
          "joinOperator": "AND",
          "compOperator": "EQ",
          "value": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `variantConditions` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::BomLineVariantCondition[] | Refers to a list of <font face="courier" height="10">BomLineVariantCondition</font> struct objects, contains the variant condition on <b>BOMLine</b> object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

### 3.5 API 版本 2008-03

**Service：** DataManagement、StructureManagement  **操作数：** 3

#### 3.5.1 createOrUpdateParts（2008-03）

**接口路径：** `Cad-2008-03-DataManagement/createOrUpdateParts`

**API 版本：** `2008-03`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_03.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "value": ""
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "value": ""
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": ""
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_03::DataManagement::PartInfo3[] | A list of PartInfo3 structures |
| `pref` | Teamcenter::Soa::Cad::_2007_12::DataManagement::CreateOrUpdatePartsPref | A Struct which contains information whether dataset needs to be modified, if input last modified date is different from actual. |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": ""
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

#### 3.5.2 resolveAttrMappings（2008-03）

**接口路径：** `Cad-2008-03-DataManagement/resolveAttrMappings`

**API 版本：** `2008-03`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 解析并返回 ItemRevision 或数据集上配置的 CAD 属性映射结果（属性值）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_03.DataManagement.resolveAttrMappings`

**请求（input）：**

```json
{
  "info": [
    {
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "mappingDefinitionInfos": [
        {
          "clientId": "",
          "cadAttrMappingDefinition": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_03::DataManagement::ResolveAttrMappingsInfo[] | An array of ResolveAttrMappingsInfo structures each containing a <b>Dataset</b> object reference, an optional item revision, and a list of corresponding CAD Att |

**响应（output）：**

```json
{
  "resolvedMappingsMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `resolvedMappingsMap` | Teamcenter::Soa::Cad::_2008_03::DataManagement::ResolveAttrMappingsOutputMap | Member of type <font face=&quot;courier&quot; height=&quot;10&quot;>ResolveAttrMappingsOutputMap</font>. This is a map containing the successfully mapped proper |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data contains any partial errors and exceptions. The objects holding the mapped attributes, resulting from successfully resolved mappings, are returned  |

---

#### 3.5.3 askChildPathBOMLines（2008-03）

**接口路径：** `Cad-2008-03-StructureManagement/askChildPathBOMLines`

**API 版本：** `2008-03`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 根据 PS 发生线程（Occurrence Thread）链描述的子路径，返回对应的 BOMLine 对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_03.StructureManagement.askChildPathBOMLines`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "parentBomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "useAsStable": "",
      "childPaths": [
        {
          "clientId": "",
          "childPath": [
            ""
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2008_03::StructureManagement::AskChildPathBOMLinesInfo[] | Specifies sets of product structure information each containing parent BOM line, based on a BOM Window opened by the client, and one or more child paths specifi |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_03::StructureManagement::AskChildPathBOMLineMap | A map of input PS Occurrence Thread UIDs to BOMLines. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing plain objects, and error information. |

---

### 3.6 API 版本 2008-06

**Service：** DataManagement、StructureManagement  **操作数：** 11

#### 3.6.1 createOrUpdateParts（2008-06）

**接口路径：** `Cad-2008-06-DataManagement/createOrUpdateParts`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "partInput": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": "",
              "boundingBoxesAvailable": "",
              "boundingBoxes": [
                {
                  "xmin": "",
                  "ymin": "",
                  "zmin": "",
                  "xmax": "",
                  "ymax": "",
                  "zmax": ""
                }
              ]
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `partInput` | Teamcenter::Soa::Cad::_2008_06::DataManagement::PartInfo[] | A list of PartInfo structures |
| `pref` | Teamcenter::Soa::Cad::_2007_12::DataManagement::CreateOrUpdatePartsPref | A Struct which contains information whether dataset needs to be modified, if input last modified date is different from actual |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": "",
                    "boundingBoxesAvailable": "",
                    "boundingBoxes": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

#### 3.6.2 expandFoldersForCAD（2008-06）

**接口路径：** `Cad-2008-06-DataManagement/expandFoldersForCAD`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 为 CAD 客户端按文件夹层次展开对象，返回可在 CAD 环境中打开/集成的对象列表。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.DataManagement.expandFoldersForCAD`

**请求（input）：**

```json
{
  "folders": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "pref": {
    "expItemRev": "",
    "latestNRevs": "",
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ],
    "contentTypesFilter": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `folders` | Teamcenter::Folder[] | A list of folders to expand. |
| `pref` | Teamcenter::Soa::Cad::_2008_06::DataManagement::ExpandFolderForCADPref2 | Filter and expand preferences |

**响应（output）：**

```json
{
  "output": [
    {
      "inputFolder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "fstlvlFolders": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "itemsOutput": [
        {
          "outputItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevsOutput": [
            {
              "outputItemRevs": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "outputDatasets": [
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
      "itemRevsOutput": [
        {
          "outputItemRevs": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "outputDatasets": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ],
      "contents": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::DataManagement::ExpandFoldersForCADOutput2[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>ExpandFoldersForCADOutput2</font> which has information about the input folder and folders, items |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains the folders, items, items revisions, datasets, and other object types in the list of plain objects. <br />Error information returned is identified by t |

---

#### 3.6.3 createOrUpdateAbsoluteStructure（2008-06）

**接口路径：** `Cad-2008-06-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新绝对坐标系下的产品结构（绝对变换/绝对定位语义）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "absOccInfos": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "boundingBoxInfo": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boundingBoxVector": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "datasetAttachments": [
              {
                "clientId": "",
                "datasetInfo": {
                  "clientId": "",
                  "dataset": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "namedReferencePreference": "",
                  "dataList": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ],
                  "datasetFileInfos": [
                    {
                      "clientId": "",
                      "fileName": "",
                      "namedReferencedName": "",
                      "isText": "",
                      "allowReplace": "",
                      "boundingBoxesAvailable": "",
                      "boundingBoxes": [
                        {
                          "xmin": "",
                          "ymin": "",
                          "zmin": "",
                          "xmax": "",
                          "ymax": "",
                          "zmax": ""
                        }
                      ]
                    }
                  ],
                  "namedReferenceObjectInfos": [
                    {
                      "clientId": "",
                      "object": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "namedReferenceName": "",
                      "typeName": "",
                      "dataNameValuePairs": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ]
                    }
                  ],
                  "name": "",
                  "basisName": "",
                  "description": "",
                  "type": "",
                  "lastModifiedOfDataset": "0001-01-01T00:00:00",
                  "id": "",
                  "datasetRev": "",
                  "createNewVersion": ""
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "formAttachments": [
              {
                "clientId": "",
                "formInfo": {
                  "formObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "name": "",
                  "description": "",
                  "formType": "",
                  "attributes": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ]
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "clientIdOfUsedArrangement": ""
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "isDefault": "",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "clientIdOfUsedArrangement": "",
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "overridesToSynchronize": [
      ""
    ],
    "relationFilters": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ],
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccInfos` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateOrUpdateAbsoluteStructureInfo3[] | List of information related to the absolute occurrences that need to be created or updated. |
| `bomViewTypeName` | std::string | The BOM view (BV) type used to find the existing BOM view. |
| `complete` | bool | Flag that if true signifies that the absolute occurrences represented in <font face=&quot;courier&quot; height=&quot;10&quot;>absOccInfos</font> are the full re |
| `pref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateOrUpdateAbsoluteStructurePref3 | The structure for setting specific preference input used by this operation. |

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrangementOutput": {},
  "formOutput": {},
  "datasetOutput": [
    {
      "clientId": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "commitInfo": [
        {
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "datasetFileTicketInfos": [
            {
              "datasetFileInfo": {
                "clientId": "",
                "fileName": "",
                "namedReferencedName": "",
                "isText": "",
                "allowReplace": "",
                "boundingBoxesAvailable": "",
                "boundingBoxes": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              },
              "ticket": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToAbsOccMap2 | A map (string, <b>AbsOccurrence</b>) of input clientId to the created, updated or found absolute occurrence. |
| `asmArrangementOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToAsmArrangementMap | A map (string, list of <b>AssemblyArrangement</b>) of input clientId to the created or updated assembly arrangement. |
| `formOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToFormMap | A map (string, <b>Form</b>) of input clientId to the created form. |
| `datasetOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::DatasetOutput[] | A list of created or updated <b>Dataset</b>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData. This operation will populate the ServiceData with created or updated PSOccurrence objects, <b>AssemblyArrangement</b> objects, <b>Dataset</b> o |

---

#### 3.6.4 createOrUpdateRelativeStructure（2008-06）

**接口路径：** `Cad-2008-06-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ],
      "precise": ""
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateOrUpdateRelativeStructureInfo3[] | List of input structures that defines all the occurrence for a given parent |
| `bomViewTypeName` | std::string | Type of BOMView to create |
| `complete` | bool | Flag that if true signifies that the structure represented in the input is the full representation of the structure under the input parent. Any other structure  |
| `pref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateOrUpdateRelativeStructurePref3 | Preference structure specific for this service |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::ClientIdToPSOccurrenceThreadMap | Member of type ClientIdToPSOccurrenceThreadMap |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Mwmber of type Teamcenter::Soa::Server::ServiceData serviceData |

---

#### 3.6.5 createVariantRules（2008-06）

**接口路径：** `Cad-2008-06-StructureManagement/createVariantRules`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 为经典变型选项创建已保存的变型规则（VariantRule）对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.createVariantRules`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "vruleName": "",
      "vruleDescription": "",
      "rev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relation": "",
      "options": [
        {
          "optionName": "",
          "optionValue": "",
          "assocRev": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateVariantRulesInfo[] | This has the list of <font face="courier" height="10">CreateVariantRulesInfo</font> struct, which are used to create a new <b>VariantRule</b> object. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "output": [
    {
      "clientId": "",
      "vrule": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the service and error information if any. |
| `output` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::VariantRulesOutput[] | Refers to a list of <font face="courier" height="10">VariantRulesOutput</font> struct objects, which in turn refers to newly created <b>VariantRule</b> objects. |

---

#### 3.6.6 deleteRelativeStructure（2008-06）

**接口路径：** `Cad-2008-06-StructureManagement/deleteRelativeStructure`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 删除相对产品结构中的指定结构关系或子结构。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.deleteRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        ""
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::DeleteRelativeStructureInfo3[] | List of input structures that specify the parent and first level children to be deleted. |
| `bomViewTypeName` | std::string | The BOM view<b> </b>(BV) type used to find the existing BOM view. |
| `pref` | Teamcenter::Soa::Cad::_2007_12::StructureManagement::DeleteRelativeStructurePref2 | The structure for setting specific preference input used by this operation. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

#### 3.6.7 expandPSAllLevels（2008-06）

**接口路径：** `Cad-2008-06-StructureManagement/expandPSAllLevels`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 从产品结构（PS）指定父 BOMLine 递归展开全部层级，返回完整 BOM 树。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.expandPSAllLevels`

**请求（input）：**

```json
{
  "info": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None2"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relatedObjAndNamedRefs": [
          {
            "objectTypeName": "",
            "namedReferenceNames": [
              ""
            ]
          }
        ],
        "namedRefHandler": "UseNamedRefsList"
      }
    ],
    "includeOccurrenceTypes": [
      ""
    ],
    "excludeOccurrenceTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSAllLevelsInfo | Input of ExpandPSAllLevelsInfo which contains parent bom lines and a filter of the type of bom lines to exclude. |
| `pref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSAllLevelsPref | of a ExpandPSAllLevelsPref which contains a list of relation name and the types of objects of the given relation to return along with the children. |

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "objectOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentRelatedObjects": [
          {
            "relatedObject": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "namedRefList": [
              {
                "namedReferenceType": "",
                "namedReferenceName": "",
                "referenceObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "fileTicket": ""
              }
            ]
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "objectOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relatedObjects": [
            {
              "relatedObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedRefList": [
                {
                  "namedReferenceType": "",
                  "namedReferenceName": "",
                  "referenceObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "fileTicket": ""
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSAllLevelsOutput[] | List of ExpandPSAllLevelsOutput1 which contains ExpandPSParentData and list of ExpandPSData |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, all o |

---

#### 3.6.8 expandPSOneLevel（2008-06）

**接口路径：** `Cad-2008-06-StructureManagement/expandPSOneLevel`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 从产品结构父 BOMLine 仅展开下一层子 BOMLine。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.expandPSOneLevel`

**请求（input）：**

```json
{
  "info": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None2"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relatedObjAndNamedRefs": [
          {
            "objectTypeName": "",
            "namedReferenceNames": [
              ""
            ]
          }
        ],
        "namedRefHandler": "UseNamedRefsList"
      }
    ],
    "includeOccurrenceTypes": [
      ""
    ],
    "excludeOccurrenceTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSOneLevelInfo | The list of parent BOM lines to expand, a filter that describes what child BOM lines are excluded in the expansion, and a filter that describes what named refer |
| `pref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSOneLevelPref | A flag for expanding BOM line object further and a list describing the relation name, related object type and named references that help define the expansion cr |

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "objectOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentRelatedObjects": [
          {
            "relatedObject": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "namedRefList": [
              {
                "namedReferenceType": "",
                "namedReferenceName": "",
                "referenceObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "fileTicket": ""
              }
            ]
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "objectOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relatedObjects": [
            {
              "relatedObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedRefList": [
                {
                  "namedReferenceType": "",
                  "namedReferenceName": "",
                  "referenceObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "fileTicket": ""
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSOneLevelOutput[] | List of ExpandPSOneLevelOutput structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, all o |

---

#### 3.6.9 getAbsoluteStructureData（2008-06）

**接口路径：** `Cad-2008-06-StructureManagement/getAbsoluteStructureData`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 获取已配置结构完全展开后的绝对结构数据（全展开 PS）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.getAbsoluteStructureData`

**请求（input）：**

```json
{
  "absOccDataQualInfos": [
    {
      "qualifyingBVR": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "upperQualifier": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "absOccDataPref": {
    "relationFilterInfos": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ],
    "qualifierFilter": "None"
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccDataQualInfos` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::AbsOccQualifierInfo[] | List of qualifying information for overrides |
| `absOccDataPref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::AbsOccDataPref | Preference on which relation overrides to expand and the preferred objects of type to return |

**响应（output）：**

```json
{
  "overrides": [
    {
      "occThreadPaths": [
        {
          "apn": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occThreadPath": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ],
      "dataOverrideInfo": {
        "overrideData": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "expandedOverrides": [
          {
            "relationName": "",
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
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `overrides` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::AbsOccStructureDataInfo[] | List of overrides |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains populated plain object list and partial errors. |

---

#### 3.6.10 reconfigureBOMWindows（2008-06）

**接口路径：** `Cad-2008-06-StructureManagement/reconfigureBOMWindows`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 按新的有效性、变型或版本规则等配置重新配置已有 BOM 窗口。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.reconfigureBOMWindows`

**请求（input）：**

```json
{
  "info": [
    {
      "clientID": "",
      "bomWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectForConfigure": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revRuleConfigInfo": {
        "clientId": "",
        "revRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "props": {
          "unitNo": "",
          "date": "0001-01-01T00:00:00",
          "today": "",
          "endItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "endItemRevision": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "overrideFolders": [
            {
              "ruleEntry": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "folder": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ReconfigureBOMWindowsInfo[] | This contains a list of <font face="courier" height="10">ReconfigureBOMWindowsInfo</font> struct objects which has <b>BOMWindow</b> objects and corresponding <b |

**响应（output）：**

```json
{
  "output": [
    {
      "clientID": "",
      "bomWindow": {
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
| `output` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ReconfigureBOMWindowsOutput[] | This contains list of <font face="courier" height="10">ReconfigureBOMWindowsOutput</font> struct object, which returns the <b>BOMWindow</b> which has updated co |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the service and error information if any. |

---

#### 3.6.11 saveBOMWindows（2008-06）

**接口路径：** `Cad-2008-06-StructureManagement/saveBOMWindows`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 保存 BOM 窗口中的结构修改（新增/更新/删除的 BOM 行等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.saveBOMWindows`

**请求（input）：**

```json
{
  "bomWindows": [
    "{{ROOT_BOM_ITEM_BOM_WINDOW_UID}}"
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `bomWindows` | Teamcenter::BOMWindow[] | References to the <b>BOMWindow</b> business objects that need to be saved after structure modifications. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any failures will be returned in the ServiceData list of partial errors. |

---

### 3.7 API 版本 2009-04

**Service：** StructureManagement  **操作数：** 1

#### 3.7.1 createOrUpdateRelativeStructure（2009-04）

**接口路径：** `Cad-2009-04-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2009-04`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2009_04.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::CreateOrUpdateRelativeStructureInfo[] | List of input structures that specify all the children to be added to the specified parent assembly. |
| `pref` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::CreateOrUpdateRelativeStructurePref | The structure for setting specific preference input used by this operation. |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::ClientIdToOccurrenceMap | Map of client IDs to <font face=&quot;courier&quot; height=&quot;10&quot;>MappedReturnData</font>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

### 3.8 API 版本 2010-09

**Service：** DataManagement  **操作数：** 1

#### 3.8.1 createOrUpdateParts（2010-09）

**接口路径：** `Cad-2010-09-DataManagement/createOrUpdateParts`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2010_09.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "partInput": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": "",
              "boundingBoxesAvailable": "",
              "destinationVolume": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boundingBoxes": [
                {
                  "xmin": "",
                  "ymin": "",
                  "zmin": "",
                  "xmax": "",
                  "ymax": "",
                  "zmax": ""
                }
              ]
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "datasetTool": "",
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `partInput` | Teamcenter::Soa::Cad::_2010_09::DataManagement::PartInfo[] | A list of PartInfo structures |
| `pref` | Teamcenter::Soa::Cad::_2007_12::DataManagement::CreateOrUpdatePartsPref | A Struct which contains information whether dataset needs to be modified, if input last modified date is different from actual |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": "",
                    "boundingBoxesAvailable": "",
                    "boundingBoxes": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

### 3.9 API 版本 2011-06

**Service：** DataManagement  **操作数：** 1

#### 3.9.1 getAllAttrMappings2（2011-06）

**接口路径：** `Cad-2011-06-DataManagement/getAllAttrMappings2`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 获取全部 CAD 属性映射定义（增强版接口，支持按数据集/Item 类型过滤）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2011_06.DataManagement.getAllAttrMappings2`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "attrMappingInfos": [
    {
      "cadAttrMappingDefinition": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propDesc": {
        "propName": "",
        "displayName": "",
        "isModifiable": "",
        "attachedSpecifier": "",
        "maxLength": "",
        "lovAttachmentsCategory": "",
        "interdependentProps": [
          ""
        ],
        "defaultValue": "",
        "propValueType": "",
        "propType": "",
        "isDisplayable": "",
        "isArray": "",
        "lov": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isRequired": "",
        "isEnabled": ""
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `attrMappingInfos` | Teamcenter::Soa::Cad::_2011_06::DataManagement::AttrMappingInfo[] | A list of attribute mapping information. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

### 3.10 API 版本 2012-09

**Service：** DataManagement  **操作数：** 1

#### 3.10.1 createOrUpdateParts（2012-09）

**接口路径：** `Cad-2012-09-DataManagement/createOrUpdateParts`

**API 版本：** `2012-09`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2012_09.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "partInput": [
    {
      "clientId": "",
      "itemInput": {
        "createOrUpdateInput": {
          "boName": "",
          "boReference": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "boolProps": {},
          "boolArrayProps": {},
          "dateProps": {},
          "dateArrayProps": {},
          "tagProps": {},
          "tagArrayProps": {},
          "compoundCreateOrUpdateInput": {},
          "stringProps": {},
          "stringArrayProps": {},
          "doubleProps": {},
          "doubleArrayProps": {},
          "floatProps": {},
          "floatArrayProps": {},
          "intProps": {},
          "intArrayProps": {}
        },
        "itemExtraObject": [
          {
            "clientId": "",
            "createOrUpdateInput": {
              "boName": "",
              "boReference": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boolProps": {},
              "boolArrayProps": {},
              "dateProps": {},
              "dateArrayProps": {},
              "tagProps": {},
              "tagArrayProps": {},
              "compoundCreateOrUpdateInput": {},
              "stringProps": {},
              "stringArrayProps": {},
              "doubleProps": {},
              "doubleArrayProps": {},
              "floatProps": {},
              "floatArrayProps": {},
              "intProps": {},
              "intArrayProps": {}
            },
            "relationTypeName": ""
          }
        ],
        "itemRevisionExtraObject": [
          {
            "clientId": "",
            "createOrUpdateInput": {
              "boName": "",
              "boReference": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boolProps": {},
              "boolArrayProps": {},
              "dateProps": {},
              "dateArrayProps": {},
              "tagProps": {},
              "tagArrayProps": {},
              "compoundCreateOrUpdateInput": {},
              "stringProps": {},
              "stringArrayProps": {},
              "doubleProps": {},
              "doubleArrayProps": {},
              "floatProps": {},
              "floatArrayProps": {},
              "intProps": {},
              "intArrayProps": {}
            },
            "relationTypeName": ""
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "datasetInput": [
        {
          "clientId": "",
          "createOrUpdateInput": {
            "boName": "",
            "boReference": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "boolProps": {},
            "boolArrayProps": {},
            "dateProps": {},
            "dateArrayProps": {},
            "tagProps": {},
            "tagArrayProps": {},
            "compoundCreateOrUpdateInput": {},
            "stringProps": {},
            "stringArrayProps": {},
            "doubleProps": {},
            "doubleArrayProps": {},
            "floatProps": {},
            "floatArrayProps": {},
            "intProps": {},
            "intArrayProps": {}
          },
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": "",
              "boundingBoxesAvailable": "",
              "destinationVolume": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boundingBoxes": [
                {
                  "xmin": "",
                  "ymin": "",
                  "zmin": "",
                  "xmax": "",
                  "ymax": "",
                  "zmax": ""
                }
              ]
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "createOrUpdateInput": {
                "boName": "",
                "boReference": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boolProps": {},
                "boolArrayProps": {},
                "dateProps": {},
                "dateArrayProps": {},
                "tagProps": {},
                "tagArrayProps": {},
                "compoundCreateOrUpdateInput": {},
                "stringProps": {},
                "stringArrayProps": {},
                "doubleProps": {},
                "doubleArrayProps": {},
                "floatProps": {},
                "floatArrayProps": {},
                "intProps": {},
                "intArrayProps": {}
              },
              "namedReferenceName": "",
              "namedReferenceType": ""
            }
          ],
          "basisName": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "itemRevRelationName": "",
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "mappingAttributes": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "extraObject": [
            {
              "clientId": "",
              "createOrUpdateInput": {
                "boName": "",
                "boReference": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boolProps": {},
                "boolArrayProps": {},
                "dateProps": {},
                "dateArrayProps": {},
                "tagProps": {},
                "tagArrayProps": {},
                "compoundCreateOrUpdateInput": {},
                "stringProps": {},
                "stringArrayProps": {},
                "doubleProps": {},
                "doubleArrayProps": {},
                "floatProps": {},
                "floatArrayProps": {},
                "intProps": {},
                "intArrayProps": {}
              },
              "relationTypeName": ""
            }
          ]
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `partInput` | Teamcenter::Soa::Cad::_2012_09::DataManagement::PartInfo[] | A list of <font face="courier" height="10">PartInfo</font> structures |
| `pref` | Teamcenter::Soa::Cad::_2007_12::DataManagement::CreateOrUpdatePartsPref | A Struct which contains information whether dataset needs to be modified, if input last modified date is different from actual |

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": "",
                    "boundingBoxesAvailable": "",
                    "boundingBoxes": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::DataManagement::CreateOrUpdatePartsOutput[] | List of CreateOrUpdatePartsOutputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. |

---

### 3.11 API 版本 2013-05

**Service：** StructureManagement  **操作数：** 3

#### 3.11.1 askChildPathBOMLines2（2013-05）

**接口路径：** `Cad-2013-05-StructureManagement/askChildPathBOMLines2`

**API 版本：** `2013-05`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 根据子路径查询 BOMLine（增强版，支持批量路径输入）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2013_05.StructureManagement.askChildPathBOMLines2`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "parentBomLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "useAsStable": "",
      "childPaths": [
        {
          "clientId": "",
          "childPath": [
            ""
          ]
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Cad::_2008_03::StructureManagement::AskChildPathBOMLinesInfo[] | Specifies sets of product structure information each containing parent <b>BOMLine</b> object, based on a BOM window opened by the client and one or more child p |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2013_05::StructureManagement::AskChildPathClientIdToBOMLineMap | A map of input Client ID to a vector of structure containing the input child path and its corresponding <b>BOMLine</b> object. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing plain objects and error information. |

---

#### 3.11.2 createBOMWindows2（2013-05）

**接口路径：** `Cad-2013-05-StructureManagement/createBOMWindows2`

**API 版本：** `2013-05`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建 BOM 窗口（增强版）：支持批量输入 ItemRevision 作为顶行，返回多个窗口信息。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2013_05.StructureManagement.createBOMWindows2`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "item": "{{ROOT_BOM_ITEM_UID}}",
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomView": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revRuleConfigInfo": {
        "clientId": "",
        "revRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "props": {
          "unitNo": "",
          "date": "0001-01-01T00:00:00",
          "today": "",
          "endItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "endItemRevision": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "overrideFolders": [
            {
              "ruleEntry": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "folder": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      },
      "objectsForConfigure": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "activeAssemblyArrangement": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "configContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomWinPropFlagMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2013_05::StructureManagement::CreateWindowsInfo2[] | list of objects containing window creation information |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "bomWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomLine": {
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
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateBOMWindowsOutput[] | List of CreateBOMWindowsOutput which contains created BOMWindow object and top line BOMLine object representing the item or item revision along with the client  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, Servi |

---

#### 3.11.3 createOrUpdateRelativeStructure（2013-05）

**接口路径：** `Cad-2013-05-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2013-05`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2013_05.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "childBomViewTypeName": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "moveInfo": {
              "commonParent": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "sourceAssembly": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "occThreadPathToBeMoved": [
                ""
              ],
              "occThreadPathTargetParent": [
                {
                  "parent": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "idType": "OccurrenceThread",
                  "id": "",
                  "isNew": ""
                }
              ]
            }
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2013_05::StructureManagement::CreateOrUpdateRelativeStructureInfo4[] | List of input structures that defines all the occurrence for a given parent. |
| `pref` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::CreateOrUpdateRelativeStructurePref | Preference structure specific for this service. |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::ClientIdToOccurrenceMap | Map of client IDs to <font face=&quot;courier&quot; height=&quot;10&quot;>MappedReturnData</font>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font face=&quot;courier&quot; height=&quot;10&qu |

---

### 3.12 API 版本 2014-10

**Service：** DataManagement  **操作数：** 1

#### 3.12.1 getAttrMappings（2014-10）

**接口路径：** `Cad-2014-10-DataManagement/getAttrMappings`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 按输入过滤条件获取 CAD 属性映射定义（可限定数据集类型与 Item 类型组合）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2014_10.DataManagement.getAttrMappings`

**请求（input）：**

```json
{
  "filter": [
    {
      "itemTypeName": "",
      "datasetTypeName": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `filter` | Teamcenter::Soa::Cad::_2014_10::DataManagement::GetAttrMappingsFilter[] | The input filter for narrowing the attribute mapping definitions returned in the response. All of the attribute mappings defined in Teamcenter are returned when |

**响应（output）：**

```json
{
  "attrMappingInfos": [
    {
      "cadAttrMappingDefinition": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propDescInfo": {
        "boTypeName": "",
        "propDescName": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `attrMappingInfos` | Teamcenter::Soa::Cad::_2014_10::DataManagement::AttrMappingInfo[] | A list of attribute mapping information. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">ServiceData</font>. This operation will populate the ServiceData plain objects with <b>CadAttrMappingDefinition</b> objects |

---

### 3.13 API 版本 2016-03

**Service：** DataManagement、StructureManagement  **操作数：** 3

#### 3.13.1 createOrUpdateModelViewPalette（2016-03）

**接口路径：** `Cad-2016-03-DataManagement/createOrUpdateModelViewPalette`

**API 版本：** `2016-03`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 创建、更新或删除模型视图面板（Fnd0ModelViewPalette）及其分组。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_03.DataManagement.createOrUpdateModelViewPalette`

**请求（input）：**

```json
{
  "mvPaletteInfo": [
    {
      "clientId": "",
      "disclosure": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "boType": "",
      "paletteToUpdate": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attrListForPalette": [
        {
          "name": "",
          "values": [
            ""
          ]
        }
      ],
      "groupsAndProxies": [
        {
          "clientId": "",
          "boType": "",
          "modelViewGroupForUpdate": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "attrListForGroup": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "proxiesInGroup": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "newOrderSequenceNumber": []
        }
      ],
      "paletteIsComplete": "",
      "groupsToDelete": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "deletePalette": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `mvPaletteInfo` | Teamcenter::Soa::Cad::_2016_03::DataManagement::ModelViewPaletteInfo[] | The model view palette information describing the details of the palette (<b>Fnd0ModelViewPalette</b>) and model view groups (<b>Fnd0ModelViewGroup</b>) to be c |

**响应（output）：**

```json
{
  "clientIDMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `clientIDMap` | Teamcenter::Soa::Cad::_2016_03::DataManagement::StringToBoMap | Map(string, <b>Fnd0ModelViewPalette</b> or <b>Fnd0ModelViewGroup</b>) of the various input <font face="courier" height="10">clientId</font> to corresponding obj |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains a list of added, updated, or deleted objects.  Also contains list of any errors which occurred within the call. |

---

#### 3.13.2 createOrUpdateModelViewProxies（2016-03）

**接口路径：** `Cad-2016-03-DataManagement/createOrUpdateModelViewProxies`

**API 版本：** `2016-03`  
**Service：** `DataManagement`  
**Library：** `Cad`

**说明：** 创建、更新或删除一组模型视图代理（Fnd0ModelViewProxy）对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_03.DataManagement.createOrUpdateModelViewProxies`

**请求（input）：**

```json
{
  "mvProxyInfos": [
    {
      "clientId": "",
      "modelView": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "boType": "",
      "deleteProxy": "",
      "owningModel": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attrList": [
        {
          "name": "",
          "values": [
            ""
          ]
        }
      ],
      "thumbnailFile": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "hiresImageFile": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "guardObjLastModifiedDate": "",
      "objLastModifiedDateGuard": "0001-01-01T00:00:00"
    }
  ],
  "updatedOwningModels": [
    {
      "owningModel": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "cadLastModifiedDate": "0001-01-01T00:00:00",
      "owningDataset": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `mvProxyInfos` | Teamcenter::Soa::Cad::_2016_03::DataManagement::ModelViewProxyInfo[] | The input list of model view proxy information describing the details of the proxies to be created or updated. |
| `updatedOwningModels` | Teamcenter::Soa::Cad::_2016_03::DataManagement::OwningModelAndCadLmd[] | The input list of model view owners which have had their CAD model views updated. After <font face="courier" height="10">mvProxyInfos</font> has been processed, |

**响应（output）：**

```json
{
  "clientIDMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `clientIDMap` | Teamcenter::Soa::Cad::_2016_03::DataManagement::StringToBoMap | Map (string, <b>Fnd0ModelViewProxy</b>) of the various input client IDs to corresponding objects (<b>Fnd0ModelViewProxy</b>) that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains a list of added, updated, or deleted objects.  Also contains list of any errors which occurred within the call. |

---

#### 3.13.3 findModelViewsInStructure（2016-03）

**接口路径：** `Cad-2016-03-StructureManagement/findModelViewsInStructure`

**API 版本：** `2016-03`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 在指定产品结构中查找关联的模型视图代理对象。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_03.StructureManagement.findModelViewsInStructure`

**请求（input）：**

```json
{
  "disclosure": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "structureScope": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "configurationContext": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "withDisclosureIntent": [
    ""
  ],
  "options": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `disclosure` | Teamcenter::BusinessObject | The use of this value is required  for update cases where the <i>compareWithMVList</i> option is set to true and <font face="courier" height="10">structureScope |
| `structureScope` | Teamcenter::BusinessObject[] | A list of one or more structures to search for model view proxy objects. If a single root assembly or workset(<b>Cpd0Workset</b>) is given, the entire structure |
| `configurationContext` | Teamcenter::ConfigurationContext | A reference to a configuration context object. Used to configure the children of the expanding structure by revision rules, effectivity, and variants. |
| `withDisclosureIntent` | std::string[] | A list of string values to match against candidate model view proxies. Only model view proxies that have any of the specified disclosure intent attribute (<b>fn |
| `options` | Teamcenter::Soa::Cad::_2016_03::StructureManagement::BoolMap | A set of optional flags. Supported options are: "compareWithMVList", "skipBackgroundScope", "doNotExpandStructureScope", "skipDirectDisclosedObject<i>" </i>or " |

**响应（output）：**

```json
{
  "modelViewsByStructureNodes": [
    {
      "structureNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "resultingViews": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "csIdContextOccurrence": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clonestableId": [
        ""
      ]
    }
  ],
  "unfoundFromModelViewList": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "possibleMatching": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `modelViewsByStructureNodes` | Teamcenter::Soa::Cad::_2016_03::StructureManagement::StructureNodeResults[] | A list of proxy objects found for various nodes in the structure - the structure nodes may be bomlines, item revisions or design elements depending on the type  |
| `unfoundFromModelViewList` | Teamcenter::Fnd0ModelViewProxy[] | The model view proxy objects (<b>Fnd0ModelViewProxy</b>) that are currently associated to the specified disclosure but are not found in the given <font face="co |
| `possibleMatching` | Teamcenter::Soa::Cad::_2016_03::StructureManagement::BoToBoMap | Map (<b>Fnd0ModelViewProxy</b>, <b>Fnd0ModelViewProxy</b>) of possible matching proxies that are equivalent. The keys are proxies in an associated MVList (assoc |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains a list of any errors which occurred during the operation. |

---

### 3.14 API 版本 2016-09

**Service：** StructureManagement  **操作数：** 4

#### 3.14.1 continueFindModelViews（2016-09）

**接口路径：** `Cad-2016-09-StructureManagement/continueFindModelViews`

**API 版本：** `2016-09`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 继续由 startFindModelViews 发起的模型视图搜索。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_09.StructureManagement.continueFindModelViews`

**请求（input）：**

```json
{
  "searchID": "",
  "stopFind": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `searchID` | std::string | A unique identifier passed by the client in order to identify the find partial results to continue searching from where the previous operation (whether <b>start |
| `stopFind` | bool | If true, the find associated to the input <font face="courier" height="10">searchID</font> will be terminated instead of returning any further results. If false |

**响应（output）：**

```json
{
  "modelViewsByStructureNodes": [
    {
      "structureNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "resultingViews": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "csIdContextOccurrence": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clonestableId": [
        ""
      ]
    }
  ],
  "finished": "",
  "structureNodesSearched": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `modelViewsByStructureNodes` | Teamcenter::Soa::Cad::_2016_03::StructureManagement::StructureNodeResults[] | A list of  proxy objects found for various  nodes in the structure - the structure nodes may be bomlines, item revisions or design elements depending on the typ |
| `finished` | bool | Flag to indicate if the find operation is complete or if there is more content or structure to be searched. If false, then the <b>continueFindModelViews</b> ope |
| `structureNodesSearched` | int | Total number of structure nodes ( <b>BomLines</b> or Design Elements) which were so far searched for model views. This shows how large the structure is as the s |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains a list of any errors which occurred during the operation. |

---

#### 3.14.2 continueReconcilePalette（2016-09）

**接口路径：** `Cad-2016-09-StructureManagement/continueReconcilePalette`

**API 版本：** `2016-09`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 继续模型视图面板与产品结构的协调过程。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_09.StructureManagement.continueReconcilePalette`

**请求（input）：**

```json
{
  "reconcilePaletteInput": {
    "clientID": "",
    "mvProxiesOrMvGroups": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "stopReconcile": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `reconcilePaletteInput` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::NextReconcilePaletteInput | Input that contains the reconciliation state identifier and the <b>Fnd0ModelViewProxy</b> if they have to prioritized for reconciliation. |

**响应（output）：**

```json
{
  "palMVPReconcileInfos": [
    {
      "paletteMVP": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "reconcileInfos": [
        {
          "candidateMVP": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "reconcileActionEnum": "",
          "reconcileAction": "",
          "reconcileReason": "",
          "candidateStructNodeInfos": [
            {
              "structNode": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cloneStableIdChain": [
                ""
              ],
              "csIdContextOccurrence": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ]
    }
  ],
  "clientID": "",
  "finished": "",
  "configurationMisMatch": "",
  "origConfigInfo": {
    "configWindow": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revisionRule": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revRuleConfigEntriesAsStrings": [
      ""
    ],
    "configOptions": [
      {
        "optionName": "",
        "boolValues": [],
        "doubleValues": [],
        "intValues": [],
        "strValues": [
          ""
        ],
        "dateValues": [
          "0001-01-01T00:00:00"
        ],
        "refValues": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    ],
    "variantRules": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "reconcileConfigInfo": {
    "configWindow": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revisionRule": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revRuleConfigEntriesAsStrings": [
      ""
    ],
    "configOptions": [
      {
        "optionName": "",
        "boolValues": [],
        "doubleValues": [],
        "intValues": [],
        "strValues": [
          ""
        ],
        "dateValues": [
          "0001-01-01T00:00:00"
        ],
        "refValues": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    ],
    "variantRules": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "estimatedMVPsLeft": "",
  "percentComplete": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `palMVPReconcileInfos` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::PaletteModelViewProxyReconcileInfo[] | A list of <font face="courier" height="10">PaletteModelViewProxyReconcileInfo</font>, one for each <b>Fnd0ModelViewProxy</b>  on the <b>Fnd0ModelViewPalette</b> |
| `clientID` | std::string | A unique clientId passed by the client to correlate multiple subsequent <font face="courier" height="10">continueReconcilePalette</font> operations . |
| `finished` | bool | True if the reconciliation is complete. |
| `configurationMisMatch` | bool | Returned as true during <font face="courier" height="10">startReconcilePalette</font> if there is a configuration mismatch between the product configuration ass |
| `origConfigInfo` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::ConfigurationDisplayInfo | The configuration information that is associated to the <b>Fnd0ModelViewPalette</b>, presented in a form that can be directly displayed to the user. |
| `reconcileConfigInfo` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::ConfigurationDisplayInfo | The configuration information for the current structure that is used for reconciliation. |
| `estimatedMVPsLeft` | int | The number of <b>Fnd0ModelViewProxy</b> objects remaining to be reconciled. |
| `percentComplete` | double | The percentage of total <b>Fnd0ModelViewProxy</b> objects on the <b>Fnd0ModelViewPalette</b> where reconciliation is complete. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">ServiceData</font> is used to communicate partial errors to the client. |

---

#### 3.14.3 startFindModelViews（2016-09）

**接口路径：** `Cad-2016-09-StructureManagement/startFindModelViews`

**API 版本：** `2016-09`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 启动模型视图搜索（大批量时分页，需配合 continueFindModelViews）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_09.StructureManagement.startFindModelViews`

**请求（input）：**

```json
{
  "findInput": {
    "searchID": "",
    "disclosure": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "startingScopes": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "configurationContext": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "withDisclosureIntents": [
      ""
    ],
    "options": {}
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `findInput` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::FindModelViewsInput | The inputs needed to start a find operation on one or more objects that support model views. |

**响应（output）：**

```json
{
  "modelViewsByStructureNodes": [
    {
      "structureNode": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "resultingViews": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "csIdContextOccurrence": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clonestableId": [
        ""
      ]
    }
  ],
  "finished": "",
  "structureNodesSearched": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `modelViewsByStructureNodes` | Teamcenter::Soa::Cad::_2016_03::StructureManagement::StructureNodeResults[] | A list of  proxy objects found for various  nodes in the structure - the structure nodes may be bomlines, item revisions or design elements depending on the typ |
| `finished` | bool | Flag to indicate if the find operation is complete or if there is more content or structure to be searched. If false, then the <b>continueFindModelViews</b> ope |
| `structureNodesSearched` | int | Total number of structure nodes ( <b>BomLines</b> or Design Elements) which were so far searched for model views. This shows how large the structure is as the s |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains a list of any errors which occurred during the operation. |

---

#### 3.14.4 startReconcilePalette（2016-09）

**接口路径：** `Cad-2016-09-StructureManagement/startReconcilePalette`

**API 版本：** `2016-09`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 开始对模型视图面板中的代理引用与产品结构进行协调（Reconcile）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2016_09.StructureManagement.startReconcilePalette`

**请求（input）：**

```json
{
  "reconcilePaletteInput": {
    "clientID": "",
    "paletteOrDisclosingObject": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "mvProxiesOrMvGroups": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "doEntirePalette": "",
    "configRecipe": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `reconcilePaletteInput` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::ReconcilePaletteInput | Input that contains the <b>Fnd0ModelViewPalette</b> or <b>Fnd0ModelViewProxy</b> that needs to be reconciled and the configuration information. |

**响应（output）：**

```json
{
  "palMVPReconcileInfos": [
    {
      "paletteMVP": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "reconcileInfos": [
        {
          "candidateMVP": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "reconcileActionEnum": "",
          "reconcileAction": "",
          "reconcileReason": "",
          "candidateStructNodeInfos": [
            {
              "structNode": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cloneStableIdChain": [
                ""
              ],
              "csIdContextOccurrence": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ]
    }
  ],
  "clientID": "",
  "finished": "",
  "configurationMisMatch": "",
  "origConfigInfo": {
    "configWindow": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revisionRule": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revRuleConfigEntriesAsStrings": [
      ""
    ],
    "configOptions": [
      {
        "optionName": "",
        "boolValues": [],
        "doubleValues": [],
        "intValues": [],
        "strValues": [
          ""
        ],
        "dateValues": [
          "0001-01-01T00:00:00"
        ],
        "refValues": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    ],
    "variantRules": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "reconcileConfigInfo": {
    "configWindow": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revisionRule": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "revRuleConfigEntriesAsStrings": [
      ""
    ],
    "configOptions": [
      {
        "optionName": "",
        "boolValues": [],
        "doubleValues": [],
        "intValues": [],
        "strValues": [
          ""
        ],
        "dateValues": [
          "0001-01-01T00:00:00"
        ],
        "refValues": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    ],
    "variantRules": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "estimatedMVPsLeft": "",
  "percentComplete": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `palMVPReconcileInfos` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::PaletteModelViewProxyReconcileInfo[] | A list of <font face="courier" height="10">PaletteModelViewProxyReconcileInfo</font>, one for each <b>Fnd0ModelViewProxy</b>  on the <b>Fnd0ModelViewPalette</b> |
| `clientID` | std::string | A unique clientId passed by the client to correlate multiple subsequent <font face="courier" height="10">continueReconcilePalette</font> operations . |
| `finished` | bool | True if the reconciliation is complete. |
| `configurationMisMatch` | bool | Returned as true during <font face="courier" height="10">startReconcilePalette</font> if there is a configuration mismatch between the product configuration ass |
| `origConfigInfo` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::ConfigurationDisplayInfo | The configuration information that is associated to the <b>Fnd0ModelViewPalette</b>, presented in a form that can be directly displayed to the user. |
| `reconcileConfigInfo` | Teamcenter::Soa::Cad::_2016_09::StructureManagement::ConfigurationDisplayInfo | The configuration information for the current structure that is used for reconciliation. |
| `estimatedMVPsLeft` | int | The number of <b>Fnd0ModelViewProxy</b> objects remaining to be reconciled. |
| `percentComplete` | double | The percentage of total <b>Fnd0ModelViewProxy</b> objects on the <b>Fnd0ModelViewPalette</b> where reconciliation is complete. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">ServiceData</font> is used to communicate partial errors to the client. |

---

### 3.15 API 版本 2018-06

**Service：** StructureManagement  **操作数：** 1

#### 3.15.1 writeAssemblyConfigurationDetails（2018-06）

**接口路径：** `Cad-2018-06-StructureManagement/writeAssemblyConfigurationDetails`

**API 版本：** `2018-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 写入装配配置明细（Assembly Configuration Details）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2018_06.StructureManagement.writeAssemblyConfigurationDetails`

**请求（input）：**

```json
{
  "bomWindow": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "optionSetName": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `bomWindow` | Teamcenter::BusinessObject | The BOM Window of the structure and its children whose content will be written to the XML file. |
| `optionSetName` | std::string | The name of the Teamcenter Import/Export Option Set to be used to process/traverse the Product Structure of the input bomWindow. |

**响应（output）：**

```json
{
  "readFileTicketForStructureData": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `readFileTicketForStructureData` | std::string | This is the FMS read file ticket for the TC XML data file written to the transient volume. The TC XML file can be downloaded using this ticket. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This service data contains any partial errors which may have been encountered during processing. The partial error client Ids match the client Id for the input  |

---

### 3.16 API 版本 2019-06

**Service：** StructureManagement  **操作数：** 1

#### 3.16.1 createOrReConfigureBOMWindows（2019-06）

**接口路径：** `Cad-2019-06-StructureManagement/createOrReConfigureBOMWindows`

**API 版本：** `2019-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或按新配置重新配置 BOM 窗口（含有效性、变型等配置上下文）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2019_06.StructureManagement.createOrReConfigureBOMWindows`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "bomWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomWinPropFlagMap": {},
      "item": "{{ROOT_BOM_ITEM_UID}}",
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomView": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revRuleConfigInfo": {
        "clientId": "",
        "revRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "props": {
          "unitNo": "",
          "date": "0001-01-01T00:00:00",
          "today": "",
          "endItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "endItemRevision": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "overrideFolders": [
            {
              "ruleEntry": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "folder": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      },
      "objectsForConfigure": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "activeAssemblyArrangement": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "configContext": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "effGrpRevList": [
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2019_06::StructureManagement::CreateWindowsInfo3[] | A list of objects containing window creation information. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "bomWindow": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bomLine": {
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
| `output` | Teamcenter::Soa::Cad::_2007_01::StructureManagement::CreateBOMWindowsOutput[] | List of CreateBOMWindowsOutput which contains created BOMWindow object and top line BOMLine object representing the item or item revision along with the client  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, Servi |

---

### 3.17 API 版本 2020-01

**Service：** AppSessionManagement  **操作数：** 2

#### 3.17.1 createOrUpdateSavedSession（2020-01）

**接口路径：** `Cad-2020-01-AppSessionManagement/createOrUpdateSavedSession`

**API 版本：** `2020-01`  
**Service：** `AppSessionManagement`  
**Library：** `Cad`

**说明：** 创建或更新已保存会话（Saved Session）数据模型，记录产品结构配置规则、非结构对象引用等，供 CAD 集成会话恢复使用。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2020_01.AppSessionManagement.createOrUpdateSavedSession`

**请求（input）：**

```json
{
  "sessionsToCreateOrUpdate": [
    {
      "clientId": "",
      "sessionToCreateOrUpdate": {
        "objectToCreate": {
          "creInp": {
            "boName": "",
            "propertyNameValues": {},
            "compoundCreateInput": {}
          },
          "relationName": "",
          "relateToObject": {
            "uid": "",
            "type": "",
            "className": ""
          }
        },
        "objectToUpdate": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lmdOfObject": "0001-01-01T00:00:00",
        "overwriteForLastModDate": "",
        "objectPropsToUpdate": {}
      },
      "attachObjectsToSession": [
        {
          "clientId": "",
          "baseObjectToCreateOrUpdate": {
            "objectToCreate": {
              "creInp": {
                "boName": "",
                "propertyNameValues": {},
                "compoundCreateInput": {}
              },
              "relationName": "",
              "relateToObject": {
                "uid": "",
                "type": "",
                "className": ""
              }
            },
            "objectToUpdate": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "lmdOfObject": "0001-01-01T00:00:00",
            "overwriteForLastModDate": "",
            "objectPropsToUpdate": {}
          },
          "relationName": "",
          "additionalProps": {},
          "recipe": {
            "structureContextIdentifier": {
              "product": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomViewType": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "configInfo": {
                "revRuleConfigInfo": {
                  "revRule": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "unitNo": "",
                  "date": "0001-01-01T00:00:00",
                  "today": "",
                  "endItem": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "endItemRevision": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "overrideFolders": [
                    {
                      "ruleEntry": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "folder": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    }
                  ]
                },
                "variantRulesOrOptionSets": [
                  {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                ],
                "activeAssemblyArrangement": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "configContext": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "bomWinPropFlagMap": {},
                "effGrpRevList": [
                  {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                ]
              },
              "configOptions": {}
            },
            "occurrenceLists": [
              {
                "resultContext": "",
                "resultObjects": {
                  "lines": [
                    {
                      "uid": "",
                      "type": "",
                      "className": ""
                    }
                  ],
                  "compositePathIdentifiers": [
                    {
                      "pathIdentifiers": [
                        {
                          "identifierPropertyName": "",
                          "resultPathIdentifiers": [
                            ""
                          ]
                        }
                      ]
                    }
                  ]
                }
              }
            ],
            "searchRecipe": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "staticStructureFile": {
              "uid": "",
              "type": "",
              "className": ""
            }
          }
        }
      ],
      "productAndConfigsToCreate": [
        {
          "clientId": "",
          "objsAttachInfos": [
            {
              "clientId": "",
              "baseObjectToCreateOrUpdate": {
                "objectToCreate": {
                  "creInp": {
                    "boName": "",
                    "propertyNameValues": {},
                    "compoundCreateInput": {}
                  },
                  "relationName": "",
                  "relateToObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                },
                "objectToUpdate": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "lmdOfObject": "0001-01-01T00:00:00",
                "overwriteForLastModDate": "",
                "objectPropsToUpdate": {}
              },
              "relationName": "",
              "additionalProps": {},
              "recipe": {
                "structureContextIdentifier": {
                  "product": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "bomViewType": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "configInfo": {
                    "revRuleConfigInfo": {
                      "revRule": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "unitNo": "",
                      "date": "0001-01-01T00:00:00",
                      "today": "",
                      "endItem": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "endItemRevision": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "overrideFolders": [
                        {
                          "ruleEntry": {
                            "uid": "",
                            "type": "",
                            "className": ""
                          },
                          "folder": {
                            "uid": "",
                            "type": "",
                            "className": ""
                          }
                        }
                      ]
                    },
                    "variantRulesOrOptionSets": [
                      {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    ],
                    "activeAssemblyArrangement": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "configContext": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "bomWinPropFlagMap": {},
                    "effGrpRevList": [
                      {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    ]
                  },
                  "configOptions": {}
                },
                "occurrenceLists": [
                  {
                    "resultContext": "",
                    "resultObjects": {
                      "lines": [
                        {
                          "uid": "",
                          "type": "",
                          "className": ""
                        }
                      ],
                      "compositePathIdentifiers": [
                        {
                          "pathIdentifiers": [
                            {
                              "identifierPropertyName": "",
                              "resultPathIdentifiers": [
                                ""
                              ]
                            }
                          ]
                        }
                      ]
                    }
                  }
                ],
                "searchRecipe": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "staticStructureFile": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ],
          "productSessionDataAttachInfos": [
            {
              "clientId": "",
              "sessionData": {
                "objectToCreate": {
                  "creInp": {
                    "boName": "",
                    "propertyNameValues": {},
                    "compoundCreateInput": {}
                  },
                  "relationName": "",
                  "relateToObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                },
                "objectToUpdate": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "lmdOfObject": "0001-01-01T00:00:00",
                "overwriteForLastModDate": "",
                "objectPropsToUpdate": {}
              }
            }
          ],
          "structureRecipe": {
            "structureContextIdentifier": {
              "product": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomViewType": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "configInfo": {
                "revRuleConfigInfo": {
                  "revRule": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "unitNo": "",
                  "date": "0001-01-01T00:00:00",
                  "today": "",
                  "endItem": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "endItemRevision": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "overrideFolders": [
                    {
                      "ruleEntry": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "folder": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    }
                  ]
                },
                "variantRulesOrOptionSets": [
                  {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                ],
                "activeAssemblyArrangement": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "configContext": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "bomWinPropFlagMap": {},
                "effGrpRevList": [
                  {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                ]
              },
              "configOptions": {}
            },
            "occurrenceLists": [
              {
                "resultContext": "",
                "resultObjects": {
                  "lines": [
                    {
                      "uid": "",
                      "type": "",
                      "className": ""
                    }
                  ],
                  "compositePathIdentifiers": [
                    {
                      "pathIdentifiers": [
                        {
                          "identifierPropertyName": "",
                          "resultPathIdentifiers": [
                            ""
                          ]
                        }
                      ]
                    }
                  ]
                }
              }
            ],
            "searchRecipe": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "staticStructureFile": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "structureRecipeProps": {}
        }
      ],
      "productAndConfigsToUpdate": [
        {
          "stableId": "",
          "objsAttachInfos": [
            {
              "clientId": "",
              "baseObjectToCreateOrUpdate": {
                "objectToCreate": {
                  "creInp": {
                    "boName": "",
                    "propertyNameValues": {},
                    "compoundCreateInput": {}
                  },
                  "relationName": "",
                  "relateToObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                },
                "objectToUpdate": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "lmdOfObject": "0001-01-01T00:00:00",
                "overwriteForLastModDate": "",
                "objectPropsToUpdate": {}
              },
              "relationName": "",
              "additionalProps": {},
              "recipe": {
                "structureContextIdentifier": {
                  "product": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "bomViewType": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "configInfo": {
                    "revRuleConfigInfo": {
                      "revRule": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "unitNo": "",
                      "date": "0001-01-01T00:00:00",
                      "today": "",
                      "endItem": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "endItemRevision": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "overrideFolders": [
                        {
                          "ruleEntry": {
                            "uid": "",
                            "type": "",
                            "className": ""
                          },
                          "folder": {
                            "uid": "",
                            "type": "",
                            "className": ""
                          }
                        }
                      ]
                    },
                    "variantRulesOrOptionSets": [
                      {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    ],
                    "activeAssemblyArrangement": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "configContext": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "bomWinPropFlagMap": {},
                    "effGrpRevList": [
                      {
                        "uid": "",
                        "type": "",
                        "className": ""
                      }
                    ]
                  },
                  "configOptions": {}
                },
                "occurrenceLists": [
                  {
                    "resultContext": "",
                    "resultObjects": {
                      "lines": [
                        {
                          "uid": "",
                          "type": "",
                          "className": ""
                        }
                      ],
                      "compositePathIdentifiers": [
                        {
                          "pathIdentifiers": [
                            {
                              "identifierPropertyName": "",
                              "resultPathIdentifiers": [
                                ""
                              ]
                            }
                          ]
                        }
                      ]
                    }
                  }
                ],
                "searchRecipe": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "staticStructureFile": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ],
          "productSessionDataAttachInfos": [
            {
              "clientId": "",
              "sessionData": {
                "objectToCreate": {
                  "creInp": {
                    "boName": "",
                    "propertyNameValues": {},
                    "compoundCreateInput": {}
                  },
                  "relationName": "",
                  "relateToObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  }
                },
                "objectToUpdate": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "lmdOfObject": "0001-01-01T00:00:00",
                "overwriteForLastModDate": "",
                "objectPropsToUpdate": {}
              }
            }
          ],
          "detachObjects": [
            ""
          ],
          "structureRecipeProps": {}
        }
      ],
      "productSessionDataAttachInfos": [
        {
          "clientId": "",
          "sessionData": {
            "objectToCreate": {
              "creInp": {
                "boName": "",
                "propertyNameValues": {},
                "compoundCreateInput": {}
              },
              "relationName": "",
              "relateToObject": {
                "uid": "",
                "type": "",
                "className": ""
              }
            },
            "objectToUpdate": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "lmdOfObject": "0001-01-01T00:00:00",
            "overwriteForLastModDate": "",
            "objectPropsToUpdate": {}
          }
        }
      ],
      "detachObjectOrProductsFromSession": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sessionsToCreateOrUpdate` | Teamcenter::Soa::Cad::_2020_01::AppSessionManagement::SessionInfo[] | A list of <font face="courier" height="10">SessionInfo</font> data structures. Each of the struct element is identified by a unique identifier assigned by the c |

**响应（output）：**

```json
{
  "sessionOutputs": [
    {
      "clientId": "",
      "sessionObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "baseObjectAttachOutputs": [
        {
          "clientId": "",
          "stableId": "",
          "baseObject": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "recipeOfOpenedProductOutputs": [
        {
          "clientId": "",
          "relativeToSessionStableId": "",
          "recipeObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "baseObjectAttachOutputs": [
            {
              "clientId": "",
              "stableId": "",
              "baseObject": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "productSessionDataAttachOutputs": [
            {
              "clientId": "",
              "stableId": "",
              "baseObject": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "productSessionDataAttachOutputs": [
        {
          "clientId": "",
          "stableId": "",
          "baseObject": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sessionOutputs` | Teamcenter::Soa::Cad::_2020_01::AppSessionManagement::CreateOrUpdateSessionOutput[] | A list of objects that were associated to the session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">ServiceData</font> that contains the partial errors if any. |

---

#### 3.17.2 openSavedSession（2020-01）

**接口路径：** `Cad-2020-01-AppSessionManagement/openSavedSession`

**API 版本：** `2020-01`  
**Service：** `AppSessionManagement`  
**Library：** `Cad`

**说明：** 打开此前通过 createOrUpdateSavedSession 保存的会话，加载其中的文档与产品结构。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2020_01.AppSessionManagement.openSavedSession`

**请求（input）：**

```json
{
  "sessionsToOpen": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "filter": {
    "relAndTypesFilter": [
      {
        "stableId": "",
        "relationName": "",
        "relatedObjAndNamedRefs": [
          {
            "objectTypeName": "",
            "namedReferenceNames": [
              ""
            ]
          }
        ],
        "namedRefHandler": ""
      }
    ],
    "productStructureFilter": {
      "productStructure": "",
      "outputFilters": {},
      "relativeToSessionStableIds": [
        ""
      ],
      "additionalPropsOnBOMWindow": {}
    },
    "productSessionDataFilter": {
      "stableIds": [
        ""
      ],
      "productSessionDataTypeNames": [
        ""
      ]
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sessionsToOpen` | Teamcenter::BusinessObject[] | A list of <font face="courier" height="10">Teamcenter::BusinessObject</font> session object that are to be opened. Valid session object is <b>Fnd0AppSession</b> |
| `filter` | Teamcenter::Soa::Cad::_2020_01::AppSessionManagement::OpenSavedSessionFilter | The filter to apply on the type of object and product structures that the client application is interested in opening. |

**响应（output）：**

```json
{
  "sessionOutputs": [
    {
      "sessionObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "sessionProductStructures": [
        {
          "stableId": "",
          "bomWindow": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "recipeObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationProperties": {},
          "staticStructureFileTicket": "",
          "relatedObjectInfos": [
            {
              "stableId": "",
              "relatedObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomWindow": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "recipeObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "relationProperties": {},
              "namedRefList": [
                {
                  "namedReferenceType": "",
                  "namedReferenceName": "",
                  "referenceObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "fileTicket": ""
                }
              ]
            }
          ],
          "productSessionDataObjects": [
            {
              "stableId": "",
              "productSessionDataObject": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "relatedObjectInfos": [
        {
          "stableId": "",
          "relatedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "bomWindow": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "recipeObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationProperties": {},
          "namedRefList": [
            {
              "namedReferenceType": "",
              "namedReferenceName": "",
              "referenceObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "fileTicket": ""
            }
          ]
        }
      ],
      "productSessionDataObjects": [
        {
          "stableId": "",
          "productSessionDataObject": {
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sessionOutputs` | Teamcenter::Soa::Cad::_2020_01::AppSessionManagement::OpenSessionOutput[] | A list of objects and product structures that were associated to the session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">ServiceData</font> that contains the partial errors if any. |

---

### 3.18 API 版本 2023-06

**Service：** StructureManagement  **操作数：** 1

#### 3.18.1 expandPSOneLevel2（2023-06）

**接口路径：** `Cad-2023-06-StructureManagement/expandPSOneLevel2`

**API 版本：** `2023-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 展开产品结构一层（增强版接口，返回结构有所扩展）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2023_06.StructureManagement.expandPSOneLevel2`

**请求（input）：**

```json
{
  "info": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None2"
  },
  "prefs": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relatedObjAndNamedRefs": [
          {
            "objectTypeName": "",
            "namedReferenceNames": [
              ""
            ]
          }
        ],
        "namedRefHandler": "UseNamedRefsList"
      }
    ],
    "includeOccurrenceTypes": [
      ""
    ],
    "excludeOccurrenceTypes": [
      ""
    ],
    "expandSettings": {}
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSOneLevelInfo | A list of parent <b>BOMLine</b> objects to expand, a filter that describes what child <b>BOMLine</b> objects are excluded in the expansion, and a filter that de |
| `prefs` | Teamcenter::Soa::Cad::_2023_06::StructureManagement::ExpandPSOneLevelPref | Contains a flag for expanding <b>BOMLine</b> object further and a list describing the relation name, related object type and named references that help define t |

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "objectOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentRelatedObjects": [
          {
            "relatedObject": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "namedRefList": [
              {
                "namedReferenceType": "",
                "namedReferenceName": "",
                "referenceObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "fileTicket": ""
              }
            ]
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "objectOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relatedObjects": [
            {
              "relatedObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedRefList": [
                {
                  "namedReferenceType": "",
                  "namedReferenceName": "",
                  "referenceObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "fileTicket": ""
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ExpandPSOneLevelOutput[] | List of ExpandPSOneLevelOutput structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and error information. For this service, all o |

---

### 3.19 API 版本 2023-12

**Service：** StructureManagement  **操作数：** 1

#### 3.19.1 createOrUpdateAbsoluteStructure（2023-12）

**接口路径：** `Cad-2023-12-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2023-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新绝对坐标系下的产品结构（绝对变换/绝对定位语义）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2023_12.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "absOccInfos": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "boundingBoxInfo": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boundingBoxVector": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "datasetAttachments": [
              {
                "clientId": "",
                "datasetInfo": {
                  "clientId": "",
                  "dataset": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "namedReferencePreference": "",
                  "dataList": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ],
                  "datasetFileInfos": [
                    {
                      "clientId": "",
                      "fileName": "",
                      "namedReferencedName": "",
                      "isText": "",
                      "allowReplace": "",
                      "boundingBoxesAvailable": "",
                      "boundingBoxes": [
                        {
                          "xmin": "",
                          "ymin": "",
                          "zmin": "",
                          "xmax": "",
                          "ymax": "",
                          "zmax": ""
                        }
                      ]
                    }
                  ],
                  "namedReferenceObjectInfos": [
                    {
                      "clientId": "",
                      "object": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "namedReferenceName": "",
                      "typeName": "",
                      "dataNameValuePairs": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ]
                    }
                  ],
                  "name": "",
                  "basisName": "",
                  "description": "",
                  "type": "",
                  "lastModifiedOfDataset": "0001-01-01T00:00:00",
                  "id": "",
                  "datasetRev": "",
                  "createNewVersion": ""
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "formAttachments": [
              {
                "clientId": "",
                "formInfo": {
                  "formObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "name": "",
                  "description": "",
                  "formType": "",
                  "attributes": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ]
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "clientIdOfUsedArrangement": ""
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "arrangementType": "isDefault",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boundingBoxInfo": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "boundingBoxVector": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  }
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "overrideObject": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "overrideObject": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "datasetAttachments": [
                  {
                    "clientId": "",
                    "datasetInfo": {
                      "clientId": "",
                      "dataset": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "namedReferencePreference": "",
                      "dataList": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ],
                      "datasetFileInfos": [
                        {
                          "clientId": "",
                          "fileName": "",
                          "namedReferencedName": "",
                          "isText": "",
                          "allowReplace": "",
                          "boundingBoxesAvailable": "",
                          "boundingBoxes": [
                            {
                              "xmin": "",
                              "ymin": "",
                              "zmin": "",
                              "xmax": "",
                              "ymax": "",
                              "zmax": ""
                            }
                          ]
                        }
                      ],
                      "namedReferenceObjectInfos": [
                        {
                          "clientId": "",
                          "object": {
                            "uid": "",
                            "type": "",
                            "className": ""
                          },
                          "namedReferenceName": "",
                          "typeName": "",
                          "dataNameValuePairs": [
                            {
                              "name": "",
                              "values": [
                                ""
                              ]
                            }
                          ]
                        }
                      ],
                      "name": "",
                      "basisName": "",
                      "description": "",
                      "type": "",
                      "lastModifiedOfDataset": "0001-01-01T00:00:00",
                      "id": "",
                      "datasetRev": "",
                      "createNewVersion": ""
                    },
                    "relationTypeName": "",
                    "createIfFound": ""
                  }
                ],
                "formAttachments": [
                  {
                    "clientId": "",
                    "formInfo": {
                      "formObject": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "name": "",
                      "description": "",
                      "formType": "",
                      "attributes": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ]
                    },
                    "relationTypeName": "",
                    "createIfFound": ""
                  }
                ],
                "clientIdOfUsedArrangement": ""
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": "",
    "overridesToSynchronize": [
      ""
    ],
    "relationFilters": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ],
    "cadOccIdAttrName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccInfos` | Teamcenter::Soa::Cad::_2023_12::StructureManagement::CreateOrUpdateAbsoluteStructureInfo4[] | List of information related to the absolute occurrences that need to be created or updated. |
| `bomViewTypeName` | std::string | The BOM view (BV) type used to find the existing BOM view. |
| `pref` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::CreateOrUpdateAbsoluteStructurePref3 | The structure for setting specific preference input used by this operation. |

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrangementOutput": {},
  "formOutput": {},
  "datasetOutput": [
    {
      "clientId": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "commitInfo": [
        {
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "datasetFileTicketInfos": [
            {
              "datasetFileInfo": {
                "clientId": "",
                "fileName": "",
                "namedReferencedName": "",
                "isText": "",
                "allowReplace": "",
                "boundingBoxesAvailable": "",
                "boundingBoxes": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              },
              "ticket": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `absOccOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToAbsOccMap2 | A map (string, <b>AbsOccurrence</b>) of input clientId to the created, updated or found absolute occurrence. |
| `asmArrangementOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToAsmArrangementMap | A map (string, list of <b>AssemblyArrangement</b>) of input clientId to the created or updated assembly arrangement. |
| `formOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::ClientIdToFormMap | A map (string, <b>Form</b>) of input clientId to the created form. |
| `datasetOutput` | Teamcenter::Soa::Cad::_2008_06::StructureManagement::DatasetOutput[] | A list of created or updated <b>Dataset</b>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData. This operation will populate the ServiceData with created or updated PSOccurrence objects, <b>AssemblyArrangement</b> objects, <b>Dataset</b> o |

---

### 3.20 API 版本 2024-12

**Service：** StructureManagement  **操作数：** 1

#### 3.20.1 createOrUpdateRelativeStructure（2024-12）

**接口路径：** `Cad-2024-12-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2024-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2024_12.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "childBomViewTypeName": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "usageRevisionType": "",
            "moveInfo": {
              "commonParent": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "sourceAssembly": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "occThreadPathToBeMoved": [
                ""
              ],
              "occThreadPathTargetParent": [
                {
                  "parent": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "idType": "OccurrenceThread",
                  "id": "",
                  "isNew": ""
                }
              ]
            }
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2024_12::StructureManagement::CreateOrUpdateRelativeStructureInfo5[] | A list of input structures that defines all the occurrence for a given parent. |
| `pref` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::CreateOrUpdateRelativeStructurePref | Preference structure specific for this service. |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2024_12::StructureManagement::ClientIdToOccurrenceMap2 | A map(std::string, <font face="courier" height="10">MappedReturnData2</font>) of client IDs to <font face="courier" height="10">MappedReturnData2</font>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">ServiceData</font>. This operation will populate the <font face="courier" height="10">ServiceData</font> with created occur |

---

### 3.21 API 版本 2025-06

**Service：** StructureManagement  **操作数：** 1

#### 3.21.1 createOrUpdateRelativeStructure（2025-06）

**接口路径：** `Cad-2025-06-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2025-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

**Soa Inclusion：** `Teamcenter.Soa.Cad._2025_06.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "childBomViewTypeName": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "usageRevisionType": "",
            "preAllocatedPsOccThreadUid": "",
            "moveInfo": {
              "commonParent": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "sourceAssembly": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "occThreadPathToBeMoved": [
                ""
              ],
              "occThreadPathTargetParent": [
                {
                  "parent": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "idType": "OccurrenceThread",
                  "id": "",
                  "isNew": ""
                }
              ]
            }
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Cad::_2025_06::StructureManagement::CreateOrUpdateRelativeStructureInfo6[] | A list of input structures that defines all the occurrence for a given parent. |
| `pref` | Teamcenter::Soa::Cad::_2009_04::StructureManagement::CreateOrUpdateRelativeStructurePref | Preference structure specific for this service. |

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Cad::_2024_12::StructureManagement::ClientIdToOccurrenceMap2 | A map(std::string, <font face="courier" height="10">MappedReturnData2</font>) of client IDs to <font face="courier" height="10">MappedReturnData2</font>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">ServiceData</font>. This operation will populate the <font face="courier" height="10">ServiceData</font> with created occur |

---

---

## 4. 同名操作多版本对照

以下 **8** 个操作名在多个 API 版本中均有定义，调用时必须使用对应版本的 Url 与 input/output 结构。

### 4.1 `createOrUpdateAbsoluteStructure`

**说明：** 创建或更新绝对坐标系下的产品结构（绝对变换/绝对定位语义）。

| API 版本 | Service | Url | Soa Inclusion |
|----------|---------|-----|---------------|
| 2007-01 | StructureManagement | `Cad-2007-01-StructureManagement/createOrUpdateAbsoluteStructure` | `Teamcenter.Soa.Cad._2007_01.StructureManagement.createOrUpdateAbsoluteStructure` |
| 2007-12 | StructureManagement | `Cad-2007-12-StructureManagement/createOrUpdateAbsoluteStructure` | `Teamcenter.Soa.Cad._2007_12.StructureManagement.createOrUpdateAbsoluteStructure` |
| 2008-06 | StructureManagement | `Cad-2008-06-StructureManagement/createOrUpdateAbsoluteStructure` | `Teamcenter.Soa.Cad._2008_06.StructureManagement.createOrUpdateAbsoluteStructure` |
| 2023-12 | StructureManagement | `Cad-2023-12-StructureManagement/createOrUpdateAbsoluteStructure` | `Teamcenter.Soa.Cad._2023_12.StructureManagement.createOrUpdateAbsoluteStructure` |

#### 版本 2007-01

##### 4.1.1 createOrUpdateAbsoluteStructure

**接口路径：** `Cad-2007-01-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "info": [
    {
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "clientIdOfUsedArrangement": "",
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            }
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "isDefault": "",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "clientIdOfUsedArrangement": "",
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "cadOccIdAttrName": ""
  }
}
```

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrOutput": {},
  "serviceData": "IServiceData"
}
```

---

#### 版本 2007-12

##### 4.1.2 createOrUpdateAbsoluteStructure

**接口路径：** `Cad-2007-12-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "info": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "clientIdOfUsedArrangement": "",
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            }
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "isDefault": "",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "clientIdOfUsedArrangement": "",
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": ""
  }
}
```

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrOutput": {},
  "serviceData": "IServiceData"
}
```

---

#### 版本 2008-06

##### 4.1.3 createOrUpdateAbsoluteStructure

**接口路径：** `Cad-2008-06-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "absOccInfos": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "boundingBoxInfo": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boundingBoxVector": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "datasetAttachments": [
              {
                "clientId": "",
                "datasetInfo": {
                  "clientId": "",
                  "dataset": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "namedReferencePreference": "",
                  "dataList": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ],
                  "datasetFileInfos": [
                    {
                      "clientId": "",
                      "fileName": "",
                      "namedReferencedName": "",
                      "isText": "",
                      "allowReplace": "",
                      "boundingBoxesAvailable": "",
                      "boundingBoxes": [
                        {
                          "xmin": "",
                          "ymin": "",
                          "zmin": "",
                          "xmax": "",
                          "ymax": "",
                          "zmax": ""
                        }
                      ]
                    }
                  ],
                  "namedReferenceObjectInfos": [
                    {
                      "clientId": "",
                      "object": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "namedReferenceName": "",
                      "typeName": "",
                      "dataNameValuePairs": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ]
                    }
                  ],
                  "name": "",
                  "basisName": "",
                  "description": "",
                  "type": "",
                  "lastModifiedOfDataset": "0001-01-01T00:00:00",
                  "id": "",
                  "datasetRev": "",
                  "createNewVersion": ""
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "formAttachments": [
              {
                "clientId": "",
                "formInfo": {
                  "formObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "name": "",
                  "description": "",
                  "formType": "",
                  "attributes": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ]
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "clientIdOfUsedArrangement": ""
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "isDefault": "",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "clientIdOfUsedArrangement": "",
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                }
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "overridesToSynchronize": [
      ""
    ],
    "relationFilters": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ],
    "cadOccIdAttrName": ""
  }
}
```

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrangementOutput": {},
  "formOutput": {},
  "datasetOutput": [
    {
      "clientId": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "commitInfo": [
        {
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "datasetFileTicketInfos": [
            {
              "datasetFileInfo": {
                "clientId": "",
                "fileName": "",
                "namedReferencedName": "",
                "isText": "",
                "allowReplace": "",
                "boundingBoxesAvailable": "",
                "boundingBoxes": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              },
              "ticket": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

---

#### 版本 2023-12

##### 4.1.4 createOrUpdateAbsoluteStructure

**接口路径：** `Cad-2023-12-StructureManagement/createOrUpdateAbsoluteStructure`

**API 版本：** `2023-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2023_12.StructureManagement.createOrUpdateAbsoluteStructure`

**请求（input）：**

```json
{
  "absOccInfos": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "contextItemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "bvrAbsOccInfo": [
        {
          "clientId": "",
          "absOcc": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "cadOccIdPath": [
            ""
          ],
          "absOccData": {
            "overridesToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "overridesToRemove": [
              ""
            ],
            "usedArr": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "boundingBoxInfo": [
              {
                "dataset": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boundingBoxVector": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "attachments": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "attachmentsToUnattach": [
              {
                "overrideObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "relationTypeName": ""
              }
            ],
            "datasetAttachments": [
              {
                "clientId": "",
                "datasetInfo": {
                  "clientId": "",
                  "dataset": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "namedReferencePreference": "",
                  "dataList": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ],
                  "datasetFileInfos": [
                    {
                      "clientId": "",
                      "fileName": "",
                      "namedReferencedName": "",
                      "isText": "",
                      "allowReplace": "",
                      "boundingBoxesAvailable": "",
                      "boundingBoxes": [
                        {
                          "xmin": "",
                          "ymin": "",
                          "zmin": "",
                          "xmax": "",
                          "ymax": "",
                          "zmax": ""
                        }
                      ]
                    }
                  ],
                  "namedReferenceObjectInfos": [
                    {
                      "clientId": "",
                      "object": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "namedReferenceName": "",
                      "typeName": "",
                      "dataNameValuePairs": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ]
                    }
                  ],
                  "name": "",
                  "basisName": "",
                  "description": "",
                  "type": "",
                  "lastModifiedOfDataset": "0001-01-01T00:00:00",
                  "id": "",
                  "datasetRev": "",
                  "createNewVersion": ""
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "formAttachments": [
              {
                "clientId": "",
                "formInfo": {
                  "formObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "name": "",
                  "description": "",
                  "formType": "",
                  "attributes": [
                    {
                      "name": "",
                      "values": [
                        ""
                      ]
                    }
                  ]
                },
                "relationTypeName": "",
                "createIfFound": ""
              }
            ],
            "clientIdOfUsedArrangement": ""
          }
        }
      ],
      "arrAbsOccInfo": [
        {
          "clientId": "",
          "arrangement": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "name": "",
          "arrangementType": "isDefault",
          "description": "",
          "externalUid": "",
          "absOccInfo": [
            {
              "clientId": "",
              "absOcc": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "cadOccIdPath": [
                ""
              ],
              "absOccData": {
                "overridesToSet": [
                  {
                    "name": "",
                    "value": ""
                  }
                ],
                "overridesToRemove": [
                  ""
                ],
                "usedArr": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boundingBoxInfo": [
                  {
                    "dataset": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "boundingBoxVector": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  }
                ],
                "asRequired": "",
                "occTransform": [],
                "occNotes": [
                  {
                    "noteType": "",
                    "noteText": ""
                  }
                ],
                "attachments": [
                  {
                    "overrideObject": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "attachmentsToUnattach": [
                  {
                    "overrideObject": {
                      "uid": "",
                      "type": "",
                      "className": ""
                    },
                    "relationTypeName": ""
                  }
                ],
                "datasetAttachments": [
                  {
                    "clientId": "",
                    "datasetInfo": {
                      "clientId": "",
                      "dataset": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "namedReferencePreference": "",
                      "dataList": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ],
                      "datasetFileInfos": [
                        {
                          "clientId": "",
                          "fileName": "",
                          "namedReferencedName": "",
                          "isText": "",
                          "allowReplace": "",
                          "boundingBoxesAvailable": "",
                          "boundingBoxes": [
                            {
                              "xmin": "",
                              "ymin": "",
                              "zmin": "",
                              "xmax": "",
                              "ymax": "",
                              "zmax": ""
                            }
                          ]
                        }
                      ],
                      "namedReferenceObjectInfos": [
                        {
                          "clientId": "",
                          "object": {
                            "uid": "",
                            "type": "",
                            "className": ""
                          },
                          "namedReferenceName": "",
                          "typeName": "",
                          "dataNameValuePairs": [
                            {
                              "name": "",
                              "values": [
                                ""
                              ]
                            }
                          ]
                        }
                      ],
                      "name": "",
                      "basisName": "",
                      "description": "",
                      "type": "",
                      "lastModifiedOfDataset": "0001-01-01T00:00:00",
                      "id": "",
                      "datasetRev": "",
                      "createNewVersion": ""
                    },
                    "relationTypeName": "",
                    "createIfFound": ""
                  }
                ],
                "formAttachments": [
                  {
                    "clientId": "",
                    "formInfo": {
                      "formObject": {
                        "uid": "",
                        "type": "",
                        "className": ""
                      },
                      "name": "",
                      "description": "",
                      "formType": "",
                      "attributes": [
                        {
                          "name": "",
                          "values": [
                            ""
                          ]
                        }
                      ]
                    },
                    "relationTypeName": "",
                    "createIfFound": ""
                  }
                ],
                "clientIdOfUsedArrangement": ""
              }
            }
          ]
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": "",
    "overridesToSynchronize": [
      ""
    ],
    "relationFilters": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ],
    "cadOccIdAttrName": ""
  }
}
```

**响应（output）：**

```json
{
  "absOccOutput": {},
  "asmArrangementOutput": {},
  "formOutput": {},
  "datasetOutput": [
    {
      "clientId": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "commitInfo": [
        {
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "datasetFileTicketInfos": [
            {
              "datasetFileInfo": {
                "clientId": "",
                "fileName": "",
                "namedReferencedName": "",
                "isText": "",
                "allowReplace": "",
                "boundingBoxesAvailable": "",
                "boundingBoxes": [
                  {
                    "xmin": "",
                    "ymin": "",
                    "zmin": "",
                    "xmax": "",
                    "ymax": "",
                    "zmax": ""
                  }
                ]
              },
              "ticket": ""
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

---

### 4.2 `createOrUpdateParts`

**说明：** 批量创建或更新 CAD 零件（Part）及其关联 Teamcenter 业务对象（Item/版本/数据集等）。

| API 版本 | Service | Url | Soa Inclusion |
|----------|---------|-----|---------------|
| 2007-01 | DataManagement | `Cad-2007-01-DataManagement/createOrUpdateParts` | `Teamcenter.Soa.Cad._2007_01.DataManagement.createOrUpdateParts` |
| 2007-12 | DataManagement | `Cad-2007-12-DataManagement/createOrUpdateParts` | `Teamcenter.Soa.Cad._2007_12.DataManagement.createOrUpdateParts` |
| 2008-03 | DataManagement | `Cad-2008-03-DataManagement/createOrUpdateParts` | `Teamcenter.Soa.Cad._2008_03.DataManagement.createOrUpdateParts` |
| 2008-06 | DataManagement | `Cad-2008-06-DataManagement/createOrUpdateParts` | `Teamcenter.Soa.Cad._2008_06.DataManagement.createOrUpdateParts` |
| 2010-09 | DataManagement | `Cad-2010-09-DataManagement/createOrUpdateParts` | `Teamcenter.Soa.Cad._2010_09.DataManagement.createOrUpdateParts` |
| 2012-09 | DataManagement | `Cad-2012-09-DataManagement/createOrUpdateParts` | `Teamcenter.Soa.Cad._2012_09.DataManagement.createOrUpdateParts` |

#### 版本 2007-01

##### 4.2.1 createOrUpdateParts

**接口路径：** `Cad-2007-01-DataManagement/createOrUpdateParts`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "attrList": [
            {
              "name": "",
              "value": ""
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "value": ""
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": ""
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "name": "",
          "description": "",
          "type": "",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": "",
          "createNewVersion": "",
          "namedReferencePreference": ""
        }
      ]
    }
  ]
}
```

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": ""
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

---

#### 版本 2007-12

##### 4.2.2 createOrUpdateParts

**接口路径：** `Cad-2007-12-DataManagement/createOrUpdateParts`

**API 版本：** `2007-12`  
**Service：** `DataManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "value": ""
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "value": ""
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": ""
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": ""
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

---

#### 版本 2008-03

##### 4.2.3 createOrUpdateParts

**接口路径：** `Cad-2008-03-DataManagement/createOrUpdateParts`

**API 版本：** `2008-03`  
**Service：** `DataManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_03.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "value": ""
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "value": ""
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "value": ""
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "value": ""
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": ""
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "value": ""
                }
              ]
            }
          ],
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": ""
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

---

#### 版本 2008-06

##### 4.2.4 createOrUpdateParts

**接口路径：** `Cad-2008-06-DataManagement/createOrUpdateParts`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "partInput": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": "",
              "boundingBoxesAvailable": "",
              "boundingBoxes": [
                {
                  "xmin": "",
                  "ymin": "",
                  "zmin": "",
                  "xmax": "",
                  "ymax": "",
                  "zmax": ""
                }
              ]
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": "",
                    "boundingBoxesAvailable": "",
                    "boundingBoxes": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

---

#### 版本 2010-09

##### 4.2.5 createOrUpdateParts

**接口路径：** `Cad-2010-09-DataManagement/createOrUpdateParts`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2010_09.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "partInput": [
    {
      "clientId": "",
      "itemInput": {
        "item": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemId": "",
        "itemType": "",
        "name": "",
        "description": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "itemRevInput": {
        "itemRevision": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revId": "",
        "attrList": [
          {
            "name": "",
            "values": [
              ""
            ]
          }
        ],
        "extraObject": [
          {
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "clientId": "",
            "relationTypeName": "",
            "typeName": "",
            "attrNameValuePairs": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "datasetInput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "attrList": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "mappingAttributes": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "extraObject": [
            {
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "clientId": "",
              "relationTypeName": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": "",
              "boundingBoxesAvailable": "",
              "destinationVolume": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boundingBoxes": [
                {
                  "xmin": "",
                  "ymin": "",
                  "zmin": "",
                  "xmax": "",
                  "ymax": "",
                  "zmax": ""
                }
              ]
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedReferenceName": "",
              "namedReferenceType": "",
              "typeName": "",
              "attrNameValuePairs": [
                {
                  "name": "",
                  "values": [
                    ""
                  ]
                }
              ]
            }
          ],
          "datasetTool": "",
          "name": "",
          "basisName": "",
          "description": "",
          "type": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "id": "",
          "datasetRev": "",
          "itemRevRelationName": ""
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": "",
                    "boundingBoxesAvailable": "",
                    "boundingBoxes": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

---

#### 版本 2012-09

##### 4.2.6 createOrUpdateParts

**接口路径：** `Cad-2012-09-DataManagement/createOrUpdateParts`

**API 版本：** `2012-09`  
**Service：** `DataManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2012_09.DataManagement.createOrUpdateParts`

**请求（input）：**

```json
{
  "partInput": [
    {
      "clientId": "",
      "itemInput": {
        "createOrUpdateInput": {
          "boName": "",
          "boReference": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "boolProps": {},
          "boolArrayProps": {},
          "dateProps": {},
          "dateArrayProps": {},
          "tagProps": {},
          "tagArrayProps": {},
          "compoundCreateOrUpdateInput": {},
          "stringProps": {},
          "stringArrayProps": {},
          "doubleProps": {},
          "doubleArrayProps": {},
          "floatProps": {},
          "floatArrayProps": {},
          "intProps": {},
          "intArrayProps": {}
        },
        "itemExtraObject": [
          {
            "clientId": "",
            "createOrUpdateInput": {
              "boName": "",
              "boReference": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boolProps": {},
              "boolArrayProps": {},
              "dateProps": {},
              "dateArrayProps": {},
              "tagProps": {},
              "tagArrayProps": {},
              "compoundCreateOrUpdateInput": {},
              "stringProps": {},
              "stringArrayProps": {},
              "doubleProps": {},
              "doubleArrayProps": {},
              "floatProps": {},
              "floatArrayProps": {},
              "intProps": {},
              "intArrayProps": {}
            },
            "relationTypeName": ""
          }
        ],
        "itemRevisionExtraObject": [
          {
            "clientId": "",
            "createOrUpdateInput": {
              "boName": "",
              "boReference": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boolProps": {},
              "boolArrayProps": {},
              "dateProps": {},
              "dateArrayProps": {},
              "tagProps": {},
              "tagArrayProps": {},
              "compoundCreateOrUpdateInput": {},
              "stringProps": {},
              "stringArrayProps": {},
              "doubleProps": {},
              "doubleArrayProps": {},
              "floatProps": {},
              "floatArrayProps": {},
              "intProps": {},
              "intArrayProps": {}
            },
            "relationTypeName": ""
          }
        ],
        "folder": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "datasetInput": [
        {
          "clientId": "",
          "createOrUpdateInput": {
            "boName": "",
            "boReference": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "boolProps": {},
            "boolArrayProps": {},
            "dateProps": {},
            "dateArrayProps": {},
            "tagProps": {},
            "tagArrayProps": {},
            "compoundCreateOrUpdateInput": {},
            "stringProps": {},
            "stringArrayProps": {},
            "doubleProps": {},
            "doubleArrayProps": {},
            "floatProps": {},
            "floatArrayProps": {},
            "intProps": {},
            "intArrayProps": {}
          },
          "datasetFileInfos": [
            {
              "clientId": "",
              "fileName": "",
              "namedReferencedName": "",
              "isText": "",
              "allowReplace": "",
              "boundingBoxesAvailable": "",
              "destinationVolume": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "boundingBoxes": [
                {
                  "xmin": "",
                  "ymin": "",
                  "zmin": "",
                  "xmax": "",
                  "ymax": "",
                  "zmax": ""
                }
              ]
            }
          ],
          "namedReferenceObjectInfos": [
            {
              "clientId": "",
              "createOrUpdateInput": {
                "boName": "",
                "boReference": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boolProps": {},
                "boolArrayProps": {},
                "dateProps": {},
                "dateArrayProps": {},
                "tagProps": {},
                "tagArrayProps": {},
                "compoundCreateOrUpdateInput": {},
                "stringProps": {},
                "stringArrayProps": {},
                "doubleProps": {},
                "doubleArrayProps": {},
                "floatProps": {},
                "floatArrayProps": {},
                "intProps": {},
                "intArrayProps": {}
              },
              "namedReferenceName": "",
              "namedReferenceType": ""
            }
          ],
          "basisName": "",
          "lastModifiedOfDataset": "0001-01-01T00:00:00",
          "itemRevRelationName": "",
          "createNewVersion": "",
          "mapAttributesWithoutDataset": "",
          "namedReferencePreference": "",
          "mappingAttributes": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ],
          "extraObject": [
            {
              "clientId": "",
              "createOrUpdateInput": {
                "boName": "",
                "boReference": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "boolProps": {},
                "boolArrayProps": {},
                "dateProps": {},
                "dateArrayProps": {},
                "tagProps": {},
                "tagArrayProps": {},
                "compoundCreateOrUpdateInput": {},
                "stringProps": {},
                "stringArrayProps": {},
                "doubleProps": {},
                "doubleArrayProps": {},
                "floatProps": {},
                "floatArrayProps": {},
                "intProps": {},
                "intArrayProps": {}
              },
              "relationTypeName": ""
            }
          ]
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

**响应（output）：**

```json
{
  "output": [
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
      "datasetOutput": [
        {
          "clientId": "",
          "dataset": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "commitInfo": [
            {
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "createNewVersion": "",
              "datasetFileTicketInfos": [
                {
                  "datasetFileInfo": {
                    "clientId": "",
                    "fileName": "",
                    "namedReferencedName": "",
                    "isText": "",
                    "allowReplace": "",
                    "boundingBoxesAvailable": "",
                    "boundingBoxes": [
                      {
                        "xmin": "",
                        "ymin": "",
                        "zmin": "",
                        "xmax": "",
                        "ymax": "",
                        "zmax": ""
                      }
                    ]
                  },
                  "ticket": ""
                }
              ]
            }
          ],
          "extraObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ],
          "namedRefObjs": [
            {
              "clientId": "",
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "extraItemObjs": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          }
        }
      ],
      "extraItemRevObjs": [
        {
          "clientId": "",
          "object": {
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

---

### 4.3 `createOrUpdateRelativeStructure`

**说明：** 创建或更新相对坐标系下的产品结构（父子相对变换）。

| API 版本 | Service | Url | Soa Inclusion |
|----------|---------|-----|---------------|
| 2007-01 | StructureManagement | `Cad-2007-01-StructureManagement/createOrUpdateRelativeStructure` | `Teamcenter.Soa.Cad._2007_01.StructureManagement.createOrUpdateRelativeStructure` |
| 2007-12 | StructureManagement | `Cad-2007-12-StructureManagement/createOrUpdateRelativeStructure` | `Teamcenter.Soa.Cad._2007_12.StructureManagement.createOrUpdateRelativeStructure` |
| 2008-06 | StructureManagement | `Cad-2008-06-StructureManagement/createOrUpdateRelativeStructure` | `Teamcenter.Soa.Cad._2008_06.StructureManagement.createOrUpdateRelativeStructure` |
| 2009-04 | StructureManagement | `Cad-2009-04-StructureManagement/createOrUpdateRelativeStructure` | `Teamcenter.Soa.Cad._2009_04.StructureManagement.createOrUpdateRelativeStructure` |
| 2013-05 | StructureManagement | `Cad-2013-05-StructureManagement/createOrUpdateRelativeStructure` | `Teamcenter.Soa.Cad._2013_05.StructureManagement.createOrUpdateRelativeStructure` |
| 2024-12 | StructureManagement | `Cad-2024-12-StructureManagement/createOrUpdateRelativeStructure` | `Teamcenter.Soa.Cad._2024_12.StructureManagement.createOrUpdateRelativeStructure` |
| 2025-06 | StructureManagement | `Cad-2025-06-StructureManagement/createOrUpdateRelativeStructure` | `Teamcenter.Soa.Cad._2025_06.StructureManagement.createOrUpdateRelativeStructure` |

#### 版本 2007-01

##### 4.3.1 createOrUpdateRelativeStructure

**接口路径：** `Cad-2007-01-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ],
      "precise": ""
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "cadOccIdAttrName": "",
    "itemTypes": [
      ""
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

---

#### 版本 2007-12

##### 4.3.2 createOrUpdateRelativeStructure

**接口路径：** `Cad-2007-12-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ],
      "precise": ""
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": "",
    "itemTypes": [
      ""
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

---

#### 版本 2008-06

##### 4.3.3 createOrUpdateRelativeStructure

**接口路径：** `Cad-2008-06-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ],
      "precise": ""
    }
  ],
  "bomViewTypeName": "",
  "complete": "",
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

---

#### 版本 2009-04

##### 4.3.4 createOrUpdateRelativeStructure

**接口路径：** `Cad-2009-04-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2009-04`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2009_04.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ]
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

---

#### 版本 2013-05

##### 4.3.5 createOrUpdateRelativeStructure

**接口路径：** `Cad-2013-05-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2013-05`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2013_05.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "childBomViewTypeName": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "moveInfo": {
              "commonParent": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "sourceAssembly": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "occThreadPathToBeMoved": [
                ""
              ],
              "occThreadPathTargetParent": [
                {
                  "parent": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "idType": "OccurrenceThread",
                  "id": "",
                  "isNew": ""
                }
              ]
            }
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

---

#### 版本 2024-12

##### 4.3.6 createOrUpdateRelativeStructure

**接口路径：** `Cad-2024-12-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2024-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2024_12.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "childBomViewTypeName": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "usageRevisionType": "",
            "moveInfo": {
              "commonParent": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "sourceAssembly": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "occThreadPathToBeMoved": [
                ""
              ],
              "occThreadPathTargetParent": [
                {
                  "parent": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "idType": "OccurrenceThread",
                  "id": "",
                  "isNew": ""
                }
              ]
            }
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

---

#### 版本 2025-06

##### 4.3.7 createOrUpdateRelativeStructure

**接口路径：** `Cad-2025-06-StructureManagement/createOrUpdateRelativeStructure`

**API 版本：** `2025-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2025_06.StructureManagement.createOrUpdateRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parentInfo": {
        "clientId": "",
        "complete": "",
        "bomViewTypeName": "",
        "parent": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "changeContext": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "lastModifiedOfBVR": "0001-01-01T00:00:00",
        "precise": "",
        "supportingClassAttrs": [
          {
            "topLineAttrThatRefersToObject": "",
            "attrsToSet": [
              {
                "name": "",
                "values": [
                  ""
                ]
              }
            ]
          }
        ]
      },
      "childInfo": [
        {
          "clientId": "",
          "childBomViewTypeName": "",
          "cadOccId": "",
          "child": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "occInfo": {
            "attrsToSet": [
              {
                "name": "",
                "value": ""
              }
            ],
            "asRequired": "",
            "occTransform": [],
            "occNotes": [
              {
                "noteType": "",
                "noteText": ""
              }
            ],
            "usageRevisionType": "",
            "preAllocatedPsOccThreadUid": "",
            "moveInfo": {
              "commonParent": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "sourceAssembly": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "occThreadPathToBeMoved": [
                ""
              ],
              "occThreadPathTargetParent": [
                {
                  "parent": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "idType": "OccurrenceThread",
                  "id": "",
                  "isNew": ""
                }
              ]
            }
          }
        }
      ]
    }
  ],
  "pref": {
    "overwriteForLastModDate": "",
    "continueOnError": "",
    "bomViewTypeName": "",
    "cadOccIdAttrName": "",
    "objectTypes": [
      ""
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": {},
  "serviceData": "IServiceData"
}
```

---

### 4.4 `deleteAssemblyArrangements`

**说明：** 删除装配配置（Assembly Arrangement）相关结构数据。

| API 版本 | Service | Url | Soa Inclusion |
|----------|---------|-----|---------------|
| 2007-01 | StructureManagement | `Cad-2007-01-StructureManagement/deleteAssemblyArrangements` | `Teamcenter.Soa.Cad._2007_01.StructureManagement.deleteAssemblyArrangements` |
| 2007-12 | StructureManagement | `Cad-2007-12-StructureManagement/deleteAssemblyArrangements` | `Teamcenter.Soa.Cad._2007_12.StructureManagement.deleteAssemblyArrangements` |

#### 版本 2007-01

##### 4.4.1 deleteAssemblyArrangements

**接口路径：** `Cad-2007-01-StructureManagement/deleteAssemblyArrangements`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.deleteAssemblyArrangements`

**请求（input）：**

```json
{
  "info": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "arrangements": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "bomViewTypeName": ""
}
```

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

---

#### 版本 2007-12

##### 4.4.2 deleteAssemblyArrangements

**接口路径：** `Cad-2007-12-StructureManagement/deleteAssemblyArrangements`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.deleteAssemblyArrangements`

**请求（input）：**

```json
{
  "info": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "arrangements": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": ""
  }
}
```

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

---

### 4.5 `deleteRelativeStructure`

**说明：** 删除相对产品结构中的指定结构关系或子结构。

| API 版本 | Service | Url | Soa Inclusion |
|----------|---------|-----|---------------|
| 2007-01 | StructureManagement | `Cad-2007-01-StructureManagement/deleteRelativeStructure` | `Teamcenter.Soa.Cad._2007_01.StructureManagement.deleteRelativeStructure` |
| 2007-12 | StructureManagement | `Cad-2007-12-StructureManagement/deleteRelativeStructure` | `Teamcenter.Soa.Cad._2007_12.StructureManagement.deleteRelativeStructure` |
| 2008-06 | StructureManagement | `Cad-2008-06-StructureManagement/deleteRelativeStructure` | `Teamcenter.Soa.Cad._2008_06.StructureManagement.deleteRelativeStructure` |

#### 版本 2007-01

##### 4.5.1 deleteRelativeStructure

**接口路径：** `Cad-2007-01-StructureManagement/deleteRelativeStructure`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.deleteRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        ""
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "cadOccIdAttrName": ""
  }
}
```

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

---

#### 版本 2007-12

##### 4.5.2 deleteRelativeStructure

**接口路径：** `Cad-2007-12-StructureManagement/deleteRelativeStructure`

**API 版本：** `2007-12`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_12.StructureManagement.deleteRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        ""
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": ""
  }
}
```

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

---

#### 版本 2008-06

##### 4.5.3 deleteRelativeStructure

**接口路径：** `Cad-2008-06-StructureManagement/deleteRelativeStructure`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.deleteRelativeStructure`

**请求（input）：**

```json
{
  "inputs": [
    {
      "lastModifiedOfBVR": "0001-01-01T00:00:00",
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childInfo": [
        ""
      ]
    }
  ],
  "bomViewTypeName": "",
  "pref": {
    "overwriteForLastModDate": "",
    "cadOccIdAttrName": ""
  }
}
```

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

---

### 4.6 `expandFoldersForCAD`

**说明：** 为 CAD 客户端按文件夹层次展开对象，返回可在 CAD 环境中打开/集成的对象列表。

| API 版本 | Service | Url | Soa Inclusion |
|----------|---------|-----|---------------|
| 2007-01 | DataManagement | `Cad-2007-01-DataManagement/expandFoldersForCAD` | `Teamcenter.Soa.Cad._2007_01.DataManagement.expandFoldersForCAD` |
| 2008-06 | DataManagement | `Cad-2008-06-DataManagement/expandFoldersForCAD` | `Teamcenter.Soa.Cad._2008_06.DataManagement.expandFoldersForCAD` |

#### 版本 2007-01

##### 4.6.1 expandFoldersForCAD

**接口路径：** `Cad-2007-01-DataManagement/expandFoldersForCAD`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.DataManagement.expandFoldersForCAD`

**请求（input）：**

```json
{
  "folders": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "pref": {
    "expItemRev": "",
    "latestNRevs": "",
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": [
    {
      "inputFolder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "fstlvlFolders": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "itemsOutput": [
        {
          "outputItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevsOutput": [
            {
              "outputItemRevs": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "outputDatasets": [
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
      "itemRevsOutput": [
        {
          "outputItemRevs": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "outputDatasets": [
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

---

#### 版本 2008-06

##### 4.6.2 expandFoldersForCAD

**接口路径：** `Cad-2008-06-DataManagement/expandFoldersForCAD`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.DataManagement.expandFoldersForCAD`

**请求（input）：**

```json
{
  "folders": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "pref": {
    "expItemRev": "",
    "latestNRevs": "",
    "info": [
      {
        "relationName": "",
        "objectTypeNames": [
          ""
        ]
      }
    ],
    "contentTypesFilter": [
      ""
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": [
    {
      "inputFolder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "fstlvlFolders": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "itemsOutput": [
        {
          "outputItem": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevsOutput": [
            {
              "outputItemRevs": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "outputDatasets": [
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
      "itemRevsOutput": [
        {
          "outputItemRevs": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "outputDatasets": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ]
        }
      ],
      "contents": [
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

---

### 4.7 `expandPSAllLevels`

**说明：** 从产品结构（PS）指定父 BOMLine 递归展开全部层级，返回完整 BOM 树。

| API 版本 | Service | Url | Soa Inclusion |
|----------|---------|-----|---------------|
| 2007-01 | StructureManagement | `Cad-2007-01-StructureManagement/expandPSAllLevels` | `Teamcenter.Soa.Cad._2007_01.StructureManagement.expandPSAllLevels` |
| 2008-06 | StructureManagement | `Cad-2008-06-StructureManagement/expandPSAllLevels` | `Teamcenter.Soa.Cad._2008_06.StructureManagement.expandPSAllLevels` |

#### 版本 2007-01

##### 4.7.1 expandPSAllLevels

**接口路径：** `Cad-2007-01-StructureManagement/expandPSAllLevels`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.expandPSAllLevels`

**请求（input）：**

```json
{
  "input": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemRevOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentDatasets": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "datasets": [
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

---

#### 版本 2008-06

##### 4.7.2 expandPSAllLevels

**接口路径：** `Cad-2008-06-StructureManagement/expandPSAllLevels`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.expandPSAllLevels`

**请求（input）：**

```json
{
  "info": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None2"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relatedObjAndNamedRefs": [
          {
            "objectTypeName": "",
            "namedReferenceNames": [
              ""
            ]
          }
        ],
        "namedRefHandler": "UseNamedRefsList"
      }
    ],
    "includeOccurrenceTypes": [
      ""
    ],
    "excludeOccurrenceTypes": [
      ""
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "objectOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentRelatedObjects": [
          {
            "relatedObject": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "namedRefList": [
              {
                "namedReferenceType": "",
                "namedReferenceName": "",
                "referenceObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "fileTicket": ""
              }
            ]
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "objectOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relatedObjects": [
            {
              "relatedObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedRefList": [
                {
                  "namedReferenceType": "",
                  "namedReferenceName": "",
                  "referenceObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "fileTicket": ""
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

---

### 4.8 `expandPSOneLevel`

**说明：** 从产品结构父 BOMLine 仅展开下一层子 BOMLine。

| API 版本 | Service | Url | Soa Inclusion |
|----------|---------|-----|---------------|
| 2007-01 | StructureManagement | `Cad-2007-01-StructureManagement/expandPSOneLevel` | `Teamcenter.Soa.Cad._2007_01.StructureManagement.expandPSOneLevel` |
| 2008-06 | StructureManagement | `Cad-2008-06-StructureManagement/expandPSOneLevel` | `Teamcenter.Soa.Cad._2008_06.StructureManagement.expandPSOneLevel` |

#### 版本 2007-01

##### 4.8.1 expandPSOneLevel

**接口路径：** `Cad-2007-01-StructureManagement/expandPSOneLevel`

**API 版本：** `2007-01`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2007_01.StructureManagement.expandPSOneLevel`

**请求（input）：**

```json
{
  "input": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relationTypeNames": [
          ""
        ]
      }
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "itemRevOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentDatasets": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "itemRevOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "datasets": [
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

---

#### 版本 2008-06

##### 4.8.2 expandPSOneLevel

**接口路径：** `Cad-2008-06-StructureManagement/expandPSOneLevel`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Cad`

**Soa Inclusion：** `Teamcenter.Soa.Cad._2008_06.StructureManagement.expandPSOneLevel`

**请求（input）：**

```json
{
  "info": {
    "parentBomLines": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "excludeFilter": "None2"
  },
  "pref": {
    "expItemRev": "",
    "info": [
      {
        "relationName": "",
        "relatedObjAndNamedRefs": [
          {
            "objectTypeName": "",
            "namedReferenceNames": [
              ""
            ]
          }
        ],
        "namedRefHandler": "UseNamedRefsList"
      }
    ],
    "includeOccurrenceTypes": [
      ""
    ],
    "excludeOccurrenceTypes": [
      ""
    ]
  }
}
```

**响应（output）：**

```json
{
  "output": [
    {
      "parent": {
        "bomLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "objectOfBOMLine": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "parentRelatedObjects": [
          {
            "relatedObject": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "namedRefList": [
              {
                "namedReferenceType": "",
                "namedReferenceName": "",
                "referenceObject": {
                  "uid": "",
                  "type": "",
                  "className": ""
                },
                "fileTicket": ""
              }
            ]
          }
        ]
      },
      "children": [
        {
          "bomLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "objectOfBOMLine": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relatedObjects": [
            {
              "relatedObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "namedRefList": [
                {
                  "namedReferenceType": "",
                  "namedReferenceName": "",
                  "referenceObject": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "fileTicket": ""
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

---

---

## 5. 附录

### 操作一览（合并索引）

| API 版本 | Service | 操作 | Url |
|----------|---------|------|-----|
| 2007-01 | DataManagement | `createOrUpdateParts` | `Cad-2007-01-DataManagement/createOrUpdateParts` |
| 2007-01 | DataManagement | `createOrUpdateRelations` | `Cad-2007-01-DataManagement/createOrUpdateRelations` |
| 2007-01 | DataManagement | `expandFoldersForCAD` | `Cad-2007-01-DataManagement/expandFoldersForCAD` |
| 2007-01 | DataManagement | `expandGRMRelations` | `Cad-2007-01-DataManagement/expandGRMRelations` |
| 2007-01 | DataManagement | `expandPrimaryObjects` | `Cad-2007-01-DataManagement/expandPrimaryObjects` |
| 2007-01 | DataManagement | `generateAlternateIds` | `Cad-2007-01-DataManagement/generateAlternateIds` |
| 2007-01 | DataManagement | `getAllAttrMappings` | `Cad-2007-01-DataManagement/getAllAttrMappings` |
| 2007-01 | DataManagement | `getAttrMappingsForDatasetType` | `Cad-2007-01-DataManagement/getAttrMappingsForDatasetType` |
| 2007-01 | DataManagement | `getAvailableTypes` | `Cad-2007-01-DataManagement/getAvailableTypes` |
| 2007-01 | DataManagement | `resolveAttrMappingsForDataset` | `Cad-2007-01-DataManagement/resolveAttrMappingsForDataset` |
| 2007-01 | StructureManagement | `closeBOMWindows` | `Cad-2007-01-StructureManagement/closeBOMWindows` |
| 2007-01 | StructureManagement | `createBOMWindows` | `Cad-2007-01-StructureManagement/createBOMWindows` |
| 2007-01 | StructureManagement | `createOrUpdateAbsoluteStructure` | `Cad-2007-01-StructureManagement/createOrUpdateAbsoluteStructure` |
| 2007-01 | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2007-01-StructureManagement/createOrUpdateRelativeStructure` |
| 2007-01 | StructureManagement | `deleteAssemblyArrangements` | `Cad-2007-01-StructureManagement/deleteAssemblyArrangements` |
| 2007-01 | StructureManagement | `deleteRelativeStructure` | `Cad-2007-01-StructureManagement/deleteRelativeStructure` |
| 2007-01 | StructureManagement | `expandPSAllLevels` | `Cad-2007-01-StructureManagement/expandPSAllLevels` |
| 2007-01 | StructureManagement | `expandPSOneLevel` | `Cad-2007-01-StructureManagement/expandPSOneLevel` |
| 2007-01 | StructureManagement | `getRevisionRules` | `Cad-2007-01-StructureManagement/getRevisionRules` |
| 2007-01 | StructureManagement | `getVariantRules` | `Cad-2007-01-StructureManagement/getVariantRules` |
| 2007-06 | StructureManagement | `createOrUpdateClassicOptions` | `Cad-2007-06-StructureManagement/createOrUpdateClassicOptions` |
| 2007-06 | StructureManagement | `createOrUpdateVariantConditions` | `Cad-2007-06-StructureManagement/createOrUpdateVariantConditions` |
| 2007-06 | StructureManagement | `deleteClassicOptions` | `Cad-2007-06-StructureManagement/deleteClassicOptions` |
| 2007-06 | StructureManagement | `deleteVariantConditions` | `Cad-2007-06-StructureManagement/deleteVariantConditions` |
| 2007-06 | StructureManagement | `getConfiguredItemRevision` | `Cad-2007-06-StructureManagement/getConfiguredItemRevision` |
| 2007-09 | StructureManagement | `createOrUpdateVariantConditions2` | `Cad-2007-09-StructureManagement/createOrUpdateVariantConditions2` |
| 2007-12 | DataManagement | `createOrUpdateParts` | `Cad-2007-12-DataManagement/createOrUpdateParts` |
| 2007-12 | StructureManagement | `createOrUpdateAbsoluteStructure` | `Cad-2007-12-StructureManagement/createOrUpdateAbsoluteStructure` |
| 2007-12 | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2007-12-StructureManagement/createOrUpdateRelativeStructure` |
| 2007-12 | StructureManagement | `deleteAssemblyArrangements` | `Cad-2007-12-StructureManagement/deleteAssemblyArrangements` |
| 2007-12 | StructureManagement | `deleteRelativeStructure` | `Cad-2007-12-StructureManagement/deleteRelativeStructure` |
| 2007-12 | StructureManagement | `queryClassicOptions` | `Cad-2007-12-StructureManagement/queryClassicOptions` |
| 2007-12 | StructureManagement | `queryVariantConditions` | `Cad-2007-12-StructureManagement/queryVariantConditions` |
| 2008-03 | DataManagement | `createOrUpdateParts` | `Cad-2008-03-DataManagement/createOrUpdateParts` |
| 2008-03 | DataManagement | `resolveAttrMappings` | `Cad-2008-03-DataManagement/resolveAttrMappings` |
| 2008-03 | StructureManagement | `askChildPathBOMLines` | `Cad-2008-03-StructureManagement/askChildPathBOMLines` |
| 2008-06 | DataManagement | `createOrUpdateParts` | `Cad-2008-06-DataManagement/createOrUpdateParts` |
| 2008-06 | DataManagement | `expandFoldersForCAD` | `Cad-2008-06-DataManagement/expandFoldersForCAD` |
| 2008-06 | StructureManagement | `createOrUpdateAbsoluteStructure` | `Cad-2008-06-StructureManagement/createOrUpdateAbsoluteStructure` |
| 2008-06 | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2008-06-StructureManagement/createOrUpdateRelativeStructure` |
| 2008-06 | StructureManagement | `createVariantRules` | `Cad-2008-06-StructureManagement/createVariantRules` |
| 2008-06 | StructureManagement | `deleteRelativeStructure` | `Cad-2008-06-StructureManagement/deleteRelativeStructure` |
| 2008-06 | StructureManagement | `expandPSAllLevels` | `Cad-2008-06-StructureManagement/expandPSAllLevels` |
| 2008-06 | StructureManagement | `expandPSOneLevel` | `Cad-2008-06-StructureManagement/expandPSOneLevel` |
| 2008-06 | StructureManagement | `getAbsoluteStructureData` | `Cad-2008-06-StructureManagement/getAbsoluteStructureData` |
| 2008-06 | StructureManagement | `reconfigureBOMWindows` | `Cad-2008-06-StructureManagement/reconfigureBOMWindows` |
| 2008-06 | StructureManagement | `saveBOMWindows` | `Cad-2008-06-StructureManagement/saveBOMWindows` |
| 2009-04 | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2009-04-StructureManagement/createOrUpdateRelativeStructure` |
| 2010-09 | DataManagement | `createOrUpdateParts` | `Cad-2010-09-DataManagement/createOrUpdateParts` |
| 2011-06 | DataManagement | `getAllAttrMappings2` | `Cad-2011-06-DataManagement/getAllAttrMappings2` |
| 2012-09 | DataManagement | `createOrUpdateParts` | `Cad-2012-09-DataManagement/createOrUpdateParts` |
| 2013-05 | StructureManagement | `askChildPathBOMLines2` | `Cad-2013-05-StructureManagement/askChildPathBOMLines2` |
| 2013-05 | StructureManagement | `createBOMWindows2` | `Cad-2013-05-StructureManagement/createBOMWindows2` |
| 2013-05 | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2013-05-StructureManagement/createOrUpdateRelativeStructure` |
| 2014-10 | DataManagement | `getAttrMappings` | `Cad-2014-10-DataManagement/getAttrMappings` |
| 2016-03 | DataManagement | `createOrUpdateModelViewPalette` | `Cad-2016-03-DataManagement/createOrUpdateModelViewPalette` |
| 2016-03 | DataManagement | `createOrUpdateModelViewProxies` | `Cad-2016-03-DataManagement/createOrUpdateModelViewProxies` |
| 2016-03 | StructureManagement | `findModelViewsInStructure` | `Cad-2016-03-StructureManagement/findModelViewsInStructure` |
| 2016-09 | StructureManagement | `continueFindModelViews` | `Cad-2016-09-StructureManagement/continueFindModelViews` |
| 2016-09 | StructureManagement | `continueReconcilePalette` | `Cad-2016-09-StructureManagement/continueReconcilePalette` |
| 2016-09 | StructureManagement | `startFindModelViews` | `Cad-2016-09-StructureManagement/startFindModelViews` |
| 2016-09 | StructureManagement | `startReconcilePalette` | `Cad-2016-09-StructureManagement/startReconcilePalette` |
| 2018-06 | StructureManagement | `writeAssemblyConfigurationDetails` | `Cad-2018-06-StructureManagement/writeAssemblyConfigurationDetails` |
| 2019-06 | StructureManagement | `createOrReConfigureBOMWindows` | `Cad-2019-06-StructureManagement/createOrReConfigureBOMWindows` |
| 2020-01 | AppSessionManagement | `createOrUpdateSavedSession` | `Cad-2020-01-AppSessionManagement/createOrUpdateSavedSession` |
| 2020-01 | AppSessionManagement | `openSavedSession` | `Cad-2020-01-AppSessionManagement/openSavedSession` |
| 2023-06 | StructureManagement | `expandPSOneLevel2` | `Cad-2023-06-StructureManagement/expandPSOneLevel2` |
| 2023-12 | StructureManagement | `createOrUpdateAbsoluteStructure` | `Cad-2023-12-StructureManagement/createOrUpdateAbsoluteStructure` |
| 2024-12 | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2024-12-StructureManagement/createOrUpdateRelativeStructure` |
| 2025-06 | StructureManagement | `createOrUpdateRelativeStructure` | `Cad-2025-06-StructureManagement/createOrUpdateRelativeStructure` |

### 典型 BOM 流程（StructureManagement）

1. `createBOMWindows` — 创建 BOM 窗口
2. `expandPSAllLevels` 或 `expandPSOneLevel` — 展开结构
3. （编辑结构，如 `createOrUpdateRelativeStructure` 等）
4. `saveBOMWindows` — 保存修改
5. `closeBOMWindows` — 关闭窗口

> 无状态 BOM 操作建议在 SOA 连接上启用 `stateless` 模式（由客户端连接属性管理）。

### 重新生成

```bash
node generate-cad-doc.js
```
