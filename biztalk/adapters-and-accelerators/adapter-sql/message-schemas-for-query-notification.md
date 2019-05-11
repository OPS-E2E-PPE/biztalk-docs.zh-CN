---
title: 使用 SQL 适配器在 BizTalk 中的查询通知的消息架构 |Microsoft Docs
description: 使用 SQL 适配器接收来自 BizTalk 中的 SQL Server 数据库的查询通知
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5183655-64d4-4767-a923-0a575e3708cd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be33d8990e5577fbb52cd1d294dff4c5257c3bdf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368435"
---
# <a name="message-schemas-for-query-notification"></a>查询通知的消息架构
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]用于从 SQL Server 数据库中接收查询通知的通知操作的图面。  
  
 通过设置绑定属性来配置通知操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 有关与通知相关的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 您设置**NotificationStatement**绑定属性来指定 SQL 语句 (SELECT 或 EXEC\<存储过程\>) 的查询通知。 此查询的结果集作为强类型化数据返回到你的代码中的通知操作。  
  
## <a name="message-structure-for-the-notification-operation"></a>通知操作的消息结构  
 下表显示了通知操作的 XML 消息结构。  

**操作**: `Notification`

**XML 消息**:  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification">
    <Info>Value</Info>
    <Source>Value</Source>
    <Type>Value</Type>
 </Notification>
```

**说明**：这是由 SQL Server 发送到适配器客户端的入站的消息。 在消息：

- `<Info>`标记指示通知的原因。 例如，此标记中的"插入"值指示表明已在一个或多个通知语句中引用的表中插入数据。
- `<Source>`标记指示通知的源。 例如，此标记中的"数据"值指示被引用对象中的数据的更改。 同样，此标记中的"对象"值指示被引用对象的更改。
- `<Type>`标记表示的数据更改的类型。 查询通知消息分为两种类型： 更改和订阅。 一个"更改"中的值`<Type>`标记指示，查询的结果已更改，而中的"订阅"值`<Type>`标记表示的订阅请求失败。

  
## <a name="message-action-for-the-notification-operation"></a>通知操作的消息操作  
 通知操作的消息操作是"通知"。  
  