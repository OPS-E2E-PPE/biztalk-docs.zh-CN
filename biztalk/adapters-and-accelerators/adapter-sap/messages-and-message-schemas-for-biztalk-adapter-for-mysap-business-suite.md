---
title: 消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器 |Microsoft Docs
description: 用于 mySAP 适配器通过 BizTalk Server 的消息和数据类型的 XML 结构
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ea5c27-8297-47bf-bcfd-503870349189
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 119fe8aea98266e0fcd3b26bff439b6136b3b755
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373221"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="88005-103">消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="88005-103">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>

## <a name="overview"></a><span data-ttu-id="88005-104">概述</span><span class="sxs-lookup"><span data-stu-id="88005-104">Overview</span></span>
<span data-ttu-id="88005-105">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="88005-105">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="88005-106">它公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。</span><span class="sxs-lookup"><span data-stu-id="88005-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="88005-107">通过通道发送 SOAP 消息来调用这些操作。</span><span class="sxs-lookup"><span data-stu-id="88005-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="88005-108">如果响应是必需的它通过同一通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="88005-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="88005-109">作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。</span><span class="sxs-lookup"><span data-stu-id="88005-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="88005-110">本主题中的部分描述的消息的 XML 结构和数据类型，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="88005-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88005-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="88005-111">In This Section</span></span>  
  
-   [<span data-ttu-id="88005-112">基本 SAP 数据类型</span><span class="sxs-lookup"><span data-stu-id="88005-112">Basic SAP Data Types</span></span>](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)  
  
-   [<span data-ttu-id="88005-113">自定义 RFC 的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="88005-113">Data Type Mapping for Custom RFCs</span></span>](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)  
  
-   [<span data-ttu-id="88005-114">IDOC 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="88005-114">Message Schemas for IDOC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)  
  
-   [<span data-ttu-id="88005-115">用于接收 IDOC 的消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="88005-115">Message Context Properties for Receiving IDOCs</span></span>](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md)  
  
-   [<span data-ttu-id="88005-116">RFC 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="88005-116">Message Schemas for RFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)  
  
-   [<span data-ttu-id="88005-117">tRFC 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="88005-117">Message Schemas for tRFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)  
  
-   [<span data-ttu-id="88005-118">BAPI 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="88005-118">Message Schemas for BAPI Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)  
  
-   [<span data-ttu-id="88005-119">特殊操作</span><span class="sxs-lookup"><span data-stu-id="88005-119">Special Operations</span></span>](../../adapters-and-accelerators/adapter-sap/special-operations.md)  
  
-   [<span data-ttu-id="88005-120">消息版本控制支持</span><span class="sxs-lookup"><span data-stu-id="88005-120">Message Versioning Support</span></span>](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)  
  
