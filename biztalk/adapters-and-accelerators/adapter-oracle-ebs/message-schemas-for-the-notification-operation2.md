---
title: "通知 Operation2 的消息架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dddab2ef-94db-46c8-95c1-57517681e8dd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8c004e83ada00b41013c2a22c5e48f29bb39ffd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-notification-operation"></a>通知操作的消息架构
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]面，用于接收从 Oracle E-business Suite 中的基础数据库的数据库更改通知的通知操作。  
  
 通过设置绑定属性配置通知操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关与通知相关的绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 你设置**NotificationStatement**绑定属性来指定 SELECT 语句，以查询通知。  
  
## <a name="message-structure-for-the-notification-operation"></a>通知操作的消息结构  
 下表显示通知操作的 XML 消息结构。  
  
|运算|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|通知|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|这是由 Oracle E-business Suite 发送到适配器客户端的入站的消息。 中会显示消息：<br /><br /> -`<Info>`标记指示通知的原因。 例如，在该标记中的"插入"值指示，已在一个或多个通知语句中引用的表中插入数据。<br /><br /> -`<Source>`标记指示通知的源。 例如，此标记中的"数据"值指示的数据中引用的对象的更改。 同样，此标记中的"对象"值指示引用的对象中的更改。<br /><br /> -`<Type>`标记指示的数据更改的类型。 例如，"更新"值中`<Type>`标记指示已更新查询的结果。|  
  
## <a name="message-action-for-the-notification-operation"></a>通知操作的消息操作  
 通知操作的消息操作是"通知"。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)