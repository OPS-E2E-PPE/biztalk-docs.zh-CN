---
title: "BAPI 操作的消息架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAPI operations, message schemas for
- BAPI operations, message structure for
- BAPI operations, message actions for
ms.assetid: ef4d88e8-f31a-4b68-a303-6885b6f8c083
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 999e60a7e2cac827031ea2a19f9482d9da0baaa6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-bapi-operations"></a><span data-ttu-id="56207-102">BAPI 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="56207-102">Message Schemas for BAPI Operations</span></span>
<span data-ttu-id="56207-103">下列各节描述的消息架构和消息操作用于调用 BAPIs[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]作为业务对象的方法。</span><span class="sxs-lookup"><span data-stu-id="56207-103">The following sections describe the message schemas and message actions used to invoke BAPIs on the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as methods of business objects.</span></span> <span data-ttu-id="56207-104">你也可以作为在适配器上的 RFC 操作调用 BAPIs。</span><span class="sxs-lookup"><span data-stu-id="56207-104">You can also invoke BAPIs as RFC operations on the adapter.</span></span> <span data-ttu-id="56207-105">有关用来调用 Rfc 的消息的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="56207-105">For more information about the messages used to invoke RFCs, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span> <span data-ttu-id="56207-106">而不考虑如何在适配器上的 BAPI 调用时，适配器始终作为 SAP 系统上 RFC 调用 BAPI。</span><span class="sxs-lookup"><span data-stu-id="56207-106">Regardless of how you invoke a BAPI on the adapter, the adapter always invokes the BAPI as an RFC on the SAP system.</span></span> <span data-ttu-id="56207-107">有关如何概述[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 BAPIs，请参阅[对 BAPIs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="56207-107">For an overview of how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports BAPIs, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
## <a name="message-structure-for-business-object-operations"></a><span data-ttu-id="56207-108">业务对象操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="56207-108">Message Structure for Business Object Operations</span></span>  
 <span data-ttu-id="56207-109">下表显示用于调用 BAPI 作为业务对象方法的消息架构。</span><span class="sxs-lookup"><span data-stu-id="56207-109">The following table shows the message schemas used to invoke a BAPI as a business object method.</span></span>  
  
|<span data-ttu-id="56207-110">运算</span><span class="sxs-lookup"><span data-stu-id="56207-110">Operation</span></span>|<span data-ttu-id="56207-111">XML 结构</span><span class="sxs-lookup"><span data-stu-id="56207-111">XML Structure</span></span>|<span data-ttu-id="56207-112">Description</span><span class="sxs-lookup"><span data-stu-id="56207-112">Description</span></span>|  
|---------------|-------------------|-----------------|  
|<span data-ttu-id="56207-113">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="56207-113">[BUSOBJ_METHOD]</span></span>|`<[BUSOBJ_METHOD] xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]>`|<span data-ttu-id="56207-114">调用上的 SAP 系统的业务对象方法。</span><span class="sxs-lookup"><span data-stu-id="56207-114">Invoke a business object method on an SAP system.</span></span><br /><br /> <span data-ttu-id="56207-115">支持导入、 更改和表参数。</span><span class="sxs-lookup"><span data-stu-id="56207-115">Import, changing, and table parameters are supported.</span></span>|  
|<span data-ttu-id="56207-116">[BUSOBJ_METHOD]响应</span><span class="sxs-lookup"><span data-stu-id="56207-116">[BUSOBJ_METHOD] Response</span></span>|`<[BUSOBJ_METHOD]Response xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]Response>`|<span data-ttu-id="56207-117">业务对象方法响应。</span><span class="sxs-lookup"><span data-stu-id="56207-117">Business object method response.</span></span><br /><br /> <span data-ttu-id="56207-118">导出、 更改，并支持表参数。</span><span class="sxs-lookup"><span data-stu-id="56207-118">Export, changing, and table parameters are supported.</span></span><br /><br /> <span data-ttu-id="56207-119">**请注意**默认情况下，表参数不显示在响应消息中。</span><span class="sxs-lookup"><span data-stu-id="56207-119">**Note** By default, table parameters are not surfaced in the response message.</span></span> <span data-ttu-id="56207-120">如果你需要在响应消息中的表参数，你必须在请求消息中传递空表参数。</span><span class="sxs-lookup"><span data-stu-id="56207-120">If you require table parameters in response message, you must pass empty table parameters in the request message.</span></span>|  
  
 <span data-ttu-id="56207-121">[VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.Sap/2007/03。</span><span class="sxs-lookup"><span data-stu-id="56207-121">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  
  
 <span data-ttu-id="56207-122">[BUSOBJ_METHOD] = 业务对象方法; 的名称例如，CREATEFROMDAT2。</span><span class="sxs-lookup"><span data-stu-id="56207-122">[BUSOBJ_METHOD] = The name of a business object method; for example, CREATEFROMDAT2.</span></span>  
  
 <span data-ttu-id="56207-123">[IN_PARAM_NAME] = BAPI 导入参数的名称。</span><span class="sxs-lookup"><span data-stu-id="56207-123">[IN_PARAM_NAME] =The name of a BAPI import parameter.</span></span>  
  
 <span data-ttu-id="56207-124">[OUT_PARAM_NAME] = BAPI 导出参数的名称。</span><span class="sxs-lookup"><span data-stu-id="56207-124">[OUT_PARAM_NAME] = The name of a BAPI export parameter.</span></span>  
  
 <span data-ttu-id="56207-125">[INOUT_PARAM_NAME] = BAPI 更改参数的名称。</span><span class="sxs-lookup"><span data-stu-id="56207-125">[INOUT_PARAM_NAME] = The name of a BAPI changing parameter.</span></span>  
  
 <span data-ttu-id="56207-126">[TABLE_PARAM_NAME] = BAPI 表参数的名称。</span><span class="sxs-lookup"><span data-stu-id="56207-126">[TABLE_PARAM_NAME] = The name of a BAPI table parameter.</span></span>  
  
 <span data-ttu-id="56207-127">[STRUCT_PARAM_NAME] = BAPI 结构参数的名称。</span><span class="sxs-lookup"><span data-stu-id="56207-127">[STRUCT_PARAM_NAME] = The name of a BAPI structure parameter.</span></span>  
  
## <a name="message-actions-for-business-object-operations"></a><span data-ttu-id="56207-128">业务对象操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="56207-128">Message Actions for Business Object Operations</span></span>  
 <span data-ttu-id="56207-129">下表显示用于调用 BAPIs 作为业务对象方法的消息操作。</span><span class="sxs-lookup"><span data-stu-id="56207-129">The following table shows the message actions that are used to invoke BAPIs as business object methods.</span></span>  
  
|<span data-ttu-id="56207-130">运算</span><span class="sxs-lookup"><span data-stu-id="56207-130">Operation</span></span>|<span data-ttu-id="56207-131">消息操作</span><span class="sxs-lookup"><span data-stu-id="56207-131">Message Action</span></span>|<span data-ttu-id="56207-132">示例</span><span class="sxs-lookup"><span data-stu-id="56207-132">Example</span></span>|  
|---------------|--------------------|-------------|  
|<span data-ttu-id="56207-133">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="56207-133">[BUSOBJ_METHOD]</span></span>|<span data-ttu-id="56207-134">[VERSION] /Bapi/ [BUSOBJ_NAME] / [BUSOBJ_METHOD] / [BAPI_RFC_NAME]</span><span class="sxs-lookup"><span data-stu-id="56207-134">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]</span></span>|<span data-ttu-id="56207-135">http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2</span><span class="sxs-lookup"><span data-stu-id="56207-135">http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2</span></span>|  
|<span data-ttu-id="56207-136">[BUSOBJ_METHOD]响应</span><span class="sxs-lookup"><span data-stu-id="56207-136">[BUSOBJ_METHOD] Response</span></span>|<span data-ttu-id="56207-137">[VERSION] /Bapi/ [BUSOBJ_NAME] / [BUSOBJ_METHOD] / [BAPI_RFC_NAME] / 响应</span><span class="sxs-lookup"><span data-stu-id="56207-137">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]/response</span></span>|<span data-ttu-id="56207-138">http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/response</span><span class="sxs-lookup"><span data-stu-id="56207-138">http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/response</span></span>|  
  
 <span data-ttu-id="56207-139">[VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.Sap/2007/03。</span><span class="sxs-lookup"><span data-stu-id="56207-139">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  
  
 <span data-ttu-id="56207-140">[BUSOBJ_NAME] = 业务对象中; 的名称例如，BUS2032。</span><span class="sxs-lookup"><span data-stu-id="56207-140">[BUSOBJ_NAME] = The name of the business object; for example, BUS2032.</span></span>  
  
 <span data-ttu-id="56207-141">[BUSOBJ_METHOD] = 业务对象中; 的方法例如，CREATEFROMDAT2。</span><span class="sxs-lookup"><span data-stu-id="56207-141">[BUSOBJ_METHOD] = The method of the business object; for example, CREATEFROMDAT2.</span></span>  
  
 <span data-ttu-id="56207-142">[BAPI_RFC_NAME] = BAPI; RFC 名称例如，BAPI_SALESORDER_CREATEFROMDAT2。</span><span class="sxs-lookup"><span data-stu-id="56207-142">[BAPI_RFC_NAME] = The RFC name for the BAPI; for example, BAPI_SALESORDER_CREATEFROMDAT2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56207-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56207-143">See Also</span></span>  
 [<span data-ttu-id="56207-144">消息和用于 mySAP Business Suite 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="56207-144">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)