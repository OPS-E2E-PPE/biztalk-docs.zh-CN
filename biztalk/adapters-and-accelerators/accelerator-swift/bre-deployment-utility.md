---
title: "BRE 部署实用工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BRE Deployment utility
- deploying, BRE Deployment utility
ms.assetid: 5b04592c-ea1e-4ded-8ca4-dcd051d6375e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5868172b566a12ab6299e0eaabe12fa2153bfb97
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="bre-deployment-utility"></a><span data-ttu-id="55f9f-102">BRE 部署实用工具</span><span class="sxs-lookup"><span data-stu-id="55f9f-102">BRE Deployment Utility</span></span>
<span data-ttu-id="55f9f-103">你可以使用 BRE 部署实用工具进行发布和部署的业务规则引擎 (BRE) 词汇和 SWIFT 架构所需的策略。</span><span class="sxs-lookup"><span data-stu-id="55f9f-103">You can use the BRE Deployment Utility to publish and deploy the Business Rule Engine (BRE) vocabularies and policies required for a SWIFT schema.</span></span> <span data-ttu-id="55f9f-104">启用消息类型的 BRE 验证需要发布和部署这些词汇和策略。</span><span class="sxs-lookup"><span data-stu-id="55f9f-104">Publishing and deploying these vocabularies and policies is required to enable BRE validation for the message type.</span></span>  
  
 <span data-ttu-id="55f9f-105">您还可以通过使用 SWIFT 标准版本指南 (SRGs) 以标识所需的规则，然后使用部署业务规则[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]业务规则编辑器工具，将部署的词汇和策略。</span><span class="sxs-lookup"><span data-stu-id="55f9f-105">You can also deploy business rules by using the SWIFT Standards Release Guides (SRGs) to identify the required rules, and then using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Business Rule Composer tool to deploy the vocabularies and policies.</span></span> <span data-ttu-id="55f9f-106">但是，使用 BRE 部署实用工具是要容易得多。</span><span class="sxs-lookup"><span data-stu-id="55f9f-106">However, using the BRE Deployment Utility is much easier.</span></span>  
  
 <span data-ttu-id="55f9f-107">BRE 部署实用工具完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="55f9f-107">The BRE Deployment Utility accomplishes the following:</span></span>  
  
-   <span data-ttu-id="55f9f-108">检查你指定的部署程序集，并确定你的程序集部署的消息架构。</span><span class="sxs-lookup"><span data-stu-id="55f9f-108">Examines the deployed assembly that you specify and determines the message schemas that you deployed for the assembly.</span></span>  
  
-   <span data-ttu-id="55f9f-109">发布[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml 和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Functions.xml 词汇所需的[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]处理的业务规则。</span><span class="sxs-lookup"><span data-stu-id="55f9f-109">Publishes the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Functions.xml vocabularies required for [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] business rules processing.</span></span>  
  
-   <span data-ttu-id="55f9f-110">发布和部署 SWIFT 基 （引用策略、 方标识符策略和网络规则策略） 与关联的策略的消息架构。</span><span class="sxs-lookup"><span data-stu-id="55f9f-110">Publishes and deploys the SWIFT base policies (reference policy, party identifier policy, and network rule policies) associated with the message schemas.</span></span>  
  
-   <span data-ttu-id="55f9f-111">发布和部署的主策略和与每个消息架构关联的验证策略。</span><span class="sxs-lookup"><span data-stu-id="55f9f-111">Publishes and deploys the master policy and validation policy associated with each message schema.</span></span>  
  
-   <span data-ttu-id="55f9f-112">生成日志文件，该值指示所需的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="55f9f-112">Generates a log file that indicates all the steps that it takes.</span></span> <span data-ttu-id="55f9f-113">此文件是在 BREDeploymentLog.txt \<*驱动器*\>: \Documents and Settings\All Users\Application 数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="55f9f-113">This file is BREDeploymentLog.txt in the \<*drive*\>:\Documents and Settings\All Users\Application Data folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="55f9f-114">BRE 部署实用工具不部署 BIC Master 策略和 BIC 验证策略。</span><span class="sxs-lookup"><span data-stu-id="55f9f-114">The BRE Deployment Utility does not deploy the BIC Master Policy and BIC Validation Policy.</span></span> <span data-ttu-id="55f9f-115">你必须部署这些使用规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="55f9f-115">You must deploy these using the Rule Engine Deployment wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="55f9f-116">如果你已安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]在非默认的目录 (C:\Program Files\Microsoft 以外[!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)])，或你正在 64 位计算机上，BRE 部署实用工具将无法正常工作之前更改中的路径BREDeployment.exe.config 文件。</span><span class="sxs-lookup"><span data-stu-id="55f9f-116">If you have installed [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] in a non-default directory (other than C:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]), or you are working on a 64-bit computer, the BRE Deployment Utility will not work correctly until you change the paths in the BREDeployment.exe.config file.</span></span> <span data-ttu-id="55f9f-117">此配置文件位于\<*驱动器*\>: files\microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools 文件夹。</span><span class="sxs-lookup"><span data-stu-id="55f9f-117">This configuration file is located in the \<*drive*\>:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools folder.</span></span> <span data-ttu-id="55f9f-118">若要更新该实用程序的配置，在记事本中，打开 BREDeployment.exe.config 和更改的基本策略、 架构和词汇目录的文件夹。</span><span class="sxs-lookup"><span data-stu-id="55f9f-118">To update the utility's configuration, open BREDeployment.exe.config in Notepad, and change the folders for the base policies, schemas, and vocabulary directories.</span></span>  
  
 <span data-ttu-id="55f9f-119">你可以使用部署实用工具要反转此过程中，取消部署和取消发布的策略和词汇。</span><span class="sxs-lookup"><span data-stu-id="55f9f-119">You can also use the deployment utility to reverse this process, undeploying and unpublishing the policies and vocabularies.</span></span> <span data-ttu-id="55f9f-120">该实用工具已两者进行部署，并取消部署功能。</span><span class="sxs-lookup"><span data-stu-id="55f9f-120">The utility has both deploy and undeploy functionality.</span></span>  
  
