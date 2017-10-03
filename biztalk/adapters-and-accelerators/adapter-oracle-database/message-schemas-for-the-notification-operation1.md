---
title: "通知 Operation1 的消息架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f98d76d0-6084-4de7-b6ff-124202ca92ab
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd0d7513a0a439d34d5bfb4722fec2b9025e676b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-notification-operation"></a>通知操作的消息架构
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]面，用于接收从 Oracle 数据库的数据库更改通知的通知操作。  
  
 通过设置绑定属性配置通知操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 有关与通知相关的绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。 你设置**NotificationStatement**绑定属性来指定 SELECT 语句，以查询通知。  
  
## <a name="message-structure-for-the-notification-operation"></a>通知操作的消息结构  
 下表显示通知操作的 XML 消息结构。  
  
|运算|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|通知|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|这是由 Oracle 数据库发送到适配器客户端的入站的消息。 中会显示消息：<br /><br /> -`<Info>`标记指示通知的原因。 例如，在该标记中的"插入"值指示，已在一个或多个通知语句中引用的表中插入数据。<br /><br /> -`<Source>`标记指示通知的源。 例如，此标记中的"数据"值指示的数据中引用的对象的更改。 同样，此标记中的"对象"值指示引用的对象中的更改。<br /><br /> -`<Type>`标记指示的数据更改的类型。 例如，"更新"值中`<Type>`标记指示已更新查询的结果。|  
  
## <a name="message-action-for-the-notification-operation"></a>通知操作的消息操作  
 通知操作的消息操作是"http://Microsoft.LobServices.OracleDB/2007/03/Notification"。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Oracle 数据库的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)