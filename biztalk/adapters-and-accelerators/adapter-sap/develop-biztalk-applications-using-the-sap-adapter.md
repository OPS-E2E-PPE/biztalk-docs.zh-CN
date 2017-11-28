---
title: "开发使用 SAP 适配器的 BizTalk 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
ms.assetid: 4aa10897-a08e-4fc3-9c1f-40485d204273
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75e70a52f12227b1bde3a43f9330c6fe373ac5a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-sap-adapter"></a><span data-ttu-id="3e513-102">开发使用 SAP 适配器的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="3e513-102">Develop BizTalk applications using the SAP adapter</span></span>
<span data-ttu-id="3e513-103">开发 BizTalk 应用程序涉及到创建中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="3e513-103">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate XML schema.</span></span> <span data-ttu-id="3e513-104">一旦你已生成架构，你可以使用基于内容的路由 (CBR)，或创建 BizTalk 业务流程，以发送和接收符合生成架构的消息。</span><span class="sxs-lookup"><span data-stu-id="3e513-104">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to the generated schema.</span></span>  
  
 <span data-ttu-id="3e513-105">CBR 可以用于的方案发送到 SAP 系统的消息不需要任何密集型处理。</span><span class="sxs-lookup"><span data-stu-id="3e513-105">CBR can be used in scenarios where the messages being sent to the SAP system do not require any intensive processing.</span></span> <span data-ttu-id="3e513-106">例如，如果你知道接收端口将接收仅特定类型的消息，可以将筛选器添加到要将路由到发送端口筛选器表达式匹配的消息的发送端口中。</span><span class="sxs-lookup"><span data-stu-id="3e513-106">For example, if you know that the receive port will be receiving messages only of a certain type, you can add a filter to the send port to route the messages matching the filter expression to the send port.</span></span>  
  
 <span data-ttu-id="3e513-107">在 BizTalk 业务流程中创建发送和接收端口发送和接收消息，并从[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这反过来将消息发送到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3e513-107">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3e513-108">本部分提供有关使用 BizTalk 业务流程执行对 SAP 系统使用的操作的信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3e513-108">This section provides information about using BizTalk orchestrations to perform operations on the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="3e513-109">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]反过来使用[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]与 WCF 绑定可以交互的适配器。</span><span class="sxs-lookup"><span data-stu-id="3e513-109">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] adapter that can interact with a WCF binding.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3e513-110">若要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，始终必须设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。</span><span class="sxs-lookup"><span data-stu-id="3e513-110">To use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="3e513-111">有关如何设置绑定属性的信息，请参阅[配置 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="3e513-111">For information about how to set binding properties, see [Configure the binding properties for the SAP adapter](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e513-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="3e513-112">In This Section</span></span>  
  
-   [<span data-ttu-id="3e513-113">若要创建的 SAP 应用程序的先决条件</span><span class="sxs-lookup"><span data-stu-id="3e513-113">Prerequisites to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
-   [<span data-ttu-id="3e513-114">若要创建的 SAP 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="3e513-114">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)
  
-   [<span data-ttu-id="3e513-115">调用中使用 BizTalk Server SAP Rfc</span><span class="sxs-lookup"><span data-stu-id="3e513-115">Invoke RFCs in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="3e513-116">接收来自 SAP 使用 BizTalk Server 的入站 RFC 调用</span><span class="sxs-lookup"><span data-stu-id="3e513-116">Receive Inbound RFC Calls from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="3e513-117">调用 tRFCs SAP 使用 BizTalk Server 中</span><span class="sxs-lookup"><span data-stu-id="3e513-117">Invoke tRFCs in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="3e513-118">从 SAP 使用 BizTalk Server 接收入站的 tRFC 调用</span><span class="sxs-lookup"><span data-stu-id="3e513-118">Receive Inbound tRFC Calls from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="3e513-119">SAP 使用 BizTalk Server 中运行 BAPI 事务</span><span class="sxs-lookup"><span data-stu-id="3e513-119">Run BAPI Transactions in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="3e513-120">将 Idoc 发送到 SAP 使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3e513-120">Send IDOCs to SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="3e513-121">从 SAP 使用 BizTalk Server 接收到的 Idoc</span><span class="sxs-lookup"><span data-stu-id="3e513-121">Receive IDOCs from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="3e513-122">从 SAP 使用 BizTalk Server 的事务上下文中接收到的 Idoc</span><span class="sxs-lookup"><span data-stu-id="3e513-122">Receive IDOCs from SAP in a Transactional Context using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="3e513-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e513-123">See Also</span></span>  
[<span data-ttu-id="3e513-124">开发您的 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="3e513-124">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)