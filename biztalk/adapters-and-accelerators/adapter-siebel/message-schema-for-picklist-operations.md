---
title: 选择列表操作的消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- picklist operations, message schemas for
- picklist operations, message actions
- picklist operations, message
ms.assetid: c0b62a8c-5a68-47ea-8676-1580601b5ec9
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5748a293c8f9dc4e4059ebdecda9527bb0bb63ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371408"
---
# <a name="message-schema-for-picklist-operations"></a>选择列表的消息架构
选择列表是在业务组件中的特殊字段类型。 它们表示的用户可能会从其选取的分配单个值的值的集合。 选择列表都是不同的类型。 有关选择列表及其类型的详细信息，请参阅 Siebel 文档。  
  
 一种选择列表类型，静态绑定选择列表，为枚举选择列表适配器会显示在设计时由适配器生成的元数据中的类型。 这包含一组静态的值必须在运行时指定的选择列表类型。  同时为静态绑定选择列表中指定一个值，必须始终指定一个值，属于集。  
  
 下面的示例显示了静态绑定选择列表类型的架构：  
  
```  
<element name="[FIELD_NAME]RequiredPickListType" nillable="true" type="ns1:[FIELD_NAME]RequiredPickListType" />  
<simpleType name="[FIELD_NAME]RequiredPickListType">  
<restriction base="string">  
  <enumeration value="value1" />  
  <enumeration value="value2" />  
  …  
</restriction>  
</simpleType>  
```  
  
 [字段名] = 业务组件中的选择列表字段名称  
  
 下面的内容表示静态绑定选择列表类型的代理体验：  
  
```  
[BC]InsertRecord[] insertRecs = new [BC]InsertRecord[1];  
insertRecs[0] = new [BC]InsertRecord();  
insertRecs[0].[BC_STATIC_PICKLIST_FIELD] = [BC_PICKLIST_FIELD_NAME]OptionalPickListType.value1;  
```  
  
 [BC_STATIC_PICKLIST_FIELD] = 适合在 BC 中静态绑定选择列表字段  
  
## <a name="see-also"></a>请参阅  
 [消息和用于 Siebel eBusiness 应用程序的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)