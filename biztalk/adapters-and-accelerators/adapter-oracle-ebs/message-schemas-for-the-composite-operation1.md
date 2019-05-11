---
title: 对于复合 Operation1 消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 768473ef-da8d-4e58-86cb-597c28ded49c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d069e543e64c26a9229bcb561052ce456c82e32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375380"
---
# <a name="message-schemas-for-the-composite-operation"></a><span data-ttu-id="3f627-102">复合操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="3f627-102">Message Schemas for the Composite Operation</span></span>
<span data-ttu-id="3f627-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ，可在 Oracle E-business Suite 中执行复合操作。</span><span class="sxs-lookup"><span data-stu-id="3f627-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] enables you to execute composite operations in Oracle E-Business Suite.</span></span> <span data-ttu-id="3f627-104">复合操作可以包含多个操作，并按任何顺序。</span><span class="sxs-lookup"><span data-stu-id="3f627-104">A composite operation can contain multiple operations, and in any order.</span></span> <span data-ttu-id="3f627-105">有关哪些操作可以包含在复合操作的信息，请参阅[支持复合操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)。</span><span class="sxs-lookup"><span data-stu-id="3f627-105">For information about which operations can be included in a composite operation, see [Support for Composite Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).</span></span>  
  
 <span data-ttu-id="3f627-106">有关如何执行复合操作使用的信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[使用 BizTalk Server 的 Oracle 数据库上运行复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="3f627-106">For information about how to perform composite operations using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [Run Composite Operations on Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
## <a name="message-structure-for-the-composite-operation"></a><span data-ttu-id="3f627-107">复合操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="3f627-107">Message Structure for the Composite Operation</span></span>  
 <span data-ttu-id="3f627-108">因为复合操作包含多个单个操作;复合操作的消息结构包含各个操作的消息的结构。</span><span class="sxs-lookup"><span data-stu-id="3f627-108">Since a composite operation contains multiple individual operations; the message structure of a composite operation contains message structures of the individual operations.</span></span> <span data-ttu-id="3f627-109">复合操作消息遵循请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="3f627-109">The composite operation message follows a request-response message exchange pattern.</span></span>  
  
 <span data-ttu-id="3f627-110">下表显示了包含插入操作的复合操作的请求和响应消息的结构，打包的存储的过程，不接受任何输入参数和删除操作。</span><span class="sxs-lookup"><span data-stu-id="3f627-110">The following table shows the structure of the request and response messages of a composite operation that contains an Insert operation, a packaged stored procedure that does not take any input parameters, and a Delete operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f627-111">实体说明表后进行查看。</span><span class="sxs-lookup"><span data-stu-id="3f627-111">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="3f627-112">操作</span><span class="sxs-lookup"><span data-stu-id="3f627-112">Operation</span></span>|<span data-ttu-id="3f627-113">XML 消息</span><span class="sxs-lookup"><span data-stu-id="3f627-113">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f627-114">复合操作请求</span><span class="sxs-lookup"><span data-stu-id="3f627-114">Composite Operation Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <Recordset>       <InsertRecord>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>           <InLineValue>[value]</InlineValue>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>           <InLineValue>[value]</InlineValue>         …       <InsertRecord>    </RECORDSET>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/[SCHEMA]/[APP_NAME]" />   <Delete xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <FILTER>[WHERE_clause]</FILTER>   </Delete> </Request>`|  
|<span data-ttu-id="3f627-115">复合操作的响应</span><span class="sxs-lookup"><span data-stu-id="3f627-115">Composite Operation Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <InsertResult>[value]</InsertResult>    </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Procedures/[SCHEMA]">     <[PRM1_NAME]>value1<[PRM1_NAME]>     <[PRM2_NAME]>value2</[PRM2_NAME]>     …   </[SP_NAME]Response>    <DeleteResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 <span data-ttu-id="3f627-116">实体说明：</span><span class="sxs-lookup"><span data-stu-id="3f627-116">Entity descriptions:</span></span>  
  
 <span data-ttu-id="3f627-117">[PROJECT_NAME] = 包含复合操作架构的 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="3f627-117">[PROJECT_NAME] = Name of the BizTalk project that contains the composite operation schema.</span></span>  
  
 <span data-ttu-id="3f627-118">[COMPOSITE_SCHEMA_NAME] = 由用户提供的复合操作架构的名称。</span><span class="sxs-lookup"><span data-stu-id="3f627-118">[COMPOSITE_SCHEMA_NAME] = Name of the composite operation schema given by the user.</span></span>  
  
 <span data-ttu-id="3f627-119">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="3f627-119">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="3f627-120">[TABLE_NAME] = 名称表;例如，员工。</span><span class="sxs-lookup"><span data-stu-id="3f627-120">[TABLE_NAME] = Name of the table; for example, EMPLOYEE.</span></span>  
  
 <span data-ttu-id="3f627-121">[FIELD1_NAME] = 表字段名称;例如，名称。</span><span class="sxs-lookup"><span data-stu-id="3f627-121">[FIELD1_NAME] = Table field name; for example, NAME.</span></span>  
  
 <span data-ttu-id="3f627-122">[SP_NAME] = 打包的存储的过程来执行;例如，ADD_EMP_DETAILS。</span><span class="sxs-lookup"><span data-stu-id="3f627-122">[SP_NAME] = The packaged stored procedure to be executed; for example, ADD_EMP_DETAILS.</span></span>  
  
 <span data-ttu-id="3f627-123">[A p p _] = 包含打包的存储的过程的 Oracle 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="3f627-123">[APP_NAME] = Name of the Oracle Application that contains the packaged stored procedure.</span></span>  
  
 <span data-ttu-id="3f627-124">[PRM1_NAME] = 打包的存储过程中的 Oracle 参数的名称。</span><span class="sxs-lookup"><span data-stu-id="3f627-124">[PRM1_NAME] = The name of the Oracle parameter in the packaged stored procedure.</span></span>  
  
## <a name="message-action-for-the-composite-operation"></a><span data-ttu-id="3f627-125">复合操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="3f627-125">Message Action for the Composite Operation</span></span>  
 <span data-ttu-id="3f627-126">复合操作的消息操作是"CompositeOperation。"</span><span class="sxs-lookup"><span data-stu-id="3f627-126">The message action for the composite operation is “CompositeOperation.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f627-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f627-127">See Also</span></span>  
 [<span data-ttu-id="3f627-128">消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="3f627-128">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)