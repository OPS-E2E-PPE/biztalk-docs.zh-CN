---
title: 步骤 1： 准备 EDI 接口开发人员教程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9be1bddf-d673-4054-87f5-0205b8b5cc0d
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b222e425f44e58d79ab65d848a7aff395b1284b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279229"
---
# <a name="step-1-prepare-for-the-edi-interface-developer-tutorial"></a><span data-ttu-id="6c784-102">步骤 1： 准备 EDI 接口开发人员教程</span><span class="sxs-lookup"><span data-stu-id="6c784-102">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>
<span data-ttu-id="6c784-103">![9 的第 1 步](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")</span><span class="sxs-lookup"><span data-stu-id="6c784-103">![Step 1 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")</span></span>  
  
 <span data-ttu-id="6c784-104">EDI 接口开发人员教程运行在单台计算机上。</span><span class="sxs-lookup"><span data-stu-id="6c784-104">The EDI Interface Development tutorial is run on a single computer.</span></span> <span data-ttu-id="6c784-105">若要准备本教程，你必须安装和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中所述[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。</span><span class="sxs-lookup"><span data-stu-id="6c784-105">To prepare for the tutorial, you must install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as described in [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span> <span data-ttu-id="6c784-106">你还必须添加到 BizTalk EDI 应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="6c784-106">You must also add reference to the BizTalk EDI Application</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c784-107">对于本教程中工作，必须在使用 IIS 7.5 或 IIS 8 平台上运行它。</span><span class="sxs-lookup"><span data-stu-id="6c784-107">For this tutorial to work, it must be run on a platform using IIS 7.5 or IIS 8.</span></span>  
  
 <span data-ttu-id="6c784-108">EDI 接口开发人员教程所需的文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6c784-108">The files required for the EDI Interface Developer tutorial are located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial folder.</span></span> <span data-ttu-id="6c784-109">此教程所需的文件夹和文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c784-109">The folders and files required for the tutorial are as follows:</span></span>  
  
|<span data-ttu-id="6c784-110">文件夹\文件</span><span class="sxs-lookup"><span data-stu-id="6c784-110">Folder\File</span></span>|<span data-ttu-id="6c784-111">用途</span><span class="sxs-lookup"><span data-stu-id="6c784-111">Purpose</span></span>|  
|------------------|-------------|  
|<span data-ttu-id="6c784-112">\SDK\EDI Interface Developer Tutorial\EDI Inbound Processing.sln</span><span class="sxs-lookup"><span data-stu-id="6c784-112">\SDK\EDI Interface Developer Tutorial\EDI Inbound Processing.sln</span></span>|<span data-ttu-id="6c784-113">在 Visual Studio 中，使用该解决方案文件可创建此消息传送方案</span><span class="sxs-lookup"><span data-stu-id="6c784-113">The solution file that you use in Visual Studio to create this messaging scenario</span></span>|  
|<span data-ttu-id="6c784-114">\SDK\EDI Interface Developer Tutorial\keyfile.snk</span><span class="sxs-lookup"><span data-stu-id="6c784-114">\SDK\EDI Interface Developer Tutorial\keyfile.snk</span></span>|<span data-ttu-id="6c784-115">为解决方案文件指定的程序集密钥文件</span><span class="sxs-lookup"><span data-stu-id="6c784-115">The assembly key file specified for the solution file</span></span>|  
|<span data-ttu-id="6c784-116">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\SamplePO.txt</span><span class="sxs-lookup"><span data-stu-id="6c784-116">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\SamplePO.txt</span></span>|<span data-ttu-id="6c784-117">示例消息文件（版本 4010 850），可用于测试解决方案</span><span class="sxs-lookup"><span data-stu-id="6c784-117">The sample message file (version 4010 850) that you use to test the solution</span></span>|  
|<span data-ttu-id="6c784-118">\SDK\EDI 接口开发人员 Tutorial\ Inbound_EDI\Inbound4010850_to_OrderFile.btm</span><span class="sxs-lookup"><span data-stu-id="6c784-118">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\Inbound4010850_to_OrderFile.btm</span></span>|<span data-ttu-id="6c784-119">BizTalk 映射，可将 850 消息数据转换为订单系统所需的格式。</span><span class="sxs-lookup"><span data-stu-id="6c784-119">The BizTalk map that converts the 850 message data into the format required by the Order System.</span></span>|  
|<span data-ttu-id="6c784-120">\SDK\EDI 接口开发人员 Tutorial\ Inbound_EDI\SendOrderFilePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="6c784-120">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\SendOrderFilePipeline.btp</span></span>|<span data-ttu-id="6c784-121">发送管道，用于处理测试消息以将该消息发送到订单系统。</span><span class="sxs-lookup"><span data-stu-id="6c784-121">The send pipeline that processes the test message for sending the message to the order system.</span></span>|  
|<span data-ttu-id="6c784-122">\SDK\EDI 接口开发人员 Tutorial\ Inbound_EDI\X12_00401_850.xsd</span><span class="sxs-lookup"><span data-stu-id="6c784-122">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\X12_00401_850.xsd</span></span>|<span data-ttu-id="6c784-123">测试消息的 850 架构。</span><span class="sxs-lookup"><span data-stu-id="6c784-123">The 850 schema for the test message.</span></span>|  
<span data-ttu-id="6c784-124">\SDK\EDI 接口开发人员 Tutorial\ ProcessEDI_TestLocations\Scenario A\fromTHEM</span><span class="sxs-lookup"><span data-stu-id="6c784-124">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\fromTHEM</span></span>|<span data-ttu-id="6c784-125">用于接收来自 Fabrikam 的入站 850 消息的文件夹</span><span class="sxs-lookup"><span data-stu-id="6c784-125">Folder where the inbound 850 message is received from Fabrikam</span></span>|  
|<span data-ttu-id="6c784-126">\SDK\EDI 接口开发人员 Tutorial\ ProcessEDI_TestLocations\Scenario A\toOrderSystem</span><span class="sxs-lookup"><span data-stu-id="6c784-126">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toOrderSystem</span></span>|<span data-ttu-id="6c784-127">用来接收出站 850 消息的文件夹，代表订单系统后端应用程序</span><span class="sxs-lookup"><span data-stu-id="6c784-127">Folder where the outbound 850 message is sent to, representing your Order System back-end application</span></span>|  
|<span data-ttu-id="6c784-128">\SDK\EDI 接口开发人员 Tutorial\ ProcessEDI_TestLocations\Scenario A\toTHEM_997</span><span class="sxs-lookup"><span data-stu-id="6c784-128">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toTHEM_997</span></span>|<span data-ttu-id="6c784-129">用于接收 997 确认的文件夹，代表 Fabrikam</span><span class="sxs-lookup"><span data-stu-id="6c784-129">Folder where the 997 acknowledgment is sent to, representing Fabrikam</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="6c784-130">先决条件</span><span class="sxs-lookup"><span data-stu-id="6c784-130">Prerequisites</span></span>  
 <span data-ttu-id="6c784-131">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="6c784-131">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-add-reference-to-the-biztalk-edi-application"></a><span data-ttu-id="6c784-132">若要添加到 BizTalk EDI 应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="6c784-132">To add reference to the BizTalk EDI Application</span></span>  
  
1.  <span data-ttu-id="6c784-133">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，在**应用程序**节点，右键单击你想要使用 EDI，如 BizTalk 应用程序 1 的应用。</span><span class="sxs-lookup"><span data-stu-id="6c784-133">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **Applications** node, right-click the application that you want to use for EDI, such as BizTalk Application 1.</span></span> <span data-ttu-id="6c784-134">指向**添加**，，然后单击引用。</span><span class="sxs-lookup"><span data-stu-id="6c784-134">Point to **Add**, and then click References.</span></span>  
  
2.  <span data-ttu-id="6c784-135">在**添加应用程序引用**对话框中，选择**BizTalk EDI 应用程序**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6c784-135">In the **Add Application Reference** dialog box, select **BizTalk EDI Application**, and then click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6c784-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6c784-136">Next Steps</span></span>  
 <span data-ttu-id="6c784-137">生成并部署 Inbound_EDI 程序集中, 所述[步骤 2： 更新并将其部署该教程解决方案](../core/step-2-update-and-deploy-the-tutorial-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="6c784-137">You build and deploy the Inbound_EDI assembly, as described in [Step 2: Update and Deploy the Tutorial Solution](../core/step-2-update-and-deploy-the-tutorial-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c784-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c784-138">See Also</span></span>  
 [<span data-ttu-id="6c784-139">教程 2: EDI 接口开发人员教程</span><span class="sxs-lookup"><span data-stu-id="6c784-139">Tutorial 2: EDI Interface Developer Tutorial</span></span>](../core/tutorial-2-edi-interface-developer-tutorial.md)