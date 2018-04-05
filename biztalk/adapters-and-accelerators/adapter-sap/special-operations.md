---
title: 特殊操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, special operations surfaced by the SAP adapter
ms.assetid: 8725fe63-6ff4-49c8-b386-d4c67e2be440
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe2472d905e9e726b827d44da79bdfe840233354
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="special-operations"></a><span data-ttu-id="45a0a-102">特殊的操作</span><span class="sxs-lookup"><span data-stu-id="45a0a-102">Special Operations</span></span>
<span data-ttu-id="45a0a-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现几个特殊操作。</span><span class="sxs-lookup"><span data-stu-id="45a0a-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces several special operations.</span></span> <span data-ttu-id="45a0a-104">这些操作不基于 SAP 系统项目的影响。</span><span class="sxs-lookup"><span data-stu-id="45a0a-104">These operations are not based on SAP system artifacts.</span></span> <span data-ttu-id="45a0a-105">它们将显示为适配器客户端应用程序提供功能。</span><span class="sxs-lookup"><span data-stu-id="45a0a-105">They are surfaced to provide functionality for adapter client applications.</span></span> <span data-ttu-id="45a0a-106">进行的特殊操作：</span><span class="sxs-lookup"><span data-stu-id="45a0a-106">The special operations are:</span></span>  
  
-   <span data-ttu-id="45a0a-107">**RfcGetAttributes**。</span><span class="sxs-lookup"><span data-stu-id="45a0a-107">**RfcGetAttributes**.</span></span> <span data-ttu-id="45a0a-108">此操作在 RFC 节点下显示，并公开的 RFC sdk 的功能。</span><span class="sxs-lookup"><span data-stu-id="45a0a-108">This operation is surfaced under the RFC node and exposes functionality of the RFC SDK.</span></span> <span data-ttu-id="45a0a-109">它提供有关 RFC 连接的以下信息：</span><span class="sxs-lookup"><span data-stu-id="45a0a-109">It provides the following information about the RFC connection:</span></span>  
  
    -   <span data-ttu-id="45a0a-110">系统 ID</span><span class="sxs-lookup"><span data-stu-id="45a0a-110">The system ID</span></span>  
  
    -   <span data-ttu-id="45a0a-111">合作伙伴代码页</span><span class="sxs-lookup"><span data-stu-id="45a0a-111">The partner code page</span></span>  
  
    -   <span data-ttu-id="45a0a-112">语言</span><span class="sxs-lookup"><span data-stu-id="45a0a-112">The language</span></span>  
  
     <span data-ttu-id="45a0a-113">有关包括其消息架构 RfcGetAttributes 操作的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="45a0a-113">For more information about the RfcGetAttributes operation including its message schema, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
-   <span data-ttu-id="45a0a-114">**RfcConfirmTransID**。</span><span class="sxs-lookup"><span data-stu-id="45a0a-114">**RfcConfirmTransID**.</span></span> <span data-ttu-id="45a0a-115">此操作在 TRFC 节点下显示，并公开 RFC SDK 功能。</span><span class="sxs-lookup"><span data-stu-id="45a0a-115">This operation is surfaced under the TRFC node and exposes RFC SDK functionality.</span></span> <span data-ttu-id="45a0a-116">你可以使用此操作以确认 SAP 系统上的 SAP 事务 Id。</span><span class="sxs-lookup"><span data-stu-id="45a0a-116">You use this operation to confirm SAP transaction IDs on the SAP system.</span></span>  
  
     <span data-ttu-id="45a0a-117">有关如何使用 RfcConfirmTransID 操作和有关其消息架构，请参阅详细信息[对 tRFCs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="45a0a-117">For more information about how to use the RfcConfirmTransID operation and about its message schema, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
-   <span data-ttu-id="45a0a-118">**字符串 SapAdapterUtilities.ConvertGuidToTid(Guid)**。</span><span class="sxs-lookup"><span data-stu-id="45a0a-118">**string SapAdapterUtilities.ConvertGuidToTid(Guid)**.</span></span> <span data-ttu-id="45a0a-119">这是由 SAP 适配器程序集公开的公共方法。</span><span class="sxs-lookup"><span data-stu-id="45a0a-119">This is a public method exposed by the SAP adapter assembly.</span></span> <span data-ttu-id="45a0a-120">（不是适配器中加以表示的操作。）它将返回 SAP 事务 ID (TID) 映射到指定的 GUID。</span><span class="sxs-lookup"><span data-stu-id="45a0a-120">(It is not an operation surfaced by the adapter.) It returns the SAP transaction ID (TID) mapped to the specified GUID.</span></span>  
  
     <span data-ttu-id="45a0a-121">在内部，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]映射为 GUID SAP 系统上的 SAP 事务 ID (TID) 标识的工作 (LUW) 逻辑单元。</span><span class="sxs-lookup"><span data-stu-id="45a0a-121">Internally, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] maps the SAP transaction ID (TID) that identifies a logical unit of work (LUW) on the SAP system to a GUID.</span></span> <span data-ttu-id="45a0a-122">此 GUID 是向适配器客户端公开，以便他们可以承诺 tRFC (LUW) 通过调用 RfcConfirmTransID 操作，以确认其 TID SAP 系统上。</span><span class="sxs-lookup"><span data-stu-id="45a0a-122">This GUID is exposed to adapter clients, so that they can commit a tRFC (LUW) by invoking the RfcConfirmTransID operation to confirm its TID on the SAP system.</span></span>  
  
     <span data-ttu-id="45a0a-123">但是，在某些情况下，你可能需要与 tRFC 关联 TID。</span><span class="sxs-lookup"><span data-stu-id="45a0a-123">However, for some scenarios, you may need the TID that is associated with a tRFC.</span></span> <span data-ttu-id="45a0a-124">例如，你可能想要确定 SAP 系统上的 LUW，以解决问题。</span><span class="sxs-lookup"><span data-stu-id="45a0a-124">For example, you may want to identify the LUW on the SAP system to troubleshoot an issue.</span></span> <span data-ttu-id="45a0a-125">对于这些情况你可以调用**ConvertGuidToTid**。</span><span class="sxs-lookup"><span data-stu-id="45a0a-125">For these scenarios you can call **ConvertGuidToTid**.</span></span> <span data-ttu-id="45a0a-126">若要使用**ConvertGuidToTid**在代码中，你必须将 SAP 适配器程序集的引用添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="45a0a-126">To use **ConvertGuidToTid** in your code, you must add a reference to the SAP adapter assembly to your project.</span></span>  
  
     <span data-ttu-id="45a0a-127">有关调用 tRFCs 的详细信息，请参阅[对 tRFCs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="45a0a-127">For more information about invoking tRFCs, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span> <span data-ttu-id="45a0a-128">下面的示例演示如何调用**ConvertGuidToTid**。</span><span class="sxs-lookup"><span data-stu-id="45a0a-128">The following example shows how to invoke **ConvertGuidToTid**.</span></span>  
  
    ```  
    // messageGuid is the GUID associated with a tRFC or IDOC  
  
    string tid = SapAdapterUtilities.ConvertGuidToTid(messageGuid);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="45a0a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45a0a-129">See Also</span></span>  
 [<span data-ttu-id="45a0a-130">消息和用于 mySAP Business Suite 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="45a0a-130">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)