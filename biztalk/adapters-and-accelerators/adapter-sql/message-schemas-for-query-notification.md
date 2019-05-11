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
# <a name="message-schemas-for-query-notification"></a><span data-ttu-id="00b05-103">查询通知的消息架构</span><span class="sxs-lookup"><span data-stu-id="00b05-103">Message Schemas for Query Notification</span></span>
<span data-ttu-id="00b05-104">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]用于从 SQL Server 数据库中接收查询通知的通知操作的图面。</span><span class="sxs-lookup"><span data-stu-id="00b05-104">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] surfaces the Notification operation to receive query notifications from the SQL Server database.</span></span>  
  
 <span data-ttu-id="00b05-105">通过设置绑定属性来配置通知操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00b05-105">You configure the Notification operation by setting binding properties in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="00b05-106">有关与通知相关的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="00b05-106">For more information about the Notification-related binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="00b05-107">您设置**NotificationStatement**绑定属性来指定 SQL 语句 (SELECT 或 EXEC\<存储过程\>) 的查询通知。</span><span class="sxs-lookup"><span data-stu-id="00b05-107">You set the **NotificationStatement** binding property to specify a SQL statement (SELECT or EXEC \<stored procedure\>) for the query notification.</span></span> <span data-ttu-id="00b05-108">此查询的结果集作为强类型化数据返回到你的代码中的通知操作。</span><span class="sxs-lookup"><span data-stu-id="00b05-108">The result set of this query is returned as strongly-typed data to your code in the Notification operation.</span></span>  
  
## <a name="message-structure-for-the-notification-operation"></a><span data-ttu-id="00b05-109">通知操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="00b05-109">Message Structure for the Notification operation</span></span>  
 <span data-ttu-id="00b05-110">下表显示了通知操作的 XML 消息结构。</span><span class="sxs-lookup"><span data-stu-id="00b05-110">The following table shows the XML message structure for the Notification operation.</span></span>  

<span data-ttu-id="00b05-111">**操作**: `Notification`</span><span class="sxs-lookup"><span data-stu-id="00b05-111">**Operation**: `Notification`</span></span>

<span data-ttu-id="00b05-112">**XML 消息**:</span><span class="sxs-lookup"><span data-stu-id="00b05-112">**XML message**:</span></span>  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification">
    <Info>Value</Info>
    <Source>Value</Source>
    <Type>Value</Type>
 </Notification>
```

<span data-ttu-id="00b05-113">**说明**：这是由 SQL Server 发送到适配器客户端的入站的消息。</span><span class="sxs-lookup"><span data-stu-id="00b05-113">**Description**: This is the inbound message that is sent by the SQL Server to the adapter clients.</span></span> <span data-ttu-id="00b05-114">在消息：</span><span class="sxs-lookup"><span data-stu-id="00b05-114">In the message:</span></span>

- <span data-ttu-id="00b05-115">`<Info>`标记指示通知的原因。</span><span class="sxs-lookup"><span data-stu-id="00b05-115">The `<Info>` tag indicates the reason for the notification.</span></span> <span data-ttu-id="00b05-116">例如，此标记中的"插入"值指示表明已在一个或多个通知语句中引用的表中插入数据。</span><span class="sxs-lookup"><span data-stu-id="00b05-116">For example, an “insert” value in this tag indicates that data has been inserted in one or more of the tables referenced in the notification statement.</span></span>
- <span data-ttu-id="00b05-117">`<Source>`标记指示通知的源。</span><span class="sxs-lookup"><span data-stu-id="00b05-117">The `<Source>` tag indicates the source for the notification.</span></span> <span data-ttu-id="00b05-118">例如，此标记中的"数据"值指示被引用对象中的数据的更改。</span><span class="sxs-lookup"><span data-stu-id="00b05-118">For example, a “data” value in this tag indicates a change in the data in a referenced object.</span></span> <span data-ttu-id="00b05-119">同样，此标记中的"对象"值指示被引用对象的更改。</span><span class="sxs-lookup"><span data-stu-id="00b05-119">Similarly, an “object” value in this tag indicates a change in a referenced object.</span></span>
- <span data-ttu-id="00b05-120">`<Type>`标记表示的数据更改的类型。</span><span class="sxs-lookup"><span data-stu-id="00b05-120">The `<Type>` tag indicates the type of data change.</span></span> <span data-ttu-id="00b05-121">查询通知消息分为两种类型： 更改和订阅。</span><span class="sxs-lookup"><span data-stu-id="00b05-121">Query notification messages are of two types: change and subscribe.</span></span> <span data-ttu-id="00b05-122">一个"更改"中的值`<Type>`标记指示，查询的结果已更改，而中的"订阅"值`<Type>`标记表示的订阅请求失败。</span><span class="sxs-lookup"><span data-stu-id="00b05-122">A “change” value in the `<Type>` tag indicates that the results of the query have changed, whereas a “subscribe” value in the `<Type>` tag indicates that a subscription request failed.</span></span>

  
## <a name="message-action-for-the-notification-operation"></a><span data-ttu-id="00b05-123">通知操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="00b05-123">Message Action for the Notification Operation</span></span>  
 <span data-ttu-id="00b05-124">通知操作的消息操作是"通知"。</span><span class="sxs-lookup"><span data-stu-id="00b05-124">The message action for the notification operation is “Notification.”</span></span>  
  