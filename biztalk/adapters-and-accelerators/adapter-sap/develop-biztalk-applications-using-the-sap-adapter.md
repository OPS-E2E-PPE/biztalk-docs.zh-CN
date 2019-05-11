---
title: 开发使用 SAP 适配器的 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
ms.assetid: 4aa10897-a08e-4fc3-9c1f-40485d204273
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 508a1050cde10e8407121036ee6e6f1038b00eb9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373515"
---
# <a name="develop-biztalk-applications-using-the-sap-adapter"></a><span data-ttu-id="c9362-102">开发 BizTalk 应用程序使用 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="c9362-102">Develop BizTalk applications using the SAP adapter</span></span>
<span data-ttu-id="c9362-103">开发 BizTalk 应用程序涉及到创建的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="c9362-103">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate XML schema.</span></span> <span data-ttu-id="c9362-104">后生成架构后，你可以使用基于内容的路由 (CBR)，或创建 BizTalk 业务流程发送和接收符合所生成的架构的消息。</span><span class="sxs-lookup"><span data-stu-id="c9362-104">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to the generated schema.</span></span>  
  
 <span data-ttu-id="c9362-105">CBR 可以在发送到 SAP 系统的消息不需要任何密集型处理方案中使用。</span><span class="sxs-lookup"><span data-stu-id="c9362-105">CBR can be used in scenarios where the messages being sent to the SAP system do not require any intensive processing.</span></span> <span data-ttu-id="c9362-106">例如，如果您知道，将在接收端口接收消息仅特定类型的可以将筛选器添加到要将路由到发送端口筛选器表达式匹配的消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="c9362-106">For example, if you know that the receive port will be receiving messages only of a certain type, you can add a filter to the send port to route the messages matching the filter expression to the send port.</span></span>  
  
 <span data-ttu-id="c9362-107">BizTalk 业务流程中创建发送和接收端口以发送和接收消息来回[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，后者又将发送到消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c9362-107">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="c9362-108">本部分提供有关使用 BizTalk 业务流程执行对 SAP 系统使用的操作信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c9362-108">This section provides information about using BizTalk orchestrations to perform operations on the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="c9362-109">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]又使用[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]可以与 WCF 绑定的适配器。</span><span class="sxs-lookup"><span data-stu-id="c9362-109">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] adapter that can interact with a WCF binding.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9362-110">若要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你必须始终设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。</span><span class="sxs-lookup"><span data-stu-id="c9362-110">To use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="c9362-111">有关如何设置绑定属性的信息，请参阅[配置的 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="c9362-111">For information about how to set binding properties, see [Configure the binding properties for the SAP adapter](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9362-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="c9362-112">In This Section</span></span>  
  
-   [<span data-ttu-id="c9362-113">创建 SAP 应用程序的先决条件</span><span class="sxs-lookup"><span data-stu-id="c9362-113">Prerequisites to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
-   [<span data-ttu-id="c9362-114">生成块以创建 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="c9362-114">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)
  
-   [<span data-ttu-id="c9362-115">调用中使用 BizTalk Server 的 SAP Rfc</span><span class="sxs-lookup"><span data-stu-id="c9362-115">Invoke RFCs in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="c9362-116">接收来自 SAP 使用 BizTalk Server 的入站 RFC 调用</span><span class="sxs-lookup"><span data-stu-id="c9362-116">Receive Inbound RFC Calls from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="c9362-117">调用 Trfc SAP 使用 BizTalk Server 中</span><span class="sxs-lookup"><span data-stu-id="c9362-117">Invoke tRFCs in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="c9362-118">接收来自 SAP 使用 BizTalk Server 的入站的 tRFC 调用</span><span class="sxs-lookup"><span data-stu-id="c9362-118">Receive Inbound tRFC Calls from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="c9362-119">在 SAP 中使用 BizTalk Server 运行 BAPI 事务</span><span class="sxs-lookup"><span data-stu-id="c9362-119">Run BAPI Transactions in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="c9362-120">向使用 BizTalk Server 的 SAP 发送 Idoc</span><span class="sxs-lookup"><span data-stu-id="c9362-120">Send IDOCs to SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="c9362-121">接收来自使用 BizTalk Server 的 SAP 的 Idoc</span><span class="sxs-lookup"><span data-stu-id="c9362-121">Receive IDOCs from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="c9362-122">接收来自事务性上下文中使用 BizTalk Server 中的 SAP 的 Idoc</span><span class="sxs-lookup"><span data-stu-id="c9362-122">Receive IDOCs from SAP in a Transactional Context using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="c9362-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9362-123">See Also</span></span>  
[<span data-ttu-id="c9362-124">开发 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="c9362-124">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)