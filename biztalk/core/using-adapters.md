---
title: "使用适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: adapters
ms.assetid: afdfa70e-5929-4746-99b4-e76274aa5c88
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18ffc3c198cbd6fc26290908dfcc3a90b2c8a62a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-adapters"></a><span data-ttu-id="b08b7-102">使用适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-102">Using Adapters</span></span>
<span data-ttu-id="b08b7-103">本部分包含有关适配器的全面信息。</span><span class="sxs-lookup"><span data-stu-id="b08b7-103">This section contains comprehensive information about adapters.</span></span> <span data-ttu-id="b08b7-104">它描述如何在 Microsoft 中使用适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以及如何配置适配器处理程序、 发送端口和接收的每个适配器的位置。</span><span class="sxs-lookup"><span data-stu-id="b08b7-104">It describes how adapters are used in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and how to configure adapter handlers, send ports, and receive locations for each adapter.</span></span> <span data-ttu-id="b08b7-105">本部分还提供了批处理支持信息以帮助你理解本地适配器以及在 BizTalk 解决方案中使用本地适配器。</span><span class="sxs-lookup"><span data-stu-id="b08b7-105">It provides batching support information to help you understand and use the native adapters in your BizTalk solution.</span></span>  
  
 <span data-ttu-id="b08b7-106">有关使用用于适配器属性页的键盘快捷方式的信息，请参阅[适配器属性页键盘快捷方式](../core/adapter-property-page-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="b08b7-106">For information about using the keyboard shortcuts for the adapter property pages, see [Adapter Property Page Keyboard Shortcuts](../core/adapter-property-page-keyboard-shortcuts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b08b7-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="b08b7-107">In This Section</span></span>  
  
-   [<span data-ttu-id="b08b7-108">BizTalk Server 中的适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-108">Adapters in BizTalk Server</span></span>](../core/adapters-in-biztalk-server.md)  
  
-   [<span data-ttu-id="b08b7-109">动态发送端口处理程序是可配置</span><span class="sxs-lookup"><span data-stu-id="b08b7-109">Dynamic Send Port Handler is Configurable</span></span>](../core/dynamic-send-port-handler-is-configurable.md)  
  
-   [<span data-ttu-id="b08b7-110">适配器的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="b08b7-110">Security Considerations for Adapters</span></span>](../core/security-considerations-for-adapters.md)  
  
-   [<span data-ttu-id="b08b7-111">SB 消息适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-111">SB-Messaging adapter</span></span>](../core/sb-messaging-adapter.md)  
  
-   [<span data-ttu-id="b08b7-112">文件适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-112">File adapter</span></span>](../core/file-adapter.md)  
  
-   [<span data-ttu-id="b08b7-113">FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-113">FTP adapter</span></span>](../core/ftp-adapter.md)  

- [<span data-ttu-id="b08b7-114">逻辑应用适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-114">Logic App adapter</span></span>](../core/logic-app-adapter.md)
  
-   [<span data-ttu-id="b08b7-115">SFTP 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-115">SFTP adapter</span></span>](../core/sftp-adapter.md)  
  
-   [<span data-ttu-id="b08b7-116">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-116">HTTP adapter</span></span>](../core/http-adapter.md)  
  
-   [<span data-ttu-id="b08b7-117">博士 Edwards EnterpriseOne 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-117">JD Edwards EnterpriseOne adapter</span></span>](../core/jd-edwards-enterpriseone-adapter.md) 
  
-   [<span data-ttu-id="b08b7-118">博士 Edwards OneWorld 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-118">JD Edwards OneWorld adapter</span></span>](../core/jd-edwards-oneworld-adapter.md)  
  
-   [<span data-ttu-id="b08b7-119">Oracle E-business Suite ODBC 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-119">Oracle E-Business Suite ODBC adapter</span></span>](../core/oracle-e-business-suite-odbc-adapter.md)  
  
-   [<span data-ttu-id="b08b7-120">Oracle 数据库 ODBC 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-120">Oracle Database ODBC adapter</span></span>](../core/oracle-database-odbc-adapter.md)  
  
-   [<span data-ttu-id="b08b7-121">PeopleSoft Enterprise 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-121">PeopleSoft Enterprise adapter</span></span>](../core/peoplesoft-enterprise-adapter.md)  
  
-   [<span data-ttu-id="b08b7-122">Siebel eBusiness 应用程序适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-122">Siebel eBusiness Applications adapter</span></span>](../core/siebel-ebusiness-applications-adapter.md)  
  
-   [<span data-ttu-id="b08b7-123">TIBCO 企业消息服务适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-123">TIBCO Enterprise Message Service adapter</span></span>](../core/tibco-enterprise-message-service-adapter.md)  
  
-   [<span data-ttu-id="b08b7-124">TIBCO 会合适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-124">TIBCO Rendezvous adapter</span></span>](../core/tibco-rendezvous-adapter.md)  
  
-   [<span data-ttu-id="b08b7-125">MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-125">MQSeries adapter</span></span>](../core/mqseries-adapter.md)  
  
-   [<span data-ttu-id="b08b7-126">MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-126">MSMQ adapter</span></span>](../core/msmq-adapter.md)  
  
-   [<span data-ttu-id="b08b7-127">POP3 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-127">POP3 adapter</span></span>](../core/pop3-adapter.md)  
  
-   [<span data-ttu-id="b08b7-128">SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-128">SAP adapter</span></span>](../core/sap-adapter.md)  
  
-   [<span data-ttu-id="b08b7-129">SMTP 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-129">SMTP adapter</span></span>](../core/smtp-adapter.md)  
  
-   [<span data-ttu-id="b08b7-130">SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-130">SOAP adapter</span></span>](../core/soap-adapter.md)  
  
-   [<span data-ttu-id="b08b7-131">SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-131">SQL adapter</span></span>](../core/sql-adapter.md)  
  
-   [<span data-ttu-id="b08b7-132">Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-132">Windows SharePoint Services adapter</span></span>](../core/windows-sharepoint-services-adapter.md)  
  
-   [<span data-ttu-id="b08b7-133">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-133">WCF adapters</span></span>](../core/wcf-adapters.md)  
  
-   [<span data-ttu-id="b08b7-134">创建和删除适配器处理程序</span><span class="sxs-lookup"><span data-stu-id="b08b7-134">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)  
  
-   [<span data-ttu-id="b08b7-135">适配器性能影响的配置参数</span><span class="sxs-lookup"><span data-stu-id="b08b7-135">Configuration Parameters that Affect Adapter Performance</span></span>](../core/configuration-parameters-that-affect-adapter-performance.md)  
  
-   [<span data-ttu-id="b08b7-136">故障排除的 BizTalk Server 适配器</span><span class="sxs-lookup"><span data-stu-id="b08b7-136">Troubleshooting BizTalk Server Adapters</span></span>](../core/troubleshooting-biztalk-server-adapters.md)  
  
-   [<span data-ttu-id="b08b7-137">其他适配器信息</span><span class="sxs-lookup"><span data-stu-id="b08b7-137">Additional Adapter Information</span></span>](../core/additional-adapter-information.md)