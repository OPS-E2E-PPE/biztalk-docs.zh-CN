---
title: 复合操作的消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d80c023b-1912-43d4-be29-eb9e1b323593
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 716e87dd2973572d473f6637e12c5a80ac6cf847
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015289"
---
# <a name="message-schemas-for-composite-operations"></a><span data-ttu-id="c78be-102">复合操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="c78be-102">Message Schemas for Composite Operations</span></span>
<span data-ttu-id="c78be-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]使您可以执行复合操作上的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="c78be-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] enables you to execute composite operations on the SQL Server database.</span></span> <span data-ttu-id="c78be-104">复合操作可以包含多个操作，包括 Insert、 Update 和删除表和视图操作和对存储过程的操作。</span><span class="sxs-lookup"><span data-stu-id="c78be-104">A composite operation can contain multiple operations including the Insert, Update, and Delete operations on the tables and views, and operations on stored procedures.</span></span> <span data-ttu-id="c78be-105">复合操作可以按任意顺序包含这些操作。</span><span class="sxs-lookup"><span data-stu-id="c78be-105">A composite operation can include these operations in any order.</span></span>  
  
 <span data-ttu-id="c78be-106">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="c78be-106">For more information about:</span></span>  
  
- <span data-ttu-id="c78be-107">复合操作，请参阅[支持复合操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)。</span><span class="sxs-lookup"><span data-stu-id="c78be-107">Composite operations, see [Support for Composite Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).</span></span>  
  
- <span data-ttu-id="c78be-108">如何执行复合操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[使用 SQL 适配器的 SQL Server 中运行复合操作](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="c78be-108">How to perform composite operations using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Run composite operations in SQL Server  using the SQL adapter](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
## <a name="message-structure-for-the-composite-operation"></a><span data-ttu-id="c78be-109">复合操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="c78be-109">Message Structure for the Composite Operation</span></span>  
 <span data-ttu-id="c78be-110">因为复合操作包含多个单个操作;复合操作的消息结构包含各个操作的消息的结构。</span><span class="sxs-lookup"><span data-stu-id="c78be-110">Since a composite operation contains multiple individual operations; the message structure of a composite operation contains message structures of the individual operations.</span></span> <span data-ttu-id="c78be-111">复合操作包含在表、 视图和存储的过程的操作，如复合操作消息遵循请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="c78be-111">As a composite operation contains operations on tables, views, and stored procedures, the composite operation message follows a request-response message exchange pattern.</span></span>  
  
 <span data-ttu-id="c78be-112">下表显示了包含插入操作的复合操作的请求和响应消息的结构，不接受任何存储的过程输入参数和删除操作。</span><span class="sxs-lookup"><span data-stu-id="c78be-112">The following table shows the structure of the request and response messages of a composite operation that contains an Insert operation, a stored procedure that does not take any input parameters, and a Delete operation.</span></span>  
  
|<span data-ttu-id="c78be-113">运算</span><span class="sxs-lookup"><span data-stu-id="c78be-113">Operation</span></span>|<span data-ttu-id="c78be-114">XML 消息</span><span class="sxs-lookup"><span data-stu-id="c78be-114">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c78be-115">复合操作请求</span><span class="sxs-lookup"><span data-stu-id="c78be-115">Composite Operation Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[Value1]</[FIELD2_NAME]>         …       </[TABLE_NAME]>     </Rows>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]" />   <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>       </[TABLE_NAME]>     </Rows>   </Delete> </Request>`|  
|<span data-ttu-id="c78be-116">复合操作的响应</span><span class="sxs-lookup"><span data-stu-id="c78be-116">Composite Operation Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <InsertResult>       <long>[value]</long>      </InsertResult>   </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">     <[SP_NAME]Result>       <DataSet>         <any>[Value]</any>          <any>[Value]</any>          …       </DataSet>     </[SP_NAME]Result>     <ReturnValue>[value]</ReturnValue>    </[SP_NAME]Response>   <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 <span data-ttu-id="c78be-117">[PROJECT_NAME] = 包含复合操作架构的 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="c78be-117">[PROJECT_NAME] = Name of the BizTalk project that contains the composite operation schema.</span></span>  
  
 <span data-ttu-id="c78be-118">[COMPOSITE_SCHEMA_NAME] = 由用户提供的复合操作架构的名称。</span><span class="sxs-lookup"><span data-stu-id="c78be-118">[COMPOSITE_SCHEMA_NAME] = Name of the composite operation schema given by the user.</span></span>  
  
 <span data-ttu-id="c78be-119">[架构] = 集合的 SQL Server 项目;例如，dbo。</span><span class="sxs-lookup"><span data-stu-id="c78be-119">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
 <span data-ttu-id="c78be-120">[TABLE_NAME] = 名称表;例如，员工。</span><span class="sxs-lookup"><span data-stu-id="c78be-120">[TABLE_NAME] = Name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="c78be-121">[FIELD1_NAME] = 表字段名称;例如，名称。</span><span class="sxs-lookup"><span data-stu-id="c78be-121">[FIELD1_NAME] = Table field name; for example, NAME.</span></span>  
  
 <span data-ttu-id="c78be-122">[SP_NAME] = 存储的过程来执行;例如，ADD_EMP_DETAILS。</span><span class="sxs-lookup"><span data-stu-id="c78be-122">[SP_NAME] = The stored procedure to be executed; for example, ADD_EMP_DETAILS.</span></span>  
  
## <a name="message-action-for-the-composite-operation"></a><span data-ttu-id="c78be-123">复合操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="c78be-123">Message Action for the Composite Operation</span></span>  
 <span data-ttu-id="c78be-124">复合操作的消息操作是"CompositeOperation。"</span><span class="sxs-lookup"><span data-stu-id="c78be-124">The message action for the composite operation is “CompositeOperation.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c78be-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="c78be-125">See Also</span></span>  
 [<span data-ttu-id="c78be-126">消息和用于 SQL Server 的 BizTalk 适配器的消息架构</span><span class="sxs-lookup"><span data-stu-id="c78be-126">Messages and Message Schemas for BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)