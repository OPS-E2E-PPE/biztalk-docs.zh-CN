---
title: "适用于 SAP 适配器客户端的功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic ports
- adapters, features
- XML data streaming
- performance counters
- adapters, support for dynamic ports in BizTalk Server
- adapters, support for message versioning
- adapters, support for XML data streaming
- adapters, support for performance counters
- adapters, support for configuring adapters using binding properties
ms.assetid: 9003c2c1-931d-405e-9a58-660032195af7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6516ff99f599d02cdf27aa7c0c07752747749021
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="features-for-sap-adapter-clients"></a><span data-ttu-id="d44ec-102">适用于 SAP 适配器客户端的功能</span><span class="sxs-lookup"><span data-stu-id="d44ec-102">Features for SAP adapter clients</span></span>
<span data-ttu-id="d44ec-103">除了对在的主题中讨论的功能[为 mySAP Business Suite 的 BizTalk Adapter 的体系结构概述](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还提供了以下功能，可用于适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="d44ec-103">In addition to the features discussed throughout the topics of [Architecture overview of BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md), the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] also provides the following features that are useful for adapter clients.</span></span>  
  
-   <span data-ttu-id="d44ec-104">**配置使用绑定属性的适配器的支持**。</span><span class="sxs-lookup"><span data-stu-id="d44ec-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="d44ec-105">适配器客户端可以配置[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过指定特定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="d44ec-105">Adapter clients can configure the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="d44ec-106">例如，客户端可以配置适配器后，若要通过指定的值指定适配器的连接池中的最大连接数**MaxConnectionsPerSystem**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="d44ec-106">For example, clients can configure the adapter to specify the maximum number of connections in the adapter's connection pool by specifying a value for the **MaxConnectionsPerSystem** binding property.</span></span> <span data-ttu-id="d44ec-107">有关详细信息，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d44ec-107">For more information, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
-   <span data-ttu-id="d44ec-108">**BizTalk Server 中的动态端口支持**。</span><span class="sxs-lookup"><span data-stu-id="d44ec-108">**Support for dynamic ports in BizTalk Server**.</span></span> <span data-ttu-id="d44ec-109">通过 BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持动态端口，使动态路由的消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]基于消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="d44ec-109">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="d44ec-110">有关详细信息，请参阅[配置动态端口](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d44ec-110">For more information, see [Configure dynamic ports](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md).</span></span>
  
-   <span data-ttu-id="d44ec-111">**对消息版本管理的支持**。</span><span class="sxs-lookup"><span data-stu-id="d44ec-111">**Support for message versioning**.</span></span> <span data-ttu-id="d44ec-112">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持将消息版本控制以启用对不同的消息架构的将来版本中支持[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d44ec-112">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports message versioning to enable support for different message schemas in future releases of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="d44ec-113">有关详细信息，请参阅[消息版本控制支持](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)。</span><span class="sxs-lookup"><span data-stu-id="d44ec-113">For more information, see [Message Versioning Support](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d44ec-114">此功能不提供与早期版本的适配器的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="d44ec-114">This feature does not provide backward compatibility with the earlier versions of the adapter.</span></span>  
  
-   <span data-ttu-id="d44ec-115">**对性能计数器支持**。</span><span class="sxs-lookup"><span data-stu-id="d44ec-115">**Support for performance counters**.</span></span> <span data-ttu-id="d44ec-116">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以适配器客户端使用支持基于 WCF 的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="d44ec-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports WCF-based performance counters for use by adapter clients.</span></span> <span data-ttu-id="d44ec-117">有关性能计数器的详细信息，请参阅[使用性能计数器与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d44ec-117">For more information about performance counters, see [Use Performance Counters with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44ec-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d44ec-118">See Also</span></span>  
 [<span data-ttu-id="d44ec-119">为 mySAP Business Suite 的 BizTalk Adapter 的体系结构概述</span><span class="sxs-lookup"><span data-stu-id="d44ec-119">Architecture overview of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)