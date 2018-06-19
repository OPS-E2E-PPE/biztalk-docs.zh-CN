---
title: 请求集的消息架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bba9677d-ee94-4da5-8611-b1e47f2f3798
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fd81ee75088b41a182c5a2aa675266420f8f32f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217093"
---
# <a name="message-schemas-for-request-sets"></a><span data-ttu-id="afd13-102">请求集的消息架构</span><span class="sxs-lookup"><span data-stu-id="afd13-102">Message Schemas for Request Sets</span></span>
<span data-ttu-id="afd13-103">在 Oracle E-business Suite 中的 Oracle 应用程序中设置每个请求显示作为中的操作[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="afd13-103">Each request set in an Oracle application in Oracle E-Business Suite is surfaced as an operation in [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span>  
  
## <a name="message-structure-of-request-set-operation"></a><span data-ttu-id="afd13-104">请求消息结构集的操作</span><span class="sxs-lookup"><span data-stu-id="afd13-104">Message Structure of Request Set Operation</span></span>  
 <span data-ttu-id="afd13-105">针对请求集显示操作遵循请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="afd13-105">The operations surfaced for request set follow a request-response message exchange pattern.</span></span> <span data-ttu-id="afd13-106">下表显示这些请求和响应消息的结构。</span><span class="sxs-lookup"><span data-stu-id="afd13-106">The following table shows the structure of these request and response messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afd13-107">在表后，请参阅实体说明。</span><span class="sxs-lookup"><span data-stu-id="afd13-107">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="afd13-108">运算</span><span class="sxs-lookup"><span data-stu-id="afd13-108">Operation</span></span>|<span data-ttu-id="afd13-109">XML 消息</span><span class="sxs-lookup"><span data-stu-id="afd13-109">XML Message</span></span>|<span data-ttu-id="afd13-110">Description</span><span class="sxs-lookup"><span data-stu-id="afd13-110">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="afd13-111">[Request_Set_Name]请求</span><span class="sxs-lookup"><span data-stu-id="afd13-111">[Request_Set_Name] Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name] xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]/">   <SetRelClassOptions>     <Application>[value]</Application>     <ClassName>[value]</ClassName>     <CancelOrHold>[value]</CancelOrHold>     <StaleDate>[value]</StaleDate>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRelClassOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <SetNlsOptions>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetNlsOptions>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_NAME1]>[value]</[CONCURRENT_PROGRAM_NAME1]>   <[CONCURRENT_PROGRAM_NAME2]>[value]</[CONCURRENT_PROGRAM_NAME2]>   … </[Request_Set_Name]>`|<span data-ttu-id="afd13-112">-[Request_Set_Name] 操作采用标准的五个参数： `SetRelClassOptions`， `SetPrintOptions`， `SetRepeatOptions`， `SetNlsOptions`，和`StartTime`。</span><span class="sxs-lookup"><span data-stu-id="afd13-112">- The [Request_Set_Name] operation takes five standard parameters:  `SetRelClassOptions`, `SetPrintOptions`,  `SetRepeatOptions`, `SetNlsOptions`, and `StartTime`.</span></span><br /><br /> <span data-ttu-id="afd13-113">-`ContinueOnFail`参数指示请求集提交是否应继续还是中引发异常用例 parent 参数 (`SetRelClassOptions`， `SetPrintOptions`，`SetRepeatOptions`或`SetNlsOptions`) 失败。</span><span class="sxs-lookup"><span data-stu-id="afd13-113">- The `ContinueOnFail` parameter indicates whether the request set submission should continue or throw an exception in case the parent parameter (`SetRelClassOptions`, `SetPrintOptions`, `SetRepeatOptions` or `SetNlsOptions`) fails.</span></span> <span data-ttu-id="afd13-114">你可以指定**True** （继续） 或**False** （引发异常）。</span><span class="sxs-lookup"><span data-stu-id="afd13-114">You can specify **True** (continue) or **False** (throw an exception).</span></span><br /><br /> <span data-ttu-id="afd13-115">-有关每个参数的详细信息，请参见[对请求设置的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="afd13-115">- For detailed information about each parameter, see [Operations on Request Sets](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).</span></span>|  
|<span data-ttu-id="afd13-116">[Request_Set_Name]响应</span><span class="sxs-lookup"><span data-stu-id="afd13-116">[Request_Set_Name] Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name]Response xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]">   <[Request_Set_Name]Result>[value]</[Request_Set_Name]Result> </[Request_Set_Name]Response>`|<span data-ttu-id="afd13-117">来自 Oracle E-business Suite 的响应包含一个并发请求 id。</span><span class="sxs-lookup"><span data-stu-id="afd13-117">The response from Oracle E-Business Suite contains a concurrent request ID.</span></span>|  
  
 <span data-ttu-id="afd13-118">实体说明：</span><span class="sxs-lookup"><span data-stu-id="afd13-118">Entity descriptions:</span></span>  
  
 <span data-ttu-id="afd13-119">[VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05</span><span class="sxs-lookup"><span data-stu-id="afd13-119">[VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05</span></span>  
  
 <span data-ttu-id="afd13-120">实例时都提供 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="afd13-120">.</span></span>  
  
 <span data-ttu-id="afd13-121">[CONCURRENT_PROGRAM_NAME] = 并发请求集中包含的程序。</span><span class="sxs-lookup"><span data-stu-id="afd13-121">[CONCURRENT_PROGRAM_NAME] = Concurrent program included in the request set.</span></span>  
  
## <a name="message-actions-for-request-sets"></a><span data-ttu-id="afd13-122">请求集的消息操作</span><span class="sxs-lookup"><span data-stu-id="afd13-122">Message Actions for Request Sets</span></span>  
 <span data-ttu-id="afd13-123">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]请求集使用以下的消息操作。</span><span class="sxs-lookup"><span data-stu-id="afd13-123">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses the following message actions for request sets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afd13-124">在表后，请参阅实体说明。</span><span class="sxs-lookup"><span data-stu-id="afd13-124">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="afd13-125">消息</span><span class="sxs-lookup"><span data-stu-id="afd13-125">Message</span></span>|<span data-ttu-id="afd13-126">操作</span><span class="sxs-lookup"><span data-stu-id="afd13-126">Action</span></span>|<span data-ttu-id="afd13-127">示例</span><span class="sxs-lookup"><span data-stu-id="afd13-127">Example</span></span>|  
|-------------|------------|-------------|  
|<span data-ttu-id="afd13-128">请求 Set 请求</span><span class="sxs-lookup"><span data-stu-id="afd13-128">Request Set request</span></span>|<span data-ttu-id="afd13-129">RequestSets / [APP_SHORT_NAME] / [REQUESTSET_SHORT_NAME]</span><span class="sxs-lookup"><span data-stu-id="afd13-129">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]</span></span>|<span data-ttu-id="afd13-130">RequestSets/SQLGL/FNDRSSUB965</span><span class="sxs-lookup"><span data-stu-id="afd13-130">RequestSets/SQLGL/FNDRSSUB965</span></span>|  
|<span data-ttu-id="afd13-131">请求集响应</span><span class="sxs-lookup"><span data-stu-id="afd13-131">Request Set response</span></span>|<span data-ttu-id="afd13-132">RequestSets / [APP_SHORT_NAME] / [REQUESTSET_SHORT_NAME]] / 响应</span><span class="sxs-lookup"><span data-stu-id="afd13-132">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]]/response</span></span>|<span data-ttu-id="afd13-133">RequestSets/SQLGL/FNDRSSUB965/响应</span><span class="sxs-lookup"><span data-stu-id="afd13-133">RequestSets/SQLGL/FNDRSSUB965/response</span></span>|  
  
 <span data-ttu-id="afd13-134">实体说明：</span><span class="sxs-lookup"><span data-stu-id="afd13-134">Entity descriptions:</span></span>  
  
 <span data-ttu-id="afd13-135">[APP_SHORT_NAME] = 应用程序短名称。</span><span class="sxs-lookup"><span data-stu-id="afd13-135">[APP_SHORT_NAME] = Application short name.</span></span>  
  
 <span data-ttu-id="afd13-136">[REQUESTSET_SHORT_NAME] = 请求设置短名称。</span><span class="sxs-lookup"><span data-stu-id="afd13-136">[REQUESTSET_SHORT_NAME] = Request Set short name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afd13-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afd13-137">See Also</span></span>  
 [<span data-ttu-id="afd13-138">消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="afd13-138">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)