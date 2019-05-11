---
title: 轮询和 TypedPolling 操作中 BizTalk SQL 适配器的消息架构 |Microsoft Docs
description: 轮询和 TypedPolling 消息结构，可由 SQL 适配器在 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e900307-2c9c-493b-81c9-67af3e143eeb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4930e854bcad679a3b6ab8c3e90150ad3e879c98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368614"
---
# <a name="message-schemas-for-the-polling-and-typedpolling-operations"></a><span data-ttu-id="138c8-103">轮询和 TypedPolling 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="138c8-103">Message Schemas for the Polling and TypedPolling Operations</span></span>
<span data-ttu-id="138c8-104">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]曲面的轮询和 TypedPolling 入站操作以返回到适配器客户端的轮询查询的结果集。</span><span class="sxs-lookup"><span data-stu-id="138c8-104">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] surfaces the Polling and TypedPolling inbound operations to return the result set of the polling query to an adapter client.</span></span>  
  
 <span data-ttu-id="138c8-105">通过设置绑定属性来配置在轮询和 TypedPolling 操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="138c8-105">You configure the Polling and TypedPolling operations by setting binding properties in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="138c8-106">有关这些绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="138c8-106">For more information about these binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="138c8-107">您设置**PollingStatement**绑定属性来指定 SQL 语句 (SELECT 或 EXEC\<存储过程\>) 的轮询查询。</span><span class="sxs-lookup"><span data-stu-id="138c8-107">You set the **PollingStatement** binding property to specify a SQL statement (SELECT or EXEC \<stored procedure\>) for the polling query.</span></span> <span data-ttu-id="138c8-108">此查询的结果集返回到你的代码在轮询操作中，数据作为和 TypedPolling 操作中的强类型化数据。</span><span class="sxs-lookup"><span data-stu-id="138c8-108">The result set of this query is returned as data to your code in the Polling operation, and as strongly-typed data in the TypedPolling operation.</span></span> <span data-ttu-id="138c8-109">该适配器显示为指定的查询由元数据，确定结果集的结构。</span><span class="sxs-lookup"><span data-stu-id="138c8-109">The structure of the result set is determined by the metadata that the adapter surfaces for the specified query.</span></span>  
  
## <a name="polling-message-structure"></a><span data-ttu-id="138c8-110">轮询消息结构</span><span class="sxs-lookup"><span data-stu-id="138c8-110">Polling message structure</span></span> 
  
<span data-ttu-id="138c8-111">**操作**: `Polling`</span><span class="sxs-lookup"><span data-stu-id="138c8-111">**Operation**: `Polling`</span></span>

<span data-ttu-id="138c8-112">**XML 消息**:</span><span class="sxs-lookup"><span data-stu-id="138c8-112">**XML Message**:</span></span>  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Polling xmlns="http://schemas.microsoft.com/Sql/2008/05/Polling">
    <PolledData>
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">
        <any>[Value]</any>
        <any>[Value]</any>
        …
        </DataSet>
    </PolledData>
 </Polling>
```

<span data-ttu-id="138c8-113">**说明**：由 SQL Server 发送到适配器客户端的入站的消息。</span><span class="sxs-lookup"><span data-stu-id="138c8-113">**Description**: The inbound message that is sent by the SQL Server to the adapter clients.</span></span>  


## <a name="typedpolling-message-structure"></a><span data-ttu-id="138c8-114">TypedPolling 消息结构</span><span class="sxs-lookup"><span data-stu-id="138c8-114">TypedPolling message structure</span></span> 

<span data-ttu-id="138c8-115">**操作**: `TypedPolling`</span><span class="sxs-lookup"><span data-stu-id="138c8-115">**Operation**: `TypedPolling`</span></span>

<span data-ttu-id="138c8-116">**XML 消息**:</span><span class="sxs-lookup"><span data-stu-id="138c8-116">**XML Message**:</span></span>  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <TypedPollingResultSet xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedPolling">
    <COLUMN1>[Value]</Column1>
    <COLUMN2>[Value]</Column2>
    …
  </TypedPollingResultSet>
```

<span data-ttu-id="138c8-117">**说明**：强类型化入站的消息的 SQL Server 发送给适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="138c8-117">**Description**: The strongly-typed inbound message that is sent by the SQL Server to the adapter clients.</span></span>
  
## <a name="message-action-for-the-polling-and-typedpolling-operations"></a><span data-ttu-id="138c8-118">用于轮询和 TypedPolling 操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="138c8-118">Message Action for the Polling and TypedPolling Operations</span></span>  
 <span data-ttu-id="138c8-119">消息操作:</span><span class="sxs-lookup"><span data-stu-id="138c8-119">The message action for the:</span></span>  
  
-   <span data-ttu-id="138c8-120">轮询操作"轮询"。</span><span class="sxs-lookup"><span data-stu-id="138c8-120">Polling operation is “Polling.”</span></span>  
  
-   <span data-ttu-id="138c8-121">TypedPolling 操作是"TypedPolling。"</span><span class="sxs-lookup"><span data-stu-id="138c8-121">TypedPolling operation is “TypedPolling.”</span></span>  
  
