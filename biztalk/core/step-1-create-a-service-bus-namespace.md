---
title: 第 1 步：创建服务总线 Namespace |Microsoft Docs
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
ms.openlocfilehash: 8d8986f729d48fd25066bd166749d6bfb2b7ed3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392819"
---
# <a name="step-1-create-a-service-bus-namespace"></a><span data-ttu-id="16be8-102">第 1 步：创建服务总线 Namespace</span><span class="sxs-lookup"><span data-stu-id="16be8-102">Step 1: Create a Service Bus Namespace</span></span>
<span data-ttu-id="16be8-103">在此步骤中，您将创建[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]命名空间。</span><span class="sxs-lookup"><span data-stu-id="16be8-103">In this step, you create a [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)] namespace.</span></span> <span data-ttu-id="16be8-104">将使用此命名空间来托管用于从 Salesforce 接收机会通知的中继终结点。</span><span class="sxs-lookup"><span data-stu-id="16be8-104">You will use this namespace to host a relay endpoint for receiving opportunity notifications from Salesforce.</span></span> <span data-ttu-id="16be8-105">更高版本的过程中创建此解决方案，您将使用此中继终结点来接收通知消息到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="16be8-105">Later in the process of creating this solution, you will use this relay endpoint to receive the notification message into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
### <a name="to-create-a-includesbincludessb-mdmd-namespace"></a><span data-ttu-id="16be8-106">若要创建[!INCLUDE[sb](../includes/sb-md.md)]命名空间</span><span class="sxs-lookup"><span data-stu-id="16be8-106">To create a [!INCLUDE[sb](../includes/sb-md.md)] namespace</span></span>  
  
1.  <span data-ttu-id="16be8-107">登录到[ http://manage.windowsazure.com ](http://manage.windowsazure.com)使用你的 Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="16be8-107">Log on to [http://manage.windowsazure.com](http://manage.windowsazure.com) using your Microsoft account.</span></span>  
  
2.  <span data-ttu-id="16be8-108">在页面底部，单击**新建**，**应用服务**，**服务总线中继**，然后**快速创建**。</span><span class="sxs-lookup"><span data-stu-id="16be8-108">At the bottom of the page, click **New**, **App Services**, **Service Bus Relay**, and then **Quick Create**.</span></span>  
  
3.  <span data-ttu-id="16be8-109">输入的命名空间`BtsSalesforce`并选择离你当前的地理位置最近的区域。</span><span class="sxs-lookup"><span data-stu-id="16be8-109">Enter the namespace as `BtsSalesforce` and select a region closest to your current geographical location.</span></span> <span data-ttu-id="16be8-110">单击**创建中继**。</span><span class="sxs-lookup"><span data-stu-id="16be8-110">Click **Create a Relay**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="16be8-111">此命名空间必须是全局唯一。</span><span class="sxs-lookup"><span data-stu-id="16be8-111">This namespace must be globally unique.</span></span> <span data-ttu-id="16be8-112">因此，必须使用一个在本教程中所述之外的命名空间。</span><span class="sxs-lookup"><span data-stu-id="16be8-112">So, you must use a namespace other than one mentioned in this tutorial.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="16be8-113">请注意，中继不作为操作的一部分创建，只有命名空间。</span><span class="sxs-lookup"><span data-stu-id="16be8-113">Note that the relay is not created as part of the operation, only the namespace is.</span></span> <span data-ttu-id="16be8-114">我们配置的接收位置时，稍后在本教程中创建的中继终结点**SB 消息**适配器。</span><span class="sxs-lookup"><span data-stu-id="16be8-114">The relay endpoint is created later in this tutorial when we configure a receive location for the **SB-Messaging** adapter.</span></span>  
  
4.  <span data-ttu-id="16be8-115">创建命名空间后，将状态设置为**Active**。</span><span class="sxs-lookup"><span data-stu-id="16be8-115">After the namespace is created, the status is set to **Active**.</span></span> <span data-ttu-id="16be8-116">一旦激活状态，可以选择的命名空间，单击**访问密钥**底部的页后，可以获取有关如何连接到详细信息**BtsSalesforce**命名空间，其中包括的值**默认用户**并**默认密钥**。</span><span class="sxs-lookup"><span data-stu-id="16be8-116">Once the status is active, you can select the namespace and click **Access Key** at the bottom of the page to get details on how to connect to the **BtsSalesforce** namespace, including the values for **Default User** and **Default Key**.</span></span> <span data-ttu-id="16be8-117">本教程的后面，将需要这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="16be8-117">You will need these details later in the tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16be8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="16be8-118">See Also</span></span>  
 [<span data-ttu-id="16be8-119">教程 6:将 BizTalk Server 2013 与 Salesforce 集成</span><span class="sxs-lookup"><span data-stu-id="16be8-119">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)