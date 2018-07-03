---
title: BAPI 操作的消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI operations, message schemas for
- BAPI operations, message structure for
- BAPI operations, message actions for
ms.assetid: ef4d88e8-f31a-4b68-a303-6885b6f8c083
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 796e7beb428e6f9a4f0df63eff9cf45e9d5410bb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995214"
---
# <a name="message-schemas-for-bapi-operations"></a><span data-ttu-id="c89ae-102">BAPI 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="c89ae-102">Message Schemas for BAPI Operations</span></span>
<span data-ttu-id="c89ae-103">以下各节介绍的消息架构和消息操作用于在调用 Bapi[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]作为业务对象的方法。</span><span class="sxs-lookup"><span data-stu-id="c89ae-103">The following sections describe the message schemas and message actions used to invoke BAPIs on the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as methods of business objects.</span></span> <span data-ttu-id="c89ae-104">此外可以在适配器上的 RFC 操作作为调用 Bapi。</span><span class="sxs-lookup"><span data-stu-id="c89ae-104">You can also invoke BAPIs as RFC operations on the adapter.</span></span> <span data-ttu-id="c89ae-105">有关用于调用 Rfc 的消息的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="c89ae-105">For more information about the messages used to invoke RFCs, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span> <span data-ttu-id="c89ae-106">无论调用在适配器上的 BAPI 的方式，该适配器始终为 SAP 系统上的 RFC 调用 BAPI。</span><span class="sxs-lookup"><span data-stu-id="c89ae-106">Regardless of how you invoke a BAPI on the adapter, the adapter always invokes the BAPI as an RFC on the SAP system.</span></span> <span data-ttu-id="c89ae-107">有关如何概述[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 Bapi，请参阅[sap Bapi 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="c89ae-107">For an overview of how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports BAPIs, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  

## <a name="message-structure-for-business-object-operations"></a><span data-ttu-id="c89ae-108">对业务对象操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="c89ae-108">Message Structure for Business Object Operations</span></span>  
 <span data-ttu-id="c89ae-109">下表显示了用于调用 BAPI 作为业务对象方法的消息架构。</span><span class="sxs-lookup"><span data-stu-id="c89ae-109">The following table shows the message schemas used to invoke a BAPI as a business object method.</span></span>  

|<span data-ttu-id="c89ae-110">运算</span><span class="sxs-lookup"><span data-stu-id="c89ae-110">Operation</span></span>|<span data-ttu-id="c89ae-111">XML 结构</span><span class="sxs-lookup"><span data-stu-id="c89ae-111">XML Structure</span></span>|<span data-ttu-id="c89ae-112">Description</span><span class="sxs-lookup"><span data-stu-id="c89ae-112">Description</span></span>|  
|---------------|-------------------|-----------------|  
|<span data-ttu-id="c89ae-113">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="c89ae-113">[BUSOBJ_METHOD]</span></span>|`<[BUSOBJ_METHOD] xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]>`|<span data-ttu-id="c89ae-114">调用上的 SAP 系统的业务对象方法。</span><span class="sxs-lookup"><span data-stu-id="c89ae-114">Invoke a business object method on an SAP system.</span></span><br /><br /> <span data-ttu-id="c89ae-115">支持导入、 更改和表参数。</span><span class="sxs-lookup"><span data-stu-id="c89ae-115">Import, changing, and table parameters are supported.</span></span>|  
|<span data-ttu-id="c89ae-116">[BUSOBJ_METHOD]响应</span><span class="sxs-lookup"><span data-stu-id="c89ae-116">[BUSOBJ_METHOD] Response</span></span>|`<[BUSOBJ_METHOD]Response xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]Response>`|<span data-ttu-id="c89ae-117">业务对象方法响应。</span><span class="sxs-lookup"><span data-stu-id="c89ae-117">Business object method response.</span></span><br /><br /> <span data-ttu-id="c89ae-118">导出，更改，并支持表参数。</span><span class="sxs-lookup"><span data-stu-id="c89ae-118">Export, changing, and table parameters are supported.</span></span><br /><br /> <span data-ttu-id="c89ae-119">**请注意**默认情况下，表参数不显示在响应消息。</span><span class="sxs-lookup"><span data-stu-id="c89ae-119">**Note** By default, table parameters are not surfaced in the response message.</span></span> <span data-ttu-id="c89ae-120">如果您需要在响应消息中的表参数，您必须在请求消息中传递空表参数。</span><span class="sxs-lookup"><span data-stu-id="c89ae-120">If you require table parameters in response message, you must pass empty table parameters in the request message.</span></span>|  

 <span data-ttu-id="c89ae-121">[VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.Sap/2007/03。</span><span class="sxs-lookup"><span data-stu-id="c89ae-121">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  

 <span data-ttu-id="c89ae-122">[BUSOBJ_METHOD] = 业务对象方法; 的名称例如，CREATEFROMDAT2。</span><span class="sxs-lookup"><span data-stu-id="c89ae-122">[BUSOBJ_METHOD] = The name of a business object method; for example, CREATEFROMDAT2.</span></span>  

 <span data-ttu-id="c89ae-123">[IN_PARAM_NAME] = BAPI 导入参数的名称。</span><span class="sxs-lookup"><span data-stu-id="c89ae-123">[IN_PARAM_NAME] =The name of a BAPI import parameter.</span></span>  

 <span data-ttu-id="c89ae-124">[OUT_PARAM_NAME] = BAPI 导出参数的名称。</span><span class="sxs-lookup"><span data-stu-id="c89ae-124">[OUT_PARAM_NAME] = The name of a BAPI export parameter.</span></span>  

 <span data-ttu-id="c89ae-125">[INOUT_PARAM_NAME] = BAPI 更改参数的名称。</span><span class="sxs-lookup"><span data-stu-id="c89ae-125">[INOUT_PARAM_NAME] = The name of a BAPI changing parameter.</span></span>  

 <span data-ttu-id="c89ae-126">[TABLE_PARAM_NAME] = BAPI 表参数的名称。</span><span class="sxs-lookup"><span data-stu-id="c89ae-126">[TABLE_PARAM_NAME] = The name of a BAPI table parameter.</span></span>  

 <span data-ttu-id="c89ae-127">[STRUCT_PARAM_NAME] = BAPI 结构参数的名称。</span><span class="sxs-lookup"><span data-stu-id="c89ae-127">[STRUCT_PARAM_NAME] = The name of a BAPI structure parameter.</span></span>  

## <a name="message-actions-for-business-object-operations"></a><span data-ttu-id="c89ae-128">对业务对象操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="c89ae-128">Message Actions for Business Object Operations</span></span>  
 <span data-ttu-id="c89ae-129">下表显示了用于调用 Bapi 作为业务对象方法的消息操作。</span><span class="sxs-lookup"><span data-stu-id="c89ae-129">The following table shows the message actions that are used to invoke BAPIs as business object methods.</span></span>  


|        <span data-ttu-id="c89ae-130">运算</span><span class="sxs-lookup"><span data-stu-id="c89ae-130">Operation</span></span>         |                            <span data-ttu-id="c89ae-131">消息操作</span><span class="sxs-lookup"><span data-stu-id="c89ae-131">Message Action</span></span>                             |                                                   <span data-ttu-id="c89ae-132">示例</span><span class="sxs-lookup"><span data-stu-id="c89ae-132">Example</span></span>                                                    |
|--------------------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="c89ae-133">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="c89ae-133">[BUSOBJ_METHOD]</span></span>      |     <span data-ttu-id="c89ae-134">[VERSION] /Bapi/ [BUSOBJ_NAME] / [BUSOBJ_METHOD] / [BAPI_RFC_NAME]</span><span class="sxs-lookup"><span data-stu-id="c89ae-134">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]</span></span>      |     http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2      |
| <span data-ttu-id="c89ae-135">[BUSOBJ_METHOD]响应</span><span class="sxs-lookup"><span data-stu-id="c89ae-135">[BUSOBJ_METHOD] Response</span></span> | <span data-ttu-id="c89ae-136">[VERSION] /Bapi/ [BUSOBJ_NAME] / [BUSOBJ_METHOD] / [BAPI_RFC_NAME] / 响应</span><span class="sxs-lookup"><span data-stu-id="c89ae-136">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]/response</span></span> | http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/response |

 <span data-ttu-id="c89ae-137">[VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.Sap/2007/03。</span><span class="sxs-lookup"><span data-stu-id="c89ae-137">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  

 <span data-ttu-id="c89ae-138">[BUSOBJ_NAME] = 业务对象中; 的名称例如，BUS2032。</span><span class="sxs-lookup"><span data-stu-id="c89ae-138">[BUSOBJ_NAME] = The name of the business object; for example, BUS2032.</span></span>  

 <span data-ttu-id="c89ae-139">[BUSOBJ_METHOD] = 的业务对象; 方法例如，CREATEFROMDAT2。</span><span class="sxs-lookup"><span data-stu-id="c89ae-139">[BUSOBJ_METHOD] = The method of the business object; for example, CREATEFROMDAT2.</span></span>  

 <span data-ttu-id="c89ae-140">[BAPI_RFC_NAME] = BAPI; 的 RFC 名称例如，BAPI_SALESORDER_CREATEFROMDAT2。</span><span class="sxs-lookup"><span data-stu-id="c89ae-140">[BAPI_RFC_NAME] = The RFC name for the BAPI; for example, BAPI_SALESORDER_CREATEFROMDAT2.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c89ae-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="c89ae-141">See Also</span></span>  
 [<span data-ttu-id="c89ae-142">消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="c89ae-142">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)