---
title: "消息和消息架构用于 Siebel eBusiness Applications 的 BizTalk Adapter |Microsoft 文档"
description: "Siebel 适配器 BizTalk 适配器包 (BAP) 中使用的消息和数据类型的 XML 结构"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b4da884-89b0-4ab1-a728-c5569088a993
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 294662793fc8103813b582d1b0d84db4447b0e7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="e447b-103">消息和用于 Siebel eBusiness Applications 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="e447b-103">Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications</span></span>

## <a name="overview"></a><span data-ttu-id="e447b-104">概述</span><span class="sxs-lookup"><span data-stu-id="e447b-104">Overview</span></span>
<span data-ttu-id="e447b-105">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="e447b-105">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="e447b-106">它公开应用程序可以调用 Siebel 系统的操作。</span><span class="sxs-lookup"><span data-stu-id="e447b-106">It exposes operations that applications can invoke on a Siebel system.</span></span> <span data-ttu-id="e447b-107">这些操作都是通过在通道上发送 SOAP 消息中调用。</span><span class="sxs-lookup"><span data-stu-id="e447b-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="e447b-108">如果需要响应，它将通过相同的通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="e447b-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="e447b-109">作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。</span><span class="sxs-lookup"><span data-stu-id="e447b-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="e447b-110">本主题中的各节描述了消息的 XML 结构和数据类型，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="e447b-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e447b-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="e447b-111">In This Section</span></span>  
  
-   [<span data-ttu-id="e447b-112">基本 Siebel 数据类型</span><span class="sxs-lookup"><span data-stu-id="e447b-112">Basic Siebel Data Types</span></span>](basic-siebel-data-types.md)  
  
-   [<span data-ttu-id="e447b-113">业务组件操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="e447b-113">Message Schemas for Business Component Operations</span></span>](message-schemas-for-business-component-operations.md)  
  
-   [<span data-ttu-id="e447b-114">业务服务操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="e447b-114">Message Schemas for Business Service Operations</span></span>](message-schemas-for-business-service-operations.md)  
  
-   [<span data-ttu-id="e447b-115">选择列表操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="e447b-115">Message Schema for Picklist Operations</span></span>](message-schema-for-picklist-operations.md)  
  
-   [<span data-ttu-id="e447b-116">消息版本控制支持</span><span class="sxs-lookup"><span data-stu-id="e447b-116">Message Versioning Support</span></span>](message-versioning-support2.md)  
  
