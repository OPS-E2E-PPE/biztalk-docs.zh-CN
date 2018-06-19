---
title: 步骤 3： 在 Visual Studio 中创建 BizTalk Server 解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4da3333-e430-4caf-bc29-44a60ebac385
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 402434ec74327b55f243fecd9d1c347ce4ff0390
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278013"
---
# <a name="step-3-create-the-biztalk-server-solution-in-visual-studio"></a><span data-ttu-id="20450-102">步骤 3： 在 Visual Studio 中创建 BizTalk 服务器解决方案</span><span class="sxs-lookup"><span data-stu-id="20450-102">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>
<span data-ttu-id="20450-103">在本部分中，我们将了解如何创建实现以下目标的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 解决方案：从 Salesforce 接收机会通知，查询 Salesforce 以获取有关机会的更多信息，并最终将这些信息插入用户所在场所的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="20450-103">In this section, we look at creating the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution for receiving opportunity notifications from Salesforce, querying Salesforce to get additional information about the opportunity, and finally inserting that information into an on-premise SQL Server database.</span></span> <span data-ttu-id="20450-104">此部分将按照其中每个更广泛的步骤进一步分类。</span><span class="sxs-lookup"><span data-stu-id="20450-104">This section is further categorized according to each of these broader steps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20450-105">为了能够向 Salesforce 发送消息并从 Salesforce 将消息接收到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，我们需要向解决方案中添加一些自定义组件。</span><span class="sxs-lookup"><span data-stu-id="20450-105">To be able to send messages to Salesforce and to receive messages from Salesforce into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], we need to include some custom components into our solution.</span></span> <span data-ttu-id="20450-106">我们将创建这些自定义组件中的[步骤 3d： 启用 BizTalk Server 发送和接收来自 Salesforce](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)。</span><span class="sxs-lookup"><span data-stu-id="20450-106">We create those custom components in [Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20450-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="20450-107">In This Section</span></span>  
  
-   [<span data-ttu-id="20450-108">步骤 3a： 接收到 BizTalk Server Salesforce 机会通知</span><span class="sxs-lookup"><span data-stu-id="20450-108">Step 3a: Receive Salesforce Opportunity Notification into BizTalk Server</span></span>](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md)  
  
-   [<span data-ttu-id="20450-109">步骤 3b： 检索机会从 Salesforce 使用 WCF WebHttp 适配器的详细信息</span><span class="sxs-lookup"><span data-stu-id="20450-109">Step 3b: Retrieve Opportunity Details from Salesforce using the WCF-WebHttp Adapter</span></span>](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)  
  
-   [<span data-ttu-id="20450-110">步骤 3c: SQL Server 数据库中插入机会详细信息</span><span class="sxs-lookup"><span data-stu-id="20450-110">Step 3c: Insert Opportunity Details into a SQL Server Database</span></span>](../core/step-3c-insert-opportunity-details-into-a-sql-server-database.md)  
  
-   [<span data-ttu-id="20450-111">步骤 3d： 启用 BizTalk 服务器发送和接收来自 Salesforce 的消息</span><span class="sxs-lookup"><span data-stu-id="20450-111">Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce</span></span>](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)  
  
-   [<span data-ttu-id="20450-112">步骤 3e： 生成并部署 BizTalk 服务器解决方案</span><span class="sxs-lookup"><span data-stu-id="20450-112">Step 3e: Build and Deploy the BizTalk Server Solution</span></span>](../core/step-3e-build-and-deploy-the-biztalk-server-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="20450-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20450-113">See Also</span></span>  
 [<span data-ttu-id="20450-114">教程 6： 将与 Salesforce 集成 BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="20450-114">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)