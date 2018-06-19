---
title: 复合操作的消息架构 |Microsoft 文档
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
ms.openlocfilehash: b89c354baea2ddb46abf549752dc09699b9c9695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222509"
---
# <a name="message-schemas-for-composite-operations"></a><span data-ttu-id="d14a9-102">复合操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="d14a9-102">Message Schemas for Composite Operations</span></span>
<span data-ttu-id="d14a9-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]使您能够执行 SQL Server 数据库上的复合操作。</span><span class="sxs-lookup"><span data-stu-id="d14a9-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] enables you to execute composite operations on the SQL Server database.</span></span> <span data-ttu-id="d14a9-104">复合操作可以包含多个操作包括 Insert、 Update 和删除操作上的表和视图和存储过程的操作。</span><span class="sxs-lookup"><span data-stu-id="d14a9-104">A composite operation can contain multiple operations including the Insert, Update, and Delete operations on the tables and views, and operations on stored procedures.</span></span> <span data-ttu-id="d14a9-105">复合操作可以按任何顺序包含这些操作。</span><span class="sxs-lookup"><span data-stu-id="d14a9-105">A composite operation can include these operations in any order.</span></span>  
  
 <span data-ttu-id="d14a9-106">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="d14a9-106">For more information about:</span></span>  
  
-   <span data-ttu-id="d14a9-107">复合操作，请参阅[对复合操作的支持](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)。</span><span class="sxs-lookup"><span data-stu-id="d14a9-107">Composite operations, see [Support for Composite Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).</span></span>  
  
-   <span data-ttu-id="d14a9-108">如何执行复合操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[在使用 SQL 适配器的 SQL Server 中运行复合操作](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d14a9-108">How to perform composite operations using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Run composite operations in SQL Server  using the SQL adapter](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
## <a name="message-structure-for-the-composite-operation"></a><span data-ttu-id="d14a9-109">复合操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="d14a9-109">Message Structure for the Composite Operation</span></span>  
 <span data-ttu-id="d14a9-110">因为复合操作包含多个单独的操作;复合操作的消息结构包含各个操作的消息的结构。</span><span class="sxs-lookup"><span data-stu-id="d14a9-110">Since a composite operation contains multiple individual operations; the message structure of a composite operation contains message structures of the individual operations.</span></span> <span data-ttu-id="d14a9-111">复合操作包含在表、 视图和存储的过程的操作，如复合操作消息遵循请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="d14a9-111">As a composite operation contains operations on tables, views, and stored procedures, the composite operation message follows a request-response message exchange pattern.</span></span>  
  
 <span data-ttu-id="d14a9-112">下表显示包含插入操作的复合操作的请求和响应消息的结构，不接受任何存储的过程输入参数和删除操作。</span><span class="sxs-lookup"><span data-stu-id="d14a9-112">The following table shows the structure of the request and response messages of a composite operation that contains an Insert operation, a stored procedure that does not take any input parameters, and a Delete operation.</span></span>  
  
|<span data-ttu-id="d14a9-113">运算</span><span class="sxs-lookup"><span data-stu-id="d14a9-113">Operation</span></span>|<span data-ttu-id="d14a9-114">XML 消息</span><span class="sxs-lookup"><span data-stu-id="d14a9-114">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d14a9-115">复合操作请求</span><span class="sxs-lookup"><span data-stu-id="d14a9-115">Composite Operation Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[Value1]</[FIELD2_NAME]>         …       </[TABLE_NAME]>     </Rows>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]" />   <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>       </[TABLE_NAME]>     </Rows>   </Delete> </Request>`|  
|<span data-ttu-id="d14a9-116">复合操作响应</span><span class="sxs-lookup"><span data-stu-id="d14a9-116">Composite Operation Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <InsertResult>       <long>[value]</long>      </InsertResult>   </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">     <[SP_NAME]Result>       <DataSet>         <any>[Value]</any>          <any>[Value]</any>          …       </DataSet>     </[SP_NAME]Result>     <ReturnValue>[value]</ReturnValue>    </[SP_NAME]Response>   <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 <span data-ttu-id="d14a9-117">[文件的内容] = 包含复合操作架构的 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="d14a9-117">[PROJECT_NAME] = Name of the BizTalk project that contains the composite operation schema.</span></span>  
  
 <span data-ttu-id="d14a9-118">[COMPOSITE_SCHEMA_NAME] = 给定用户的复合操作架构的名称。</span><span class="sxs-lookup"><span data-stu-id="d14a9-118">[COMPOSITE_SCHEMA_NAME] = Name of the composite operation schema given by the user.</span></span>  
  
 <span data-ttu-id="d14a9-119">[架构] = SQL Server 集合项目;例如，dbo。</span><span class="sxs-lookup"><span data-stu-id="d14a9-119">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
 <span data-ttu-id="d14a9-120">[TABLE_NAME] = 表; 的名称例如，员工。</span><span class="sxs-lookup"><span data-stu-id="d14a9-120">[TABLE_NAME] = Name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="d14a9-121">[FIELD1_NAME] = 表字段名称;例如，名称。</span><span class="sxs-lookup"><span data-stu-id="d14a9-121">[FIELD1_NAME] = Table field name; for example, NAME.</span></span>  
  
 <span data-ttu-id="d14a9-122">[SP_NAME] = 存储的过程以执行;例如，ADD_EMP_DETAILS。</span><span class="sxs-lookup"><span data-stu-id="d14a9-122">[SP_NAME] = The stored procedure to be executed; for example, ADD_EMP_DETAILS.</span></span>  
  
## <a name="message-action-for-the-composite-operation"></a><span data-ttu-id="d14a9-123">复合操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="d14a9-123">Message Action for the Composite Operation</span></span>  
 <span data-ttu-id="d14a9-124">复合操作的消息操作是"CompositeOperation。"</span><span class="sxs-lookup"><span data-stu-id="d14a9-124">The message action for the composite operation is “CompositeOperation.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14a9-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d14a9-125">See Also</span></span>  
 [<span data-ttu-id="d14a9-126">消息和用于 SQL Server 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="d14a9-126">Messages and Message Schemas for BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)