---
title: 部署 BRE 规则 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, BRE policies
- BRE policies, deploying
ms.assetid: 3a66aa57-e7f9-400f-963c-eda12fb1e659
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5627731bd84a761ffb62b95646876c768e3298ea
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967882"
---
# <a name="deploying-bre-rules"></a><span data-ttu-id="db688-102">部署 BRE 规则</span><span class="sxs-lookup"><span data-stu-id="db688-102">Deploying BRE Rules</span></span>
<span data-ttu-id="db688-103">必须将部署使用的 BRE 规则[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]业务流程来处理 SWIFT 消息。</span><span class="sxs-lookup"><span data-stu-id="db688-103">You must deploy the BRE rules used by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] orchestrations to process SWIFT messages.</span></span>  
  
 <span data-ttu-id="db688-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="db688-104">**Summary**</span></span>  
  
 <span data-ttu-id="db688-105">发布以下词汇：</span><span class="sxs-lookup"><span data-stu-id="db688-105">Publish the following vocabularies:</span></span>  
  
-   <span data-ttu-id="db688-106">A4SWIFT_CodeLists.xml 和 A4SWIFT_Functions.xml 词汇。</span><span class="sxs-lookup"><span data-stu-id="db688-106">A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml vocabularies.</span></span> <span data-ttu-id="db688-107">这些建议位于*\<驱动器\>*: files\microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base Policies\Vocabulary。</span><span class="sxs-lookup"><span data-stu-id="db688-107">These are located in *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies\Vocabulary.</span></span> <span data-ttu-id="db688-108">发布和部署这些使用 BRE 部署实用工具。</span><span class="sxs-lookup"><span data-stu-id="db688-108">Publish and deploy these using the BRE Deployment Utility.</span></span>  
  
 <span data-ttu-id="db688-109">发布和部署以下策略：</span><span class="sxs-lookup"><span data-stu-id="db688-109">Publish and deploy the following policies:</span></span>  
  
-   <span data-ttu-id="db688-110">消息架构的 SWIFT 基策略，包括 SWIFT_Reference_Policy.xml、 SWIFT_PartyIdentifier_Policy.xml 和网络规则策略 (SWIFT_NetworkRulexxx_Policy.xml) 部署架构。</span><span class="sxs-lookup"><span data-stu-id="db688-110">SWIFT base policies for message schema, including SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.xml, and network rule policies (SWIFT_NetworkRulexxx_Policy.xml) for deployed schemas.</span></span> <span data-ttu-id="db688-111">这些建议位于\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 策略。</span><span class="sxs-lookup"><span data-stu-id="db688-111">These are located in \<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies.</span></span> <span data-ttu-id="db688-112">发布和部署这些使用 BRE 部署实用工具。</span><span class="sxs-lookup"><span data-stu-id="db688-112">Publish and deploy these using the BRE Deployment Utility.</span></span>  
  
-   <span data-ttu-id="db688-113">与已部署的消息架构 （MTxxx_Master_Policy.xml 和 MTxxx_Validation_Policy.xml） 相关联的 Master 和验证策略。</span><span class="sxs-lookup"><span data-stu-id="db688-113">Master and validation policies associated with deployed message schemas (MTxxx_Master_Policy.xml and MTxxx_Validation_Policy.xml).</span></span> <span data-ttu-id="db688-114">这些建议位于\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MTxxx。</span><span class="sxs-lookup"><span data-stu-id="db688-114">These are located in \<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MTxxx.</span></span> <span data-ttu-id="db688-115">发布和部署这些使用 BRE 部署实用工具。</span><span class="sxs-lookup"><span data-stu-id="db688-115">Publish and deploy these using the BRE Deployment Utility.</span></span>  
  