### <a name="to-use-the-bre-deployment-utility"></a><span data-ttu-id="55f9f-121">若要使用 BRE 部署实用工具</span><span class="sxs-lookup"><span data-stu-id="55f9f-121">To use the BRE Deployment Utility</span></span>  
  
1.  <span data-ttu-id="55f9f-122">单击**启动**，指向**程序**，指向**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BRE 部署实用工具**。</span><span class="sxs-lookup"><span data-stu-id="55f9f-122">Click **Start**, point to **Programs**, point to **Microsoft BizTalk Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="55f9f-123">在 BRE 部署实用程序中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="55f9f-123">In the BRE Deployment Utility, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="55f9f-124">选择部署的程序集或程序集要发布和部署的词汇和策略，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="55f9f-124">Select the deployed assembly or assemblies for which you want to publish and deploy vocabularies and policies, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="55f9f-125">单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="55f9f-125">Click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="55f9f-126">根据使用该程序集部署的架构，BRE 部署实用工具将经历标识相关的规则，并将其发布以用于 BRE 的过程。</span><span class="sxs-lookup"><span data-stu-id="55f9f-126">Based on the schemas that you deployed with that assembly, the BRE Deployment Utility goes through the process of identifying the related rules and publishing them for use with the BRE.</span></span> <span data-ttu-id="55f9f-127">完成后，BRE 部署实用工具，则显示以下消息：**部署已完成**。</span><span class="sxs-lookup"><span data-stu-id="55f9f-127">When complete, the BRE Deployment Utility displays the following message: **Deployment has completed**.</span></span> <span data-ttu-id="55f9f-128">使用业务规则编辑器来验证成功部署。</span><span class="sxs-lookup"><span data-stu-id="55f9f-128">Use the Business Rule Composer to verify successful deployment.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="55f9f-129">若要取消部署的策略和词汇表，请单击**取消部署后再次**。</span><span class="sxs-lookup"><span data-stu-id="55f9f-129">To undeploy the policies and vocabularies, click **Undeploy**.</span></span> <span data-ttu-id="55f9f-130">取消部署过程取消 A4SWIFT_CodeLists.xml 和 A4SWIFT_Functions.xml 词汇，可能由其他部署策略未部署。</span><span class="sxs-lookup"><span data-stu-id="55f9f-130">The undeploy process does not undeploy the A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml vocabularies, which might be used by other deployed policies.</span></span>  
  
5.  <span data-ttu-id="55f9f-131">找到\<*驱动器*\>: \Documents and Settings\All Users\Application 数据，以确认该实用程序创建日志文件 BREDeploymentLog.txt。</span><span class="sxs-lookup"><span data-stu-id="55f9f-131">Locate \<*drive*\>:\Documents and Settings\All Users\Application Data to confirm that the utility created the log file BREDeploymentLog.txt.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="55f9f-132">可以通过使用文本编辑器以确认每个部署步骤来打开日志文件。</span><span class="sxs-lookup"><span data-stu-id="55f9f-132">You can open the log file by using a text editor to confirm each deployment step.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55f9f-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55f9f-133">See Also</span></span>  
 [<span data-ttu-id="55f9f-134">工具</span><span class="sxs-lookup"><span data-stu-id="55f9f-134">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)