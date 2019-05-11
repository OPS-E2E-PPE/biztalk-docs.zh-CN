---
title: 请求集的消息架构 |Microsoft Docs
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
ms.openlocfilehash: 1fb14d8ed93f61f72b08bc4db31464bcf8eb4561
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530687"
---
# <a name="message-schemas-for-request-sets"></a><span data-ttu-id="e4456-102">请求集的消息架构</span><span class="sxs-lookup"><span data-stu-id="e4456-102">Message Schemas for Request Sets</span></span>
<span data-ttu-id="e4456-103">在 Oracle E-business Suite 中的 Oracle 应用程序中设置每个请求显示在操作的形式[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e4456-103">Each request set in an Oracle application in Oracle E-Business Suite is surfaced as an operation in [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span>  
  
## <a name="message-structure-of-request-set-operation"></a><span data-ttu-id="e4456-104">请求的消息结构设置操作</span><span class="sxs-lookup"><span data-stu-id="e4456-104">Message Structure of Request Set Operation</span></span>  
 <span data-ttu-id="e4456-105">提供的请求集的操作遵循请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="e4456-105">The operations surfaced for request set follow a request-response message exchange pattern.</span></span> <span data-ttu-id="e4456-106">下表显示了这些请求和响应消息的结构。</span><span class="sxs-lookup"><span data-stu-id="e4456-106">The following table shows the structure of these request and response messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4456-107">实体说明表后进行查看。</span><span class="sxs-lookup"><span data-stu-id="e4456-107">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="e4456-108">操作</span><span class="sxs-lookup"><span data-stu-id="e4456-108">Operation</span></span>|<span data-ttu-id="e4456-109">XML 消息</span><span class="sxs-lookup"><span data-stu-id="e4456-109">XML Message</span></span>|<span data-ttu-id="e4456-110">Description</span><span class="sxs-lookup"><span data-stu-id="e4456-110">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="e4456-111">[Request_Set_Name] Request</span><span class="sxs-lookup"><span data-stu-id="e4456-111">[Request_Set_Name] Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name] xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]/">   <SetRelClassOptions>     <Application>[value]</Application>     <ClassName>[value]</ClassName>     <CancelOrHold>[value]</CancelOrHold>     <StaleDate>[value]</StaleDate>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRelClassOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <SetNlsOptions>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetNlsOptions>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_NAME1]>[value]</[CONCURRENT_PROGRAM_NAME1]>   <[CONCURRENT_PROGRAM_NAME2]>[value]</[CONCURRENT_PROGRAM_NAME2]>   … </[Request_Set_Name]>`|<span data-ttu-id="e4456-112">-[Request_Set_Name] 操作采用标准的五个参数： `SetRelClassOptions`， `SetPrintOptions`， `SetRepeatOptions`， `SetNlsOptions`，和`StartTime`。</span><span class="sxs-lookup"><span data-stu-id="e4456-112">- The [Request_Set_Name] operation takes five standard parameters:  `SetRelClassOptions`, `SetPrintOptions`,  `SetRepeatOptions`, `SetNlsOptions`, and `StartTime`.</span></span><br /><br /> <span data-ttu-id="e4456-113">-`ContinueOnFail`参数指示是否应继续还是中引发异常用例的父参数集提交请求 (`SetRelClassOptions`， `SetPrintOptions`，`SetRepeatOptions`或`SetNlsOptions`) 失败。</span><span class="sxs-lookup"><span data-stu-id="e4456-113">- The `ContinueOnFail` parameter indicates whether the request set submission should continue or throw an exception in case the parent parameter (`SetRelClassOptions`, `SetPrintOptions`, `SetRepeatOptions` or `SetNlsOptions`) fails.</span></span> <span data-ttu-id="e4456-114">您可以指定 **，则返回 True** （继续） 或**False** （引发异常）。</span><span class="sxs-lookup"><span data-stu-id="e4456-114">You can specify **True** (continue) or **False** (throw an exception).</span></span><br /><br /> <span data-ttu-id="e4456-115">-对于每个参数的详细信息，请参阅[请求集的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="e4456-115">- For detailed information about each parameter, see [Operations on Request Sets](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).</span></span>|  
|<span data-ttu-id="e4456-116">[Request_Set_Name]响应</span><span class="sxs-lookup"><span data-stu-id="e4456-116">[Request_Set_Name] Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name]Response xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]">   <[Request_Set_Name]Result>[value]</[Request_Set_Name]Result> </[Request_Set_Name]Response>`|<span data-ttu-id="e4456-117">来自 Oracle E-business Suite 的响应包含并发请求 id。</span><span class="sxs-lookup"><span data-stu-id="e4456-117">The response from Oracle E-Business Suite contains a concurrent request ID.</span></span>|  
  
 <span data-ttu-id="e4456-118">实体说明：</span><span class="sxs-lookup"><span data-stu-id="e4456-118">Entity descriptions:</span></span>  
  
 <span data-ttu-id="e4456-119">[VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05</span><span class="sxs-lookup"><span data-stu-id="e4456-119">[VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05</span></span>  
  
 <span data-ttu-id="e4456-120">.</span><span class="sxs-lookup"><span data-stu-id="e4456-120">.</span></span>  
  
 <span data-ttu-id="e4456-121">[CONCURRENT_PROGRAM_NAME] = 请求集中包含的并发程序。</span><span class="sxs-lookup"><span data-stu-id="e4456-121">[CONCURRENT_PROGRAM_NAME] = Concurrent program included in the request set.</span></span>  
  
## <a name="message-actions-for-request-sets"></a><span data-ttu-id="e4456-122">请求集的消息操作</span><span class="sxs-lookup"><span data-stu-id="e4456-122">Message Actions for Request Sets</span></span>  
 <span data-ttu-id="e4456-123">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]请求集的使用以下的消息操作。</span><span class="sxs-lookup"><span data-stu-id="e4456-123">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses the following message actions for request sets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4456-124">实体说明表后进行查看。</span><span class="sxs-lookup"><span data-stu-id="e4456-124">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="e4456-125">消息</span><span class="sxs-lookup"><span data-stu-id="e4456-125">Message</span></span>|<span data-ttu-id="e4456-126">操作</span><span class="sxs-lookup"><span data-stu-id="e4456-126">Action</span></span>|<span data-ttu-id="e4456-127">示例</span><span class="sxs-lookup"><span data-stu-id="e4456-127">Example</span></span>|  
|-------------|------------|-------------|  
|<span data-ttu-id="e4456-128">请求集请求</span><span class="sxs-lookup"><span data-stu-id="e4456-128">Request Set request</span></span>|<span data-ttu-id="e4456-129">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]</span><span class="sxs-lookup"><span data-stu-id="e4456-129">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]</span></span>|<span data-ttu-id="e4456-130">RequestSets/SQLGL/FNDRSSUB965</span><span class="sxs-lookup"><span data-stu-id="e4456-130">RequestSets/SQLGL/FNDRSSUB965</span></span>|  
|<span data-ttu-id="e4456-131">请求集响应</span><span class="sxs-lookup"><span data-stu-id="e4456-131">Request Set response</span></span>|<span data-ttu-id="e4456-132">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]]/response</span><span class="sxs-lookup"><span data-stu-id="e4456-132">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]]/response</span></span>|<span data-ttu-id="e4456-133">RequestSets/SQLGL/FNDRSSUB965/response</span><span class="sxs-lookup"><span data-stu-id="e4456-133">RequestSets/SQLGL/FNDRSSUB965/response</span></span>|  
  
 <span data-ttu-id="e4456-134">实体说明：</span><span class="sxs-lookup"><span data-stu-id="e4456-134">Entity descriptions:</span></span>  
  
 <span data-ttu-id="e4456-135">[APP_SHORT_NAME] = 应用程序的短名称。</span><span class="sxs-lookup"><span data-stu-id="e4456-135">[APP_SHORT_NAME] = Application short name.</span></span>  
  
 <span data-ttu-id="e4456-136">[REQUESTSET_SHORT_NAME] = 请求设置短名称。</span><span class="sxs-lookup"><span data-stu-id="e4456-136">[REQUESTSET_SHORT_NAME] = Request Set short name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4456-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4456-137">See Also</span></span>  
 [<span data-ttu-id="e4456-138">消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="e4456-138">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)