---
title: 步骤 1： 创建服务总线 Namespace |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede1ac50-bbfb-4aeb-8217-1877ae218f89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4d7630316f72fd63bac5ce7127b5451683e2f97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276757"
---
# <a name="step-1-create-a-service-bus-namespace"></a><span data-ttu-id="4b066-102">步骤 1： 创建服务总线 Namespace</span><span class="sxs-lookup"><span data-stu-id="4b066-102">Step 1: Create a Service Bus Namespace</span></span>
<span data-ttu-id="4b066-103">在此步骤中，你将创建[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]命名空间。</span><span class="sxs-lookup"><span data-stu-id="4b066-103">In this step, you create a [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)] namespace.</span></span> <span data-ttu-id="4b066-104">你将使用此命名空间托管用于从 Salesforce 接收机会通知的中继终结点。</span><span class="sxs-lookup"><span data-stu-id="4b066-104">You will use this namespace to host a relay endpoint for receiving opportunity notifications from Salesforce.</span></span> <span data-ttu-id="4b066-105">在创建此解决方案的过程的后面部分，将使用此中继终结点将通知消息接收到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统中。</span><span class="sxs-lookup"><span data-stu-id="4b066-105">Later in the process of creating this solution, you will use this relay endpoint to receive the notification message into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
### <a name="to-create-a-includesbincludessb-mdmd-namespace"></a><span data-ttu-id="4b066-106">创建 [!INCLUDE[sb](../includes/sb-md.md)] 命名空间</span><span class="sxs-lookup"><span data-stu-id="4b066-106">To create a [!INCLUDE[sb](../includes/sb-md.md)] namespace</span></span>  
  
1.  <span data-ttu-id="4b066-107">登录到[http://manage.windowsazure.com](http://manage.windowsazure.com)使用你的 Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="4b066-107">Log on to [http://manage.windowsazure.com](http://manage.windowsazure.com) using your Microsoft account.</span></span>  
  
2.  <span data-ttu-id="4b066-108">在页面底部，单击**新建**，**应用程序服务**， **Service Bus 中继**，，然后**快速创建**。</span><span class="sxs-lookup"><span data-stu-id="4b066-108">At the bottom of the page, click **New**, **App Services**, **Service Bus Relay**, and then **Quick Create**.</span></span>  
  
3.  <span data-ttu-id="4b066-109">输入作为命名空间`BtsSalesforce`选择离你当前的地理位置区域。</span><span class="sxs-lookup"><span data-stu-id="4b066-109">Enter the namespace as `BtsSalesforce` and select a region closest to your current geographical location.</span></span> <span data-ttu-id="4b066-110">单击**创建中继**。</span><span class="sxs-lookup"><span data-stu-id="4b066-110">Click **Create a Relay**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="4b066-111">这必须是全球唯一的命名空间。</span><span class="sxs-lookup"><span data-stu-id="4b066-111">This namespace must be globally unique.</span></span> <span data-ttu-id="4b066-112">因此，你必须使用本教程中提及的命名空间以外的命名空间。</span><span class="sxs-lookup"><span data-stu-id="4b066-112">So, you must use a namespace other than one mentioned in this tutorial.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b066-113">请注意，中继并不作为操作的一部分创建，只有命名空间才是如此。</span><span class="sxs-lookup"><span data-stu-id="4b066-113">Note that the relay is not created as part of the operation, only the namespace is.</span></span> <span data-ttu-id="4b066-114">我们将配置的接收位置时，将中继终结点创建本教程中稍后**SB 消息**适配器。</span><span class="sxs-lookup"><span data-stu-id="4b066-114">The relay endpoint is created later in this tutorial when we configure a receive location for the **SB-Messaging** adapter.</span></span>  
  
4.  <span data-ttu-id="4b066-115">创建命名空间后，将状态设置为**Active**。</span><span class="sxs-lookup"><span data-stu-id="4b066-115">After the namespace is created, the status is set to **Active**.</span></span> <span data-ttu-id="4b066-116">活动状态后，你可以选择的命名空间并单击**访问密钥**要获取有关如何连接到的详细信息的页的底部**BtsSalesforce**命名空间，包括的值**默认用户**和**默认密钥**。</span><span class="sxs-lookup"><span data-stu-id="4b066-116">Once the status is active, you can select the namespace and click **Access Key** at the bottom of the page to get details on how to connect to the **BtsSalesforce** namespace, including the values for **Default User** and **Default Key**.</span></span> <span data-ttu-id="4b066-117">在本教程的后面部分，你将需要这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b066-117">You will need these details later in the tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b066-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b066-118">See Also</span></span>  
 [<span data-ttu-id="4b066-119">教程 6： 将与 Salesforce 集成 BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b066-119">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)