-   <span data-ttu-id="db688-116">如果需要 BIC 验证与 BIC 验证 （BIC_Master_Policy.xml 和 BIC_Validation_Policy.xml） 相关联的 Master 和验证策略。</span><span class="sxs-lookup"><span data-stu-id="db688-116">Master and validation policies associated with BIC validation (BIC_Master_Policy.xml and BIC_Validation_Policy.xml), if BIC validation is required.</span></span> <span data-ttu-id="db688-117">这些建议位于\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 策略。</span><span class="sxs-lookup"><span data-stu-id="db688-117">These are located in \<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies.</span></span> <span data-ttu-id="db688-118">之前发布和部署这些策略，你必须使用的 SQL Server，BIC 数据库名称，名称来自定义 BIC_Master_Policy.xml 和集成安全值。</span><span class="sxs-lookup"><span data-stu-id="db688-118">Before publishing and deploying these policies, you must customize BIC_Master_Policy.xml with the names of the SQL Server, the BIC database name, and integrated security value.</span></span> <span data-ttu-id="db688-119">有关详细信息，请参阅[启用验证 Bank 标识符代码的](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="db688-119">For more information, see [Enabling Validation of Bank Identifier Codes](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md).</span></span> <span data-ttu-id="db688-120">发布和部署这些使用规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="db688-120">Publish and deploy these using the Rules Engine Deployment Wizard.</span></span>  
  
### <a name="to-deploy-bre-rules"></a><span data-ttu-id="db688-121">若要部署 BRE 规则</span><span class="sxs-lookup"><span data-stu-id="db688-121">To deploy BRE rules</span></span>  
  
1.  <span data-ttu-id="db688-122">运行 BRE 部署实用工具。</span><span class="sxs-lookup"><span data-stu-id="db688-122">Run the BRE Deployment Utility.</span></span> <span data-ttu-id="db688-123">有关详细信息，请参阅"部署 BRE 规则所有在一次"下面。</span><span class="sxs-lookup"><span data-stu-id="db688-123">For more information, see "Deploying BRE Rules All at Once" below.</span></span> <span data-ttu-id="db688-124">此实用程序将发布和部署以下：</span><span class="sxs-lookup"><span data-stu-id="db688-124">This utility will publish and deploy the following:</span></span>  
  
    -   <span data-ttu-id="db688-125">A4SWIFT_CodeLists.xml 和 A4SWIFT_Functions.xml 词汇</span><span class="sxs-lookup"><span data-stu-id="db688-125">A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml vocabularies</span></span>  
  
    -   <span data-ttu-id="db688-126">对于消息架构，包括 SWIFT_Reference_Policy.xml、 SWIFT_PartyIdentifier_Policy.xml 和网络规则策略 (SWIFT_NetworkRulexxx_Policy.xml) SWIFT 基策略</span><span class="sxs-lookup"><span data-stu-id="db688-126">SWIFT base policies for message schema, including SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.xml, and network rule policies (SWIFT_NetworkRulexxx_Policy.xml)</span></span>  
  
    -   <span data-ttu-id="db688-127">与已部署的消息架构 （MTxxx_Master_Policy.xml 和 MTxxx_Validation_Policy.xml） 相关联的 Master 和验证策略</span><span class="sxs-lookup"><span data-stu-id="db688-127">Master and validation policies associated with deployed message schemas (MTxxx_Master_Policy.xml and MTxxx_Validation_Policy.xml)</span></span>  
  
2.  <span data-ttu-id="db688-128">利用 SQL server，BIC 数据库名称和集成的安全值的名称自定义 BIC_Master_Policy.xml。</span><span class="sxs-lookup"><span data-stu-id="db688-128">Customize BIC_Master_Policy.xml with the names of the SQL server, the BIC database name, and integrated security value.</span></span> <span data-ttu-id="db688-129">有关详细信息，请参阅[启用验证 Bank 标识符代码的](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="db688-129">For more information, see [Enabling Validation of Bank Identifier Codes](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md).</span></span>  
  
3.  <span data-ttu-id="db688-130">运行规则引擎部署向导来发布和部署 BIC_Master_Policy.xml 和 BIC_Validation_Policy.xml (在\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 策略)。</span><span class="sxs-lookup"><span data-stu-id="db688-130">Run the Rules Engine Deployment Wizard to publish and deploy BIC_Master_Policy.xml and   BIC_Validation_Policy.xml (in \<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies).</span></span> <span data-ttu-id="db688-131">有关详细信息，请参阅"部署 BRE 规则一次"下面。</span><span class="sxs-lookup"><span data-stu-id="db688-131">For more information, see "Deploying BRE Rules One at a Time" below.</span></span>  
  
## <a name="tools-for-deploying-the-policies"></a><span data-ttu-id="db688-132">部署策略的工具</span><span class="sxs-lookup"><span data-stu-id="db688-132">Tools for Deploying the Policies</span></span>  
 <span data-ttu-id="db688-133">发布词汇和部署策略的最简单方法是使用业务规则引擎 (BRE) 部署实用工具在 A4SWIFT 软件开发工具包 (SDK)。</span><span class="sxs-lookup"><span data-stu-id="db688-133">The easiest way to publish the vocabularies and deploy the policies is by using the Business Rule Engine (BRE) Deployment Utility in the A4SWIFT Software Development Kit (SDK).</span></span> <span data-ttu-id="db688-134">你还可以通过执行这样[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]规则引擎部署向导，这一次执行相同任务的一个词汇或策略。</span><span class="sxs-lookup"><span data-stu-id="db688-134">You can also do so by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Rule Engine Deployment Wizard, which performs the same task one vocabulary or policy at a time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db688-135">BRE 部署实用工具不部署 BIC Master 策略和 BIC 验证策略。</span><span class="sxs-lookup"><span data-stu-id="db688-135">The BRE Deployment Utility does not deploy the BIC Master Policy and BIC Validation Policy.</span></span> <span data-ttu-id="db688-136">你必须部署这些使用规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="db688-136">You must deploy these using the Rule Engine Deployment wizard.</span></span>  
  
### <a name="deploying-bre-rules-all-at-once"></a><span data-ttu-id="db688-137">在一次部署 BRE 规则</span><span class="sxs-lookup"><span data-stu-id="db688-137">Deploying BRE Rules All at Once</span></span>  
 <span data-ttu-id="db688-138">业务规则引擎 (BRE) 部署实用工具执行一个步骤中的一系列的发布和部署任务。</span><span class="sxs-lookup"><span data-stu-id="db688-138">The Business Rule Engine (BRE) Deployment Utility performs a series of publishing and deployment tasks in one step.</span></span> <span data-ttu-id="db688-139">你必须重新运行部署实用工具随时架构添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="db688-139">You must rerun the deployment utility any time that you add a schema to your project.</span></span>  
  
##### <a name="to-deploy-bre-rules-using-the-bre-deployment-utility"></a><span data-ttu-id="db688-140">若要将 BRE 规则使用 BRE 部署实用工具部署</span><span class="sxs-lookup"><span data-stu-id="db688-140">To deploy BRE rules using the BRE Deployment Utility</span></span>  
  
1.  <span data-ttu-id="db688-141">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BRE 部署实用工具**.</span><span class="sxs-lookup"><span data-stu-id="db688-141">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="db688-142">在 BRE 部署实用工具的对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="db688-142">In the BRE Deployment Utility dialog box, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="db688-143">在.NET 全局程序集缓存对话框中，选择项目程序集，部署在[部署 A4SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="db688-143">In the .NET Global Assembly Cache dialog box, select the project assembly that you deployed in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md), and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="db688-144">在 BRE 部署实用工具的对话框中，单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="db688-144">In the BRE Deployment Utility dialog box, click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="db688-145">根据使用该程序集部署的架构，部署实用工具标识相关的规则，并将其发布与 BRE 一起使用。</span><span class="sxs-lookup"><span data-stu-id="db688-145">Based on the schemas you deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="db688-146">完成后，BRE 部署实用程序显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="db688-146">When complete, the BRE Deployment Utility displays the following message:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="db688-147">"部署已完成。</span><span class="sxs-lookup"><span data-stu-id="db688-147">"Deployment has completed.</span></span> <span data-ttu-id="db688-148">查看日志文件或业务规则编辑器的详细信息。"</span><span class="sxs-lookup"><span data-stu-id="db688-148">View the log file or Business Rule Composer for details."</span></span>  
  
5.  <span data-ttu-id="db688-149">关闭 BRE 部署实用工具的对话框。</span><span class="sxs-lookup"><span data-stu-id="db688-149">Close the BRE Deployment Utility dialog box.</span></span>  
  
6.  <span data-ttu-id="db688-150">打开[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器。</span><span class="sxs-lookup"><span data-stu-id="db688-150">Open [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer.</span></span> <span data-ttu-id="db688-151">浏览到\<*驱动器*\>: \Documents and Settings\All Users\Application 数据，并确认的日志文件 BREDeploymentLog.txt 是否显示在该驱动器。</span><span class="sxs-lookup"><span data-stu-id="db688-151">Browse to \<*drive*\>:\Documents and Settings\All Users\Application Data, and confirm that the log file BREDeploymentLog.txt appears in that drive.</span></span>  
  
7.  <span data-ttu-id="db688-152">重新启动的规则引擎更新服务。</span><span class="sxs-lookup"><span data-stu-id="db688-152">Restart the Rule Engine Update Service.</span></span> <span data-ttu-id="db688-153">通过单击来做到**启动**、 单击**运行**、 输入**services.msc**，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="db688-153">Do so by clicking **Start**, clicking **Run**, entering **services.msc**, and clicking **OK**.</span></span> <span data-ttu-id="db688-154">在**服务 （本地）** 窗口中，右键单击**规则引擎更新服务**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="db688-154">In the **Services (Local)** window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>  
  
### <a name="deploying-bre-rules-one-at-a-time"></a><span data-ttu-id="db688-155">一次部署 BRE 规则一个</span><span class="sxs-lookup"><span data-stu-id="db688-155">Deploying BRE Rules One at a Time</span></span>  
 <span data-ttu-id="db688-156">规则引擎部署向导可用于发布的词汇和一次部署一个策略。</span><span class="sxs-lookup"><span data-stu-id="db688-156">You can use the Rules Engine Deployment Wizard to publish vocabularies and deploy policies one at a time.</span></span> <span data-ttu-id="db688-157">有关词汇，此过程涉及到导入和从一个步骤中的文件发布到数据库的词汇。</span><span class="sxs-lookup"><span data-stu-id="db688-157">For a vocabulary, this process involves importing and publishing the vocabulary to the database from a file in one step.</span></span> <span data-ttu-id="db688-158">对于策略，该过程包括导入和在一个步骤中，发布策略并将在另一个步骤中对其进行部署。</span><span class="sxs-lookup"><span data-stu-id="db688-158">For a policy, the process involves importing and publishing the policy in one step, and then deploying it in another step.</span></span>  
  
##### <a name="to-deploy-bre-rules-using-the-rules-engine-deployment-wizard"></a><span data-ttu-id="db688-159">若要部署 BRE 规则使用规则引擎部署向导</span><span class="sxs-lookup"><span data-stu-id="db688-159">To deploy BRE rules Using the Rules Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="db688-160">单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则引擎部署向导**.</span><span class="sxs-lookup"><span data-stu-id="db688-160">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
2.  <span data-ttu-id="db688-161">在欢迎使用规则引擎部署向导页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="db688-161">On the Welcome to the Rules Engine Deployment Wizard page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="db688-162">在部署任务页上，单击**导入并将其从文件发布到数据库的策略/词汇**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="db688-162">On the Deployment Task page, click **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="db688-163">在策略存储区页上，在**SQL Server 名称列表**，选择你的服务器，然后在**选定的服务器上的配置数据库**列表中，选择**BizTalkRuleEngineDb**。</span><span class="sxs-lookup"><span data-stu-id="db688-163">On the Policy Store page, in the **SQL Server Name list**, select your server, and in the **Configuration Database on selected server** list, select **BizTalkRuleEngineDb**.</span></span> <span data-ttu-id="db688-164">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="db688-164">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="db688-165">在导入规则引擎策略/词汇文件页上，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="db688-165">On the Import Rules Engine Policy/Vocabulary file page, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="db688-166">在从文件页上，导入策略中**查找**下拉列表中，移动到以下文件夹，根据的词汇和策略之一：</span><span class="sxs-lookup"><span data-stu-id="db688-166">On the Import Policy from file page, in the **Look in** drop-down list, move to one of the following folders, depending upon the vocabulary or policy:</span></span>  
  
    -   <span data-ttu-id="db688-167">\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>A4SWIFT_ 的 \Base Policies\VocabularyCodeLists.xml 和 A4SWIFT_Functions.xml</span><span class="sxs-lookup"><span data-stu-id="db688-167">\<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies\Vocabulary for A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml</span></span>  
  
    -   <span data-ttu-id="db688-168">\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base SWIFT_Reference_Policy.xml，策略SWIFT_PartyIdentifier_Policy.xml、 网络规则策略、 BIC_Master_Policy.xml 和 BIC_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="db688-168">\<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies for SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.xml, network rule policies, BIC_Master_Policy.xml, and BIC_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="db688-169">\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MTxxx 的 master 和验证与已部署的消息架构关联的策略</span><span class="sxs-lookup"><span data-stu-id="db688-169">\<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MTxxx for the master and validation policies associated with deployed message schemas</span></span>  
  
7.  <span data-ttu-id="db688-170">选择的策略，你想要部署，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="db688-170">Select the policy that you want to deploy, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="db688-171">在导入规则引擎策略/词汇文件页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="db688-171">On the Import Rules Engine Policy/Vocabulary file page, click **Next**.</span></span>  
  
9. <span data-ttu-id="db688-172">在准备页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="db688-172">On the Ready page, click **Next**.</span></span>  
  
10. <span data-ttu-id="db688-173">在导入策略/词汇页上，验证该命令已成功，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="db688-173">On the Importing Policy/Vocabulary page, verify that the command succeeded, and then click **Next**.</span></span>  
  
11. <span data-ttu-id="db688-174">如果你想要部署策略，在完成规则引擎部署向导页上，单击**再次运行此向导**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="db688-174">If you want to deploy a policy, on the Completing the Rules Engine Deployment Wizard page, click **Run this Wizard again**, and then click **Finish**.</span></span>  
  
12. <span data-ttu-id="db688-175">在欢迎使用规则引擎部署向导页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="db688-175">On the Welcome to the Rules Engine Deployment Wizard page, click **Next**.</span></span>  
  
13. <span data-ttu-id="db688-176">在部署任务页上，单击**部署策略**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="db688-176">On the Deployment Task page, click **Deploy Policy**, and then click **Next**.</span></span>  
  
14. <span data-ttu-id="db688-177">在策略存储区页上，在**SQL Server 名称列表**，选择你的服务器，然后在**选定的服务器上的配置数据库**列表中，选择**BizTalkRuleEngineDb**。</span><span class="sxs-lookup"><span data-stu-id="db688-177">On the Policy Store page, in the **SQL Server Name list**, select your server, and in the **Configuration Database on selected server** list, select **BizTalkRuleEngineDb**.</span></span> <span data-ttu-id="db688-178">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="db688-178">Click **Next**.</span></span>  
  
15. <span data-ttu-id="db688-179">在部署策略页上，单击向下箭头旁边**规则引擎策略**文本框中，选择你刚策略发布，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="db688-179">On the Deploy Policy page, click the down arrow next to the **Rules Engine Policy** text box, select the policy you just published, and then click **Next**.</span></span>  
  
16. <span data-ttu-id="db688-180">在准备页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="db688-180">On the Ready page, click **Next**.</span></span>  
  
17. <span data-ttu-id="db688-181">上**导入策略/词汇**页上，验证该命令成功，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="db688-181">On the **Importing Policy/Vocabulary** page, verify that the command succeeded, and then click **Next**.</span></span>  
  
18. <span data-ttu-id="db688-182">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="db688-182">Click **Finish**.</span></span>  
  
19. <span data-ttu-id="db688-183">重新启动**规则引擎更新服务**。</span><span class="sxs-lookup"><span data-stu-id="db688-183">Restart the **Rule Engine Update Service**.</span></span> <span data-ttu-id="db688-184">通过单击来做到**启动**、 单击**运行**、 输入**services.msc**，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="db688-184">Do so by clicking **Start**, clicking **Run**, entering **services.msc**, and clicking **OK**.</span></span> <span data-ttu-id="db688-185">在**服务 （本地）** 窗口中，右键单击**规则引擎更新服务**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="db688-185">In the **Services (Local)** window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>