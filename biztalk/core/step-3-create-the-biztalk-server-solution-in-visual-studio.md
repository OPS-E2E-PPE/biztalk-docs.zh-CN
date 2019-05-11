---
title: 步骤 3：在 Visual Studio 中创建的 BizTalk Server 解决方案 |Microsoft Docs
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
ms.openlocfilehash: 35f5c2b16aa29613a3709b9b5ece6ae3bd815229
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392655"
---
# <a name="step-3-create-the-biztalk-server-solution-in-visual-studio"></a><span data-ttu-id="1f6bf-102">步骤 3：在 Visual Studio 中创建的 BizTalk Server 解决方案</span><span class="sxs-lookup"><span data-stu-id="1f6bf-102">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>
<span data-ttu-id="1f6bf-103">在本部分中，我们介绍创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收从 Salesforce 接收机会通知、 查询 Salesforce 以获取其他信息的机会，以及最后将该信息插入到本地 SQL 的解决方案服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="1f6bf-103">In this section, we look at creating the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution for receiving opportunity notifications from Salesforce, querying Salesforce to get additional information about the opportunity, and finally inserting that information into an on-premise SQL Server database.</span></span> <span data-ttu-id="1f6bf-104">本部分中进一步分类根据每个更广泛的步骤。</span><span class="sxs-lookup"><span data-stu-id="1f6bf-104">This section is further categorized according to each of these broader steps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f6bf-105">若要能够将消息发送到 Salesforce 并接收来自 Salesforce 到邮件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，我们需要我们的解决方案中添加一些自定义组件。</span><span class="sxs-lookup"><span data-stu-id="1f6bf-105">To be able to send messages to Salesforce and to receive messages from Salesforce into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], we need to include some custom components into our solution.</span></span> <span data-ttu-id="1f6bf-106">我们将创建这些自定义组件中的[步骤 3d:启用 BizTalk Server 可以发送和接收来自 Salesforce 的消息](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)。</span><span class="sxs-lookup"><span data-stu-id="1f6bf-106">We create those custom components in [Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f6bf-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="1f6bf-107">In This Section</span></span>  
  
-   [<span data-ttu-id="1f6bf-108">步骤 3a:Salesforce 机会通知接收到 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="1f6bf-108">Step 3a: Receive Salesforce Opportunity Notification into BizTalk Server</span></span>](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md)  
  
-   [<span data-ttu-id="1f6bf-109">步骤 3b:使用 Wcf-webhttp 适配器从 Salesforce 检索机会详细信息</span><span class="sxs-lookup"><span data-stu-id="1f6bf-109">Step 3b: Retrieve Opportunity Details from Salesforce using the WCF-WebHttp Adapter</span></span>](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)  
  
-   [<span data-ttu-id="1f6bf-110">步骤 3c:将机会详细信息插入到 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="1f6bf-110">Step 3c: Insert Opportunity Details into a SQL Server Database</span></span>](../core/step-3c-insert-opportunity-details-into-a-sql-server-database.md)  
  
-   [<span data-ttu-id="1f6bf-111">步骤 3d:启用 BizTalk Server 可以发送和接收来自 Salesforce 的消息</span><span class="sxs-lookup"><span data-stu-id="1f6bf-111">Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce</span></span>](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)  
  
-   [<span data-ttu-id="1f6bf-112">步骤 3e:生成和部署 BizTalk Server 解决方案</span><span class="sxs-lookup"><span data-stu-id="1f6bf-112">Step 3e: Build and Deploy the BizTalk Server Solution</span></span>](../core/step-3e-build-and-deploy-the-biztalk-server-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="1f6bf-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f6bf-113">See Also</span></span>  
 [<span data-ttu-id="1f6bf-114">教程 6:将 BizTalk Server 2013 与 Salesforce 集成</span><span class="sxs-lookup"><span data-stu-id="1f6bf-114">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)