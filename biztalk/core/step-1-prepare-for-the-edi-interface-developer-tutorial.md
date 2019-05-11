---
title: 第 1 步：EDI 接口开发人员教程的准备工作 |Microsoft Docs
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
ms.openlocfilehash: d01678bb342909d13beb15141765b789b12a0687
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392799"
---
# <a name="step-1-prepare-for-the-edi-interface-developer-tutorial"></a><span data-ttu-id="99808-102">第 1 步：EDI 接口开发人员教程的准备工作</span><span class="sxs-lookup"><span data-stu-id="99808-102">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>
<span data-ttu-id="99808-103">![步骤 1 部分，共 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")</span><span class="sxs-lookup"><span data-stu-id="99808-103">![Step 1 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")</span></span>  
  
 <span data-ttu-id="99808-104">EDI 接口开发人员教程运行在单台计算机上。</span><span class="sxs-lookup"><span data-stu-id="99808-104">The EDI Interface Development tutorial is run on a single computer.</span></span> <span data-ttu-id="99808-105">若要准备本教程，必须安装和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中所述[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。</span><span class="sxs-lookup"><span data-stu-id="99808-105">To prepare for the tutorial, you must install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as described in [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span> <span data-ttu-id="99808-106">您还必须添加对 BizTalk EDI 应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="99808-106">You must also add reference to the BizTalk EDI Application</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99808-107">若要运行本教程，必须使用 IIS 7.5 或 IIS 8 的平台上运行它。</span><span class="sxs-lookup"><span data-stu-id="99808-107">For this tutorial to work, it must be run on a platform using IIS 7.5 or IIS 8.</span></span>  
  
 <span data-ttu-id="99808-108">EDI 接口开发人员教程所需的文件位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial 文件夹。</span><span class="sxs-lookup"><span data-stu-id="99808-108">The files required for the EDI Interface Developer tutorial are located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial folder.</span></span> <span data-ttu-id="99808-109">文件夹和教程所需的文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="99808-109">The folders and files required for the tutorial are as follows:</span></span>  
  
|<span data-ttu-id="99808-110">Folder\File</span><span class="sxs-lookup"><span data-stu-id="99808-110">Folder\File</span></span>|<span data-ttu-id="99808-111">用途</span><span class="sxs-lookup"><span data-stu-id="99808-111">Purpose</span></span>|  
|------------------|-------------|  
|<span data-ttu-id="99808-112">\SDK\EDI 接口开发人员 Tutorial\EDI 入站 Processing.sln</span><span class="sxs-lookup"><span data-stu-id="99808-112">\SDK\EDI Interface Developer Tutorial\EDI Inbound Processing.sln</span></span>|<span data-ttu-id="99808-113">使用 Visual Studio 中创建此消息传递方案的解决方案文件</span><span class="sxs-lookup"><span data-stu-id="99808-113">The solution file that you use in Visual Studio to create this messaging scenario</span></span>|  
|<span data-ttu-id="99808-114">\SDK\EDI 接口开发人员 Tutorial\keyfile.snk</span><span class="sxs-lookup"><span data-stu-id="99808-114">\SDK\EDI Interface Developer Tutorial\keyfile.snk</span></span>|<span data-ttu-id="99808-115">指定解决方案文件的程序集密钥文件</span><span class="sxs-lookup"><span data-stu-id="99808-115">The assembly key file specified for the solution file</span></span>|  
|<span data-ttu-id="99808-116">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\SamplePO.txt</span><span class="sxs-lookup"><span data-stu-id="99808-116">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\SamplePO.txt</span></span>|<span data-ttu-id="99808-117">示例消息文件 （版本 4010 850），用来测试解决方案</span><span class="sxs-lookup"><span data-stu-id="99808-117">The sample message file (version 4010 850) that you use to test the solution</span></span>|  
|<span data-ttu-id="99808-118">\SDK\EDI 接口开发人员 Tutorial\ Inbound_EDI\Inbound4010850_to_OrderFile.btm</span><span class="sxs-lookup"><span data-stu-id="99808-118">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\Inbound4010850_to_OrderFile.btm</span></span>|<span data-ttu-id="99808-119">BizTalk 映射，可将 850 消息数据转换为订单系统所需的格式。</span><span class="sxs-lookup"><span data-stu-id="99808-119">The BizTalk map that converts the 850 message data into the format required by the Order System.</span></span>|  
|<span data-ttu-id="99808-120">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\SendOrderFilePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="99808-120">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\SendOrderFilePipeline.btp</span></span>|<span data-ttu-id="99808-121">处理测试消息以将消息发送到订单系统的发送管道。</span><span class="sxs-lookup"><span data-stu-id="99808-121">The send pipeline that processes the test message for sending the message to the order system.</span></span>|  
|<span data-ttu-id="99808-122">\SDK\EDI 接口开发人员 Tutorial\ Inbound_EDI\X12_00401_850.xsd</span><span class="sxs-lookup"><span data-stu-id="99808-122">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\X12_00401_850.xsd</span></span>|<span data-ttu-id="99808-123">测试消息的 850 架构。</span><span class="sxs-lookup"><span data-stu-id="99808-123">The 850 schema for the test message.</span></span>|  
<span data-ttu-id="99808-124">\SDK\EDI interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\fromTHEM</span><span class="sxs-lookup"><span data-stu-id="99808-124">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\fromTHEM</span></span>|<span data-ttu-id="99808-125">从 Fabrikam 接收入站 850 消息所在的文件夹</span><span class="sxs-lookup"><span data-stu-id="99808-125">Folder where the inbound 850 message is received from Fabrikam</span></span>|  
|<span data-ttu-id="99808-126">\SDK\EDI 界面开发人员 Tutorial\ ProcessEDI_TestLocations\Scenario A\toOrderSystem</span><span class="sxs-lookup"><span data-stu-id="99808-126">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toOrderSystem</span></span>|<span data-ttu-id="99808-127">其中的出站 850 消息发送到的文件夹表示订单系统后端应用程序</span><span class="sxs-lookup"><span data-stu-id="99808-127">Folder where the outbound 850 message is sent to, representing your Order System back-end application</span></span>|  
|<span data-ttu-id="99808-128">\SDK\EDI 接口开发人员 Tutorial\ ProcessEDI_TestLocations\Scenario A\toTHEM_997</span><span class="sxs-lookup"><span data-stu-id="99808-128">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toTHEM_997</span></span>|<span data-ttu-id="99808-129">文件夹位置将 997 确认发送到代表 Fabrikam</span><span class="sxs-lookup"><span data-stu-id="99808-129">Folder where the 997 acknowledgment is sent to, representing Fabrikam</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="99808-130">先决条件</span><span class="sxs-lookup"><span data-stu-id="99808-130">Prerequisites</span></span>  
 <span data-ttu-id="99808-131">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="99808-131">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-add-reference-to-the-biztalk-edi-application"></a><span data-ttu-id="99808-132">若要添加到 BizTalk EDI 应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="99808-132">To add reference to the BizTalk EDI Application</span></span>  
  
1. <span data-ttu-id="99808-133">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**应用程序**节点，右键单击你想要为 EDI，如 BizTalk Application 1 使用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="99808-133">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **Applications** node, right-click the application that you want to use for EDI, such as BizTalk Application 1.</span></span> <span data-ttu-id="99808-134">指向**添加**，然后单击引用。</span><span class="sxs-lookup"><span data-stu-id="99808-134">Point to **Add**, and then click References.</span></span>  
  
2. <span data-ttu-id="99808-135">在中**添加应用程序引用**对话框中，选择**BizTalk EDI 应用程序**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="99808-135">In the **Add Application Reference** dialog box, select **BizTalk EDI Application**, and then click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="99808-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="99808-136">Next Steps</span></span>  
 <span data-ttu-id="99808-137">生成并部署 Inbound_EDI 程序集，如中所述[步骤 2:更新和部署教程解决方案](../core/step-2-update-and-deploy-the-tutorial-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="99808-137">You build and deploy the Inbound_EDI assembly, as described in [Step 2: Update and Deploy the Tutorial Solution](../core/step-2-update-and-deploy-the-tutorial-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99808-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="99808-138">See Also</span></span>  
 [<span data-ttu-id="99808-139">教程 2：EDI 接口开发人员教程</span><span class="sxs-lookup"><span data-stu-id="99808-139">Tutorial 2: EDI Interface Developer Tutorial</span></span>](../core/tutorial-2-edi-interface-developer-tutorial.md)