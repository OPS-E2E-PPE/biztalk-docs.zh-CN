---
title: 复合 Operation2 的消息架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0164ea07-a373-430b-b569-3e29df1d081b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1014ea162e9fab33aa6630d0cdb4eb774f91031
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214061"
---
# <a name="message-schemas-for-the-composite-operation"></a><span data-ttu-id="00229-102">复合操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="00229-102">Message Schemas for the Composite Operation</span></span>
<span data-ttu-id="00229-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]使你可以执行对 Oracle 数据库的复合操作。</span><span class="sxs-lookup"><span data-stu-id="00229-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] enables you to execute composite operations on the Oracle database.</span></span> <span data-ttu-id="00229-104">复合操作可以包含多个操作，并按任何顺序。</span><span class="sxs-lookup"><span data-stu-id="00229-104">A composite operation can contain multiple operations, and in any order.</span></span> <span data-ttu-id="00229-105">有关哪些操作可以包含在复合操作的信息，请参阅[运行 Oracle 数据库中的复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="00229-105">For information about which operations can be included in a composite operation, see [Run Composite Operations in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md).</span></span>  
  
 <span data-ttu-id="00229-106">有关如何执行复合操作使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[使用 BizTalk Server 的 Oracle 数据库上运行复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="00229-106">For information about how to perform composite operations using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Run Composite Operations on Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
## <a name="message-structure-for-the-composite-operation"></a><span data-ttu-id="00229-107">复合操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="00229-107">Message Structure for the Composite Operation</span></span>  
 <span data-ttu-id="00229-108">因为复合操作包含多个单独的操作;复合操作的消息结构包含各个操作的消息的结构。</span><span class="sxs-lookup"><span data-stu-id="00229-108">Because a composite operation contains multiple individual operations; the message structure of a composite operation contains message structures of the individual operations.</span></span> <span data-ttu-id="00229-109">复合操作消息遵循请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="00229-109">The composite operation message follows a request-response message exchange pattern.</span></span>  
  
 <span data-ttu-id="00229-110">下表显示包含插入操作的复合操作的请求和响应消息的结构、 打包的存储的过程，不接受任何输入参数和删除操作。</span><span class="sxs-lookup"><span data-stu-id="00229-110">The following table shows the structure of the request and response messages of a composite operation that contains an Insert operation, a packaged stored procedure that does not take any input parameters, and a Delete operation.</span></span>  
  
|<span data-ttu-id="00229-111">运算</span><span class="sxs-lookup"><span data-stu-id="00229-111">Operation</span></span>|<span data-ttu-id="00229-112">XML 消息</span><span class="sxs-lookup"><span data-stu-id="00229-112">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00229-113">复合操作请求</span><span class="sxs-lookup"><span data-stu-id="00229-113">Composite Operation Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <RECORDSET>       <[TABLE_NAME]RECORDINSERT>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>         …       </[TABLE_NAME]RECORDINSERT>    </RECORDSET>   </Insert>   <[SP_NAME] xmlns="[VERSION]/[SCHEMA]/Procedure" />   <Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <FILTER>[WHERE_clause]</FILTER>   </Delete> </Request>`|  
|<span data-ttu-id="00229-114">复合操作响应</span><span class="sxs-lookup"><span data-stu-id="00229-114">Composite Operation Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <InsertResult>[value]</InsertResult>    </InsertResponse>   <[SP_NAME]Response xmlns="[VERSION]/[SCHEMA]/Procedure">     <[PRM1_NAME]>value1<[PRM1_NAME]>     <[PRM2_NAME]>value2</[PRM2_NAME]>     …   </[SP_NAME]Response>    <DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 <span data-ttu-id="00229-115">[VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.OracleDB/2007/03</span><span class="sxs-lookup"><span data-stu-id="00229-115">[VERSION] = The message version string; for example, http://Microsoft.LobServices.OracleDB/2007/03</span></span>  
  
 <span data-ttu-id="00229-116">[文件的内容] = 包含复合操作架构的 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="00229-116">[PROJECT_NAME] = Name of the BizTalk project that contains the composite operation schema.</span></span>  
  
 <span data-ttu-id="00229-117">[COMPOSITE_SCHEMA_NAME] = 给定用户的复合操作架构的名称。</span><span class="sxs-lookup"><span data-stu-id="00229-117">[COMPOSITE_SCHEMA_NAME] = Name of the composite operation schema given by the user.</span></span>  
  
 <span data-ttu-id="00229-118">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="00229-118">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="00229-119">[TABLE_NAME] = 表; 的名称例如，员工。</span><span class="sxs-lookup"><span data-stu-id="00229-119">[TABLE_NAME] = Name of the table; for example, EMPLOYEE.</span></span>  
  
 <span data-ttu-id="00229-120">[FIELD1_NAME] = 表字段名称;例如，名称。</span><span class="sxs-lookup"><span data-stu-id="00229-120">[FIELD1_NAME] = Table field name; for example, NAME.</span></span>  
  
 <span data-ttu-id="00229-121">[SP_NAME] = 打包的存储的过程以执行;例如，ADD_EMP_DETAILS。</span><span class="sxs-lookup"><span data-stu-id="00229-121">[SP_NAME] = The packaged stored procedure to be executed; for example, ADD_EMP_DETAILS.</span></span>  
  
 <span data-ttu-id="00229-122">[PRM1_NAME] = 存储过程中的 Oracle 参数的名称。</span><span class="sxs-lookup"><span data-stu-id="00229-122">[PRM1_NAME] = The name of the Oracle parameter in the stored procedure.</span></span>  
  
## <a name="message-action-for-the-composite-operation"></a><span data-ttu-id="00229-123">复合操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="00229-123">Message Action for the Composite Operation</span></span>  
 <span data-ttu-id="00229-124">复合操作的消息操作是"http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation。"</span><span class="sxs-lookup"><span data-stu-id="00229-124">The message action for the composite operation is “http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00229-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00229-125">See Also</span></span>  
 [<span data-ttu-id="00229-126">消息和用于 Oracle 数据库的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="00229-126">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)