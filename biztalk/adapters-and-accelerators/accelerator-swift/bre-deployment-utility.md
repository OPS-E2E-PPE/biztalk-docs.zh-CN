---
title: BRE 部署实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BRE Deployment utility
- deploying, BRE Deployment utility
ms.assetid: 5b04592c-ea1e-4ded-8ca4-dcd051d6375e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d59a06b55e4d30e9e87a68adbf830dad38578f3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378971"
---
# <a name="bre-deployment-utility"></a><span data-ttu-id="fdf9f-102">BRE 部署实用工具</span><span class="sxs-lookup"><span data-stu-id="fdf9f-102">BRE Deployment Utility</span></span>
<span data-ttu-id="fdf9f-103">您可以使用 BRE 部署实用工具来发布和部署业务规则引擎 (BRE) 的词汇和策略所需的 SWIFT 架构。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-103">You can use the BRE Deployment Utility to publish and deploy the Business Rule Engine (BRE) vocabularies and policies required for a SWIFT schema.</span></span> <span data-ttu-id="fdf9f-104">启用消息类型的 BRE 验证需要发布和部署这些词汇和策略。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-104">Publishing and deploying these vocabularies and policies is required to enable BRE validation for the message type.</span></span>  
  
 <span data-ttu-id="fdf9f-105">您还可以通过使用 SWIFT 标准发布指南 (SRGs) 来标识所需的规则，然后使用 Microsoft 部署业务规则[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]业务规则编辑器工具来部署词汇和策略。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-105">You can also deploy business rules by using the SWIFT Standards Release Guides (SRGs) to identify the required rules, and then using the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Business Rule Composer tool to deploy the vocabularies and policies.</span></span> <span data-ttu-id="fdf9f-106">但是，使用 BRE 部署实用工具要容易得多。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-106">However, using the BRE Deployment Utility is much easier.</span></span>  
  
 <span data-ttu-id="fdf9f-107">BRE 部署实用工具完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="fdf9f-107">The BRE Deployment Utility accomplishes the following:</span></span>  
  
- <span data-ttu-id="fdf9f-108">检查你指定的已部署程序集并确定部署的程序集的消息架构。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-108">Examines the deployed assembly that you specify and determines the message schemas that you deployed for the assembly.</span></span>  
  
- <span data-ttu-id="fdf9f-109">将发布[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml 并[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Functions.xml 词汇所需的 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]处理的业务规则。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-109">Publishes the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Functions.xml vocabularies required for Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] business rules processing.</span></span>  
  
- <span data-ttu-id="fdf9f-110">发布和部署的 SWIFT 基本策略 （引用策略、 参与方标识符策略和网络规则策略） 与消息架构相关联。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-110">Publishes and deploys the SWIFT base policies (reference policy, party identifier policy, and network rule policies) associated with the message schemas.</span></span>  
  
- <span data-ttu-id="fdf9f-111">发布和部署主策略以及与每个消息架构相关联的验证策略。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-111">Publishes and deploys the master policy and validation policy associated with each message schema.</span></span>  
  
- <span data-ttu-id="fdf9f-112">生成日志文件，该值指示所需的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-112">Generates a log file that indicates all the steps that it takes.</span></span> <span data-ttu-id="fdf9f-113">此文件是在 BREDeploymentLog.txt \<*驱动器*\>: \Documents and Settings\All Users\Application Data 文件夹。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-113">This file is BREDeploymentLog.txt in the \<*drive*\>:\Documents and Settings\All Users\Application Data folder.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="fdf9f-114">BRE 部署实用工具不部署 BIC Master 策略和 BIC 验证策略。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-114">The BRE Deployment Utility does not deploy the BIC Master Policy and BIC Validation Policy.</span></span> <span data-ttu-id="fdf9f-115">您必须部署这些使用规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-115">You must deploy these using the Rule Engine Deployment wizard.</span></span>  
  > 
  > [!NOTE]
  >  <span data-ttu-id="fdf9f-116">如果已安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]中的非默认目录 (C:\Program Files\Microsoft 以外[!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)])，或在 64 位计算机上工作，BRE 部署实用工具将无法正常工作之前更改中的路径BREDeployment.exe.config 文件。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-116">If you have installed [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] in a non-default directory (other than C:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]), or you are working on a 64-bit computer, the BRE Deployment Utility will not work correctly until you change the paths in the BREDeployment.exe.config file.</span></span> <span data-ttu-id="fdf9f-117">此配置文件位于\<*驱动器*\>: \Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools 文件夹。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-117">This configuration file is located in the \<*drive*\>:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools folder.</span></span> <span data-ttu-id="fdf9f-118">若要更新该实用程序的配置，在记事本中，打开 BREDeployment.exe.config 和更改的基本策略、 架构和词汇目录的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-118">To update the utility's configuration, open BREDeployment.exe.config in Notepad, and change the folders for the base policies, schemas, and vocabulary directories.</span></span>  
  
  <span data-ttu-id="fdf9f-119">此外可以使用部署实用工具来逆转此过程中，取消部署和取消发布的策略和词汇。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-119">You can also use the deployment utility to reverse this process, undeploying and unpublishing the policies and vocabularies.</span></span> <span data-ttu-id="fdf9f-120">此实用工具已同时部署和取消部署功能。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-120">The utility has both deploy and undeploy functionality.</span></span>  
  
