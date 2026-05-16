# Teamcenter SOA API — Core 接口文档（TC 2512）

> 本文档汇总 **Core** Library 下**全部 API 版本（年-月）**的 SOA 操作，已按版本与 Service 双向合并整理。
> 数据来源：TC 2512 SOA Api Browser（`structure.js`）。
>
> - **API 版本数：** 38 个（`2006-03` ～ `2025-06`）
> - **Service 数：** 15 个
> - **操作总数：** 234 个（含 **13** 组同名跨版本操作）
> - **Url 格式：** `Core-{Year}-{Service}/{operation}`

---

## 目录

1. [API 版本总览](#1-api-版本总览)
2. [按 Service 合并（跨版本）](#2-按-service-合并跨版本)
3. [按 API 版本（年-月）归档](#3-按-api-版本年-月归档)
4. [附录](#4-附录)

---

## 1. API 版本总览

Core 是 Teamcenter 最核心的 SOA 库，涵盖会话、数据管理、文件、结构等 **15** 个 Service，接口契约自 **2006-03** 持续演进至 **2025-06**。

<details>
<summary>展开完整版本×操作对照表（234 条）</summary>

| API 版本 | Service | 操作 | Url |
|----------|---------|------|-----|
| **2006-03** | DataManagement | `changeOwnership` | `Core-2006-03-DataManagement/changeOwnership` |
| **2006-03** | DataManagement | `createDatasets` | `Core-2006-03-DataManagement/createDatasets` |
| **2006-03** | DataManagement | `createFolders` | `Core-2006-03-DataManagement/createFolders` |
| **2006-03** | DataManagement | `createItems` | `Core-2006-03-DataManagement/createItems` |
| **2006-03** | DataManagement | `createRelations` | `Core-2006-03-DataManagement/createRelations` |
| **2006-03** | DataManagement | `deleteObjects` | `Core-2006-03-DataManagement/deleteObjects` |
| **2006-03** | DataManagement | `deleteRelations` | `Core-2006-03-DataManagement/deleteRelations` |
| **2006-03** | DataManagement | `generateItemIdsAndInitialRevisionIds` | `Core-2006-03-DataManagement/generateItemIdsAndInitialRevisionIds` |
| **2006-03** | DataManagement | `generateRevisionIds` | `Core-2006-03-DataManagement/generateRevisionIds` |
| **2006-03** | DataManagement | `getProperties` | `Core-2006-03-DataManagement/getProperties` |
| **2006-03** | DataManagement | `revise` | `Core-2006-03-DataManagement/revise` |
| **2006-03** | DataManagement | `setDisplayProperties` | `Core-2006-03-DataManagement/setDisplayProperties` |
| **2006-03** | FileManagement | `commitDatasetFiles` | `Core-2006-03-FileManagement/commitDatasetFiles` |
| **2006-03** | FileManagement | `getDatasetWriteTickets` | `Core-2006-03-FileManagement/getDatasetWriteTickets` |
| **2006-03** | FileManagement | `getFileReadTickets` | `Core-2006-03-FileManagement/getFileReadTickets` |
| **2006-03** | Reservation | `cancelCheckout` | `Core-2006-03-Reservation/cancelCheckout` |
| **2006-03** | Reservation | `checkin` | `Core-2006-03-Reservation/checkin` |
| **2006-03** | Reservation | `checkout` | `Core-2006-03-Reservation/checkout` |
| **2006-03** | Reservation | `getReservationHistory` | `Core-2006-03-Reservation/getReservationHistory` |
| **2006-03** | Session | `getAvailableServices` | `Core-2006-03-Session/getAvailableServices` |
| **2006-03** | Session | `getGroupMembership` | `Core-2006-03-Session/getGroupMembership` |
| **2006-03** | Session | `getPreferences` | `Core-2006-03-Session/getPreferences` |
| **2006-03** | Session | `getSessionGroupMember` | `Core-2006-03-Session/getSessionGroupMember` |
| **2006-03** | Session | `login` | `Core-2006-03-Session/login` |
| **2006-03** | Session | `loginSSO` | `Core-2006-03-Session/loginSSO` |
| **2006-03** | Session | `logout` | `Core-2006-03-Session/logout` |
| **2006-03** | Session | `setPreferences` | `Core-2006-03-Session/setPreferences` |
| **2006-03** | Session | `setSessionGroupMember` | `Core-2006-03-Session/setSessionGroupMember` |
| **2007-01** | DataManagement | `createOrUpdateForms` | `Core-2007-01-DataManagement/createOrUpdateForms` |
| **2007-01** | DataManagement | `generateUID` | `Core-2007-01-DataManagement/generateUID` |
| **2007-01** | DataManagement | `getDatasetCreationRelatedInfo` | `Core-2007-01-DataManagement/getDatasetCreationRelatedInfo` |
| **2007-01** | DataManagement | `getItemCreationRelatedInfo` | `Core-2007-01-DataManagement/getItemCreationRelatedInfo` |
| **2007-01** | DataManagement | `getItemFromId` | `Core-2007-01-DataManagement/getItemFromId` |
| **2007-01** | DataManagement | `moveToNewFolder` | `Core-2007-01-DataManagement/moveToNewFolder` |
| **2007-01** | DataManagement | `refreshObjects` | `Core-2007-01-DataManagement/refreshObjects` |
| **2007-01** | DataManagement | `saveAsNewItem` | `Core-2007-01-DataManagement/saveAsNewItem` |
| **2007-01** | DataManagement | `setProperties` | `Core-2007-01-DataManagement/setProperties` |
| **2007-01** | DataManagement | `whereReferenced` | `Core-2007-01-DataManagement/whereReferenced` |
| **2007-01** | DataManagement | `whereUsed` | `Core-2007-01-DataManagement/whereUsed` |
| **2007-01** | FileManagement | `getTransientFileTicketsForUpload` | `Core-2007-01-FileManagement/getTransientFileTicketsForUpload` |
| **2007-01** | ManagedRelations | `createRelation` | `Core-2007-01-ManagedRelations/createRelation` |
| **2007-01** | ManagedRelations | `getTraceReport` | `Core-2007-01-ManagedRelations/getTraceReport` |
| **2007-01** | ManagedRelations | `modifyRelation` | `Core-2007-01-ManagedRelations/modifyRelation` |
| **2007-01** | Session | `getPreferences` | `Core-2007-01-Session/getPreferences` |
| **2007-01** | Session | `getTCSessionInfo` | `Core-2007-01-Session/getTCSessionInfo` |
| **2007-01** | Session | `setObjectPropertyPolicy` | `Core-2007-01-Session/setObjectPropertyPolicy` |
| **2007-06** | DataManagement | `expandGRMRelationsForPrimary` | `Core-2007-06-DataManagement/expandGRMRelationsForPrimary` |
| **2007-06** | DataManagement | `expandGRMRelationsForSecondary` | `Core-2007-06-DataManagement/expandGRMRelationsForSecondary` |
| **2007-06** | DataManagement | `getAvailableTypes` | `Core-2007-06-DataManagement/getAvailableTypes` |
| **2007-06** | DataManagement | `getDatasetTypeInfo` | `Core-2007-06-DataManagement/getDatasetTypeInfo` |
| **2007-06** | DataManagement | `purgeSequences` | `Core-2007-06-DataManagement/purgeSequences` |
| **2007-06** | DataManagement | `setOrRemoveImmunity` | `Core-2007-06-DataManagement/setOrRemoveImmunity` |
| **2007-06** | DataManagement | `validateItemIdsAndRevIds` | `Core-2007-06-DataManagement/validateItemIdsAndRevIds` |
| **2007-06** | DataManagement | `whereReferencedByRelationName` | `Core-2007-06-DataManagement/whereReferencedByRelationName` |
| **2007-06** | LOV | `getAttachedLOVs` | `Core-2007-06-LOV/getAttachedLOVs` |
| **2007-06** | PropDescriptor | `getAttachedPropDescs` | `Core-2007-06-PropDescriptor/getAttachedPropDescs` |
| **2007-06** | Session | `refreshPOMCachePerRequest` | `Core-2007-06-Session/refreshPOMCachePerRequest` |
| **2007-09** | DataManagement | `expandGRMRelationsForPrimary` | `Core-2007-09-DataManagement/expandGRMRelationsForPrimary` |
| **2007-09** | DataManagement | `expandGRMRelationsForSecondary` | `Core-2007-09-DataManagement/expandGRMRelationsForSecondary` |
| **2007-09** | DataManagement | `loadObjects` | `Core-2007-09-DataManagement/loadObjects` |
| **2007-09** | DataManagement | `removeNamedReferenceFromDataset` | `Core-2007-09-DataManagement/removeNamedReferenceFromDataset` |
| **2007-09** | ProjectLevelSecurity | `assignOrRemoveObjects` | `Core-2007-09-ProjectLevelSecurity/assignOrRemoveObjects` |
| **2007-12** | DataManagement | `createAlternateIdentifiers` | `Core-2007-12-DataManagement/createAlternateIdentifiers` |
| **2007-12** | DataManagement | `getContextsAndIdentifierTypes` | `Core-2007-12-DataManagement/getContextsAndIdentifierTypes` |
| **2007-12** | DataManagement | `listAlternateIdDisplayRules` | `Core-2007-12-DataManagement/listAlternateIdDisplayRules` |
| **2007-12** | DataManagement | `validateAlternateIds` | `Core-2007-12-DataManagement/validateAlternateIds` |
| **2007-12** | Session | `setAndEvaluateIdDisplayRule` | `Core-2007-12-Session/setAndEvaluateIdDisplayRule` |
| **2007-12** | Session | `setUserSessionState` | `Core-2007-12-Session/setUserSessionState` |
| **2008-03** | Session | `connect` | `Core-2008-03-Session/connect` |
| **2008-03** | Session | `getFavorites` | `Core-2008-03-Session/getFavorites` |
| **2008-03** | Session | `setFavorites` | `Core-2008-03-Session/setFavorites` |
| **2008-05** | DataManagement | `unloadObjects` | `Core-2008-05-DataManagement/unloadObjects` |
| **2008-06** | DataManagement | `addParticipants` | `Core-2008-06-DataManagement/addParticipants` |
| **2008-06** | DataManagement | `createConnections` | `Core-2008-06-DataManagement/createConnections` |
| **2008-06** | DataManagement | `createDatasets2` | `Core-2008-06-DataManagement/createDatasets2` |
| **2008-06** | DataManagement | `createObjects` | `Core-2008-06-DataManagement/createObjects` |
| **2008-06** | DataManagement | `createOrUpdateGDELinks` | `Core-2008-06-DataManagement/createOrUpdateGDELinks` |
| **2008-06** | DataManagement | `createOrUpdateItemElements` | `Core-2008-06-DataManagement/createOrUpdateItemElements` |
| **2008-06** | DataManagement | `createOrUpdateRelations` | `Core-2008-06-DataManagement/createOrUpdateRelations` |
| **2008-06** | DataManagement | `findDisplayableSubBusinessObjects` | `Core-2008-06-DataManagement/findDisplayableSubBusinessObjects` |
| **2008-06** | DataManagement | `getItemAndRelatedObjects` | `Core-2008-06-DataManagement/getItemAndRelatedObjects` |
| **2008-06** | DataManagement | `getNextIds` | `Core-2008-06-DataManagement/getNextIds` |
| **2008-06** | DataManagement | `getNRPatternsWithCounters` | `Core-2008-06-DataManagement/getNRPatternsWithCounters` |
| **2008-06** | DataManagement | `getRevNRAttachDetails` | `Core-2008-06-DataManagement/getRevNRAttachDetails` |
| **2008-06** | DataManagement | `removeParticipants` | `Core-2008-06-DataManagement/removeParticipants` |
| **2008-06** | DataManagement | `revise2` | `Core-2008-06-DataManagement/revise2` |
| **2008-06** | DataManagement | `saveAsNewItem2` | `Core-2008-06-DataManagement/saveAsNewItem2` |
| **2008-06** | DispatcherManagement | `createDispatcherRequest` | `Core-2008-06-DispatcherManagement/createDispatcherRequest` |
| **2008-06** | ManagedRelations | `getManagedRelations` | `Core-2008-06-ManagedRelations/getManagedRelations` |
| **2008-06** | PropDescriptor | `getCreateDesc` | `Core-2008-06-PropDescriptor/getCreateDesc` |
| **2008-06** | Reservation | `transferCheckout` | `Core-2008-06-Reservation/transferCheckout` |
| **2008-06** | Session | `getDisplayStrings` | `Core-2008-06-Session/getDisplayStrings` |
| **2008-06** | Session | `login` | `Core-2008-06-Session/login` |
| **2008-06** | Session | `loginSSO` | `Core-2008-06-Session/loginSSO` |
| **2008-06** | Session | `setObjectPropertyPolicy` | `Core-2008-06-Session/setObjectPropertyPolicy` |
| **2008-06** | StructureManagement | `createInStructureAssociations` | `Core-2008-06-StructureManagement/createInStructureAssociations` |
| **2008-06** | StructureManagement | `getPrimariesOfInStructureAssociation` | `Core-2008-06-StructureManagement/getPrimariesOfInStructureAssociation` |
| **2008-06** | StructureManagement | `getSecondariesOfInStructureAssociation` | `Core-2008-06-StructureManagement/getSecondariesOfInStructureAssociation` |
| **2008-06** | StructureManagement | `removeInStructureAssociations` | `Core-2008-06-StructureManagement/removeInStructureAssociations` |
| **2009-04** | ProjectLevelSecurity | `loadProjectDataForUser` | `Core-2009-04-ProjectLevelSecurity/loadProjectDataForUser` |
| **2009-04** | Session | `startOperation` | `Core-2009-04-Session/startOperation` |
| **2009-04** | Session | `stopOperation` | `Core-2009-04-Session/stopOperation` |
| **2009-10** | DataManagement | `getItemFromAttribute` | `Core-2009-10-DataManagement/getItemFromAttribute` |
| **2009-10** | DataManagement | `getTableProperties` | `Core-2009-10-DataManagement/getTableProperties` |
| **2009-10** | DataManagement | `setTableProperties` | `Core-2009-10-DataManagement/setTableProperties` |
| **2009-10** | ProjectLevelSecurity | `getUserProjects` | `Core-2009-10-ProjectLevelSecurity/getUserProjects` |
| **2010-04** | DataManagement | `createDatasets` | `Core-2010-04-DataManagement/createDatasets` |
| **2010-04** | DataManagement | `findDisplayableSubBusinessObjectsWithDisplayNames` | `Core-2010-04-DataManagement/findDisplayableSubBusinessObjectsWithDisplayNames` |
| **2010-04** | DataManagement | `getAvailableTypesWithDisplayNames` | `Core-2010-04-DataManagement/getAvailableTypesWithDisplayNames` |
| **2010-04** | DataManagement | `getDatasetCreationRelatedInfo2` | `Core-2010-04-DataManagement/getDatasetCreationRelatedInfo2` |
| **2010-04** | DataManagement | `getLocalizedProperties` | `Core-2010-04-DataManagement/getLocalizedProperties` |
| **2010-04** | DataManagement | `isPropertyLocalizable` | `Core-2010-04-DataManagement/isPropertyLocalizable` |
| **2010-04** | DataManagement | `setLocalizedProperties` | `Core-2010-04-DataManagement/setLocalizedProperties` |
| **2010-04** | DataManagement | `setLocalizedPropertyValues` | `Core-2010-04-DataManagement/setLocalizedPropertyValues` |
| **2010-04** | LanguageInformation | `getAllTranslationStatuses` | `Core-2010-04-LanguageInformation/getAllTranslationStatuses` |
| **2010-04** | LanguageInformation | `getLanguagesList` | `Core-2010-04-LanguageInformation/getLanguagesList` |
| **2010-04** | Session | `getPreferences2` | `Core-2010-04-Session/getPreferences2` |
| **2010-04** | Session | `getShortcuts` | `Core-2010-04-Session/getShortcuts` |
| **2010-09** | DataManagement | `createOrUpdateStaticTableData` | `Core-2010-09-DataManagement/createOrUpdateStaticTableData` |
| **2010-09** | DataManagement | `getEventTypes` | `Core-2010-09-DataManagement/getEventTypes` |
| **2010-09** | DataManagement | `getStaticTableData` | `Core-2010-09-DataManagement/getStaticTableData` |
| **2010-09** | DataManagement | `postEvent` | `Core-2010-09-DataManagement/postEvent` |
| **2010-09** | DataManagement | `setProperties` | `Core-2010-09-DataManagement/setProperties` |
| **2010-09** | DataManagement | `verifyExtension` | `Core-2010-09-DataManagement/verifyExtension` |
| **2011-06** | DataManagement | `getTraceReport` | `Core-2011-06-DataManagement/getTraceReport` |
| **2011-06** | DataManagement | `saveAsObjects` | `Core-2011-06-DataManagement/saveAsObjects` |
| **2011-06** | DataManagement | `validateRevIds` | `Core-2011-06-DataManagement/validateRevIds` |
| **2011-06** | Envelope | `sendAndDeleteEnvelopes` | `Core-2011-06-Envelope/sendAndDeleteEnvelopes` |
| **2011-06** | LOV | `getLOVAttachments` | `Core-2011-06-LOV/getLOVAttachments` |
| **2011-06** | OperationDescriptor | `getSaveAsDesc` | `Core-2011-06-OperationDescriptor/getSaveAsDesc` |
| **2011-06** | PropDescriptor | `getAttachedPropDescs2` | `Core-2011-06-PropDescriptor/getAttachedPropDescs2` |
| **2011-06** | Reservation | `okToCheckout` | `Core-2011-06-Reservation/okToCheckout` |
| **2011-06** | Session | `getClientCacheData` | `Core-2011-06-Session/getClientCacheData` |
| **2011-06** | Session | `getTypeDescriptions` | `Core-2011-06-Session/getTypeDescriptions` |
| **2011-06** | Session | `login` | `Core-2011-06-Session/login` |
| **2011-06** | Session | `loginSSO` | `Core-2011-06-Session/loginSSO` |
| **2011-06** | Session | `updateObjectPropertyPolicy` | `Core-2011-06-Session/updateObjectPropertyPolicy` |
| **2012-02** | DataManagement | `bulkCreateObjects` | `Core-2012-02-DataManagement/bulkCreateObjects` |
| **2012-02** | DataManagement | `validateIdValue` | `Core-2012-02-DataManagement/validateIdValue` |
| **2012-02** | DataManagement | `whereUsed` | `Core-2012-02-DataManagement/whereUsed` |
| **2012-02** | OperationDescriptor | `getDeepCopyData` | `Core-2012-02-OperationDescriptor/getDeepCopyData` |
| **2012-02** | Session | `registerState` | `Core-2012-02-Session/registerState` |
| **2012-02** | Session | `setObjectPropertyPolicy` | `Core-2012-02-Session/setObjectPropertyPolicy` |
| **2012-02** | Session | `unregisterState` | `Core-2012-02-Session/unregisterState` |
| **2012-09** | DataManagement | `saveAsObjectAndRelate` | `Core-2012-09-DataManagement/saveAsObjectAndRelate` |
| **2012-09** | ProjectLevelSecurity | `copyProjects` | `Core-2012-09-ProjectLevelSecurity/copyProjects` |
| **2012-09** | ProjectLevelSecurity | `createProjects` | `Core-2012-09-ProjectLevelSecurity/createProjects` |
| **2012-09** | ProjectLevelSecurity | `getProjectTeams` | `Core-2012-09-ProjectLevelSecurity/getProjectTeams` |
| **2012-09** | ProjectLevelSecurity | `modifyProjects` | `Core-2012-09-ProjectLevelSecurity/modifyProjects` |
| **2012-10** | DataManagement | `getDatasetTypesWithFileExtension` | `Core-2012-10-DataManagement/getDatasetTypesWithFileExtension` |
| **2012-10** | DataManagement | `getTraceReport` | `Core-2012-10-DataManagement/getTraceReport` |
| **2012-10** | DataManagement | `refreshObjects2` | `Core-2012-10-DataManagement/refreshObjects2` |
| **2013-05** | DataManagement | `generateNextValues` | `Core-2013-05-DataManagement/generateNextValues` |
| **2013-05** | DataManagement | `getChildren` | `Core-2013-05-DataManagement/getChildren` |
| **2013-05** | DataManagement | `getPasteRelations` | `Core-2013-05-DataManagement/getPasteRelations` |
| **2013-05** | DataManagement | `getSubTypeNames` | `Core-2013-05-DataManagement/getSubTypeNames` |
| **2013-05** | DataManagement | `reviseObjects` | `Core-2013-05-DataManagement/reviseObjects` |
| **2013-05** | DataManagement | `validateValues` | `Core-2013-05-DataManagement/validateValues` |
| **2013-05** | LOV | `getInitialLOVValues` | `Core-2013-05-LOV/getInitialLOVValues` |
| **2013-05** | LOV | `getNextLOVValues` | `Core-2013-05-LOV/getNextLOVValues` |
| **2013-05** | LOV | `validateLOVValueSelections` | `Core-2013-05-LOV/validateLOVValueSelections` |
| **2014-06** | DataManagement | `getTraceReport2` | `Core-2014-06-DataManagement/getTraceReport2` |
| **2014-06** | DataManagement | `getTraceReportLegacy` | `Core-2014-06-DataManagement/getTraceReportLegacy` |
| **2014-06** | DigitalSignature | `applySignatures` | `Core-2014-06-DigitalSignature/applySignatures` |
| **2014-06** | DigitalSignature | `getSignatureMessages` | `Core-2014-06-DigitalSignature/getSignatureMessages` |
| **2014-06** | DigitalSignature | `voidSignatures` | `Core-2014-06-DigitalSignature/voidSignatures` |
| **2014-06** | Reservation | `bulkCancelCheckout` | `Core-2014-06-Reservation/bulkCancelCheckout` |
| **2014-06** | Reservation | `bulkCheckin` | `Core-2014-06-Reservation/bulkCheckin` |
| **2014-06** | Reservation | `bulkCheckout` | `Core-2014-06-Reservation/bulkCheckout` |
| **2014-10** | DataManagement | `addChildren` | `Core-2014-10-DataManagement/addChildren` |
| **2014-10** | DataManagement | `generateIdsUsingIDGenerationRules` | `Core-2014-10-DataManagement/generateIdsUsingIDGenerationRules` |
| **2014-10** | DataManagement | `getDeepCopyData` | `Core-2014-10-DataManagement/getDeepCopyData` |
| **2014-10** | DataManagement | `getPasteRelations2` | `Core-2014-10-DataManagement/getPasteRelations2` |
| **2014-10** | DataManagement | `pruneNamedReferences` | `Core-2014-10-DataManagement/pruneNamedReferences` |
| **2014-10** | DataManagement | `removeChildren` | `Core-2014-10-DataManagement/removeChildren` |
| **2014-10** | DataManagement | `saveAsObjectsAndRelate` | `Core-2014-10-DataManagement/saveAsObjectsAndRelate` |
| **2014-10** | ProjectLevelSecurity | `propagateData` | `Core-2014-10-ProjectLevelSecurity/propagateData` |
| **2015-07** | DataManagement | `createRelateAndSubmitObjects2` | `Core-2015-07-DataManagement/createRelateAndSubmitObjects2` |
| **2015-07** | DataManagement | `generateNextValuesForProperties` | `Core-2015-07-DataManagement/generateNextValuesForProperties` |
| **2015-07** | DataManagement | `getCreatbleSubBuisnessObjectNames` | `Core-2015-07-DataManagement/getCreatbleSubBuisnessObjectNames` |
| **2015-07** | DataManagement | `getDeepCopyData` | `Core-2015-07-DataManagement/getDeepCopyData` |
| **2015-07** | DataManagement | `getDomainOfObjectOrType` | `Core-2015-07-DataManagement/getDomainOfObjectOrType` |
| **2015-07** | DataManagement | `getLocalizedProperties2` | `Core-2015-07-DataManagement/getLocalizedProperties2` |
| **2015-10** | DataManagement | `reassignParticipants` | `Core-2015-10-DataManagement/reassignParticipants` |
| **2015-10** | FileManagement | `getDigestInfoForDatasets` | `Core-2015-10-FileManagement/getDigestInfoForDatasets` |
| **2015-10** | FileManagement | `getDigestInfoForFiles` | `Core-2015-10-FileManagement/getDigestInfoForFiles` |
| **2015-10** | Session | `getTypeDescriptions2` | `Core-2015-10-Session/getTypeDescriptions2` |
| **2015-10** | Session | `setUserSessionStateAndUpdateDefaults` | `Core-2015-10-Session/setUserSessionStateAndUpdateDefaults` |
| **2015-10** | Session | `sponsoredLogin` | `Core-2015-10-Session/sponsoredLogin` |
| **2015-10** | Session | `sponsoredLoginSSO` | `Core-2015-10-Session/sponsoredLoginSSO` |
| **2016-05** | DataManagement | `generateContextSpecificIDs` | `Core-2016-05-DataManagement/generateContextSpecificIDs` |
| **2016-05** | DataManagement | `resetContextID` | `Core-2016-05-DataManagement/resetContextID` |
| **2016-05** | DataManagement | `setPropertiesAndDetectOverwrite` | `Core-2016-05-DataManagement/setPropertiesAndDetectOverwrite` |
| **2016-09** | DataManagement | `createAttachAndSubmitObjects` | `Core-2016-09-DataManagement/createAttachAndSubmitObjects` |
| **2016-10** | ProjectLevelSecurity | `getDefaultProject` | `Core-2016-10-ProjectLevelSecurity/getDefaultProject` |
| **2017-05** | FileManagement | `commitDatasetFilesInBulk` | `Core-2017-05-FileManagement/commitDatasetFilesInBulk` |
| **2017-05** | FileManagement | `replaceFiles` | `Core-2017-05-FileManagement/replaceFiles` |
| **2017-05** | ProjectLevelSecurity | `assignOrRemoveObjectsFromProjects` | `Core-2017-05-ProjectLevelSecurity/assignOrRemoveObjectsFromProjects` |
| **2017-05** | ProjectLevelSecurity | `copyProjects2` | `Core-2017-05-ProjectLevelSecurity/copyProjects2` |
| **2017-05** | ProjectLevelSecurity | `createProjects2` | `Core-2017-05-ProjectLevelSecurity/createProjects2` |
| **2017-05** | ProjectLevelSecurity | `getProjectsForAssignOrRemove` | `Core-2017-05-ProjectLevelSecurity/getProjectsForAssignOrRemove` |
| **2017-05** | ProjectLevelSecurity | `modifyProjects2` | `Core-2017-05-ProjectLevelSecurity/modifyProjects2` |
| **2017-05** | ProjectLevelSecurity | `setPropagationEnabledProperties` | `Core-2017-05-ProjectLevelSecurity/setPropagationEnabledProperties` |
| **2017-11** | LogicalObject | `getLogicalObjects` | `Core-2017-11-LogicalObject/getLogicalObjects` |
| **2018-06** | DataManagement | `createObjectsInBulkAndRelate` | `Core-2018-06-DataManagement/createObjectsInBulkAndRelate` |
| **2018-06** | LogicalObject | `getLogicalObjects2` | `Core-2018-06-LogicalObject/getLogicalObjects2` |
| **2018-11** | LogicalObject | `getLogicalObjectsWithContext` | `Core-2018-11-LogicalObject/getLogicalObjectsWithContext` |
| **2018-11** | ProjectLevelSecurity | `changeOwningProgram` | `Core-2018-11-ProjectLevelSecurity/changeOwningProgram` |
| **2018-11** | ProjectLevelSecurity | `getUserProjects2` | `Core-2018-11-ProjectLevelSecurity/getUserProjects2` |
| **2019-06** | DataManagement | `unlinkAndDeleteObjects` | `Core-2019-06-DataManagement/unlinkAndDeleteObjects` |
| **2019-06** | Session | `licenseAdmin` | `Core-2019-06-Session/licenseAdmin` |
| **2020-01** | DataManagement | `createIdDisplayRules` | `Core-2020-01-DataManagement/createIdDisplayRules` |
| **2020-01** | DataManagement | `getIdContexts` | `Core-2020-01-DataManagement/getIdContexts` |
| **2020-01** | DataManagement | `getIdentifierTypes` | `Core-2020-01-DataManagement/getIdentifierTypes` |
| **2020-01** | ProjectLevelSecurity | `addOrRemoveProjectMembers` | `Core-2020-01-ProjectLevelSecurity/addOrRemoveProjectMembers` |
| **2020-01** | ProjectLevelSecurity | `getFirstLevelProjectTeamStructure` | `Core-2020-01-ProjectLevelSecurity/getFirstLevelProjectTeamStructure` |
| **2020-01** | ProjectLevelSecurity | `getModifiableProjects` | `Core-2020-01-ProjectLevelSecurity/getModifiableProjects` |
| **2020-01** | ProjectLevelSecurity | `getPrivilegeInProjects` | `Core-2020-01-ProjectLevelSecurity/getPrivilegeInProjects` |
| **2020-01** | ProjectLevelSecurity | `getProjectTeamChildNodes` | `Core-2020-01-ProjectLevelSecurity/getProjectTeamChildNodes` |
| **2020-01** | ProjectLevelSecurity | `setUserPrivilege` | `Core-2020-01-ProjectLevelSecurity/setUserPrivilege` |
| **2020-04** | DataManagement | `generateContextSpecificIDs2` | `Core-2020-04-DataManagement/generateContextSpecificIDs2` |
| **2021-06** | DataManagement | `addNamedReferenceToDatasets` | `Core-2021-06-DataManagement/addNamedReferenceToDatasets` |
| **2021-06** | DataManagement | `removeNamedReferenceFromDataset2` | `Core-2021-06-DataManagement/removeNamedReferenceFromDataset2` |
| **2021-12** | LOV | `validatePropertyValuesForLOVInBulk` | `Core-2021-12-LOV/validatePropertyValuesForLOVInBulk` |
| **2021-12** | Session | `addObjectPropertyPolicies` | `Core-2021-12-Session/addObjectPropertyPolicies` |
| **2022-12** | Session | `tcServerSleep` | `Core-2022-12-Session/tcServerSleep` |
| **2023-06** | DataManagement | `createObjects` | `Core-2023-06-DataManagement/createObjects` |
| **2023-12** | DataManagement | `changeOwner2` | `Core-2023-12-DataManagement/changeOwner2` |
| **2023-12** | DataManagement | `generateNextValuesForProperties2` | `Core-2023-12-DataManagement/generateNextValuesForProperties2` |
| **2023-12** | DataManagement | `getNRPatterns` | `Core-2023-12-DataManagement/getNRPatterns` |
| **2023-12** | DataManagement | `getRelatedObjects` | `Core-2023-12-DataManagement/getRelatedObjects` |
| **2023-12** | Session | `logout` | `Core-2023-12-Session/logout` |
| **2024-06** | DataManagement | `queryForFileExistence` | `Core-2024-06-DataManagement/queryForFileExistence` |
| **2025-06** | DataManagement | `getLocalizedProperties3` | `Core-2025-06-DataManagement/getLocalizedProperties3` |

</details>

### 版本—Service 对照

| API 版本 | 包含的 Service | 操作数 |
|----------|----------------|--------|
| 2006-03 | DataManagement、FileManagement、Reservation、Session | 28 |
| 2007-01 | DataManagement、FileManagement、ManagedRelations、Session | 18 |
| 2007-06 | DataManagement、LOV、PropDescriptor、Session | 11 |
| 2007-09 | DataManagement、ProjectLevelSecurity | 5 |
| 2007-12 | DataManagement、Session | 6 |
| 2008-03 | Session | 3 |
| 2008-05 | DataManagement | 1 |
| 2008-06 | DataManagement、DispatcherManagement、ManagedRelations、PropDescriptor、Reservation、Session、StructureManagement | 27 |
| 2009-04 | ProjectLevelSecurity、Session | 3 |
| 2009-10 | DataManagement、ProjectLevelSecurity | 4 |
| 2010-04 | DataManagement、LanguageInformation、Session | 12 |
| 2010-09 | DataManagement | 6 |
| 2011-06 | DataManagement、Envelope、LOV、OperationDescriptor、PropDescriptor、Reservation、Session | 13 |
| 2012-02 | DataManagement、OperationDescriptor、Session | 7 |
| 2012-09 | DataManagement、ProjectLevelSecurity | 5 |
| 2012-10 | DataManagement | 3 |
| 2013-05 | DataManagement、LOV | 9 |
| 2014-06 | DataManagement、DigitalSignature、Reservation | 8 |
| 2014-10 | DataManagement、ProjectLevelSecurity | 8 |
| 2015-07 | DataManagement | 6 |
| 2015-10 | DataManagement、FileManagement、Session | 7 |
| 2016-05 | DataManagement | 3 |
| 2016-09 | DataManagement | 1 |
| 2016-10 | ProjectLevelSecurity | 1 |
| 2017-05 | FileManagement、ProjectLevelSecurity | 8 |
| 2017-11 | LogicalObject | 1 |
| 2018-06 | DataManagement、LogicalObject | 2 |
| 2018-11 | LogicalObject、ProjectLevelSecurity | 3 |
| 2019-06 | DataManagement、Session | 2 |
| 2020-01 | DataManagement、ProjectLevelSecurity | 9 |
| 2020-04 | DataManagement | 1 |
| 2021-06 | DataManagement | 2 |
| 2021-12 | LOV、Session | 2 |
| 2022-12 | Session | 1 |
| 2023-06 | DataManagement | 1 |
| 2023-12 | DataManagement、Session | 5 |
| 2024-06 | DataManagement | 1 |
| 2025-06 | DataManagement | 1 |

### 同名多版本操作

以下操作在多个 API 版本中均有定义，调用时必须使用对应版本的 Url：

| Service | 操作 | API 版本 |
|---------|------|----------|
| DataManagement | `createDatasets` | `2006-03`、`2010-04` |
| DataManagement | `createObjects` | `2008-06`、`2023-06` |
| DataManagement | `expandGRMRelationsForPrimary` | `2007-06`、`2007-09` |
| DataManagement | `expandGRMRelationsForSecondary` | `2007-06`、`2007-09` |
| DataManagement | `getDeepCopyData` | `2014-10`、`2015-07` |
| DataManagement | `getTraceReport` | `2011-06`、`2012-10` |
| DataManagement | `setProperties` | `2007-01`、`2010-09` |
| DataManagement | `whereUsed` | `2007-01`、`2012-02` |
| Session | `getPreferences` | `2006-03`、`2007-01` |
| Session | `login` | `2006-03`、`2008-06`、`2011-06` |
| Session | `loginSSO` | `2006-03`、`2008-06`、`2011-06` |
| Session | `logout` | `2006-03`、`2023-12` |
| Session | `setObjectPropertyPolicy` | `2007-01`、`2008-06`、`2012-02` |

---

## 2. 按 Service 合并（跨版本）

同一 Service 下按 **API 版本（年-月）** 分组；同名操作若跨版本出现，在各版本小节中分别列出（input/output 可能不同）。

### 2.1 数据管理（DataManagement）

**涵盖 API 版本：** `2006-03`、`2007-01`、`2007-06`、`2007-09`、`2007-12`、`2008-05`、`2008-06`、`2009-10`、`2010-04`、`2010-09`、`2011-06`、`2012-02`、`2012-09`、`2012-10`、`2013-05`、`2014-06`、`2014-10`、`2015-07`、`2015-10`、`2016-05`、`2016-09`、`2018-06`、`2019-06`、`2020-01`、`2020-04`、`2021-06`、`2023-06`、`2023-12`、`2024-06`、`2025-06`  
**操作数：** 123

#### 版本 2006-03

##### 2.1.1.1 changeOwnership

**接口路径：** `Core-2006-03-DataManagement/changeOwnership`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 can be used to change the ownership on a given 业务对象 to the given user and group. Owning user attribute on the 业务对象 will be changed to the given user and owning group attribute is changed to the given group. The user needs CHANGE_OWNER privilege and WRITE privilege on the 业务对象 to be able to change its ownership. If user does not…

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.changeOwnership`

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
      "owner": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "group": {
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
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::ObjectOwner[] | Input object to the operation that holds the business object, new owning user and new owning group. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.1.2 createDatasets

**接口路径：** `Core-2006-03-DataManagement/createDatasets`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建一个或多个数据集（Dataset）及其文件信息。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.createDatasets`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "type": "",
      "name": "",
      "description": "",
      "toolUsed": "",
      "container": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::DatasetProperties[] | The information needed to create <b>Dataset</b> objects<br /> |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "dataset": {
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
| `output` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateDatasetsOutput[] | A list of created <b>Dataset</b> output |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

##### 2.1.1.3 createFolders

**接口路径：** `Core-2006-03-DataManagement/createFolders`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 在指定容器下创建一个或多个文件夹。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.createFolders`

**请求（input）：**

```json
{
  "folders": [
    {
      "clientId": "",
      "name": "",
      "desc": ""
    }
  ],
  "container": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "relationType": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `folders` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateFolderInput[] | Input struture to create <b>Folder</b> Objects |
| `container` | Teamcenter::BusinessObject | The object to which all the created <b>Folder</b> objects will be related to via the input relation type, may be null. |
| `relationType` | std::string | The name of relation type that all created <b>Folder</b> objects will be related to the container, may be an empty strin |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "folder": {
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
| `output` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateFoldersOutput[] | Each element in the list contains a client Id and the related <b>Folder</b> object created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

##### 2.1.1.4 createItems

**接口路径：** `Core-2006-03-DataManagement/createItems`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建一个或多个 Item 及其初始版本，可指定容器与关系类型。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.createItems`

**请求（input）：**

```json
{
  "properties": [
    {
      "clientId": "",
      "itemId": "",
      "name": "",
      "type": "",
      "revId": "",
      "uom": "",
      "description": "",
      "extendedAttributes": [
        {
          "objectType": "",
          "attributes": {}
        }
      ]
    }
  ],
  "container": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "relationType": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `properties` | Teamcenter::Soa::Core::_2006_03::DataManagement::ItemProperties[] | A list of properties to create new <b>Item</b> objects |
| `container` | Teamcenter::BusinessObject | The container object to which all the items will be related to via the input relation type, optional. |
| `relationType` | std::string | The relation type that will be used to relate the newly created <b>Item</b>s to the container, optional. |

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
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateItemsOutput[] | A list of the created <b>Item</b> and <b>ItemRevision</b> |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

##### 2.1.1.5 createRelations

**接口路径：** `Core-2006-03-DataManagement/createRelations`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 在主对象与次对象之间建立指定类型的关系。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.createRelations`

**请求（input）：**

```json
{
  "input": [
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
      "userData": {
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
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::Relationship[] | A list of structures containing details of relationships to be created between primary and secondary objects with the gi |

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
| `output` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateRelationsOutput[] | A list of created relations. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> object to hold the partial errors that the operation encoun |

---

##### 2.1.1.6 deleteObjects

**接口路径：** `Core-2006-03-DataManagement/deleteObjects`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 删除指定业务对象。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.deleteObjects`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of objects to be deleted |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.1.7 deleteRelations

**接口路径：** `Core-2006-03-DataManagement/deleteRelations`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 删除 the specified relation between the primary and secondary object for each input structure.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.deleteRelations`

**请求（input）：**

```json
{
  "input": [
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
      "userData": {
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
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::Relationship[] | A list of structures containing details of relationships to be deleted between primary and secondary objects with the gi |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.1.8 generateItemIdsAndInitialRevisionIds

**接口路径：** `Core-2006-03-DataManagement/generateItemIdsAndInitialRevisionIds`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates a list of Item IDs and initial ItemRevision IDs. The initial revision ID is defined as the first revision ID for the given type.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.generateItemIdsAndInitialRevisionIds`

**请求（input）：**

```json
{
  "input": [
    {
      "item": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemType": "",
      "count": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::GenerateItemIdsAndInitialRevisionIdsProperties[] | A list of the <b>Item</b>, <b>Item</b> type, and the number of IDs to generate. |

**响应（output）：**

```json
{
  "outputItemIdsAndInitialRevisionIds": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `outputItemIdsAndInitialRevisionIds` | Teamcenter::Soa::Core::_2006_03::DataManagement::IndexToIdMap | A list of the new <b>Item</b> and <b>ItemRevision</b> IDs and flags indicating if the system is configured to allow modi |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

##### 2.1.1.9 generateRevisionIds

**接口路径：** `Core-2006-03-DataManagement/generateRevisionIds`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 按规则预生成版本号。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.generateRevisionIds`

**请求（input）：**

```json
{
  "input": [
    {
      "item": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::GenerateRevisionIdsProperties[] | A list <b>Item</b> and <b>Item</b> type |

**响应（output）：**

```json
{
  "outputRevisionIds": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `outputRevisionIds` | Teamcenter::Soa::Core::_2006_03::DataManagement::IndexToRevIdMap | A list of the new generated id values |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

##### 2.1.1.10 getProperties

**接口路径：** `Core-2006-03-DataManagement/getProperties`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 批量获取指定业务对象的属性；attributes 为空时返回全部属性。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.getProperties`

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
  "attributes": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | List of attribute/property name strings for which values are needed |
| `attributes` | std::string[] | List of object references for which property values are requested |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.1.11 revise

**接口路径：** `Core-2006-03-DataManagement/revise`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** Revises a list of next Item 版本s based on input existing Item 版本 object references and any additional attributes. Uses deep copy rules to propagate existing relations from the Item 版本 or to create new references.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.revise`

**请求（input）：**

```json
{
  "input": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::ItemRevPropertyMap | A map of Item Revisions and ReviseProperties structures |

**响应（output）：**

```json
{
  "oldItemRevToNewItemRev": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `oldItemRevToNewItemRev` | Teamcenter::Soa::Core::_2006_03::DataManagement::ItemRevMap | A Map whose keys are the input old item revisions and values are the newly created revisions |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |

---

##### 2.1.1.12 setDisplayProperties

**接口路径：** `Core-2006-03-DataManagement/setDisplayProperties`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 is provided to update the Teamcenter objects for the given name/display value pairs. 此操作 works for all supported 属性 value types to set display values. When setting 此操作 it invokes the server PROP_UIF_set_value extensions. For updating an array 属性, display values need to be comma (,) separated which server parses them into indiv…

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.setDisplayProperties`

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
  "attributes": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of objects for which property values need to be set |
| `attributes` | Teamcenter::Soa::Core::_2006_03::DataManagement::AttributeNameValueMap | A map of attribute names and display values of a property  (string/string) |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2007-01

##### 2.1.2.1 createOrUpdateForms

**接口路径：** `Core-2007-01-DataManagement/createOrUpdateForms`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 创建 Form objects or update existing Form objects using the info provided. A new Form will be associated to the container object with specified relation type. The 属性 of the existing Form will be updated.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.createOrUpdateForms`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "formObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": "",
      "saveDB": "",
      "name": "",
      "description": "",
      "formType": "",
      "attributesMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2007_01::DataManagement::FormInfo[] | Input for creating or updating <b>Form</b> objects |

**响应（output）：**

```json
{
  "outputs": [
    {
      "clientId": "",
      "form": {
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
| `outputs` | Teamcenter::Soa::Core::_2007_01::DataManagement::CreateFormsOutput[] | List of created or updated <b>Form</b> objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

##### 2.1.2.2 generateUID

**接口路径：** `Core-2007-01-DataManagement/generateUID`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** This function 返回 a number of Teamcenter UIDs generated from the Teamcenter server. 此操作 can be used for assigning unique identifiers to objects that will not be stored in Teamcenter or for objects which have yet to be created in Teamcenter. The createObjects and createOrUpdateParts operations will support input of a preallocated UID for use during creation. Pl…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.generateUID`

**请求（input）：**

```json
{
  "nUID": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `nUID` | int | The number of UIDs to be generated. |

**响应（output）：**

```json
{
  "uids": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `uids` | std::string[] | List of the UIDs that were generated |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains any errors encountered during processing in the partial errors list. |

---

##### 2.1.2.3 getDatasetCreationRelatedInfo

**接口路径：** `Core-2007-01-DataManagement/getDatasetCreationRelatedInfo`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 pre-populates 数据集 creation information, default new 数据集 name and Tool names, for a specified 数据集 type. 此操作 is used to get all the information associates with the specified 数据集 prior to the creation operation. The returned default new 数据集 name may be determined by the parent container object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.getDatasetCreationRelatedInfo`

**请求（input）：**

```json
{
  "typeName": "",
  "parentObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `typeName` | std::string |  desired <b>Dataset</b> type name |
| `parentObject` | Teamcenter::BusinessObject | The containe object under which the new <b>Dataset</b> object will be created |

**响应（output）：**

```json
{
  "toolNames": [
    ""
  ],
  "newDatasetName": "",
  "nameCanBeModified": "",
  "initValuePropertyRules": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `toolNames` | std::string[] | List of <b>Tool</b> names |
| `newDatasetName` | std::string | The name of the new <b>Dataset</b>, can be an empty string |
| `nameCanBeModified` | bool | If true, the name of the <b>Dataset</b> can be modified |
| `initValuePropertyRules` | std::string[] | List of properties have the initialized values from property constant attachments |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

##### 2.1.2.4 getItemCreationRelatedInfo

**接口路径：** `Core-2007-01-DataManagement/getItemCreationRelatedInfo`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 will return naming rules, 属性 rule, form 属性 descriptor, unit of measurement and ItemRevision type name based on Item type selected by user during Item creation.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.getItemCreationRelatedInfo`

**请求（input）：**

```json
{
  "typeName": "",
  "parentObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `typeName` | std::string | <b>Item</b> type name |
| `parentObject` | Teamcenter::BusinessObject | <b>parentObject</b> is an unused parameter and may be null |

**响应（output）：**

```json
{
  "complexValuePropertyRules": [
    ""
  ],
  "initValuePropertyRules": [
    ""
  ],
  "patternMap": {},
  "uoms": [
    ""
  ],
  "formAttrs": [
    {
      "formType": "",
      "formPDs": [
        {
          "propName": "",
          "displayName": "",
          "attachedSpecifier": "",
          "maxLength": "",
          "interdependentProps": [
            ""
          ],
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
          "isEnabled": "",
          "isModifiable": ""
        }
      ]
    }
  ],
  "revTypeName": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `complexValuePropertyRules` | std::string[] | List of complex value property rules |
| `initValuePropertyRules` | std::string[] | List of initial values |
| `patternMap` | Teamcenter::Soa::Core::_2007_01::DataManagement::StringArrayMap | Pattern map (string/string) |
| `uoms` | std::string[] | List of unit of measures |
| `formAttrs` | Teamcenter::Soa::Core::_2007_01::DataManagement::FormAttributesInfo[] | List of <b>Form</b> attributes |
| `revTypeName` | std::string | <b>ItemRevision</b> type name |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful object ids, partial errors and failures |

---

##### 2.1.2.5 getItemFromId

**接口路径：** `Core-2007-01-DataManagement/getItemFromId`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 根据 Item 编号与版本号解析并返回 Item/ItemRevision 对象。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.getItemFromId`

**请求（input）：**

```json
{
  "infos": [
    {
      "itemId": "{{ITEM_ID}}",
      "revIds": [
        ""
      ]
    }
  ],
  "nRev": "",
  "pref": {
    "prefs": [
      {
        "relationTypeName": "",
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
| `infos` | Teamcenter::Soa::Core::_2007_01::DataManagement::GetItemFromIdInfo[] | list of GetItemFromIdInfo structures |
| `nRev` | int | value for the latest number of Item Revisions to return |
| `pref` | Teamcenter::Soa::Core::_2007_01::DataManagement::GetItemFromIdPref | GetItemFromIdPref structure for relation and types filtering |

**响应（output）：**

```json
{
  "output": [
    {
      "item": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemRevOutput": [
        {
          "itemRevision": {
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
| `output` | Teamcenter::Soa::Core::_2007_01::DataManagement::GetItemFromIdItemOutput[] | List of GetItemFromIdItemOutput |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |

---

##### 2.1.2.6 moveToNewFolder

**接口路径：** `Core-2007-01-DataManagement/moveToNewFolder`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** The moveToNew文件夹 operation moves a set of objects from one 文件夹 to another. 此操作 allows for moving multiple 设置 of objects to and from different 文件夹s. If no old 文件夹 is specified, 此操作 adds the objects to the new 文件夹.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.moveToNewFolder`

**请求（input）：**

```json
{
  "moveToNewFolderInfos": [
    {
      "oldFolder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newFolder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectsToMove": [
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
| `moveToNewFolderInfos` | Teamcenter::Soa::Core::_2007_01::DataManagement::MoveToNewFolderInfo[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>MoveToNewFolderInfo</font> structures each containing an  |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains the updated old folder, the new folder, and partial errors from this operation. |

---

##### 2.1.2.7 refreshObjects

**接口路径：** `Core-2007-01-DataManagement/refreshObjects`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 刷新会话中对象的最新状态。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.refreshObjects`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of object to be refreshed |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.2.8 saveAsNewItem

**接口路径：** `Core-2007-01-DataManagement/saveAsNewItem`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 创建 a new Item object and ItemRevision object from an existing ItemRevision object. The master form 属性 may be supplied for the new ItemRevision and item master form objects. If master form data is not supplied the master forms will be initialized from the master forms attached to the existing ItemRevision. Deep Copy rules may also be supplied to ov…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.saveAsNewItem`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "itemRevision": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemId": "",
      "revId": "",
      "name": "",
      "description": "",
      "folder": {
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
| `info` | Teamcenter::Soa::Core::_2007_01::DataManagement::SaveAsNewItemInfo[] | The necessary information to create the new <b>Item</b> and <b>ItemRevision</b> |

**响应（output）：**

```json
{
  "inputToNewItem": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputToNewItem` | Teamcenter::Soa::Core::_2007_01::DataManagement::InputToNewItemMap | Map whose keys are the input clientIds and output values (newly created <b>Item</b> and <b>ItemRevision</b> objects) pai |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

##### 2.1.2.9 setProperties

**接口路径：** `Core-2007-01-DataManagement/setProperties`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 批量设置业务对象的属性值。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.setProperties`

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
  "attributes": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | List of Business Objects for which the properties values to be set. |
| `attributes` | Teamcenter::Soa::Core::_2007_01::DataManagement::NameValueMap | A map of attribute names and desired value pairs (string/VecStruct). The <font face=&quot;courier&quot; height=&quot;10& |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.2.10 whereReferenced

**接口路径：** `Core-2007-01-DataManagement/whereReferenced`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 finds the objects and relations that reference a given object. It 返回 objects where the input object is specified in a Reference 属性 on that object. It also 返回 relations where the input object is listed as the secondary object for that relation. It does not return relations where the input object is the primary object for that relation. The Datam…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.whereReferenced`

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
  "numLevels": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::WorkspaceObject[] | List of <b>WorkspaceObject</b> references to find referencers for. If an element in the list is null a partial error is  |
| `numLevels` | int | Number of levels to traverse to find the referencers. For example, if A references B, and B references C, a 1 level sear |

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
      "info": [
        {
          "referencer": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relation": "",
          "level": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2007_01::DataManagement::WhereReferencedOutput[] | List of information containing reference, relation name and level for input object |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

##### 2.1.2.11 whereUsed

**接口路径：** `Core-2007-01-DataManagement/whereUsed`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 查询指定对象在结构或关系中的使用位置（Where Used）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.whereUsed`

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
  "numLevels": "",
  "whereUsedPrecise": "",
  "rule": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | List of object references on which to perform the <font face="courier" height="10">whereUsed</font> search. It is a requ |
| `numLevels` | int | Number of levels to traverse in the <font face="courier" height="10">whereUsed</font> search and return |
| `whereUsedPrecise` | bool | Boolean representing whether to only send back precise parents ( used by <b>ItemRevision</b> specifically and not <b>Ite |
| `rule` | Teamcenter::BusinessObject | <b>RevisionRule</b> used get unique configured <b>ItemRevision</b> from each level of <font face="courier" height="10">w |

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
      "info": [
        {
          "parentItemRev": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "level": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2007_01::DataManagement::WhereUsedOutput[] | List of WhereUsedOutput structures |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

#### 版本 2007-06

##### 2.1.3.1 expandGRMRelationsForPrimary

**接口路径：** `Core-2007-06-DataManagement/expandGRMRelationsForPrimary`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从主对象展开 GRM（全局关系模型）关系。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.expandGRMRelationsForPrimary`

**请求（input）：**

```json
{
  "primaryObjects": [
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
| `primaryObjects` | Teamcenter::BusinessObject[] | A Vector of Teamcenter primary objects |
| `pref` | Teamcenter::Soa::Core::_2007_06::DataManagement::ExpandGRMRelationsPref | Expand GRM Relations Preference |

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
| `output` | Teamcenter::Soa::Core::_2007_06::DataManagement::ExpandGRMRelationsOutput[] | List of SaveQueryCriteriaInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |

---

##### 2.1.3.2 expandGRMRelationsForSecondary

**接口路径：** `Core-2007-06-DataManagement/expandGRMRelationsForSecondary`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从次对象展开 GRM 关系。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.expandGRMRelationsForSecondary`

**请求（input）：**

```json
{
  "secondaryObjects": [
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
| `secondaryObjects` | Teamcenter::BusinessObject[] | A Vector of Teamcenter secondary objects |
| `pref` | Teamcenter::Soa::Core::_2007_06::DataManagement::ExpandGRMRelationsPref | Expand GRM Relations Preference |

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
| `output` | Teamcenter::Soa::Core::_2007_06::DataManagement::ExpandGRMRelationsOutput[] | List of SaveQueryCriteriaInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |

---

##### 2.1.3.3 getAvailableTypes

**接口路径：** `Core-2007-06-DataManagement/getAvailableTypes`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：获取Available Types。This will return type names implemented by the given classes. This is lightweight way to get all displayable types by name rather than model object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.getAvailableTypes`

**请求（input）：**

```json
{
  "classes": [
    {
      "baseClass": "",
      "exclusionTypes": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `classes` | Teamcenter::Soa::Core::_2007_06::DataManagement::BaseClassInput[] | A list of given base class name and exclusion list. |

**响应（output）：**

```json
{
  "inputClassToTypes": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputClassToTypes` | Teamcenter::Soa::Core::_2007_06::DataManagement::ClassToTypesMap | A map of given class names and all according AvailableTypeInfo objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData contains any parital error if any failure happens. |

---

##### 2.1.3.4 getDatasetTypeInfo

**接口路径：** `Core-2007-06-DataManagement/getDatasetTypeInfo`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 the named reference information for a set of 数据集 types. Named references are Teamcenter objects that relate to a specific data file. Any failure that occurs during 此操作 is returned in the ServiceData list of partial errors with the 数据集 type name string mapped to error message.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.getDatasetTypeInfo`

**请求（input）：**

```json
{
  "datasetTypeNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `datasetTypeNames` | std::string[] | List of dataset type names used to get the named reference information. An empty list will return information for all da |

**响应（output）：**

```json
{
  "infos": [
    {
      "tag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "refInfos": [
        {
          "referenceName": "",
          "isObject": "",
          "fileFormat": "",
          "fileExtension": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `infos` | Teamcenter::Soa::Core::_2007_06::DataManagement::DatasetTypeInfo[] | List of named reference information for each dataset type specified in <font face=&quot;courier&quot; height=&quot;10&qu |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font fac |

---

##### 2.1.3.5 purgeSequences

**接口路径：** `Core-2007-06-DataManagement/purgeSequences`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `purgeSequences`。Given a list of ItemRevision sequences, this opertion is used ot perform per the following criteria: If the input object is the latest sequence of an ItemRevision, all previous sequences will be purged. If the input object is not the latest sequence of the ItemRevision and the validateLatestFlag is false, the input object will be purged.If the input object is not the latest …

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.purgeSequences`

**请求（input）：**

```json
{
  "objects": [
    {
      "validateLatestFlag": "",
      "inputObject": {
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
| `objects` | Teamcenter::Soa::Core::_2007_06::DataManagement::PurgeSequencesInfo[] | A list of the objects to be purged and a flag noting whether to validate the object is the latest sequence. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.3.6 setOrRemoveImmunity

**接口路径：** `Core-2007-06-DataManagement/setOrRemoveImmunity`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 is used to add or remove immunity for each object in the input list according to the value of the associated setOrRemoveFlag. A value of true indicates to apply immunity to the object. A value of false indicates that immunity should be removed from the object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.setOrRemoveImmunity`

**请求（input）：**

```json
{
  "objects": [
    {
      "setOrRemoveFlag": "",
      "inputObject": {
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
| `objects` | Teamcenter::Soa::Core::_2007_06::DataManagement::SetOrRemoveImmunityInfo[] | A list of the <b>ItemRevision</b> sequence objects and a flag set true or false. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.3.7 validateItemIdsAndRevIds

**接口路径：** `Core-2007-06-DataManagement/validateItemIdsAndRevIds`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 校验 Item 编号与版本号是否合法/可用。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.validateItemIdsAndRevIds`

**请求（input）：**

```json
{
  "infos": [
    {
      "itemId": "{{ITEM_ID}}",
      "revId": "",
      "itemType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `infos` | Teamcenter::Soa::Core::_2007_06::DataManagement::ValidateIdsInfo[] | A List of item IDs, revision IDs, and item type for validation.<br /> |

**响应（output）：**

```json
{
  "output": [
    {
      "modItemId": "",
      "itemIdStatus": "Valid",
      "modRevId": "",
      "revIdStatus": "Valid"
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2007_06::DataManagement::ValidateIdsOutput[] | List of <font face=&quot;courier&quot; height=&quot;10&quot;>ValidateIdsOutput</font> structures |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData contains only error information returned by this operation. |

---

##### 2.1.3.8 whereReferencedByRelationName

**接口路径：** `Core-2007-06-DataManagement/whereReferencedByRelationName`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `whereReferencedByRelationName`。Finds the objects that reference a given object by a specific relation. The input object will be the secondary object for that relation. It does not return relations where the given input object is the primary object for the relation. The Datamanagement service operation expandGRMRelationsForPrimary can be used to return the relations where the input object is the primary ob…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.whereReferencedByRelationName`

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
      "filter": [
        {
          "relationTypeName": "",
          "otherSideObjectTypes": [
            ""
          ]
        }
      ]
    }
  ],
  "numLevels": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2007_06::DataManagement::WhereReferencedByRelationNameInfo[] | A list of desired business objects and filters to find the referencing objects for |
| `numLevels` | int | The number of levels to search.  For example, if A references B, and B references C, a 1-level search from C produces ju |

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
      "info": [
        {
          "referencer": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationTypeName": "",
          "level": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2007_06::DataManagement::WhereReferencedByRelationNameOutput[] | A list of filtered referencing objects for each input object |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

#### 版本 2007-09

##### 2.1.4.1 expandGRMRelationsForPrimary

**接口路径：** `Core-2007-09-DataManagement/expandGRMRelationsForPrimary`

**API 版本：** `2007-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从主对象展开 GRM（全局关系模型）关系。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_09.DataManagement.expandGRMRelationsForPrimary`

**请求（input）：**

```json
{
  "primaryObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "pref": {
    "expItemRev": "",
    "returnRelations": "",
    "info": [
      {
        "relationTypeName": "",
        "otherSideObjectTypes": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `primaryObjects` | Teamcenter::BusinessObject[] | The list of Teamcenter primary objects. |
| `pref` | Teamcenter::Soa::Core::_2007_09::DataManagement::ExpandGRMRelationsPref2 | The structure for setting specific preference input used by this operation. |

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
      "relationshipData": [
        {
          "relationshipObjects": [
            {
              "otherSideObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "relation": {
                "uid": "",
                "type": "",
                "className": ""
              }
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
| `output` | Teamcenter::Soa::Core::_2007_09::DataManagement::ExpandGRMRelationsOutput2[] | The list of input objects and the found related side objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font fac |

---

##### 2.1.4.2 expandGRMRelationsForSecondary

**接口路径：** `Core-2007-09-DataManagement/expandGRMRelationsForSecondary`

**API 版本：** `2007-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从次对象展开 GRM 关系。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_09.DataManagement.expandGRMRelationsForSecondary`

**请求（input）：**

```json
{
  "secondaryObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "pref": {
    "expItemRev": "",
    "returnRelations": "",
    "info": [
      {
        "relationTypeName": "",
        "otherSideObjectTypes": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `secondaryObjects` | Teamcenter::BusinessObject[] | The list of Teamcenter secondary objects. |
| `pref` | Teamcenter::Soa::Core::_2007_09::DataManagement::ExpandGRMRelationsPref2 | The structure for setting specific preference input used by this operation. |

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
      "relationshipData": [
        {
          "relationshipObjects": [
            {
              "otherSideObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "relation": {
                "uid": "",
                "type": "",
                "className": ""
              }
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
| `output` | Teamcenter::Soa::Core::_2007_09::DataManagement::ExpandGRMRelationsOutput2[] | The list of input objects and the found related side objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font fac |

---

##### 2.1.4.3 loadObjects

**接口路径：** `Core-2007-09-DataManagement/loadObjects`

**API 版本：** `2007-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从服务器加载业务对象到会话。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_09.DataManagement.loadObjects`

**请求（input）：**

```json
{
  "uids": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `uids` | std::string[] | An array of UIDs. These UID may come from an outside source or from other service operations such as executeSavedQuery. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.4.4 removeNamedReferenceFromDataset

**接口路径：** `Core-2007-09-DataManagement/removeNamedReferenceFromDataset`

**API 版本：** `2007-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 removes the specified named references from a 数据集. If the NamedReferenceInfo.targetObject input is not specified then all named references of the type specified are removed from the 数据集. If the NamedReferenceInfo.targetObject input is specified then only that named reference is removed from the 数据集. If the NamedReferenceInfo.deleteTarget input is t…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_09.DataManagement.removeNamedReferenceFromDataset`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "nrInfo": [
        {
          "clientId": "",
          "type": "",
          "targetObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "deleteTarget": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2007_09::DataManagement::RemoveNamedReferenceFromDatasetInfo[] | A list of datasets and the named references to be removed from the datasets. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2007-12

##### 2.1.5.1 createAlternateIdentifiers

**接口路径：** `Core-2007-12-DataManagement/createAlternateIdentifiers`

**API 版本：** `2007-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：创建Alternate Identifiers。Create new alternate identifiers. Given an IdContext, an IdentifierType and an Item ( and optionally an ItemRevision ), create an Identifier object to display an option part number when the IdContext is valid.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.DataManagement.createAlternateIdentifiers`

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
      "identifierType": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "mainObject": {
        "identifiableObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "alternateId": "",
        "additionalProps": {},
        "makeDefault": ""
      },
      "revObject": {
        "identifiableObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "alternateId": "",
        "additionalProps": {},
        "makeDefault": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2007_12::DataManagement::AlternateIdentifiersInput[] | A list of AlternateIdentifiersInput containing details of alternate identifiers to be created. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.5.2 getContextsAndIdentifierTypes

**接口路径：** `Core-2007-12-DataManagement/getContextsAndIdentifierTypes`

**API 版本：** `2007-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 返回 the context and identifier types for the supplied identifiable types.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.DataManagement.getContextsAndIdentifierTypes`

**请求（input）：**

```json
{
  "typeTags": [
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
| `typeTags` | Teamcenter::ImanType[] | A list of <b>ImanType</b> objects. |

**响应（output）：**

```json
{
  "contextAndIdentifierTypesMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `contextAndIdentifierTypesMap` | Teamcenter::Soa::Core::_2007_12::DataManagement::ContextAndIdentifierTypesMap | A map of context and identifier types for each requested <b>ImanType</b> (<b>ImanType</b>/<font face="courier" height="1 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data associated with the call |

---

##### 2.1.5.3 listAlternateIdDisplayRules

**接口路径：** `Core-2007-12-DataManagement/listAlternateIdDisplayRules`

**API 版本：** `2007-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `listAlternateIdDisplayRules`。Return the current display rule. If the current user flag is set then also return the display rules for the current user. If a list of users is supplied, then return the display rules for the list of users; otherwise return the display rules for all users.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.DataManagement.listAlternateIdDisplayRules`

**请求（input）：**

```json
{
  "input": {
    "users": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "currentUser": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2007_12::DataManagement::ListAlternateIdDisplayRulesInfo | A <font face="courier" height="10">ListAlternateIdDisplayRulesInfo</font> data structure. |

**响应（output）：**

```json
{
  "userDisplayRuleMaps": {},
  "currentRuleInDB": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `userDisplayRuleMaps` | Teamcenter::Soa::Core::_2007_12::DataManagement::UserDisplayRuleMap | A list of maps of <font face="courier" height="10">Teamcenter::UserImpl</font> to <font face="courier" height="10">IdDis |
| `currentRuleInDB` | Teamcenter::IdDispRule | The current rule in the database ( valid for current user only ). |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">ServiceData</font> associated with the call. |

---

##### 2.1.5.4 validateAlternateIds

**接口路径：** `Core-2007-12-DataManagement/validateAlternateIds`

**API 版本：** `2007-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：校验Alternate Ids。Determines if the supplied alternateIds are valid. The USER exit USER_validate_alt_id is used for validation. A "modified" alternate id is returned. If the alternate id supplied is valid then the modified one returned is the same as the one supplied. If the alternate id supplied is not valid, then the one returned is a valid one.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.DataManagement.validateAlternateIds`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "alternateId": "",
      "alternateRevId": "",
      "patternName": "",
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "identifierType": {
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
| `inputs` | Teamcenter::Soa::Core::_2007_12::DataManagement::ValidateAlternateIdInput[] | A list of <font face="courier" height="10">ValidateAlternateIdInput</font> data structures. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "modifiedAltId": "",
      "modifiedAltRevId": "",
      "validityId": "Valid",
      "validityRevId": "Valid"
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2007_12::DataManagement::ValidateAlternateIdOutput[] | List of <font face="courier" height="10">ValidateAlternateIdOutput</font>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">ServiceData</font> will contain the objects that are returned by the service call.  |

---

#### 版本 2008-05

##### 2.1.6.1 unloadObjects

**接口路径：** `Core-2008-05-DataManagement/unloadObjects`

**API 版本：** `2008-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从会话中卸载业务对象。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_05.DataManagement.unloadObjects`

**请求（input）：**

```json
{
  "objsToUnload": [
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
| `objsToUnload` | Teamcenter::BusinessObject[] | A list of model objects to unload. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2008-06

##### 2.1.7.1 addParticipants

**接口路径：** `Core-2008-06-DataManagement/addParticipants`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 创建 the Participant objects and adds them to the input Item 版本. If a Participant object with specified attributes already exists, it is added to the Item 版本.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.addParticipants`

**请求（input）：**

```json
{
  "addParticipantInfo": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "participantInfo": [
        {
          "assignee": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "participantType": "",
          "clientId": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `addParticipantInfo` | Teamcenter::Soa::Core::_2008_06::DataManagement::AddParticipantInfo[] | Contains a list of <font face="courier" height="10">ParticipantInfo</font> structures with information about participant |

**响应（output）：**

```json
{
  "participantOutput": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "participant": [
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
| `participantOutput` | Teamcenter::Soa::Core::_2008_06::DataManagement::Participants[] | List of structures containing the participants and the object to which participants are added. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The service data. |

---

##### 2.1.7.2 createConnections

**接口路径：** `Core-2008-06-DataManagement/createConnections`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建 a list of Connection objects and any associated data (ConnectionRevision, ConnectionMaster Form and ConnectionRevision Master Form) based on the input 属性 structure. It also 创建 the specified relation type between newly created Connection object and input container object. If container and relation type are not supplied, none of the Connection objects will…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createConnections`

**请求（input）：**

```json
{
  "properties": [
    {
      "clientId": "",
      "connId": "",
      "name": "",
      "type": "",
      "revId": "",
      "description": "",
      "extendedAttributes": [
        {
          "objectType": "",
          "attributes": {}
        }
      ]
    }
  ],
  "container": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "relationType": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `properties` | Teamcenter::Soa::Core::_2008_06::DataManagement::ConnectionProperties[] | A <b>Connection</b> object is created for each ConnectionProperties in the list. The data on the ConnectionProperties is |
| `container` | Teamcenter::BusinessObject | Object to which all the <b>Connection</b> objects created will be related to via the input relationType (Folder instance |
| `relationType` | std::string | The name of the relation used to attach the created <b>Connection</b> objects to input container. This argument is used  |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "output": [
    {
      "clientId": "",
      "connection": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "connectionRev": {
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
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::ConnectionOutput[] | A list of created <b>Connection</b> objects and associate <b>ConnectionRevision</b> in the form of ConnectionsOutput str |

---

##### 2.1.7.3 createDatasets2

**接口路径：** `Core-2008-06-DataManagement/createDatasets2`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 创建 a list of 数据集 objects and 创建 the specified relation type between created 数据集 and input container object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createDatasets2`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "type": "",
      "name": "",
      "description": "",
      "toolUsed": "",
      "datasetId": "",
      "datasetRev": "",
      "container": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_06::DataManagement::DatasetProperties2[] | The information needed to create  <b>Dataset</b> |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "dataset": {
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
| `output` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateDatasetsOutput[] | A list of created <b>Dataset</b> output |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

##### 2.1.7.4 createObjects

**接口路径：** `Core-2008-06-DataManagement/createObjects`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 按类型批量创建业务对象（通用创建接口）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "data": {
        "boName": "",
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateIn[] | This is a vector of CreateIn objects each one of which represents the CreateInput information used to create an object.  |

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOut[] | Vector of output objects representing objects that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data including partial errors that are mapped to the client id from the input. Created objects are also added to |

---

##### 2.1.7.5 createOrUpdateGDELinks

**接口路径：** `Core-2008-06-DataManagement/createOrUpdateGDELinks`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：创建Or Update G D E Links。Create and/or update GeneralDesignElementLink(GDELink) objects based on the input 属性 structure. If the given GDELink object exists in Teamcenter then 该操作 will be treated as an update based on the input 属性 structure

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createOrUpdateGDELinks`

**请求（input）：**

```json
{
  "gdeLinkInfos": [
    {
      "clientID": "",
      "name": "",
      "description": "",
      "type": "",
      "gdeLink": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attributes": [
        {
          "name": "",
          "values": [
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
| `gdeLinkInfos` | Teamcenter::Soa::Core::_2008_06::DataManagement::GDELinkInfo[] | An input of vector of structures containing values necessary to create or update the Teamcenter Model Data representing  |

**响应（output）：**

```json
{
  "successfullyProcessedGDELinks": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `successfullyProcessedGDELinks` | Teamcenter::Soa::Core::_2008_06::DataManagement::SuccessfullyProcessedGDELinksMap | A map containing the clientIds and the successfully created/updated <b>GeneralDesignElementLink</b> objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data to report partial errors. |

---

##### 2.1.7.6 createOrUpdateItemElements

**接口路径：** `Core-2008-06-DataManagement/createOrUpdateItemElements`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：创建Or Update Item Elements。Allows the user to create a new GeneralDesignElement (GDE) or its subtype and set its 属性. In the case of existing GDE, user can update the 属性.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createOrUpdateItemElements`

**请求（input）：**

```json
{
  "properties": [
    {
      "clientId": "",
      "name": "",
      "type": "",
      "description": "",
      "itemElemAttributes": {},
      "itemElement": {
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
| `properties` | Teamcenter::Soa::Core::_2008_06::DataManagement::ItemElementProperties[] | This is a vector of <i>ItemElementProperties</i>. While creating a new element it shall contain a unique clientId, name  |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "output": [
    {
      "clientId": "",
      "itemElem": {
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
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member containing created/updated objects and partial errors if any |
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::ItemElementsOutput[] | A list of createItemElementsOutput |

---

##### 2.1.7.7 createOrUpdateRelations

**接口路径：** `Core-2008-06-DataManagement/createOrUpdateRelations`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建 the specified relation between the input objects (primary and secondary objects) for each input structure. If the sync flag is specified, then if any Generic Relationship Management (GRM) relations exist between the primary and secondary objects and they are not specified in the input they will be deleted. If sync flag is provided, the relations member of CreateOrUpd…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createOrUpdateRelations`

**请求（input）：**

```json
{
  "infos": [
    {
      "clientId": "",
      "relationType": "",
      "primaryObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "secondaryData": [
        {
          "clientId": "",
          "secondary": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "userData": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "properties": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ]
        }
      ],
      "relations": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "sync": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `infos` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOrUpdateRelationsInfo[] | A list of <font face="courier" height="10">CreateOrUpdateRelationsInfo</font> structures containing details of relations |
| `sync` | bool | If true then GRM relations in db and the number of secondary objects specified in the <font face="courier" height="10">i |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "relations": [
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
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOrUpdateRelationsOutput[] | A list of <font face="courier" height="10">CreateOrUpdateRelationsOutput</font> |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> object to hold the partial errors that the operation encoun |

---

##### 2.1.7.8 findDisplayableSubBusinessObjects

**接口路径：** `Core-2008-06-DataManagement/findDisplayableSubBusinessObjects`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** Operation to retrieve sub 业务对象 Names for a 业务对象 that are displayable to the login user in the object creation dialog. e.g File-new, select Item, what types to be displayed for Item

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.findDisplayableSubBusinessObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "boTypeName": "",
      "exclusionBOTypeNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_06::DataManagement::BOWithExclusionIn[] | - a list of input objects representing the BO type names for which the displayable types are to be retrieved |

**响应（output）：**

```json
{
  "output": [
    {
      "boTypeName": "",
      "displayableBOTypeNames": [
        {
          "BOName": "",
          "BOParents": [
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
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::DisplayableBOsOut[] | Vector of output objects representing displayable types during create of a BO |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data including partial errors that are mapped to the input BO type name |

---

##### 2.1.7.9 getItemAndRelatedObjects

**接口路径：** `Core-2008-06-DataManagement/getItemAndRelatedObjects`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 Items, ItemRevisions, 数据集 and NamedReference information based on the input. Input is a list of GetItemAndRelatedObjectsInfo structures each of which contains item uid or id, revison information and optionally a list of filters to determine the 数据集s to be returned. For the 数据集s the client can request information about the NamedReferences. N…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.getItemAndRelatedObjects`

**请求（input）：**

```json
{
  "infos": [
    {
      "clientId": "",
      "itemInfo": {
        "clientId": "",
        "useIdFirst": "",
        "uid": "",
        "ids": [
          {
            "name": "",
            "value": ""
          }
        ]
      },
      "revInfo": {
        "clientId": "",
        "processing": "None",
        "useIdFirst": "",
        "uid": "",
        "id": "",
        "nRevs": "",
        "revisionRule": ""
      },
      "datasetInfo": {
        "clientId": "",
        "uid": "",
        "filter": {
          "useNameFirst": "",
          "processing": "None",
          "nrFilters": [
            {
              "namedReference": "",
              "uidReferenced": ""
            }
          ],
          "name": "",
          "relationFilters": [
            {
              "relationTypeName": "",
              "datasetTypeName": ""
            }
          ]
        },
        "namedRefs": [
          {
            "namedReference": "",
            "ticket": ""
          }
        ]
      },
      "bvrTypeNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `infos` | Teamcenter::Soa::Core::_2008_06::DataManagement::GetItemAndRelatedObjectsInfo[] | list of <font face="courier" height="10">GetItemAndRelatedObjectsInfo</font> structures. |

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
      "itemRevOutput": [
        {
          "clientId": "",
          "itemRevision": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "bvrs": [
            {
              "bvr": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "viewTypeName": ""
            }
          ],
          "datasetOutput": [
            {
              "clientId": "",
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "relationTypeName": "",
              "namedReferenceOutput": [
                {
                  "namedReference": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "namedReferenceName": "",
                  "ticket": ""
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
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::GetItemAndRelatedObjectsItemOutput[] | List of <font face=&quot;courier&quot; height=&quot;10&quot;>GetItemAndRelatedObjectsItemOutput</font> |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |

---

##### 2.1.7.10 getNextIds

**接口路径：** `Core-2008-06-DataManagement/getNextIds`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 该操作 generates the next id as per the input pattern in the attached Naming Rule to the 属性 of an object type. The type name, 属性 name and pattern are passed in the input structure. The input for 此操作 contains a list of this structure. The return structure contains the list of nextId along with the service data member. In the case where no pattern…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.getNextIds`

**请求（input）：**

```json
{
  "vInfoForNextId": [
    {
      "typeName": "",
      "propName": "",
      "pattern": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `vInfoForNextId` | Teamcenter::Soa::Core::_2008_06::DataManagement::InfoForNextId[] | Contains Type Name, Property Name and pattern. |

**响应（output）：**

```json
{
  "nextIds": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `nextIds` | std::string[] | List containing next Id strings generated as per the pattern. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> structure. It contains partial errors and failures along wi |

---

##### 2.1.7.11 getNRPatternsWithCounters

**接口路径：** `Core-2008-06-DataManagement/getNRPatternsWithCounters`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 gives the list of Patterns which has counters along with preferred patterns and conditions for the Naming Rule attached to the 属性 of an object Type. The Type name and the 属性 name are passed in the input structure. The input for 此操作 contains a list of this structure. The return structure contains the vector of patterns with counters, pref…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.getNRPatternsWithCounters`

**请求（input）：**

```json
{
  "vAttachInfo": [
    {
      "typeName": "",
      "propName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `vAttachInfo` | Teamcenter::Soa::Core::_2008_06::DataManagement::NRAttachInfo[] | Struct that contains Type Name and Property Name |

**响应（output）：**

```json
{
  "patterns": [
    {
      "patternStrings": [
        ""
      ]
    }
  ],
  "preferredPattern": [
    ""
  ],
  "condition": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `patterns` | Teamcenter::Soa::Core::_2008_06::DataManagement::PatternsWithCounters[] | List of structs which contain Patterns which has counters. |
| `preferredPattern` | std::string[] | List of preferred patterns. |
| `condition` | std::string[] | List of conditions. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData structure. It contains partial errors and failures along with the clientIds. |

---

##### 2.1.7.12 getRevNRAttachDetails

**接口路径：** `Core-2008-06-DataManagement/getRevNRAttachDetails`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 获取 all the possible initial, secondary and supplemental revision next Ids for an ItemRevision along with the available formats and the set of excluded letters for revision. The Revision Type Name and the current revision are passed in the input typeAndItemRevInfos structure. The input for 此操作 contains a list of this structure. The return structure…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.getRevNRAttachDetails`

**请求（input）：**

```json
{
  "typeAndItemRevInfos": [
    {
      "typeName": "",
      "itemRev": {
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
| `typeAndItemRevInfos` | Teamcenter::Soa::Core::_2008_06::DataManagement::TypeAndItemRevInfo[] | List of <font face="courier" height="10">TypeAndItemRevInfo</font> structs which contains <b>Item</b> and <b>ItemRevisio |

**响应（output）：**

```json
{
  "initRevDetails": [
    {
      "revOption": "",
      "revFormat": ""
    }
  ],
  "secRevDetails": [
    {
      "revOption": "",
      "revFormat": ""
    }
  ],
  "supplRevDetails": [
    {
      "revOption": "",
      "revFormat": ""
    }
  ],
  "excludedLetters": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `initRevDetails` | Teamcenter::Soa::Core::_2008_06::DataManagement::RevOptionDetails[] | List containing information about Initial Revision Type. |
| `secRevDetails` | Teamcenter::Soa::Core::_2008_06::DataManagement::RevOptionDetails[] | List containing information about Secondary Revision Type. |
| `supplRevDetails` | Teamcenter::Soa::Core::_2008_06::DataManagement::RevOptionDetails[] | List containing information about Supplemental Revision Type. |
| `excludedLetters` | std::string[] | List of exluded letters. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData structure. It contains partial errors and failures along with the clientIds. |

---

##### 2.1.7.13 removeParticipants

**接口路径：** `Core-2008-06-DataManagement/removeParticipants`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 allows the user to remove Participant objects associated with specified Item 版本. If a participant being removed is no longer associated with any other objects, it 获取 deleted.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.removeParticipants`

**请求（input）：**

```json
{
  "participants": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "participant": [
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
| `participants` | Teamcenter::Soa::Core::_2008_06::DataManagement::Participants[] | List of participants structures each containing a list of <b>Participant</b> objects to be removed and an Item Revision  |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.7.14 revise2

**接口路径：** `Core-2008-06-DataManagement/revise2`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 provides the ability to revise the ItemRevision objects given in the input list and carries forward relations to existing objects. When applying deep copy rules, if user overridden deep copy information is provided in the input, relations are propagated to the new ItemRevision based on that input. If no deep copy information is provided in the input, the deep …

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.revise2`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "baseItemRevision": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newRevId": "",
      "name": "",
      "description": "",
      "deepCopyInfo": [
        {
          "otherSideObjectTag": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationTypeName": "",
          "newName": "",
          "action": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": ""
        }
      ],
      "newItemRevisionMasterProperties": {
        "form": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "propertyValueInfo": [
          {
            "propertyName": "",
            "propertyValues": [
              ""
            ]
          }
        ]
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2008_06::DataManagement::ReviseInfo[] | The necessary information to create the new revision |

**响应（output）：**

```json
{
  "reviseOutputMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `reviseOutputMap` | Teamcenter::Soa::Core::_2008_06::DataManagement::ReviseOutputMap | Map whose keys are the input clientIds and output values pairs (<font face="courier" height="10">string</font>, <font fa |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This contains the status of the operation. |

---

##### 2.1.7.15 saveAsNewItem2

**接口路径：** `Core-2008-06-DataManagement/saveAsNewItem2`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 provides the capability to create one or more new Item objects based on a list of existing ItemRevision objects. It optionally carries forward ItemRevision relations based on the deepCopyRequired flag. When applying deep copy rules, if user overridden deep copy information is provided in the input, then old ItemRevision relations are propagated to the new Item…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.saveAsNewItem2`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "baseItemRevision": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newItemId": "",
      "newRevId": "",
      "name": "",
      "description": "",
      "deepCopyInfo": [
        {
          "otherSideObjectTag": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationTypeName": "",
          "newName": "",
          "action": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": ""
        }
      ],
      "newItemMasterProperties": {
        "form": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "propertyValueInfo": [
          {
            "propertyName": "",
            "propertyValues": [
              ""
            ]
          }
        ]
      },
      "newItemRevisionMasterProperties": {
        "form": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "propertyValueInfo": [
          {
            "propertyName": "",
            "propertyValues": [
              ""
            ]
          }
        ]
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2008_06::DataManagement::SaveAsNewItemInfo[] | The necessary information to create the new <b>Iitem</b> and <b>ItemRevision</b> |

**响应（output）：**

```json
{
  "saveAsOutputMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `saveAsOutputMap` | Teamcenter::Soa::Core::_2008_06::DataManagement::SaveAsNewItemOutputMap | Map whose keys are the input clientIds and output values pairs(<font face="courier" height="10">string</font>, <font fac |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

#### 版本 2009-10

##### 2.1.8.1 getItemFromAttribute

**接口路径：** `Core-2009-10-DataManagement/getItemFromAttribute`

**API 版本：** `2009-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：获取Item From Attribute。This service retrieves Item and its related ItemRevision objects based on the supplied attribute key-value pairs supplied in the infos list. All the key-value pairs except for the rev_id key are used to create a query for Item objects. Once a set of Item objects have been retrieved, their ItemRevision objects are retrieved based on the following rules: If nRev is a negative …

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_10.DataManagement.getItemFromAttribute`

**请求（input）：**

```json
{
  "infos": [
    {
      "itemAttributes": {},
      "revIds": [
        ""
      ]
    }
  ],
  "nRev": "",
  "pref": {
    "prefs": [
      {
        "relationTypeName": "",
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
| `infos` | Teamcenter::Soa::Core::_2009_10::DataManagement::GetItemFromAttributeInfo[] | The list of attribute value keys for the retrieval. The attributes must be the unique key attributes of the class. Curre |
| `nRev` | int | Maximum number of <b>ItemRevision</b> objects to retrieve.<br /><ul><ul><li type="disc">nRev < 0        retrieve all ava |
| `pref` | Teamcenter::Soa::Core::_2007_01::DataManagement::GetItemFromIdPref | <font face="courier" height="10">GetItemFromIdPref</font> object used to filter the returned <b>ItemRevision</b> objects |

**响应（output）：**

```json
{
  "output": [
    {
      "item": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemRevOutput": [
        {
          "itemRevision": {
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
| `output` | Teamcenter::Soa::Core::_2009_10::DataManagement::GetItemFromAttributeItemOutput[] | A list of found <b>Item</b> and <b>ItemRevision</b> objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServerData</font> member with any returned error codes and messages |

---

##### 2.1.8.2 getTableProperties

**接口路径：** `Core-2009-10-DataManagement/getTableProperties`

**API 版本：** `2009-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 allows 客户端应用s to obtain the 属性 pertaining to one or more Table 业务对象. Client developers will need to pass in references to each Table that they need to query information on. Note that the input vector needs to contain only references to the Teamcenter Table 业务对象, 此操作 cannot be used to fetch 属性 of an…

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_10.DataManagement.getTableProperties`

**请求（input）：**

```json
{
  "table": [
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
| `table` | Teamcenter::Table[] | This is a vector of the Table Business Objects for which the properties need to be obtained. |

**响应（output）：**

```json
{
  "tableInfo": [
    {
      "tableObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tableDefInfo": {
        "rows": "",
        "columns": "",
        "rowLabels": [
          ""
        ],
        "colLabels": [
          ""
        ],
        "tableDef": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "tableCells": [
        {
          "row": "",
          "column": "",
          "desc": "",
          "value": {
            "type": "",
            "strValues": [
              ""
            ]
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
| `tableInfo` | Teamcenter::Soa::Core::_2009_10::DataManagement::TableInfo[] | This vector contains a list of <i>TableInfo</i>, and each <i>TableInfo</i> contains information pertaining to the specif |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData structure is used to return the updated Table objects in the update section and also any errors encounte |

---

##### 2.1.8.3 setTableProperties

**接口路径：** `Core-2009-10-DataManagement/setTableProperties`

**API 版本：** `2009-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 allows 客户端应用s to set the 属性 pertaining to one or more Table 业务对象. Client developers will need to set information pertaining to the number of rows, columns, descriptions of each row and column, and cell information for each cell of the Table. The cell information must contain the type of cell, value to be placed in the cell, and…

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_10.DataManagement.setTableProperties`

**请求（input）：**

```json
{
  "tableData": [
    {
      "tableObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tableDefInfo": {
        "rows": "",
        "columns": "",
        "rowLabels": [
          ""
        ],
        "colLabels": [
          ""
        ],
        "tableDef": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "tableCells": [
        {
          "row": "",
          "column": "",
          "desc": "",
          "value": {
            "type": "",
            "strValues": [
              ""
            ]
          }
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `tableData` | Teamcenter::Soa::Core::_2009_10::DataManagement::TableInfo[] | This vector contains a list of <i>TableInfo</i>, and each <i>TableInfo</i> contains information pertaining to the specif |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2010-04

##### 2.1.9.1 createDatasets

**接口路径：** `Core-2010-04-DataManagement/createDatasets`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建一个或多个数据集（Dataset）及其文件信息。

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.createDatasets`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "name": "",
      "container": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationType": "",
      "description": "",
      "type": "",
      "datasetId": "",
      "datasetRev": "",
      "toolUsed": "",
      "attrs": [
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
          "namedReferenceName": "",
          "isText": "",
          "allowReplace": ""
        }
      ],
      "nrObjectInfos": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "namedReferenceName": "",
          "referenceType": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2010_04::DataManagement::DatasetInfo[] | Input list of DatasetInfo structures |

**响应（output）：**

```json
{
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
                "namedReferenceName": "",
                "isText": "",
                "allowReplace": ""
              },
              "ticket": ""
            }
          ]
        }
      ]
    }
  ],
  "servData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `datasetOutput` | Teamcenter::Soa::Core::_2010_04::DataManagement::DatasetOutput[] | List of output structure for creatDatasets operation. Each element in the list contains a client Id and the related <b>D |
| `servData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

##### 2.1.9.2 findDisplayableSubBusinessObjectsWithDisplayNames

**接口路径：** `Core-2010-04-DataManagement/findDisplayableSubBusinessObjectsWithDisplayNames`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 sub 业务对象 names that are displayable to the login user in the object creation dialog and their display names for each Primary 业务对象 given as the input. Returned 业务对象 lists have exclusions of 业务对象 and their secondary 业务对象 as specified in the input. This 返回 the hierarchy of displayable objects f…

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.findDisplayableSubBusinessObjectsWithDisplayNames`

**请求（input）：**

```json
{
  "input": [
    {
      "boTypeName": "",
      "exclusionBOTypeNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_06::DataManagement::BOWithExclusionIn[] | A list of Business Object names and their exclusion list for which the displayable Business Objects are to be retrieved. |

**响应（output）：**

```json
{
  "output": [
    {
      "boTypeName": "",
      "displayableBOTypeNames": [
        {
          "boName": "",
          "boDisplayName": "",
          "boParents": [
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
| `output` | Teamcenter::Soa::Core::_2010_04::DataManagement::DisplayableBusinessObjectsOut[] | List of displayable Business Objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service data. |

---

##### 2.1.9.3 getAvailableTypesWithDisplayNames

**接口路径：** `Core-2010-04-DataManagement/getAvailableTypesWithDisplayNames`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 业务对象 names and their display names for each primary 业务对象 given as the input. Returned 业务对象 lists have exclusions of 业务对象 and their secondary 业务对象 as specified in the input. If any of the returned 业务对象 is also a primary 业务对象 then 此操作 may not return its secondary B…

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.getAvailableTypesWithDisplayNames`

**请求（input）：**

```json
{
  "classes": [
    {
      "baseClass": "",
      "exclusionTypes": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `classes` | Teamcenter::Soa::Core::_2007_06::DataManagement::BaseClassInput[] | A list of primary Business Object names and their exclusion list. |

**响应（output）：**

```json
{
  "inputClassToTypes": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputClassToTypes` | Teamcenter::Soa::Core::_2010_04::DataManagement::BusinessObjectClassToTypesMap | A map of <b>Business Object </b>names and associated descendant Business Objects (<b>string, vector<AvailableBusinessObj |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData. |

---

##### 2.1.9.4 getDatasetCreationRelatedInfo2

**接口路径：** `Core-2010-04-DataManagement/getDatasetCreationRelatedInfo2`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 pre-populates 数据集 creation information, default new 数据集 name and Tool names, for a specified 数据集 type. 此操作 is used to get all the information associates with the specified 数据集 prior to the creation operation. The returned default new 数据集 name may be determined by the parent container object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.getDatasetCreationRelatedInfo2`

**请求（input）：**

```json
{
  "typeName": "",
  "parentObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `typeName` | std::string | The desired <b>Dataset</b> type name |
| `parentObject` | Teamcenter::BusinessObject | The container object under which the new <b>Dataset</b> object will be created |

**响应（output）：**

```json
{
  "toolNames": [
    ""
  ],
  "toolDisplayNames": [
    ""
  ],
  "newDatasetName": "",
  "nameCanBeModified": "",
  "initValuePropertyRules": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `toolNames` | std::string[] | List of <b>Tool</b> names |
| `toolDisplayNames` | std::string[] | List of <b>Tool</b> display names. |
| `newDatasetName` | std::string | The name of the new <b>Dataset</b>, can be an empty string |
| `nameCanBeModified` | bool | If true, the name of the <b>Dataset</b> can be modified |
| `initValuePropertyRules` | std::string[] | List of properties have the initialized values from property constant attachments |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

##### 2.1.9.5 getLocalizedProperties

**接口路径：** `Core-2010-04-DataManagement/getLocalizedProperties`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** Typically 业务对象 属性 values are returned in the locale of the current 会话, 此操作 返回 desired 属性 values in any of the supported locales of the Teamcenter server. String type 属性 may be localized with values for each supported locale, 此操作 will return the translated values for one or more desired locales.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.getLocalizedProperties`

**请求（input）：**

```json
{
  "info": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propsToget": [
        {
          "name": "",
          "locales": [
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
| `info` | Teamcenter::Soa::Core::_2010_04::DataManagement::PropertyInfo[] | A list of desired business objects, property names, and locales to retrieve those properties in. |

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
      "propertyValues": [
        {
          "name": "",
          "values": [
            ""
          ],
          "locale": "",
          "seqNum": "",
          "status": [
            ""
          ],
          "statusDesc": [
            ""
          ],
          "master": ""
        }
      ]
    }
  ],
  "partialErrors": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2010_04::DataManagement::LocalizedPropertyValuesInfo[] | A list of structure LocalizedPropertyValuesInfo to keep the localized property values info. |
| `partialErrors` | Teamcenter::Soa::Server::ServiceData | Used for storing partial error and standard service data. |

---

##### 2.1.9.6 isPropertyLocalizable

**接口路径：** `Core-2010-04-DataManagement/isPropertyLocalizable`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 该操作 is used to determine if string-type 属性 is localizable or not and can retrieve the localizable status for ONE or MORE 属性.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.isPropertyLocalizable`

**请求（input）：**

```json
{
  "inputInfo": [
    {
      "objTypeName": "",
      "propNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputInfo` | Teamcenter::Soa::Core::_2010_04::DataManagement::LocalizableStatusInput[] |  A list of business object type names and internal property names |

**响应（output）：**

```json
{
  "results": [
    {
      "objTypeName": "",
      "results": [
        {
          "propName": "",
          "islocalizable": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `results` | Teamcenter::Soa::Core::_2010_04::DataManagement::LocalizableStatusOutput[] | A list of <font face="courier" height="10">LocalizableResults</font> structure to hold the localizable information for a |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">serviceData</font> |

---

##### 2.1.9.7 setLocalizedProperties

**接口路径：** `Core-2010-04-DataManagement/setLocalizedProperties`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 allows user to set or modify the display values for a localized 属性 on a single object. This 设置 the 属性 values for a single 属性 on an object in different locales. With the display values capability, each localized string 属性 could have different language translations associated with that. Please be aware of the following: 此操作 i…

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.setLocalizedProperties`

**请求（input）：**

```json
{
  "info": {
    "object": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "propertyValues": [
      {
        "name": "",
        "values": [
          ""
        ],
        "locale": "",
        "seqNum": "",
        "status": [
          ""
        ],
        "statusDesc": [
          ""
        ],
        "master": ""
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2010_04::DataManagement::LocalizedPropertyValuesInfo | The business object and a list of the property name, value and locale of the property value. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.9.8 setLocalizedPropertyValues

**接口路径：** `Core-2010-04-DataManagement/setLocalizedPropertyValues`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 设置 the 属性 values for multiple 属性 on a single object in different locales. With the display values capability, each localized string 属性 could have different language translations associated with that. 此操作 allows user to set or modify the display values for the localized 属性 on a single object. It should be noted that 此操作 is o…

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.setLocalizedPropertyValues`

**请求（input）：**

```json
{
  "info": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyValues": [
        {
          "name": "",
          "values": [
            ""
          ],
          "locale": "",
          "seqNum": "",
          "status": [
            ""
          ],
          "statusDesc": [
            ""
          ],
          "master": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2010_04::DataManagement::LocalizedPropertyValuesInfo[] |  A list of business object, the property name, value and locale of the property value. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2010-09

##### 2.1.10.1 createOrUpdateStaticTableData

**接口路径：** `Core-2010-09-DataManagement/createOrUpdateStaticTableData`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** This 创建 a new Table along with Rows or updates an existing Table with rows and their values based on input StaticTableInfo and created Table rows are added to the Table. ServiceData is updated with newly created/updated Table.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.createOrUpdateStaticTableData`

**请求（input）：**

```json
{
  "staticTableInfo": {
    "tableType": "",
    "tableObject": {
      "uid": "",
      "type": "",
      "className": ""
    }
  },
  "rowProperties": [
    {
      "clientId": "",
      "rowObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "rowType": "",
      "rowAttrValueMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `staticTableInfo` | Teamcenter::Soa::Core::_2010_09::DataManagement::StaticTableInfo | This represents static table object that needs to be created/updated. |
| `rowProperties` | Teamcenter::Soa::Core::_2010_09::DataManagement::RowData[] | Vector of RowData where each element is of type TableProperties |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "staticTableObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | SOA Service Data. |
| `staticTableObject` | Teamcenter::Fnd0StaticTable | StaticTable Object |

---

##### 2.1.10.2 getEventTypes

**接口路径：** `Core-2010-09-DataManagement/getEventTypes`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：获取Event Types。The getEventTypes operation retrieves the valid Auditable and Subscribable events for each of the businessObject in the input EventObject vector. When an event is auditable, you can audit actions on Teamcenter objects when that event happens on the businessObject. When an event is Subscribable, that means subscriptions can be created for that event. Partial failures, if any,…

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.getEventTypes`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "businessObject": {
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
| `input` | Teamcenter::Soa::Core::_2010_09::DataManagement::EventObject[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>EventObject</font> structure consisting of list of Busi |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "auditableEvents": [
        ""
      ],
      "subscribableEvents": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2010_09::DataManagement::EventTypesOutput[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>EventTypesOutput</font> structures packaged in custom r |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Partial failures will be returned in the ServiceDate for each failed processing. Error encountered while processing post |

---

##### 2.1.10.3 getStaticTableData

**接口路径：** `Core-2010-09-DataManagement/getStaticTableData`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 返回 a list of objects of type Table属性 which are associated with Fnd0StaticTable object. Fnd0StaticTable object has an attribute fnd0StaticTableData which is an array of Table属性 objects. Any failures will be returned with the input object mapped to the error message in the ServiceData list of partial errors.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.getStaticTableData`

**请求（input）：**

```json
{
  "staticTable": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `staticTable` | Teamcenter::Fnd0StaticTable | StaticTable |

**响应（output）：**

```json
{
  "clientId": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `clientId` | std::string | A unique string supplied by caller.<br />This ID is used to identify return data elements and partial errors associated  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data. |

---

##### 2.1.10.4 postEvent

**接口路径：** `Core-2010-09-DataManagement/postEvent`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 will post an event for each of the Teamcenter 业务对象 in the input list, with all the supplied information: secondaryObject, 属性 to be logged, and the error details. . Partial failures will be returned in the serviceData.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.postEvent`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
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
      "propertyCount": "",
      "propertyNames": [
        ""
      ],
      "propertyValues": [
        ""
      ],
      "errorCode": "",
      "errorMessage": ""
    }
  ],
  "eventTypeName": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2010_09::DataManagement::PostEventObjectProperties[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>ObjectProperties</font> structure. Each structure consi |
| `eventTypeName` | std::string | Name of the event. This is a mandatory parameter and should be a valid auditable or subscribable event mapped for the pr |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "ifailError": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2010_09::DataManagement::PostEventOutput[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>PostEventOutput</font> structures packaged in custom re |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Partial failures will be returned in the Service Data for each failed processing. Error encountered while processing pos |

---

##### 2.1.10.5 setProperties

**接口路径：** `Core-2010-09-DataManagement/setProperties`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 批量设置业务对象的属性值。

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.setProperties`

**请求（input）：**

```json
{
  "info": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "vecNameVal": [
        {
          "name": "",
          "values": [
            ""
          ]
        }
      ],
      "timestamp": "0001-01-01T00:00:00"
    }
  ],
  "options": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2010_09::DataManagement::PropInfo[] | List of PropInfo structure which consists of information about the objects and the property values to set. |
| `options` | std::string[] | To updating the objects in controlled manner. Valid options are:<br /><ul><ul><li type="disc"><b>No</b> options can be p |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "objPropMap": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | This is the service data. It contains the updated objects and their properties. |
| `objPropMap` | Teamcenter::Soa::Core::_2010_09::DataManagement::ObjectPropMap | Additional information to be communicated to client such as objects and props those are overwritten. This map can be emp |

---

##### 2.1.10.6 verifyExtension

**接口路径：** `Core-2010-09-DataManagement/verifyExtension`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 checks if an extension exists on an operation of a specific type.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.verifyExtension`

**请求（input）：**

```json
{
  "extensionInfo": [
    {
      "typeName": "",
      "operationName": "",
      "extensionName": "",
      "extensionType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `extensionInfo` | Teamcenter::Soa::Core::_2010_09::DataManagement::VerifyExtensionInfo[] | The specific type, operation and extension information required to verify an extension exists. |

**响应（output）：**

```json
{
  "output": [],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | bool[] | Returns True if extension exists otherwise False. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This data structure provides service data for associated information. |

---

#### 版本 2011-06

##### 2.1.11.1 getTraceReport

**接口路径：** `Core-2011-06-DataManagement/getTraceReport`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 will generate a Trace Report on the objects selected by user. User will get information about complying as well as defining objects which are connected to selected object using FND_TraceLink or its subtype of GRM relation. Trace links can be between following objects: 1. Between occurrences of an ItemRevision 2. Between ItemRevisions 3. Between Items 4. Betwee…

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.DataManagement.getTraceReport`

**请求（input）：**

```json
{
  "input": {
    "selectedObjs": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "reportType": "",
    "reportDepth": "",
    "isIndirectTraceReportNeeded": "",
    "relationTypeName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2011_06::DataManagement::TraceabilityInfoInput | A TraceabilityInfoInput structure to generate a Trace Report.This input structure holds selected objects for which trace |

**响应（output）：**

```json
{
  "traceReports": [
    {
      "definingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "indirectDefiningTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "complyingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "indirectComplyingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "selectedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "persistentObjects": [
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
| `traceReports` | Teamcenter::Soa::Core::_2011_06::DataManagement::TraceReport[] | This member holds all the Trace Reports user has asked for. This is vector of <br />TraceReport type of structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data. |

---

##### 2.1.11.2 saveAsObjects

**接口路径：** `Core-2011-06-DataManagement/saveAsObjects`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 is generic operation for saving of 业务对象. It will also save any secondary objects that also need to be saved based on deep copy rule information

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.DataManagement.saveAsObjects`

**请求（input）：**

```json
{
  "saveAsIn": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "saveAsInput": {
        "boName": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      },
      "deepCopyDatas": [
        {
          "attachedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "propertyName": "",
          "propertyType": "Relation",
          "copyAction": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": "",
          "saveAsInputTypeName": "",
          "childDeepCopyData": [],
          "saveAsInput": {
            "boName": "",
            "stringProps": {},
            "boolArrayProps": {},
            "dateProps": {},
            "dateArrayProps": {},
            "tagProps": {},
            "tagArrayProps": {},
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
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `saveAsIn` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsIn[] | Input data containing target object and DeepCopyData of the attached objects |

**响应（output）：**

```json
{
  "output": [
    {
      "targetObject": {
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
  ],
  "saveAsTrees": [
    {
      "originalObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectCopy": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childSaveAsNodes": []
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsOut[] | SaveAsout vector |
| `saveAsTrees` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsTree[] | List of the input target objects that holds mapping between the original objects and the copied  objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing created objects, errors, etc |

---

##### 2.1.11.3 validateRevIds

**接口路径：** `Core-2011-06-DataManagement/validateRevIds`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：校验Rev Ids。Validates and/or modifies the Revision Id based on the naming rules/revision naming rules and user exit callbacks.

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.DataManagement.validateRevIds`

**请求（input）：**

```json
{
  "inputs": [
    {
      "revId": "",
      "itemObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2011_06::DataManagement::ValidateRevIdsInfo[] | A list of <font face="courier" height="10">ValidateRevIdsInfo</font> structures, each of which contain revId/itemObject/ |

**响应（output）：**

```json
{
  "output": [
    {
      "modRevId": "",
      "revIdStatus": "ValidRevID"
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2011_06::DataManagement::ValidateRevIdsOutput[] | List of <font face="courier" height="10">ValidateRevIdsOutput</font> structures, which contain the modified revision id  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> structure. It contains partial errors and failures along wi |

---

#### 版本 2012-02

##### 2.1.12.1 bulkCreateObjects

**接口路径：** `Core-2012-02-DataManagement/bulkCreateObjects`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `bulkCreateObjects`。This is a generic operation for bulk creation of 业务对象. This will create instances of the given quantity of the specified type in their specified containing 文件夹s. This will also create any secondary(compounded) objects that need to be created, assuming the CreateInput for the secondary object is represented in the recursive CreateInput object e.g. Item is Prima…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.DataManagement.bulkCreateObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "quantity": "",
      "folder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "data": {
        "boName": "",
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2012_02::DataManagement::BulkCreIn[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>BulkCreIn</font> structures representing the <font face |

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOut[] | Vector of output objects representing objects that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data including partial errors that are mapped to the client id from the input. Created objects are also added to |

---

##### 2.1.12.2 validateIdValue

**接口路径：** `Core-2012-02-DataManagement/validateIdValue`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 determines if the given MultiFieldKey 属性 are unique based on the MultiFieldKey definition.

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.DataManagement.validateIdValue`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "data": {
        "boName": "",
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateIn[] | A list of MultiFieldKey attribute/value pairs for the object to be created |

**响应（output）：**

```json
{
  "validationResult": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `validationResult` | Teamcenter::Soa::Core::_2012_02::DataManagement::ValidationResult | A map of type <<font face="courier" height="10">std::string ,bool</font>> indicating if the ID is valid. The key is clie |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

##### 2.1.12.3 whereUsed

**接口路径：** `Core-2012-02-DataManagement/whereUsed`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 查询指定对象在结构或关系中的使用位置（Where Used）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.DataManagement.whereUsed`

**请求（input）：**

```json
{
  "input": [
    {
      "inputObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "useLocalParams": "",
      "inputParams": {
        "stringMap": {},
        "doubleMap": {},
        "intMap": {},
        "boolMap": {},
        "dateMap": {},
        "tagMap": {},
        "floatMap": {}
      },
      "clientId": ""
    }
  ],
  "configParams": {
    "stringMap": {},
    "doubleMap": {},
    "intMap": {},
    "boolMap": {},
    "dateMap": {},
    "tagMap": {},
    "floatMap": {}
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2012_02::DataManagement::WhereUsedInputData[] | <font face="courier" height="10">WhereUsedInputData</font> object list |
| `configParams` | Teamcenter::Soa::Core::_2012_02::DataManagement::WhereUsedConfigParameters | Additional Configuration Parameters if required. For example <font face="courier" height="10">tagMap</font> to specify t |

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
      "info": [
        {
          "parentObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "level": ""
        }
      ],
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2012_02::DataManagement::WhereUsedOutputData[] | List of <font face="courier" height="10">WhereUsedOutputData</font> structures |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> Member |

---

#### 版本 2012-09

##### 2.1.13.1 saveAsObjectAndRelate

**接口路径：** `Core-2012-09-DataManagement/saveAsObjectAndRelate`

**API 版本：** `2012-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 保存 the given object and its related objects as new instances. Related objects are identifed using deep copy rules. Optionally,this method relates the new object to the input target object or to a default 文件夹.

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_09.DataManagement.saveAsObjectAndRelate`

**请求（input）：**

```json
{
  "saveAsInput": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "saveAsInput": {
        "boName": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      },
      "deepCopyDatas": [
        {
          "attachedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "propertyName": "",
          "propertyType": "Relation",
          "copyAction": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": "",
          "saveAsInputTypeName": "",
          "childDeepCopyData": [],
          "saveAsInput": {
            "boName": "",
            "stringProps": {},
            "boolArrayProps": {},
            "dateProps": {},
            "dateArrayProps": {},
            "tagProps": {},
            "tagArrayProps": {},
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
  ],
  "relateInfo": [
    {
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyName": "",
      "relate": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `saveAsInput` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsIn[] | The property values to be used for the new objects. The properties passed in should be defined in SaveAs descriptor. |
| `relateInfo` | Teamcenter::Soa::Core::_2012_09::DataManagement::RelateInfoIn[] | The paste options used to relate the newly created object. |

**响应（output）：**

```json
{
  "output": [
    {
      "targetObject": {
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
  ],
  "saveAsTrees": [
    {
      "originalObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectCopy": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childSaveAsNodes": []
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsOut[] | SaveAsout vector |
| `saveAsTrees` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsTree[] | List of the input target objects that holds mapping between the original objects and the copied  objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing created objects, errors, etc |

---

#### 版本 2012-10

##### 2.1.14.1 getDatasetTypesWithFileExtension

**接口路径：** `Core-2012-10-DataManagement/getDatasetTypesWithFileExtension`

**API 版本：** `2012-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 the 数据集 type and reference information for a set of file extensions. Named references are Teamcenter objects that relate to a specific data file. For each file extension, it is possible that it belongs to multiple 数据集 types. For such cases, all matching 数据集 types will be returned using the file extension as the key in the Get数据集TypesWit…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_10.DataManagement.getDatasetTypesWithFileExtension`

**请求（input）：**

```json
{
  "fileExtensions": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `fileExtensions` | std::string[] | List of file extensions used to get the named reference information |

**响应（output）：**

```json
{
  "output": [
    {
      "fileExtension": "",
      "datasetTypesInfo": [
        {
          "tag": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "refInfos": [
            {
              "referenceName": "",
              "isObject": "",
              "fileFormat": "",
              "fileExtension": ""
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
| `output` | Teamcenter::Soa::Core::_2012_10::DataManagement::GetDatasetTypesWithFileExtensionOutput[] | List of named reference information for each dataset type specified in fileExtensions input |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The DatasetType objects that corresponds to fileExtensions input |

---

##### 2.1.14.2 getTraceReport

**接口路径：** `Core-2012-10-DataManagement/getTraceReport`

**API 版本：** `2012-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 will generate a Trace Report on the objects selected by user. The report will contain information about complying as well as defining objects which are connected to selected object using FND_TraceLink, or its subtype. 此操作 will check if there is any TraceLink relation starting or ending from selected object(s). If TraceLink relation exists for select…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_10.DataManagement.getTraceReport`

**请求（input）：**

```json
{
  "input": [
    {
      "selectedObjs": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "reportType": "",
      "exportTo": "",
      "exportTemplate": "",
      "exportColumnNames": [
        ""
      ],
      "reportDepth": "",
      "isIndirectTraceReportNeeded": "",
      "filteredTraceLinkTypes": [
        ""
      ],
      "filteredObjectTypes": [
        ""
      ],
      "scopeLines": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "propertyFilterInput": [
        {
          "logicalOperatorType": "",
          "propertyName": "",
          "operatorType": "",
          "propertyValue": ""
        }
      ],
      "sortPropName": "",
      "sortDirection": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2012_10::DataManagement::TraceabilityInfoInput1[] | A list of TraceabilityInfoInput1 structure to generate a Trace Report. This input structure holds, selected object(s) (f |

**响应（output）：**

```json
{
  "traceReports": [
    {
      "defRootNode": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "srcContextName": "",
        "tarContextName": "",
        "bomView": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isDirectLink": "",
        "isTraceLinkObj": "",
        "childNodes": []
      },
      "compRootNode": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "srcContextName": "",
        "tarContextName": "",
        "bomView": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isDirectLink": "",
        "isTraceLinkObj": "",
        "childNodes": []
      },
      "selectedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "persistentObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "transientFileReadTickets": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `traceReports` | Teamcenter::Soa::Core::_2012_10::DataManagement::TraceReport1[] | This member holds all the Trace Reports user has asked for. This is vector of TraceReport1 type of structures. |
| `transientFileReadTickets` | std::string[] | The transient file read tickets for the exported file. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data. |

---

##### 2.1.14.3 refreshObjects2

**接口路径：** `Core-2012-10-DataManagement/refreshObjects2`

**API 版本：** `2012-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 is used to reload the in-memory representation of the objects from the database. Any references to the object will still be valid. Any in-memory changes to the original object will be lost. If the object has been changed in the database since it was last loaded, then those changes will not be present in memory. 该操作 updates the in memory representatio…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_10.DataManagement.refreshObjects2`

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
  "lockObjects": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of business objects for which lock or unlock operation is required . |
| `lockObjects` | bool | If true then business objects will be locked , false will unlock the given business objects. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2013-05

##### 2.1.15.1 generateNextValues

**接口路径：** `Core-2013-05-DataManagement/generateNextValues`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates values for the given 属性 of an object(s) during create/revise/save as action based on the user exits or naming rules configured on those 属性. Customer user exits are given priority over the naming rules if both of them are configured on the same 属性. The counter has to be set active on the naming rule in order to generate the next …

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.generateNextValues`

**请求（input）：**

```json
{
  "generateNextValuesIn": [
    {
      "clientId": "",
      "operationType": "",
      "businessObjectName": "",
      "propertyNameWithSelectedPattern": {},
      "propValues": {},
      "additionalInputParams": {},
      "compoundObjectInput": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `generateNextValuesIn` | Teamcenter::Soa::Core::_2013_05::DataManagement::GenerateNextValuesIn[] | This is the input that the SOA 'generateNextValues' expects. This contains the list of properties for which the next val |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "generatedValues": [
    {
      "clientId": "",
      "generatedValues": {},
      "generatedValuesOfSecondaryObjects": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | The Service Data with partial errors for each GenerateNextValuesInput and identified by  its clientId. |
| `generatedValues` | Teamcenter::Soa::Core::_2013_05::DataManagement::GeneratedValuesOutput[] | A list of GeneratedValuesOutput one for each entry in generateNextvaluesIn input list and  identified by its clientId. |

---

##### 2.1.15.2 getChildren

**接口路径：** `Core-2013-05-DataManagement/getChildren`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 the children for each input object. The children returned is determined by the input 属性Names list of strings which defines the 属性 which are to be processed in order to collect the children to be returned If the 属性Names list is empty, then the 属性 which are processed to object the children is based on the _DefaultChildProperti…

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.getChildren`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "obj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2013_05::DataManagement::GetChildrenInputData[] | The list of objects and desired children for which to expand and return children. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "objectWithChildren": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The service data contains any partial errors which may have been encountered during processing.  All business objects wh |
| `objectWithChildren` | Teamcenter::Soa::Core::_2013_05::DataManagement::GetChildrenOutputMap | A map of requested objects and a list of children(business object/vector<GetChildrenOutput>). |

---

##### 2.1.15.3 getPasteRelations

**接口路径：** `Core-2013-05-DataManagement/getPasteRelations`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 返回 the paste relation names for the given parent types and the child types, within which the expandable relations and the preferred paste relation are indicated.

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.getPasteRelations`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "obj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childTypeName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2013_05::DataManagement::GetPasteRelationsInputData[] | The list of  the parent object and the child type. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "outputMap": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The service data contains any partial errors which may have been encountered during processing.  All business objects wh |
| `outputMap` | Teamcenter::Soa::Core::_2013_05::DataManagement::GetPasteRelationsOutputMap | A map of input parent object to a vector of GetPasteRelationsOutput objects. |

---

##### 2.1.15.4 getSubTypeNames

**接口路径：** `Core-2013-05-DataManagement/getSubTypeNames`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 获取指定类型的子类型名称列表。

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.getSubTypeNames`

**请求（input）：**

```json
{
  "inBOTypeNames": [
    {
      "typeName": "",
      "contextName": "",
      "exclusionPreference": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inBOTypeNames` | Teamcenter::Soa::Core::_2013_05::DataManagement::SubTypeNamesInput[] | A list of business object type names with the desired context. |

**响应（output）：**

```json
{
  "output": [
    {
      "typeName": "",
      "contextName": "",
      "exclusionPreference": "",
      "subTypeNames": [
        ""
      ],
      "displayableSubTypeNames": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2013_05::DataManagement::SubTypeNamesOut[] | List of  business object type names. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service data. |

---

##### 2.1.15.5 reviseObjects

**接口路径：** `Core-2013-05-DataManagement/reviseObjects`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 is generic single revise operation for revisable 业务对象. 此操作 revises the given objects and copies or 创建 new objects using the data for the 属性 values and deep copy data. Deep copy processing is recursive such that relations between secondary objects, or from secondary objects to the revised object, are replicated during this revi…

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.reviseObjects`

**请求（input）：**

```json
{
  "reviseIn": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "reviseInputs": {},
      "deepCopyDatas": [
        {
          "attachedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "propertyName": "",
          "propertyType": "",
          "copyAction": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": "",
          "operationInputTypeName": "",
          "childDeepCopyData": [],
          "operationInputs": {}
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `reviseIn` | Teamcenter::Soa::Core::_2013_05::DataManagement::ReviseIn[] | Input data containing target object and DeepCopyData of the attached objects |

**响应（output）：**

```json
{
  "output": [
    {
      "targetObject": {
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
  ],
  "reviseTrees": [
    {
      "originalObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectCopy": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childReviseNodes": []
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2013_05::DataManagement::ReviseOut[] | The target object and the newly created revised objects. |
| `reviseTrees` | Teamcenter::Soa::Core::_2013_05::DataManagement::ReviseTree[] | List corresponding to the input target objects that holds mapping between the original objects and the copied objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Data containing created objects, errors, etc. |

---

##### 2.1.15.6 validateValues

**接口路径：** `Core-2013-05-DataManagement/validateValues`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 validates whether the input 属性 values are valid according to defined naming rules and specified user exits for the input 属性. Also, for the 属性 used in the multifield key (MFK) definition for the input type, 此操作 validates whether the combined 属性 values makes up a unique value. The validateValues operation can be called before…

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.validateValues`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "operationType": "",
      "businessObjectName": "",
      "propValuesMap": {},
      "compoundObjectInput": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2013_05::DataManagement::ValidateInput[] | The list of <b>ValidateInput</b>. The properties specified in each input are validated against defined naming rules and  |

**响应（output）：**

```json
{
  "validationResults": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `validationResults` | Teamcenter::Soa::Core::_2013_05::DataManagement::ValidationResultsMap | A map where the key (string) is the <font face="courier" height="10">clientId</font> and the value (<font face="courier" |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing errors that occurred during the operation. |

---

#### 版本 2014-06

##### 2.1.16.1 getTraceReport2

**接口路径：** `Core-2014-06-DataManagement/getTraceReport2`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates a Trace Report for the input objects. The report will contain information about complying as well as defining objects which are connected to input object using FND_TraceLink, or its subtype. 此操作 checks if there is any FND_TraceLink relation starting or ending from input object(s). If FND_TraceLink relation exists for input object(s), then …

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.DataManagement.getTraceReport2`

**请求（input）：**

```json
{
  "input": [
    {
      "selectedObjs": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "reportType": "",
      "exportTo": "",
      "exportTemplate": "",
      "exportColumnNames": [
        ""
      ],
      "reportDepth": "",
      "isIndirectTraceReportNeeded": "",
      "filteredTraceLinkTypes": [
        ""
      ],
      "filteredObjectTypes": [
        ""
      ],
      "scopeLines": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "propertyFilterInput": [
        {
          "logicalOperatorType": "",
          "propertyName": "",
          "operatorType": "",
          "propertyValue": ""
        }
      ],
      "sortPropName": "",
      "sortDirection": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2012_10::DataManagement::TraceabilityInfoInput1[] | Information required to generate a trace report. The object(s) (for which trace report needs to be generated), trace rep |

**响应（output）：**

```json
{
  "traceReports": [
    {
      "defRootNode": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "srcContextName": "",
        "tarContextName": "",
        "bomView": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "contextLineObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isDirectLink": "",
        "isTraceLinkObj": "",
        "childNodes": []
      },
      "compRootNode": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "srcContextName": "",
        "tarContextName": "",
        "bomView": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "contextLineObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isDirectLink": "",
        "isTraceLinkObj": "",
        "childNodes": []
      },
      "selectedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "persistentObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "transientFileReadTickets": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `traceReports` | Teamcenter::Soa::Core::_2014_06::DataManagement::TraceReport2[] | All of the requested Trace Reports. |
| `transientFileReadTickets` | std::string[] | The transient file read tickets for the exported file, this is specific to Export to Excel. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data. |

---

##### 2.1.16.2 getTraceReportLegacy

**接口路径：** `Core-2014-06-DataManagement/getTraceReportLegacy`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates a Trace Report for the input objects. 此操作 返回 information about complying as well as defining objects which are connected to selected object using FND_TraceLink or its subtype of GRM relation. Trace links can be between following objects: 1. Between occurrences of an ItemRevision 2. Between any two WorkspaceObject. If indirect trace re…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.DataManagement.getTraceReportLegacy`

**请求（input）：**

```json
{
  "input": {
    "selectedObjs": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "reportType": "",
    "reportDepth": "",
    "isIndirectTraceReportNeeded": "",
    "relationTypeName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2011_06::DataManagement::TraceabilityInfoInput | A TraceabilityInfoInput structure to generate a Trace Report.This input structure holds selected objects for which trace |

**响应（output）：**

```json
{
  "traceReports": [
    {
      "definingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "contextLineObj": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "contextLineObj": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "indirectDefiningTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "contextLineObj": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "contextLineObj": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "complyingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "contextLineObj": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "contextLineObj": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "indirectComplyingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "contextLineObj": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "contextLineObj": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "selectedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "persistentObjects": [
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
| `traceReports` | Teamcenter::Soa::Core::_2014_06::DataManagement::TraceReportLegacy[] | This member holds all the Trace Reports user has asked for. This is list of <br />TraceReport type of structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data. |

---

#### 版本 2014-10

##### 2.1.17.1 addChildren

**接口路径：** `Core-2014-10-DataManagement/addChildren`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 adds a list of objects as children to a list of parent objects which could be related by relation or reference 属性. If the 属性 name is not supplied as input it will use the default relation 属性 between the parent and the children given by ParentTypeName>_ChildTypeName>_default_relation. Please see the Preferences and Environment variables refe…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.addChildren`

**请求（input）：**

```json
{
  "inputData": [
    {
      "clientId": "",
      "parentObj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childrenObj": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "propertyName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputData` | Teamcenter::Soa::Core::_2014_10::DataManagement::ChildrenInputData[] | A list which contains list of children objects, parent object and the <br />property name (optional) by which the parent |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.17.2 generateIdsUsingIDGenerationRules

**接口路径：** `Core-2014-10-DataManagement/generateIdsUsingIDGenerationRules`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates object ids using ID Generation Rules associated with the 业务对象's 属性. Currently only Item and its subtypes are supported. Object ids are generated using information provided in createInput. 此操作 should be called in case of a specific requirement where ID Generation is independent of creating Objects. (e.g. in case of some CAD…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.generateIdsUsingIDGenerationRules`

**请求（input）：**

```json
{
  "generateIdsInputs": [
    {
      "createInput": {
        "boName": "",
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
      "propertyName": "",
      "quantity": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `generateIdsInputs` | Teamcenter::Soa::Core::_2014_10::DataManagement::GenerateIdInput[] | <ul><ul><li type="disc">A Structure containing input values for the operation</li></ul></ul> |

**响应（output）：**

```json
{
  "generateIdsOutput": [
    {
      "generatedIDs": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `generateIdsOutput` | Teamcenter::Soa::Core::_2014_10::DataManagement::GenerateIdResponseStruct[] | Multiple lists of Generated IDs. Each list corresponds to the individual elements in GenerateIdInputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Holds error stacks. |

---

##### 2.1.17.3 getDeepCopyData

**接口路径：** `Core-2014-10-DataManagement/getDeepCopyData`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 获取深拷贝所需的数据结构。

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.getDeepCopyData`

**请求（input）：**

```json
{
  "deepCopyDataInput": [
    {
      "operation": "",
      "businessObject": {
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
| `deepCopyDataInput` | Teamcenter::Soa::Core::_2014_10::DataManagement::DeepCopyDataInput[] | A list ofPOM_objects and operation type. |

**响应（output）：**

```json
{
  "deepCopyInfoMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `deepCopyInfoMap` | Teamcenter::Soa::Core::_2014_10::DataManagement::DeepCopyInfoMap | A map of business objects and DeepCopyData (POM_object/DeepCopyData). Each business object from the method input will ha |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing errors, etc. The plain object list of the Service data is populated with the target objects whic |

---

##### 2.1.17.4 getPasteRelations2

**接口路径：** `Core-2014-10-DataManagement/getPasteRelations2`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 the paste relation names for the given parent 业务对象 and the child 业务对象 name; the expandable relations and the preferred paste relation are also indicated.

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.getPasteRelations2`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "obj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childTypeName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2013_05::DataManagement::GetPasteRelationsInputData[] | List of parent parent and child buiness objects<b> </b>with clientId |

**响应（output）：**

```json
{
  "outputs": [
    {
      "clientId": "",
      "pasteRelInfo": [
        {
          "pastRelName": "",
          "pastRelDisplayName": "",
          "isExpandable": ""
        }
      ],
      "indexOfPreferred": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `outputs` | Teamcenter::Soa::Core::_2014_10::DataManagement::GetPasteRelationsOutput2[] | A list of paste relation output. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">Service Data</font> including partial errors that are mapped to the client id from the  |

---

##### 2.1.17.5 pruneNamedReferences

**接口路径：** `Core-2014-10-DataManagement/pruneNamedReferences`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 performs a prune operation by a given list of 数据集 named references, per the following criteria 1. Remove the input named references from their owning 数据集 2. Delete the input named reference objects 3. Delete the owning 数据集 objects which contain no named references after the prune operation 4. The pruned named references, deleted 数据集s and update…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.pruneNamedReferences`

**请求（input）：**

```json
{
  "namedReferences": [
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
| `namedReferences` | Teamcenter::POM_object[] | List of <b>Dataset</b> <font face="courier" height="10">named references</font> to be pruned |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.17.6 removeChildren

**接口路径：** `Core-2014-10-DataManagement/removeChildren`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 removes a list of objects as children to a list of parent objects which could be related by relation or reference 属性. If the 属性 name is not supplied as input it will use the default relation 属性 between the parent and the children given by ParentTypeName>_ChildTypeName>_default_relation. Please see the Preferences and Environment variables r…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.removeChildren`

**请求（input）：**

```json
{
  "inputData": [
    {
      "clientId": "",
      "parentObj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childrenObj": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "propertyName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputData` | Teamcenter::Soa::Core::_2014_10::DataManagement::ChildrenInputData[] | A  list containing a list of children objects, parent object and relation name (optional) by which parent and children a |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.17.7 saveAsObjectsAndRelate

**接口路径：** `Core-2014-10-DataManagement/saveAsObjectsAndRelate`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 performs SaveAs on the input target 业务对象 and its related objects as new instances. Related objects are identifed using deep copy rules. Optionally, this method relates the new object to the input target object or to a default 文件夹.

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.saveAsObjectsAndRelate`

**请求（input）：**

```json
{
  "iVecSoaSavAsIn": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "inputPropValues": {},
      "deepCopyDatas": [
        {
          "attachedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "propertyName": "",
          "propertyType": "",
          "copyAction": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": "",
          "operationInputTypeName": "",
          "childDeepCopyData": [],
          "operationInputs": {}
        }
      ]
    }
  ],
  "iVecSoaRelteInfoIn": [
    {
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyName": "",
      "relate": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `iVecSoaSavAsIn` | Teamcenter::Soa::Core::_2014_10::DataManagement::SaveAsIn[] | Input data containing target object, map (PropertyValuesMap) of properties and their corresponding values and DeepCopyDa |
| `iVecSoaRelteInfoIn` | Teamcenter::Soa::Core::_2012_09::DataManagement::RelateInfoIn[] | Input data containing the paste options used to relate the newly created object. |

**响应（output）：**

```json
{
  "output": [
    {
      "targetObject": {
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
  ],
  "saveAsTrees": [
    {
      "originalObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectCopy": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childSaveAsNodes": []
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsOut[] | SaveAsout vector |
| `saveAsTrees` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsTree[] | List of the input target objects that holds mapping between the original objects and the copied  objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing created objects, errors, etc |

---

#### 版本 2015-07

##### 2.1.18.1 createRelateAndSubmitObjects2

**接口路径：** `Core-2015-07-DataManagement/createRelateAndSubmitObjects2`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：创建Relate And Submit 对象s2。This is a generic operation for creation of 业务对象. This will also create any secondary (compounded) objects that need to be created, assuming the CreateInput2 for the secondary object is represented in the recursive CreateInput2 object e.g. Item is primary object that also 创建 Item Master and ItemRevision. ItemRevision in turn 创建 ItemRevision Master. The …

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.createRelateAndSubmitObjects2`

**请求（input）：**

```json
{
  "createInputs": [
    {
      "clientId": "",
      "createData": {
        "boName": "",
        "propertyNameValues": {},
        "compoundCreateInput": {}
      },
      "dataToBeRelated": {},
      "workflowData": {},
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "pasteProp": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `createInputs` | Teamcenter::Soa::Core::_2015_07::DataManagement::CreateIn2[] | This is a list of <i>CreateIn2</i> objects in which each one represents the information required for the following opera |

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOut[] | Vector of output objects representing objects that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data including partial errors that are mapped to the client id from the input. Created objects are also added to |

---

##### 2.1.18.2 generateNextValuesForProperties

**接口路径：** `Core-2015-07-DataManagement/generateNextValuesForProperties`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates values for the given 属性 of an object(s) during create/revise/save as action based on the user exits or naming rules configured on those 属性.Customer user exits are given priority over the naming rules if both of them are configured on the same 属性. The counter has to be set active on the naming rule in order to generate the next v…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.generateNextValuesForProperties`

**请求（input）：**

```json
{
  "propertyNamingRuleInfo": [
    {
      "clientId": "",
      "operationType": "",
      "businessObjectTypeName": "",
      "propertyNameAttachedPattern": {},
      "propertyValuesMap": {},
      "additionalInputMap": {},
      "compoundObjectInput": {},
      "propertyNameContextListMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `propertyNamingRuleInfo` | Teamcenter::Soa::Core::_2015_07::DataManagement::PropertyNamingruleInfo[] | This is the input that the operation 'generateNextValuesForProperties' expects. This contains the list of properties for |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "generatedValues": [
    {
      "clientId": "",
      "generatedValues": {},
      "generatedValuesOfSecondaryObjects": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | The Service Data with partial errors for each GenerateNextValuesInput and identified by  its clientId. |
| `generatedValues` | Teamcenter::Soa::Core::_2013_05::DataManagement::GeneratedValuesOutput[] | A list of GeneratedValuesOutput one for each entry in generateNextvaluesIn input list and  identified by its clientId. |

---

##### 2.1.18.3 getCreatbleSubBuisnessObjectNames

**接口路径：** `Core-2015-07-DataManagement/getCreatbleSubBuisnessObjectNames`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 sub 业务对象 names that are displayable to the login user in the object creation dialog and their display names for each primary 业务对象 given as the input, based on specified context. Returned 业务对象 lists have exclusions of 业务对象 and their secondary 业务对象 as per the exclusion preference and/or exlusion bu…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.getCreatbleSubBuisnessObjectNames`

**请求（input）：**

```json
{
  "input": [
    {
      "boName": "",
      "exclusionPreference": "",
      "exclusionBONames": [
        ""
      ],
      "context": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2015_07::DataManagement::CreatableSubBONamesInput[] | A list of primary business object names and the exclusion preferences and/or types, along with context, for which the cr |

**响应（output）：**

```json
{
  "output": [
    {
      "boName": "",
      "creatableBONames": [
        {
          "boName": "",
          "boDisplayName": "",
          "boParents": [
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
| `output` | Teamcenter::Soa::Core::_2015_07::DataManagement::CreatableBusinessObjectsOut[] | List of output objects representing the creatable business objects displayable in the Create dialog |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data including the partial errors that are mapped to the input primary business objects |

---

##### 2.1.18.4 getDeepCopyData

**接口路径：** `Core-2015-07-DataManagement/getDeepCopyData`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 获取深拷贝所需的数据结构。

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.getDeepCopyData`

**请求（input）：**

```json
{
  "deepCopyDataInput": {
    "operation": "",
    "targetObject": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "deepCopyDatas": [
      {
        "attachedObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "propertyValuesMap": {},
        "operationInputTypeName": "",
        "childDeepCopyData": [],
        "operationInputs": {}
      }
    ],
    "parentDeepCopyData": {
      "attachedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyValuesMap": {},
      "operationInputTypeName": "",
      "childDeepCopyData": [],
      "operationInputs": {}
    },
    "selectedBO": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `deepCopyDataInput` | Teamcenter::Soa::Core::_2015_07::DataManagement::DeepCopyDataInput | The information about the business object (which save-as and revise will be performed ), its DeepCopyData, the business  |

**响应（output）：**

```json
{
  "selectedBOIsDuplicated": "",
  "deepCopyDatas": [
    {
      "attachedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyValuesMap": {},
      "operationInputTypeName": "",
      "childDeepCopyData": [],
      "operationInputs": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `selectedBOIsDuplicated` | bool | This indicates whether the <font face="courier" height="10">selectedBO</font> from the method input already has DeepCopy |
| `deepCopyDatas` | Teamcenter::Soa::Core::_2014_10::DataManagement::DeepCopyData[] | A list of DeepCopyData for the <font face="courier" height="10">selectedBO</font> from the method input. The DeepCopyDat |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing errors, etc. The plain object list of the Service data is populated with the target objects whic |

---

##### 2.1.18.5 getDomainOfObjectOrType

**接口路径：** `Core-2015-07-DataManagement/getDomainOfObjectOrType`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 identifies the application domain information of the input design artifact object or type name and the domain value will be returned as part of the response. The input object can be any WorkspaceObject. The application domain where the object or the type belongs to is returned as domain value. Out of the box the supported application domains are &ldquo;Mechani…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.getDomainOfObjectOrType`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "inputDesignArtifact": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "typName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2015_07::DataManagement::GetDomainInput[] |  Input object or type name for which the application domain information is to be identified. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "domain": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2015_07::DataManagement::DomainOutput[] | The domain information output. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Holds any partial errors occurred during the operation. |

---

##### 2.1.18.6 getLocalizedProperties2

**接口路径：** `Core-2015-07-DataManagement/getLocalizedProperties2`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** Typically 业务对象 属性 values are returned in the locale of the current 会话, 此操作 返回 desired 属性 values in any of the supported locales of the Teamcenter server. String type 属性 may be localized with values for each supported locale, 此操作 will return the translated values for one or more desired locales.

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.getLocalizedProperties2`

**请求（input）：**

```json
{
  "propertyInfo": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propsToget": [
        {
          "name": "",
          "locales": [
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
| `propertyInfo` | Teamcenter::Soa::Core::_2010_04::DataManagement::PropertyInfo[] | A list of desired business objects, property names, and locales to retrieve those properties in. |

**响应（output）：**

```json
{
  "output": [
    {
      "businessObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyValues": [
        {
          "name": "",
          "values": [
            ""
          ],
          "locale": "",
          "seqNum": "",
          "status": [
            ""
          ],
          "internalStatus": [
            ""
          ],
          "statusDesc": [
            ""
          ],
          "master": ""
        }
      ]
    }
  ],
  "partialErrors": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2015_07::DataManagement::LocalizedPropertyValuesInfo2[] | A list of structure LocalizedPropertyValuesInfo2 to keep the localized property values info. |
| `partialErrors` | Teamcenter::Soa::Server::ServiceData | Used for storing partial error and standard service data. |

---

#### 版本 2015-10

##### 2.1.19.1 reassignParticipants

**接口路径：** `Core-2015-10-DataManagement/reassignParticipants`

**API 版本：** `2015-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `reassignParticipants`。Reassigns the participant roles from one user to another for a given list of participant types on the input list of objects. The Particpant for the fromAssignee User is replaced with the Particpant for the toAssignee User. If the toAssignee User already exists as participant, then the fromAssignee User will not be replaced.

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.DataManagement.reassignParticipants`

**请求（input）：**

```json
{
  "reassignParticipantInfo": [
    {
      "itemRevs": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "fromAssignee": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toAssignee": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "participantTypes": [
        ""
      ],
      "allParticipantTypes": "",
      "comments": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `reassignParticipantInfo` | Teamcenter::Soa::Core::_2015_10::DataManagement::ReassignParticipantInfo[] | A list of structures containing a list of input objects whose participant roles are reassigned, assignee to reassign fro |

**响应（output）：**

```json
{
  "failedObjects": [
    {
      "clientId": "",
      "failedItemRevs": [
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
| `failedObjects` | Teamcenter::Soa::Core::_2015_10::DataManagement::ReassignParticipantOutput[] | A list of failed objects information. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The modified participant objects are returned along with partial errors. |

---

#### 版本 2016-05

##### 2.1.20.1 generateContextSpecificIDs

**接口路径：** `Core-2016-05-DataManagement/generateContextSpecificIDs`

**API 版本：** `2016-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `generateContextSpecificIDs`。Generates the range of unique IDs for input context names. The number of IDs generated for each context name depends on the input. If for a given context name, the ID has been reset using Teamcenter service resetContextID, then this service generates IDs for that context from the beginning. ID generation will also reset when the maximum limit is met. This limit is maximum nu…

**Soa Inclusion：** `Teamcenter.Soa.Core._2016_05.DataManagement.generateContextSpecificIDs`

**请求（input）：**

```json
{
  "generateContextIDsIn": [
    {
      "clientID": "",
      "contextName": "",
      "numberOfIDs": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `generateContextIDsIn` | Teamcenter::Soa::Core::_2016_05::DataManagement::GenerateContextIDsInput[] | List of GenerateContextIDsInput which contains the context name and number of IDs to be generated for that context. Cont |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "generatedContextIDValues": [
    {
      "contextName": "",
      "generatedIDs": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Partial Errors are returned in the ServiceData when service generateContextSpecificIDs fails to generate IDs of any of t |
| `generatedContextIDValues` | Teamcenter::Soa::Core::_2016_05::DataManagement::GeneratedContextIDs[] | A list of GeneratedContextIDs, which contains each of the context names and IDs generated for it by service generateCont |

---

##### 2.1.20.2 resetContextID

**接口路径：** `Core-2016-05-DataManagement/resetContextID`

**API 版本：** `2016-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `resetContextID`。This service enables the client to reset the ID for given context names. When the IDs for a context name are reset, ID generation will begain from beginning value. WARNING: Be advised that if a client re设置 the ID for a context name, it is possible that repeated IDs will be returned from generateContextSpecificIDs service for that context name.

**Soa Inclusion：** `Teamcenter.Soa.Core._2016_05.DataManagement.resetContextID`

**请求（input）：**

```json
{
  "contextNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `contextNames` | std::string[] | List of the context names for those, IDs to be reset. Empty strings should not be used to reset ID. An error is returned |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.20.3 setPropertiesAndDetectOverwrite

**接口路径：** `Core-2016-05-DataManagement/setPropertiesAndDetectOverwrite`

**API 版本：** `2016-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 detects the overwrite condition for the 业务对象 instances if those are modified by any other 会话 concurrently and updates the remaining objects with the new 属性 values provided. Use 此操作 if the overwrite detection is required to avoid any unintentional overwriting of the objects due to concurrent modification of the object. The overw…

**Soa Inclusion：** `Teamcenter.Soa.Core._2016_05.DataManagement.setPropertiesAndDetectOverwrite`

**请求（input）：**

```json
{
  "propData": [
    {
      "businessObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "vecPropNameVal": [
        {
          "propertyName": "",
          "oldValues": [
            ""
          ],
          "newValues": [
            ""
          ]
        }
      ],
      "lastSavedDateExportedToClient": "0001-01-01T00:00:00"
    }
  ],
  "options": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `propData` | Teamcenter::Soa::Core::_2016_05::DataManagement::PropData[] | List of PropData structure which consists of information about the objects, old values of properties and new values of   |
| `options` | Teamcenter::Soa::Core::_2016_05::DataManagement::OptionsMap | A map ( string / list of strings ) of options. Valid keys are:<br />1. SKIP_SAVING_ALL_OBJECTS_ON_CONFLICT: Valid values |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "overwriteDetectedObjPropMap": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | This is the service data. It contains the updated objects and their properties. |
| `overwriteDetectedObjPropMap` | Teamcenter::Soa::Core::_2016_05::DataManagement::ObjectPropertiesMap | The  map ( business object / list of string ) contains the objects and properties list for which overwrite condition has |

---

#### 版本 2016-09

##### 2.1.21.1 createAttachAndSubmitObjects

**接口路径：** `Core-2016-09-DataManagement/createAttachAndSubmitObjects`

**API 版本：** `2016-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建对象、建立附件关系并提交（组合操作）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2016_09.DataManagement.createAttachAndSubmitObjects`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "createData": {
        "boName": "",
        "propertyNameValues": {},
        "compoundCreateInput": {}
      },
      "dataToBeRelated": {},
      "workflowData": {},
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "pasteProp": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2015_07::DataManagement::CreateIn2[] | This is a list of CreateIn2 objects in which each one represents the information required for the following operations:< |

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
      ],
      "datasets": [
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
                    "namedReferenceName": "",
                    "isText": "",
                    "allowReplace": ""
                  },
                  "ticket": ""
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
| `output` | Teamcenter::Soa::Core::_2016_09::DataManagement::CreateAttachOut[] | List of output objects representing objects that were created |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data including partial errors that are mapped to the client id |

---

#### 版本 2018-06

##### 2.1.22.1 createObjectsInBulkAndRelate

**接口路径：** `Core-2018-06-DataManagement/createObjectsInBulkAndRelate`

**API 版本：** `2018-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：创建对象s In Bulk And Relate。(1) This is a generic operation for creation of 业务对象 in bulk (i.e. in a set&ndash;based manner). All 业务对象 will be created or none, a failure for a single object will result in no 业务对象 being created. 此操作 will also create any secondary objects compounded with the main object being created. For example, please refer to the Create I…

**Soa Inclusion：** `Teamcenter.Soa.Core._2018_06.DataManagement.createObjectsInBulkAndRelate`

**请求（input）：**

```json
{
  "createInputs": [
    {
      "clientId": "",
      "createData": {
        "boName": "",
        "propertyNameValues": {},
        "compoundCreateInput": {}
      },
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "pasteProp": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `createInputs` | Teamcenter::Soa::Core::_2018_06::DataManagement::CreateIn3[] | This is a list of <i>CreateIn3</i> objects in which each one represents the information required for the following:<br / |

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOut[] | Vector of output objects representing objects that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data including partial errors that are mapped to the client id from the input. Created objects are also added to |

---

#### 版本 2019-06

##### 2.1.23.1 unlinkAndDeleteObjects

**接口路径：** `Core-2019-06-DataManagement/unlinkAndDeleteObjects`

**API 版本：** `2019-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 unlinks the input objects from their corresponding container and then attempts to 删除 them. The input objects are related to the container as the reference or relation 属性 supplied as part of the input. 该操作 also takes a flag whether to unlink the objects from the container in case the deletion fails. After unlinking the objects from the inpu…

**Soa Inclusion：** `Teamcenter.Soa.Core._2019_06.DataManagement.unlinkAndDeleteObjects`

**请求（input）：**

```json
{
  "deleteInput": [
    {
      "container": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectsToDelete": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "property": "",
      "unlinkAlways": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `deleteInput` | Teamcenter::Soa::Core::_2019_06::DataManagement::DeleteIn[] | A list containing an input container and list of objects to be first unrelated from the container and then deleted. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2020-01

##### 2.1.24.1 createIdDisplayRules

**接口路径：** `Core-2020-01-DataManagement/createIdDisplayRules`

**API 版本：** `2020-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 创建 the ID Display Rules (IdDispRule) with the input ID Context information. ID Display Rule contains the list of ID Contexts and their order. Based on the order of the ID Contexts defined, the system evaluates the display name of the Item and ItemRevision from their Alternate IDs. ID Context (IdContext), represents the context information under which the …

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.DataManagement.createIdDisplayRules`

**请求（input）：**

```json
{
  "idDispRuleCreIns": [
    {
      "ruleName": "",
      "idContexts": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "useDefault": "",
      "setCurrent": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `idDispRuleCreIns` | Teamcenter::Soa::Core::_2020_01::DataManagement::IDDispRuleCreateIn[] | A list of objects of type IdDispRuleCreateIn. The data on IdDispRuleCreateIn is used to create the <b>IdContextRule</b>  |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.24.2 getIdContexts

**接口路径：** `Core-2020-01-DataManagement/getIdContexts`

**API 版本：** `2020-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 fetches all instances of the ID Context objects (IdContext) from the Teamcenter database applicable for the input objects of type Item and ItemRevision based on defined ID Context Rules (IdContextRule) by the system administrators. 此操作 queries ID Context Rule objects and fetches the ID Context objects based on the input Item, ItemRevision or null. T…

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.DataManagement.getIdContexts`

**请求（input）：**

```json
{
  "inputObjs": [
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
| `inputObjs` | Teamcenter::WorkspaceObject[] | A list of objects of type <b>WorkspaceObject</b> or null for which the objects of type <b>IdContext</b> are fetched. |

**响应（output）：**

```json
{
  "idContextOuts": [
    {
      "inputObj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "idContexts": [
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
| `idContextOuts` | Teamcenter::Soa::Core::_2020_01::DataManagement::IDContextOut[] | A list of IdContextOut structures which holds the list of <b>IdContext</b> objects and input object of type <b>Workspace |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any partial errors encountered during this operation are returned in the list of partial errors of the ServiceData. |

---

##### 2.1.24.3 getIdentifierTypes

**接口路径：** `Core-2020-01-DataManagement/getIdentifierTypes`

**API 版本：** `2020-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 fetches the applicable Identifier types for the input objects of type Item and/or ItemRevision along with the input IdContext object. System queries the ID Context Rules defined in Teamcenter database and retrives the Identifier types. Alternate and Alias IDs are defined in Teamcenter as instances of 业务对象 of type Identifier. ID Context, of business …

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.DataManagement.getIdentifierTypes`

**请求（input）：**

```json
{
  "identifierTypesIn": [
    {
      "inputItemOrRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "idContext": {
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
| `identifierTypesIn` | Teamcenter::Soa::Core::_2020_01::DataManagement::IdentifierTypesIn[] | A list of objects of type IdentifierTypesIn. The data on IdentifierTypesIn is used to query <b>Identifer</b> type based  |

**响应（output）：**

```json
{
  "identifiersOutput": [
    {
      "inputItemOrRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "identifierTypes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "item": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revisions": [
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
| `identifiersOutput` | Teamcenter::Soa::Core::_2020_01::DataManagement::IdentifiersOut[] | A list of IdentifiersOut structures which holds list of <b>Identifier</b> types, object of type <b>Item</b> and list of  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any partial errors encountered during this operation are returned in the list of partial errors of the ServiceData. |

---

#### 版本 2020-04

##### 2.1.25.1 generateContextSpecificIDs2

**接口路径：** `Core-2020-04-DataManagement/generateContextSpecificIDs2`

**API 版本：** `2020-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `generateContextSpecificIDs2`。Generates the range of unique IDs for input context names. The number of IDs generated for each context name depends on the input. If for a given context name, the ID has been reset using Teamcenter service resetContextID, then this service generates IDs for that context from the beginning. ID generation will also reset when the maximum limit is met. This limit is maximum nu…

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_04.DataManagement.generateContextSpecificIDs2`

**请求（input）：**

```json
{
  "generateContextIDsIn": [
    {
      "clientID": "",
      "contextName": "",
      "contextTypeName": "",
      "contextPropName": "",
      "validateIDs": "",
      "numberOfIDs": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `generateContextIDsIn` | Teamcenter::Soa::Core::_2020_04::DataManagement::GenerateContextIDsInput2[] | A list of GenerateContextIDsInput2 which contains the context name, type, property name, validation flag, and number of  |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "generatedContextIDValues": [
    {
      "contextName": "",
      "generatedIDs": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Partial Errors are returned in the ServiceData when service generateContextSpecificIDs fails to generate IDs of any of t |
| `generatedContextIDValues` | Teamcenter::Soa::Core::_2016_05::DataManagement::GeneratedContextIDs[] | A list of GeneratedContextIDs, which contains each of the context names and IDs generated for it by service generateCont |

---

#### 版本 2021-06

##### 2.1.26.1 addNamedReferenceToDatasets

**接口路径：** `Core-2021-06-DataManagement/addNamedReferenceToDatasets`

**API 版本：** `2021-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 adds a list of named references to the input 数据集. Operation adds only existing named reference objects and does not create new named reference. 此操作 can optionally create a new version of an input 数据集.

**Soa Inclusion：** `Teamcenter.Soa.Core._2021_06.DataManagement.addNamedReferenceToDatasets`

**请求（input）：**

```json
{
  "addNamedReferenceIn": [
    {
      "clientID": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "nrInfo": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "namedReferenceName": "",
          "referenceType": ""
        }
      ],
      "createNewDatasetVersion": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `addNamedReferenceIn` | Teamcenter::Soa::Core::_2021_06::DataManagement::AddNamedReferenceToDatasetInfo[] | A list of AddNamedReferenceToDatasetInfo which contains <b>Dataset</b> objects and the named references to be added to t |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.26.2 removeNamedReferenceFromDataset2

**接口路径：** `Core-2021-06-DataManagement/removeNamedReferenceFromDataset2`

**API 版本：** `2021-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 removes the specified named references from a 数据集.If the NamedReferenceInfo.targetObject input is specified and matched then only that named reference is removed from the 数据集. The NamedReferenceInfo.targetObject input is not matched with any named references in the 数据集 instance then no named reference is removed. If the NamedReferenceInfo.deleteTar…

**Soa Inclusion：** `Teamcenter.Soa.Core._2021_06.DataManagement.removeNamedReferenceFromDataset2`

**请求（input）：**

```json
{
  "removeNamedReferenceIn": [
    {
      "clientID": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "nrInfo": [
        {
          "clientId": "",
          "type": "",
          "targetObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "deleteTarget": ""
        }
      ],
      "createNewDatasetVersion": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `removeNamedReferenceIn` | Teamcenter::Soa::Core::_2021_06::DataManagement::RemoveNamedReferenceFromDataset[] | A list of RemoveNamedReferenceFromDataset which contains <b>Dataset</b> objects and the named references to be removed f |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2023-06

##### 2.1.27.1 createObjects

**接口路径：** `Core-2023-06-DataManagement/createObjects`

**API 版本：** `2023-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 按类型批量创建业务对象（通用创建接口）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_06.DataManagement.createObjects`

**请求（input）：**

```json
{
  "createInputs": [
    {
      "clientId": "",
      "data": {
        "boName": "",
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
  ],
  "runInBackground": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `createInputs` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateIn[] | A list of CreateIn objects each one of which represents the CreateInput information used to create an object. Each Creat |
| `runInBackground` | bool | If true, the operation is performed in background mode in a separate asynchronous server session; otherwise, perform the |

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOut[] | Vector of output objects representing objects that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data including partial errors that are mapped to the client id from the input. Created objects are also added to |

---

#### 版本 2023-12

##### 2.1.28.1 changeOwner2

**接口路径：** `Core-2023-12-DataManagement/changeOwner2`

**API 版本：** `2023-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 can be used to change the ownership on a given 业务对象 to the given user and group. Owning user attribute on the 业务对象 will be changed to the given user and owning group attribute is changed to the given group. The user needs CHANGE_OWNER privilege and WRITE privilege on the 业务对象 to be able to change its ownership. If user does not…

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_12.DataManagement.changeOwner2`

**请求（input）：**

```json
{
  "objectsAndOwnersInput": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "owner": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "group": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "relatedObjectsIncluded": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objectsAndOwnersInput` | Teamcenter::Soa::Core::_2006_03::DataManagement::ObjectOwner[] | The set of objects to transfer ownership of and user objects to which ownership is to be transferred. |
| `relatedObjectsIncluded` | bool | If &ldquo;true&rdquo;, only the input objects are considered for change ownership. If &ldquo;false&rdquo;, server traver |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.1.28.2 generateNextValuesForProperties2

**接口路径：** `Core-2023-12-DataManagement/generateNextValuesForProperties2`

**API 版本：** `2023-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates values for specific 属性 of an object or objects during the Create/Revise/SaveAs action. The values are determined based on user exits, ID generation rules, naming rules and revision naming rules that have been configured for these 属性. When both customer user exits and naming rules are configured for the same 属性, the customer user…

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_12.DataManagement.generateNextValuesForProperties2`

**请求（input）：**

```json
{
  "propertyNextValueInputs": [
    {
      "clientID": "",
      "operationType": "",
      "businessObjectTypeName": "",
      "boReference": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyInputList": [
        {
          "propertyName": "",
          "pattern": "",
          "context": [
            ""
          ],
          "quantity": ""
        }
      ],
      "propertyValuesMap": {},
      "additionalInputMap": {},
      "compoundObjectInput": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `propertyNextValueInputs` | Teamcenter::Soa::Core::_2023_12::DataManagement::PropertyNextValueInput[] | A list of PropertyNextValueInput objects which actually holds essential information like clientId, operation type, busin |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "generatedValues": [
    {
      "clientId": "",
      "generatedValues": {},
      "generatedValuesOfSecondaryObjects": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | The Service Data with partial errors for each PropertyNextValueInput and identified by its clientId. |
| `generatedValues` | Teamcenter::Soa::Core::_2023_12::DataManagement::PropertyNextValueOutput[] | A list of PropertyNextValueOutput one for each entry in PropertyNextValueInput input list and identified by its clientId |

---

##### 2.1.28.3 getNRPatterns

**接口路径：** `Core-2023-12-DataManagement/getNRPatterns`

**API 版本：** `2023-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 the list of Patterns with counters and without counters along with preferred patterns and conditions for the Naming Rule attached to the 属性 of an object Type. The Type name and the 属性 name are passed in the input structure. The input for 此操作 contains a list of this structure. The return structure contains patterns, preferredPatte…

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_12.DataManagement.getNRPatterns`

**请求（input）：**

```json
{
  "attachInfos": [
    {
      "typeName": "",
      "propName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `attachInfos` | Teamcenter::Soa::Core::_2008_06::DataManagement::NRAttachInfo[] | A list of  type  and property names. |

**响应（output）：**

```json
{
  "patterns": [
    {
      "patternStrings": [
        ""
      ]
    }
  ],
  "preferredPattern": [
    ""
  ],
  "condition": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `patterns` | Teamcenter::Soa::Core::_2023_12::DataManagement::Patterns[] | A list of naming rule patterns. |
| `preferredPattern` | std::string[] | A list of preferred naming rule patterns. |
| `condition` | std::string[] | A list of conditions in naming rule attachments. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData structure. It contains partial errors and failures along with the clientIds. |

---

##### 2.1.28.4 getRelatedObjects

**接口路径：** `Core-2023-12-DataManagement/getRelatedObjects`

**API 版本：** `2023-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 获取 the related objects of input BusinessObject objects as determined by the preference: &lt;TypeName&gt;_defaultChild属性.

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_12.DataManagement.getRelatedObjects`

**请求（input）：**

```json
{
  "inputObjects": [
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
| `inputObjects` | Teamcenter::BusinessObject[] | A list of objects whose related objects are needed. |

**响应（output）：**

```json
{
  "parentChildMap": {},
  "treeNodes": [
    {
      "identifier": "",
      "displayName": "",
      "parentIdentifier": "",
      "isPreselected": "",
      "isSelectable": "",
      "relationType": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `parentChildMap` | Teamcenter::Soa::Core::_2023_12::DataManagement::ParentChildMap | A map (string, string) which holds parent node's UIDs vs children node's UIDs. Parent node UIDs are the ones sent in the |
| `treeNodes` | Teamcenter::Soa::Core::_2023_12::DataManagement::TreeNode[] | A list of information about individual child tree nodes. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data for the operation. |

---

#### 版本 2024-06

##### 2.1.29.1 queryForFileExistence

**接口路径：** `Core-2024-06-DataManagement/queryForFileExistence`

**API 版本：** `2024-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 takes a source object, a list of files, and relation types as input. It filters 数据集 objects associated with the source object based on the specified relations. 该操作 then searches these filtered 数据集 objects to determine if any files from the input list exist within them. If one or more files are found, the corresponding 数据集 objects are retu…

**Soa Inclusion：** `Teamcenter.Soa.Core._2024_06.DataManagement.queryForFileExistence`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "fileNames": [
        ""
      ],
      "relationNames": [
        ""
      ],
      "parentObject": {
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
| `input` | Teamcenter::Soa::Core::_2024_06::DataManagement::DatasetsForFileRelationInput[] | A list of <i>DatasetsForFileRelationInput</i> objects containing references to the input data. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "datasetsForFile": [
        {
          "fileName": "",
          "dataset": {
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
| `output` | Teamcenter::Soa::Core::_2024_06::DataManagement::DatasetsForFileOutput[] | A list of <i>DatasetsForFileOutput</i>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data object associated with the operation. |

---

#### 版本 2025-06

##### 2.1.30.1 getLocalizedProperties3

**接口路径：** `Core-2025-06-DataManagement/getLocalizedProperties3`

**API 版本：** `2025-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** The getLocalized属性3 operation enables retrieval of 属性 values in any supported locale on the Teamcenter server. For string-type 属性 that support localization, it provides translated values for specified locales. 此操作 also 返回 the internal status of localized values and read-access status for the 属性. If the user lacks read access, the…

**Soa Inclusion：** `Teamcenter.Soa.Core._2025_06.DataManagement.getLocalizedProperties3`

**请求（input）：**

```json
{
  "propertyInfo": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propsToget": [
        {
          "name": "",
          "locales": [
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
| `propertyInfo` | Teamcenter::Soa::Core::_2010_04::DataManagement::PropertyInfo[] | A list of <font face="courier" height="10">propertyInfo</font> objects which actually holds desired business objects, pr |

**响应（output）：**

```json
{
  "output": [
    {
      "businessObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyValues": [
        {
          "name": "",
          "values": [
            ""
          ],
          "locale": "",
          "seqNum": "",
          "status": [
            ""
          ],
          "internalStatus": [
            ""
          ],
          "statusDesc": [
            ""
          ],
          "master": "",
          "hasReadAccess": ""
        }
      ]
    }
  ],
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2025_06::DataManagement::LocalizedPropertyValuesInfo3[] | A list of  <font face="courier" height="10">LocalizedPropertyValuesInfo3</font> to store the localized property values i |
| `data` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">Service Data</font> with partial errors for each <font face="courier" height="10">P |

---

### 2.2 数字签名（DigitalSignature）

**涵盖 API 版本：** `2014-06`  
**操作数：** 3

#### 版本 2014-06

##### 2.2.1.1 applySignatures

**接口路径：** `Core-2014-06-DigitalSignature/applySignatures`

**API 版本：** `2014-06`  
**Service：** `DigitalSignature`  
**Library：** `Core`

**说明：** 此操作 applies digital signature to a list of 业务对象 provided in the input. 该操作 input is a list of DigitalSignatureInput structures. Each structure in this list consists of details pertaining to the 业务对象 and its corresponding CMS (Cryptographic Message Syntax). Digital Signature is allowed to be applied on 业务对象 for which the…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.DigitalSignature.applySignatures`

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
      "encryptedString": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2014_06::DigitalSignature::ApplySignaturesInputData[] | A list of DigitalSignatureInput structures containing the business object and its corresponding CMS ( Cryptographic Mess |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.2.1.2 getSignatureMessages

**接口路径：** `Core-2014-06-DigitalSignature/getSignatureMessages`

**API 版本：** `2014-06`  
**Service：** `DigitalSignature`  
**Library：** `Core`

**说明：** 此操作 返回 signature messages for a list of 业务对象. These signature messages are used by SOA framework method com.Teamcenter.soa.client.PKCS7.sign API to generate CMS string (Cryptographic Message Syntax). 该操作 response 获取ignatureMessagesResponse contains details of signature messages computed for each of the input 业务对象 along with…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.DigitalSignature.getSignatureMessages`

**请求（input）：**

```json
{
  "targetObject": [
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
| `targetObject` | Teamcenter::BusinessObject[] | A list of business objects for which signature messages need to be computed. |

**响应（output）：**

```json
{
  "output": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "message": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2014_06::DigitalSignature::GetSignatureMessagesOutput[] | List of getSignatureMessagesOuput structures.  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData Containing list of partial errors and details of business objects for which signature message computation wa |

---

##### 2.2.1.3 voidSignatures

**接口路径：** `Core-2014-06-DigitalSignature/voidSignatures`

**API 版本：** `2014-06`  
**Service：** `DigitalSignature`  
**Library：** `Core`

**说明：** 此操作 voids the selected digital signatureson a given target object.. The details of the electronic signature may be obtained by calling the requisite SOA framework method com.Teamcenter.soa.client.PKCS7.sign. ..This is provided as input to the voidDigitalSignatures opearation along with the other inputs. Successful completion of 该操作, is an indication that…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.DigitalSignature.voidSignatures`

**请求（input）：**

```json
{
  "input": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "signatureobject": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "comment": ""
    }
  ],
  "electronicSignature": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2014_06::DigitalSignature::VoidSignaturesInputData[] | This structure contains input parameters required for voidSignatures operation. |
| `electronicSignature` | std::string | An electronic signature that will be used to validate that the person requesting the void operation is the one who logge |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.3 调度管理（DispatcherManagement）

**涵盖 API 版本：** `2008-06`  
**操作数：** 1

#### 版本 2008-06

##### 2.3.1.1 createDispatcherRequest

**接口路径：** `Core-2008-06-DispatcherManagement/createDispatcherRequest`

**API 版本：** `2008-06`  
**Service：** `DispatcherManagement`  
**Library：** `Core`

**说明：** 调度管理（DispatcherManagement）：创建Dispatcher Request。Create a DispatcherRequest within Teamcenter for use with Dispatcher Management Services.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DispatcherManagement.createDispatcherRequest`

**请求（input）：**

```json
{
  "inputs": [
    {
      "providerName": "",
      "serviceName": "",
      "type": "",
      "primaryObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "secondaryObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "priority": "",
      "startTime": "",
      "endTime": "",
      "interval": "",
      "keyValueArgs": [
        {
          "key": "",
          "value": ""
        }
      ],
      "dataFiles": [
        {
          "key": "",
          "file": {
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
| `inputs` | Teamcenter::Soa::Core::_2008_06::DispatcherManagement::CreateDispatcherRequestArgs[] | holds the values needed to create the <b>DispatcherRequest</b>. |

**响应（output）：**

```json
{
  "requestsCreated": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `requestsCreated` | Teamcenter::BusinessObject[] | The Dispatcher Request objects created. |
| `svcData` | Teamcenter::Soa::Server::ServiceData | The SOA Service Data. |

---

### 2.4 信封（Envelope）

**涵盖 API 版本：** `2011-06`  
**操作数：** 1

#### 版本 2011-06

##### 2.4.1.1 sendAndDeleteEnvelopes

**接口路径：** `Core-2011-06-Envelope/sendAndDeleteEnvelopes`

**API 版本：** `2011-06`  
**Service：** `Envelope`  
**Library：** `Core`

**说明：** 此操作 sends mails to the recipients of each Envelope 业务对象 in envelopes. All the envelopes passed to 此操作 are deleted after they are processed, even if the processing is not successful. Each Envelope 业务对象 contains mail information such as subject, body, recipients, and attachments. Recipients can be Teamcenter users, groups and address…

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Envelope.sendAndDeleteEnvelopes`

**请求（input）：**

```json
{
  "envelopes": [
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
| `envelopes` | Teamcenter::Envelope[] | The list of <b>Envelope</b> business objects to be sent. |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.5 文件管理（FileManagement）

**涵盖 API 版本：** `2006-03`、`2007-01`、`2015-10`、`2017-05`  
**操作数：** 8

#### 版本 2006-03

##### 2.5.1.1 commitDatasetFiles

**接口路径：** `Core-2006-03-FileManagement/commitDatasetFiles`

**API 版本：** `2006-03`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 将已上传至 FMS 的文件提交并关联到数据集。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.FileManagement.commitDatasetFiles`

**请求（input）：**

```json
{
  "commitInput": [
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
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `commitInput` | Teamcenter::Soa::Core::_2006_03::FileManagement::CommitDatasetFileInfo[] | The vector of <font face=&quot;courier&quot; height=&quot;10&quot;>CommitDatasetFileInfo</font> structures returned in t |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.5.1.2 getDatasetWriteTickets

**接口路径：** `Core-2006-03-FileManagement/getDatasetWriteTickets`

**API 版本：** `2006-03`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 此操作 obtains File Management System (FMS) write tickets and file storage information for a set of supplied 数据集 objects. The write tickets are used to transfer files from a local storage to Teamcenter volume, and the file storage information can be used to commit 数据集 objects referencing those transferred files. The caller will provide a vector of Get数据集W…

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.FileManagement.getDatasetWriteTickets`

**请求（input）：**

```json
{
  "inputs": [
    {
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "createNewVersion": "",
      "datasetFileInfos": [
        {
          "clientId": "",
          "fileName": "",
          "namedReferencedName": "",
          "isText": "",
          "allowReplace": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2006_03::FileManagement::GetDatasetWriteTicketsInputData[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>GetDatasetWriteTicketsInputData</font> structures which |

**响应（output）：**

```json
{
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
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `commitInfo` | Teamcenter::Soa::Core::_2006_03::FileManagement::CommitDatasetFileInfo[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>CommitDatasetFileInfo</font> structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Teamcenter Services structure used to return status of the operation.  Any errors that occurred during the operation |

---

##### 2.5.1.3 getFileReadTickets

**接口路径：** `Core-2006-03-FileManagement/getFileReadTickets`

**API 版本：** `2006-03`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 此操作 obtains File Management System (FMS) read tickets for a set of supplied ImanFile objects. The supplied tickets are used to transfer files from a Teamcenter volume to local storage. The files input parameter contains a list of the ImanFile objects to be read from the Teamcenter volume and transferred to local storage. FMS requires tickets for all file transfers…

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.FileManagement.getFileReadTickets`

**请求（input）：**

```json
{
  "files": [
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
| `files` | Teamcenter::ImanFile[] | A vector of <b>ImanFile</b> objects to be transferred from a<br />Teamcenter volume to local storage.  The calling clien |

**响应（output）：**

```json
{
  "tickets": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `tickets` | Teamcenter::Soa::Core::_2006_03::FileManagement::TicketMap | A map of the input <b>ImanFile</b> objects to FMS tickets used to access files in the Teamcenter volume. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Teamcenter Services structure used to return status of the operation.  Any errors that occurred during the operation |

---

#### 版本 2007-01

##### 2.5.2.1 getTransientFileTicketsForUpload

**接口路径：** `Core-2007-01-FileManagement/getTransientFileTicketsForUpload`

**API 版本：** `2007-01`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 此操作 获取 the tickets for the desired files to be uploaded to the transient volume. These tickets can be used to upload corresponding files via FileManagementUtility::putFileViaTicket. The TransientFileInfo contains the basic information for a file to be uploaded such as file name, file type and whether the file should be deleted after reading.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.FileManagement.getTransientFileTicketsForUpload`

**请求（input）：**

```json
{
  "transientFileInfos": [
    {
      "fileName": "",
      "isBinary": "",
      "deleteFlag": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `transientFileInfos` | Teamcenter::Soa::Core::_2007_01::FileManagement::TransientFileInfo[] | List containing the details of the files for which the tickets are requested. |

**响应（output）：**

```json
{
  "transientFileTicketInfos": [
    {
      "transientFileInfo": {
        "fileName": "",
        "isBinary": "",
        "deleteFlag": ""
      },
      "ticket": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `transientFileTicketInfos` | Teamcenter::Soa::Core::_2007_01::FileManagement::TransientFileTicketInfo[] | The requested transient files ticket information. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This contains the status of the operation. |

---

#### 版本 2015-10

##### 2.5.3.1 getDigestInfoForDatasets

**接口路径：** `Core-2015-10-FileManagement/getDigestInfoForDatasets`

**API 版本：** `2015-10`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 获取 the file digest information for the ImanFile objects contained in the 数据集 objects. These digests can be used by clients to check for file integrity. Clients must use the same digest algorithm (as returned by 此操作) to compute the digest on their end and compare with the digest returned by 此操作. The Teamcenter File Management System (FMS) computes …

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.FileManagement.getDigestInfoForDatasets`

**请求（input）：**

```json
{
  "datasets": [
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
| `datasets` | Teamcenter::Dataset[] | the <b>Dataset</b> objects for which the digest information is to be obtained for each of the <b>ImanFile</b> objects in |

**响应（output）：**

```json
{
  "datasetDigestInfo": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `datasetDigestInfo` | Teamcenter::Soa::Core::_2015_10::FileManagement::DatasetDigestInfoMap | A list of DatasetDigestInfos objects. It contains the digest information for each file referenced by each of the input d |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData response that can contain the partial errors. |

---

##### 2.5.3.2 getDigestInfoForFiles

**接口路径：** `Core-2015-10-FileManagement/getDigestInfoForFiles`

**API 版本：** `2015-10`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 获取 the file digest information for all the ImanFile objects specified using files. These digests can be used by clients to check for file integrity. Clients must use the same digest algorithm (as returned by 此操作) to compute the digest on their end and compare with the digest returned by 此操作. The Teamcenter File Management System (FMS) computes and sto…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.FileManagement.getDigestInfoForFiles`

**请求（input）：**

```json
{
  "files": [
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
| `files` | Teamcenter::ImanFile[] | The <b>ImanFile</b> objects for which the digest information is to be obtained. |

**响应（output）：**

```json
{
  "fileDigestInfo": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `fileDigestInfo` | Teamcenter::Soa::Core::_2015_10::FileManagement::FileDigestInfoMap | A map (<b>ImanFile</b>, list of DigestInfo) of input <b>ImanFile</b> objects to the digest informationa for the file. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData response that can contain the partial errors. |

---

#### 版本 2017-05

##### 2.5.4.1 commitDatasetFilesInBulk

**接口路径：** `Core-2017-05-FileManagement/commitDatasetFilesInBulk`

**API 版本：** `2017-05`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 此操作 up加载 files to a Teamcenter volume and associates them to a 数据集. The mechanism for a 客户端应用 adding files to a Teamcenter volume contains several steps. This mechanism is implemented in the com.Teamcenter.soa.client.FileManagementUtility class, which provides this functionality to clients in a consistent, reusable package. 此操作 is su…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.FileManagement.commitDatasetFilesInBulk`

**请求（input）：**

```json
{
  "commitInput": [
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
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `commitInput` | Teamcenter::Soa::Core::_2006_03::FileManagement::CommitDatasetFileInfo[] | The list of CommitDatasetFileInfo structures returned in the commitInfo element of the GetDatasetWriteTicketsResponse st |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.5.4.2 replaceFiles

**接口路径：** `Core-2017-05-FileManagement/replaceFiles`

**API 版本：** `2017-05`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 此操作 replaces an existing volume file with a new file that has already been uploaded to a transient volume. It up加载 the file from the transient volume to the regular Teamcenter volume. The original volume file is replaced with the new file, and the ImanFile references the new file. Note that there is no new ImanFile object created. 此操作 includes the ab…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.FileManagement.replaceFiles`

**请求（input）：**

```json
{
  "inputs": [
    {
      "imanFile": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newFileTicket": "",
      "retainOriginalFileName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2017_05::FileManagement::ReplaceFileInput[] | The input to this operation includes a list of write tickets used to upload the new file to the transient volume.  It al |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.6 值列表（LOV）

**涵盖 API 版本：** `2007-06`、`2011-06`、`2013-05`、`2021-12`  
**操作数：** 6

#### 版本 2007-06

##### 2.6.1.1 getAttachedLOVs

**接口路径：** `Core-2007-06-LOV/getAttachedLOVs`

**API 版本：** `2007-06`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 值列表（LOV）：获取Attached L O Vs。Get attached LOV based on input type name and 属性 names structure. The LOV Tag is returned in the response and service data.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.LOV.getAttachedLOVs`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2007_06::LOV::LOVInfo[] | - vector of structure of LOVInfo with type name and property names vector. |

**响应（output）：**

```json
{
  "inputTypeNameToLOVOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputTypeNameToLOVOutput` | Teamcenter::Soa::Core::_2007_06::LOV::InputTypeNameToLOVOutputMap | Map of input type name to LOVOutput |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData which has output tags as plain objects and errors in partialError |

---

#### 版本 2011-06

##### 2.6.2.1 getLOVAttachments

**接口路径：** `Core-2011-06-LOV/getLOVAttachments`

**API 版本：** `2011-06`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 返回 valid LOV attachments for the 属性 of each object passed in as input. It may return LOV or null based on condition validations. If none of the conditions evaluated to be True, then no LOV attachment is returned for the 属性 of an instance.

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.LOV.getLOVAttachments`

**请求（input）：**

```json
{
  "objectStructArray": [
    {
      "objects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "properties": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objectStructArray` | Teamcenter::Soa::Core::_2011_06::LOV::LOVAttachmentsInput[] | LOV attachments are evaluated for each property of the structure LOVAttachmentsInut based on each object in <font face=& |

**响应（output）：**

```json
{
  "lovAttachments": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `lovAttachments` | Teamcenter::Soa::Core::_2011_06::LOV::InpoutObjectToLOVAttachmentsMap | A list of objects and its properties and associated LOV attachments. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data. |

---

#### 版本 2013-05

##### 2.6.3.1 getInitialLOVValues

**接口路径：** `Core-2013-05-LOV/getInitialLOVValues`

**API 版本：** `2013-05`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 此操作 is invoked to query the data for a 属性 having an LOV attachment. The results returned from the server also take into consideration any filter string that is in the input. 此操作 返回 both LOV meta data as necessary for the client to render the LOV and partial LOV values list as specified. 该操作 will return the results in the LOVSearchRe…

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.LOV.getInitialLOVValues`

**请求（input）：**

```json
{
  "initialData": {
    "lov": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "lovInput": {
      "owningObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "boName": "",
      "operationName": "",
      "propertyValues": {}
    },
    "propertyName": "",
    "filterData": {
      "filterString": "",
      "maxResults": "",
      "numberToReturn": "",
      "sortPropertyName": "",
      "order": ""
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `initialData` | Teamcenter::Soa::Core::_2013_05::LOV::InitialLovData | Input data to get LOV results for any LOV |

**响应（output）：**

```json
{
  "lovValues": [
    {
      "uid": "",
      "propInternalValues": {},
      "propInternalValueTypes": {},
      "propDisplayValues": {},
      "childRows": []
    }
  ],
  "moreValuesExist": "",
  "behaviorData": {
    "lovUsage": "",
    "style": "",
    "columnNames": {
      "lovValueProp": "",
      "lovDescrProp": "",
      "filterProperties": [
        ""
      ],
      "displayNames": {},
      "columnManagementFlags": {}
    },
    "descriptionsAttached": [],
    "dependendProps": [
      ""
    ],
    "rangeUpperLimit": "",
    "rangeLowerLimit": ""
  },
  "lovData": {
    "style": "",
    "filterData": {
      "filterString": "",
      "maxResults": "",
      "numberToReturn": "",
      "sortPropertyName": "",
      "order": ""
    },
    "unProcessedObjects": [
      ""
    ],
    "additionalValuesSkipped": "",
    "currentIndex": "",
    "lovs": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `lovValues` | Teamcenter::Soa::Core::_2013_05::LOV::LOVValueRow[] | This is a list of LOVValueRow objects. Each LOVValueRow object represents a single row of the LOV results. It includes t |
| `moreValuesExist` | bool | true indicates there are more values available which will can be retrieved by a call to the getNextValues operation |
| `behaviorData` | Teamcenter::Soa::Core::_2013_05::LOV::LOVBehaviorData | LOV data used to define the UI component behavior. This includes data such as LOV usage, Style, Lov Column Names. Additi |
| `lovData` | Teamcenter::Soa::Core::_2013_05::LOV::LOVData | If moreValuesExist is true, this object is passed as input to the getNextValues operation to get the next list of LOV se |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData |

---

##### 2.6.3.2 getNextLOVValues

**接口路径：** `Core-2013-05-LOV/getNextLOVValues`

**API 版本：** `2013-05`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 此操作 is invoked after a call to getInitialLOVValues if the moreValuesExist flag is true in the LOVSearchResults output returned from a call to the getInitialLOVValues operation. 该操作 will retrieve the next set of LOV values

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.LOV.getNextLOVValues`

**请求（input）：**

```json
{
  "lovData": {
    "style": "",
    "filterData": {
      "filterString": "",
      "maxResults": "",
      "numberToReturn": "",
      "sortPropertyName": "",
      "order": ""
    },
    "unProcessedObjects": [
      ""
    ],
    "additionalValuesSkipped": "",
    "currentIndex": "",
    "lovs": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `lovData` | Teamcenter::Soa::Core::_2013_05::LOV::LOVData | Input data to get next set of LOV results for Dynamic LOV. This is returned as part of the LOVSearchResults output from  |

**响应（output）：**

```json
{
  "lovValues": [
    {
      "uid": "",
      "propInternalValues": {},
      "propInternalValueTypes": {},
      "propDisplayValues": {},
      "childRows": []
    }
  ],
  "moreValuesExist": "",
  "behaviorData": {
    "lovUsage": "",
    "style": "",
    "columnNames": {
      "lovValueProp": "",
      "lovDescrProp": "",
      "filterProperties": [
        ""
      ],
      "displayNames": {},
      "columnManagementFlags": {}
    },
    "descriptionsAttached": [],
    "dependendProps": [
      ""
    ],
    "rangeUpperLimit": "",
    "rangeLowerLimit": ""
  },
  "lovData": {
    "style": "",
    "filterData": {
      "filterString": "",
      "maxResults": "",
      "numberToReturn": "",
      "sortPropertyName": "",
      "order": ""
    },
    "unProcessedObjects": [
      ""
    ],
    "additionalValuesSkipped": "",
    "currentIndex": "",
    "lovs": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `lovValues` | Teamcenter::Soa::Core::_2013_05::LOV::LOVValueRow[] | This is a list of LOVValueRow objects. Each LOVValueRow object represents a single row of the LOV results. It includes t |
| `moreValuesExist` | bool | true indicates there are more values available which will can be retrieved by a call to the getNextValues operation |
| `behaviorData` | Teamcenter::Soa::Core::_2013_05::LOV::LOVBehaviorData | LOV data used to define the UI component behavior. This includes data such as LOV usage, Style, Lov Column Names. Additi |
| `lovData` | Teamcenter::Soa::Core::_2013_05::LOV::LOVData | If moreValuesExist is true, this object is passed as input to the getNextValues operation to get the next list of LOV se |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData |

---

##### 2.6.3.3 validateLOVValueSelections

**接口路径：** `Core-2013-05-LOV/validateLOVValueSelections`

**API 版本：** `2013-05`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 此操作 can be invoked after selecting a value from the LOV. Use 此操作 to do additional validation to be done on server such as validating Range value, getting the dependent 属性 values in case of interdependent LOV (resetting the dependendent 属性 values), Coordinated LOVs ( populating dependent 属性 values )

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.LOV.validateLOVValueSelections`

**请求（input）：**

```json
{
  "lovInput": {
    "owningObject": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "boName": "",
    "operationName": "",
    "propertyValues": {}
  },
  "propName": "",
  "uidOfSelectedRows": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `lovInput` | Teamcenter::Soa::Core::_2013_05::LOV::LOVInput | updated LOV input with new selection |
| `propName` | std::string | It is the name of the Property for which LOV is being evaluated |
| `uidOfSelectedRows` | std::string[] | Pass the uids from the selected rows. Every LovValueRow returned from server is designated with valid UID for dynamic LO |

**响应（output）：**

```json
{
  "propHasValidValues": "",
  "dependentPropNames": [
    ""
  ],
  "updatedPropValues": {
    "uid": "",
    "propInternalValues": {},
    "propInternalValueTypes": {},
    "propDisplayValues": {},
    "childRows": []
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `propHasValidValues` | bool | Indicates whether input property has valid values. |
| `dependentPropNames` | std::string[] | Names of dependent properties server modified to be updated by client as a results of dependency with input property sel |
| `updatedPropValues` | Teamcenter::Soa::Core::_2013_05::LOV::LOVValueRow | Updated property values. It contains both internal and display values of the updated properties.  It can be empty. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The service data. |

---

#### 版本 2021-12

##### 2.6.4.1 validatePropertyValuesForLOVInBulk

**接口路径：** `Core-2021-12-LOV/validatePropertyValuesForLOVInBulk`

**API 版本：** `2021-12`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 此操作 validates the input 属性 against the LOV defination. The validate属性ValuesForLOVInBulk operation is used to validate input 属性 values before invoking service operations like creating objects, save as objects or revise objects etc. All of the input 属性 names and their values should be included in 属性ValuesMap.

**Soa Inclusion：** `Teamcenter.Soa.Core._2021_12.LOV.validatePropertyValuesForLOVInBulk`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientID": "",
      "owningObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "boName": "",
      "operationName": "",
      "propNames": [
        ""
      ],
      "propValues": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2021_12::LOV::ValidatePropertyValuesForLOVInBulkInputData[] | A list of <i>ValidatePropertyValuesForLOVInBulkInputData</i> objects containing LOV property values to be evaluated. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientID": "",
      "validateLOVPropertyOutput": [
        {
          "propName": "",
          "propHasValidValues": "",
          "dependentPropNames": [
            ""
          ],
          "updatedPropValues": {
            "uid": "",
            "propInternalValues": {},
            "propInternalValueTypes": {},
            "propDisplayValues": {},
            "childRows": []
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
| `output` | Teamcenter::Soa::Core::_2021_12::LOV::ValidatePropertyValuesForLOVInBulkOutput[] | A list containing the clientID and list of <i>ValidatePropertyValuesForLOVInBulkOutput</i>. For each input, one <i>Valid |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data object associated with the operation. |

---

### 2.7 语言信息（LanguageInformation）

**涵盖 API 版本：** `2010-04`  
**操作数：** 2

#### 版本 2010-04

##### 2.7.1.1 getAllTranslationStatuses

**接口路径：** `Core-2010-04-LanguageInformation/getAllTranslationStatuses`

**API 版本：** `2010-04`  
**Service：** `LanguageInformation`  
**Library：** `Core`

**说明：** 语言信息（LanguageInformation）：获取All Translation Statuses。Retrieves the full set of translation statuses: their enumeration, localized name and description. Currently, the translation statuses in the Teamcenter system includes: "Master", "Approved", "Pending", "In-Review", and "Invalid"

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.LanguageInformation.getAllTranslationStatuses`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "fullTranslationStatuses": [
    {
      "status": "TranslationStatusMaster",
      "statusName": "",
      "statusDescription": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `fullTranslationStatuses` | Teamcenter::Soa::Core::_2010_04::LanguageInformation::FullTranslationStatus[] | List of all the full translation statuses |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">ServiceData</font>. |

---

##### 2.7.1.2 getLanguagesList

**接口路径：** `Core-2010-04-LanguageInformation/getLanguagesList`

**API 版本：** `2010-04`  
**Service：** `LanguageInformation`  
**Library：** `Core`

**说明：** 语言信息（LanguageInformation）：获取Languages List。Retrieves a list of languages according to different scenarios as specified in the input parameter. All the returned language names are in the Java-standard format.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.LanguageInformation.getLanguagesList`

**请求（input）：**

```json
{
  "scenario": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `scenario` | std::string | Defines the type of languages list that will be returned. <br />Valid values are (case sensitive): <br /><ul><ul><li typ |

**响应（output）：**

```json
{
  "languageList": [
    {
      "languageCode": "",
      "languageName": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `languageList` | Teamcenter::Soa::Core::_2010_04::LanguageInformation::Language[] | An ordered list of languages |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any partial errors that may occur when filling this request |

---

### 2.8 逻辑对象（LogicalObject）

**涵盖 API 版本：** `2017-11`、`2018-06`、`2018-11`  
**操作数：** 3

#### 版本 2017-11

##### 2.8.1.1 getLogicalObjects

**接口路径：** `Core-2017-11-LogicalObject/getLogicalObjects`

**API 版本：** `2017-11`  
**Service：** `LogicalObject`  
**Library：** `Core`

**说明：** 此操作 返回 the logical object instances for the input list of root object instances and logical object type names. 此操作 can also return classification objects [ A classification object is also called an ICO], if the root obejct or a member object is configured on the logical object type for retieving classification data. For such usecases it also return…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_11.LogicalObject.getLogicalObjects`

**请求（input）：**

```json
{
  "loInputs": [
    {
      "rootObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "loTypeName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `loInputs` | Teamcenter::Soa::Core::_2017_11::LogicalObject::GetLogicalObjectInput[] | A list of the root object instances and logical object type names to retrieve the logical object instances. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "loOutputs": [
    {
      "logicalObjects": [
        {
          "root": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "logicalObjectInstances": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "memberClassificationObjects": [
            {
              "memberOrRootName": "",
              "icoIDs": [
                ""
              ]
            }
          ]
        }
      ]
    }
  ],
  "classificationAttributeDesc": {},
  "classificationObjectInfo": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Returned service data. |
| `loOutputs` | Teamcenter::Soa::Core::_2017_11::LogicalObject::GetLogicalObjectOutput[] | A list of the retrieved logical object output response corresponding to a  logical object input. |
| `classificationAttributeDesc` | Teamcenter::Soa::Core::_2017_11::LogicalObject::ClassificationAttributeDescMap | A map of classification objects and a list of references to their attribute descriptors. |
| `classificationObjectInfo` | Teamcenter::Soa::Core::_2017_11::LogicalObject::ClassificationObjectInfoMap | A map of the ICO ids and their class attribute info. |

---

#### 版本 2018-06

##### 2.8.2.1 getLogicalObjects2

**接口路径：** `Core-2018-06-LogicalObject/getLogicalObjects2`

**API 版本：** `2018-06`  
**Service：** `LogicalObject`  
**Library：** `Core`

**说明：** 此操作 返回 the logical object instances for the input list of root object instances and logical object type names. 此操作 can also return classification objects (A classification object is also called an ICO), if the root obejct or a member object is configured on the logical object type for retieving classification data. For such use cases it also return…

**Soa Inclusion：** `Teamcenter.Soa.Core._2018_06.LogicalObject.getLogicalObjects2`

**请求（input）：**

```json
{
  "loInputs": [
    {
      "rootObjects": [
        {
          "root": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "clientID": ""
        }
      ],
      "loTypeName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `loInputs` | Teamcenter::Soa::Core::_2018_06::LogicalObject::GetLogicalObjectInput2[] | A list of the root object instances and logical object type names to retrieve the logical object instances. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "loOutputs": [
    {
      "logicalObjectsOutput": [
        {
          "root": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "logicalObjectInstances": [
            {
              "loInstance": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "memberClassificationObjects": [
                {
                  "memberOrRootName": "",
                  "icoIDs": [
                    ""
                  ]
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "classificationObjectInfo": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Returned service data. |
| `loOutputs` | Teamcenter::Soa::Core::_2018_06::LogicalObject::GetLogicalObjectOutput2[] | A list of the retrieved logical object output response corresponding to a  logical object input. |
| `classificationObjectInfo` | Teamcenter::Soa::Core::_2018_06::LogicalObject::ClassificationObjectInfoMap2 | A map (string, classificationObjectInfo) of the <b>ICO</b> Ids and their class attribute info. |

---

#### 版本 2018-11

##### 2.8.3.1 getLogicalObjectsWithContext

**接口路径：** `Core-2018-11-LogicalObject/getLogicalObjectsWithContext`

**API 版本：** `2018-11`  
**Service：** `LogicalObject`  
**Library：** `Core`

**说明：** 此操作 返回 the logical object instances for the input list of client id and root object instance pairs, logical object type names and a map containing the included logical object ID, or member ID and configuration context UID. 此操作 can also return classification objects [A classification object is also called an ICO], if the root object or a member obje…

**Soa Inclusion：** `Teamcenter.Soa.Core._2018_11.LogicalObject.getLogicalObjectsWithContext`

**请求（input）：**

```json
{
  "loInputs": [
    {
      "rootInstances": [
        {
          "root": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "clientID": ""
        }
      ],
      "loTypeName": "",
      "loQueryNameValues": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `loInputs` | Teamcenter::Soa::Core::_2018_11::LogicalObject::GetLogicalObjectInput3[] | A list of the root object instances, logical object type names and a map containing the logical object ID and configurat |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "loOutputs": [
    {
      "logicalObjectsOutput": [
        {
          "root": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "logicalObjectInstances": [
            {
              "loInstance": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "memberClassificationObjects": [
                {
                  "memberOrRootName": "",
                  "icoIDs": [
                    ""
                  ]
                }
              ],
              "includedLOInstances": {}
            }
          ]
        }
      ]
    }
  ],
  "classificationObjectInfo": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Returned service data. |
| `loOutputs` | Teamcenter::Soa::Core::_2018_11::LogicalObject::GetLogicalObjectOutput3[] | A list of the retrieved logical object output response corresponding to a  logical object input. |
| `classificationObjectInfo` | Teamcenter::Soa::Core::_2018_11::LogicalObject::ClassificationObjectInfoMap3 | A map(string, ClassificationObjectInfo)  of the ICO IDs and their classification object info. |

---

### 2.9 托管关系（ManagedRelations）

**涵盖 API 版本：** `2007-01`、`2008-06`  
**操作数：** 4

#### 版本 2007-01

##### 2.9.1.1 createRelation

**接口路径：** `Core-2007-01-ManagedRelations/createRelation`

**API 版本：** `2007-01`  
**Service：** `ManagedRelations`  
**Library：** `Core`

**说明：** 此操作 will create new managed relation

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.ManagedRelations.createRelation`

**请求（input）：**

```json
{
  "relationinfo": [
    {
      "name": "",
      "type": "",
      "primaryTagList": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "secondaryTagList": [
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
| `relationinfo` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::CreateManagedRelationInput[] | input information required to create managed relation |

**响应（output）：**

```json
{
  "managedRelationObjects": [
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
| `managedRelationObjects` | Teamcenter::TraceLink[] | List of Managed Relation Objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |

---

##### 2.9.1.2 getTraceReport

**接口路径：** `Core-2007-01-ManagedRelations/getTraceReport`

**API 版本：** `2007-01`  
**Service：** `ManagedRelations`  
**Library：** `Core`

**说明：** 此操作 will create traceability report for the selected TC object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.ManagedRelations.getTraceReport`

**请求（input）：**

```json
{
  "input": {
    "inputTag": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "reportType": "",
    "reportDepth": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::TraceabilityInfoInput | information required to create report |

**响应（output）：**

```json
{
  "definingTree": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "children": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "indirectDefiningTree": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "children": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "complyingTree": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "children": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "indirectComplyingTree": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "children": [
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
| `definingTree` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::DefiningReport[] | List of Defining Reports |
| `indirectDefiningTree` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::DefiningReport[] | List of Defining Reports (Indirect) |
| `complyingTree` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::ComplyingReport[] | List of Complying Reports |
| `indirectComplyingTree` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::ComplyingReport[] | List of Complying Reports (Indirect) |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |

---

##### 2.9.1.3 modifyRelation

**接口路径：** `Core-2007-01-ManagedRelations/modifyRelation`

**API 版本：** `2007-01`  
**Service：** `ManagedRelations`  
**Library：** `Core`

**说明：** 此操作 will Edit the managed relation

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.ManagedRelations.modifyRelation`

**请求（input）：**

```json
{
  "newInput": [
    {
      "relationTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "setSourcesInput": {
        "addSources": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "removeSources": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      },
      "setTargetsInput": {
        "addTargets": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "removeTargets": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `newInput` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::ModifyManagedRelationInput[] | will have the modification info for given relation |

**响应（output）：**

```json
{
  "managedRelationObjects": [
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
| `managedRelationObjects` | Teamcenter::TraceLink[] | List of Managed Relation Objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |

---

#### 版本 2008-06

##### 2.9.2.1 getManagedRelations

**接口路径：** `Core-2008-06-ManagedRelations/getManagedRelations`

**API 版本：** `2008-06`  
**Service：** `ManagedRelations`  
**Library：** `Core`

**说明：** 此操作 will return tracelinks between primary and secondary objects

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.ManagedRelations.getManagedRelations`

**请求（input）：**

```json
{
  "inputdata": {
    "primaryTags": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "secondaryTags": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "primaryType": "",
    "subtype": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputdata` | Teamcenter::Soa::Core::_2008_06::ManagedRelations::GetManagedRelationInput | information required to get tracelink relations |

**响应（output）：**

```json
{
  "managedRelations": [
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
| `managedRelations` | Teamcenter::WorkspaceObject[] | Tracelink relations |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |

---

### 2.10 操作描述符（OperationDescriptor）

**涵盖 API 版本：** `2011-06`、`2012-02`  
**操作数：** 2

#### 版本 2011-06

##### 2.10.1.1 getSaveAsDesc

**接口路径：** `Core-2011-06-OperationDescriptor/getSaveAsDesc`

**API 版本：** `2011-06`  
**Service：** `OperationDescriptor`  
**Library：** `Core`

**说明：** 此操作 返回 information required to save a 业务对象. The SaveAsDescriptor includes the metadata information for the 属性 required when saving a 业务对象, i.e., the 属性 is mandatory, the 属性 is visible, if value is to be copied from original object, etc. The SaveAsDescriptor also includes the DeepCopyData which is a recursive data stru…

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.OperationDescriptor.getSaveAsDesc`

**请求（input）：**

```json
{
  "targetObjects": [
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
| `targetObjects` | Teamcenter::BusinessObject[] | Set of objects for which the SaveAs Descriptor is needed. |

**响应（output）：**

```json
{
  "saveAsDescMap": {},
  "deepCopyInfoMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `saveAsDescMap` | Teamcenter::Soa::Core::_2011_06::OperationDescriptor::SaveAsDescMap | A map of business object types and SaveAs Descriptors (string/SaveAsDesc).  This is the container of metadata for SaveAs |
| `deepCopyInfoMap` | Teamcenter::Soa::Core::_2011_06::OperationDescriptor::DeepCopyInfoMap | A map of business objects and <font face=&quot;courier&quot; height=&quot;10&quot;>DeepCopyData</font> (business object/ |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing errors, etc. The plain object list of the Service data is populated with the target objects whic |

---

#### 版本 2012-02

##### 2.10.2.1 getDeepCopyData

**接口路径：** `Core-2012-02-OperationDescriptor/getDeepCopyData`

**API 版本：** `2012-02`  
**Service：** `OperationDescriptor`  
**Library：** `Core`

**说明：** 获取深拷贝所需的数据结构。

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.OperationDescriptor.getDeepCopyData`

**请求（input）：**

```json
{
  "deepCopyDataInput": [
    {
      "operation": "",
      "object": {
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
| `deepCopyDataInput` | Teamcenter::Soa::Core::_2012_02::OperationDescriptor::DeepCopyDataInput[] | A list of DeepCopyDataInput structures which contains an object, and operation type. |

**响应（output）：**

```json
{
  "deepCopyInfoMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `deepCopyInfoMap` | Teamcenter::Soa::Core::_2012_02::OperationDescriptor::DeepCopyInfoMap2 | Map of the DeepCopy data |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Creates a list of Datasets and creates the specified relation type between created Dataset and input container object. |

---

### 2.11 项目级安全（ProjectLevelSecurity）

**涵盖 API 版本：** `2007-09`、`2009-04`、`2009-10`、`2012-09`、`2014-10`、`2016-10`、`2017-05`、`2018-11`、`2020-01`  
**操作数：** 23

#### 版本 2007-09

##### 2.11.1.1 assignOrRemoveObjects

**接口路径：** `Core-2007-09-ProjectLevelSecurity/assignOrRemoveObjects`

**API 版本：** `2007-09`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 assigns the given set of workspace objects to the given projects. Similarly, it removes an additional set of given workspace objects from the same set of given projects. If user is not privileged to assign objects to any of the given projects then 此操作 will return the error 101014 : You have insufficient privilege to assign object to a project. Simil…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_09.ProjectLevelSecurity.assignOrRemoveObjects`

**请求（input）：**

```json
{
  "assignedOrRemovedobjects": [
    {
      "projects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "objectToAssign": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "objectToRemove": [
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
| `assignedOrRemovedobjects` | Teamcenter::Soa::Core::_2007_09::ProjectLevelSecurity::AssignedOrRemovedObjects[] | A list of AssignedOrRemovedObjects. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2009-04

##### 2.11.2.1 loadProjectDataForUser

**接口路径：** `Core-2009-04-ProjectLevelSecurity/loadProjectDataForUser`

**API 版本：** `2009-04`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 list of projects for a given user, group and role combination. If no group and role is specified it obtains all the projects for the specified user. If any of the arguments passed are invalid an error is returned by 该操作 added as a partial error.

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_04.ProjectLevelSecurity.loadProjectDataForUser`

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
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> object. |
| `group` | Teamcenter::Group | The <b>Group</b> object in which the user belongs to. |
| `role` | Teamcenter::Role | The <b>Role</b> object in which the user belongs to. |

**响应（output）：**

```json
{
  "applicableProjects": [
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
| `applicableProjects` | Teamcenter::TC_Project[] | List of <b>TC_project</b> objects found. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | A  standard  ServicData. |

---

#### 版本 2009-10

##### 2.11.3.1 getUserProjects

**接口路径：** `Core-2009-10-ProjectLevelSecurity/getUserProjects`

**API 版本：** `2009-10`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 the list of TC_Project objects for each of the users in the input structure based on the additional criteria like active projects only, user privileged projects only and programs only. The output for 此操作 is a UserProjectsInfoResponse structure.

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_10.ProjectLevelSecurity.getUserProjects`

**请求（input）：**

```json
{
  "userProjectsInfoInputs": [
    {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "activeProjectsOnly": "",
      "privilegedProjectsOnly": "",
      "programsOnly": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `userProjectsInfoInputs` | Teamcenter::Soa::Core::_2009_10::ProjectLevelSecurity::UserProjectsInfoInput[] | A list of UserProjectsInfoInput structures. |

**响应（output）：**

```json
{
  "userProjectInfos": [
    {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "activeProjectsOnly": "",
      "privilegedProjectsOnly": "",
      "programsOnly": "",
      "clientId": "",
      "projectsInfo": [
        {
          "project": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isUserPrivileged": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `userProjectInfos` | Teamcenter::Soa::Core::_2009_10::ProjectLevelSecurity::UserProjectsInfo[] | List of UserProjectsInfo structures one for each given user.. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | A  standard ServiceData. |

---

#### 版本 2012-09

##### 2.11.4.1 copyProjects

**接口路径：** `Core-2012-09-ProjectLevelSecurity/copyProjects`

**API 版本：** `2012-09`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 copies the given list of TC_Project objects. 该操作 also copies any information which is in contained in the project. Data such as project team members and any objects assigned to the source project will also be copied to the new project. If a project with given project ID exists in the system then 此操作 will return error 101010. 该操作 …

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_09.ProjectLevelSecurity.copyProjects`

**请求（input）：**

```json
{
  "copyProjectsInfos": [
    {
      "sourceProject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "projectInfo": {
        "projectId": "",
        "projectName": "",
        "projectDescription": "",
        "useProgramContext": "",
        "active": "",
        "visible": "",
        "teamMembers": [
          {
            "teamMember": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "teamMemberType": ""
          }
        ],
        "clientId": ""
      },
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `copyProjectsInfos` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::CopyProjectsInfo[] | A list of CopyProjectsInfo structures. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

##### 2.11.4.2 createProjects

**接口路径：** `Core-2012-09-ProjectLevelSecurity/createProjects`

**API 版本：** `2012-09`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 创建 TC_Project objects using the given input information. If the project with given project ID exists in the system then 此操作 will return unique id violation error 101010. However, creation of rest of the projects will continue.

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_09.ProjectLevelSecurity.createProjects`

**请求（input）：**

```json
{
  "projectInfos": [
    {
      "projectId": "",
      "projectName": "",
      "projectDescription": "",
      "useProgramContext": "",
      "active": "",
      "visible": "",
      "teamMembers": [
        {
          "teamMember": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "teamMemberType": ""
        }
      ],
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectInfos` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectInformation[] | A list of ProjectInformation objects. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

##### 2.11.4.3 getProjectTeams

**接口路径：** `Core-2012-09-ProjectLevelSecurity/getProjectTeams`

**API 版本：** `2012-09`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 team members for the given list of TC_Project objects.

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_09.ProjectLevelSecurity.getProjectTeams`

**请求（input）：**

```json
{
  "projectObjs": [
    {
      "tcProject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectObjs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectClientId[] |   A list of ProjectClientId structures one for each of the given projects. |

**响应（output）：**

```json
{
  "projectTeams": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "regularMembers": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "projectTeamAdmins": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "privMembers": [
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
| `projectTeams` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectTeamData[] | List of ProjectTeamData objects one for each of the given projects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | A standard ServiceData object. |

---

##### 2.11.4.4 modifyProjects

**接口路径：** `Core-2012-09-ProjectLevelSecurity/modifyProjects`

**API 版本：** `2012-09`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 modifies the given list of TC_Project objects using the input specified. The input contains new values for all the project 属性. Values for 属性 other than the project team are ignored unless the user is the Project Administrator. The entire Project Team, with the exception of the Project Administrator, is replaced with the specified team. Therefor…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_09.ProjectLevelSecurity.modifyProjects`

**请求（input）：**

```json
{
  "modifyProjectsInfos": [
    {
      "sourceProject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "projectInfo": {
        "projectId": "",
        "projectName": "",
        "projectDescription": "",
        "useProgramContext": "",
        "active": "",
        "visible": "",
        "teamMembers": [
          {
            "teamMember": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "teamMemberType": ""
          }
        ],
        "clientId": ""
      },
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `modifyProjectsInfos` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ModifyProjectsInfo[] | Vector of ModifyProjectsInfo structures. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

#### 版本 2014-10

##### 2.11.5.1 propagateData

**接口路径：** `Core-2014-10-ProjectLevelSecurity/propagateData`

**API 版本：** `2014-10`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 can propagate security or anyother Teamcenter data based on the source object and applicable propagation rules. The propagateData operation should only be invoked when propagation rule is configured to run in background. The propagation rule defined in BMIDE states what data from source to desination object has to be propagated.For example project_list, licens…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.ProjectLevelSecurity.propagateData`

**请求（input）：**

```json
{
  "propagateDataElements": [
    {
      "operationType": "",
      "sourceObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propagationRulesInfo": [
        {
          "applicablePropagationRules": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "associatedObject": {
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
| `propagateDataElements` | Teamcenter::Soa::Core::_2014_10::ProjectLevelSecurity::PropagateDataElement[] | A list  the source object, operation type and the applicable propagation rules  that define the data to be propagated. |

**响应（output）：**

```json
"void"
```

---

#### 版本 2016-10

##### 2.11.6.1 getDefaultProject

**接口路径：** `Core-2016-10-ProjectLevelSecurity/getDefaultProject`

**API 版本：** `2016-10`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 a list of the default projects for a given user, group and role combination. If no user is specified, it looks for the default project of the current logged in user. If no group and role is specified, all default projects for the specified user are returned. When TC_show_all_user_projects is set to TRUE, projects are reteturned regardless of the given …

**Soa Inclusion：** `Teamcenter.Soa.Core._2016_10.ProjectLevelSecurity.getDefaultProject`

**请求（input）：**

```json
{
  "tcUser": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "tcGroup": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "tcRole": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `tcUser` | Teamcenter::User | The <b>User</b> object. |
| `tcGroup` | Teamcenter::Group | The <b>Group</b> object in which the user belongs to. |
| `tcRole` | Teamcenter::Role | The <b>Role</b> object in which the user belongs to. |

**响应（output）：**

```json
{
  "applicableProjects": [
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
| `applicableProjects` | Teamcenter::TC_Project[] | List of <b>TC_project</b> objects found. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | A  standard  ServicData. |

---

#### 版本 2017-05

##### 2.11.7.1 assignOrRemoveObjectsFromProjects

**接口路径：** `Core-2017-05-ProjectLevelSecurity/assignOrRemoveObjectsFromProjects`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 assigns the given set of workspace objects to the given projects. Similarly, it removes an additional set of given workspace objects from the same set of given projects. If the input contains revision rule and or variant rule these will be applied to the given set of objects for traversing the structure i.e. the project will be propagated to the objects which …

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.assignOrRemoveObjectsFromProjects`

**请求（input）：**

```json
{
  "assignOrRemoveInput": [
    {
      "projectsToAssign": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "objectsForAssignment": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "projectsForRemoval": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "objectsToRemoveFromProjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "contextInfo": {
        "selectedTopLevelObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "variantRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revisionRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "typeOption": "",
        "depth": ""
      },
      "processAsynchronously": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `assignOrRemoveInput` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ProjectAssignOrRemoveInput[] | The list of ProjectAssignOrRemoveInput structure. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.11.7.2 copyProjects2

**接口路径：** `Core-2017-05-ProjectLevelSecurity/copyProjects2`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 copies the given list of TC_Project objects. 该操作 also copies any information which is in contained in the project. Data such as project team members and any objects assigned to the source project will also be copied to the new project. If a project with given project ID exists in the system then 此操作 will return error 101010. 该操作 …

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.copyProjects2`

**请求（input）：**

```json
{
  "copyProjectInfos": [
    {
      "sourceProject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "projectInfo": {
        "projectId": "",
        "projectName": "",
        "projectDescription": "",
        "useProgramContext": "",
        "active": "",
        "visible": "",
        "teamMembers": [
          {
            "teamMember": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "teamMemberType": ""
          }
        ],
        "clientId": "",
        "propertyMap": {}
      },
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `copyProjectInfos` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::CopyProjectsInfo2[] | List of CopyProjectsInfo2 structure. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

##### 2.11.7.3 createProjects2

**接口路径：** `Core-2017-05-ProjectLevelSecurity/createProjects2`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 创建 TC_Project objects using the given input information. 此操作 also supports creation of TC_Project object in hierarchical configuration. If the project with given project ID exists in the system then 此操作 will return unique id violation error 101010. However, creation of rest of the projects will continue.

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.createProjects2`

**请求（input）：**

```json
{
  "projectInfos": [
    {
      "projectId": "",
      "projectName": "",
      "projectDescription": "",
      "useProgramContext": "",
      "active": "",
      "visible": "",
      "teamMembers": [
        {
          "teamMember": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "teamMemberType": ""
        }
      ],
      "clientId": "",
      "propertyMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectInfos` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ProjectInformation2[] | A list of ProjectInformation2 objects. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

##### 2.11.7.4 getProjectsForAssignOrRemove

**接口路径：** `Core-2017-05-ProjectLevelSecurity/getProjectsForAssignOrRemove`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 retrieves the assigned projects to the input data and all available projects where the input user is a priveleged member. When multiple 业务对象 are selected 此操作 retrieves the assigned projects which are in common for the complete input data. It also retrieves level or structure information in case of ActiveWorkspace Content context. In Acti…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.getProjectsForAssignOrRemove`

**请求（input）：**

```json
{
  "projectsInput": [
    {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "selectedObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "assignedObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "paginationInfo": {
        "startIndexForAvailableProjects": "",
        "maxToReturnForAvailableProjects": ""
      },
      "filterText": "",
      "isAceContext": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectsInput` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ProjectsInput[] | A list of ProjectsInput objects. |

**响应（output）：**

```json
{
  "projectOutput": {
    "assignedProjectsList": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "selectedObjects": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "serviceData": "IServiceData",
  "availableProjectList": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "projectOptions": {},
  "totalFound": "",
  "totalLoaded": "",
  "endIndex": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOutput` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ProjectsOutput | A list of projectsOutput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and er |
| `availableProjectList` | Teamcenter::TC_Project[] | A list of available TC_Project objects sorted in  alphabetical order. |
| `projectOptions` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ProjectOptions | A map(string, list of ConfigurationContextChoice) of ActiveWorkspace Content context attributes with the list of ActiveW |
| `totalFound` | int | The total number of projects found. |
| `totalLoaded` | int | The total number of projects loaded. |
| `endIndex` | int | The end index to return the projects. |

---

##### 2.11.7.5 modifyProjects2

**接口路径：** `Core-2017-05-ProjectLevelSecurity/modifyProjects2`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 modifies the given list of TC_Project objects using the input specified. The input contains new values for all the project 属性. Values for 属性 other than the project team are ignored unless the user is the Project Administrator. The entire Project Team, with the exception of the Project Administrator, is replaced with the specified team. Therefor…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.modifyProjects2`

**请求（input）：**

```json
{
  "modifyProjectsInfos": [
    {
      "sourceProject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "projectInfo": {
        "projectId": "",
        "projectName": "",
        "projectDescription": "",
        "useProgramContext": "",
        "active": "",
        "visible": "",
        "teamMembers": [
          {
            "teamMember": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "teamMemberType": ""
          }
        ],
        "clientId": "",
        "propertyMap": {}
      },
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `modifyProjectsInfos` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ModifyProjectsInfo2[] | List of ModifyProjectsInfo2 structures. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

##### 2.11.7.6 setPropagationEnabledProperties

**接口路径：** `Core-2017-05-ProjectLevelSecurity/setPropagationEnabledProperties`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 该操作 设置 propagation enabled 属性 on a given set of objects and performs propagation. This will be done either in the same 会话 or a different 会话 depending on the dispatcher configuration. If dispatcher is configured and the SOA URL is set correctly in organization application then the request will be processed asynchronously. On the otherhand if disp…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.setPropagationEnabledProperties`

**请求（input）：**

```json
{
  "propagationDataInput": [
    {
      "assignOrAttachData": [
        {
          "selectedObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "selectedProjectsOrLicenses": [
            ""
          ],
          "eadParagraph": [
            ""
          ],
          "propertyName": ""
        }
      ],
      "removeOrDetachData": [
        {
          "selectedObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "selectedProjectsOrLicenses": [
            ""
          ],
          "eadParagraph": [
            ""
          ],
          "propertyName": ""
        }
      ],
      "propertyDataToSetAndPropagate": [
        {
          "selectedObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "propertyName": "",
          "newPropertyValues": [
            ""
          ]
        }
      ],
      "configInfo": {
        "selectedTopLevelObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "variantRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revisionRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "typeOption": "",
        "depth": ""
      },
      "reconstructConfigurationInfo": {
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
        "bomView": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "objectsForConfigure": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "revRuleConfigInfo": {
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
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `propagationDataInput` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::PropagationDataInput[] | The list of PropagationDataInput structure. |

**响应（output）：**

```json
"void"
```

---

#### 版本 2018-11

##### 2.11.8.1 changeOwningProgram

**接口路径：** `Core-2018-11-ProjectLevelSecurity/changeOwningProgram`

**API 版本：** `2018-11`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 changes the owning program of the given set of objects. Owning Program (owning_project attribute ) is changed to the new value passed in.

**Soa Inclusion：** `Teamcenter.Soa.Core._2018_11.ProjectLevelSecurity.changeOwningProgram`

**请求（input）：**

```json
{
  "chgOwnProgramInput": [
    {
      "owningProgram": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "inputObjects": [
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
| `chgOwnProgramInput` | Teamcenter::Soa::Core::_2018_11::ProjectLevelSecurity::ChangeOwningProgramInput2[] | The list of ChangeOwningProgramInput2 structure. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.11.8.2 getUserProjects2

**接口路径：** `Core-2018-11-ProjectLevelSecurity/getUserProjects2`

**API 版本：** `2018-11`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 the list of TC_Project objects for the user, group, and role based on the additional criteria like active projects only, user privileged projects only and programs only.

**Soa Inclusion：** `Teamcenter.Soa.Core._2018_11.ProjectLevelSecurity.getUserProjects2`

**请求（input）：**

```json
{
  "userInfoList": [
    {
      "tcUser": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tcGroup": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tcRole": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "activeProjectsOnly": "",
  "visibleProjectsOnly": "",
  "privilegedProjectsOnly": "",
  "programsOnly": "",
  "programsAndTheChildProjects": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `userInfoList` | Teamcenter::Soa::Core::_2018_11::ProjectLevelSecurity::UserGroupRoleInfo[] | A list of <b>UserGroupRoleInfo</b> objects to query the <b>TC_Project</b> objects. If the <b>Group</b> or <b>Role</b> is |
| `activeProjectsOnly` | bool | If true, query only the active <b>TC_Project</b> objects. |
| `visibleProjectsOnly` | bool | If true, query only the visible <b>TC_Project</b> objects. |
| `privilegedProjectsOnly` | bool | If true, query only the <b>TC_Project</b> objects that the user is a privileged member of. |
| `programsOnly` | bool | If true, query only the <b>TC_Project</b> objects that are using &quot;Program Level Security&quot;. When true, paramete |
| `programsAndTheChildProjects` | bool | If true, query the <b>TC_Project</b> objects that are using &quot;Program Level Security&quot;, and their child projects |

**响应（output）：**

```json
{
  "userProjectList": [
    {
      "userGroupRole": {
        "tcUser": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "tcGroup": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "tcRole": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "projects": [
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
| `userProjectList` | Teamcenter::Soa::Core::_2018_11::ProjectLevelSecurity::UserProjects[] | A list of <b>UserProjects</b> structure. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData. |

---

#### 版本 2020-01

##### 2.11.9.1 addOrRemoveProjectMembers

**接口路径：** `Core-2020-01-ProjectLevelSecurity/addOrRemoveProjectMembers`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 项目级安全（ProjectLevelSecurity） 服务操作 `addOrRemoveProjectMembers`。Adds or removes GroupMember objects or Group objects to/from the ProjectTeam of the given TC_Project.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.addOrRemoveProjectMembers`

**请求（input）：**

```json
{
  "inputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "gms": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "groups": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "groupRoles": [
        {
          "tcGroup": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "tcRole": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isRemovable": ""
        }
      ],
      "addOrRemove": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::AddOrRemoveProjectMemberInput[] | A list of <b>AddOrRemoveProjectMemberInput</b> structures which consists of the <b>TC_Project</b> object to add or remov |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.11.9.2 getFirstLevelProjectTeamStructure

**接口路径：** `Core-2020-01-ProjectLevelSecurity/getFirstLevelProjectTeamStructure`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作s 返回 the paginated output of the first level nodes of the ProjectTeam for the given TC_Project object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.getFirstLevelProjectTeamStructure`

**请求（input）：**

```json
{
  "input": {
    "project": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "startIndex": "",
    "pageSize": "",
    "quickLoad": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::ProjectTeamPagedInput | The <b>TC_Project</b> and the pagination configuration to return <b>ProjectTeam</b> first level nodes and configuration  |

**响应（output）：**

```json
{
  "totalMemberCount": "",
  "endIndex": "",
  "groups": [
    {
      "tcGroup": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isRemovable": ""
    }
  ],
  "structuredGroupMembers": [
    {
      "tcGroup": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tcRole": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isRemovable": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `totalMemberCount` | int | The total number of the project members in the <b>ProjectTeam</b> of the given <b>TC_Project</b> object. |
| `endIndex` | int | The index of the last element returned for pagination. |
| `groups` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupNode[] | A list of <b>Group</b> objects that are in the project members of the input <b>TC_Project</b>. |
| `structuredGroupMembers` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupRoleNode[] | A list of structured <b>GroupRoleNode</b> which represents the first level node of the <b>GroupMember</b> objects in the |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data |

---

##### 2.11.9.3 getModifiableProjects

**接口路径：** `Core-2020-01-ProjectLevelSecurity/getModifiableProjects`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 the TC_Project objects that the login user can modify. The TC_Project objects in the response are based on the pagination input.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.getModifiableProjects`

**请求（input）：**

```json
{
  "startIndex": "",
  "pageSize": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `startIndex` | int | The start index for pagination. |
| `pageSize` | int | The size of a page. |

**响应（output）：**

```json
{
  "userProjects": [
    {
      "userGroupRole": {
        "tcUser": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "tcGroup": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "tcRole": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "totalProjectCount": "",
      "endIndex": "",
      "projects": [
        {
          "project": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "privilege": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `userProjects` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::UserProjectsAndPrivilege[] | The <b>Users</b> and their associated <b>TC_Projects</b>, along with the privilege status of each <b>User</b>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data. |

---

##### 2.11.9.4 getPrivilegeInProjects

**接口路径：** `Core-2020-01-ProjectLevelSecurity/getPrivilegeInProjects`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 the privilege of the current user in each TC_Project object in the input.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.getPrivilegeInProjects`

**请求（input）：**

```json
{
  "projects": [
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
| `projects` | Teamcenter::TC_Project[] | A list of <b>TC_Project</b> objects to check the current user's privilege. |

**响应（output）：**

```json
{
  "projectPrivilege": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "privilege": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectPrivilege` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::ProjectAndPrivilege[] | A list of <b>TC_Project</b> objects and the privileges of the login user in them. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data |

---

##### 2.11.9.5 getProjectTeamChildNodes

**接口路径：** `Core-2020-01-ProjectLevelSecurity/getProjectTeamChildNodes`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 该操作 返回 child nodes for the given Group node or a Role node in the ProjectTeam tree based on the given depth.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.getProjectTeamChildNodes`

**请求（input）：**

```json
{
  "project": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "node": {
    "tcGroup": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "tcRole": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "isRemovable": ""
  },
  "depth": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `project` | Teamcenter::TC_Project | The <b>TC_Project</b> object which associated with the <b>ProjectTeam</b> to load child nodes. |
| `node` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupRoleNode | The <b>Group</b> or <b>GroupRole</b> node to load the children.<br />If the <i>tcRole</i> field is NULL or empty, then l |
| `depth` | int | The depth of the tree to load children. |

**响应（output）：**

```json
{
  "childGroups": [
    {
      "groupNode": {
        "tcGroup": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isRemovable": ""
      },
      "childGroups": [
        {
          "tcGroup": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isRemovable": ""
        }
      ],
      "childRoles": [
        {
          "groupRole": {
            "tcGroup": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "tcRole": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "isRemovable": ""
          },
          "groupmemberList": [
            {
              "groupmember": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "privilege": "",
              "isRemovable": ""
            }
          ]
        }
      ]
    }
  ],
  "childRoles": [
    {
      "groupRole": {
        "tcGroup": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "tcRole": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isRemovable": ""
      },
      "groupmemberList": [
        {
          "groupmember": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "privilege": "",
          "isRemovable": ""
        }
      ]
    }
  ],
  "childGroupMembers": [
    {
      "groupmember": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "privilege": "",
      "isRemovable": ""
    }
  ],
  "childGroupMap": {},
  "sd": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `childGroups` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupNodeWithChildren[] | The child <b>Groups</b>. |
| `childRoles` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupRoleNodeWithChildren[] | The child <b>Roles</b>. |
| `childGroupMembers` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupMemberPrivilege[] | The child <b>GroupMembers</b>. |
| `childGroupMap` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupChildGroup | Map the <b>Group</b> objects to their child <b>Groups</b>. |
| `sd` | Teamcenter::Soa::Server::ServiceData | The Service Data. |

---

##### 2.11.9.6 setUserPrivilege

**接口路径：** `Core-2020-01-ProjectLevelSecurity/setUserPrivilege`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 项目级安全（ProjectLevelSecurity）：设置User Privilege。Set the privilege of the given User objects in ProjectTeam of the given TC_Project.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.setUserPrivilege`

**请求（input）：**

```json
{
  "inputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "users": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "groupNode": [
        {
          "tcGroup": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isRemovable": ""
        }
      ],
      "groupRoleNode": [
        {
          "tcGroup": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "tcRole": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isRemovable": ""
        }
      ],
      "privilegeStatus": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::SetPrivilegeForUserInput[] | A list of <b>SetPrivilegeForUserInput</b> structures. The structure holds the <b>TC_Project</b>, a list of <b>User</b> o |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.12 属性描述符（PropDescriptor）

**涵盖 API 版本：** `2007-06`、`2008-06`、`2011-06`  
**操作数：** 3

#### 版本 2007-06

##### 2.12.1.1 getAttachedPropDescs

**接口路径：** `Core-2007-06-PropDescriptor/getAttachedPropDescs`

**API 版本：** `2007-06`  
**Service：** `PropDescriptor`  
**Library：** `Core`

**说明：** Get the attached 属性 descriptor based on input type name and 属性 names structure.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.PropDescriptor.getAttachedPropDescs`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2007_06::PropDescriptor::PropDescInfo[] | - vector of structure of PropDescInfo with type name and property names vector. |

**响应（output）：**

```json
{
  "inputTypeNameToPropDescOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputTypeNameToPropDescOutput` | Teamcenter::Soa::Core::_2007_06::PropDescriptor::InputTypeNameToPropDescOutputMap | Map of input type name to PropertyDescriptor |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData which has output tags as plain objects and errors in partialError |

---

#### 版本 2008-06

##### 2.12.2.1 getCreateDesc

**接口路径：** `Core-2008-06-PropDescriptor/getCreateDesc`

**API 版本：** `2008-06`  
**Service：** `PropDescriptor`  
**Library：** `Core`

**说明：** 该操作 返回 information required to create a 业务对象. The Create Descriptor (CreateDesc object) includes the metadata information for the 属性 required when creating a 业务对象 i.e, 属性 is mandatory, 属性 is visible, etc. The CreateDesc is a recursive data structure. The CreateDesc object can also reference CreateDesc on secondary obje…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.PropDescriptor.getCreateDesc`

**请求（input）：**

```json
{
  "businessObjectTypeNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `businessObjectTypeNames` | std::string[] | list of business object names for which Create Descriptor is needed. |

**响应（output）：**

```json
{
  "createDescs": [
    {
      "businessObjectTypeName": "",
      "propDescs": [
        {
          "propName": "",
          "displayName": "",
          "isEnabled": "",
          "isModifiable": "",
          "attachedSpecifier": "",
          "maxLength": "",
          "interdependentProps": [
            ""
          ],
          "namingPatterns": [
            ""
          ],
          "defaultValue": "",
          "propValueType": "",
          "propType": "",
          "isDisplayable": "",
          "isArray": "",
          "maxNumElems": "",
          "lov": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isRequired": ""
        }
      ],
      "secondaryCreateDescs": {}
    }
  ],
  "srvData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `createDescs` | Teamcenter::Soa::Core::_2008_06::PropDescriptor::CreateDesc[] | List of <font face=&quot;courier&quot; height=&quot;10&quot;>Teamcenter::Soa::Core::_2008_06::PropDescriptor::CreateDesc |
| `srvData` | Teamcenter::Soa::Server::ServiceData | Service data containing partial errors. If there is any error in retrieving the Create Descriptor for any Business Objec |

---

#### 版本 2011-06

##### 2.12.3.1 getAttachedPropDescs2

**接口路径：** `Core-2011-06-PropDescriptor/getAttachedPropDescs2`

**API 版本：** `2011-06`  
**Service：** `PropDescriptor`  
**Library：** `Core`

**说明：** 返回 a list of 属性 Descriptors based on the input structure. The 属性 Descriptors contain the Display Name, Description and other information about the input 属性.

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.PropDescriptor.getAttachedPropDescs2`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2007_06::PropDescriptor::PropDescInfo[] | An input Type Name and a list of property names on the input type.  A Property Descriptor is returned for each Property  |

**响应（output）：**

```json
{
  "inputTypeNameToPropDescOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputTypeNameToPropDescOutput` | Teamcenter::Soa::Core::_2011_06::PropDescriptor::InputTypeNameToPropDescOutputMap2 | A map of property descriptor lists and the associated input type name. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data. |

---

### 2.13 预留（Reservation）

**涵盖 API 版本：** `2006-03`、`2008-06`、`2011-06`、`2014-06`  
**操作数：** 9

#### 版本 2006-03

##### 2.13.1.1 cancelCheckout

**接口路径：** `Core-2006-03-Reservation/cancelCheckout`

**API 版本：** `2006-03`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 取消检出并丢弃未保存更改。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Reservation.cancelCheckout`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of objects to be canceled for previously check-out. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.13.1.2 checkin

**接口路径：** `Core-2006-03-Reservation/checkin`

**API 版本：** `2006-03`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 签入已检出的业务对象。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Reservation.checkin`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] |  Set of previously checked-out valid business objects. (e.g. <b>Dataset</b>, <b>Item</b>, <b>ItemRevision</b> ) |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.13.1.3 checkout

**接口路径：** `Core-2006-03-Reservation/checkout`

**API 版本：** `2006-03`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 检出业务对象以进行编辑。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Reservation.checkout`

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
  "comment": "",
  "changeId": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of business objects to be checked out. |
| `comment` | std::string | A comment describing the reason for the check-out.  An empty string is allowed. |
| `changeId` | std::string | A string value to identify the change.  Empty string allowed. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.13.1.4 getReservationHistory

**接口路径：** `Core-2006-03-Reservation/getReservationHistory`

**API 版本：** `2006-03`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 获取 the reservation history for a set of 业务对象, such as 数据集, Item, ItemRevision and many other 业务对象 types. An object which has never been checked out will have a valid reservation history with an empty sequence of events.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Reservation.getReservationHistory`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of business objects to query for reservation history. |

**响应（output）：**

```json
{
  "histories": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "events": [
        {
          "dateTime": "",
          "user": "",
          "activity": "",
          "changeId": "",
          "comment": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `histories` | Teamcenter::Soa::Core::_2006_03::Reservation::ReservationHistory[] | Reservation history. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Objects which are queried successfully are added to the ServiceData plain list. |

---

#### 版本 2008-06

##### 2.13.2.1 transferCheckout

**接口路径：** `Core-2008-06-Reservation/transferCheckout`

**API 版本：** `2008-06`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 transfers the previously checked-out 业务对象 to the user given from input. 此操作 takes care of all complex business logic involved in transfer checked-out based on passed in objects. Each input object is verified that it is valid for transferring its checkout. 此操作 validates precondition defined per type in COTS object and site cust…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.Reservation.transferCheckout`

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
  "userId": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of the previously checked-out Teamcenter objects (e.g. <b>Dataset</b>, <b>Item</b>, <b>ItemRevision</b> ) to tran |
| `userId` | Teamcenter::User |  The Teamcenter user id to who checked-out has to be transferred to. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2011-06

##### 2.13.3.1 okToCheckout

**接口路径：** `Core-2011-06-Reservation/okToCheckout`

**API 版本：** `2011-06`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 determines whether or not the input objects may be checked out given the type of object, access rules, and current checkout state of the object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Reservation.okToCheckout`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | The list of objects which should be validated for Checkout. |

**响应（output）：**

```json
{
  "verdict": [],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `verdict` | bool[] | A list indicating if the input business object can be checked out. "<i>true</i>" indicates the object may be checked out |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains the partial errors for any objects for which the <font face="courier" height="10">okToCheckout</font> validatio |

---

#### 版本 2014-06

##### 2.13.4.1 bulkCancelCheckout

**接口路径：** `Core-2014-06-Reservation/bulkCancelCheckout`

**API 版本：** `2014-06`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 cancels a check-out for a set of previously checked-out 业务对象 in bulk. The objects will be restored to the pre-check-out state. Only one user can perform a cancel check-out transaction on the object if the user has enough privilege on the object. This action may be applied to remote checked-out objects, and will cancel the check-out and records the …

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.Reservation.bulkCancelCheckout`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of objects which are in the checked-out state.(e.g. Dataset, Item, ItemRevision ) |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.13.4.2 bulkCheckin

**接口路径：** `Core-2014-06-Reservation/bulkCheckin`

**API 版本：** `2014-06`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 checks-in a set of previously checked-out 业务对象 in bulk. 此操作 takes care of all complex business logic involved to check-in passed in 业务对象. Each input object is verified that it is locally owned, site owned, and not transferred to another user after the checkout was performed. 此操作 validates precondition defined per t…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.Reservation.bulkCheckin`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of objects which are in the checked-out state. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.13.4.3 bulkCheckout

**接口路径：** `Core-2014-06-Reservation/bulkCheckout`

**API 版本：** `2014-06`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 checks out a set of 业务对象 with given comment and, change identifier in bulk fashion. Only one user can perform a check-out transaction on the object. The user must have sufficient privilege on the object or the checkout will fail. 此操作 allows for remote check-out and records the check-out transaction event. In the case where the reservatio…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.Reservation.bulkCheckout`

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
  "comment": "",
  "changeId": "",
  "reservationType": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of business objects to be checked out. |
| `comment` | std::string | A comment describing the reason for the check-out. An empty string is allowed. |
| `changeId` | std::string | The ID of the change. Empty string allowed. |
| `reservationType` | int | Following two types of reservation are allowed.<br /><ul><ul><li type="disc">RES_EXCLUSIVE_RESERVE for checking out busi |

**响应（output）：**

```json
"IServiceData"
```

---

### 2.14 会话（Session）

**涵盖 API 版本：** `2006-03`、`2007-01`、`2007-06`、`2007-12`、`2008-03`、`2008-06`、`2009-04`、`2010-04`、`2011-06`、`2012-02`、`2015-10`、`2019-06`、`2021-12`、`2022-12`、`2023-12`  
**操作数：** 42

#### 版本 2006-03

##### 2.14.1.1 getAvailableServices

**接口路径：** `Core-2006-03-Session/getAvailableServices`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 返回 a list of services and service operations that this Teamcenter server instance supports. This is useful for 客户端应用s that expose different functionality based on the version of the Teamcenter server it is connecting to.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.getAvailableServices`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "serviceNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceNames` | std::string[] | List of available services |

---

##### 2.14.1.2 getGroupMembership

**接口路径：** `Core-2006-03-Session/getGroupMembership`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session）：获取Group Membership。Get the valid groups and roles for the current user.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.getGroupMembership`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "groupMembers": [
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
| `groupMembers` | Teamcenter::GroupMember[] | A list of all the valid <b>GroupMember</b> objects for the current session`s <b>User</b>.  A <b>GroupMember</b> holds id |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The plain list has all the <b>GroupMembers</b>, <b>Groups</b> and <b>Roles</b> for this <b>User</b> |

---

##### 2.14.1.3 getPreferences

**接口路径：** `Core-2006-03-Session/getPreferences`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取用户或站点偏好设置。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.getPreferences`

**请求（input）：**

```json
{
  "prefScope": "",
  "prefNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `prefScope` | std::string | The scope in which the preferences are to be searched,                     "all", "site", "user", "group", or "role". |
| `prefNames` | std::string[] | A vector of the names of the desired preferences. |

**响应（output）：**

```json
{
  "preferences": "IPreferences",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `preferences` | Teamcenter::Soa::Server::Preferences | The requested preference name/values. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any partial errors that may occur when filling this request. |

---

##### 2.14.1.4 getSessionGroupMember

**接口路径：** `Core-2006-03-Session/getSessionGroupMember`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** Get the Group and Role for the current 会话. The group and role are set at login, either to default values or as specified by the input arguments to the login operation. The group and role can be changed at any time throughout the 会话 through the set会话GroupMember or setUser会话State operations.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.getSessionGroupMember`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> object which represents the logged in user's, <b>Group</b>, and Role for the current session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> object is included in the plain list. |

---

##### 2.14.1.5 login

**接口路径：** `Core-2006-03-Session/login`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 验证用户凭据并初始化 Teamcenter 客户端会话；在四层架构下还会分配服务器实例。凭据无效时抛出 InvalidCredentialsException。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.login`

**请求（input）：**

```json
{
  "username": "",
  "password": "",
  "group": "",
  "role": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `username` | std::string | The user's Teamcenter user name. |
| `password` | std::string | The user's Teamcenter password. |
| `group` | std::string | The group ID for this session. If empty (""), the user's default group is assumed. |
| `role` | std::string | The role the user is performing in the group. If empty (""), the user's default role in the group is assumed. |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

##### 2.14.1.6 loginSSO

**接口路径：** `Core-2006-03-Session/loginSSO`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 通过单点登录（SSO）方式验证用户并初始化 Teamcenter 会话。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.loginSSO`

**请求（input）：**

```json
{
  "username": "",
  "ssoCredentials": "",
  "group": "",
  "role": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `username` | std::string | The user's Teamcenter username. |
| `ssoCredentials` | std::string | The user's Teamcenter SSO credentials. This should have been obtained from Teamcenter Security Services. |
| `group` | std::string | The group id for this session. If blank (""), the user's default group is assumed. |
| `role` | std::string | The role the user is performing in the group. If blank (""), the user's default role in the group is assumed. |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

##### 2.14.1.7 logout

**接口路径：** `Core-2006-03-Session/logout`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 注销当前 Teamcenter 会话并释放相关资源。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.logout`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.14.1.8 setPreferences

**接口路径：** `Core-2006-03-Session/setPreferences`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 设置用户或站点偏好设置。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.setPreferences`

**请求（input）：**

```json
{
  "settings": [
    {
      "prefScope": "",
      "prefName": "",
      "prefValues": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `settings` | Teamcenter::Soa::Core::_2006_03::Session::PrefSetting[] | vector of PrefSetting structures, which specify the scope, name, and value(s) for each of the preferences to be set. |

**响应（output）：**

```json
{
  "preferences": "IPreferences",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `preferences` | Teamcenter::Soa::Server::Preferences | The requested preference name/values. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any partial errors that may occur when filling this request. |

---

##### 2.14.1.9 setSessionGroupMember

**接口路径：** `Core-2006-03-Session/setSessionGroupMember`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** Set the Group and Role for the current 会话. The group and role are set at login, either to default values or as specified by the input arguments to the login operation. The group and role can be changed at any time throughout the 会话 through 此操作 or the setUser会话State operations. The get会话GroupMember will return the current group and roll.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.setSessionGroupMember`

**请求（input）：**

```json
{
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `groupMember` | Teamcenter::GroupMember | The desired <b>GroupMember</b> for the current session.  The <b>GroupMember</b> defines the <b>Group</b> and <b>Role</b> |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2007-01

##### 2.14.2.1 getPreferences

**接口路径：** `Core-2007-01-Session/getPreferences`

**API 版本：** `2007-01`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取用户或站点偏好设置。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.Session.getPreferences`

**请求（input）：**

```json
{
  "requestedPrefs": [
    {
      "scope": "",
      "names": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `requestedPrefs` | Teamcenter::Soa::Core::_2007_01::Session::ScopedPreferenceNames[] | vector of PrefSetting structures, which specify the scope name for each of the preferences to be set. |

**响应（output）：**

```json
{
  "preferences": [
    {
      "name": "",
      "scope": "",
      "values": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `preferences` | Teamcenter::Soa::Core::_2007_01::Session::ReturnedPreferences[] | List of Returned Preferences |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |

---

##### 2.14.2.2 getTCSessionInfo

**接口路径：** `Core-2007-01-Session/getTCSessionInfo`

**API 版本：** `2007-01`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取当前用户会话详细信息（用户、组、角色、站点、卷、项目、工作上下文等）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.Session.getTCSessionInfo`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "serverVersion": "",
  "transientVolRootDir": "",
  "site": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "bypass": "",
  "journaling": "",
  "appJournaling": "",
  "secJournaling": "",
  "admJournaling": "",
  "privileged": "",
  "isPartBOMUsageEnabled": "",
  "isSubscriptionMgrEnabled": "",
  "textInfos": [
    {
      "realName": "",
      "displayName": ""
    }
  ],
  "isInV7Mode": "",
  "extraInfo": {},
  "serviceData": "IServiceData",
  "moduleNumber": "",
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
  "tcVolume": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "project": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "workContext": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serverVersion` | std::string | The version of the server. |
| `transientVolRootDir` | std::string | Path to the root folder of the transient volume. |
| `site` | Teamcenter::POM_imc | The site object for this session |
| `bypass` | bool | True if bypass is enabled. |
| `journaling` | bool | True if journaling is enabled. |
| `appJournaling` | bool | True if application journaling is enabled. |
| `secJournaling` | bool | True if sec journaling is enabled. |
| `admJournaling` | bool | True if administration journaling is enabled. |
| `privileged` | bool | True if the user is privileged. |
| `isPartBOMUsageEnabled` | bool | True if the Part BOM Usage is enabled. |
| `isSubscriptionMgrEnabled` | bool | True if the Subscription Manager is enabled. |
| `textInfos` | Teamcenter::Soa::Core::_2007_01::Session::TextInfo[] | textInfos |
| `isInV7Mode` | bool | True if the server is operating in V7 mode. |
| `extraInfo` | Teamcenter::Soa::Core::_2007_01::Session::ExtraInfo | Map of kev/value pairs (string/string).The following keys are returned:<br /><ul><ul><li type="disc"><i>TcServerIDUnique |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData |
| `moduleNumber` | int | This element is not to be used anymore and always returns a -1. |
| `user` | Teamcenter::User | The <b>User</b> object for this session. |
| `group` | Teamcenter::Group | The <b>Group</b> object for this session. |
| `role` | Teamcenter::Role | The <b>Role</b> object for this session. |
| `tcVolume` | Teamcenter::ImanVolume | The <b>ImanVolume</b> object for this session. |
| `project` | Teamcenter::TC_Project | The <b>Project</b> object for this session. |
| `workContext` | Teamcenter::TC_WorkContext | The <b>WorkContext</b> object for this session. |

---

##### 2.14.2.3 setObjectPropertyPolicy

**接口路径：** `Core-2007-01-Session/setObjectPropertyPolicy`

**API 版本：** `2007-01`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 设置对象属性策略（Property Policy），控制返回哪些属性。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.Session.setObjectPropertyPolicy`

**请求（input）：**

```json
{
  "policyName": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policyName` | std::string | The name of the policy file without the <font face="courier" height="10">.xml </font>extension. The file must exist on t |

**响应（output）：**

```json
"bool"
```

---

#### 版本 2007-06

##### 2.14.3.1 refreshPOMCachePerRequest

**接口路径：** `Core-2007-06-Session/refreshPOMCachePerRequest`

**API 版本：** `2007-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `refreshPOMCachePerRequest`。By Default the service operations will retrieve 属性 value data straight from the POM. When refresh is set to true, a refresh will be done on 业务对象 before getting any 属性 data. This will update the POM with fresh data from the database. The refresh is only applied to 业务对象 that are actually being returned by a service operation. This applies on…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.Session.refreshPOMCachePerRequest`

**请求（input）：**

```json
{
  "refresh": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `refresh` | bool | If true, the business objects are refreshed before getting property values, if false the properties are retrieved from t |

**响应（output）：**

```json
"bool"
```

---

#### 版本 2007-12

##### 2.14.4.1 setAndEvaluateIdDisplayRule

**接口路径：** `Core-2007-12-Session/setAndEvaluateIdDisplayRule`

**API 版本：** `2007-12`  
**Service：** `Session`  
**Library：** `Core`

**说明：** Set the ID display rule for the 会话 and optionally set it in the database. The 业务对象 from the identifiableObjects list are expanded using the new ID display rule and returned. The rule is applied to all 业务对象 process throughout the rest of the 会话.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.Session.setAndEvaluateIdDisplayRule`

**请求（input）：**

```json
{
  "identifiableObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "displayRule": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "setRuleAsCurrentInDB": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `identifiableObjects` | Teamcenter::BusinessObject[] | A list of business objects for which the new ID display rule has to be re-evaluated. |
| `displayRule` | Teamcenter::IdDispRule | The ID display rule that is to be used for evaluation. |
| `setRuleAsCurrentInDB` | bool | If true then the ID display rule will be set for the current user in the database. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.14.4.2 setUserSessionState

**接口路径：** `Core-2007-12-Session/setUserSessionState`

**API 版本：** `2007-12`  
**Service：** `Session`  
**Library：** `Core`

**说明：** Set the desired user 会话 state values. To clear a field's value, pass an empty string "" as the value. Failure to set a particular state value will result in a Partial Error with the clientId set to the name of the state 属性. State values can be per client 会话 or per server 会话. Client 会话 state is kept separate for each 客户端应用 sharing the sa…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.Session.setUserSessionState`

**请求（input）：**

```json
{
  "pairs": [
    {
      "name": "",
      "value": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `pairs` | Teamcenter::Soa::Core::_2007_12::Session::StateNameValue[] | A list of name/value pairs of state properties to set. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2008-03

##### 2.14.5.1 connect

**接口路径：** `Core-2008-03-Session/connect`

**API 版本：** `2008-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `connect`。Performs Teamcenter Flexlm license related operations, depending on the input parameters. The low level actions are: 1. ILM__init_module: Initializes the license module (if it has not already been initialized). 2. ILM__leave_module: Deallocates a license of the given module. If the user had N free licenses for this module, (N plus one) will be left after this call. 3. ILM__c…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_03.Session.connect`

**请求（input）：**

```json
{
  "featureKey": "",
  "action": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `featureKey` | std::string | A string corresponding to the product as listed in the license file (e.g. teamcenter_author) |
| `action` | std::string | A string corresponding to the desired action. Valid values are:<br />1.   init: Performs the ILM__init_module action (co |

**响应（output）：**

```json
{
  "outputVal": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `outputVal` | int | The number of available licenses for the specified featureKey parameter. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData structure contains these potential error numbers:<br />&nbsp;&nbsp;&nbsp;&nbsp;  214401: The initializat |

---

##### 2.14.5.2 getFavorites

**接口路径：** `Core-2008-03-Session/getFavorites`

**API 版本：** `2008-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取当前用户收藏的业务对象列表。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_03.Session.getFavorites`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "output": {
    "containers": [
      {
        "clientId": "",
        "id": "",
        "type": "",
        "displayName": "",
        "parentId": ""
      }
    ],
    "objects": [
      {
        "clientId": "",
        "objectTag": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayName": "",
        "parentId": ""
      }
    ]
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_03::Session::FavoritesList | List of favorite containers and favorite objects for the current session user. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The service data. This operation will populate the Service Data plain objects list with the Favorite containers and obje |

---

##### 2.14.5.3 setFavorites

**接口路径：** `Core-2008-03-Session/setFavorites`

**API 版本：** `2008-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 保存 new favorite containers and favorite objects for the current 会话 user. Any partial errors encountered during 此操作 are returned using the clientID specified by the caller. A service exception is thrown if an error is encountered that is not related to a specific favorite container or favorite object. You can use favorites to track containers…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_03.Session.setFavorites`

**请求（input）：**

```json
{
  "input": {
    "curFavorites": {
      "containers": [
        {
          "clientId": "",
          "id": "",
          "type": "",
          "displayName": "",
          "parentId": ""
        }
      ],
      "objects": [
        {
          "clientId": "",
          "objectTag": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "displayName": "",
          "parentId": ""
        }
      ]
    },
    "newFavorites": {
      "containers": [
        {
          "clientId": "",
          "id": "",
          "type": "",
          "displayName": "",
          "parentId": ""
        }
      ],
      "objects": [
        {
          "clientId": "",
          "objectTag": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "displayName": "",
          "parentId": ""
        }
      ]
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_03::Session::FavoritesInfo | The information required to establish a new set of saved favorites for the current session user. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2008-06

##### 2.14.6.1 getDisplayStrings

**接口路径：** `Core-2008-06-Session/getDisplayStrings`

**API 版本：** `2008-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session）：获取Display Strings。Get the localized text string for each input key from the info array. The input key must correspond to a key defined in the Text Server. If the input array is empty, the returned array will also be empty.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.Session.getDisplayStrings`

**请求（input）：**

```json
{
  "info": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | std::string[] | A list of Text Server key names. |

**响应（output）：**

```json
{
  "output": [
    {
      "key": "",
      "value": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::Session::GetDisplayStringsOutput[] | A list Text Server key/localized value pairs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Partial errors with the key name attached to the partial error. |

---

##### 2.14.6.2 login

**接口路径：** `Core-2008-06-Session/login`

**API 版本：** `2008-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 验证用户凭据并初始化 Teamcenter 客户端会话；在四层架构下还会分配服务器实例。凭据无效时抛出 InvalidCredentialsException。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.Session.login`

**请求（input）：**

```json
{
  "username": "",
  "password": "",
  "group": "",
  "role": "",
  "locale": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `username` | std::string | The user`s Teamcenter user name. This is case insensitive (<i>jdoe</i> or <i>JDOE</i>) |
| `password` | std::string | The user`s Teamcenter password. |
| `group` | std::string | The group ID for this session. If null, the user`s default group is assumed. |
| `role` | std::string | The role the user is performing in the group. If null, the user`s default role in the group is assumed. |
| `locale` | std::string | The locale to be used by the Teamcenter server process for this session. If null, the server`s default locale will be us |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

##### 2.14.6.3 loginSSO

**接口路径：** `Core-2008-06-Session/loginSSO`

**API 版本：** `2008-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 通过单点登录（SSO）方式验证用户并初始化 Teamcenter 会话。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.Session.loginSSO`

**请求（input）：**

```json
{
  "username": "",
  "ssoCredentials": "",
  "group": "",
  "role": "",
  "locale": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `username` | std::string | The user's Teamcenter username. |
| `ssoCredentials` | std::string | The user's Teamcenter SSO credentials. This should have been obtained from Teamcenter Security Services. |
| `group` | std::string | The group id for this session (optional). If NULL, the user's default group is assumed. |
| `role` | std::string | The role the user is performing in the group (optional). If NULL, the user's default role in the group is assumed. |
| `locale` | std::string | The locale to be used by the Teamcenter server process for this session (optional). If NULL, the server's default locale |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

##### 2.14.6.4 setObjectPropertyPolicy

**接口路径：** `Core-2008-06-Session/setObjectPropertyPolicy`

**API 版本：** `2008-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 设置对象属性策略（Property Policy），控制返回哪些属性。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.Session.setObjectPropertyPolicy`

**请求（input）：**

```json
{
  "policy": "IObjectPropertyPolicy"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policy` | Teamcenter::Soa::Common::ObjectPropertyPolicy | The object property policy. |

**响应（output）：**

```json
"String"
```

---

#### 版本 2009-04

##### 2.14.7.1 startOperation

**接口路径：** `Core-2009-04-Session/startOperation`

**API 版本：** `2009-04`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `startOperation`。Start an operation bracket. An operation bracket is a period of execution in which any object will need to be refreshed in the server from the database only once. This allows the client to avoid unnecessary database operations that the server might perform redundantly if underlying code accesses the same object multiple times. The client will use the return value to call the…

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_04.Session.startOperation`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
"String"
```

---

##### 2.14.7.2 stopOperation

**接口路径：** `Core-2009-04-Session/stopOperation`

**API 版本：** `2009-04`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `stopOperation`。Stop an operation bracket, in which objects need to be refreshed only once. See startOperation.

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_04.Session.stopOperation`

**请求（input）：**

```json
{
  "opId": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `opId` | std::string | The operation identifier assigned to the operation and returned by the <font face="courier" height="10">startOperation</ |

**响应（output）：**

```json
"bool"
```

---

#### 版本 2010-04

##### 2.14.8.1 getPreferences2

**接口路径：** `Core-2010-04-Session/getPreferences2`

**API 版本：** `2010-04`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 takes an input structure which contains a scope value and vector of preference names. The return type of 此操作 is the MultiPreferencesResponse2 structure whose elements are the ServiceData and the vector of ReturnedPreferences2 structure.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.Session.getPreferences2`

**请求（input）：**

```json
{
  "preferenceNames": [
    {
      "scope": "",
      "names": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `preferenceNames` | Teamcenter::Soa::Core::_2007_01::Session::ScopedPreferenceNames[] | The input structure, the object of which would ahve 2 input parameters of scope and the preference names. |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "preferences": [
    {
      "scope": "",
      "category": "",
      "description": "",
      "prefType": "",
      "isArray": "",
      "isDisabled": "",
      "values": [
        ""
      ],
      "name": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |
| `preferences` | Teamcenter::Soa::Core::_2010_04::Session::ReturnedPreferences2[] | List of ReturnedPreferences2 Object |

---

##### 2.14.8.2 getShortcuts

**接口路径：** `Core-2010-04-Session/getShortcuts`

**API 版本：** `2010-04`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 获取 the sections and corresponding content in Left Hand Navigation task pane given the section name and the corresponding preference name for the current 会话 user. The preference name is the key to look up section content stored in preference. In the rich client, the LHN sections are Quick Links, Open Items, History, Favorites and I Want To. The user can …

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.Session.getShortcuts`

**请求（input）：**

```json
{
  "shortcutInputs": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `shortcutInputs` | Teamcenter::Soa::Core::_2010_04::Session::LHNShortcutInputs | A map of the key representing the  section name in the left hand navigation and the value representing the preference na |

**响应（output）：**

```json
{
  "favorites": {
    "containers": [
      {
        "clientId": "",
        "id": "",
        "type": "",
        "displayName": "",
        "parentId": ""
      }
    ],
    "objects": [
      {
        "clientId": "",
        "objectTag": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayName": "",
        "parentId": ""
      }
    ]
  },
  "shortcuts": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `favorites` | Teamcenter::Soa::Core::_2008_03::Session::FavoritesList | A hierarchical Favorites tree structure list that contains all the favorites containers and favorites objects for the cu |
| `shortcuts` | Teamcenter::Soa::Core::_2010_04::Session::LHNSectionComponentsMap | A map structure that includes the given section name and corresponding content of the section. The key is the name of th |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData contains any failures and Teamcenter objects  wrapped in LHNSecitonComponents and default properties. The fo |

---

#### 版本 2011-06

##### 2.14.9.1 getClientCacheData

**接口路径：** `Core-2011-06-Session/getClientCacheData`

**API 版本：** `2011-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 返回 information required to maintain a client cache. The Teamcneter server maintains a set of 数据集s with static or near static data that is pertainant to a 客户端应用. This static data can be downloaded through FMS to the cleint host one time, and available for each subsequent client 会话, thus improving the overall performance of the client …

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Session.getClientCacheData`

**请求（input）：**

```json
{
  "features": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `features` | std::string[] | Names of features to return<i>, All</i> to return data for all features. Available features are <i>ClientMetaModel</i> a |

**响应（output）：**

```json
{
  "features": [
    {
      "name": "",
      "cacheTickets": {}
    }
  ],
  "partialErrors": "IPartialErrors"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `features` | Teamcenter::Soa::Core::_2011_06::Session::Feature[] | The list of  features. |
| `partialErrors` | Teamcenter::Soa::Server::PartialErrors | Errors are return for features that do not exist or if there are other errors in getting data for a given service. The c |

---

##### 2.14.9.2 getTypeDescriptions

**接口路径：** `Core-2011-06-Session/getTypeDescriptions`

**API 版本：** `2011-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取类型描述信息（属性、关系等元数据）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Session.getTypeDescriptions`

**请求（input）：**

```json
{
  "typeNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `typeNames` | std::string[] | List of Business Model Object type names. |

**响应（output）：** 无

---

##### 2.14.9.3 login

**接口路径：** `Core-2011-06-Session/login`

**API 版本：** `2011-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 验证用户凭据并初始化 Teamcenter 客户端会话；在四层架构下还会分配服务器实例。凭据无效时抛出 InvalidCredentialsException。

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Session.login`

**请求（input）：**

```json
{
  "credentials": {
    "user": "{{USER_NAME}}",
    "password": "{{USER_PASSWORD}}",
    "group": "",
    "role": "",
    "locale": "",
    "descrimator": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `credentials` | Teamcenter::Soa::Core::_2011_06::Session::Credentials | The user's Teamcenter credentials |

**响应（output）：**

```json
{
  "serverInfo": {},
  "partialErrors": "IPartialErrors"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serverInfo` | Teamcenter::Soa::Core::_2011_06::Session::ServerInfo | Name/Value pairs (string/string) of data related to the server. The following keys are valid:<br /><ul><ul><li type="dis |
| `partialErrors` | Teamcenter::Soa::Server::PartialErrors | Partial errors or warnings resulting from the login attempt. |

---

##### 2.14.9.4 loginSSO

**接口路径：** `Core-2011-06-Session/loginSSO`

**API 版本：** `2011-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 通过单点登录（SSO）方式验证用户并初始化 Teamcenter 会话。

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Session.loginSSO`

**请求（input）：**

```json
{
  "credentials": {
    "user": "{{USER_NAME}}",
    "password": "{{USER_PASSWORD}}",
    "group": "",
    "role": "",
    "locale": "",
    "descrimator": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `credentials` | Teamcenter::Soa::Core::_2011_06::Session::Credentials | The user's Teamcenter credentials. |

**响应（output）：**

```json
{
  "serverInfo": {},
  "partialErrors": "IPartialErrors"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serverInfo` | Teamcenter::Soa::Core::_2011_06::Session::ServerInfo | Name/Value pairs (string/string) of data related to the server. The following keys are valid:<br /><ul><ul><li type="dis |
| `partialErrors` | Teamcenter::Soa::Server::PartialErrors | Partial errors or warnings resulting from the login attempt. |

---

##### 2.14.9.5 updateObjectPropertyPolicy

**接口路径：** `Core-2011-06-Session/updateObjectPropertyPolicy`

**API 版本：** `2011-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session）：更新对象 属性 Policy。Update the named policy, adding and removing the named 属性. 此操作 only applies to object 属性 policies that have been defined on the client side.

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Session.updateObjectPropertyPolicy`

**请求（input）：**

```json
{
  "policyID": "",
  "addProperties": [
    "IPolicyType"
  ],
  "removeProperties": [
    "IPolicyType"
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policyID` | std::string | The ID of the policy to update. This is the ID that is returned from the <font face="courier" height="10">setObjectPrope |
| `addProperties` | Teamcenter::Soa::Common::PolicyType[] | List of properties to add to the named policy.  If the property already exists in the policy, the flags (i.e. <font face |
| `removeProperties` | Teamcenter::Soa::Common::PolicyType[] | List of properties to remove from the named policy. If a source <font face="courier" height="10">PolicyType</font> defin |

**响应（output）：**

```json
"String"
```

---

#### 版本 2012-02

##### 2.14.10.1 registerState

**接口路径：** `Core-2012-02-Session/registerState`

**API 版本：** `2012-02`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `registerState`。Register desired level for server state as used by the Server Manager to control server timeout. Note that an attempt to register at LEVEL_STATELESS is ignored since this is the default level when no registrations are in effect. To move from a higher level to the stateless level the unregister operation should be used to delete the earlier registration. Note that it is possi…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.Session.registerState`

**请求（input）：**

```json
{
  "level": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `level` | std::string | Desired server state: "<i>Edit</i>" or "<i>Read</i>" |

**响应（output）：**

```json
{
  "registryIndex": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `registryIndex` | int | Index to be used for unregistering. |

---

##### 2.14.10.2 setObjectPropertyPolicy

**接口路径：** `Core-2012-02-Session/setObjectPropertyPolicy`

**API 版本：** `2012-02`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 设置对象属性策略（Property Policy），控制返回哪些属性。

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.Session.setObjectPropertyPolicy`

**请求（input）：**

```json
{
  "policyName": "",
  "useRefCounting": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policyName` | std::string | The name of the policy file without the .xml extension. The file must exist on the Teamcenter server volume at <font fac |
| `useRefCounting` | bool | When set to true, the policy will not remove a property value until there is a matching number of removes and adds in su |

**响应（output）：**

```json
{
  "policyId": "",
  "policy": "IObjectPropertyPolicy"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policyId` | std::string | Unique ID for this object property policy. |
| `policy` | Teamcenter::Soa::Common::ObjectPropertyPolicy | The full definition of the object property policy. |

---

##### 2.14.10.3 unregisterState

**接口路径：** `Core-2012-02-Session/unregisterState`

**API 版本：** `2012-02`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `unregisterState`。Remove the specified registration.

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.Session.unregisterState`

**请求（input）：**

```json
{
  "index": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `index` | int | Index returned by previous call to <font face="courier" height="10">registerState</font>. |

**响应（output）：**

```json
"bool"
```

---

#### 版本 2015-10

##### 2.14.11.1 getTypeDescriptions2

**接口路径：** `Core-2015-10-Session/getTypeDescriptions2`

**API 版本：** `2015-10`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取 the Meta data for the named Business Model object types based on the configurations specified by the client. To improve performance, clients can specify to exclude certain Meta data such as LOV References and Naming Rule References for the given types. If options are not provided 此操作 返回 all meta data associated with given types.

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.Session.getTypeDescriptions2`

**请求（input）：**

```json
{
  "typeNames": [
    ""
  ],
  "options": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `typeNames` | std::string[] | List of Business Model Object type names. |
| `options` | Teamcenter::Soa::Core::_2015_10::Session::TypeDescriptionOptions | A map (string/List of strings) of supported options and the option values.<br />The supported options for the map are li |

**响应（output）：** 无

---

##### 2.14.11.2 setUserSessionStateAndUpdateDefaults

**接口路径：** `Core-2015-10-Session/setUserSessionStateAndUpdateDefaults`

**API 版本：** `2015-10`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 设置 the desired user 会话 state values. 此操作 also updates the default value of the Group, Role and Project when these 会话 states are changed. To clear a field's value, client needs to pass an empty string "" as the value. Failure to set a particular state value will result in a Partial Error with the clientId set to the name of the state prop…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.Session.setUserSessionStateAndUpdateDefaults`

**请求（input）：**

```json
{
  "pairs": [
    {
      "name": "",
      "value": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `pairs` | Teamcenter::Soa::Core::_2007_12::Session::StateNameValue[] | A list of name/value pairs (string/string) of state properties to set. |

**响应（output）：**

```json
"IServiceData"
```

---

##### 2.14.11.3 sponsoredLogin

**接口路径：** `Core-2015-10-Session/sponsoredLogin`

**API 版本：** `2015-10`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `sponsoredLogin`。Authenticates the sponsoring user`s credentials and initialize a Teamcenter 会话 for the sponsored user. 该操作 will throw an InvalidCredentialsException as described below. When the 客户端应用 is deployed to a 4Tier environment the login operation also contributes to the assignment of a Teamcenter server instance to the client 会话. The sponsoring user,…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.Session.sponsoredLogin`

**请求（input）：**

```json
{
  "sponsoringUser": "",
  "password": "",
  "sponsoredUser": "",
  "sponsoredGroup": "",
  "sponsoredRole": "",
  "locale": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sponsoringUser` | std::string | The sponsoring user`s Teamcenter user name. This is case insensitive (jdoe or JDOE) |
| `password` | std::string | The sponsoring user`s Teamcenter password. |
| `sponsoredUser` | std::string | Sponsored user`s user name. This is case insensitive (jdoe or JDOE) |
| `sponsoredGroup` | std::string | The group ID for the sponsored user. |
| `sponsoredRole` | std::string | The role of the sponsored user. |
| `locale` | std::string | The locale to be used by the Teamcenter server process for this session. If null, the server`s default locale will be us |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

##### 2.14.11.4 sponsoredLoginSSO

**接口路径：** `Core-2015-10-Session/sponsoredLoginSSO`

**API 版本：** `2015-10`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `sponsoredLoginSSO`。Authenticates the sponsoring user using Single-Sign-On (SSO) credentials and initialize a Teamcenter 会话 for the sponsored user client. The username and ssoCredentials arguments are for the sponsoring user and must be obtained from Teamcenter's Security Services. The SsoCredentials class offers a simple API to get these values. 该操作 will throw an InvalidCredenti…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.Session.sponsoredLoginSSO`

**请求（input）：**

```json
{
  "sponsoringUser": "",
  "ssoCredentials": "",
  "sponsoredUser": "",
  "sponsoredGroup": "",
  "sponsoredRole": "",
  "locale": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sponsoringUser` | std::string | The sponsoring user`s Teamcenter user name. This is case insensitive (jdoe or JDOE) |
| `ssoCredentials` | std::string | The sponsoring user's Teamcenter SSO credentials. This should have been obtained from Teamcenter Security Services. |
| `sponsoredUser` | std::string | Sponsored user`s user name. This is case insensitive (jdoe or JDOE) |
| `sponsoredGroup` | std::string | The group ID for the sponsored user. |
| `sponsoredRole` | std::string | The role of the sponsored user. |
| `locale` | std::string | The locale to be used by the Teamcenter server process for this session. If null, the server`s default locale will be us |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

#### 版本 2019-06

##### 2.14.12.1 licenseAdmin

**接口路径：** `Core-2019-06-Session/licenseAdmin`

**API 版本：** `2019-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 provides licensing related operations such as check-out and check-in of a license feature key.

**Soa Inclusion：** `Teamcenter.Soa.Core._2019_06.Session.licenseAdmin`

**请求（input）：**

```json
{
  "licAdminInput": [
    {
      "featureKey": "",
      "licensingAction": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `licAdminInput` | Teamcenter::Soa::Core::_2019_06::Session::LicAdminInput[] | A list of feature key and action pairs. This allows multiple license keys to be checked out in one service operation cal |

**响应（output）：**

```json
"IServiceData"
```

---

#### 版本 2021-12

##### 2.14.13.1 addObjectPropertyPolicies

**接口路径：** `Core-2021-12-Session/addObjectPropertyPolicies`

**API 版本：** `2021-12`  
**Service：** `Session`  
**Library：** `Core`

**说明：** Adds multiple object 属性 policies to the 会话. Once these policies are added to the 会话, the 客户端应用 can quickly switch between policies using the appropriate methods on the Object属性PolicyManager class in the SOA client framework. The business logic of a service operation determines what 业务对象 are returned, while the object 属性 po…

**Soa Inclusion：** `Teamcenter.Soa.Core._2021_12.Session.addObjectPropertyPolicies`

**请求（input）：**

```json
{
  "clientPolicies": [
    "IObjectPropertyPolicy"
  ],
  "namedPolicies": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `clientPolicies` | Teamcenter::Soa::Common::ObjectPropertyPolicy[] | A list of client defined object property policies. |
| `namedPolicies` | std::string[] | A list of policy files defined on the Teamcenter server volume at<font face="courier" height="10"> $TC_Data/soa/policies |

**响应（output）：**

```json
{
  "policyIDs": [
    ""
  ],
  "partialErrors": "IPartialErrors"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policyIDs` | std::string[] | A list of policy IDs. The initial size and order of this list will match the input list of <font face="courier" height=" |
| `partialErrors` | Teamcenter::Soa::Server::PartialErrors | Partial errors or warnings. |

---

#### 版本 2022-12

##### 2.14.14.1 tcServerSleep

**接口路径：** `Core-2022-12-Session/tcServerSleep`

**API 版本：** `2022-12`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `tcServerSleep`。A no-op serivce operation that puts the TcServer in a wait/sleep for the requested amount of time before returning. This can be used to simulate long running service requests.

**Soa Inclusion：** `Teamcenter.Soa.Core._2022_12.Session.tcServerSleep`

**请求（input）：**

```json
{
  "seconds": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `seconds` | int | The number of seconds to sleep. |

**响应（output）：**

```json
"String"
```

---

#### 版本 2023-12

##### 2.14.15.1 logout

**接口路径：** `Core-2023-12-Session/logout`

**API 版本：** `2023-12`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 注销当前 Teamcenter 会话并释放相关资源。

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_12.Session.logout`

**请求（input）：**

```json
{
  "clientIDs": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `clientIDs` | std::string[] | The list of Client IDs. |

**响应（output）：**

```json
"bool"
```

---

### 2.15 结构管理（StructureManagement）

**涵盖 API 版本：** `2008-06`  
**操作数：** 4

#### 版本 2008-06

##### 2.15.1.1 createInStructureAssociations

**接口路径：** `Core-2008-06-StructureManagement/createInStructureAssociations`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Core`

**说明：** 此操作 创建 the specified association between primary and secondary BOMLine objects in a structure. As the name indicates, these associations are created in a specific context and are applicable only in that context. The context is specified as an additional input in the input structure, by the caller. Some examples of these associations are: the ConnectTo, Implem…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.StructureManagement.createInStructureAssociations`

**请求（input）：**

```json
{
  "inputs": [
    {
      "primaryBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "contextBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "secondaries": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "associationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2008_06::StructureManagement::InStructureAssociationInfo[] | This is a vector of InStructureAssociationInfo structure. Each element shall consist of a primary <b>BOMLine</b>, the se |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <i>ServiceData</i> structure is used to return the updated objects and contains partial errors, if any, occurring in |

---

##### 2.15.1.2 getPrimariesOfInStructureAssociation

**接口路径：** `Core-2008-06-StructureManagement/getPrimariesOfInStructureAssociation`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Core`

**说明：** 此操作 获取 the primary BOMLines like PSConnection, Signal of an association given the secondary object and association type. Examples of these associations are: ConnectTo, ImplementedBy, RealizedBy, RoutedBy, FixingToSegment, DeviceToConnector, SignalToTransmitter, SignalToSource, SignalToTarget, ProcessVariable, RedundantSignal. 此操作 takes a vector of Get…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.StructureManagement.getPrimariesOfInStructureAssociation`

**请求（input）：**

```json
{
  "inputs": [
    {
      "secondary": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "contextBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "associationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2008_06::StructureManagement::GetPrimariesOfInStructureAssociationInfo[] | This is a vector of <i>GetPrimariesOfInStructureAssociationInfo</i> structure. Each element consists of a secondary <b>B |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "primariesInfo": [
    {
      "secondary": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "associationType": "",
      "primaryBOMLine": {
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
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <i>ServiceData</i> structure is used to return the primary <b>BOMLine</b> business objects and partial errors if any |
| `primariesInfo` | Teamcenter::Soa::Core::_2008_06::StructureManagement::PrimariesOfInStructureAssociation[] | Context object of association. This is generally the parent line of the primary object. |

---

##### 2.15.1.3 getSecondariesOfInStructureAssociation

**接口路径：** `Core-2008-06-StructureManagement/getSecondariesOfInStructureAssociation`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Core`

**说明：** 结构管理（StructureManagement）：获取Secondaries Of In Structure Association。Given the primary object and association type, 返回 the secondary BOMLine 业务对象 of in structure associations. These associations can be ConnectTo, ImplementedBy, RealizedBy, RoutedBy, FixingToSegment, DeviceToConnector, SignalToSource, SignalToTarget, SignalToTransmitter, ProcessVariable or RedundantSignal. It takes a vector of 获取econdariesOfInStructureAssoci…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.StructureManagement.getSecondariesOfInStructureAssociation`

**请求（input）：**

```json
{
  "inputs": [
    {
      "primaryBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "contextBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "associationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2008_06::StructureManagement::GetSecondariesOfInStructureAssociationInfo[] | This is a vector of <i>GetSecondariesOfInStructureAssociationInfo</i> structure. Each element shall consist of a primary |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "secondariesInfo": [
    {
      "primaryBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "associationType": "",
      "secondaries": [
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
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Secondary <b>BOMLine</b> business objects and Partial errors if any |
| `secondariesInfo` | Teamcenter::Soa::Core::_2008_06::StructureManagement::SecondariesOfInStructureAssociation[] | primary <b>BOMLine</b> and association type. |

---

##### 2.15.1.4 removeInStructureAssociations

**接口路径：** `Core-2008-06-StructureManagement/removeInStructureAssociations`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Core`

**说明：** 结构管理（StructureManagement）：移除In Structure Associations。Given the primary BOMLine, the association type, and the secondary BOMLines 此操作 removes the instructure associations between the BOMLines. These associations can be ConnectTo, ImplementedBy, RealizedBy, RoutedBy, FixingToSegment, DeviceToConnector, SignalToSource, SignalToTarget, SignalToTransmitter, ProcessVariable or RedundantSignal. 该操作 takes a vector…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.StructureManagement.removeInStructureAssociations`

**请求（input）：**

```json
{
  "inputs": [
    {
      "primaryBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "contextBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "secondaries": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "associationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2008_06::StructureManagement::RemoveInStructureAssociationsInfo[] | This is a vector of <i>RemoveInStructureAssociationsInfo</i> structure. Each element shall consist of a primary <b>BOMLi |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The updated objects and partial errors if any. |

---

---

## 3. 按 API 版本（年-月）归档

按时间线列出各版本契约下的全部接口（与第 2 节内容一致，便于按版本检索）。

### 3.1 API 版本 2006-03

**Service：** DataManagement、FileManagement、Reservation、Session  **操作数：** 28

#### 3.1.1 changeOwnership（2006-03）

**接口路径：** `Core-2006-03-DataManagement/changeOwnership`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 can be used to change the ownership on a given 业务对象 to the given user and group. Owning user attribute on the 业务对象 will be changed to the given user and owning group attribute is changed to the given group. The user needs CHANGE_OWNER privilege and WRITE privilege on the 业务对象 to be able to change its ownership. If user does not…

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.changeOwnership`

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
      "owner": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "group": {
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
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::ObjectOwner[] | Input object to the operation that holds the business object, new owning user and new owning group. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.1.2 createDatasets（2006-03）

**接口路径：** `Core-2006-03-DataManagement/createDatasets`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建一个或多个数据集（Dataset）及其文件信息。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.createDatasets`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "type": "",
      "name": "",
      "description": "",
      "toolUsed": "",
      "container": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::DatasetProperties[] | The information needed to create <b>Dataset</b> objects<br /> |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "dataset": {
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
| `output` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateDatasetsOutput[] | A list of created <b>Dataset</b> output |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

#### 3.1.3 createFolders（2006-03）

**接口路径：** `Core-2006-03-DataManagement/createFolders`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 在指定容器下创建一个或多个文件夹。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.createFolders`

**请求（input）：**

```json
{
  "folders": [
    {
      "clientId": "",
      "name": "",
      "desc": ""
    }
  ],
  "container": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "relationType": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `folders` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateFolderInput[] | Input struture to create <b>Folder</b> Objects |
| `container` | Teamcenter::BusinessObject | The object to which all the created <b>Folder</b> objects will be related to via the input relation type, may be null. |
| `relationType` | std::string | The name of relation type that all created <b>Folder</b> objects will be related to the container, may be an empty strin |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "folder": {
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
| `output` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateFoldersOutput[] | Each element in the list contains a client Id and the related <b>Folder</b> object created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

#### 3.1.4 createItems（2006-03）

**接口路径：** `Core-2006-03-DataManagement/createItems`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建一个或多个 Item 及其初始版本，可指定容器与关系类型。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.createItems`

**请求（input）：**

```json
{
  "properties": [
    {
      "clientId": "",
      "itemId": "",
      "name": "",
      "type": "",
      "revId": "",
      "uom": "",
      "description": "",
      "extendedAttributes": [
        {
          "objectType": "",
          "attributes": {}
        }
      ]
    }
  ],
  "container": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "relationType": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `properties` | Teamcenter::Soa::Core::_2006_03::DataManagement::ItemProperties[] | A list of properties to create new <b>Item</b> objects |
| `container` | Teamcenter::BusinessObject | The container object to which all the items will be related to via the input relation type, optional. |
| `relationType` | std::string | The relation type that will be used to relate the newly created <b>Item</b>s to the container, optional. |

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
      }
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateItemsOutput[] | A list of the created <b>Item</b> and <b>ItemRevision</b> |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

#### 3.1.5 createRelations（2006-03）

**接口路径：** `Core-2006-03-DataManagement/createRelations`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 在主对象与次对象之间建立指定类型的关系。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.createRelations`

**请求（input）：**

```json
{
  "input": [
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
      "userData": {
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
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::Relationship[] | A list of structures containing details of relationships to be created between primary and secondary objects with the gi |

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
| `output` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateRelationsOutput[] | A list of created relations. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> object to hold the partial errors that the operation encoun |

---

#### 3.1.6 deleteObjects（2006-03）

**接口路径：** `Core-2006-03-DataManagement/deleteObjects`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 删除指定业务对象。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.deleteObjects`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of objects to be deleted |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.1.7 deleteRelations（2006-03）

**接口路径：** `Core-2006-03-DataManagement/deleteRelations`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 删除 the specified relation between the primary and secondary object for each input structure.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.deleteRelations`

**请求（input）：**

```json
{
  "input": [
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
      "userData": {
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
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::Relationship[] | A list of structures containing details of relationships to be deleted between primary and secondary objects with the gi |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.1.8 generateItemIdsAndInitialRevisionIds（2006-03）

**接口路径：** `Core-2006-03-DataManagement/generateItemIdsAndInitialRevisionIds`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates a list of Item IDs and initial ItemRevision IDs. The initial revision ID is defined as the first revision ID for the given type.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.generateItemIdsAndInitialRevisionIds`

**请求（input）：**

```json
{
  "input": [
    {
      "item": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemType": "",
      "count": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::GenerateItemIdsAndInitialRevisionIdsProperties[] | A list of the <b>Item</b>, <b>Item</b> type, and the number of IDs to generate. |

**响应（output）：**

```json
{
  "outputItemIdsAndInitialRevisionIds": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `outputItemIdsAndInitialRevisionIds` | Teamcenter::Soa::Core::_2006_03::DataManagement::IndexToIdMap | A list of the new <b>Item</b> and <b>ItemRevision</b> IDs and flags indicating if the system is configured to allow modi |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

#### 3.1.9 generateRevisionIds（2006-03）

**接口路径：** `Core-2006-03-DataManagement/generateRevisionIds`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 按规则预生成版本号。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.generateRevisionIds`

**请求（input）：**

```json
{
  "input": [
    {
      "item": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::GenerateRevisionIdsProperties[] | A list <b>Item</b> and <b>Item</b> type |

**响应（output）：**

```json
{
  "outputRevisionIds": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `outputRevisionIds` | Teamcenter::Soa::Core::_2006_03::DataManagement::IndexToRevIdMap | A list of the new generated id values |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

#### 3.1.10 getProperties（2006-03）

**接口路径：** `Core-2006-03-DataManagement/getProperties`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 批量获取指定业务对象的属性；attributes 为空时返回全部属性。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.getProperties`

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
  "attributes": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | List of attribute/property name strings for which values are needed |
| `attributes` | std::string[] | List of object references for which property values are requested |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.1.11 revise（2006-03）

**接口路径：** `Core-2006-03-DataManagement/revise`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** Revises a list of next Item 版本s based on input existing Item 版本 object references and any additional attributes. Uses deep copy rules to propagate existing relations from the Item 版本 or to create new references.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.revise`

**请求（input）：**

```json
{
  "input": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2006_03::DataManagement::ItemRevPropertyMap | A map of Item Revisions and ReviseProperties structures |

**响应（output）：**

```json
{
  "oldItemRevToNewItemRev": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `oldItemRevToNewItemRev` | Teamcenter::Soa::Core::_2006_03::DataManagement::ItemRevMap | A Map whose keys are the input old item revisions and values are the newly created revisions |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |

---

#### 3.1.12 setDisplayProperties（2006-03）

**接口路径：** `Core-2006-03-DataManagement/setDisplayProperties`

**API 版本：** `2006-03`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 is provided to update the Teamcenter objects for the given name/display value pairs. 此操作 works for all supported 属性 value types to set display values. When setting 此操作 it invokes the server PROP_UIF_set_value extensions. For updating an array 属性, display values need to be comma (,) separated which server parses them into indiv…

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.DataManagement.setDisplayProperties`

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
  "attributes": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of objects for which property values need to be set |
| `attributes` | Teamcenter::Soa::Core::_2006_03::DataManagement::AttributeNameValueMap | A map of attribute names and display values of a property  (string/string) |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.1.13 commitDatasetFiles（2006-03）

**接口路径：** `Core-2006-03-FileManagement/commitDatasetFiles`

**API 版本：** `2006-03`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 将已上传至 FMS 的文件提交并关联到数据集。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.FileManagement.commitDatasetFiles`

**请求（input）：**

```json
{
  "commitInput": [
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
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `commitInput` | Teamcenter::Soa::Core::_2006_03::FileManagement::CommitDatasetFileInfo[] | The vector of <font face=&quot;courier&quot; height=&quot;10&quot;>CommitDatasetFileInfo</font> structures returned in t |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.1.14 getDatasetWriteTickets（2006-03）

**接口路径：** `Core-2006-03-FileManagement/getDatasetWriteTickets`

**API 版本：** `2006-03`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 此操作 obtains File Management System (FMS) write tickets and file storage information for a set of supplied 数据集 objects. The write tickets are used to transfer files from a local storage to Teamcenter volume, and the file storage information can be used to commit 数据集 objects referencing those transferred files. The caller will provide a vector of Get数据集W…

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.FileManagement.getDatasetWriteTickets`

**请求（input）：**

```json
{
  "inputs": [
    {
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "createNewVersion": "",
      "datasetFileInfos": [
        {
          "clientId": "",
          "fileName": "",
          "namedReferencedName": "",
          "isText": "",
          "allowReplace": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2006_03::FileManagement::GetDatasetWriteTicketsInputData[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>GetDatasetWriteTicketsInputData</font> structures which |

**响应（output）：**

```json
{
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
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `commitInfo` | Teamcenter::Soa::Core::_2006_03::FileManagement::CommitDatasetFileInfo[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>CommitDatasetFileInfo</font> structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Teamcenter Services structure used to return status of the operation.  Any errors that occurred during the operation |

---

#### 3.1.15 getFileReadTickets（2006-03）

**接口路径：** `Core-2006-03-FileManagement/getFileReadTickets`

**API 版本：** `2006-03`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 此操作 obtains File Management System (FMS) read tickets for a set of supplied ImanFile objects. The supplied tickets are used to transfer files from a Teamcenter volume to local storage. The files input parameter contains a list of the ImanFile objects to be read from the Teamcenter volume and transferred to local storage. FMS requires tickets for all file transfers…

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.FileManagement.getFileReadTickets`

**请求（input）：**

```json
{
  "files": [
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
| `files` | Teamcenter::ImanFile[] | A vector of <b>ImanFile</b> objects to be transferred from a<br />Teamcenter volume to local storage.  The calling clien |

**响应（output）：**

```json
{
  "tickets": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `tickets` | Teamcenter::Soa::Core::_2006_03::FileManagement::TicketMap | A map of the input <b>ImanFile</b> objects to FMS tickets used to access files in the Teamcenter volume. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Teamcenter Services structure used to return status of the operation.  Any errors that occurred during the operation |

---

#### 3.1.16 cancelCheckout（2006-03）

**接口路径：** `Core-2006-03-Reservation/cancelCheckout`

**API 版本：** `2006-03`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 取消检出并丢弃未保存更改。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Reservation.cancelCheckout`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of objects to be canceled for previously check-out. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.1.17 checkin（2006-03）

**接口路径：** `Core-2006-03-Reservation/checkin`

**API 版本：** `2006-03`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 签入已检出的业务对象。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Reservation.checkin`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] |  Set of previously checked-out valid business objects. (e.g. <b>Dataset</b>, <b>Item</b>, <b>ItemRevision</b> ) |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.1.18 checkout（2006-03）

**接口路径：** `Core-2006-03-Reservation/checkout`

**API 版本：** `2006-03`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 检出业务对象以进行编辑。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Reservation.checkout`

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
  "comment": "",
  "changeId": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of business objects to be checked out. |
| `comment` | std::string | A comment describing the reason for the check-out.  An empty string is allowed. |
| `changeId` | std::string | A string value to identify the change.  Empty string allowed. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.1.19 getReservationHistory（2006-03）

**接口路径：** `Core-2006-03-Reservation/getReservationHistory`

**API 版本：** `2006-03`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 获取 the reservation history for a set of 业务对象, such as 数据集, Item, ItemRevision and many other 业务对象 types. An object which has never been checked out will have a valid reservation history with an empty sequence of events.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Reservation.getReservationHistory`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of business objects to query for reservation history. |

**响应（output）：**

```json
{
  "histories": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "events": [
        {
          "dateTime": "",
          "user": "",
          "activity": "",
          "changeId": "",
          "comment": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `histories` | Teamcenter::Soa::Core::_2006_03::Reservation::ReservationHistory[] | Reservation history. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Objects which are queried successfully are added to the ServiceData plain list. |

---

#### 3.1.20 getAvailableServices（2006-03）

**接口路径：** `Core-2006-03-Session/getAvailableServices`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 返回 a list of services and service operations that this Teamcenter server instance supports. This is useful for 客户端应用s that expose different functionality based on the version of the Teamcenter server it is connecting to.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.getAvailableServices`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "serviceNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceNames` | std::string[] | List of available services |

---

#### 3.1.21 getGroupMembership（2006-03）

**接口路径：** `Core-2006-03-Session/getGroupMembership`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session）：获取Group Membership。Get the valid groups and roles for the current user.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.getGroupMembership`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "groupMembers": [
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
| `groupMembers` | Teamcenter::GroupMember[] | A list of all the valid <b>GroupMember</b> objects for the current session`s <b>User</b>.  A <b>GroupMember</b> holds id |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The plain list has all the <b>GroupMembers</b>, <b>Groups</b> and <b>Roles</b> for this <b>User</b> |

---

#### 3.1.22 getPreferences（2006-03）

**接口路径：** `Core-2006-03-Session/getPreferences`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取用户或站点偏好设置。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.getPreferences`

**请求（input）：**

```json
{
  "prefScope": "",
  "prefNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `prefScope` | std::string | The scope in which the preferences are to be searched,                     "all", "site", "user", "group", or "role". |
| `prefNames` | std::string[] | A vector of the names of the desired preferences. |

**响应（output）：**

```json
{
  "preferences": "IPreferences",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `preferences` | Teamcenter::Soa::Server::Preferences | The requested preference name/values. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any partial errors that may occur when filling this request. |

---

#### 3.1.23 getSessionGroupMember（2006-03）

**接口路径：** `Core-2006-03-Session/getSessionGroupMember`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** Get the Group and Role for the current 会话. The group and role are set at login, either to default values or as specified by the input arguments to the login operation. The group and role can be changed at any time throughout the 会话 through the set会话GroupMember or setUser会话State operations.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.getSessionGroupMember`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> object which represents the logged in user's, <b>Group</b>, and Role for the current session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> object is included in the plain list. |

---

#### 3.1.24 login（2006-03）

**接口路径：** `Core-2006-03-Session/login`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 验证用户凭据并初始化 Teamcenter 客户端会话；在四层架构下还会分配服务器实例。凭据无效时抛出 InvalidCredentialsException。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.login`

**请求（input）：**

```json
{
  "username": "",
  "password": "",
  "group": "",
  "role": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `username` | std::string | The user's Teamcenter user name. |
| `password` | std::string | The user's Teamcenter password. |
| `group` | std::string | The group ID for this session. If empty (""), the user's default group is assumed. |
| `role` | std::string | The role the user is performing in the group. If empty (""), the user's default role in the group is assumed. |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

#### 3.1.25 loginSSO（2006-03）

**接口路径：** `Core-2006-03-Session/loginSSO`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 通过单点登录（SSO）方式验证用户并初始化 Teamcenter 会话。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.loginSSO`

**请求（input）：**

```json
{
  "username": "",
  "ssoCredentials": "",
  "group": "",
  "role": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `username` | std::string | The user's Teamcenter username. |
| `ssoCredentials` | std::string | The user's Teamcenter SSO credentials. This should have been obtained from Teamcenter Security Services. |
| `group` | std::string | The group id for this session. If blank (""), the user's default group is assumed. |
| `role` | std::string | The role the user is performing in the group. If blank (""), the user's default role in the group is assumed. |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

#### 3.1.26 logout（2006-03）

**接口路径：** `Core-2006-03-Session/logout`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 注销当前 Teamcenter 会话并释放相关资源。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.logout`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.1.27 setPreferences（2006-03）

**接口路径：** `Core-2006-03-Session/setPreferences`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 设置用户或站点偏好设置。

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.setPreferences`

**请求（input）：**

```json
{
  "settings": [
    {
      "prefScope": "",
      "prefName": "",
      "prefValues": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `settings` | Teamcenter::Soa::Core::_2006_03::Session::PrefSetting[] | vector of PrefSetting structures, which specify the scope, name, and value(s) for each of the preferences to be set. |

**响应（output）：**

```json
{
  "preferences": "IPreferences",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `preferences` | Teamcenter::Soa::Server::Preferences | The requested preference name/values. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any partial errors that may occur when filling this request. |

---

#### 3.1.28 setSessionGroupMember（2006-03）

**接口路径：** `Core-2006-03-Session/setSessionGroupMember`

**API 版本：** `2006-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** Set the Group and Role for the current 会话. The group and role are set at login, either to default values or as specified by the input arguments to the login operation. The group and role can be changed at any time throughout the 会话 through 此操作 or the setUser会话State operations. The get会话GroupMember will return the current group and roll.

**Soa Inclusion：** `Teamcenter.Soa.Core._2006_03.Session.setSessionGroupMember`

**请求（input）：**

```json
{
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `groupMember` | Teamcenter::GroupMember | The desired <b>GroupMember</b> for the current session.  The <b>GroupMember</b> defines the <b>Group</b> and <b>Role</b> |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.2 API 版本 2007-01

**Service：** DataManagement、FileManagement、ManagedRelations、Session  **操作数：** 18

#### 3.2.1 createOrUpdateForms（2007-01）

**接口路径：** `Core-2007-01-DataManagement/createOrUpdateForms`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 创建 Form objects or update existing Form objects using the info provided. A new Form will be associated to the container object with specified relation type. The 属性 of the existing Form will be updated.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.createOrUpdateForms`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "formObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "parentObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationName": "",
      "saveDB": "",
      "name": "",
      "description": "",
      "formType": "",
      "attributesMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2007_01::DataManagement::FormInfo[] | Input for creating or updating <b>Form</b> objects |

**响应（output）：**

```json
{
  "outputs": [
    {
      "clientId": "",
      "form": {
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
| `outputs` | Teamcenter::Soa::Core::_2007_01::DataManagement::CreateFormsOutput[] | List of created or updated <b>Form</b> objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

#### 3.2.2 generateUID（2007-01）

**接口路径：** `Core-2007-01-DataManagement/generateUID`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** This function 返回 a number of Teamcenter UIDs generated from the Teamcenter server. 此操作 can be used for assigning unique identifiers to objects that will not be stored in Teamcenter or for objects which have yet to be created in Teamcenter. The createObjects and createOrUpdateParts operations will support input of a preallocated UID for use during creation. Pl…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.generateUID`

**请求（input）：**

```json
{
  "nUID": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `nUID` | int | The number of UIDs to be generated. |

**响应（output）：**

```json
{
  "uids": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `uids` | std::string[] | List of the UIDs that were generated |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains any errors encountered during processing in the partial errors list. |

---

#### 3.2.3 getDatasetCreationRelatedInfo（2007-01）

**接口路径：** `Core-2007-01-DataManagement/getDatasetCreationRelatedInfo`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 pre-populates 数据集 creation information, default new 数据集 name and Tool names, for a specified 数据集 type. 此操作 is used to get all the information associates with the specified 数据集 prior to the creation operation. The returned default new 数据集 name may be determined by the parent container object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.getDatasetCreationRelatedInfo`

**请求（input）：**

```json
{
  "typeName": "",
  "parentObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `typeName` | std::string |  desired <b>Dataset</b> type name |
| `parentObject` | Teamcenter::BusinessObject | The containe object under which the new <b>Dataset</b> object will be created |

**响应（output）：**

```json
{
  "toolNames": [
    ""
  ],
  "newDatasetName": "",
  "nameCanBeModified": "",
  "initValuePropertyRules": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `toolNames` | std::string[] | List of <b>Tool</b> names |
| `newDatasetName` | std::string | The name of the new <b>Dataset</b>, can be an empty string |
| `nameCanBeModified` | bool | If true, the name of the <b>Dataset</b> can be modified |
| `initValuePropertyRules` | std::string[] | List of properties have the initialized values from property constant attachments |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

#### 3.2.4 getItemCreationRelatedInfo（2007-01）

**接口路径：** `Core-2007-01-DataManagement/getItemCreationRelatedInfo`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 will return naming rules, 属性 rule, form 属性 descriptor, unit of measurement and ItemRevision type name based on Item type selected by user during Item creation.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.getItemCreationRelatedInfo`

**请求（input）：**

```json
{
  "typeName": "",
  "parentObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `typeName` | std::string | <b>Item</b> type name |
| `parentObject` | Teamcenter::BusinessObject | <b>parentObject</b> is an unused parameter and may be null |

**响应（output）：**

```json
{
  "complexValuePropertyRules": [
    ""
  ],
  "initValuePropertyRules": [
    ""
  ],
  "patternMap": {},
  "uoms": [
    ""
  ],
  "formAttrs": [
    {
      "formType": "",
      "formPDs": [
        {
          "propName": "",
          "displayName": "",
          "attachedSpecifier": "",
          "maxLength": "",
          "interdependentProps": [
            ""
          ],
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
          "isEnabled": "",
          "isModifiable": ""
        }
      ]
    }
  ],
  "revTypeName": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `complexValuePropertyRules` | std::string[] | List of complex value property rules |
| `initValuePropertyRules` | std::string[] | List of initial values |
| `patternMap` | Teamcenter::Soa::Core::_2007_01::DataManagement::StringArrayMap | Pattern map (string/string) |
| `uoms` | std::string[] | List of unit of measures |
| `formAttrs` | Teamcenter::Soa::Core::_2007_01::DataManagement::FormAttributesInfo[] | List of <b>Form</b> attributes |
| `revTypeName` | std::string | <b>ItemRevision</b> type name |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful object ids, partial errors and failures |

---

#### 3.2.5 getItemFromId（2007-01）

**接口路径：** `Core-2007-01-DataManagement/getItemFromId`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 根据 Item 编号与版本号解析并返回 Item/ItemRevision 对象。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.getItemFromId`

**请求（input）：**

```json
{
  "infos": [
    {
      "itemId": "{{ITEM_ID}}",
      "revIds": [
        ""
      ]
    }
  ],
  "nRev": "",
  "pref": {
    "prefs": [
      {
        "relationTypeName": "",
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
| `infos` | Teamcenter::Soa::Core::_2007_01::DataManagement::GetItemFromIdInfo[] | list of GetItemFromIdInfo structures |
| `nRev` | int | value for the latest number of Item Revisions to return |
| `pref` | Teamcenter::Soa::Core::_2007_01::DataManagement::GetItemFromIdPref | GetItemFromIdPref structure for relation and types filtering |

**响应（output）：**

```json
{
  "output": [
    {
      "item": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemRevOutput": [
        {
          "itemRevision": {
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
| `output` | Teamcenter::Soa::Core::_2007_01::DataManagement::GetItemFromIdItemOutput[] | List of GetItemFromIdItemOutput |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |

---

#### 3.2.6 moveToNewFolder（2007-01）

**接口路径：** `Core-2007-01-DataManagement/moveToNewFolder`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** The moveToNew文件夹 operation moves a set of objects from one 文件夹 to another. 此操作 allows for moving multiple 设置 of objects to and from different 文件夹s. If no old 文件夹 is specified, 此操作 adds the objects to the new 文件夹.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.moveToNewFolder`

**请求（input）：**

```json
{
  "moveToNewFolderInfos": [
    {
      "oldFolder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newFolder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectsToMove": [
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
| `moveToNewFolderInfos` | Teamcenter::Soa::Core::_2007_01::DataManagement::MoveToNewFolderInfo[] | A list of <font face=&quot;courier&quot; height=&quot;10&quot;>MoveToNewFolderInfo</font> structures each containing an  |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains the updated old folder, the new folder, and partial errors from this operation. |

---

#### 3.2.7 refreshObjects（2007-01）

**接口路径：** `Core-2007-01-DataManagement/refreshObjects`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 刷新会话中对象的最新状态。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.refreshObjects`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of object to be refreshed |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.8 saveAsNewItem（2007-01）

**接口路径：** `Core-2007-01-DataManagement/saveAsNewItem`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 创建 a new Item object and ItemRevision object from an existing ItemRevision object. The master form 属性 may be supplied for the new ItemRevision and item master form objects. If master form data is not supplied the master forms will be initialized from the master forms attached to the existing ItemRevision. Deep Copy rules may also be supplied to ov…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.saveAsNewItem`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "itemRevision": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemId": "",
      "revId": "",
      "name": "",
      "description": "",
      "folder": {
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
| `info` | Teamcenter::Soa::Core::_2007_01::DataManagement::SaveAsNewItemInfo[] | The necessary information to create the new <b>Item</b> and <b>ItemRevision</b> |

**响应（output）：**

```json
{
  "inputToNewItem": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputToNewItem` | Teamcenter::Soa::Core::_2007_01::DataManagement::InputToNewItemMap | Map whose keys are the input clientIds and output values (newly created <b>Item</b> and <b>ItemRevision</b> objects) pai |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

#### 3.2.9 setProperties（2007-01）

**接口路径：** `Core-2007-01-DataManagement/setProperties`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 批量设置业务对象的属性值。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.setProperties`

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
  "attributes": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | List of Business Objects for which the properties values to be set. |
| `attributes` | Teamcenter::Soa::Core::_2007_01::DataManagement::NameValueMap | A map of attribute names and desired value pairs (string/VecStruct). The <font face=&quot;courier&quot; height=&quot;10& |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.2.10 whereReferenced（2007-01）

**接口路径：** `Core-2007-01-DataManagement/whereReferenced`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 finds the objects and relations that reference a given object. It 返回 objects where the input object is specified in a Reference 属性 on that object. It also 返回 relations where the input object is listed as the secondary object for that relation. It does not return relations where the input object is the primary object for that relation. The Datam…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.whereReferenced`

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
  "numLevels": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::WorkspaceObject[] | List of <b>WorkspaceObject</b> references to find referencers for. If an element in the list is null a partial error is  |
| `numLevels` | int | Number of levels to traverse to find the referencers. For example, if A references B, and B references C, a 1 level sear |

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
      "info": [
        {
          "referencer": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relation": "",
          "level": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2007_01::DataManagement::WhereReferencedOutput[] | List of information containing reference, relation name and level for input object |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

#### 3.2.11 whereUsed（2007-01）

**接口路径：** `Core-2007-01-DataManagement/whereUsed`

**API 版本：** `2007-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 查询指定对象在结构或关系中的使用位置（Where Used）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.DataManagement.whereUsed`

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
  "numLevels": "",
  "whereUsedPrecise": "",
  "rule": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | List of object references on which to perform the <font face="courier" height="10">whereUsed</font> search. It is a requ |
| `numLevels` | int | Number of levels to traverse in the <font face="courier" height="10">whereUsed</font> search and return |
| `whereUsedPrecise` | bool | Boolean representing whether to only send back precise parents ( used by <b>ItemRevision</b> specifically and not <b>Ite |
| `rule` | Teamcenter::BusinessObject | <b>RevisionRule</b> used get unique configured <b>ItemRevision</b> from each level of <font face="courier" height="10">w |

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
      "info": [
        {
          "parentItemRev": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "level": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2007_01::DataManagement::WhereUsedOutput[] | List of WhereUsedOutput structures |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

#### 3.2.12 getTransientFileTicketsForUpload（2007-01）

**接口路径：** `Core-2007-01-FileManagement/getTransientFileTicketsForUpload`

**API 版本：** `2007-01`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 此操作 获取 the tickets for the desired files to be uploaded to the transient volume. These tickets can be used to upload corresponding files via FileManagementUtility::putFileViaTicket. The TransientFileInfo contains the basic information for a file to be uploaded such as file name, file type and whether the file should be deleted after reading.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.FileManagement.getTransientFileTicketsForUpload`

**请求（input）：**

```json
{
  "transientFileInfos": [
    {
      "fileName": "",
      "isBinary": "",
      "deleteFlag": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `transientFileInfos` | Teamcenter::Soa::Core::_2007_01::FileManagement::TransientFileInfo[] | List containing the details of the files for which the tickets are requested. |

**响应（output）：**

```json
{
  "transientFileTicketInfos": [
    {
      "transientFileInfo": {
        "fileName": "",
        "isBinary": "",
        "deleteFlag": ""
      },
      "ticket": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `transientFileTicketInfos` | Teamcenter::Soa::Core::_2007_01::FileManagement::TransientFileTicketInfo[] | The requested transient files ticket information. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This contains the status of the operation. |

---

#### 3.2.13 createRelation（2007-01）

**接口路径：** `Core-2007-01-ManagedRelations/createRelation`

**API 版本：** `2007-01`  
**Service：** `ManagedRelations`  
**Library：** `Core`

**说明：** 此操作 will create new managed relation

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.ManagedRelations.createRelation`

**请求（input）：**

```json
{
  "relationinfo": [
    {
      "name": "",
      "type": "",
      "primaryTagList": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "secondaryTagList": [
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
| `relationinfo` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::CreateManagedRelationInput[] | input information required to create managed relation |

**响应（output）：**

```json
{
  "managedRelationObjects": [
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
| `managedRelationObjects` | Teamcenter::TraceLink[] | List of Managed Relation Objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |

---

#### 3.2.14 getTraceReport（2007-01）

**接口路径：** `Core-2007-01-ManagedRelations/getTraceReport`

**API 版本：** `2007-01`  
**Service：** `ManagedRelations`  
**Library：** `Core`

**说明：** 此操作 will create traceability report for the selected TC object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.ManagedRelations.getTraceReport`

**请求（input）：**

```json
{
  "input": {
    "inputTag": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "reportType": "",
    "reportDepth": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::TraceabilityInfoInput | information required to create report |

**响应（output）：**

```json
{
  "definingTree": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "children": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "indirectDefiningTree": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "children": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "complyingTree": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "children": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "indirectComplyingTree": [
    {
      "parent": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "children": [
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
| `definingTree` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::DefiningReport[] | List of Defining Reports |
| `indirectDefiningTree` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::DefiningReport[] | List of Defining Reports (Indirect) |
| `complyingTree` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::ComplyingReport[] | List of Complying Reports |
| `indirectComplyingTree` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::ComplyingReport[] | List of Complying Reports (Indirect) |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |

---

#### 3.2.15 modifyRelation（2007-01）

**接口路径：** `Core-2007-01-ManagedRelations/modifyRelation`

**API 版本：** `2007-01`  
**Service：** `ManagedRelations`  
**Library：** `Core`

**说明：** 此操作 will Edit the managed relation

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.ManagedRelations.modifyRelation`

**请求（input）：**

```json
{
  "newInput": [
    {
      "relationTag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "setSourcesInput": {
        "addSources": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "removeSources": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      },
      "setTargetsInput": {
        "addTargets": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "removeTargets": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ]
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `newInput` | Teamcenter::Soa::Core::_2007_01::ManagedRelations::ModifyManagedRelationInput[] | will have the modification info for given relation |

**响应（output）：**

```json
{
  "managedRelationObjects": [
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
| `managedRelationObjects` | Teamcenter::TraceLink[] | List of Managed Relation Objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |

---

#### 3.2.16 getPreferences（2007-01）

**接口路径：** `Core-2007-01-Session/getPreferences`

**API 版本：** `2007-01`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取用户或站点偏好设置。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.Session.getPreferences`

**请求（input）：**

```json
{
  "requestedPrefs": [
    {
      "scope": "",
      "names": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `requestedPrefs` | Teamcenter::Soa::Core::_2007_01::Session::ScopedPreferenceNames[] | vector of PrefSetting structures, which specify the scope name for each of the preferences to be set. |

**响应（output）：**

```json
{
  "preferences": [
    {
      "name": "",
      "scope": "",
      "values": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `preferences` | Teamcenter::Soa::Core::_2007_01::Session::ReturnedPreferences[] | List of Returned Preferences |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |

---

#### 3.2.17 getTCSessionInfo（2007-01）

**接口路径：** `Core-2007-01-Session/getTCSessionInfo`

**API 版本：** `2007-01`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取当前用户会话详细信息（用户、组、角色、站点、卷、项目、工作上下文等）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.Session.getTCSessionInfo`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "serverVersion": "",
  "transientVolRootDir": "",
  "site": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "bypass": "",
  "journaling": "",
  "appJournaling": "",
  "secJournaling": "",
  "admJournaling": "",
  "privileged": "",
  "isPartBOMUsageEnabled": "",
  "isSubscriptionMgrEnabled": "",
  "textInfos": [
    {
      "realName": "",
      "displayName": ""
    }
  ],
  "isInV7Mode": "",
  "extraInfo": {},
  "serviceData": "IServiceData",
  "moduleNumber": "",
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
  "tcVolume": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "project": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "workContext": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serverVersion` | std::string | The version of the server. |
| `transientVolRootDir` | std::string | Path to the root folder of the transient volume. |
| `site` | Teamcenter::POM_imc | The site object for this session |
| `bypass` | bool | True if bypass is enabled. |
| `journaling` | bool | True if journaling is enabled. |
| `appJournaling` | bool | True if application journaling is enabled. |
| `secJournaling` | bool | True if sec journaling is enabled. |
| `admJournaling` | bool | True if administration journaling is enabled. |
| `privileged` | bool | True if the user is privileged. |
| `isPartBOMUsageEnabled` | bool | True if the Part BOM Usage is enabled. |
| `isSubscriptionMgrEnabled` | bool | True if the Subscription Manager is enabled. |
| `textInfos` | Teamcenter::Soa::Core::_2007_01::Session::TextInfo[] | textInfos |
| `isInV7Mode` | bool | True if the server is operating in V7 mode. |
| `extraInfo` | Teamcenter::Soa::Core::_2007_01::Session::ExtraInfo | Map of kev/value pairs (string/string).The following keys are returned:<br /><ul><ul><li type="disc"><i>TcServerIDUnique |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | serviceData |
| `moduleNumber` | int | This element is not to be used anymore and always returns a -1. |
| `user` | Teamcenter::User | The <b>User</b> object for this session. |
| `group` | Teamcenter::Group | The <b>Group</b> object for this session. |
| `role` | Teamcenter::Role | The <b>Role</b> object for this session. |
| `tcVolume` | Teamcenter::ImanVolume | The <b>ImanVolume</b> object for this session. |
| `project` | Teamcenter::TC_Project | The <b>Project</b> object for this session. |
| `workContext` | Teamcenter::TC_WorkContext | The <b>WorkContext</b> object for this session. |

---

#### 3.2.18 setObjectPropertyPolicy（2007-01）

**接口路径：** `Core-2007-01-Session/setObjectPropertyPolicy`

**API 版本：** `2007-01`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 设置对象属性策略（Property Policy），控制返回哪些属性。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_01.Session.setObjectPropertyPolicy`

**请求（input）：**

```json
{
  "policyName": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policyName` | std::string | The name of the policy file without the <font face="courier" height="10">.xml </font>extension. The file must exist on t |

**响应（output）：**

```json
"bool"
```

---

### 3.3 API 版本 2007-06

**Service：** DataManagement、LOV、PropDescriptor、Session  **操作数：** 11

#### 3.3.1 expandGRMRelationsForPrimary（2007-06）

**接口路径：** `Core-2007-06-DataManagement/expandGRMRelationsForPrimary`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从主对象展开 GRM（全局关系模型）关系。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.expandGRMRelationsForPrimary`

**请求（input）：**

```json
{
  "primaryObjects": [
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
| `primaryObjects` | Teamcenter::BusinessObject[] | A Vector of Teamcenter primary objects |
| `pref` | Teamcenter::Soa::Core::_2007_06::DataManagement::ExpandGRMRelationsPref | Expand GRM Relations Preference |

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
| `output` | Teamcenter::Soa::Core::_2007_06::DataManagement::ExpandGRMRelationsOutput[] | List of SaveQueryCriteriaInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |

---

#### 3.3.2 expandGRMRelationsForSecondary（2007-06）

**接口路径：** `Core-2007-06-DataManagement/expandGRMRelationsForSecondary`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从次对象展开 GRM 关系。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.expandGRMRelationsForSecondary`

**请求（input）：**

```json
{
  "secondaryObjects": [
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
| `secondaryObjects` | Teamcenter::BusinessObject[] | A Vector of Teamcenter secondary objects |
| `pref` | Teamcenter::Soa::Core::_2007_06::DataManagement::ExpandGRMRelationsPref | Expand GRM Relations Preference |

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
| `output` | Teamcenter::Soa::Core::_2007_06::DataManagement::ExpandGRMRelationsOutput[] | List of SaveQueryCriteriaInfo |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |

---

#### 3.3.3 getAvailableTypes（2007-06）

**接口路径：** `Core-2007-06-DataManagement/getAvailableTypes`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：获取Available Types。This will return type names implemented by the given classes. This is lightweight way to get all displayable types by name rather than model object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.getAvailableTypes`

**请求（input）：**

```json
{
  "classes": [
    {
      "baseClass": "",
      "exclusionTypes": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `classes` | Teamcenter::Soa::Core::_2007_06::DataManagement::BaseClassInput[] | A list of given base class name and exclusion list. |

**响应（output）：**

```json
{
  "inputClassToTypes": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputClassToTypes` | Teamcenter::Soa::Core::_2007_06::DataManagement::ClassToTypesMap | A map of given class names and all according AvailableTypeInfo objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData contains any parital error if any failure happens. |

---

#### 3.3.4 getDatasetTypeInfo（2007-06）

**接口路径：** `Core-2007-06-DataManagement/getDatasetTypeInfo`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 the named reference information for a set of 数据集 types. Named references are Teamcenter objects that relate to a specific data file. Any failure that occurs during 此操作 is returned in the ServiceData list of partial errors with the 数据集 type name string mapped to error message.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.getDatasetTypeInfo`

**请求（input）：**

```json
{
  "datasetTypeNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `datasetTypeNames` | std::string[] | List of dataset type names used to get the named reference information. An empty list will return information for all da |

**响应（output）：**

```json
{
  "infos": [
    {
      "tag": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "refInfos": [
        {
          "referenceName": "",
          "isObject": "",
          "fileFormat": "",
          "fileExtension": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `infos` | Teamcenter::Soa::Core::_2007_06::DataManagement::DatasetTypeInfo[] | List of named reference information for each dataset type specified in <font face=&quot;courier&quot; height=&quot;10&qu |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font fac |

---

#### 3.3.5 purgeSequences（2007-06）

**接口路径：** `Core-2007-06-DataManagement/purgeSequences`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `purgeSequences`。Given a list of ItemRevision sequences, this opertion is used ot perform per the following criteria: If the input object is the latest sequence of an ItemRevision, all previous sequences will be purged. If the input object is not the latest sequence of the ItemRevision and the validateLatestFlag is false, the input object will be purged.If the input object is not the latest …

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.purgeSequences`

**请求（input）：**

```json
{
  "objects": [
    {
      "validateLatestFlag": "",
      "inputObject": {
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
| `objects` | Teamcenter::Soa::Core::_2007_06::DataManagement::PurgeSequencesInfo[] | A list of the objects to be purged and a flag noting whether to validate the object is the latest sequence. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.3.6 setOrRemoveImmunity（2007-06）

**接口路径：** `Core-2007-06-DataManagement/setOrRemoveImmunity`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 is used to add or remove immunity for each object in the input list according to the value of the associated setOrRemoveFlag. A value of true indicates to apply immunity to the object. A value of false indicates that immunity should be removed from the object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.setOrRemoveImmunity`

**请求（input）：**

```json
{
  "objects": [
    {
      "setOrRemoveFlag": "",
      "inputObject": {
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
| `objects` | Teamcenter::Soa::Core::_2007_06::DataManagement::SetOrRemoveImmunityInfo[] | A list of the <b>ItemRevision</b> sequence objects and a flag set true or false. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.3.7 validateItemIdsAndRevIds（2007-06）

**接口路径：** `Core-2007-06-DataManagement/validateItemIdsAndRevIds`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 校验 Item 编号与版本号是否合法/可用。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.validateItemIdsAndRevIds`

**请求（input）：**

```json
{
  "infos": [
    {
      "itemId": "{{ITEM_ID}}",
      "revId": "",
      "itemType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `infos` | Teamcenter::Soa::Core::_2007_06::DataManagement::ValidateIdsInfo[] | A List of item IDs, revision IDs, and item type for validation.<br /> |

**响应（output）：**

```json
{
  "output": [
    {
      "modItemId": "",
      "itemIdStatus": "Valid",
      "modRevId": "",
      "revIdStatus": "Valid"
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2007_06::DataManagement::ValidateIdsOutput[] | List of <font face=&quot;courier&quot; height=&quot;10&quot;>ValidateIdsOutput</font> structures |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData contains only error information returned by this operation. |

---

#### 3.3.8 whereReferencedByRelationName（2007-06）

**接口路径：** `Core-2007-06-DataManagement/whereReferencedByRelationName`

**API 版本：** `2007-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `whereReferencedByRelationName`。Finds the objects that reference a given object by a specific relation. The input object will be the secondary object for that relation. It does not return relations where the given input object is the primary object for the relation. The Datamanagement service operation expandGRMRelationsForPrimary can be used to return the relations where the input object is the primary ob…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.DataManagement.whereReferencedByRelationName`

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
      "filter": [
        {
          "relationTypeName": "",
          "otherSideObjectTypes": [
            ""
          ]
        }
      ]
    }
  ],
  "numLevels": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2007_06::DataManagement::WhereReferencedByRelationNameInfo[] | A list of desired business objects and filters to find the referencing objects for |
| `numLevels` | int | The number of levels to search.  For example, if A references B, and B references C, a 1-level search from C produces ju |

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
      "info": [
        {
          "referencer": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationTypeName": "",
          "level": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2007_06::DataManagement::WhereReferencedByRelationNameOutput[] | A list of filtered referencing objects for each input object |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

#### 3.3.9 getAttachedLOVs（2007-06）

**接口路径：** `Core-2007-06-LOV/getAttachedLOVs`

**API 版本：** `2007-06`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 值列表（LOV）：获取Attached L O Vs。Get attached LOV based on input type name and 属性 names structure. The LOV Tag is returned in the response and service data.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.LOV.getAttachedLOVs`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2007_06::LOV::LOVInfo[] | - vector of structure of LOVInfo with type name and property names vector. |

**响应（output）：**

```json
{
  "inputTypeNameToLOVOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputTypeNameToLOVOutput` | Teamcenter::Soa::Core::_2007_06::LOV::InputTypeNameToLOVOutputMap | Map of input type name to LOVOutput |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData which has output tags as plain objects and errors in partialError |

---

#### 3.3.10 getAttachedPropDescs（2007-06）

**接口路径：** `Core-2007-06-PropDescriptor/getAttachedPropDescs`

**API 版本：** `2007-06`  
**Service：** `PropDescriptor`  
**Library：** `Core`

**说明：** Get the attached 属性 descriptor based on input type name and 属性 names structure.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.PropDescriptor.getAttachedPropDescs`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2007_06::PropDescriptor::PropDescInfo[] | - vector of structure of PropDescInfo with type name and property names vector. |

**响应（output）：**

```json
{
  "inputTypeNameToPropDescOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputTypeNameToPropDescOutput` | Teamcenter::Soa::Core::_2007_06::PropDescriptor::InputTypeNameToPropDescOutputMap | Map of input type name to PropertyDescriptor |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData which has output tags as plain objects and errors in partialError |

---

#### 3.3.11 refreshPOMCachePerRequest（2007-06）

**接口路径：** `Core-2007-06-Session/refreshPOMCachePerRequest`

**API 版本：** `2007-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `refreshPOMCachePerRequest`。By Default the service operations will retrieve 属性 value data straight from the POM. When refresh is set to true, a refresh will be done on 业务对象 before getting any 属性 data. This will update the POM with fresh data from the database. The refresh is only applied to 业务对象 that are actually being returned by a service operation. This applies on…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_06.Session.refreshPOMCachePerRequest`

**请求（input）：**

```json
{
  "refresh": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `refresh` | bool | If true, the business objects are refreshed before getting property values, if false the properties are retrieved from t |

**响应（output）：**

```json
"bool"
```

---

### 3.4 API 版本 2007-09

**Service：** DataManagement、ProjectLevelSecurity  **操作数：** 5

#### 3.4.1 expandGRMRelationsForPrimary（2007-09）

**接口路径：** `Core-2007-09-DataManagement/expandGRMRelationsForPrimary`

**API 版本：** `2007-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从主对象展开 GRM（全局关系模型）关系。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_09.DataManagement.expandGRMRelationsForPrimary`

**请求（input）：**

```json
{
  "primaryObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "pref": {
    "expItemRev": "",
    "returnRelations": "",
    "info": [
      {
        "relationTypeName": "",
        "otherSideObjectTypes": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `primaryObjects` | Teamcenter::BusinessObject[] | The list of Teamcenter primary objects. |
| `pref` | Teamcenter::Soa::Core::_2007_09::DataManagement::ExpandGRMRelationsPref2 | The structure for setting specific preference input used by this operation. |

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
      "relationshipData": [
        {
          "relationshipObjects": [
            {
              "otherSideObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "relation": {
                "uid": "",
                "type": "",
                "className": ""
              }
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
| `output` | Teamcenter::Soa::Core::_2007_09::DataManagement::ExpandGRMRelationsOutput2[] | The list of input objects and the found related side objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font fac |

---

#### 3.4.2 expandGRMRelationsForSecondary（2007-09）

**接口路径：** `Core-2007-09-DataManagement/expandGRMRelationsForSecondary`

**API 版本：** `2007-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从次对象展开 GRM 关系。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_09.DataManagement.expandGRMRelationsForSecondary`

**请求（input）：**

```json
{
  "secondaryObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "pref": {
    "expItemRev": "",
    "returnRelations": "",
    "info": [
      {
        "relationTypeName": "",
        "otherSideObjectTypes": [
          ""
        ]
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `secondaryObjects` | Teamcenter::BusinessObject[] | The list of Teamcenter secondary objects. |
| `pref` | Teamcenter::Soa::Core::_2007_09::DataManagement::ExpandGRMRelationsPref2 | The structure for setting specific preference input used by this operation. |

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
      "relationshipData": [
        {
          "relationshipObjects": [
            {
              "otherSideObject": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "relation": {
                "uid": "",
                "type": "",
                "className": ""
              }
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
| `output` | Teamcenter::Soa::Core::_2007_09::DataManagement::ExpandGRMRelationsOutput2[] | The list of input objects and the found related side objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face=&quot;courier&quot; height=&quot;10&quot;>ServiceData</font>.  This operation will populate the <font fac |

---

#### 3.4.3 loadObjects（2007-09）

**接口路径：** `Core-2007-09-DataManagement/loadObjects`

**API 版本：** `2007-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从服务器加载业务对象到会话。

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_09.DataManagement.loadObjects`

**请求（input）：**

```json
{
  "uids": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `uids` | std::string[] | An array of UIDs. These UID may come from an outside source or from other service operations such as executeSavedQuery. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.4.4 removeNamedReferenceFromDataset（2007-09）

**接口路径：** `Core-2007-09-DataManagement/removeNamedReferenceFromDataset`

**API 版本：** `2007-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 removes the specified named references from a 数据集. If the NamedReferenceInfo.targetObject input is not specified then all named references of the type specified are removed from the 数据集. If the NamedReferenceInfo.targetObject input is specified then only that named reference is removed from the 数据集. If the NamedReferenceInfo.deleteTarget input is t…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_09.DataManagement.removeNamedReferenceFromDataset`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "nrInfo": [
        {
          "clientId": "",
          "type": "",
          "targetObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "deleteTarget": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2007_09::DataManagement::RemoveNamedReferenceFromDatasetInfo[] | A list of datasets and the named references to be removed from the datasets. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.4.5 assignOrRemoveObjects（2007-09）

**接口路径：** `Core-2007-09-ProjectLevelSecurity/assignOrRemoveObjects`

**API 版本：** `2007-09`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 assigns the given set of workspace objects to the given projects. Similarly, it removes an additional set of given workspace objects from the same set of given projects. If user is not privileged to assign objects to any of the given projects then 此操作 will return the error 101014 : You have insufficient privilege to assign object to a project. Simil…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_09.ProjectLevelSecurity.assignOrRemoveObjects`

**请求（input）：**

```json
{
  "assignedOrRemovedobjects": [
    {
      "projects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "objectToAssign": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "objectToRemove": [
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
| `assignedOrRemovedobjects` | Teamcenter::Soa::Core::_2007_09::ProjectLevelSecurity::AssignedOrRemovedObjects[] | A list of AssignedOrRemovedObjects. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.5 API 版本 2007-12

**Service：** DataManagement、Session  **操作数：** 6

#### 3.5.1 createAlternateIdentifiers（2007-12）

**接口路径：** `Core-2007-12-DataManagement/createAlternateIdentifiers`

**API 版本：** `2007-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：创建Alternate Identifiers。Create new alternate identifiers. Given an IdContext, an IdentifierType and an Item ( and optionally an ItemRevision ), create an Identifier object to display an option part number when the IdContext is valid.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.DataManagement.createAlternateIdentifiers`

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
      "identifierType": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "mainObject": {
        "identifiableObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "alternateId": "",
        "additionalProps": {},
        "makeDefault": ""
      },
      "revObject": {
        "identifiableObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "alternateId": "",
        "additionalProps": {},
        "makeDefault": ""
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2007_12::DataManagement::AlternateIdentifiersInput[] | A list of AlternateIdentifiersInput containing details of alternate identifiers to be created. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.5.2 getContextsAndIdentifierTypes（2007-12）

**接口路径：** `Core-2007-12-DataManagement/getContextsAndIdentifierTypes`

**API 版本：** `2007-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 返回 the context and identifier types for the supplied identifiable types.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.DataManagement.getContextsAndIdentifierTypes`

**请求（input）：**

```json
{
  "typeTags": [
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
| `typeTags` | Teamcenter::ImanType[] | A list of <b>ImanType</b> objects. |

**响应（output）：**

```json
{
  "contextAndIdentifierTypesMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `contextAndIdentifierTypesMap` | Teamcenter::Soa::Core::_2007_12::DataManagement::ContextAndIdentifierTypesMap | A map of context and identifier types for each requested <b>ImanType</b> (<b>ImanType</b>/<font face="courier" height="1 |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data associated with the call |

---

#### 3.5.3 listAlternateIdDisplayRules（2007-12）

**接口路径：** `Core-2007-12-DataManagement/listAlternateIdDisplayRules`

**API 版本：** `2007-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `listAlternateIdDisplayRules`。Return the current display rule. If the current user flag is set then also return the display rules for the current user. If a list of users is supplied, then return the display rules for the list of users; otherwise return the display rules for all users.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.DataManagement.listAlternateIdDisplayRules`

**请求（input）：**

```json
{
  "input": {
    "users": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "currentUser": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2007_12::DataManagement::ListAlternateIdDisplayRulesInfo | A <font face="courier" height="10">ListAlternateIdDisplayRulesInfo</font> data structure. |

**响应（output）：**

```json
{
  "userDisplayRuleMaps": {},
  "currentRuleInDB": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `userDisplayRuleMaps` | Teamcenter::Soa::Core::_2007_12::DataManagement::UserDisplayRuleMap | A list of maps of <font face="courier" height="10">Teamcenter::UserImpl</font> to <font face="courier" height="10">IdDis |
| `currentRuleInDB` | Teamcenter::IdDispRule | The current rule in the database ( valid for current user only ). |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">ServiceData</font> associated with the call. |

---

#### 3.5.4 validateAlternateIds（2007-12）

**接口路径：** `Core-2007-12-DataManagement/validateAlternateIds`

**API 版本：** `2007-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：校验Alternate Ids。Determines if the supplied alternateIds are valid. The USER exit USER_validate_alt_id is used for validation. A "modified" alternate id is returned. If the alternate id supplied is valid then the modified one returned is the same as the one supplied. If the alternate id supplied is not valid, then the one returned is a valid one.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.DataManagement.validateAlternateIds`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "alternateId": "",
      "alternateRevId": "",
      "patternName": "",
      "context": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "identifierType": {
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
| `inputs` | Teamcenter::Soa::Core::_2007_12::DataManagement::ValidateAlternateIdInput[] | A list of <font face="courier" height="10">ValidateAlternateIdInput</font> data structures. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "modifiedAltId": "",
      "modifiedAltRevId": "",
      "validityId": "Valid",
      "validityRevId": "Valid"
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2007_12::DataManagement::ValidateAlternateIdOutput[] | List of <font face="courier" height="10">ValidateAlternateIdOutput</font>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">ServiceData</font> will contain the objects that are returned by the service call.  |

---

#### 3.5.5 setAndEvaluateIdDisplayRule（2007-12）

**接口路径：** `Core-2007-12-Session/setAndEvaluateIdDisplayRule`

**API 版本：** `2007-12`  
**Service：** `Session`  
**Library：** `Core`

**说明：** Set the ID display rule for the 会话 and optionally set it in the database. The 业务对象 from the identifiableObjects list are expanded using the new ID display rule and returned. The rule is applied to all 业务对象 process throughout the rest of the 会话.

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.Session.setAndEvaluateIdDisplayRule`

**请求（input）：**

```json
{
  "identifiableObjects": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "displayRule": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "setRuleAsCurrentInDB": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `identifiableObjects` | Teamcenter::BusinessObject[] | A list of business objects for which the new ID display rule has to be re-evaluated. |
| `displayRule` | Teamcenter::IdDispRule | The ID display rule that is to be used for evaluation. |
| `setRuleAsCurrentInDB` | bool | If true then the ID display rule will be set for the current user in the database. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.5.6 setUserSessionState（2007-12）

**接口路径：** `Core-2007-12-Session/setUserSessionState`

**API 版本：** `2007-12`  
**Service：** `Session`  
**Library：** `Core`

**说明：** Set the desired user 会话 state values. To clear a field's value, pass an empty string "" as the value. Failure to set a particular state value will result in a Partial Error with the clientId set to the name of the state 属性. State values can be per client 会话 or per server 会话. Client 会话 state is kept separate for each 客户端应用 sharing the sa…

**Soa Inclusion：** `Teamcenter.Soa.Core._2007_12.Session.setUserSessionState`

**请求（input）：**

```json
{
  "pairs": [
    {
      "name": "",
      "value": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `pairs` | Teamcenter::Soa::Core::_2007_12::Session::StateNameValue[] | A list of name/value pairs of state properties to set. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.6 API 版本 2008-03

**Service：** Session  **操作数：** 3

#### 3.6.1 connect（2008-03）

**接口路径：** `Core-2008-03-Session/connect`

**API 版本：** `2008-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `connect`。Performs Teamcenter Flexlm license related operations, depending on the input parameters. The low level actions are: 1. ILM__init_module: Initializes the license module (if it has not already been initialized). 2. ILM__leave_module: Deallocates a license of the given module. If the user had N free licenses for this module, (N plus one) will be left after this call. 3. ILM__c…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_03.Session.connect`

**请求（input）：**

```json
{
  "featureKey": "",
  "action": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `featureKey` | std::string | A string corresponding to the product as listed in the license file (e.g. teamcenter_author) |
| `action` | std::string | A string corresponding to the desired action. Valid values are:<br />1.   init: Performs the ILM__init_module action (co |

**响应（output）：**

```json
{
  "outputVal": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `outputVal` | int | The number of available licenses for the specified featureKey parameter. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData structure contains these potential error numbers:<br />&nbsp;&nbsp;&nbsp;&nbsp;  214401: The initializat |

---

#### 3.6.2 getFavorites（2008-03）

**接口路径：** `Core-2008-03-Session/getFavorites`

**API 版本：** `2008-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取当前用户收藏的业务对象列表。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_03.Session.getFavorites`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "output": {
    "containers": [
      {
        "clientId": "",
        "id": "",
        "type": "",
        "displayName": "",
        "parentId": ""
      }
    ],
    "objects": [
      {
        "clientId": "",
        "objectTag": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayName": "",
        "parentId": ""
      }
    ]
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_03::Session::FavoritesList | List of favorite containers and favorite objects for the current session user. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The service data. This operation will populate the Service Data plain objects list with the Favorite containers and obje |

---

#### 3.6.3 setFavorites（2008-03）

**接口路径：** `Core-2008-03-Session/setFavorites`

**API 版本：** `2008-03`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 保存 new favorite containers and favorite objects for the current 会话 user. Any partial errors encountered during 此操作 are returned using the clientID specified by the caller. A service exception is thrown if an error is encountered that is not related to a specific favorite container or favorite object. You can use favorites to track containers…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_03.Session.setFavorites`

**请求（input）：**

```json
{
  "input": {
    "curFavorites": {
      "containers": [
        {
          "clientId": "",
          "id": "",
          "type": "",
          "displayName": "",
          "parentId": ""
        }
      ],
      "objects": [
        {
          "clientId": "",
          "objectTag": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "displayName": "",
          "parentId": ""
        }
      ]
    },
    "newFavorites": {
      "containers": [
        {
          "clientId": "",
          "id": "",
          "type": "",
          "displayName": "",
          "parentId": ""
        }
      ],
      "objects": [
        {
          "clientId": "",
          "objectTag": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "displayName": "",
          "parentId": ""
        }
      ]
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_03::Session::FavoritesInfo | The information required to establish a new set of saved favorites for the current session user. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.7 API 版本 2008-05

**Service：** DataManagement  **操作数：** 1

#### 3.7.1 unloadObjects（2008-05）

**接口路径：** `Core-2008-05-DataManagement/unloadObjects`

**API 版本：** `2008-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 从会话中卸载业务对象。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_05.DataManagement.unloadObjects`

**请求（input）：**

```json
{
  "objsToUnload": [
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
| `objsToUnload` | Teamcenter::BusinessObject[] | A list of model objects to unload. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.8 API 版本 2008-06

**Service：** DataManagement、DispatcherManagement、ManagedRelations、PropDescriptor、Reservation、Session、StructureManagement  **操作数：** 27

#### 3.8.1 addParticipants（2008-06）

**接口路径：** `Core-2008-06-DataManagement/addParticipants`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 创建 the Participant objects and adds them to the input Item 版本. If a Participant object with specified attributes already exists, it is added to the Item 版本.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.addParticipants`

**请求（input）：**

```json
{
  "addParticipantInfo": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "participantInfo": [
        {
          "assignee": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "participantType": "",
          "clientId": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `addParticipantInfo` | Teamcenter::Soa::Core::_2008_06::DataManagement::AddParticipantInfo[] | Contains a list of <font face="courier" height="10">ParticipantInfo</font> structures with information about participant |

**响应（output）：**

```json
{
  "participantOutput": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "participant": [
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
| `participantOutput` | Teamcenter::Soa::Core::_2008_06::DataManagement::Participants[] | List of structures containing the participants and the object to which participants are added. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The service data. |

---

#### 3.8.2 createConnections（2008-06）

**接口路径：** `Core-2008-06-DataManagement/createConnections`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建 a list of Connection objects and any associated data (ConnectionRevision, ConnectionMaster Form and ConnectionRevision Master Form) based on the input 属性 structure. It also 创建 the specified relation type between newly created Connection object and input container object. If container and relation type are not supplied, none of the Connection objects will…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createConnections`

**请求（input）：**

```json
{
  "properties": [
    {
      "clientId": "",
      "connId": "",
      "name": "",
      "type": "",
      "revId": "",
      "description": "",
      "extendedAttributes": [
        {
          "objectType": "",
          "attributes": {}
        }
      ]
    }
  ],
  "container": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "relationType": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `properties` | Teamcenter::Soa::Core::_2008_06::DataManagement::ConnectionProperties[] | A <b>Connection</b> object is created for each ConnectionProperties in the list. The data on the ConnectionProperties is |
| `container` | Teamcenter::BusinessObject | Object to which all the <b>Connection</b> objects created will be related to via the input relationType (Folder instance |
| `relationType` | std::string | The name of the relation used to attach the created <b>Connection</b> objects to input container. This argument is used  |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "output": [
    {
      "clientId": "",
      "connection": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "connectionRev": {
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
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::ConnectionOutput[] | A list of created <b>Connection</b> objects and associate <b>ConnectionRevision</b> in the form of ConnectionsOutput str |

---

#### 3.8.3 createDatasets2（2008-06）

**接口路径：** `Core-2008-06-DataManagement/createDatasets2`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 创建 a list of 数据集 objects and 创建 the specified relation type between created 数据集 and input container object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createDatasets2`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "type": "",
      "name": "",
      "description": "",
      "toolUsed": "",
      "datasetId": "",
      "datasetRev": "",
      "container": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_06::DataManagement::DatasetProperties2[] | The information needed to create  <b>Dataset</b> |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "dataset": {
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
| `output` | Teamcenter::Soa::Core::_2006_03::DataManagement::CreateDatasetsOutput[] | A list of created <b>Dataset</b> output |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

#### 3.8.4 createObjects（2008-06）

**接口路径：** `Core-2008-06-DataManagement/createObjects`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 按类型批量创建业务对象（通用创建接口）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "data": {
        "boName": "",
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateIn[] | This is a vector of CreateIn objects each one of which represents the CreateInput information used to create an object.  |

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOut[] | Vector of output objects representing objects that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data including partial errors that are mapped to the client id from the input. Created objects are also added to |

---

#### 3.8.5 createOrUpdateGDELinks（2008-06）

**接口路径：** `Core-2008-06-DataManagement/createOrUpdateGDELinks`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：创建Or Update G D E Links。Create and/or update GeneralDesignElementLink(GDELink) objects based on the input 属性 structure. If the given GDELink object exists in Teamcenter then 该操作 will be treated as an update based on the input 属性 structure

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createOrUpdateGDELinks`

**请求（input）：**

```json
{
  "gdeLinkInfos": [
    {
      "clientID": "",
      "name": "",
      "description": "",
      "type": "",
      "gdeLink": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "attributes": [
        {
          "name": "",
          "values": [
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
| `gdeLinkInfos` | Teamcenter::Soa::Core::_2008_06::DataManagement::GDELinkInfo[] | An input of vector of structures containing values necessary to create or update the Teamcenter Model Data representing  |

**响应（output）：**

```json
{
  "successfullyProcessedGDELinks": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `successfullyProcessedGDELinks` | Teamcenter::Soa::Core::_2008_06::DataManagement::SuccessfullyProcessedGDELinksMap | A map containing the clientIds and the successfully created/updated <b>GeneralDesignElementLink</b> objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data to report partial errors. |

---

#### 3.8.6 createOrUpdateItemElements（2008-06）

**接口路径：** `Core-2008-06-DataManagement/createOrUpdateItemElements`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：创建Or Update Item Elements。Allows the user to create a new GeneralDesignElement (GDE) or its subtype and set its 属性. In the case of existing GDE, user can update the 属性.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createOrUpdateItemElements`

**请求（input）：**

```json
{
  "properties": [
    {
      "clientId": "",
      "name": "",
      "type": "",
      "description": "",
      "itemElemAttributes": {},
      "itemElement": {
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
| `properties` | Teamcenter::Soa::Core::_2008_06::DataManagement::ItemElementProperties[] | This is a vector of <i>ItemElementProperties</i>. While creating a new element it shall contain a unique clientId, name  |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "output": [
    {
      "clientId": "",
      "itemElem": {
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
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member containing created/updated objects and partial errors if any |
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::ItemElementsOutput[] | A list of createItemElementsOutput |

---

#### 3.8.7 createOrUpdateRelations（2008-06）

**接口路径：** `Core-2008-06-DataManagement/createOrUpdateRelations`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建 the specified relation between the input objects (primary and secondary objects) for each input structure. If the sync flag is specified, then if any Generic Relationship Management (GRM) relations exist between the primary and secondary objects and they are not specified in the input they will be deleted. If sync flag is provided, the relations member of CreateOrUpd…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.createOrUpdateRelations`

**请求（input）：**

```json
{
  "infos": [
    {
      "clientId": "",
      "relationType": "",
      "primaryObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "secondaryData": [
        {
          "clientId": "",
          "secondary": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "userData": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "properties": [
            {
              "name": "",
              "values": [
                ""
              ]
            }
          ]
        }
      ],
      "relations": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "sync": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `infos` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOrUpdateRelationsInfo[] | A list of <font face="courier" height="10">CreateOrUpdateRelationsInfo</font> structures containing details of relations |
| `sync` | bool | If true then GRM relations in db and the number of secondary objects specified in the <font face="courier" height="10">i |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "relations": [
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
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOrUpdateRelationsOutput[] | A list of <font face="courier" height="10">CreateOrUpdateRelationsOutput</font> |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> object to hold the partial errors that the operation encoun |

---

#### 3.8.8 findDisplayableSubBusinessObjects（2008-06）

**接口路径：** `Core-2008-06-DataManagement/findDisplayableSubBusinessObjects`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** Operation to retrieve sub 业务对象 Names for a 业务对象 that are displayable to the login user in the object creation dialog. e.g File-new, select Item, what types to be displayed for Item

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.findDisplayableSubBusinessObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "boTypeName": "",
      "exclusionBOTypeNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_06::DataManagement::BOWithExclusionIn[] | - a list of input objects representing the BO type names for which the displayable types are to be retrieved |

**响应（output）：**

```json
{
  "output": [
    {
      "boTypeName": "",
      "displayableBOTypeNames": [
        {
          "BOName": "",
          "BOParents": [
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
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::DisplayableBOsOut[] | Vector of output objects representing displayable types during create of a BO |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data including partial errors that are mapped to the input BO type name |

---

#### 3.8.9 getItemAndRelatedObjects（2008-06）

**接口路径：** `Core-2008-06-DataManagement/getItemAndRelatedObjects`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 Items, ItemRevisions, 数据集 and NamedReference information based on the input. Input is a list of GetItemAndRelatedObjectsInfo structures each of which contains item uid or id, revison information and optionally a list of filters to determine the 数据集s to be returned. For the 数据集s the client can request information about the NamedReferences. N…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.getItemAndRelatedObjects`

**请求（input）：**

```json
{
  "infos": [
    {
      "clientId": "",
      "itemInfo": {
        "clientId": "",
        "useIdFirst": "",
        "uid": "",
        "ids": [
          {
            "name": "",
            "value": ""
          }
        ]
      },
      "revInfo": {
        "clientId": "",
        "processing": "None",
        "useIdFirst": "",
        "uid": "",
        "id": "",
        "nRevs": "",
        "revisionRule": ""
      },
      "datasetInfo": {
        "clientId": "",
        "uid": "",
        "filter": {
          "useNameFirst": "",
          "processing": "None",
          "nrFilters": [
            {
              "namedReference": "",
              "uidReferenced": ""
            }
          ],
          "name": "",
          "relationFilters": [
            {
              "relationTypeName": "",
              "datasetTypeName": ""
            }
          ]
        },
        "namedRefs": [
          {
            "namedReference": "",
            "ticket": ""
          }
        ]
      },
      "bvrTypeNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `infos` | Teamcenter::Soa::Core::_2008_06::DataManagement::GetItemAndRelatedObjectsInfo[] | list of <font face="courier" height="10">GetItemAndRelatedObjectsInfo</font> structures. |

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
      "itemRevOutput": [
        {
          "clientId": "",
          "itemRevision": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "bvrs": [
            {
              "bvr": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "viewTypeName": ""
            }
          ],
          "datasetOutput": [
            {
              "clientId": "",
              "dataset": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "relationTypeName": "",
              "namedReferenceOutput": [
                {
                  "namedReference": {
                    "uid": "",
                    "type": "",
                    "className": ""
                  },
                  "namedReferenceName": "",
                  "ticket": ""
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
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::GetItemAndRelatedObjectsItemOutput[] | List of <font face=&quot;courier&quot; height=&quot;10&quot;>GetItemAndRelatedObjectsItemOutput</font> |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData member |

---

#### 3.8.10 getNextIds（2008-06）

**接口路径：** `Core-2008-06-DataManagement/getNextIds`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 该操作 generates the next id as per the input pattern in the attached Naming Rule to the 属性 of an object type. The type name, 属性 name and pattern are passed in the input structure. The input for 此操作 contains a list of this structure. The return structure contains the list of nextId along with the service data member. In the case where no pattern…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.getNextIds`

**请求（input）：**

```json
{
  "vInfoForNextId": [
    {
      "typeName": "",
      "propName": "",
      "pattern": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `vInfoForNextId` | Teamcenter::Soa::Core::_2008_06::DataManagement::InfoForNextId[] | Contains Type Name, Property Name and pattern. |

**响应（output）：**

```json
{
  "nextIds": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `nextIds` | std::string[] | List containing next Id strings generated as per the pattern. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> structure. It contains partial errors and failures along wi |

---

#### 3.8.11 getNRPatternsWithCounters（2008-06）

**接口路径：** `Core-2008-06-DataManagement/getNRPatternsWithCounters`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 gives the list of Patterns which has counters along with preferred patterns and conditions for the Naming Rule attached to the 属性 of an object Type. The Type name and the 属性 name are passed in the input structure. The input for 此操作 contains a list of this structure. The return structure contains the vector of patterns with counters, pref…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.getNRPatternsWithCounters`

**请求（input）：**

```json
{
  "vAttachInfo": [
    {
      "typeName": "",
      "propName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `vAttachInfo` | Teamcenter::Soa::Core::_2008_06::DataManagement::NRAttachInfo[] | Struct that contains Type Name and Property Name |

**响应（output）：**

```json
{
  "patterns": [
    {
      "patternStrings": [
        ""
      ]
    }
  ],
  "preferredPattern": [
    ""
  ],
  "condition": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `patterns` | Teamcenter::Soa::Core::_2008_06::DataManagement::PatternsWithCounters[] | List of structs which contain Patterns which has counters. |
| `preferredPattern` | std::string[] | List of preferred patterns. |
| `condition` | std::string[] | List of conditions. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData structure. It contains partial errors and failures along with the clientIds. |

---

#### 3.8.12 getRevNRAttachDetails（2008-06）

**接口路径：** `Core-2008-06-DataManagement/getRevNRAttachDetails`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 获取 all the possible initial, secondary and supplemental revision next Ids for an ItemRevision along with the available formats and the set of excluded letters for revision. The Revision Type Name and the current revision are passed in the input typeAndItemRevInfos structure. The input for 此操作 contains a list of this structure. The return structure…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.getRevNRAttachDetails`

**请求（input）：**

```json
{
  "typeAndItemRevInfos": [
    {
      "typeName": "",
      "itemRev": {
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
| `typeAndItemRevInfos` | Teamcenter::Soa::Core::_2008_06::DataManagement::TypeAndItemRevInfo[] | List of <font face="courier" height="10">TypeAndItemRevInfo</font> structs which contains <b>Item</b> and <b>ItemRevisio |

**响应（output）：**

```json
{
  "initRevDetails": [
    {
      "revOption": "",
      "revFormat": ""
    }
  ],
  "secRevDetails": [
    {
      "revOption": "",
      "revFormat": ""
    }
  ],
  "supplRevDetails": [
    {
      "revOption": "",
      "revFormat": ""
    }
  ],
  "excludedLetters": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `initRevDetails` | Teamcenter::Soa::Core::_2008_06::DataManagement::RevOptionDetails[] | List containing information about Initial Revision Type. |
| `secRevDetails` | Teamcenter::Soa::Core::_2008_06::DataManagement::RevOptionDetails[] | List containing information about Secondary Revision Type. |
| `supplRevDetails` | Teamcenter::Soa::Core::_2008_06::DataManagement::RevOptionDetails[] | List containing information about Supplemental Revision Type. |
| `excludedLetters` | std::string[] | List of exluded letters. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData structure. It contains partial errors and failures along with the clientIds. |

---

#### 3.8.13 removeParticipants（2008-06）

**接口路径：** `Core-2008-06-DataManagement/removeParticipants`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 allows the user to remove Participant objects associated with specified Item 版本. If a participant being removed is no longer associated with any other objects, it 获取 deleted.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.removeParticipants`

**请求（input）：**

```json
{
  "participants": [
    {
      "itemRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "participant": [
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
| `participants` | Teamcenter::Soa::Core::_2008_06::DataManagement::Participants[] | List of participants structures each containing a list of <b>Participant</b> objects to be removed and an Item Revision  |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.8.14 revise2（2008-06）

**接口路径：** `Core-2008-06-DataManagement/revise2`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 provides the ability to revise the ItemRevision objects given in the input list and carries forward relations to existing objects. When applying deep copy rules, if user overridden deep copy information is provided in the input, relations are propagated to the new ItemRevision based on that input. If no deep copy information is provided in the input, the deep …

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.revise2`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "baseItemRevision": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newRevId": "",
      "name": "",
      "description": "",
      "deepCopyInfo": [
        {
          "otherSideObjectTag": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationTypeName": "",
          "newName": "",
          "action": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": ""
        }
      ],
      "newItemRevisionMasterProperties": {
        "form": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "propertyValueInfo": [
          {
            "propertyName": "",
            "propertyValues": [
              ""
            ]
          }
        ]
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2008_06::DataManagement::ReviseInfo[] | The necessary information to create the new revision |

**响应（output）：**

```json
{
  "reviseOutputMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `reviseOutputMap` | Teamcenter::Soa::Core::_2008_06::DataManagement::ReviseOutputMap | Map whose keys are the input clientIds and output values pairs (<font face="courier" height="10">string</font>, <font fa |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This contains the status of the operation. |

---

#### 3.8.15 saveAsNewItem2（2008-06）

**接口路径：** `Core-2008-06-DataManagement/saveAsNewItem2`

**API 版本：** `2008-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 provides the capability to create one or more new Item objects based on a list of existing ItemRevision objects. It optionally carries forward ItemRevision relations based on the deepCopyRequired flag. When applying deep copy rules, if user overridden deep copy information is provided in the input, then old ItemRevision relations are propagated to the new Item…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DataManagement.saveAsNewItem2`

**请求（input）：**

```json
{
  "info": [
    {
      "clientId": "",
      "baseItemRevision": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newItemId": "",
      "newRevId": "",
      "name": "",
      "description": "",
      "deepCopyInfo": [
        {
          "otherSideObjectTag": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "relationTypeName": "",
          "newName": "",
          "action": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": ""
        }
      ],
      "newItemMasterProperties": {
        "form": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "propertyValueInfo": [
          {
            "propertyName": "",
            "propertyValues": [
              ""
            ]
          }
        ]
      },
      "newItemRevisionMasterProperties": {
        "form": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "propertyValueInfo": [
          {
            "propertyName": "",
            "propertyValues": [
              ""
            ]
          }
        ]
      }
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2008_06::DataManagement::SaveAsNewItemInfo[] | The necessary information to create the new <b>Iitem</b> and <b>ItemRevision</b> |

**响应（output）：**

```json
{
  "saveAsOutputMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `saveAsOutputMap` | Teamcenter::Soa::Core::_2008_06::DataManagement::SaveAsNewItemOutputMap | Map whose keys are the input clientIds and output values pairs(<font face="courier" height="10">string</font>, <font fac |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

#### 3.8.16 createDispatcherRequest（2008-06）

**接口路径：** `Core-2008-06-DispatcherManagement/createDispatcherRequest`

**API 版本：** `2008-06`  
**Service：** `DispatcherManagement`  
**Library：** `Core`

**说明：** 调度管理（DispatcherManagement）：创建Dispatcher Request。Create a DispatcherRequest within Teamcenter for use with Dispatcher Management Services.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.DispatcherManagement.createDispatcherRequest`

**请求（input）：**

```json
{
  "inputs": [
    {
      "providerName": "",
      "serviceName": "",
      "type": "",
      "primaryObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "secondaryObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "priority": "",
      "startTime": "",
      "endTime": "",
      "interval": "",
      "keyValueArgs": [
        {
          "key": "",
          "value": ""
        }
      ],
      "dataFiles": [
        {
          "key": "",
          "file": {
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
| `inputs` | Teamcenter::Soa::Core::_2008_06::DispatcherManagement::CreateDispatcherRequestArgs[] | holds the values needed to create the <b>DispatcherRequest</b>. |

**响应（output）：**

```json
{
  "requestsCreated": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "svcData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `requestsCreated` | Teamcenter::BusinessObject[] | The Dispatcher Request objects created. |
| `svcData` | Teamcenter::Soa::Server::ServiceData | The SOA Service Data. |

---

#### 3.8.17 getManagedRelations（2008-06）

**接口路径：** `Core-2008-06-ManagedRelations/getManagedRelations`

**API 版本：** `2008-06`  
**Service：** `ManagedRelations`  
**Library：** `Core`

**说明：** 此操作 will return tracelinks between primary and secondary objects

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.ManagedRelations.getManagedRelations`

**请求（input）：**

```json
{
  "inputdata": {
    "primaryTags": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "secondaryTags": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "primaryType": "",
    "subtype": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputdata` | Teamcenter::Soa::Core::_2008_06::ManagedRelations::GetManagedRelationInput | information required to get tracelink relations |

**响应（output）：**

```json
{
  "managedRelations": [
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
| `managedRelations` | Teamcenter::WorkspaceObject[] | Tracelink relations |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |

---

#### 3.8.18 getCreateDesc（2008-06）

**接口路径：** `Core-2008-06-PropDescriptor/getCreateDesc`

**API 版本：** `2008-06`  
**Service：** `PropDescriptor`  
**Library：** `Core`

**说明：** 该操作 返回 information required to create a 业务对象. The Create Descriptor (CreateDesc object) includes the metadata information for the 属性 required when creating a 业务对象 i.e, 属性 is mandatory, 属性 is visible, etc. The CreateDesc is a recursive data structure. The CreateDesc object can also reference CreateDesc on secondary obje…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.PropDescriptor.getCreateDesc`

**请求（input）：**

```json
{
  "businessObjectTypeNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `businessObjectTypeNames` | std::string[] | list of business object names for which Create Descriptor is needed. |

**响应（output）：**

```json
{
  "createDescs": [
    {
      "businessObjectTypeName": "",
      "propDescs": [
        {
          "propName": "",
          "displayName": "",
          "isEnabled": "",
          "isModifiable": "",
          "attachedSpecifier": "",
          "maxLength": "",
          "interdependentProps": [
            ""
          ],
          "namingPatterns": [
            ""
          ],
          "defaultValue": "",
          "propValueType": "",
          "propType": "",
          "isDisplayable": "",
          "isArray": "",
          "maxNumElems": "",
          "lov": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isRequired": ""
        }
      ],
      "secondaryCreateDescs": {}
    }
  ],
  "srvData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `createDescs` | Teamcenter::Soa::Core::_2008_06::PropDescriptor::CreateDesc[] | List of <font face=&quot;courier&quot; height=&quot;10&quot;>Teamcenter::Soa::Core::_2008_06::PropDescriptor::CreateDesc |
| `srvData` | Teamcenter::Soa::Server::ServiceData | Service data containing partial errors. If there is any error in retrieving the Create Descriptor for any Business Objec |

---

#### 3.8.19 transferCheckout（2008-06）

**接口路径：** `Core-2008-06-Reservation/transferCheckout`

**API 版本：** `2008-06`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 transfers the previously checked-out 业务对象 to the user given from input. 此操作 takes care of all complex business logic involved in transfer checked-out based on passed in objects. Each input object is verified that it is valid for transferring its checkout. 此操作 validates precondition defined per type in COTS object and site cust…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.Reservation.transferCheckout`

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
  "userId": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of the previously checked-out Teamcenter objects (e.g. <b>Dataset</b>, <b>Item</b>, <b>ItemRevision</b> ) to tran |
| `userId` | Teamcenter::User |  The Teamcenter user id to who checked-out has to be transferred to. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.8.20 getDisplayStrings（2008-06）

**接口路径：** `Core-2008-06-Session/getDisplayStrings`

**API 版本：** `2008-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session）：获取Display Strings。Get the localized text string for each input key from the info array. The input key must correspond to a key defined in the Text Server. If the input array is empty, the returned array will also be empty.

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.Session.getDisplayStrings`

**请求（input）：**

```json
{
  "info": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | std::string[] | A list of Text Server key names. |

**响应（output）：**

```json
{
  "output": [
    {
      "key": "",
      "value": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::Session::GetDisplayStringsOutput[] | A list Text Server key/localized value pairs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Partial errors with the key name attached to the partial error. |

---

#### 3.8.21 login（2008-06）

**接口路径：** `Core-2008-06-Session/login`

**API 版本：** `2008-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 验证用户凭据并初始化 Teamcenter 客户端会话；在四层架构下还会分配服务器实例。凭据无效时抛出 InvalidCredentialsException。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.Session.login`

**请求（input）：**

```json
{
  "username": "",
  "password": "",
  "group": "",
  "role": "",
  "locale": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `username` | std::string | The user`s Teamcenter user name. This is case insensitive (<i>jdoe</i> or <i>JDOE</i>) |
| `password` | std::string | The user`s Teamcenter password. |
| `group` | std::string | The group ID for this session. If null, the user`s default group is assumed. |
| `role` | std::string | The role the user is performing in the group. If null, the user`s default role in the group is assumed. |
| `locale` | std::string | The locale to be used by the Teamcenter server process for this session. If null, the server`s default locale will be us |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

#### 3.8.22 loginSSO（2008-06）

**接口路径：** `Core-2008-06-Session/loginSSO`

**API 版本：** `2008-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 通过单点登录（SSO）方式验证用户并初始化 Teamcenter 会话。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.Session.loginSSO`

**请求（input）：**

```json
{
  "username": "",
  "ssoCredentials": "",
  "group": "",
  "role": "",
  "locale": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `username` | std::string | The user's Teamcenter username. |
| `ssoCredentials` | std::string | The user's Teamcenter SSO credentials. This should have been obtained from Teamcenter Security Services. |
| `group` | std::string | The group id for this session (optional). If NULL, the user's default group is assumed. |
| `role` | std::string | The role the user is performing in the group (optional). If NULL, the user's default role in the group is assumed. |
| `locale` | std::string | The locale to be used by the Teamcenter server process for this session (optional). If NULL, the server's default locale |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

#### 3.8.23 setObjectPropertyPolicy（2008-06）

**接口路径：** `Core-2008-06-Session/setObjectPropertyPolicy`

**API 版本：** `2008-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 设置对象属性策略（Property Policy），控制返回哪些属性。

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.Session.setObjectPropertyPolicy`

**请求（input）：**

```json
{
  "policy": "IObjectPropertyPolicy"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policy` | Teamcenter::Soa::Common::ObjectPropertyPolicy | The object property policy. |

**响应（output）：**

```json
"String"
```

---

#### 3.8.24 createInStructureAssociations（2008-06）

**接口路径：** `Core-2008-06-StructureManagement/createInStructureAssociations`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Core`

**说明：** 此操作 创建 the specified association between primary and secondary BOMLine objects in a structure. As the name indicates, these associations are created in a specific context and are applicable only in that context. The context is specified as an additional input in the input structure, by the caller. Some examples of these associations are: the ConnectTo, Implem…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.StructureManagement.createInStructureAssociations`

**请求（input）：**

```json
{
  "inputs": [
    {
      "primaryBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "contextBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "secondaries": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "associationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2008_06::StructureManagement::InStructureAssociationInfo[] | This is a vector of InStructureAssociationInfo structure. Each element shall consist of a primary <b>BOMLine</b>, the se |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <i>ServiceData</i> structure is used to return the updated objects and contains partial errors, if any, occurring in |

---

#### 3.8.25 getPrimariesOfInStructureAssociation（2008-06）

**接口路径：** `Core-2008-06-StructureManagement/getPrimariesOfInStructureAssociation`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Core`

**说明：** 此操作 获取 the primary BOMLines like PSConnection, Signal of an association given the secondary object and association type. Examples of these associations are: ConnectTo, ImplementedBy, RealizedBy, RoutedBy, FixingToSegment, DeviceToConnector, SignalToTransmitter, SignalToSource, SignalToTarget, ProcessVariable, RedundantSignal. 此操作 takes a vector of Get…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.StructureManagement.getPrimariesOfInStructureAssociation`

**请求（input）：**

```json
{
  "inputs": [
    {
      "secondary": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "contextBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "associationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2008_06::StructureManagement::GetPrimariesOfInStructureAssociationInfo[] | This is a vector of <i>GetPrimariesOfInStructureAssociationInfo</i> structure. Each element consists of a secondary <b>B |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "primariesInfo": [
    {
      "secondary": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "associationType": "",
      "primaryBOMLine": {
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
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <i>ServiceData</i> structure is used to return the primary <b>BOMLine</b> business objects and partial errors if any |
| `primariesInfo` | Teamcenter::Soa::Core::_2008_06::StructureManagement::PrimariesOfInStructureAssociation[] | Context object of association. This is generally the parent line of the primary object. |

---

#### 3.8.26 getSecondariesOfInStructureAssociation（2008-06）

**接口路径：** `Core-2008-06-StructureManagement/getSecondariesOfInStructureAssociation`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Core`

**说明：** 结构管理（StructureManagement）：获取Secondaries Of In Structure Association。Given the primary object and association type, 返回 the secondary BOMLine 业务对象 of in structure associations. These associations can be ConnectTo, ImplementedBy, RealizedBy, RoutedBy, FixingToSegment, DeviceToConnector, SignalToSource, SignalToTarget, SignalToTransmitter, ProcessVariable or RedundantSignal. It takes a vector of 获取econdariesOfInStructureAssoci…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.StructureManagement.getSecondariesOfInStructureAssociation`

**请求（input）：**

```json
{
  "inputs": [
    {
      "primaryBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "contextBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "associationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2008_06::StructureManagement::GetSecondariesOfInStructureAssociationInfo[] | This is a vector of <i>GetSecondariesOfInStructureAssociationInfo</i> structure. Each element shall consist of a primary |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "secondariesInfo": [
    {
      "primaryBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "associationType": "",
      "secondaries": [
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
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Secondary <b>BOMLine</b> business objects and Partial errors if any |
| `secondariesInfo` | Teamcenter::Soa::Core::_2008_06::StructureManagement::SecondariesOfInStructureAssociation[] | primary <b>BOMLine</b> and association type. |

---

#### 3.8.27 removeInStructureAssociations（2008-06）

**接口路径：** `Core-2008-06-StructureManagement/removeInStructureAssociations`

**API 版本：** `2008-06`  
**Service：** `StructureManagement`  
**Library：** `Core`

**说明：** 结构管理（StructureManagement）：移除In Structure Associations。Given the primary BOMLine, the association type, and the secondary BOMLines 此操作 removes the instructure associations between the BOMLines. These associations can be ConnectTo, ImplementedBy, RealizedBy, RoutedBy, FixingToSegment, DeviceToConnector, SignalToSource, SignalToTarget, SignalToTransmitter, ProcessVariable or RedundantSignal. 该操作 takes a vector…

**Soa Inclusion：** `Teamcenter.Soa.Core._2008_06.StructureManagement.removeInStructureAssociations`

**请求（input）：**

```json
{
  "inputs": [
    {
      "primaryBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "contextBOMLine": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "secondaries": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "associationType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2008_06::StructureManagement::RemoveInStructureAssociationsInfo[] | This is a vector of <i>RemoveInStructureAssociationsInfo</i> structure. Each element shall consist of a primary <b>BOMLi |

**响应（output）：**

```json
{
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The updated objects and partial errors if any. |

---

### 3.9 API 版本 2009-04

**Service：** ProjectLevelSecurity、Session  **操作数：** 3

#### 3.9.1 loadProjectDataForUser（2009-04）

**接口路径：** `Core-2009-04-ProjectLevelSecurity/loadProjectDataForUser`

**API 版本：** `2009-04`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 list of projects for a given user, group and role combination. If no group and role is specified it obtains all the projects for the specified user. If any of the arguments passed are invalid an error is returned by 该操作 added as a partial error.

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_04.ProjectLevelSecurity.loadProjectDataForUser`

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
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> object. |
| `group` | Teamcenter::Group | The <b>Group</b> object in which the user belongs to. |
| `role` | Teamcenter::Role | The <b>Role</b> object in which the user belongs to. |

**响应（output）：**

```json
{
  "applicableProjects": [
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
| `applicableProjects` | Teamcenter::TC_Project[] | List of <b>TC_project</b> objects found. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | A  standard  ServicData. |

---

#### 3.9.2 startOperation（2009-04）

**接口路径：** `Core-2009-04-Session/startOperation`

**API 版本：** `2009-04`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `startOperation`。Start an operation bracket. An operation bracket is a period of execution in which any object will need to be refreshed in the server from the database only once. This allows the client to avoid unnecessary database operations that the server might perform redundantly if underlying code accesses the same object multiple times. The client will use the return value to call the…

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_04.Session.startOperation`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
"String"
```

---

#### 3.9.3 stopOperation（2009-04）

**接口路径：** `Core-2009-04-Session/stopOperation`

**API 版本：** `2009-04`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `stopOperation`。Stop an operation bracket, in which objects need to be refreshed only once. See startOperation.

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_04.Session.stopOperation`

**请求（input）：**

```json
{
  "opId": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `opId` | std::string | The operation identifier assigned to the operation and returned by the <font face="courier" height="10">startOperation</ |

**响应（output）：**

```json
"bool"
```

---

### 3.10 API 版本 2009-10

**Service：** DataManagement、ProjectLevelSecurity  **操作数：** 4

#### 3.10.1 getItemFromAttribute（2009-10）

**接口路径：** `Core-2009-10-DataManagement/getItemFromAttribute`

**API 版本：** `2009-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：获取Item From Attribute。This service retrieves Item and its related ItemRevision objects based on the supplied attribute key-value pairs supplied in the infos list. All the key-value pairs except for the rev_id key are used to create a query for Item objects. Once a set of Item objects have been retrieved, their ItemRevision objects are retrieved based on the following rules: If nRev is a negative …

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_10.DataManagement.getItemFromAttribute`

**请求（input）：**

```json
{
  "infos": [
    {
      "itemAttributes": {},
      "revIds": [
        ""
      ]
    }
  ],
  "nRev": "",
  "pref": {
    "prefs": [
      {
        "relationTypeName": "",
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
| `infos` | Teamcenter::Soa::Core::_2009_10::DataManagement::GetItemFromAttributeInfo[] | The list of attribute value keys for the retrieval. The attributes must be the unique key attributes of the class. Curre |
| `nRev` | int | Maximum number of <b>ItemRevision</b> objects to retrieve.<br /><ul><ul><li type="disc">nRev < 0        retrieve all ava |
| `pref` | Teamcenter::Soa::Core::_2007_01::DataManagement::GetItemFromIdPref | <font face="courier" height="10">GetItemFromIdPref</font> object used to filter the returned <b>ItemRevision</b> objects |

**响应（output）：**

```json
{
  "output": [
    {
      "item": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemRevOutput": [
        {
          "itemRevision": {
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
| `output` | Teamcenter::Soa::Core::_2009_10::DataManagement::GetItemFromAttributeItemOutput[] | A list of found <b>Item</b> and <b>ItemRevision</b> objects |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServerData</font> member with any returned error codes and messages |

---

#### 3.10.2 getTableProperties（2009-10）

**接口路径：** `Core-2009-10-DataManagement/getTableProperties`

**API 版本：** `2009-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 allows 客户端应用s to obtain the 属性 pertaining to one or more Table 业务对象. Client developers will need to pass in references to each Table that they need to query information on. Note that the input vector needs to contain only references to the Teamcenter Table 业务对象, 此操作 cannot be used to fetch 属性 of an…

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_10.DataManagement.getTableProperties`

**请求（input）：**

```json
{
  "table": [
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
| `table` | Teamcenter::Table[] | This is a vector of the Table Business Objects for which the properties need to be obtained. |

**响应（output）：**

```json
{
  "tableInfo": [
    {
      "tableObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tableDefInfo": {
        "rows": "",
        "columns": "",
        "rowLabels": [
          ""
        ],
        "colLabels": [
          ""
        ],
        "tableDef": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "tableCells": [
        {
          "row": "",
          "column": "",
          "desc": "",
          "value": {
            "type": "",
            "strValues": [
              ""
            ]
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
| `tableInfo` | Teamcenter::Soa::Core::_2009_10::DataManagement::TableInfo[] | This vector contains a list of <i>TableInfo</i>, and each <i>TableInfo</i> contains information pertaining to the specif |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData structure is used to return the updated Table objects in the update section and also any errors encounte |

---

#### 3.10.3 setTableProperties（2009-10）

**接口路径：** `Core-2009-10-DataManagement/setTableProperties`

**API 版本：** `2009-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 allows 客户端应用s to set the 属性 pertaining to one or more Table 业务对象. Client developers will need to set information pertaining to the number of rows, columns, descriptions of each row and column, and cell information for each cell of the Table. The cell information must contain the type of cell, value to be placed in the cell, and…

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_10.DataManagement.setTableProperties`

**请求（input）：**

```json
{
  "tableData": [
    {
      "tableObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tableDefInfo": {
        "rows": "",
        "columns": "",
        "rowLabels": [
          ""
        ],
        "colLabels": [
          ""
        ],
        "tableDef": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "tableCells": [
        {
          "row": "",
          "column": "",
          "desc": "",
          "value": {
            "type": "",
            "strValues": [
              ""
            ]
          }
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `tableData` | Teamcenter::Soa::Core::_2009_10::DataManagement::TableInfo[] | This vector contains a list of <i>TableInfo</i>, and each <i>TableInfo</i> contains information pertaining to the specif |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.10.4 getUserProjects（2009-10）

**接口路径：** `Core-2009-10-ProjectLevelSecurity/getUserProjects`

**API 版本：** `2009-10`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 the list of TC_Project objects for each of the users in the input structure based on the additional criteria like active projects only, user privileged projects only and programs only. The output for 此操作 is a UserProjectsInfoResponse structure.

**Soa Inclusion：** `Teamcenter.Soa.Core._2009_10.ProjectLevelSecurity.getUserProjects`

**请求（input）：**

```json
{
  "userProjectsInfoInputs": [
    {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "activeProjectsOnly": "",
      "privilegedProjectsOnly": "",
      "programsOnly": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `userProjectsInfoInputs` | Teamcenter::Soa::Core::_2009_10::ProjectLevelSecurity::UserProjectsInfoInput[] | A list of UserProjectsInfoInput structures. |

**响应（output）：**

```json
{
  "userProjectInfos": [
    {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "activeProjectsOnly": "",
      "privilegedProjectsOnly": "",
      "programsOnly": "",
      "clientId": "",
      "projectsInfo": [
        {
          "project": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isUserPrivileged": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `userProjectInfos` | Teamcenter::Soa::Core::_2009_10::ProjectLevelSecurity::UserProjectsInfo[] | List of UserProjectsInfo structures one for each given user.. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | A  standard ServiceData. |

---

### 3.11 API 版本 2010-04

**Service：** DataManagement、LanguageInformation、Session  **操作数：** 12

#### 3.11.1 createDatasets（2010-04）

**接口路径：** `Core-2010-04-DataManagement/createDatasets`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建一个或多个数据集（Dataset）及其文件信息。

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.createDatasets`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "name": "",
      "container": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "relationType": "",
      "description": "",
      "type": "",
      "datasetId": "",
      "datasetRev": "",
      "toolUsed": "",
      "attrs": [
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
          "namedReferenceName": "",
          "isText": "",
          "allowReplace": ""
        }
      ],
      "nrObjectInfos": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "namedReferenceName": "",
          "referenceType": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2010_04::DataManagement::DatasetInfo[] | Input list of DatasetInfo structures |

**响应（output）：**

```json
{
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
                "namedReferenceName": "",
                "isText": "",
                "allowReplace": ""
              },
              "ticket": ""
            }
          ]
        }
      ]
    }
  ],
  "servData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `datasetOutput` | Teamcenter::Soa::Core::_2010_04::DataManagement::DatasetOutput[] | List of output structure for creatDatasets operation. Each element in the list contains a client Id and the related <b>D |
| `servData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

#### 3.11.2 findDisplayableSubBusinessObjectsWithDisplayNames（2010-04）

**接口路径：** `Core-2010-04-DataManagement/findDisplayableSubBusinessObjectsWithDisplayNames`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 sub 业务对象 names that are displayable to the login user in the object creation dialog and their display names for each Primary 业务对象 given as the input. Returned 业务对象 lists have exclusions of 业务对象 and their secondary 业务对象 as specified in the input. This 返回 the hierarchy of displayable objects f…

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.findDisplayableSubBusinessObjectsWithDisplayNames`

**请求（input）：**

```json
{
  "input": [
    {
      "boTypeName": "",
      "exclusionBOTypeNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_06::DataManagement::BOWithExclusionIn[] | A list of Business Object names and their exclusion list for which the displayable Business Objects are to be retrieved. |

**响应（output）：**

```json
{
  "output": [
    {
      "boTypeName": "",
      "displayableBOTypeNames": [
        {
          "boName": "",
          "boDisplayName": "",
          "boParents": [
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
| `output` | Teamcenter::Soa::Core::_2010_04::DataManagement::DisplayableBusinessObjectsOut[] | List of displayable Business Objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service data. |

---

#### 3.11.3 getAvailableTypesWithDisplayNames（2010-04）

**接口路径：** `Core-2010-04-DataManagement/getAvailableTypesWithDisplayNames`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 业务对象 names and their display names for each primary 业务对象 given as the input. Returned 业务对象 lists have exclusions of 业务对象 and their secondary 业务对象 as specified in the input. If any of the returned 业务对象 is also a primary 业务对象 then 此操作 may not return its secondary B…

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.getAvailableTypesWithDisplayNames`

**请求（input）：**

```json
{
  "classes": [
    {
      "baseClass": "",
      "exclusionTypes": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `classes` | Teamcenter::Soa::Core::_2007_06::DataManagement::BaseClassInput[] | A list of primary Business Object names and their exclusion list. |

**响应（output）：**

```json
{
  "inputClassToTypes": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputClassToTypes` | Teamcenter::Soa::Core::_2010_04::DataManagement::BusinessObjectClassToTypesMap | A map of <b>Business Object </b>names and associated descendant Business Objects (<b>string, vector<AvailableBusinessObj |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData. |

---

#### 3.11.4 getDatasetCreationRelatedInfo2（2010-04）

**接口路径：** `Core-2010-04-DataManagement/getDatasetCreationRelatedInfo2`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 pre-populates 数据集 creation information, default new 数据集 name and Tool names, for a specified 数据集 type. 此操作 is used to get all the information associates with the specified 数据集 prior to the creation operation. The returned default new 数据集 name may be determined by the parent container object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.getDatasetCreationRelatedInfo2`

**请求（input）：**

```json
{
  "typeName": "",
  "parentObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `typeName` | std::string | The desired <b>Dataset</b> type name |
| `parentObject` | Teamcenter::BusinessObject | The container object under which the new <b>Dataset</b> object will be created |

**响应（output）：**

```json
{
  "toolNames": [
    ""
  ],
  "toolDisplayNames": [
    ""
  ],
  "newDatasetName": "",
  "nameCanBeModified": "",
  "initValuePropertyRules": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `toolNames` | std::string[] | List of <b>Tool</b> names |
| `toolDisplayNames` | std::string[] | List of <b>Tool</b> display names. |
| `newDatasetName` | std::string | The name of the new <b>Dataset</b>, can be an empty string |
| `nameCanBeModified` | bool | If true, the name of the <b>Dataset</b> can be modified |
| `initValuePropertyRules` | std::string[] | List of properties have the initialized values from property constant attachments |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> member |

---

#### 3.11.5 getLocalizedProperties（2010-04）

**接口路径：** `Core-2010-04-DataManagement/getLocalizedProperties`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** Typically 业务对象 属性 values are returned in the locale of the current 会话, 此操作 返回 desired 属性 values in any of the supported locales of the Teamcenter server. String type 属性 may be localized with values for each supported locale, 此操作 will return the translated values for one or more desired locales.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.getLocalizedProperties`

**请求（input）：**

```json
{
  "info": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propsToget": [
        {
          "name": "",
          "locales": [
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
| `info` | Teamcenter::Soa::Core::_2010_04::DataManagement::PropertyInfo[] | A list of desired business objects, property names, and locales to retrieve those properties in. |

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
      "propertyValues": [
        {
          "name": "",
          "values": [
            ""
          ],
          "locale": "",
          "seqNum": "",
          "status": [
            ""
          ],
          "statusDesc": [
            ""
          ],
          "master": ""
        }
      ]
    }
  ],
  "partialErrors": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2010_04::DataManagement::LocalizedPropertyValuesInfo[] | A list of structure LocalizedPropertyValuesInfo to keep the localized property values info. |
| `partialErrors` | Teamcenter::Soa::Server::ServiceData | Used for storing partial error and standard service data. |

---

#### 3.11.6 isPropertyLocalizable（2010-04）

**接口路径：** `Core-2010-04-DataManagement/isPropertyLocalizable`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 该操作 is used to determine if string-type 属性 is localizable or not and can retrieve the localizable status for ONE or MORE 属性.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.isPropertyLocalizable`

**请求（input）：**

```json
{
  "inputInfo": [
    {
      "objTypeName": "",
      "propNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputInfo` | Teamcenter::Soa::Core::_2010_04::DataManagement::LocalizableStatusInput[] |  A list of business object type names and internal property names |

**响应（output）：**

```json
{
  "results": [
    {
      "objTypeName": "",
      "results": [
        {
          "propName": "",
          "islocalizable": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `results` | Teamcenter::Soa::Core::_2010_04::DataManagement::LocalizableStatusOutput[] | A list of <font face="courier" height="10">LocalizableResults</font> structure to hold the localizable information for a |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">serviceData</font> |

---

#### 3.11.7 setLocalizedProperties（2010-04）

**接口路径：** `Core-2010-04-DataManagement/setLocalizedProperties`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 allows user to set or modify the display values for a localized 属性 on a single object. This 设置 the 属性 values for a single 属性 on an object in different locales. With the display values capability, each localized string 属性 could have different language translations associated with that. Please be aware of the following: 此操作 i…

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.setLocalizedProperties`

**请求（input）：**

```json
{
  "info": {
    "object": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "propertyValues": [
      {
        "name": "",
        "values": [
          ""
        ],
        "locale": "",
        "seqNum": "",
        "status": [
          ""
        ],
        "statusDesc": [
          ""
        ],
        "master": ""
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2010_04::DataManagement::LocalizedPropertyValuesInfo | The business object and a list of the property name, value and locale of the property value. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.11.8 setLocalizedPropertyValues（2010-04）

**接口路径：** `Core-2010-04-DataManagement/setLocalizedPropertyValues`

**API 版本：** `2010-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 设置 the 属性 values for multiple 属性 on a single object in different locales. With the display values capability, each localized string 属性 could have different language translations associated with that. 此操作 allows user to set or modify the display values for the localized 属性 on a single object. It should be noted that 此操作 is o…

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.DataManagement.setLocalizedPropertyValues`

**请求（input）：**

```json
{
  "info": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyValues": [
        {
          "name": "",
          "values": [
            ""
          ],
          "locale": "",
          "seqNum": "",
          "status": [
            ""
          ],
          "statusDesc": [
            ""
          ],
          "master": ""
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2010_04::DataManagement::LocalizedPropertyValuesInfo[] |  A list of business object, the property name, value and locale of the property value. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.11.9 getAllTranslationStatuses（2010-04）

**接口路径：** `Core-2010-04-LanguageInformation/getAllTranslationStatuses`

**API 版本：** `2010-04`  
**Service：** `LanguageInformation`  
**Library：** `Core`

**说明：** 语言信息（LanguageInformation）：获取All Translation Statuses。Retrieves the full set of translation statuses: their enumeration, localized name and description. Currently, the translation statuses in the Teamcenter system includes: "Master", "Approved", "Pending", "In-Review", and "Invalid"

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.LanguageInformation.getAllTranslationStatuses`

**请求（input）：**

```json
{}
```

**响应（output）：**

```json
{
  "fullTranslationStatuses": [
    {
      "status": "TranslationStatusMaster",
      "statusName": "",
      "statusDescription": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `fullTranslationStatuses` | Teamcenter::Soa::Core::_2010_04::LanguageInformation::FullTranslationStatus[] | List of all the full translation statuses |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">ServiceData</font>. |

---

#### 3.11.10 getLanguagesList（2010-04）

**接口路径：** `Core-2010-04-LanguageInformation/getLanguagesList`

**API 版本：** `2010-04`  
**Service：** `LanguageInformation`  
**Library：** `Core`

**说明：** 语言信息（LanguageInformation）：获取Languages List。Retrieves a list of languages according to different scenarios as specified in the input parameter. All the returned language names are in the Java-standard format.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.LanguageInformation.getLanguagesList`

**请求（input）：**

```json
{
  "scenario": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `scenario` | std::string | Defines the type of languages list that will be returned. <br />Valid values are (case sensitive): <br /><ul><ul><li typ |

**响应（output）：**

```json
{
  "languageList": [
    {
      "languageCode": "",
      "languageName": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `languageList` | Teamcenter::Soa::Core::_2010_04::LanguageInformation::Language[] | An ordered list of languages |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any partial errors that may occur when filling this request |

---

#### 3.11.11 getPreferences2（2010-04）

**接口路径：** `Core-2010-04-Session/getPreferences2`

**API 版本：** `2010-04`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 takes an input structure which contains a scope value and vector of preference names. The return type of 此操作 is the MultiPreferencesResponse2 structure whose elements are the ServiceData and the vector of ReturnedPreferences2 structure.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.Session.getPreferences2`

**请求（input）：**

```json
{
  "preferenceNames": [
    {
      "scope": "",
      "names": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `preferenceNames` | Teamcenter::Soa::Core::_2007_01::Session::ScopedPreferenceNames[] | The input structure, the object of which would ahve 2 input parameters of scope and the preference names. |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "preferences": [
    {
      "scope": "",
      "category": "",
      "description": "",
      "prefType": "",
      "isArray": "",
      "isDisabled": "",
      "values": [
        ""
      ],
      "name": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | The successful Object ids, partial errors and failures |
| `preferences` | Teamcenter::Soa::Core::_2010_04::Session::ReturnedPreferences2[] | List of ReturnedPreferences2 Object |

---

#### 3.11.12 getShortcuts（2010-04）

**接口路径：** `Core-2010-04-Session/getShortcuts`

**API 版本：** `2010-04`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 获取 the sections and corresponding content in Left Hand Navigation task pane given the section name and the corresponding preference name for the current 会话 user. The preference name is the key to look up section content stored in preference. In the rich client, the LHN sections are Quick Links, Open Items, History, Favorites and I Want To. The user can …

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_04.Session.getShortcuts`

**请求（input）：**

```json
{
  "shortcutInputs": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `shortcutInputs` | Teamcenter::Soa::Core::_2010_04::Session::LHNShortcutInputs | A map of the key representing the  section name in the left hand navigation and the value representing the preference na |

**响应（output）：**

```json
{
  "favorites": {
    "containers": [
      {
        "clientId": "",
        "id": "",
        "type": "",
        "displayName": "",
        "parentId": ""
      }
    ],
    "objects": [
      {
        "clientId": "",
        "objectTag": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayName": "",
        "parentId": ""
      }
    ]
  },
  "shortcuts": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `favorites` | Teamcenter::Soa::Core::_2008_03::Session::FavoritesList | A hierarchical Favorites tree structure list that contains all the favorites containers and favorites objects for the cu |
| `shortcuts` | Teamcenter::Soa::Core::_2010_04::Session::LHNSectionComponentsMap | A map structure that includes the given section name and corresponding content of the section. The key is the name of th |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData contains any failures and Teamcenter objects  wrapped in LHNSecitonComponents and default properties. The fo |

---

### 3.12 API 版本 2010-09

**Service：** DataManagement  **操作数：** 6

#### 3.12.1 createOrUpdateStaticTableData（2010-09）

**接口路径：** `Core-2010-09-DataManagement/createOrUpdateStaticTableData`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** This 创建 a new Table along with Rows or updates an existing Table with rows and their values based on input StaticTableInfo and created Table rows are added to the Table. ServiceData is updated with newly created/updated Table.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.createOrUpdateStaticTableData`

**请求（input）：**

```json
{
  "staticTableInfo": {
    "tableType": "",
    "tableObject": {
      "uid": "",
      "type": "",
      "className": ""
    }
  },
  "rowProperties": [
    {
      "clientId": "",
      "rowObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "rowType": "",
      "rowAttrValueMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `staticTableInfo` | Teamcenter::Soa::Core::_2010_09::DataManagement::StaticTableInfo | This represents static table object that needs to be created/updated. |
| `rowProperties` | Teamcenter::Soa::Core::_2010_09::DataManagement::RowData[] | Vector of RowData where each element is of type TableProperties |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "staticTableObject": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | SOA Service Data. |
| `staticTableObject` | Teamcenter::Fnd0StaticTable | StaticTable Object |

---

#### 3.12.2 getEventTypes（2010-09）

**接口路径：** `Core-2010-09-DataManagement/getEventTypes`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：获取Event Types。The getEventTypes operation retrieves the valid Auditable and Subscribable events for each of the businessObject in the input EventObject vector. When an event is auditable, you can audit actions on Teamcenter objects when that event happens on the businessObject. When an event is Subscribable, that means subscriptions can be created for that event. Partial failures, if any,…

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.getEventTypes`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "businessObject": {
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
| `input` | Teamcenter::Soa::Core::_2010_09::DataManagement::EventObject[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>EventObject</font> structure consisting of list of Busi |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "auditableEvents": [
        ""
      ],
      "subscribableEvents": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2010_09::DataManagement::EventTypesOutput[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>EventTypesOutput</font> structures packaged in custom r |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Partial failures will be returned in the ServiceDate for each failed processing. Error encountered while processing post |

---

#### 3.12.3 getStaticTableData（2010-09）

**接口路径：** `Core-2010-09-DataManagement/getStaticTableData`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 返回 a list of objects of type Table属性 which are associated with Fnd0StaticTable object. Fnd0StaticTable object has an attribute fnd0StaticTableData which is an array of Table属性 objects. Any failures will be returned with the input object mapped to the error message in the ServiceData list of partial errors.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.getStaticTableData`

**请求（input）：**

```json
{
  "staticTable": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `staticTable` | Teamcenter::Fnd0StaticTable | StaticTable |

**响应（output）：**

```json
{
  "clientId": "",
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `clientId` | std::string | A unique string supplied by caller.<br />This ID is used to identify return data elements and partial errors associated  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data. |

---

#### 3.12.4 postEvent（2010-09）

**接口路径：** `Core-2010-09-DataManagement/postEvent`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 will post an event for each of the Teamcenter 业务对象 in the input list, with all the supplied information: secondaryObject, 属性 to be logged, and the error details. . Partial failures will be returned in the serviceData.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.postEvent`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
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
      "propertyCount": "",
      "propertyNames": [
        ""
      ],
      "propertyValues": [
        ""
      ],
      "errorCode": "",
      "errorMessage": ""
    }
  ],
  "eventTypeName": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2010_09::DataManagement::PostEventObjectProperties[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>ObjectProperties</font> structure. Each structure consi |
| `eventTypeName` | std::string | Name of the event. This is a mandatory parameter and should be a valid auditable or subscribable event mapped for the pr |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "ifailError": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2010_09::DataManagement::PostEventOutput[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>PostEventOutput</font> structures packaged in custom re |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Partial failures will be returned in the Service Data for each failed processing. Error encountered while processing pos |

---

#### 3.12.5 setProperties（2010-09）

**接口路径：** `Core-2010-09-DataManagement/setProperties`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 批量设置业务对象的属性值。

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.setProperties`

**请求（input）：**

```json
{
  "info": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "vecNameVal": [
        {
          "name": "",
          "values": [
            ""
          ]
        }
      ],
      "timestamp": "0001-01-01T00:00:00"
    }
  ],
  "options": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `info` | Teamcenter::Soa::Core::_2010_09::DataManagement::PropInfo[] | List of PropInfo structure which consists of information about the objects and the property values to set. |
| `options` | std::string[] | To updating the objects in controlled manner. Valid options are:<br /><ul><ul><li type="disc"><b>No</b> options can be p |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "objPropMap": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | This is the service data. It contains the updated objects and their properties. |
| `objPropMap` | Teamcenter::Soa::Core::_2010_09::DataManagement::ObjectPropMap | Additional information to be communicated to client such as objects and props those are overwritten. This map can be emp |

---

#### 3.12.6 verifyExtension（2010-09）

**接口路径：** `Core-2010-09-DataManagement/verifyExtension`

**API 版本：** `2010-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 checks if an extension exists on an operation of a specific type.

**Soa Inclusion：** `Teamcenter.Soa.Core._2010_09.DataManagement.verifyExtension`

**请求（input）：**

```json
{
  "extensionInfo": [
    {
      "typeName": "",
      "operationName": "",
      "extensionName": "",
      "extensionType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `extensionInfo` | Teamcenter::Soa::Core::_2010_09::DataManagement::VerifyExtensionInfo[] | The specific type, operation and extension information required to verify an extension exists. |

**响应（output）：**

```json
{
  "output": [],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | bool[] | Returns True if extension exists otherwise False. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | This data structure provides service data for associated information. |

---

### 3.13 API 版本 2011-06

**Service：** DataManagement、Envelope、LOV、OperationDescriptor、PropDescriptor、Reservation、Session  **操作数：** 13

#### 3.13.1 getTraceReport（2011-06）

**接口路径：** `Core-2011-06-DataManagement/getTraceReport`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 will generate a Trace Report on the objects selected by user. User will get information about complying as well as defining objects which are connected to selected object using FND_TraceLink or its subtype of GRM relation. Trace links can be between following objects: 1. Between occurrences of an ItemRevision 2. Between ItemRevisions 3. Between Items 4. Betwee…

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.DataManagement.getTraceReport`

**请求（input）：**

```json
{
  "input": {
    "selectedObjs": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "reportType": "",
    "reportDepth": "",
    "isIndirectTraceReportNeeded": "",
    "relationTypeName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2011_06::DataManagement::TraceabilityInfoInput | A TraceabilityInfoInput structure to generate a Trace Report.This input structure holds selected objects for which trace |

**响应（output）：**

```json
{
  "traceReports": [
    {
      "definingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "indirectDefiningTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "complyingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "indirectComplyingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "selectedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "persistentObjects": [
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
| `traceReports` | Teamcenter::Soa::Core::_2011_06::DataManagement::TraceReport[] | This member holds all the Trace Reports user has asked for. This is vector of <br />TraceReport type of structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data. |

---

#### 3.13.2 saveAsObjects（2011-06）

**接口路径：** `Core-2011-06-DataManagement/saveAsObjects`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 is generic operation for saving of 业务对象. It will also save any secondary objects that also need to be saved based on deep copy rule information

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.DataManagement.saveAsObjects`

**请求（input）：**

```json
{
  "saveAsIn": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "saveAsInput": {
        "boName": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      },
      "deepCopyDatas": [
        {
          "attachedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "propertyName": "",
          "propertyType": "Relation",
          "copyAction": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": "",
          "saveAsInputTypeName": "",
          "childDeepCopyData": [],
          "saveAsInput": {
            "boName": "",
            "stringProps": {},
            "boolArrayProps": {},
            "dateProps": {},
            "dateArrayProps": {},
            "tagProps": {},
            "tagArrayProps": {},
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
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `saveAsIn` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsIn[] | Input data containing target object and DeepCopyData of the attached objects |

**响应（output）：**

```json
{
  "output": [
    {
      "targetObject": {
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
  ],
  "saveAsTrees": [
    {
      "originalObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectCopy": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childSaveAsNodes": []
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsOut[] | SaveAsout vector |
| `saveAsTrees` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsTree[] | List of the input target objects that holds mapping between the original objects and the copied  objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing created objects, errors, etc |

---

#### 3.13.3 validateRevIds（2011-06）

**接口路径：** `Core-2011-06-DataManagement/validateRevIds`

**API 版本：** `2011-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：校验Rev Ids。Validates and/or modifies the Revision Id based on the naming rules/revision naming rules and user exit callbacks.

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.DataManagement.validateRevIds`

**请求（input）：**

```json
{
  "inputs": [
    {
      "revId": "",
      "itemObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "itemType": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2011_06::DataManagement::ValidateRevIdsInfo[] | A list of <font face="courier" height="10">ValidateRevIdsInfo</font> structures, each of which contain revId/itemObject/ |

**响应（output）：**

```json
{
  "output": [
    {
      "modRevId": "",
      "revIdStatus": "ValidRevID"
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2011_06::DataManagement::ValidateRevIdsOutput[] | List of <font face="courier" height="10">ValidateRevIdsOutput</font> structures, which contain the modified revision id  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> structure. It contains partial errors and failures along wi |

---

#### 3.13.4 sendAndDeleteEnvelopes（2011-06）

**接口路径：** `Core-2011-06-Envelope/sendAndDeleteEnvelopes`

**API 版本：** `2011-06`  
**Service：** `Envelope`  
**Library：** `Core`

**说明：** 此操作 sends mails to the recipients of each Envelope 业务对象 in envelopes. All the envelopes passed to 此操作 are deleted after they are processed, even if the processing is not successful. Each Envelope 业务对象 contains mail information such as subject, body, recipients, and attachments. Recipients can be Teamcenter users, groups and address…

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Envelope.sendAndDeleteEnvelopes`

**请求（input）：**

```json
{
  "envelopes": [
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
| `envelopes` | Teamcenter::Envelope[] | The list of <b>Envelope</b> business objects to be sent. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.13.5 getLOVAttachments（2011-06）

**接口路径：** `Core-2011-06-LOV/getLOVAttachments`

**API 版本：** `2011-06`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 返回 valid LOV attachments for the 属性 of each object passed in as input. It may return LOV or null based on condition validations. If none of the conditions evaluated to be True, then no LOV attachment is returned for the 属性 of an instance.

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.LOV.getLOVAttachments`

**请求（input）：**

```json
{
  "objectStructArray": [
    {
      "objects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "properties": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objectStructArray` | Teamcenter::Soa::Core::_2011_06::LOV::LOVAttachmentsInput[] | LOV attachments are evaluated for each property of the structure LOVAttachmentsInut based on each object in <font face=& |

**响应（output）：**

```json
{
  "lovAttachments": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `lovAttachments` | Teamcenter::Soa::Core::_2011_06::LOV::InpoutObjectToLOVAttachmentsMap | A list of objects and its properties and associated LOV attachments. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data. |

---

#### 3.13.6 getSaveAsDesc（2011-06）

**接口路径：** `Core-2011-06-OperationDescriptor/getSaveAsDesc`

**API 版本：** `2011-06`  
**Service：** `OperationDescriptor`  
**Library：** `Core`

**说明：** 此操作 返回 information required to save a 业务对象. The SaveAsDescriptor includes the metadata information for the 属性 required when saving a 业务对象, i.e., the 属性 is mandatory, the 属性 is visible, if value is to be copied from original object, etc. The SaveAsDescriptor also includes the DeepCopyData which is a recursive data stru…

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.OperationDescriptor.getSaveAsDesc`

**请求（input）：**

```json
{
  "targetObjects": [
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
| `targetObjects` | Teamcenter::BusinessObject[] | Set of objects for which the SaveAs Descriptor is needed. |

**响应（output）：**

```json
{
  "saveAsDescMap": {},
  "deepCopyInfoMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `saveAsDescMap` | Teamcenter::Soa::Core::_2011_06::OperationDescriptor::SaveAsDescMap | A map of business object types and SaveAs Descriptors (string/SaveAsDesc).  This is the container of metadata for SaveAs |
| `deepCopyInfoMap` | Teamcenter::Soa::Core::_2011_06::OperationDescriptor::DeepCopyInfoMap | A map of business objects and <font face=&quot;courier&quot; height=&quot;10&quot;>DeepCopyData</font> (business object/ |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing errors, etc. The plain object list of the Service data is populated with the target objects whic |

---

#### 3.13.7 getAttachedPropDescs2（2011-06）

**接口路径：** `Core-2011-06-PropDescriptor/getAttachedPropDescs2`

**API 版本：** `2011-06`  
**Service：** `PropDescriptor`  
**Library：** `Core`

**说明：** 返回 a list of 属性 Descriptors based on the input structure. The 属性 Descriptors contain the Display Name, Description and other information about the input 属性.

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.PropDescriptor.getAttachedPropDescs2`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2007_06::PropDescriptor::PropDescInfo[] | An input Type Name and a list of property names on the input type.  A Property Descriptor is returned for each Property  |

**响应（output）：**

```json
{
  "inputTypeNameToPropDescOutput": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputTypeNameToPropDescOutput` | Teamcenter::Soa::Core::_2011_06::PropDescriptor::InputTypeNameToPropDescOutputMap2 | A map of property descriptor lists and the associated input type name. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data. |

---

#### 3.13.8 okToCheckout（2011-06）

**接口路径：** `Core-2011-06-Reservation/okToCheckout`

**API 版本：** `2011-06`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 determines whether or not the input objects may be checked out given the type of object, access rules, and current checkout state of the object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Reservation.okToCheckout`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | The list of objects which should be validated for Checkout. |

**响应（output）：**

```json
{
  "verdict": [],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `verdict` | bool[] | A list indicating if the input business object can be checked out. "<i>true</i>" indicates the object may be checked out |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Contains the partial errors for any objects for which the <font face="courier" height="10">okToCheckout</font> validatio |

---

#### 3.13.9 getClientCacheData（2011-06）

**接口路径：** `Core-2011-06-Session/getClientCacheData`

**API 版本：** `2011-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 返回 information required to maintain a client cache. The Teamcneter server maintains a set of 数据集s with static or near static data that is pertainant to a 客户端应用. This static data can be downloaded through FMS to the cleint host one time, and available for each subsequent client 会话, thus improving the overall performance of the client …

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Session.getClientCacheData`

**请求（input）：**

```json
{
  "features": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `features` | std::string[] | Names of features to return<i>, All</i> to return data for all features. Available features are <i>ClientMetaModel</i> a |

**响应（output）：**

```json
{
  "features": [
    {
      "name": "",
      "cacheTickets": {}
    }
  ],
  "partialErrors": "IPartialErrors"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `features` | Teamcenter::Soa::Core::_2011_06::Session::Feature[] | The list of  features. |
| `partialErrors` | Teamcenter::Soa::Server::PartialErrors | Errors are return for features that do not exist or if there are other errors in getting data for a given service. The c |

---

#### 3.13.10 getTypeDescriptions（2011-06）

**接口路径：** `Core-2011-06-Session/getTypeDescriptions`

**API 版本：** `2011-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取类型描述信息（属性、关系等元数据）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Session.getTypeDescriptions`

**请求（input）：**

```json
{
  "typeNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `typeNames` | std::string[] | List of Business Model Object type names. |

**响应（output）：** 无

---

#### 3.13.11 login（2011-06）

**接口路径：** `Core-2011-06-Session/login`

**API 版本：** `2011-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 验证用户凭据并初始化 Teamcenter 客户端会话；在四层架构下还会分配服务器实例。凭据无效时抛出 InvalidCredentialsException。

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Session.login`

**请求（input）：**

```json
{
  "credentials": {
    "user": "{{USER_NAME}}",
    "password": "{{USER_PASSWORD}}",
    "group": "",
    "role": "",
    "locale": "",
    "descrimator": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `credentials` | Teamcenter::Soa::Core::_2011_06::Session::Credentials | The user's Teamcenter credentials |

**响应（output）：**

```json
{
  "serverInfo": {},
  "partialErrors": "IPartialErrors"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serverInfo` | Teamcenter::Soa::Core::_2011_06::Session::ServerInfo | Name/Value pairs (string/string) of data related to the server. The following keys are valid:<br /><ul><ul><li type="dis |
| `partialErrors` | Teamcenter::Soa::Server::PartialErrors | Partial errors or warnings resulting from the login attempt. |

---

#### 3.13.12 loginSSO（2011-06）

**接口路径：** `Core-2011-06-Session/loginSSO`

**API 版本：** `2011-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 通过单点登录（SSO）方式验证用户并初始化 Teamcenter 会话。

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Session.loginSSO`

**请求（input）：**

```json
{
  "credentials": {
    "user": "{{USER_NAME}}",
    "password": "{{USER_PASSWORD}}",
    "group": "",
    "role": "",
    "locale": "",
    "descrimator": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `credentials` | Teamcenter::Soa::Core::_2011_06::Session::Credentials | The user's Teamcenter credentials. |

**响应（output）：**

```json
{
  "serverInfo": {},
  "partialErrors": "IPartialErrors"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serverInfo` | Teamcenter::Soa::Core::_2011_06::Session::ServerInfo | Name/Value pairs (string/string) of data related to the server. The following keys are valid:<br /><ul><ul><li type="dis |
| `partialErrors` | Teamcenter::Soa::Server::PartialErrors | Partial errors or warnings resulting from the login attempt. |

---

#### 3.13.13 updateObjectPropertyPolicy（2011-06）

**接口路径：** `Core-2011-06-Session/updateObjectPropertyPolicy`

**API 版本：** `2011-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session）：更新对象 属性 Policy。Update the named policy, adding and removing the named 属性. 此操作 only applies to object 属性 policies that have been defined on the client side.

**Soa Inclusion：** `Teamcenter.Soa.Core._2011_06.Session.updateObjectPropertyPolicy`

**请求（input）：**

```json
{
  "policyID": "",
  "addProperties": [
    "IPolicyType"
  ],
  "removeProperties": [
    "IPolicyType"
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policyID` | std::string | The ID of the policy to update. This is the ID that is returned from the <font face="courier" height="10">setObjectPrope |
| `addProperties` | Teamcenter::Soa::Common::PolicyType[] | List of properties to add to the named policy.  If the property already exists in the policy, the flags (i.e. <font face |
| `removeProperties` | Teamcenter::Soa::Common::PolicyType[] | List of properties to remove from the named policy. If a source <font face="courier" height="10">PolicyType</font> defin |

**响应（output）：**

```json
"String"
```

---

### 3.14 API 版本 2012-02

**Service：** DataManagement、OperationDescriptor、Session  **操作数：** 7

#### 3.14.1 bulkCreateObjects（2012-02）

**接口路径：** `Core-2012-02-DataManagement/bulkCreateObjects`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `bulkCreateObjects`。This is a generic operation for bulk creation of 业务对象. This will create instances of the given quantity of the specified type in their specified containing 文件夹s. This will also create any secondary(compounded) objects that need to be created, assuming the CreateInput for the secondary object is represented in the recursive CreateInput object e.g. Item is Prima…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.DataManagement.bulkCreateObjects`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "quantity": "",
      "folder": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "data": {
        "boName": "",
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2012_02::DataManagement::BulkCreIn[] | A vector of <font face=&quot;courier&quot; height=&quot;10&quot;>BulkCreIn</font> structures representing the <font face |

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOut[] | Vector of output objects representing objects that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data including partial errors that are mapped to the client id from the input. Created objects are also added to |

---

#### 3.14.2 validateIdValue（2012-02）

**接口路径：** `Core-2012-02-DataManagement/validateIdValue`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 determines if the given MultiFieldKey 属性 are unique based on the MultiFieldKey definition.

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.DataManagement.validateIdValue`

**请求（input）：**

```json
{
  "input": [
    {
      "clientId": "",
      "data": {
        "boName": "",
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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateIn[] | A list of MultiFieldKey attribute/value pairs for the object to be created |

**响应（output）：**

```json
{
  "validationResult": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `validationResult` | Teamcenter::Soa::Core::_2012_02::DataManagement::ValidationResult | A map of type <<font face="courier" height="10">std::string ,bool</font>> indicating if the ID is valid. The key is clie |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data |

---

#### 3.14.3 whereUsed（2012-02）

**接口路径：** `Core-2012-02-DataManagement/whereUsed`

**API 版本：** `2012-02`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 查询指定对象在结构或关系中的使用位置（Where Used）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.DataManagement.whereUsed`

**请求（input）：**

```json
{
  "input": [
    {
      "inputObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "useLocalParams": "",
      "inputParams": {
        "stringMap": {},
        "doubleMap": {},
        "intMap": {},
        "boolMap": {},
        "dateMap": {},
        "tagMap": {},
        "floatMap": {}
      },
      "clientId": ""
    }
  ],
  "configParams": {
    "stringMap": {},
    "doubleMap": {},
    "intMap": {},
    "boolMap": {},
    "dateMap": {},
    "tagMap": {},
    "floatMap": {}
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2012_02::DataManagement::WhereUsedInputData[] | <font face="courier" height="10">WhereUsedInputData</font> object list |
| `configParams` | Teamcenter::Soa::Core::_2012_02::DataManagement::WhereUsedConfigParameters | Additional Configuration Parameters if required. For example <font face="courier" height="10">tagMap</font> to specify t |

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
      "info": [
        {
          "parentObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "level": ""
        }
      ],
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2012_02::DataManagement::WhereUsedOutputData[] | List of <font face="courier" height="10">WhereUsedOutputData</font> structures |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard <font face="courier" height="10">ServiceData</font> Member |

---

#### 3.14.4 getDeepCopyData（2012-02）

**接口路径：** `Core-2012-02-OperationDescriptor/getDeepCopyData`

**API 版本：** `2012-02`  
**Service：** `OperationDescriptor`  
**Library：** `Core`

**说明：** 获取深拷贝所需的数据结构。

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.OperationDescriptor.getDeepCopyData`

**请求（input）：**

```json
{
  "deepCopyDataInput": [
    {
      "operation": "",
      "object": {
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
| `deepCopyDataInput` | Teamcenter::Soa::Core::_2012_02::OperationDescriptor::DeepCopyDataInput[] | A list of DeepCopyDataInput structures which contains an object, and operation type. |

**响应（output）：**

```json
{
  "deepCopyInfoMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `deepCopyInfoMap` | Teamcenter::Soa::Core::_2012_02::OperationDescriptor::DeepCopyInfoMap2 | Map of the DeepCopy data |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Creates a list of Datasets and creates the specified relation type between created Dataset and input container object. |

---

#### 3.14.5 registerState（2012-02）

**接口路径：** `Core-2012-02-Session/registerState`

**API 版本：** `2012-02`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `registerState`。Register desired level for server state as used by the Server Manager to control server timeout. Note that an attempt to register at LEVEL_STATELESS is ignored since this is the default level when no registrations are in effect. To move from a higher level to the stateless level the unregister operation should be used to delete the earlier registration. Note that it is possi…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.Session.registerState`

**请求（input）：**

```json
{
  "level": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `level` | std::string | Desired server state: "<i>Edit</i>" or "<i>Read</i>" |

**响应（output）：**

```json
{
  "registryIndex": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `registryIndex` | int | Index to be used for unregistering. |

---

#### 3.14.6 setObjectPropertyPolicy（2012-02）

**接口路径：** `Core-2012-02-Session/setObjectPropertyPolicy`

**API 版本：** `2012-02`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 设置对象属性策略（Property Policy），控制返回哪些属性。

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.Session.setObjectPropertyPolicy`

**请求（input）：**

```json
{
  "policyName": "",
  "useRefCounting": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policyName` | std::string | The name of the policy file without the .xml extension. The file must exist on the Teamcenter server volume at <font fac |
| `useRefCounting` | bool | When set to true, the policy will not remove a property value until there is a matching number of removes and adds in su |

**响应（output）：**

```json
{
  "policyId": "",
  "policy": "IObjectPropertyPolicy"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policyId` | std::string | Unique ID for this object property policy. |
| `policy` | Teamcenter::Soa::Common::ObjectPropertyPolicy | The full definition of the object property policy. |

---

#### 3.14.7 unregisterState（2012-02）

**接口路径：** `Core-2012-02-Session/unregisterState`

**API 版本：** `2012-02`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `unregisterState`。Remove the specified registration.

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_02.Session.unregisterState`

**请求（input）：**

```json
{
  "index": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `index` | int | Index returned by previous call to <font face="courier" height="10">registerState</font>. |

**响应（output）：**

```json
"bool"
```

---

### 3.15 API 版本 2012-09

**Service：** DataManagement、ProjectLevelSecurity  **操作数：** 5

#### 3.15.1 saveAsObjectAndRelate（2012-09）

**接口路径：** `Core-2012-09-DataManagement/saveAsObjectAndRelate`

**API 版本：** `2012-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 保存 the given object and its related objects as new instances. Related objects are identifed using deep copy rules. Optionally,this method relates the new object to the input target object or to a default 文件夹.

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_09.DataManagement.saveAsObjectAndRelate`

**请求（input）：**

```json
{
  "saveAsInput": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "saveAsInput": {
        "boName": "",
        "stringProps": {},
        "boolArrayProps": {},
        "dateProps": {},
        "dateArrayProps": {},
        "tagProps": {},
        "tagArrayProps": {},
        "stringArrayProps": {},
        "doubleProps": {},
        "doubleArrayProps": {},
        "floatProps": {},
        "floatArrayProps": {},
        "intProps": {},
        "intArrayProps": {},
        "boolProps": {}
      },
      "deepCopyDatas": [
        {
          "attachedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "propertyName": "",
          "propertyType": "Relation",
          "copyAction": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": "",
          "saveAsInputTypeName": "",
          "childDeepCopyData": [],
          "saveAsInput": {
            "boName": "",
            "stringProps": {},
            "boolArrayProps": {},
            "dateProps": {},
            "dateArrayProps": {},
            "tagProps": {},
            "tagArrayProps": {},
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
  ],
  "relateInfo": [
    {
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyName": "",
      "relate": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `saveAsInput` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsIn[] | The property values to be used for the new objects. The properties passed in should be defined in SaveAs descriptor. |
| `relateInfo` | Teamcenter::Soa::Core::_2012_09::DataManagement::RelateInfoIn[] | The paste options used to relate the newly created object. |

**响应（output）：**

```json
{
  "output": [
    {
      "targetObject": {
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
  ],
  "saveAsTrees": [
    {
      "originalObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectCopy": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childSaveAsNodes": []
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsOut[] | SaveAsout vector |
| `saveAsTrees` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsTree[] | List of the input target objects that holds mapping between the original objects and the copied  objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing created objects, errors, etc |

---

#### 3.15.2 copyProjects（2012-09）

**接口路径：** `Core-2012-09-ProjectLevelSecurity/copyProjects`

**API 版本：** `2012-09`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 copies the given list of TC_Project objects. 该操作 also copies any information which is in contained in the project. Data such as project team members and any objects assigned to the source project will also be copied to the new project. If a project with given project ID exists in the system then 此操作 will return error 101010. 该操作 …

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_09.ProjectLevelSecurity.copyProjects`

**请求（input）：**

```json
{
  "copyProjectsInfos": [
    {
      "sourceProject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "projectInfo": {
        "projectId": "",
        "projectName": "",
        "projectDescription": "",
        "useProgramContext": "",
        "active": "",
        "visible": "",
        "teamMembers": [
          {
            "teamMember": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "teamMemberType": ""
          }
        ],
        "clientId": ""
      },
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `copyProjectsInfos` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::CopyProjectsInfo[] | A list of CopyProjectsInfo structures. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

#### 3.15.3 createProjects（2012-09）

**接口路径：** `Core-2012-09-ProjectLevelSecurity/createProjects`

**API 版本：** `2012-09`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 创建 TC_Project objects using the given input information. If the project with given project ID exists in the system then 此操作 will return unique id violation error 101010. However, creation of rest of the projects will continue.

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_09.ProjectLevelSecurity.createProjects`

**请求（input）：**

```json
{
  "projectInfos": [
    {
      "projectId": "",
      "projectName": "",
      "projectDescription": "",
      "useProgramContext": "",
      "active": "",
      "visible": "",
      "teamMembers": [
        {
          "teamMember": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "teamMemberType": ""
        }
      ],
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectInfos` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectInformation[] | A list of ProjectInformation objects. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

#### 3.15.4 getProjectTeams（2012-09）

**接口路径：** `Core-2012-09-ProjectLevelSecurity/getProjectTeams`

**API 版本：** `2012-09`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 team members for the given list of TC_Project objects.

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_09.ProjectLevelSecurity.getProjectTeams`

**请求（input）：**

```json
{
  "projectObjs": [
    {
      "tcProject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectObjs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectClientId[] |   A list of ProjectClientId structures one for each of the given projects. |

**响应（output）：**

```json
{
  "projectTeams": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "regularMembers": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "projectTeamAdmins": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "privMembers": [
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
| `projectTeams` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectTeamData[] | List of ProjectTeamData objects one for each of the given projects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | A standard ServiceData object. |

---

#### 3.15.5 modifyProjects（2012-09）

**接口路径：** `Core-2012-09-ProjectLevelSecurity/modifyProjects`

**API 版本：** `2012-09`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 modifies the given list of TC_Project objects using the input specified. The input contains new values for all the project 属性. Values for 属性 other than the project team are ignored unless the user is the Project Administrator. The entire Project Team, with the exception of the Project Administrator, is replaced with the specified team. Therefor…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_09.ProjectLevelSecurity.modifyProjects`

**请求（input）：**

```json
{
  "modifyProjectsInfos": [
    {
      "sourceProject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "projectInfo": {
        "projectId": "",
        "projectName": "",
        "projectDescription": "",
        "useProgramContext": "",
        "active": "",
        "visible": "",
        "teamMembers": [
          {
            "teamMember": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "teamMemberType": ""
          }
        ],
        "clientId": ""
      },
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `modifyProjectsInfos` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ModifyProjectsInfo[] | Vector of ModifyProjectsInfo structures. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

### 3.16 API 版本 2012-10

**Service：** DataManagement  **操作数：** 3

#### 3.16.1 getDatasetTypesWithFileExtension（2012-10）

**接口路径：** `Core-2012-10-DataManagement/getDatasetTypesWithFileExtension`

**API 版本：** `2012-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 the 数据集 type and reference information for a set of file extensions. Named references are Teamcenter objects that relate to a specific data file. For each file extension, it is possible that it belongs to multiple 数据集 types. For such cases, all matching 数据集 types will be returned using the file extension as the key in the Get数据集TypesWit…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_10.DataManagement.getDatasetTypesWithFileExtension`

**请求（input）：**

```json
{
  "fileExtensions": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `fileExtensions` | std::string[] | List of file extensions used to get the named reference information |

**响应（output）：**

```json
{
  "output": [
    {
      "fileExtension": "",
      "datasetTypesInfo": [
        {
          "tag": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "refInfos": [
            {
              "referenceName": "",
              "isObject": "",
              "fileFormat": "",
              "fileExtension": ""
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
| `output` | Teamcenter::Soa::Core::_2012_10::DataManagement::GetDatasetTypesWithFileExtensionOutput[] | List of named reference information for each dataset type specified in fileExtensions input |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The DatasetType objects that corresponds to fileExtensions input |

---

#### 3.16.2 getTraceReport（2012-10）

**接口路径：** `Core-2012-10-DataManagement/getTraceReport`

**API 版本：** `2012-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 will generate a Trace Report on the objects selected by user. The report will contain information about complying as well as defining objects which are connected to selected object using FND_TraceLink, or its subtype. 此操作 will check if there is any TraceLink relation starting or ending from selected object(s). If TraceLink relation exists for select…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_10.DataManagement.getTraceReport`

**请求（input）：**

```json
{
  "input": [
    {
      "selectedObjs": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "reportType": "",
      "exportTo": "",
      "exportTemplate": "",
      "exportColumnNames": [
        ""
      ],
      "reportDepth": "",
      "isIndirectTraceReportNeeded": "",
      "filteredTraceLinkTypes": [
        ""
      ],
      "filteredObjectTypes": [
        ""
      ],
      "scopeLines": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "propertyFilterInput": [
        {
          "logicalOperatorType": "",
          "propertyName": "",
          "operatorType": "",
          "propertyValue": ""
        }
      ],
      "sortPropName": "",
      "sortDirection": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2012_10::DataManagement::TraceabilityInfoInput1[] | A list of TraceabilityInfoInput1 structure to generate a Trace Report. This input structure holds, selected object(s) (f |

**响应（output）：**

```json
{
  "traceReports": [
    {
      "defRootNode": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "srcContextName": "",
        "tarContextName": "",
        "bomView": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isDirectLink": "",
        "isTraceLinkObj": "",
        "childNodes": []
      },
      "compRootNode": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "srcContextName": "",
        "tarContextName": "",
        "bomView": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isDirectLink": "",
        "isTraceLinkObj": "",
        "childNodes": []
      },
      "selectedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "persistentObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "transientFileReadTickets": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `traceReports` | Teamcenter::Soa::Core::_2012_10::DataManagement::TraceReport1[] | This member holds all the Trace Reports user has asked for. This is vector of TraceReport1 type of structures. |
| `transientFileReadTickets` | std::string[] | The transient file read tickets for the exported file. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data. |

---

#### 3.16.3 refreshObjects2（2012-10）

**接口路径：** `Core-2012-10-DataManagement/refreshObjects2`

**API 版本：** `2012-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 is used to reload the in-memory representation of the objects from the database. Any references to the object will still be valid. Any in-memory changes to the original object will be lost. If the object has been changed in the database since it was last loaded, then those changes will not be present in memory. 该操作 updates the in memory representatio…

**Soa Inclusion：** `Teamcenter.Soa.Core._2012_10.DataManagement.refreshObjects2`

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
  "lockObjects": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of business objects for which lock or unlock operation is required . |
| `lockObjects` | bool | If true then business objects will be locked , false will unlock the given business objects. |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.17 API 版本 2013-05

**Service：** DataManagement、LOV  **操作数：** 9

#### 3.17.1 generateNextValues（2013-05）

**接口路径：** `Core-2013-05-DataManagement/generateNextValues`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates values for the given 属性 of an object(s) during create/revise/save as action based on the user exits or naming rules configured on those 属性. Customer user exits are given priority over the naming rules if both of them are configured on the same 属性. The counter has to be set active on the naming rule in order to generate the next …

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.generateNextValues`

**请求（input）：**

```json
{
  "generateNextValuesIn": [
    {
      "clientId": "",
      "operationType": "",
      "businessObjectName": "",
      "propertyNameWithSelectedPattern": {},
      "propValues": {},
      "additionalInputParams": {},
      "compoundObjectInput": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `generateNextValuesIn` | Teamcenter::Soa::Core::_2013_05::DataManagement::GenerateNextValuesIn[] | This is the input that the SOA 'generateNextValues' expects. This contains the list of properties for which the next val |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "generatedValues": [
    {
      "clientId": "",
      "generatedValues": {},
      "generatedValuesOfSecondaryObjects": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | The Service Data with partial errors for each GenerateNextValuesInput and identified by  its clientId. |
| `generatedValues` | Teamcenter::Soa::Core::_2013_05::DataManagement::GeneratedValuesOutput[] | A list of GeneratedValuesOutput one for each entry in generateNextvaluesIn input list and  identified by its clientId. |

---

#### 3.17.2 getChildren（2013-05）

**接口路径：** `Core-2013-05-DataManagement/getChildren`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 the children for each input object. The children returned is determined by the input 属性Names list of strings which defines the 属性 which are to be processed in order to collect the children to be returned If the 属性Names list is empty, then the 属性 which are processed to object the children is based on the _DefaultChildProperti…

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.getChildren`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "obj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyNames": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2013_05::DataManagement::GetChildrenInputData[] | The list of objects and desired children for which to expand and return children. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "objectWithChildren": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The service data contains any partial errors which may have been encountered during processing.  All business objects wh |
| `objectWithChildren` | Teamcenter::Soa::Core::_2013_05::DataManagement::GetChildrenOutputMap | A map of requested objects and a list of children(business object/vector<GetChildrenOutput>). |

---

#### 3.17.3 getPasteRelations（2013-05）

**接口路径：** `Core-2013-05-DataManagement/getPasteRelations`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 返回 the paste relation names for the given parent types and the child types, within which the expandable relations and the preferred paste relation are indicated.

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.getPasteRelations`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "obj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childTypeName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2013_05::DataManagement::GetPasteRelationsInputData[] | The list of  the parent object and the child type. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "outputMap": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The service data contains any partial errors which may have been encountered during processing.  All business objects wh |
| `outputMap` | Teamcenter::Soa::Core::_2013_05::DataManagement::GetPasteRelationsOutputMap | A map of input parent object to a vector of GetPasteRelationsOutput objects. |

---

#### 3.17.4 getSubTypeNames（2013-05）

**接口路径：** `Core-2013-05-DataManagement/getSubTypeNames`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 获取指定类型的子类型名称列表。

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.getSubTypeNames`

**请求（input）：**

```json
{
  "inBOTypeNames": [
    {
      "typeName": "",
      "contextName": "",
      "exclusionPreference": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inBOTypeNames` | Teamcenter::Soa::Core::_2013_05::DataManagement::SubTypeNamesInput[] | A list of business object type names with the desired context. |

**响应（output）：**

```json
{
  "output": [
    {
      "typeName": "",
      "contextName": "",
      "exclusionPreference": "",
      "subTypeNames": [
        ""
      ],
      "displayableSubTypeNames": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2013_05::DataManagement::SubTypeNamesOut[] | List of  business object type names. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service data. |

---

#### 3.17.5 reviseObjects（2013-05）

**接口路径：** `Core-2013-05-DataManagement/reviseObjects`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 is generic single revise operation for revisable 业务对象. 此操作 revises the given objects and copies or 创建 new objects using the data for the 属性 values and deep copy data. Deep copy processing is recursive such that relations between secondary objects, or from secondary objects to the revised object, are replicated during this revi…

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.reviseObjects`

**请求（input）：**

```json
{
  "reviseIn": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "reviseInputs": {},
      "deepCopyDatas": [
        {
          "attachedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "propertyName": "",
          "propertyType": "",
          "copyAction": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": "",
          "operationInputTypeName": "",
          "childDeepCopyData": [],
          "operationInputs": {}
        }
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `reviseIn` | Teamcenter::Soa::Core::_2013_05::DataManagement::ReviseIn[] | Input data containing target object and DeepCopyData of the attached objects |

**响应（output）：**

```json
{
  "output": [
    {
      "targetObject": {
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
  ],
  "reviseTrees": [
    {
      "originalObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectCopy": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childReviseNodes": []
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2013_05::DataManagement::ReviseOut[] | The target object and the newly created revised objects. |
| `reviseTrees` | Teamcenter::Soa::Core::_2013_05::DataManagement::ReviseTree[] | List corresponding to the input target objects that holds mapping between the original objects and the copied objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Data containing created objects, errors, etc. |

---

#### 3.17.6 validateValues（2013-05）

**接口路径：** `Core-2013-05-DataManagement/validateValues`

**API 版本：** `2013-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 validates whether the input 属性 values are valid according to defined naming rules and specified user exits for the input 属性. Also, for the 属性 used in the multifield key (MFK) definition for the input type, 此操作 validates whether the combined 属性 values makes up a unique value. The validateValues operation can be called before…

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.DataManagement.validateValues`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "operationType": "",
      "businessObjectName": "",
      "propValuesMap": {},
      "compoundObjectInput": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2013_05::DataManagement::ValidateInput[] | The list of <b>ValidateInput</b>. The properties specified in each input are validated against defined naming rules and  |

**响应（output）：**

```json
{
  "validationResults": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `validationResults` | Teamcenter::Soa::Core::_2013_05::DataManagement::ValidationResultsMap | A map where the key (string) is the <font face="courier" height="10">clientId</font> and the value (<font face="courier" |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing errors that occurred during the operation. |

---

#### 3.17.7 getInitialLOVValues（2013-05）

**接口路径：** `Core-2013-05-LOV/getInitialLOVValues`

**API 版本：** `2013-05`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 此操作 is invoked to query the data for a 属性 having an LOV attachment. The results returned from the server also take into consideration any filter string that is in the input. 此操作 返回 both LOV meta data as necessary for the client to render the LOV and partial LOV values list as specified. 该操作 will return the results in the LOVSearchRe…

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.LOV.getInitialLOVValues`

**请求（input）：**

```json
{
  "initialData": {
    "lov": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "lovInput": {
      "owningObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "boName": "",
      "operationName": "",
      "propertyValues": {}
    },
    "propertyName": "",
    "filterData": {
      "filterString": "",
      "maxResults": "",
      "numberToReturn": "",
      "sortPropertyName": "",
      "order": ""
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `initialData` | Teamcenter::Soa::Core::_2013_05::LOV::InitialLovData | Input data to get LOV results for any LOV |

**响应（output）：**

```json
{
  "lovValues": [
    {
      "uid": "",
      "propInternalValues": {},
      "propInternalValueTypes": {},
      "propDisplayValues": {},
      "childRows": []
    }
  ],
  "moreValuesExist": "",
  "behaviorData": {
    "lovUsage": "",
    "style": "",
    "columnNames": {
      "lovValueProp": "",
      "lovDescrProp": "",
      "filterProperties": [
        ""
      ],
      "displayNames": {},
      "columnManagementFlags": {}
    },
    "descriptionsAttached": [],
    "dependendProps": [
      ""
    ],
    "rangeUpperLimit": "",
    "rangeLowerLimit": ""
  },
  "lovData": {
    "style": "",
    "filterData": {
      "filterString": "",
      "maxResults": "",
      "numberToReturn": "",
      "sortPropertyName": "",
      "order": ""
    },
    "unProcessedObjects": [
      ""
    ],
    "additionalValuesSkipped": "",
    "currentIndex": "",
    "lovs": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `lovValues` | Teamcenter::Soa::Core::_2013_05::LOV::LOVValueRow[] | This is a list of LOVValueRow objects. Each LOVValueRow object represents a single row of the LOV results. It includes t |
| `moreValuesExist` | bool | true indicates there are more values available which will can be retrieved by a call to the getNextValues operation |
| `behaviorData` | Teamcenter::Soa::Core::_2013_05::LOV::LOVBehaviorData | LOV data used to define the UI component behavior. This includes data such as LOV usage, Style, Lov Column Names. Additi |
| `lovData` | Teamcenter::Soa::Core::_2013_05::LOV::LOVData | If moreValuesExist is true, this object is passed as input to the getNextValues operation to get the next list of LOV se |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData |

---

#### 3.17.8 getNextLOVValues（2013-05）

**接口路径：** `Core-2013-05-LOV/getNextLOVValues`

**API 版本：** `2013-05`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 此操作 is invoked after a call to getInitialLOVValues if the moreValuesExist flag is true in the LOVSearchResults output returned from a call to the getInitialLOVValues operation. 该操作 will retrieve the next set of LOV values

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.LOV.getNextLOVValues`

**请求（input）：**

```json
{
  "lovData": {
    "style": "",
    "filterData": {
      "filterString": "",
      "maxResults": "",
      "numberToReturn": "",
      "sortPropertyName": "",
      "order": ""
    },
    "unProcessedObjects": [
      ""
    ],
    "additionalValuesSkipped": "",
    "currentIndex": "",
    "lovs": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `lovData` | Teamcenter::Soa::Core::_2013_05::LOV::LOVData | Input data to get next set of LOV results for Dynamic LOV. This is returned as part of the LOVSearchResults output from  |

**响应（output）：**

```json
{
  "lovValues": [
    {
      "uid": "",
      "propInternalValues": {},
      "propInternalValueTypes": {},
      "propDisplayValues": {},
      "childRows": []
    }
  ],
  "moreValuesExist": "",
  "behaviorData": {
    "lovUsage": "",
    "style": "",
    "columnNames": {
      "lovValueProp": "",
      "lovDescrProp": "",
      "filterProperties": [
        ""
      ],
      "displayNames": {},
      "columnManagementFlags": {}
    },
    "descriptionsAttached": [],
    "dependendProps": [
      ""
    ],
    "rangeUpperLimit": "",
    "rangeLowerLimit": ""
  },
  "lovData": {
    "style": "",
    "filterData": {
      "filterString": "",
      "maxResults": "",
      "numberToReturn": "",
      "sortPropertyName": "",
      "order": ""
    },
    "unProcessedObjects": [
      ""
    ],
    "additionalValuesSkipped": "",
    "currentIndex": "",
    "lovs": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `lovValues` | Teamcenter::Soa::Core::_2013_05::LOV::LOVValueRow[] | This is a list of LOVValueRow objects. Each LOVValueRow object represents a single row of the LOV results. It includes t |
| `moreValuesExist` | bool | true indicates there are more values available which will can be retrieved by a call to the getNextValues operation |
| `behaviorData` | Teamcenter::Soa::Core::_2013_05::LOV::LOVBehaviorData | LOV data used to define the UI component behavior. This includes data such as LOV usage, Style, Lov Column Names. Additi |
| `lovData` | Teamcenter::Soa::Core::_2013_05::LOV::LOVData | If moreValuesExist is true, this object is passed as input to the getNextValues operation to get the next list of LOV se |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData |

---

#### 3.17.9 validateLOVValueSelections（2013-05）

**接口路径：** `Core-2013-05-LOV/validateLOVValueSelections`

**API 版本：** `2013-05`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 此操作 can be invoked after selecting a value from the LOV. Use 此操作 to do additional validation to be done on server such as validating Range value, getting the dependent 属性 values in case of interdependent LOV (resetting the dependendent 属性 values), Coordinated LOVs ( populating dependent 属性 values )

**Soa Inclusion：** `Teamcenter.Soa.Core._2013_05.LOV.validateLOVValueSelections`

**请求（input）：**

```json
{
  "lovInput": {
    "owningObject": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "boName": "",
    "operationName": "",
    "propertyValues": {}
  },
  "propName": "",
  "uidOfSelectedRows": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `lovInput` | Teamcenter::Soa::Core::_2013_05::LOV::LOVInput | updated LOV input with new selection |
| `propName` | std::string | It is the name of the Property for which LOV is being evaluated |
| `uidOfSelectedRows` | std::string[] | Pass the uids from the selected rows. Every LovValueRow returned from server is designated with valid UID for dynamic LO |

**响应（output）：**

```json
{
  "propHasValidValues": "",
  "dependentPropNames": [
    ""
  ],
  "updatedPropValues": {
    "uid": "",
    "propInternalValues": {},
    "propInternalValueTypes": {},
    "propDisplayValues": {},
    "childRows": []
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `propHasValidValues` | bool | Indicates whether input property has valid values. |
| `dependentPropNames` | std::string[] | Names of dependent properties server modified to be updated by client as a results of dependency with input property sel |
| `updatedPropValues` | Teamcenter::Soa::Core::_2013_05::LOV::LOVValueRow | Updated property values. It contains both internal and display values of the updated properties.  It can be empty. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The service data. |

---

### 3.18 API 版本 2014-06

**Service：** DataManagement、DigitalSignature、Reservation  **操作数：** 8

#### 3.18.1 getTraceReport2（2014-06）

**接口路径：** `Core-2014-06-DataManagement/getTraceReport2`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates a Trace Report for the input objects. The report will contain information about complying as well as defining objects which are connected to input object using FND_TraceLink, or its subtype. 此操作 checks if there is any FND_TraceLink relation starting or ending from input object(s). If FND_TraceLink relation exists for input object(s), then …

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.DataManagement.getTraceReport2`

**请求（input）：**

```json
{
  "input": [
    {
      "selectedObjs": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "reportType": "",
      "exportTo": "",
      "exportTemplate": "",
      "exportColumnNames": [
        ""
      ],
      "reportDepth": "",
      "isIndirectTraceReportNeeded": "",
      "filteredTraceLinkTypes": [
        ""
      ],
      "filteredObjectTypes": [
        ""
      ],
      "scopeLines": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "propertyFilterInput": [
        {
          "logicalOperatorType": "",
          "propertyName": "",
          "operatorType": "",
          "propertyValue": ""
        }
      ],
      "sortPropName": "",
      "sortDirection": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2012_10::DataManagement::TraceabilityInfoInput1[] | Information required to generate a trace report. The object(s) (for which trace report needs to be generated), trace rep |

**响应（output）：**

```json
{
  "traceReports": [
    {
      "defRootNode": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "srcContextName": "",
        "tarContextName": "",
        "bomView": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "contextLineObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isDirectLink": "",
        "isTraceLinkObj": "",
        "childNodes": []
      },
      "compRootNode": {
        "object": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "displayObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "srcContextName": "",
        "tarContextName": "",
        "bomView": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "contextLineObj": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isDirectLink": "",
        "isTraceLinkObj": "",
        "childNodes": []
      },
      "selectedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "persistentObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ]
    }
  ],
  "transientFileReadTickets": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `traceReports` | Teamcenter::Soa::Core::_2014_06::DataManagement::TraceReport2[] | All of the requested Trace Reports. |
| `transientFileReadTickets` | std::string[] | The transient file read tickets for the exported file, this is specific to Export to Excel. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data. |

---

#### 3.18.2 getTraceReportLegacy（2014-06）

**接口路径：** `Core-2014-06-DataManagement/getTraceReportLegacy`

**API 版本：** `2014-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates a Trace Report for the input objects. 此操作 返回 information about complying as well as defining objects which are connected to selected object using FND_TraceLink or its subtype of GRM relation. Trace links can be between following objects: 1. Between occurrences of an ItemRevision 2. Between any two WorkspaceObject. If indirect trace re…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.DataManagement.getTraceReportLegacy`

**请求（input）：**

```json
{
  "input": {
    "selectedObjs": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "reportType": "",
    "reportDepth": "",
    "isIndirectTraceReportNeeded": "",
    "relationTypeName": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2011_06::DataManagement::TraceabilityInfoInput | A TraceabilityInfoInput structure to generate a Trace Report.This input structure holds selected objects for which trace |

**响应（output）：**

```json
{
  "traceReports": [
    {
      "definingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "contextLineObj": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "contextLineObj": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "indirectDefiningTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "contextLineObj": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "contextLineObj": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "complyingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "contextLineObj": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "contextLineObj": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "indirectComplyingTree": [
        {
          "parent": {
            "contextName": "",
            "displayObj": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "object": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "bomView": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "contextLineObj": {
              "uid": "",
              "type": "",
              "className": ""
            }
          },
          "children": [
            {
              "contextName": "",
              "displayObj": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "object": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "bomView": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "contextLineObj": {
                "uid": "",
                "type": "",
                "className": ""
              }
            }
          ]
        }
      ],
      "selectedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "persistentObjects": [
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
| `traceReports` | Teamcenter::Soa::Core::_2014_06::DataManagement::TraceReportLegacy[] | This member holds all the Trace Reports user has asked for. This is list of <br />TraceReport type of structures. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data. |

---

#### 3.18.3 applySignatures（2014-06）

**接口路径：** `Core-2014-06-DigitalSignature/applySignatures`

**API 版本：** `2014-06`  
**Service：** `DigitalSignature`  
**Library：** `Core`

**说明：** 此操作 applies digital signature to a list of 业务对象 provided in the input. 该操作 input is a list of DigitalSignatureInput structures. Each structure in this list consists of details pertaining to the 业务对象 and its corresponding CMS (Cryptographic Message Syntax). Digital Signature is allowed to be applied on 业务对象 for which the…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.DigitalSignature.applySignatures`

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
      "encryptedString": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2014_06::DigitalSignature::ApplySignaturesInputData[] | A list of DigitalSignatureInput structures containing the business object and its corresponding CMS ( Cryptographic Mess |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.18.4 getSignatureMessages（2014-06）

**接口路径：** `Core-2014-06-DigitalSignature/getSignatureMessages`

**API 版本：** `2014-06`  
**Service：** `DigitalSignature`  
**Library：** `Core`

**说明：** 此操作 返回 signature messages for a list of 业务对象. These signature messages are used by SOA framework method com.Teamcenter.soa.client.PKCS7.sign API to generate CMS string (Cryptographic Message Syntax). 该操作 response 获取ignatureMessagesResponse contains details of signature messages computed for each of the input 业务对象 along with…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.DigitalSignature.getSignatureMessages`

**请求（input）：**

```json
{
  "targetObject": [
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
| `targetObject` | Teamcenter::BusinessObject[] | A list of business objects for which signature messages need to be computed. |

**响应（output）：**

```json
{
  "output": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "message": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2014_06::DigitalSignature::GetSignatureMessagesOutput[] | List of getSignatureMessagesOuput structures.  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | ServiceData Containing list of partial errors and details of business objects for which signature message computation wa |

---

#### 3.18.5 voidSignatures（2014-06）

**接口路径：** `Core-2014-06-DigitalSignature/voidSignatures`

**API 版本：** `2014-06`  
**Service：** `DigitalSignature`  
**Library：** `Core`

**说明：** 此操作 voids the selected digital signatureson a given target object.. The details of the electronic signature may be obtained by calling the requisite SOA framework method com.Teamcenter.soa.client.PKCS7.sign. ..This is provided as input to the voidDigitalSignatures opearation along with the other inputs. Successful completion of 该操作, is an indication that…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.DigitalSignature.voidSignatures`

**请求（input）：**

```json
{
  "input": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "signatureobject": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "comment": ""
    }
  ],
  "electronicSignature": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2014_06::DigitalSignature::VoidSignaturesInputData[] | This structure contains input parameters required for voidSignatures operation. |
| `electronicSignature` | std::string | An electronic signature that will be used to validate that the person requesting the void operation is the one who logge |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.18.6 bulkCancelCheckout（2014-06）

**接口路径：** `Core-2014-06-Reservation/bulkCancelCheckout`

**API 版本：** `2014-06`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 cancels a check-out for a set of previously checked-out 业务对象 in bulk. The objects will be restored to the pre-check-out state. Only one user can perform a cancel check-out transaction on the object if the user has enough privilege on the object. This action may be applied to remote checked-out objects, and will cancel the check-out and records the …

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.Reservation.bulkCancelCheckout`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of objects which are in the checked-out state.(e.g. Dataset, Item, ItemRevision ) |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.18.7 bulkCheckin（2014-06）

**接口路径：** `Core-2014-06-Reservation/bulkCheckin`

**API 版本：** `2014-06`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 checks-in a set of previously checked-out 业务对象 in bulk. 此操作 takes care of all complex business logic involved to check-in passed in 业务对象. Each input object is verified that it is locally owned, site owned, and not transferred to another user after the checkout was performed. 此操作 validates precondition defined per t…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.Reservation.bulkCheckin`

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of objects which are in the checked-out state. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.18.8 bulkCheckout（2014-06）

**接口路径：** `Core-2014-06-Reservation/bulkCheckout`

**API 版本：** `2014-06`  
**Service：** `Reservation`  
**Library：** `Core`

**说明：** 此操作 checks out a set of 业务对象 with given comment and, change identifier in bulk fashion. Only one user can perform a check-out transaction on the object. The user must have sufficient privilege on the object or the checkout will fail. 此操作 allows for remote check-out and records the check-out transaction event. In the case where the reservatio…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_06.Reservation.bulkCheckout`

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
  "comment": "",
  "changeId": "",
  "reservationType": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objects` | Teamcenter::BusinessObject[] | A list of business objects to be checked out. |
| `comment` | std::string | A comment describing the reason for the check-out. An empty string is allowed. |
| `changeId` | std::string | The ID of the change. Empty string allowed. |
| `reservationType` | int | Following two types of reservation are allowed.<br /><ul><ul><li type="disc">RES_EXCLUSIVE_RESERVE for checking out busi |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.19 API 版本 2014-10

**Service：** DataManagement、ProjectLevelSecurity  **操作数：** 8

#### 3.19.1 addChildren（2014-10）

**接口路径：** `Core-2014-10-DataManagement/addChildren`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 adds a list of objects as children to a list of parent objects which could be related by relation or reference 属性. If the 属性 name is not supplied as input it will use the default relation 属性 between the parent and the children given by ParentTypeName>_ChildTypeName>_default_relation. Please see the Preferences and Environment variables refe…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.addChildren`

**请求（input）：**

```json
{
  "inputData": [
    {
      "clientId": "",
      "parentObj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childrenObj": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "propertyName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputData` | Teamcenter::Soa::Core::_2014_10::DataManagement::ChildrenInputData[] | A list which contains list of children objects, parent object and the <br />property name (optional) by which the parent |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.19.2 generateIdsUsingIDGenerationRules（2014-10）

**接口路径：** `Core-2014-10-DataManagement/generateIdsUsingIDGenerationRules`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates object ids using ID Generation Rules associated with the 业务对象's 属性. Currently only Item and its subtypes are supported. Object ids are generated using information provided in createInput. 此操作 should be called in case of a specific requirement where ID Generation is independent of creating Objects. (e.g. in case of some CAD…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.generateIdsUsingIDGenerationRules`

**请求（input）：**

```json
{
  "generateIdsInputs": [
    {
      "createInput": {
        "boName": "",
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
      "propertyName": "",
      "quantity": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `generateIdsInputs` | Teamcenter::Soa::Core::_2014_10::DataManagement::GenerateIdInput[] | <ul><ul><li type="disc">A Structure containing input values for the operation</li></ul></ul> |

**响应（output）：**

```json
{
  "generateIdsOutput": [
    {
      "generatedIDs": [
        ""
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `generateIdsOutput` | Teamcenter::Soa::Core::_2014_10::DataManagement::GenerateIdResponseStruct[] | Multiple lists of Generated IDs. Each list corresponds to the individual elements in GenerateIdInputs. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Holds error stacks. |

---

#### 3.19.3 getDeepCopyData（2014-10）

**接口路径：** `Core-2014-10-DataManagement/getDeepCopyData`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 获取深拷贝所需的数据结构。

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.getDeepCopyData`

**请求（input）：**

```json
{
  "deepCopyDataInput": [
    {
      "operation": "",
      "businessObject": {
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
| `deepCopyDataInput` | Teamcenter::Soa::Core::_2014_10::DataManagement::DeepCopyDataInput[] | A list ofPOM_objects and operation type. |

**响应（output）：**

```json
{
  "deepCopyInfoMap": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `deepCopyInfoMap` | Teamcenter::Soa::Core::_2014_10::DataManagement::DeepCopyInfoMap | A map of business objects and DeepCopyData (POM_object/DeepCopyData). Each business object from the method input will ha |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing errors, etc. The plain object list of the Service data is populated with the target objects whic |

---

#### 3.19.4 getPasteRelations2（2014-10）

**接口路径：** `Core-2014-10-DataManagement/getPasteRelations2`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 the paste relation names for the given parent 业务对象 and the child 业务对象 name; the expandable relations and the preferred paste relation are also indicated.

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.getPasteRelations2`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "obj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childTypeName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2013_05::DataManagement::GetPasteRelationsInputData[] | List of parent parent and child buiness objects<b> </b>with clientId |

**响应（output）：**

```json
{
  "outputs": [
    {
      "clientId": "",
      "pasteRelInfo": [
        {
          "pastRelName": "",
          "pastRelDisplayName": "",
          "isExpandable": ""
        }
      ],
      "indexOfPreferred": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `outputs` | Teamcenter::Soa::Core::_2014_10::DataManagement::GetPasteRelationsOutput2[] | A list of paste relation output. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | <font face="courier" height="10">Service Data</font> including partial errors that are mapped to the client id from the  |

---

#### 3.19.5 pruneNamedReferences（2014-10）

**接口路径：** `Core-2014-10-DataManagement/pruneNamedReferences`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 performs a prune operation by a given list of 数据集 named references, per the following criteria 1. Remove the input named references from their owning 数据集 2. Delete the input named reference objects 3. Delete the owning 数据集 objects which contain no named references after the prune operation 4. The pruned named references, deleted 数据集s and update…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.pruneNamedReferences`

**请求（input）：**

```json
{
  "namedReferences": [
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
| `namedReferences` | Teamcenter::POM_object[] | List of <b>Dataset</b> <font face="courier" height="10">named references</font> to be pruned |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.19.6 removeChildren（2014-10）

**接口路径：** `Core-2014-10-DataManagement/removeChildren`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 removes a list of objects as children to a list of parent objects which could be related by relation or reference 属性. If the 属性 name is not supplied as input it will use the default relation 属性 between the parent and the children given by ParentTypeName>_ChildTypeName>_default_relation. Please see the Preferences and Environment variables r…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.removeChildren`

**请求（input）：**

```json
{
  "inputData": [
    {
      "clientId": "",
      "parentObj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childrenObj": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "propertyName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputData` | Teamcenter::Soa::Core::_2014_10::DataManagement::ChildrenInputData[] | A  list containing a list of children objects, parent object and relation name (optional) by which parent and children a |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.19.7 saveAsObjectsAndRelate（2014-10）

**接口路径：** `Core-2014-10-DataManagement/saveAsObjectsAndRelate`

**API 版本：** `2014-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 performs SaveAs on the input target 业务对象 and its related objects as new instances. Related objects are identifed using deep copy rules. Optionally, this method relates the new object to the input target object or to a default 文件夹.

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.DataManagement.saveAsObjectsAndRelate`

**请求（input）：**

```json
{
  "iVecSoaSavAsIn": [
    {
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "inputPropValues": {},
      "deepCopyDatas": [
        {
          "attachedObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "propertyName": "",
          "propertyType": "",
          "copyAction": "",
          "isTargetPrimary": "",
          "isRequired": "",
          "copyRelations": "",
          "operationInputTypeName": "",
          "childDeepCopyData": [],
          "operationInputs": {}
        }
      ]
    }
  ],
  "iVecSoaRelteInfoIn": [
    {
      "target": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyName": "",
      "relate": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `iVecSoaSavAsIn` | Teamcenter::Soa::Core::_2014_10::DataManagement::SaveAsIn[] | Input data containing target object, map (PropertyValuesMap) of properties and their corresponding values and DeepCopyDa |
| `iVecSoaRelteInfoIn` | Teamcenter::Soa::Core::_2012_09::DataManagement::RelateInfoIn[] | Input data containing the paste options used to relate the newly created object. |

**响应（output）：**

```json
{
  "output": [
    {
      "targetObject": {
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
  ],
  "saveAsTrees": [
    {
      "originalObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectCopy": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "childSaveAsNodes": []
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsOut[] | SaveAsout vector |
| `saveAsTrees` | Teamcenter::Soa::Core::_2011_06::DataManagement::SaveAsTree[] | List of the input target objects that holds mapping between the original objects and the copied  objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing created objects, errors, etc |

---

#### 3.19.8 propagateData（2014-10）

**接口路径：** `Core-2014-10-ProjectLevelSecurity/propagateData`

**API 版本：** `2014-10`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 can propagate security or anyother Teamcenter data based on the source object and applicable propagation rules. The propagateData operation should only be invoked when propagation rule is configured to run in background. The propagation rule defined in BMIDE states what data from source to desination object has to be propagated.For example project_list, licens…

**Soa Inclusion：** `Teamcenter.Soa.Core._2014_10.ProjectLevelSecurity.propagateData`

**请求（input）：**

```json
{
  "propagateDataElements": [
    {
      "operationType": "",
      "sourceObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propagationRulesInfo": [
        {
          "applicablePropagationRules": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "associatedObject": {
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
| `propagateDataElements` | Teamcenter::Soa::Core::_2014_10::ProjectLevelSecurity::PropagateDataElement[] | A list  the source object, operation type and the applicable propagation rules  that define the data to be propagated. |

**响应（output）：**

```json
"void"
```

---

### 3.20 API 版本 2015-07

**Service：** DataManagement  **操作数：** 6

#### 3.20.1 createRelateAndSubmitObjects2（2015-07）

**接口路径：** `Core-2015-07-DataManagement/createRelateAndSubmitObjects2`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：创建Relate And Submit 对象s2。This is a generic operation for creation of 业务对象. This will also create any secondary (compounded) objects that need to be created, assuming the CreateInput2 for the secondary object is represented in the recursive CreateInput2 object e.g. Item is primary object that also 创建 Item Master and ItemRevision. ItemRevision in turn 创建 ItemRevision Master. The …

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.createRelateAndSubmitObjects2`

**请求（input）：**

```json
{
  "createInputs": [
    {
      "clientId": "",
      "createData": {
        "boName": "",
        "propertyNameValues": {},
        "compoundCreateInput": {}
      },
      "dataToBeRelated": {},
      "workflowData": {},
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "pasteProp": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `createInputs` | Teamcenter::Soa::Core::_2015_07::DataManagement::CreateIn2[] | This is a list of <i>CreateIn2</i> objects in which each one represents the information required for the following opera |

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOut[] | Vector of output objects representing objects that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data including partial errors that are mapped to the client id from the input. Created objects are also added to |

---

#### 3.20.2 generateNextValuesForProperties（2015-07）

**接口路径：** `Core-2015-07-DataManagement/generateNextValuesForProperties`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates values for the given 属性 of an object(s) during create/revise/save as action based on the user exits or naming rules configured on those 属性.Customer user exits are given priority over the naming rules if both of them are configured on the same 属性. The counter has to be set active on the naming rule in order to generate the next v…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.generateNextValuesForProperties`

**请求（input）：**

```json
{
  "propertyNamingRuleInfo": [
    {
      "clientId": "",
      "operationType": "",
      "businessObjectTypeName": "",
      "propertyNameAttachedPattern": {},
      "propertyValuesMap": {},
      "additionalInputMap": {},
      "compoundObjectInput": {},
      "propertyNameContextListMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `propertyNamingRuleInfo` | Teamcenter::Soa::Core::_2015_07::DataManagement::PropertyNamingruleInfo[] | This is the input that the operation 'generateNextValuesForProperties' expects. This contains the list of properties for |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "generatedValues": [
    {
      "clientId": "",
      "generatedValues": {},
      "generatedValuesOfSecondaryObjects": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | The Service Data with partial errors for each GenerateNextValuesInput and identified by  its clientId. |
| `generatedValues` | Teamcenter::Soa::Core::_2013_05::DataManagement::GeneratedValuesOutput[] | A list of GeneratedValuesOutput one for each entry in generateNextvaluesIn input list and  identified by its clientId. |

---

#### 3.20.3 getCreatbleSubBuisnessObjectNames（2015-07）

**接口路径：** `Core-2015-07-DataManagement/getCreatbleSubBuisnessObjectNames`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 sub 业务对象 names that are displayable to the login user in the object creation dialog and their display names for each primary 业务对象 given as the input, based on specified context. Returned 业务对象 lists have exclusions of 业务对象 and their secondary 业务对象 as per the exclusion preference and/or exlusion bu…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.getCreatbleSubBuisnessObjectNames`

**请求（input）：**

```json
{
  "input": [
    {
      "boName": "",
      "exclusionPreference": "",
      "exclusionBONames": [
        ""
      ],
      "context": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2015_07::DataManagement::CreatableSubBONamesInput[] | A list of primary business object names and the exclusion preferences and/or types, along with context, for which the cr |

**响应（output）：**

```json
{
  "output": [
    {
      "boName": "",
      "creatableBONames": [
        {
          "boName": "",
          "boDisplayName": "",
          "boParents": [
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
| `output` | Teamcenter::Soa::Core::_2015_07::DataManagement::CreatableBusinessObjectsOut[] | List of output objects representing the creatable business objects displayable in the Create dialog |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data including the partial errors that are mapped to the input primary business objects |

---

#### 3.20.4 getDeepCopyData（2015-07）

**接口路径：** `Core-2015-07-DataManagement/getDeepCopyData`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 获取深拷贝所需的数据结构。

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.getDeepCopyData`

**请求（input）：**

```json
{
  "deepCopyDataInput": {
    "operation": "",
    "targetObject": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "deepCopyDatas": [
      {
        "attachedObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "propertyValuesMap": {},
        "operationInputTypeName": "",
        "childDeepCopyData": [],
        "operationInputs": {}
      }
    ],
    "parentDeepCopyData": {
      "attachedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyValuesMap": {},
      "operationInputTypeName": "",
      "childDeepCopyData": [],
      "operationInputs": {}
    },
    "selectedBO": {
      "uid": "",
      "type": "",
      "className": ""
    }
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `deepCopyDataInput` | Teamcenter::Soa::Core::_2015_07::DataManagement::DeepCopyDataInput | The information about the business object (which save-as and revise will be performed ), its DeepCopyData, the business  |

**响应（output）：**

```json
{
  "selectedBOIsDuplicated": "",
  "deepCopyDatas": [
    {
      "attachedObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyValuesMap": {},
      "operationInputTypeName": "",
      "childDeepCopyData": [],
      "operationInputs": {}
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `selectedBOIsDuplicated` | bool | This indicates whether the <font face="courier" height="10">selectedBO</font> from the method input already has DeepCopy |
| `deepCopyDatas` | Teamcenter::Soa::Core::_2014_10::DataManagement::DeepCopyData[] | A list of DeepCopyData for the <font face="courier" height="10">selectedBO</font> from the method input. The DeepCopyDat |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data containing errors, etc. The plain object list of the Service data is populated with the target objects whic |

---

#### 3.20.5 getDomainOfObjectOrType（2015-07）

**接口路径：** `Core-2015-07-DataManagement/getDomainOfObjectOrType`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 identifies the application domain information of the input design artifact object or type name and the domain value will be returned as part of the response. The input object can be any WorkspaceObject. The application domain where the object or the type belongs to is returned as domain value. Out of the box the supported application domains are &ldquo;Mechani…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.getDomainOfObjectOrType`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "inputDesignArtifact": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "typName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2015_07::DataManagement::GetDomainInput[] |  Input object or type name for which the application domain information is to be identified. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "domain": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2015_07::DataManagement::DomainOutput[] | The domain information output. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Holds any partial errors occurred during the operation. |

---

#### 3.20.6 getLocalizedProperties2（2015-07）

**接口路径：** `Core-2015-07-DataManagement/getLocalizedProperties2`

**API 版本：** `2015-07`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** Typically 业务对象 属性 values are returned in the locale of the current 会话, 此操作 返回 desired 属性 values in any of the supported locales of the Teamcenter server. String type 属性 may be localized with values for each supported locale, 此操作 will return the translated values for one or more desired locales.

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_07.DataManagement.getLocalizedProperties2`

**请求（input）：**

```json
{
  "propertyInfo": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propsToget": [
        {
          "name": "",
          "locales": [
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
| `propertyInfo` | Teamcenter::Soa::Core::_2010_04::DataManagement::PropertyInfo[] | A list of desired business objects, property names, and locales to retrieve those properties in. |

**响应（output）：**

```json
{
  "output": [
    {
      "businessObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyValues": [
        {
          "name": "",
          "values": [
            ""
          ],
          "locale": "",
          "seqNum": "",
          "status": [
            ""
          ],
          "internalStatus": [
            ""
          ],
          "statusDesc": [
            ""
          ],
          "master": ""
        }
      ]
    }
  ],
  "partialErrors": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2015_07::DataManagement::LocalizedPropertyValuesInfo2[] | A list of structure LocalizedPropertyValuesInfo2 to keep the localized property values info. |
| `partialErrors` | Teamcenter::Soa::Server::ServiceData | Used for storing partial error and standard service data. |

---

### 3.21 API 版本 2015-10

**Service：** DataManagement、FileManagement、Session  **操作数：** 7

#### 3.21.1 reassignParticipants（2015-10）

**接口路径：** `Core-2015-10-DataManagement/reassignParticipants`

**API 版本：** `2015-10`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `reassignParticipants`。Reassigns the participant roles from one user to another for a given list of participant types on the input list of objects. The Particpant for the fromAssignee User is replaced with the Particpant for the toAssignee User. If the toAssignee User already exists as participant, then the fromAssignee User will not be replaced.

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.DataManagement.reassignParticipants`

**请求（input）：**

```json
{
  "reassignParticipantInfo": [
    {
      "itemRevs": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "fromAssignee": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "toAssignee": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "participantTypes": [
        ""
      ],
      "allParticipantTypes": "",
      "comments": "",
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `reassignParticipantInfo` | Teamcenter::Soa::Core::_2015_10::DataManagement::ReassignParticipantInfo[] | A list of structures containing a list of input objects whose participant roles are reassigned, assignee to reassign fro |

**响应（output）：**

```json
{
  "failedObjects": [
    {
      "clientId": "",
      "failedItemRevs": [
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
| `failedObjects` | Teamcenter::Soa::Core::_2015_10::DataManagement::ReassignParticipantOutput[] | A list of failed objects information. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The modified participant objects are returned along with partial errors. |

---

#### 3.21.2 getDigestInfoForDatasets（2015-10）

**接口路径：** `Core-2015-10-FileManagement/getDigestInfoForDatasets`

**API 版本：** `2015-10`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 获取 the file digest information for the ImanFile objects contained in the 数据集 objects. These digests can be used by clients to check for file integrity. Clients must use the same digest algorithm (as returned by 此操作) to compute the digest on their end and compare with the digest returned by 此操作. The Teamcenter File Management System (FMS) computes …

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.FileManagement.getDigestInfoForDatasets`

**请求（input）：**

```json
{
  "datasets": [
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
| `datasets` | Teamcenter::Dataset[] | the <b>Dataset</b> objects for which the digest information is to be obtained for each of the <b>ImanFile</b> objects in |

**响应（output）：**

```json
{
  "datasetDigestInfo": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `datasetDigestInfo` | Teamcenter::Soa::Core::_2015_10::FileManagement::DatasetDigestInfoMap | A list of DatasetDigestInfos objects. It contains the digest information for each file referenced by each of the input d |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData response that can contain the partial errors. |

---

#### 3.21.3 getDigestInfoForFiles（2015-10）

**接口路径：** `Core-2015-10-FileManagement/getDigestInfoForFiles`

**API 版本：** `2015-10`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 获取 the file digest information for all the ImanFile objects specified using files. These digests can be used by clients to check for file integrity. Clients must use the same digest algorithm (as returned by 此操作) to compute the digest on their end and compare with the digest returned by 此操作. The Teamcenter File Management System (FMS) computes and sto…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.FileManagement.getDigestInfoForFiles`

**请求（input）：**

```json
{
  "files": [
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
| `files` | Teamcenter::ImanFile[] | The <b>ImanFile</b> objects for which the digest information is to be obtained. |

**响应（output）：**

```json
{
  "fileDigestInfo": {},
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `fileDigestInfo` | Teamcenter::Soa::Core::_2015_10::FileManagement::FileDigestInfoMap | A map (<b>ImanFile</b>, list of DigestInfo) of input <b>ImanFile</b> objects to the digest informationa for the file. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData response that can contain the partial errors. |

---

#### 3.21.4 getTypeDescriptions2（2015-10）

**接口路径：** `Core-2015-10-Session/getTypeDescriptions2`

**API 版本：** `2015-10`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 获取 the Meta data for the named Business Model object types based on the configurations specified by the client. To improve performance, clients can specify to exclude certain Meta data such as LOV References and Naming Rule References for the given types. If options are not provided 此操作 返回 all meta data associated with given types.

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.Session.getTypeDescriptions2`

**请求（input）：**

```json
{
  "typeNames": [
    ""
  ],
  "options": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `typeNames` | std::string[] | List of Business Model Object type names. |
| `options` | Teamcenter::Soa::Core::_2015_10::Session::TypeDescriptionOptions | A map (string/List of strings) of supported options and the option values.<br />The supported options for the map are li |

**响应（output）：** 无

---

#### 3.21.5 setUserSessionStateAndUpdateDefaults（2015-10）

**接口路径：** `Core-2015-10-Session/setUserSessionStateAndUpdateDefaults`

**API 版本：** `2015-10`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 设置 the desired user 会话 state values. 此操作 also updates the default value of the Group, Role and Project when these 会话 states are changed. To clear a field's value, client needs to pass an empty string "" as the value. Failure to set a particular state value will result in a Partial Error with the clientId set to the name of the state prop…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.Session.setUserSessionStateAndUpdateDefaults`

**请求（input）：**

```json
{
  "pairs": [
    {
      "name": "",
      "value": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `pairs` | Teamcenter::Soa::Core::_2007_12::Session::StateNameValue[] | A list of name/value pairs (string/string) of state properties to set. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.21.6 sponsoredLogin（2015-10）

**接口路径：** `Core-2015-10-Session/sponsoredLogin`

**API 版本：** `2015-10`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `sponsoredLogin`。Authenticates the sponsoring user`s credentials and initialize a Teamcenter 会话 for the sponsored user. 该操作 will throw an InvalidCredentialsException as described below. When the 客户端应用 is deployed to a 4Tier environment the login operation also contributes to the assignment of a Teamcenter server instance to the client 会话. The sponsoring user,…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.Session.sponsoredLogin`

**请求（input）：**

```json
{
  "sponsoringUser": "",
  "password": "",
  "sponsoredUser": "",
  "sponsoredGroup": "",
  "sponsoredRole": "",
  "locale": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sponsoringUser` | std::string | The sponsoring user`s Teamcenter user name. This is case insensitive (jdoe or JDOE) |
| `password` | std::string | The sponsoring user`s Teamcenter password. |
| `sponsoredUser` | std::string | Sponsored user`s user name. This is case insensitive (jdoe or JDOE) |
| `sponsoredGroup` | std::string | The group ID for the sponsored user. |
| `sponsoredRole` | std::string | The role of the sponsored user. |
| `locale` | std::string | The locale to be used by the Teamcenter server process for this session. If null, the server`s default locale will be us |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

#### 3.21.7 sponsoredLoginSSO（2015-10）

**接口路径：** `Core-2015-10-Session/sponsoredLoginSSO`

**API 版本：** `2015-10`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `sponsoredLoginSSO`。Authenticates the sponsoring user using Single-Sign-On (SSO) credentials and initialize a Teamcenter 会话 for the sponsored user client. The username and ssoCredentials arguments are for the sponsoring user and must be obtained from Teamcenter's Security Services. The SsoCredentials class offers a simple API to get these values. 该操作 will throw an InvalidCredenti…

**Soa Inclusion：** `Teamcenter.Soa.Core._2015_10.Session.sponsoredLoginSSO`

**请求（input）：**

```json
{
  "sponsoringUser": "",
  "ssoCredentials": "",
  "sponsoredUser": "",
  "sponsoredGroup": "",
  "sponsoredRole": "",
  "locale": "",
  "sessionDiscriminator": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `sponsoringUser` | std::string | The sponsoring user`s Teamcenter user name. This is case insensitive (jdoe or JDOE) |
| `ssoCredentials` | std::string | The sponsoring user's Teamcenter SSO credentials. This should have been obtained from Teamcenter Security Services. |
| `sponsoredUser` | std::string | Sponsored user`s user name. This is case insensitive (jdoe or JDOE) |
| `sponsoredGroup` | std::string | The group ID for the sponsored user. |
| `sponsoredRole` | std::string | The role of the sponsored user. |
| `locale` | std::string | The locale to be used by the Teamcenter server process for this session. If null, the server`s default locale will be us |
| `sessionDiscriminator` | std::string | Client defined identifier for this session. This argument is ignored when the client application is deployed in a 2Tier  |

**响应（output）：**

```json
{
  "user": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "groupMember": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `user` | Teamcenter::User | The <b>User</b> of this session. |
| `groupMember` | Teamcenter::GroupMember | The <b>GroupMember</b> of this session. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The <b>GroupMember</b> and <b>User</b> are added to the plain object list. |

---

### 3.22 API 版本 2016-05

**Service：** DataManagement  **操作数：** 3

#### 3.22.1 generateContextSpecificIDs（2016-05）

**接口路径：** `Core-2016-05-DataManagement/generateContextSpecificIDs`

**API 版本：** `2016-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `generateContextSpecificIDs`。Generates the range of unique IDs for input context names. The number of IDs generated for each context name depends on the input. If for a given context name, the ID has been reset using Teamcenter service resetContextID, then this service generates IDs for that context from the beginning. ID generation will also reset when the maximum limit is met. This limit is maximum nu…

**Soa Inclusion：** `Teamcenter.Soa.Core._2016_05.DataManagement.generateContextSpecificIDs`

**请求（input）：**

```json
{
  "generateContextIDsIn": [
    {
      "clientID": "",
      "contextName": "",
      "numberOfIDs": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `generateContextIDsIn` | Teamcenter::Soa::Core::_2016_05::DataManagement::GenerateContextIDsInput[] | List of GenerateContextIDsInput which contains the context name and number of IDs to be generated for that context. Cont |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "generatedContextIDValues": [
    {
      "contextName": "",
      "generatedIDs": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Partial Errors are returned in the ServiceData when service generateContextSpecificIDs fails to generate IDs of any of t |
| `generatedContextIDValues` | Teamcenter::Soa::Core::_2016_05::DataManagement::GeneratedContextIDs[] | A list of GeneratedContextIDs, which contains each of the context names and IDs generated for it by service generateCont |

---

#### 3.22.2 resetContextID（2016-05）

**接口路径：** `Core-2016-05-DataManagement/resetContextID`

**API 版本：** `2016-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `resetContextID`。This service enables the client to reset the ID for given context names. When the IDs for a context name are reset, ID generation will begain from beginning value. WARNING: Be advised that if a client re设置 the ID for a context name, it is possible that repeated IDs will be returned from generateContextSpecificIDs service for that context name.

**Soa Inclusion：** `Teamcenter.Soa.Core._2016_05.DataManagement.resetContextID`

**请求（input）：**

```json
{
  "contextNames": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `contextNames` | std::string[] | List of the context names for those, IDs to be reset. Empty strings should not be used to reset ID. An error is returned |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.22.3 setPropertiesAndDetectOverwrite（2016-05）

**接口路径：** `Core-2016-05-DataManagement/setPropertiesAndDetectOverwrite`

**API 版本：** `2016-05`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 detects the overwrite condition for the 业务对象 instances if those are modified by any other 会话 concurrently and updates the remaining objects with the new 属性 values provided. Use 此操作 if the overwrite detection is required to avoid any unintentional overwriting of the objects due to concurrent modification of the object. The overw…

**Soa Inclusion：** `Teamcenter.Soa.Core._2016_05.DataManagement.setPropertiesAndDetectOverwrite`

**请求（input）：**

```json
{
  "propData": [
    {
      "businessObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "vecPropNameVal": [
        {
          "propertyName": "",
          "oldValues": [
            ""
          ],
          "newValues": [
            ""
          ]
        }
      ],
      "lastSavedDateExportedToClient": "0001-01-01T00:00:00"
    }
  ],
  "options": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `propData` | Teamcenter::Soa::Core::_2016_05::DataManagement::PropData[] | List of PropData structure which consists of information about the objects, old values of properties and new values of   |
| `options` | Teamcenter::Soa::Core::_2016_05::DataManagement::OptionsMap | A map ( string / list of strings ) of options. Valid keys are:<br />1. SKIP_SAVING_ALL_OBJECTS_ON_CONFLICT: Valid values |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "overwriteDetectedObjPropMap": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | This is the service data. It contains the updated objects and their properties. |
| `overwriteDetectedObjPropMap` | Teamcenter::Soa::Core::_2016_05::DataManagement::ObjectPropertiesMap | The  map ( business object / list of string ) contains the objects and properties list for which overwrite condition has |

---

### 3.23 API 版本 2016-09

**Service：** DataManagement  **操作数：** 1

#### 3.23.1 createAttachAndSubmitObjects（2016-09）

**接口路径：** `Core-2016-09-DataManagement/createAttachAndSubmitObjects`

**API 版本：** `2016-09`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 创建对象、建立附件关系并提交（组合操作）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2016_09.DataManagement.createAttachAndSubmitObjects`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientId": "",
      "createData": {
        "boName": "",
        "propertyNameValues": {},
        "compoundCreateInput": {}
      },
      "dataToBeRelated": {},
      "workflowData": {},
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "pasteProp": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2015_07::DataManagement::CreateIn2[] | This is a list of CreateIn2 objects in which each one represents the information required for the following operations:< |

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
      ],
      "datasets": [
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
                    "namedReferenceName": "",
                    "isText": "",
                    "allowReplace": ""
                  },
                  "ticket": ""
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
| `output` | Teamcenter::Soa::Core::_2016_09::DataManagement::CreateAttachOut[] | List of output objects representing objects that were created |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data including partial errors that are mapped to the client id |

---

### 3.24 API 版本 2016-10

**Service：** ProjectLevelSecurity  **操作数：** 1

#### 3.24.1 getDefaultProject（2016-10）

**接口路径：** `Core-2016-10-ProjectLevelSecurity/getDefaultProject`

**API 版本：** `2016-10`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 a list of the default projects for a given user, group and role combination. If no user is specified, it looks for the default project of the current logged in user. If no group and role is specified, all default projects for the specified user are returned. When TC_show_all_user_projects is set to TRUE, projects are reteturned regardless of the given …

**Soa Inclusion：** `Teamcenter.Soa.Core._2016_10.ProjectLevelSecurity.getDefaultProject`

**请求（input）：**

```json
{
  "tcUser": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "tcGroup": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "tcRole": {
    "uid": "",
    "type": "",
    "className": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `tcUser` | Teamcenter::User | The <b>User</b> object. |
| `tcGroup` | Teamcenter::Group | The <b>Group</b> object in which the user belongs to. |
| `tcRole` | Teamcenter::Role | The <b>Role</b> object in which the user belongs to. |

**响应（output）：**

```json
{
  "applicableProjects": [
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
| `applicableProjects` | Teamcenter::TC_Project[] | List of <b>TC_project</b> objects found. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | A  standard  ServicData. |

---

### 3.25 API 版本 2017-05

**Service：** FileManagement、ProjectLevelSecurity  **操作数：** 8

#### 3.25.1 commitDatasetFilesInBulk（2017-05）

**接口路径：** `Core-2017-05-FileManagement/commitDatasetFilesInBulk`

**API 版本：** `2017-05`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 此操作 up加载 files to a Teamcenter volume and associates them to a 数据集. The mechanism for a 客户端应用 adding files to a Teamcenter volume contains several steps. This mechanism is implemented in the com.Teamcenter.soa.client.FileManagementUtility class, which provides this functionality to clients in a consistent, reusable package. 此操作 is su…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.FileManagement.commitDatasetFilesInBulk`

**请求（input）：**

```json
{
  "commitInput": [
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
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `commitInput` | Teamcenter::Soa::Core::_2006_03::FileManagement::CommitDatasetFileInfo[] | The list of CommitDatasetFileInfo structures returned in the commitInfo element of the GetDatasetWriteTicketsResponse st |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.25.2 replaceFiles（2017-05）

**接口路径：** `Core-2017-05-FileManagement/replaceFiles`

**API 版本：** `2017-05`  
**Service：** `FileManagement`  
**Library：** `Core`

**说明：** 此操作 replaces an existing volume file with a new file that has already been uploaded to a transient volume. It up加载 the file from the transient volume to the regular Teamcenter volume. The original volume file is replaced with the new file, and the ImanFile references the new file. Note that there is no new ImanFile object created. 此操作 includes the ab…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.FileManagement.replaceFiles`

**请求（input）：**

```json
{
  "inputs": [
    {
      "imanFile": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "newFileTicket": "",
      "retainOriginalFileName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2017_05::FileManagement::ReplaceFileInput[] | The input to this operation includes a list of write tickets used to upload the new file to the transient volume.  It al |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.25.3 assignOrRemoveObjectsFromProjects（2017-05）

**接口路径：** `Core-2017-05-ProjectLevelSecurity/assignOrRemoveObjectsFromProjects`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 assigns the given set of workspace objects to the given projects. Similarly, it removes an additional set of given workspace objects from the same set of given projects. If the input contains revision rule and or variant rule these will be applied to the given set of objects for traversing the structure i.e. the project will be propagated to the objects which …

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.assignOrRemoveObjectsFromProjects`

**请求（input）：**

```json
{
  "assignOrRemoveInput": [
    {
      "projectsToAssign": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "objectsForAssignment": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "projectsForRemoval": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "objectsToRemoveFromProjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "contextInfo": {
        "selectedTopLevelObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "variantRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revisionRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "typeOption": "",
        "depth": ""
      },
      "processAsynchronously": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `assignOrRemoveInput` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ProjectAssignOrRemoveInput[] | The list of ProjectAssignOrRemoveInput structure. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.25.4 copyProjects2（2017-05）

**接口路径：** `Core-2017-05-ProjectLevelSecurity/copyProjects2`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 copies the given list of TC_Project objects. 该操作 also copies any information which is in contained in the project. Data such as project team members and any objects assigned to the source project will also be copied to the new project. If a project with given project ID exists in the system then 此操作 will return error 101010. 该操作 …

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.copyProjects2`

**请求（input）：**

```json
{
  "copyProjectInfos": [
    {
      "sourceProject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "projectInfo": {
        "projectId": "",
        "projectName": "",
        "projectDescription": "",
        "useProgramContext": "",
        "active": "",
        "visible": "",
        "teamMembers": [
          {
            "teamMember": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "teamMemberType": ""
          }
        ],
        "clientId": "",
        "propertyMap": {}
      },
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `copyProjectInfos` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::CopyProjectsInfo2[] | List of CopyProjectsInfo2 structure. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

#### 3.25.5 createProjects2（2017-05）

**接口路径：** `Core-2017-05-ProjectLevelSecurity/createProjects2`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 创建 TC_Project objects using the given input information. 此操作 also supports creation of TC_Project object in hierarchical configuration. If the project with given project ID exists in the system then 此操作 will return unique id violation error 101010. However, creation of rest of the projects will continue.

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.createProjects2`

**请求（input）：**

```json
{
  "projectInfos": [
    {
      "projectId": "",
      "projectName": "",
      "projectDescription": "",
      "useProgramContext": "",
      "active": "",
      "visible": "",
      "teamMembers": [
        {
          "teamMember": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "teamMemberType": ""
        }
      ],
      "clientId": "",
      "propertyMap": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectInfos` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ProjectInformation2[] | A list of ProjectInformation2 objects. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

#### 3.25.6 getProjectsForAssignOrRemove（2017-05）

**接口路径：** `Core-2017-05-ProjectLevelSecurity/getProjectsForAssignOrRemove`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 retrieves the assigned projects to the input data and all available projects where the input user is a priveleged member. When multiple 业务对象 are selected 此操作 retrieves the assigned projects which are in common for the complete input data. It also retrieves level or structure information in case of ActiveWorkspace Content context. In Acti…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.getProjectsForAssignOrRemove`

**请求（input）：**

```json
{
  "projectsInput": [
    {
      "user": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "selectedObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "assignedObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "paginationInfo": {
        "startIndexForAvailableProjects": "",
        "maxToReturnForAvailableProjects": ""
      },
      "filterText": "",
      "isAceContext": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectsInput` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ProjectsInput[] | A list of ProjectsInput objects. |

**响应（output）：**

```json
{
  "projectOutput": {
    "assignedProjectsList": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ],
    "selectedObjects": [
      {
        "uid": "",
        "type": "",
        "className": ""
      }
    ]
  },
  "serviceData": "IServiceData",
  "availableProjectList": [
    {
      "uid": "",
      "type": "",
      "className": ""
    }
  ],
  "projectOptions": {},
  "totalFound": "",
  "totalLoaded": "",
  "endIndex": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOutput` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ProjectsOutput | A list of projectsOutput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The SOA framework object containing objects that were created, deleted, or updated by the Service, plain objects, and er |
| `availableProjectList` | Teamcenter::TC_Project[] | A list of available TC_Project objects sorted in  alphabetical order. |
| `projectOptions` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ProjectOptions | A map(string, list of ConfigurationContextChoice) of ActiveWorkspace Content context attributes with the list of ActiveW |
| `totalFound` | int | The total number of projects found. |
| `totalLoaded` | int | The total number of projects loaded. |
| `endIndex` | int | The end index to return the projects. |

---

#### 3.25.7 modifyProjects2（2017-05）

**接口路径：** `Core-2017-05-ProjectLevelSecurity/modifyProjects2`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 modifies the given list of TC_Project objects using the input specified. The input contains new values for all the project 属性. Values for 属性 other than the project team are ignored unless the user is the Project Administrator. The entire Project Team, with the exception of the Project Administrator, is replaced with the specified team. Therefor…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.modifyProjects2`

**请求（input）：**

```json
{
  "modifyProjectsInfos": [
    {
      "sourceProject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "projectInfo": {
        "projectId": "",
        "projectName": "",
        "projectDescription": "",
        "useProgramContext": "",
        "active": "",
        "visible": "",
        "teamMembers": [
          {
            "teamMember": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "teamMemberType": ""
          }
        ],
        "clientId": "",
        "propertyMap": {}
      },
      "clientId": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `modifyProjectsInfos` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::ModifyProjectsInfo2[] | List of ModifyProjectsInfo2 structures. |

**响应（output）：**

```json
{
  "projectOpsOutputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "clientId": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectOpsOutputs` | Teamcenter::Soa::Core::_2012_09::ProjectLevelSecurity::ProjectOpsOutput[] | Vector of ProjectOpsOuput objects. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data with the partial error information |

---

#### 3.25.8 setPropagationEnabledProperties（2017-05）

**接口路径：** `Core-2017-05-ProjectLevelSecurity/setPropagationEnabledProperties`

**API 版本：** `2017-05`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 该操作 设置 propagation enabled 属性 on a given set of objects and performs propagation. This will be done either in the same 会话 or a different 会话 depending on the dispatcher configuration. If dispatcher is configured and the SOA URL is set correctly in organization application then the request will be processed asynchronously. On the otherhand if disp…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_05.ProjectLevelSecurity.setPropagationEnabledProperties`

**请求（input）：**

```json
{
  "propagationDataInput": [
    {
      "assignOrAttachData": [
        {
          "selectedObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "selectedProjectsOrLicenses": [
            ""
          ],
          "eadParagraph": [
            ""
          ],
          "propertyName": ""
        }
      ],
      "removeOrDetachData": [
        {
          "selectedObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "selectedProjectsOrLicenses": [
            ""
          ],
          "eadParagraph": [
            ""
          ],
          "propertyName": ""
        }
      ],
      "propertyDataToSetAndPropagate": [
        {
          "selectedObjects": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "propertyName": "",
          "newPropertyValues": [
            ""
          ]
        }
      ],
      "configInfo": {
        "selectedTopLevelObject": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "variantRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "revisionRule": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "typeOption": "",
        "depth": ""
      },
      "reconstructConfigurationInfo": {
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
        "bomView": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "objectsForConfigure": [
          {
            "uid": "",
            "type": "",
            "className": ""
          }
        ],
        "revRuleConfigInfo": {
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
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `propagationDataInput` | Teamcenter::Soa::Core::_2017_05::ProjectLevelSecurity::PropagationDataInput[] | The list of PropagationDataInput structure. |

**响应（output）：**

```json
"void"
```

---

### 3.26 API 版本 2017-11

**Service：** LogicalObject  **操作数：** 1

#### 3.26.1 getLogicalObjects（2017-11）

**接口路径：** `Core-2017-11-LogicalObject/getLogicalObjects`

**API 版本：** `2017-11`  
**Service：** `LogicalObject`  
**Library：** `Core`

**说明：** 此操作 返回 the logical object instances for the input list of root object instances and logical object type names. 此操作 can also return classification objects [ A classification object is also called an ICO], if the root obejct or a member object is configured on the logical object type for retieving classification data. For such usecases it also return…

**Soa Inclusion：** `Teamcenter.Soa.Core._2017_11.LogicalObject.getLogicalObjects`

**请求（input）：**

```json
{
  "loInputs": [
    {
      "rootObjects": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "loTypeName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `loInputs` | Teamcenter::Soa::Core::_2017_11::LogicalObject::GetLogicalObjectInput[] | A list of the root object instances and logical object type names to retrieve the logical object instances. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "loOutputs": [
    {
      "logicalObjects": [
        {
          "root": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "logicalObjectInstances": [
            {
              "uid": "",
              "type": "",
              "className": ""
            }
          ],
          "memberClassificationObjects": [
            {
              "memberOrRootName": "",
              "icoIDs": [
                ""
              ]
            }
          ]
        }
      ]
    }
  ],
  "classificationAttributeDesc": {},
  "classificationObjectInfo": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Returned service data. |
| `loOutputs` | Teamcenter::Soa::Core::_2017_11::LogicalObject::GetLogicalObjectOutput[] | A list of the retrieved logical object output response corresponding to a  logical object input. |
| `classificationAttributeDesc` | Teamcenter::Soa::Core::_2017_11::LogicalObject::ClassificationAttributeDescMap | A map of classification objects and a list of references to their attribute descriptors. |
| `classificationObjectInfo` | Teamcenter::Soa::Core::_2017_11::LogicalObject::ClassificationObjectInfoMap | A map of the ICO ids and their class attribute info. |

---

### 3.27 API 版本 2018-06

**Service：** DataManagement、LogicalObject  **操作数：** 2

#### 3.27.1 createObjectsInBulkAndRelate（2018-06）

**接口路径：** `Core-2018-06-DataManagement/createObjectsInBulkAndRelate`

**API 版本：** `2018-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement）：创建对象s In Bulk And Relate。(1) This is a generic operation for creation of 业务对象 in bulk (i.e. in a set&ndash;based manner). All 业务对象 will be created or none, a failure for a single object will result in no 业务对象 being created. 此操作 will also create any secondary objects compounded with the main object being created. For example, please refer to the Create I…

**Soa Inclusion：** `Teamcenter.Soa.Core._2018_06.DataManagement.createObjectsInBulkAndRelate`

**请求（input）：**

```json
{
  "createInputs": [
    {
      "clientId": "",
      "createData": {
        "boName": "",
        "propertyNameValues": {},
        "compoundCreateInput": {}
      },
      "targetObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "pasteProp": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `createInputs` | Teamcenter::Soa::Core::_2018_06::DataManagement::CreateIn3[] | This is a list of <i>CreateIn3</i> objects in which each one represents the information required for the following:<br / |

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOut[] | Vector of output objects representing objects that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data including partial errors that are mapped to the client id from the input. Created objects are also added to |

---

#### 3.27.2 getLogicalObjects2（2018-06）

**接口路径：** `Core-2018-06-LogicalObject/getLogicalObjects2`

**API 版本：** `2018-06`  
**Service：** `LogicalObject`  
**Library：** `Core`

**说明：** 此操作 返回 the logical object instances for the input list of root object instances and logical object type names. 此操作 can also return classification objects (A classification object is also called an ICO), if the root obejct or a member object is configured on the logical object type for retieving classification data. For such use cases it also return…

**Soa Inclusion：** `Teamcenter.Soa.Core._2018_06.LogicalObject.getLogicalObjects2`

**请求（input）：**

```json
{
  "loInputs": [
    {
      "rootObjects": [
        {
          "root": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "clientID": ""
        }
      ],
      "loTypeName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `loInputs` | Teamcenter::Soa::Core::_2018_06::LogicalObject::GetLogicalObjectInput2[] | A list of the root object instances and logical object type names to retrieve the logical object instances. |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "loOutputs": [
    {
      "logicalObjectsOutput": [
        {
          "root": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "logicalObjectInstances": [
            {
              "loInstance": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "memberClassificationObjects": [
                {
                  "memberOrRootName": "",
                  "icoIDs": [
                    ""
                  ]
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "classificationObjectInfo": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Returned service data. |
| `loOutputs` | Teamcenter::Soa::Core::_2018_06::LogicalObject::GetLogicalObjectOutput2[] | A list of the retrieved logical object output response corresponding to a  logical object input. |
| `classificationObjectInfo` | Teamcenter::Soa::Core::_2018_06::LogicalObject::ClassificationObjectInfoMap2 | A map (string, classificationObjectInfo) of the <b>ICO</b> Ids and their class attribute info. |

---

### 3.28 API 版本 2018-11

**Service：** LogicalObject、ProjectLevelSecurity  **操作数：** 3

#### 3.28.1 getLogicalObjectsWithContext（2018-11）

**接口路径：** `Core-2018-11-LogicalObject/getLogicalObjectsWithContext`

**API 版本：** `2018-11`  
**Service：** `LogicalObject`  
**Library：** `Core`

**说明：** 此操作 返回 the logical object instances for the input list of client id and root object instance pairs, logical object type names and a map containing the included logical object ID, or member ID and configuration context UID. 此操作 can also return classification objects [A classification object is also called an ICO], if the root object or a member obje…

**Soa Inclusion：** `Teamcenter.Soa.Core._2018_11.LogicalObject.getLogicalObjectsWithContext`

**请求（input）：**

```json
{
  "loInputs": [
    {
      "rootInstances": [
        {
          "root": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "clientID": ""
        }
      ],
      "loTypeName": "",
      "loQueryNameValues": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `loInputs` | Teamcenter::Soa::Core::_2018_11::LogicalObject::GetLogicalObjectInput3[] | A list of the root object instances, logical object type names and a map containing the logical object ID and configurat |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "loOutputs": [
    {
      "logicalObjectsOutput": [
        {
          "root": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "logicalObjectInstances": [
            {
              "loInstance": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "memberClassificationObjects": [
                {
                  "memberOrRootName": "",
                  "icoIDs": [
                    ""
                  ]
                }
              ],
              "includedLOInstances": {}
            }
          ]
        }
      ]
    }
  ],
  "classificationObjectInfo": {}
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Returned service data. |
| `loOutputs` | Teamcenter::Soa::Core::_2018_11::LogicalObject::GetLogicalObjectOutput3[] | A list of the retrieved logical object output response corresponding to a  logical object input. |
| `classificationObjectInfo` | Teamcenter::Soa::Core::_2018_11::LogicalObject::ClassificationObjectInfoMap3 | A map(string, ClassificationObjectInfo)  of the ICO IDs and their classification object info. |

---

#### 3.28.2 changeOwningProgram（2018-11）

**接口路径：** `Core-2018-11-ProjectLevelSecurity/changeOwningProgram`

**API 版本：** `2018-11`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 changes the owning program of the given set of objects. Owning Program (owning_project attribute ) is changed to the new value passed in.

**Soa Inclusion：** `Teamcenter.Soa.Core._2018_11.ProjectLevelSecurity.changeOwningProgram`

**请求（input）：**

```json
{
  "chgOwnProgramInput": [
    {
      "owningProgram": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "inputObjects": [
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
| `chgOwnProgramInput` | Teamcenter::Soa::Core::_2018_11::ProjectLevelSecurity::ChangeOwningProgramInput2[] | The list of ChangeOwningProgramInput2 structure. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.28.3 getUserProjects2（2018-11）

**接口路径：** `Core-2018-11-ProjectLevelSecurity/getUserProjects2`

**API 版本：** `2018-11`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 the list of TC_Project objects for the user, group, and role based on the additional criteria like active projects only, user privileged projects only and programs only.

**Soa Inclusion：** `Teamcenter.Soa.Core._2018_11.ProjectLevelSecurity.getUserProjects2`

**请求（input）：**

```json
{
  "userInfoList": [
    {
      "tcUser": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tcGroup": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tcRole": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "activeProjectsOnly": "",
  "visibleProjectsOnly": "",
  "privilegedProjectsOnly": "",
  "programsOnly": "",
  "programsAndTheChildProjects": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `userInfoList` | Teamcenter::Soa::Core::_2018_11::ProjectLevelSecurity::UserGroupRoleInfo[] | A list of <b>UserGroupRoleInfo</b> objects to query the <b>TC_Project</b> objects. If the <b>Group</b> or <b>Role</b> is |
| `activeProjectsOnly` | bool | If true, query only the active <b>TC_Project</b> objects. |
| `visibleProjectsOnly` | bool | If true, query only the visible <b>TC_Project</b> objects. |
| `privilegedProjectsOnly` | bool | If true, query only the <b>TC_Project</b> objects that the user is a privileged member of. |
| `programsOnly` | bool | If true, query only the <b>TC_Project</b> objects that are using &quot;Program Level Security&quot;. When true, paramete |
| `programsAndTheChildProjects` | bool | If true, query the <b>TC_Project</b> objects that are using &quot;Program Level Security&quot;, and their child projects |

**响应（output）：**

```json
{
  "userProjectList": [
    {
      "userGroupRole": {
        "tcUser": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "tcGroup": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "tcRole": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "projects": [
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
| `userProjectList` | Teamcenter::Soa::Core::_2018_11::ProjectLevelSecurity::UserProjects[] | A list of <b>UserProjects</b> structure. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The ServiceData. |

---

### 3.29 API 版本 2019-06

**Service：** DataManagement、Session  **操作数：** 2

#### 3.29.1 unlinkAndDeleteObjects（2019-06）

**接口路径：** `Core-2019-06-DataManagement/unlinkAndDeleteObjects`

**API 版本：** `2019-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 unlinks the input objects from their corresponding container and then attempts to 删除 them. The input objects are related to the container as the reference or relation 属性 supplied as part of the input. 该操作 also takes a flag whether to unlink the objects from the container in case the deletion fails. After unlinking the objects from the inpu…

**Soa Inclusion：** `Teamcenter.Soa.Core._2019_06.DataManagement.unlinkAndDeleteObjects`

**请求（input）：**

```json
{
  "deleteInput": [
    {
      "container": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "objectsToDelete": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "property": "",
      "unlinkAlways": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `deleteInput` | Teamcenter::Soa::Core::_2019_06::DataManagement::DeleteIn[] | A list containing an input container and list of objects to be first unrelated from the container and then deleted. |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.29.2 licenseAdmin（2019-06）

**接口路径：** `Core-2019-06-Session/licenseAdmin`

**API 版本：** `2019-06`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 此操作 provides licensing related operations such as check-out and check-in of a license feature key.

**Soa Inclusion：** `Teamcenter.Soa.Core._2019_06.Session.licenseAdmin`

**请求（input）：**

```json
{
  "licAdminInput": [
    {
      "featureKey": "",
      "licensingAction": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `licAdminInput` | Teamcenter::Soa::Core::_2019_06::Session::LicAdminInput[] | A list of feature key and action pairs. This allows multiple license keys to be checked out in one service operation cal |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.30 API 版本 2020-01

**Service：** DataManagement、ProjectLevelSecurity  **操作数：** 9

#### 3.30.1 createIdDisplayRules（2020-01）

**接口路径：** `Core-2020-01-DataManagement/createIdDisplayRules`

**API 版本：** `2020-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 创建 the ID Display Rules (IdDispRule) with the input ID Context information. ID Display Rule contains the list of ID Contexts and their order. Based on the order of the ID Contexts defined, the system evaluates the display name of the Item and ItemRevision from their Alternate IDs. ID Context (IdContext), represents the context information under which the …

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.DataManagement.createIdDisplayRules`

**请求（input）：**

```json
{
  "idDispRuleCreIns": [
    {
      "ruleName": "",
      "idContexts": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "useDefault": "",
      "setCurrent": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `idDispRuleCreIns` | Teamcenter::Soa::Core::_2020_01::DataManagement::IDDispRuleCreateIn[] | A list of objects of type IdDispRuleCreateIn. The data on IdDispRuleCreateIn is used to create the <b>IdContextRule</b>  |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.30.2 getIdContexts（2020-01）

**接口路径：** `Core-2020-01-DataManagement/getIdContexts`

**API 版本：** `2020-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 fetches all instances of the ID Context objects (IdContext) from the Teamcenter database applicable for the input objects of type Item and ItemRevision based on defined ID Context Rules (IdContextRule) by the system administrators. 此操作 queries ID Context Rule objects and fetches the ID Context objects based on the input Item, ItemRevision or null. T…

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.DataManagement.getIdContexts`

**请求（input）：**

```json
{
  "inputObjs": [
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
| `inputObjs` | Teamcenter::WorkspaceObject[] | A list of objects of type <b>WorkspaceObject</b> or null for which the objects of type <b>IdContext</b> are fetched. |

**响应（output）：**

```json
{
  "idContextOuts": [
    {
      "inputObj": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "idContexts": [
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
| `idContextOuts` | Teamcenter::Soa::Core::_2020_01::DataManagement::IDContextOut[] | A list of IdContextOut structures which holds the list of <b>IdContext</b> objects and input object of type <b>Workspace |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any partial errors encountered during this operation are returned in the list of partial errors of the ServiceData. |

---

#### 3.30.3 getIdentifierTypes（2020-01）

**接口路径：** `Core-2020-01-DataManagement/getIdentifierTypes`

**API 版本：** `2020-01`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 fetches the applicable Identifier types for the input objects of type Item and/or ItemRevision along with the input IdContext object. System queries the ID Context Rules defined in Teamcenter database and retrives the Identifier types. Alternate and Alias IDs are defined in Teamcenter as instances of 业务对象 of type Identifier. ID Context, of business …

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.DataManagement.getIdentifierTypes`

**请求（input）：**

```json
{
  "identifierTypesIn": [
    {
      "inputItemOrRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "idContext": {
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
| `identifierTypesIn` | Teamcenter::Soa::Core::_2020_01::DataManagement::IdentifierTypesIn[] | A list of objects of type IdentifierTypesIn. The data on IdentifierTypesIn is used to query <b>Identifer</b> type based  |

**响应（output）：**

```json
{
  "identifiersOutput": [
    {
      "inputItemOrRev": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "identifierTypes": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "item": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "revisions": [
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
| `identifiersOutput` | Teamcenter::Soa::Core::_2020_01::DataManagement::IdentifiersOut[] | A list of IdentifiersOut structures which holds list of <b>Identifier</b> types, object of type <b>Item</b> and list of  |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Any partial errors encountered during this operation are returned in the list of partial errors of the ServiceData. |

---

#### 3.30.4 addOrRemoveProjectMembers（2020-01）

**接口路径：** `Core-2020-01-ProjectLevelSecurity/addOrRemoveProjectMembers`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 项目级安全（ProjectLevelSecurity） 服务操作 `addOrRemoveProjectMembers`。Adds or removes GroupMember objects or Group objects to/from the ProjectTeam of the given TC_Project.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.addOrRemoveProjectMembers`

**请求（input）：**

```json
{
  "inputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "gms": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "groups": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "groupRoles": [
        {
          "tcGroup": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "tcRole": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isRemovable": ""
        }
      ],
      "addOrRemove": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::AddOrRemoveProjectMemberInput[] | A list of <b>AddOrRemoveProjectMemberInput</b> structures which consists of the <b>TC_Project</b> object to add or remov |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.30.5 getFirstLevelProjectTeamStructure（2020-01）

**接口路径：** `Core-2020-01-ProjectLevelSecurity/getFirstLevelProjectTeamStructure`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作s 返回 the paginated output of the first level nodes of the ProjectTeam for the given TC_Project object.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.getFirstLevelProjectTeamStructure`

**请求（input）：**

```json
{
  "input": {
    "project": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "startIndex": "",
    "pageSize": "",
    "quickLoad": ""
  }
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `input` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::ProjectTeamPagedInput | The <b>TC_Project</b> and the pagination configuration to return <b>ProjectTeam</b> first level nodes and configuration  |

**响应（output）：**

```json
{
  "totalMemberCount": "",
  "endIndex": "",
  "groups": [
    {
      "tcGroup": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isRemovable": ""
    }
  ],
  "structuredGroupMembers": [
    {
      "tcGroup": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "tcRole": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "isRemovable": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `totalMemberCount` | int | The total number of the project members in the <b>ProjectTeam</b> of the given <b>TC_Project</b> object. |
| `endIndex` | int | The index of the last element returned for pagination. |
| `groups` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupNode[] | A list of <b>Group</b> objects that are in the project members of the input <b>TC_Project</b>. |
| `structuredGroupMembers` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupRoleNode[] | A list of structured <b>GroupRoleNode</b> which represents the first level node of the <b>GroupMember</b> objects in the |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data |

---

#### 3.30.6 getModifiableProjects（2020-01）

**接口路径：** `Core-2020-01-ProjectLevelSecurity/getModifiableProjects`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 the TC_Project objects that the login user can modify. The TC_Project objects in the response are based on the pagination input.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.getModifiableProjects`

**请求（input）：**

```json
{
  "startIndex": "",
  "pageSize": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `startIndex` | int | The start index for pagination. |
| `pageSize` | int | The size of a page. |

**响应（output）：**

```json
{
  "userProjects": [
    {
      "userGroupRole": {
        "tcUser": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "tcGroup": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "tcRole": {
          "uid": "",
          "type": "",
          "className": ""
        }
      },
      "totalProjectCount": "",
      "endIndex": "",
      "projects": [
        {
          "project": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "privilege": ""
        }
      ]
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `userProjects` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::UserProjectsAndPrivilege[] | The <b>Users</b> and their associated <b>TC_Projects</b>, along with the privilege status of each <b>User</b>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data. |

---

#### 3.30.7 getPrivilegeInProjects（2020-01）

**接口路径：** `Core-2020-01-ProjectLevelSecurity/getPrivilegeInProjects`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 此操作 返回 the privilege of the current user in each TC_Project object in the input.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.getPrivilegeInProjects`

**请求（input）：**

```json
{
  "projects": [
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
| `projects` | Teamcenter::TC_Project[] | A list of <b>TC_Project</b> objects to check the current user's privilege. |

**响应（output）：**

```json
{
  "projectPrivilege": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "privilege": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `projectPrivilege` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::ProjectAndPrivilege[] | A list of <b>TC_Project</b> objects and the privileges of the login user in them. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | The Service Data |

---

#### 3.30.8 getProjectTeamChildNodes（2020-01）

**接口路径：** `Core-2020-01-ProjectLevelSecurity/getProjectTeamChildNodes`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 该操作 返回 child nodes for the given Group node or a Role node in the ProjectTeam tree based on the given depth.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.getProjectTeamChildNodes`

**请求（input）：**

```json
{
  "project": {
    "uid": "",
    "type": "",
    "className": ""
  },
  "node": {
    "tcGroup": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "tcRole": {
      "uid": "",
      "type": "",
      "className": ""
    },
    "isRemovable": ""
  },
  "depth": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `project` | Teamcenter::TC_Project | The <b>TC_Project</b> object which associated with the <b>ProjectTeam</b> to load child nodes. |
| `node` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupRoleNode | The <b>Group</b> or <b>GroupRole</b> node to load the children.<br />If the <i>tcRole</i> field is NULL or empty, then l |
| `depth` | int | The depth of the tree to load children. |

**响应（output）：**

```json
{
  "childGroups": [
    {
      "groupNode": {
        "tcGroup": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isRemovable": ""
      },
      "childGroups": [
        {
          "tcGroup": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isRemovable": ""
        }
      ],
      "childRoles": [
        {
          "groupRole": {
            "tcGroup": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "tcRole": {
              "uid": "",
              "type": "",
              "className": ""
            },
            "isRemovable": ""
          },
          "groupmemberList": [
            {
              "groupmember": {
                "uid": "",
                "type": "",
                "className": ""
              },
              "privilege": "",
              "isRemovable": ""
            }
          ]
        }
      ]
    }
  ],
  "childRoles": [
    {
      "groupRole": {
        "tcGroup": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "tcRole": {
          "uid": "",
          "type": "",
          "className": ""
        },
        "isRemovable": ""
      },
      "groupmemberList": [
        {
          "groupmember": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "privilege": "",
          "isRemovable": ""
        }
      ]
    }
  ],
  "childGroupMembers": [
    {
      "groupmember": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "privilege": "",
      "isRemovable": ""
    }
  ],
  "childGroupMap": {},
  "sd": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `childGroups` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupNodeWithChildren[] | The child <b>Groups</b>. |
| `childRoles` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupRoleNodeWithChildren[] | The child <b>Roles</b>. |
| `childGroupMembers` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupMemberPrivilege[] | The child <b>GroupMembers</b>. |
| `childGroupMap` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::GroupChildGroup | Map the <b>Group</b> objects to their child <b>Groups</b>. |
| `sd` | Teamcenter::Soa::Server::ServiceData | The Service Data. |

---

#### 3.30.9 setUserPrivilege（2020-01）

**接口路径：** `Core-2020-01-ProjectLevelSecurity/setUserPrivilege`

**API 版本：** `2020-01`  
**Service：** `ProjectLevelSecurity`  
**Library：** `Core`

**说明：** 项目级安全（ProjectLevelSecurity）：设置User Privilege。Set the privilege of the given User objects in ProjectTeam of the given TC_Project.

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_01.ProjectLevelSecurity.setUserPrivilege`

**请求（input）：**

```json
{
  "inputs": [
    {
      "project": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "users": [
        {
          "uid": "",
          "type": "",
          "className": ""
        }
      ],
      "groupNode": [
        {
          "tcGroup": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isRemovable": ""
        }
      ],
      "groupRoleNode": [
        {
          "tcGroup": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "tcRole": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "isRemovable": ""
        }
      ],
      "privilegeStatus": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2020_01::ProjectLevelSecurity::SetPrivilegeForUserInput[] | A list of <b>SetPrivilegeForUserInput</b> structures. The structure holds the <b>TC_Project</b>, a list of <b>User</b> o |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.31 API 版本 2020-04

**Service：** DataManagement  **操作数：** 1

#### 3.31.1 generateContextSpecificIDs2（2020-04）

**接口路径：** `Core-2020-04-DataManagement/generateContextSpecificIDs2`

**API 版本：** `2020-04`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 数据管理（DataManagement） 服务操作 `generateContextSpecificIDs2`。Generates the range of unique IDs for input context names. The number of IDs generated for each context name depends on the input. If for a given context name, the ID has been reset using Teamcenter service resetContextID, then this service generates IDs for that context from the beginning. ID generation will also reset when the maximum limit is met. This limit is maximum nu…

**Soa Inclusion：** `Teamcenter.Soa.Core._2020_04.DataManagement.generateContextSpecificIDs2`

**请求（input）：**

```json
{
  "generateContextIDsIn": [
    {
      "clientID": "",
      "contextName": "",
      "contextTypeName": "",
      "contextPropName": "",
      "validateIDs": "",
      "numberOfIDs": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `generateContextIDsIn` | Teamcenter::Soa::Core::_2020_04::DataManagement::GenerateContextIDsInput2[] | A list of GenerateContextIDsInput2 which contains the context name, type, property name, validation flag, and number of  |

**响应（output）：**

```json
{
  "serviceData": "IServiceData",
  "generatedContextIDValues": [
    {
      "contextName": "",
      "generatedIDs": [
        ""
      ]
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Partial Errors are returned in the ServiceData when service generateContextSpecificIDs fails to generate IDs of any of t |
| `generatedContextIDValues` | Teamcenter::Soa::Core::_2016_05::DataManagement::GeneratedContextIDs[] | A list of GeneratedContextIDs, which contains each of the context names and IDs generated for it by service generateCont |

---

### 3.32 API 版本 2021-06

**Service：** DataManagement  **操作数：** 2

#### 3.32.1 addNamedReferenceToDatasets（2021-06）

**接口路径：** `Core-2021-06-DataManagement/addNamedReferenceToDatasets`

**API 版本：** `2021-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 adds a list of named references to the input 数据集. Operation adds only existing named reference objects and does not create new named reference. 此操作 can optionally create a new version of an input 数据集.

**Soa Inclusion：** `Teamcenter.Soa.Core._2021_06.DataManagement.addNamedReferenceToDatasets`

**请求（input）：**

```json
{
  "addNamedReferenceIn": [
    {
      "clientID": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "nrInfo": [
        {
          "clientId": "",
          "object": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "namedReferenceName": "",
          "referenceType": ""
        }
      ],
      "createNewDatasetVersion": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `addNamedReferenceIn` | Teamcenter::Soa::Core::_2021_06::DataManagement::AddNamedReferenceToDatasetInfo[] | A list of AddNamedReferenceToDatasetInfo which contains <b>Dataset</b> objects and the named references to be added to t |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.32.2 removeNamedReferenceFromDataset2（2021-06）

**接口路径：** `Core-2021-06-DataManagement/removeNamedReferenceFromDataset2`

**API 版本：** `2021-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 removes the specified named references from a 数据集.If the NamedReferenceInfo.targetObject input is specified and matched then only that named reference is removed from the 数据集. The NamedReferenceInfo.targetObject input is not matched with any named references in the 数据集 instance then no named reference is removed. If the NamedReferenceInfo.deleteTar…

**Soa Inclusion：** `Teamcenter.Soa.Core._2021_06.DataManagement.removeNamedReferenceFromDataset2`

**请求（input）：**

```json
{
  "removeNamedReferenceIn": [
    {
      "clientID": "",
      "dataset": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "nrInfo": [
        {
          "clientId": "",
          "type": "",
          "targetObject": {
            "uid": "",
            "type": "",
            "className": ""
          },
          "deleteTarget": ""
        }
      ],
      "createNewDatasetVersion": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `removeNamedReferenceIn` | Teamcenter::Soa::Core::_2021_06::DataManagement::RemoveNamedReferenceFromDataset[] | A list of RemoveNamedReferenceFromDataset which contains <b>Dataset</b> objects and the named references to be removed f |

**响应（output）：**

```json
"IServiceData"
```

---

### 3.33 API 版本 2021-12

**Service：** LOV、Session  **操作数：** 2

#### 3.33.1 validatePropertyValuesForLOVInBulk（2021-12）

**接口路径：** `Core-2021-12-LOV/validatePropertyValuesForLOVInBulk`

**API 版本：** `2021-12`  
**Service：** `LOV`  
**Library：** `Core`

**说明：** 此操作 validates the input 属性 against the LOV defination. The validate属性ValuesForLOVInBulk operation is used to validate input 属性 values before invoking service operations like creating objects, save as objects or revise objects etc. All of the input 属性 names and their values should be included in 属性ValuesMap.

**Soa Inclusion：** `Teamcenter.Soa.Core._2021_12.LOV.validatePropertyValuesForLOVInBulk`

**请求（input）：**

```json
{
  "inputs": [
    {
      "clientID": "",
      "owningObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "boName": "",
      "operationName": "",
      "propNames": [
        ""
      ],
      "propValues": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `inputs` | Teamcenter::Soa::Core::_2021_12::LOV::ValidatePropertyValuesForLOVInBulkInputData[] | A list of <i>ValidatePropertyValuesForLOVInBulkInputData</i> objects containing LOV property values to be evaluated. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientID": "",
      "validateLOVPropertyOutput": [
        {
          "propName": "",
          "propHasValidValues": "",
          "dependentPropNames": [
            ""
          ],
          "updatedPropValues": {
            "uid": "",
            "propInternalValues": {},
            "propInternalValueTypes": {},
            "propDisplayValues": {},
            "childRows": []
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
| `output` | Teamcenter::Soa::Core::_2021_12::LOV::ValidatePropertyValuesForLOVInBulkOutput[] | A list containing the clientID and list of <i>ValidatePropertyValuesForLOVInBulkOutput</i>. For each input, one <i>Valid |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data object associated with the operation. |

---

#### 3.33.2 addObjectPropertyPolicies（2021-12）

**接口路径：** `Core-2021-12-Session/addObjectPropertyPolicies`

**API 版本：** `2021-12`  
**Service：** `Session`  
**Library：** `Core`

**说明：** Adds multiple object 属性 policies to the 会话. Once these policies are added to the 会话, the 客户端应用 can quickly switch between policies using the appropriate methods on the Object属性PolicyManager class in the SOA client framework. The business logic of a service operation determines what 业务对象 are returned, while the object 属性 po…

**Soa Inclusion：** `Teamcenter.Soa.Core._2021_12.Session.addObjectPropertyPolicies`

**请求（input）：**

```json
{
  "clientPolicies": [
    "IObjectPropertyPolicy"
  ],
  "namedPolicies": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `clientPolicies` | Teamcenter::Soa::Common::ObjectPropertyPolicy[] | A list of client defined object property policies. |
| `namedPolicies` | std::string[] | A list of policy files defined on the Teamcenter server volume at<font face="courier" height="10"> $TC_Data/soa/policies |

**响应（output）：**

```json
{
  "policyIDs": [
    ""
  ],
  "partialErrors": "IPartialErrors"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `policyIDs` | std::string[] | A list of policy IDs. The initial size and order of this list will match the input list of <font face="courier" height=" |
| `partialErrors` | Teamcenter::Soa::Server::PartialErrors | Partial errors or warnings. |

---

### 3.34 API 版本 2022-12

**Service：** Session  **操作数：** 1

#### 3.34.1 tcServerSleep（2022-12）

**接口路径：** `Core-2022-12-Session/tcServerSleep`

**API 版本：** `2022-12`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 会话（Session） 服务操作 `tcServerSleep`。A no-op serivce operation that puts the TcServer in a wait/sleep for the requested amount of time before returning. This can be used to simulate long running service requests.

**Soa Inclusion：** `Teamcenter.Soa.Core._2022_12.Session.tcServerSleep`

**请求（input）：**

```json
{
  "seconds": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `seconds` | int | The number of seconds to sleep. |

**响应（output）：**

```json
"String"
```

---

### 3.35 API 版本 2023-06

**Service：** DataManagement  **操作数：** 1

#### 3.35.1 createObjects（2023-06）

**接口路径：** `Core-2023-06-DataManagement/createObjects`

**API 版本：** `2023-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 按类型批量创建业务对象（通用创建接口）。

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_06.DataManagement.createObjects`

**请求（input）：**

```json
{
  "createInputs": [
    {
      "clientId": "",
      "data": {
        "boName": "",
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
  ],
  "runInBackground": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `createInputs` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateIn[] | A list of CreateIn objects each one of which represents the CreateInput information used to create an object. Each Creat |
| `runInBackground` | bool | If true, the operation is performed in background mode in a separate asynchronous server session; otherwise, perform the |

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

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2008_06::DataManagement::CreateOut[] | Vector of output objects representing objects that were created. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data including partial errors that are mapped to the client id from the input. Created objects are also added to |

---

### 3.36 API 版本 2023-12

**Service：** DataManagement、Session  **操作数：** 5

#### 3.36.1 changeOwner2（2023-12）

**接口路径：** `Core-2023-12-DataManagement/changeOwner2`

**API 版本：** `2023-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 can be used to change the ownership on a given 业务对象 to the given user and group. Owning user attribute on the 业务对象 will be changed to the given user and owning group attribute is changed to the given group. The user needs CHANGE_OWNER privilege and WRITE privilege on the 业务对象 to be able to change its ownership. If user does not…

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_12.DataManagement.changeOwner2`

**请求（input）：**

```json
{
  "objectsAndOwnersInput": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "owner": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "group": {
        "uid": "",
        "type": "",
        "className": ""
      }
    }
  ],
  "relatedObjectsIncluded": ""
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `objectsAndOwnersInput` | Teamcenter::Soa::Core::_2006_03::DataManagement::ObjectOwner[] | The set of objects to transfer ownership of and user objects to which ownership is to be transferred. |
| `relatedObjectsIncluded` | bool | If &ldquo;true&rdquo;, only the input objects are considered for change ownership. If &ldquo;false&rdquo;, server traver |

**响应（output）：**

```json
"IServiceData"
```

---

#### 3.36.2 generateNextValuesForProperties2（2023-12）

**接口路径：** `Core-2023-12-DataManagement/generateNextValuesForProperties2`

**API 版本：** `2023-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 generates values for specific 属性 of an object or objects during the Create/Revise/SaveAs action. The values are determined based on user exits, ID generation rules, naming rules and revision naming rules that have been configured for these 属性. When both customer user exits and naming rules are configured for the same 属性, the customer user…

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_12.DataManagement.generateNextValuesForProperties2`

**请求（input）：**

```json
{
  "propertyNextValueInputs": [
    {
      "clientID": "",
      "operationType": "",
      "businessObjectTypeName": "",
      "boReference": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyInputList": [
        {
          "propertyName": "",
          "pattern": "",
          "context": [
            ""
          ],
          "quantity": ""
        }
      ],
      "propertyValuesMap": {},
      "additionalInputMap": {},
      "compoundObjectInput": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `propertyNextValueInputs` | Teamcenter::Soa::Core::_2023_12::DataManagement::PropertyNextValueInput[] | A list of PropertyNextValueInput objects which actually holds essential information like clientId, operation type, busin |

**响应（output）：**

```json
{
  "data": "IServiceData",
  "generatedValues": [
    {
      "clientId": "",
      "generatedValues": {},
      "generatedValuesOfSecondaryObjects": {}
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `data` | Teamcenter::Soa::Server::ServiceData | The Service Data with partial errors for each PropertyNextValueInput and identified by its clientId. |
| `generatedValues` | Teamcenter::Soa::Core::_2023_12::DataManagement::PropertyNextValueOutput[] | A list of PropertyNextValueOutput one for each entry in PropertyNextValueInput input list and identified by its clientId |

---

#### 3.36.3 getNRPatterns（2023-12）

**接口路径：** `Core-2023-12-DataManagement/getNRPatterns`

**API 版本：** `2023-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 返回 the list of Patterns with counters and without counters along with preferred patterns and conditions for the Naming Rule attached to the 属性 of an object Type. The Type name and the 属性 name are passed in the input structure. The input for 此操作 contains a list of this structure. The return structure contains patterns, preferredPatte…

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_12.DataManagement.getNRPatterns`

**请求（input）：**

```json
{
  "attachInfos": [
    {
      "typeName": "",
      "propName": ""
    }
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `attachInfos` | Teamcenter::Soa::Core::_2008_06::DataManagement::NRAttachInfo[] | A list of  type  and property names. |

**响应（output）：**

```json
{
  "patterns": [
    {
      "patternStrings": [
        ""
      ]
    }
  ],
  "preferredPattern": [
    ""
  ],
  "condition": [
    ""
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `patterns` | Teamcenter::Soa::Core::_2023_12::DataManagement::Patterns[] | A list of naming rule patterns. |
| `preferredPattern` | std::string[] | A list of preferred naming rule patterns. |
| `condition` | std::string[] | A list of conditions in naming rule attachments. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Standard ServiceData structure. It contains partial errors and failures along with the clientIds. |

---

#### 3.36.4 getRelatedObjects（2023-12）

**接口路径：** `Core-2023-12-DataManagement/getRelatedObjects`

**API 版本：** `2023-12`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 获取 the related objects of input BusinessObject objects as determined by the preference: &lt;TypeName&gt;_defaultChild属性.

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_12.DataManagement.getRelatedObjects`

**请求（input）：**

```json
{
  "inputObjects": [
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
| `inputObjects` | Teamcenter::BusinessObject[] | A list of objects whose related objects are needed. |

**响应（output）：**

```json
{
  "parentChildMap": {},
  "treeNodes": [
    {
      "identifier": "",
      "displayName": "",
      "parentIdentifier": "",
      "isPreselected": "",
      "isSelectable": "",
      "relationType": ""
    }
  ],
  "serviceData": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `parentChildMap` | Teamcenter::Soa::Core::_2023_12::DataManagement::ParentChildMap | A map (string, string) which holds parent node's UIDs vs children node's UIDs. Parent node UIDs are the ones sent in the |
| `treeNodes` | Teamcenter::Soa::Core::_2023_12::DataManagement::TreeNode[] | A list of information about individual child tree nodes. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service Data for the operation. |

---

#### 3.36.5 logout（2023-12）

**接口路径：** `Core-2023-12-Session/logout`

**API 版本：** `2023-12`  
**Service：** `Session`  
**Library：** `Core`

**说明：** 注销当前 Teamcenter 会话并释放相关资源。

**Soa Inclusion：** `Teamcenter.Soa.Core._2023_12.Session.logout`

**请求（input）：**

```json
{
  "clientIDs": [
    ""
  ]
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `clientIDs` | std::string[] | The list of Client IDs. |

**响应（output）：**

```json
"bool"
```

---

### 3.37 API 版本 2024-06

**Service：** DataManagement  **操作数：** 1

#### 3.37.1 queryForFileExistence（2024-06）

**接口路径：** `Core-2024-06-DataManagement/queryForFileExistence`

**API 版本：** `2024-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** 此操作 takes a source object, a list of files, and relation types as input. It filters 数据集 objects associated with the source object based on the specified relations. 该操作 then searches these filtered 数据集 objects to determine if any files from the input list exist within them. If one or more files are found, the corresponding 数据集 objects are retu…

**Soa Inclusion：** `Teamcenter.Soa.Core._2024_06.DataManagement.queryForFileExistence`

**请求（input）：**

```json
{
  "input": [
    {
      "clientID": "",
      "fileNames": [
        ""
      ],
      "relationNames": [
        ""
      ],
      "parentObject": {
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
| `input` | Teamcenter::Soa::Core::_2024_06::DataManagement::DatasetsForFileRelationInput[] | A list of <i>DatasetsForFileRelationInput</i> objects containing references to the input data. |

**响应（output）：**

```json
{
  "output": [
    {
      "clientId": "",
      "datasetsForFile": [
        {
          "fileName": "",
          "dataset": {
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
| `output` | Teamcenter::Soa::Core::_2024_06::DataManagement::DatasetsForFileOutput[] | A list of <i>DatasetsForFileOutput</i>. |
| `serviceData` | Teamcenter::Soa::Server::ServiceData | Service data object associated with the operation. |

---

### 3.38 API 版本 2025-06

**Service：** DataManagement  **操作数：** 1

#### 3.38.1 getLocalizedProperties3（2025-06）

**接口路径：** `Core-2025-06-DataManagement/getLocalizedProperties3`

**API 版本：** `2025-06`  
**Service：** `DataManagement`  
**Library：** `Core`

**说明：** The getLocalized属性3 operation enables retrieval of 属性 values in any supported locale on the Teamcenter server. For string-type 属性 that support localization, it provides translated values for specified locales. 此操作 also 返回 the internal status of localized values and read-access status for the 属性. If the user lacks read access, the…

**Soa Inclusion：** `Teamcenter.Soa.Core._2025_06.DataManagement.getLocalizedProperties3`

**请求（input）：**

```json
{
  "propertyInfo": [
    {
      "object": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propsToget": [
        {
          "name": "",
          "locales": [
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
| `propertyInfo` | Teamcenter::Soa::Core::_2010_04::DataManagement::PropertyInfo[] | A list of <font face="courier" height="10">propertyInfo</font> objects which actually holds desired business objects, pr |

**响应（output）：**

```json
{
  "output": [
    {
      "businessObject": {
        "uid": "",
        "type": "",
        "className": ""
      },
      "propertyValues": [
        {
          "name": "",
          "values": [
            ""
          ],
          "locale": "",
          "seqNum": "",
          "status": [
            ""
          ],
          "internalStatus": [
            ""
          ],
          "statusDesc": [
            ""
          ],
          "master": "",
          "hasReadAccess": ""
        }
      ]
    }
  ],
  "data": "IServiceData"
}
```

| 字段 | 类型 | 说明（原文） |
|------|------|--------------|
| `output` | Teamcenter::Soa::Core::_2025_06::DataManagement::LocalizedPropertyValuesInfo3[] | A list of  <font face="courier" height="10">LocalizedPropertyValuesInfo3</font> to store the localized property values i |
| `data` | Teamcenter::Soa::Server::ServiceData | The <font face="courier" height="10">Service Data</font> with partial errors for each <font face="courier" height="10">P |

---

---

## 4. 附录

### Service 统计

| Service | 操作数 | API 版本数 |
|---------|--------|------------|
| DataManagement | 123 | 30 |
| DigitalSignature | 3 | 1 |
| DispatcherManagement | 1 | 1 |
| Envelope | 1 | 1 |
| FileManagement | 8 | 4 |
| LOV | 6 | 4 |
| LanguageInformation | 2 | 1 |
| LogicalObject | 3 | 3 |
| ManagedRelations | 4 | 2 |
| OperationDescriptor | 2 | 2 |
| ProjectLevelSecurity | 23 | 9 |
| PropDescriptor | 3 | 3 |
| Reservation | 9 | 4 |
| Session | 42 | 15 |
| StructureManagement | 4 | 1 |

### 典型流程

**登录与会话：** `login` → `getTCSessionInfo` → `getFavorites`

**查询属性：** `getProperties`

**创建 Item 与数据集：** `createItems` → `createDatasets` → FMS 上传 → `commitDatasetFiles` → `createRelations`

**创建文件夹：** `createFolders`

### 重新生成

```bash
node generate-core-doc.js
```