### <a name="to-use-the-bre-deployment-utility"></a><span data-ttu-id="fdf9f-121">若要使用 BRE 部署实用工具</span><span class="sxs-lookup"><span data-stu-id="fdf9f-121">To use the BRE Deployment Utility</span></span>  
  
1.  <span data-ttu-id="fdf9f-122">单击**启动**，依次指向**程序**，指向**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BRE 部署实用工具**。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-122">Click **Start**, point to **Programs**, point to **Microsoft BizTalk Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="fdf9f-123">BRE 部署实用工具中单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-123">In the BRE Deployment Utility, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="fdf9f-124">选择部署的程序集或程序集要发布和部署词汇和策略，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-124">Select the deployed assembly or assemblies for which you want to publish and deploy vocabularies and policies, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="fdf9f-125">单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-125">Click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fdf9f-126">根据使用该程序集部署的架构，BRE 部署实用工具都要通过确定相关的规则并将其发布与 BRE 一起使用的过程。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-126">Based on the schemas that you deployed with that assembly, the BRE Deployment Utility goes through the process of identifying the related rules and publishing them for use with the BRE.</span></span> <span data-ttu-id="fdf9f-127">完成后，BRE 部署实用工具将显示以下消息：**完成部署后**。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-127">When complete, the BRE Deployment Utility displays the following message: **Deployment has completed**.</span></span> <span data-ttu-id="fdf9f-128">使用业务规则编辑器来验证成功的部署。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-128">Use the Business Rule Composer to verify successful deployment.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fdf9f-129">若要取消部署策略和词汇，请单击**Undeploy**。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-129">To undeploy the policies and vocabularies, click **Undeploy**.</span></span> <span data-ttu-id="fdf9f-130">取消部署过程取消 A4SWIFT_CodeLists.xml 和 A4SWIFT_Functions.xml 词汇，可能由其他已部署的策略未部署。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-130">The undeploy process does not undeploy the A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml vocabularies, which might be used by other deployed policies.</span></span>  
  
5.  <span data-ttu-id="fdf9f-131">找到\<*驱动器*\>: \Documents and Settings\All Users\Application Data，若要确认该实用程序创建日志文件 BREDeploymentLog.txt。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-131">Locate \<*drive*\>:\Documents and Settings\All Users\Application Data to confirm that the utility created the log file BREDeploymentLog.txt.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fdf9f-132">可以使用文本编辑器以确认每个部署步骤来打开日志文件。</span><span class="sxs-lookup"><span data-stu-id="fdf9f-132">You can open the log file by using a text editor to confirm each deployment step.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdf9f-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdf9f-133">See Also</span></span>  
 [<span data-ttu-id="fdf9f-134">工具</span><span class="sxs-lookup"><span data-stu-id="fdf9f-134">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)