---
title: "演练： 部署策略 |Microsoft 文档"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 205760e2-9cd4-496f-93cd-0f93bc5d3231
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00c603a3a0c52d735441858af6a2f602c30d1f51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-deploying-the-policy"></a><span data-ttu-id="9c154-102">演练： 部署策略</span><span class="sxs-lookup"><span data-stu-id="9c154-102">Walkthrough: Deploying the Policy</span></span>
<span data-ttu-id="9c154-103">本演练提供了部署的分步说明**ProcessPurchaseOrder**以下三种方式的策略：</span><span class="sxs-lookup"><span data-stu-id="9c154-103">This walkthrough provides step-by-step instructions for deploying the **ProcessPurchaseOrder** policy in the following three ways:</span></span>  
  
-   <span data-ttu-id="9c154-104">导出和导入策略，通过使用业务规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="9c154-104">Exporting and importing the policy by using the Business Rules Engine Deployment Wizard.</span></span>  
  
-   <span data-ttu-id="9c154-105">通过使用 BizTalk Server 管理控制台将策略导出到某一 XML 文件或者从某一 XML 文件导入策略。</span><span class="sxs-lookup"><span data-stu-id="9c154-105">Exporting the policy to an XML file and importing the policy from an XML file by using the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="9c154-106">通过使用 BizTalk Server 管理控制台将策略作为 XML 文件的一部分导出并导入该 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="9c154-106">Exporting the policy as part of an MSI file and importing the MSI file by using BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c154-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="9c154-107">Prerequisites</span></span>  
 <span data-ttu-id="9c154-108">必须完成[演练： 跟踪策略执行](../core/walkthrough-tracking-policy-execution.md)执行本演练之前的演练。</span><span class="sxs-lookup"><span data-stu-id="9c154-108">You must complete the [Walkthrough: Tracking Policy Execution](../core/walkthrough-tracking-policy-execution.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="9c154-109">本演练的概述</span><span class="sxs-lookup"><span data-stu-id="9c154-109">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="9c154-110">本主题包含下列三个演练：</span><span class="sxs-lookup"><span data-stu-id="9c154-110">This topic  contains the following three walkthroughs:</span></span>  
  
1.  <span data-ttu-id="9c154-111">第一个演练包含用于部署的过程**ProcessPurchaseOrder**通过业务规则引擎部署向导的策略。</span><span class="sxs-lookup"><span data-stu-id="9c154-111">The first walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using the Business Rules Engine Deployment Wizard.</span></span> <span data-ttu-id="9c154-112">下表描述此演练中的各个过程。</span><span class="sxs-lookup"><span data-stu-id="9c154-112">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="9c154-113">过程标题</span><span class="sxs-lookup"><span data-stu-id="9c154-113">Procedure title</span></span>|<span data-ttu-id="9c154-114">过程说明</span><span class="sxs-lookup"><span data-stu-id="9c154-114">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="9c154-115">若要使用业务规则引擎部署向导导出 POVocabulary 1.0 和 1.1 版</span><span class="sxs-lookup"><span data-stu-id="9c154-115">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="9c154-116">提供用于导出的 1.0 和 1.1 版的分步说明**POVocabulary**词汇到 XML 文件使用业务规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="9c154-116">Provides step-by-step instructions for exporting versions 1.0 and 1.1 of the **POVocabulary** vocabulary to XML files by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="9c154-117">使用业务规则引擎部署向导来导出 ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="9c154-117">To export ProcessPurchaseOrder 1.3 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="9c154-118">提供用于导出 1.3 版的分步说明**ProcessPurchaseOrder**策略应用到 XML 文件使用业务规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="9c154-118">Provides step-by-step instructions for exporting version 1.3 of the **ProcessPurchaseOrder** policy to an XML file by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="9c154-119">删除 ProcessPurchaseOrder 和 POVocabulary</span><span class="sxs-lookup"><span data-stu-id="9c154-119">To delete ProcessPurchaseOrder and POVocabulary</span></span>|<span data-ttu-id="9c154-120">提供有关删除的分步说明**ProcessPurchaseOrder**策略和**POVocabulary**词汇，以便可以测试导入 XML 文件来重新创建它们。</span><span class="sxs-lookup"><span data-stu-id="9c154-120">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary so that you can test importing the XML files to re-create them.</span></span>|  
    |<span data-ttu-id="9c154-121">从 XML 导入以重新创建 POVocabulary 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="9c154-121">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>|<span data-ttu-id="9c154-122">提供你在重新创建的第一个过程中创建的导入词汇 XML 文件的分步说明**POVocabulary**词汇。</span><span class="sxs-lookup"><span data-stu-id="9c154-122">Provides step-by-step instructions for importing the vocabulary XML file you created in the first procedure to re-create the **POVocabulary** vocabulary.</span></span>|  
    |<span data-ttu-id="9c154-123">确认 POVocabulary 1.0 和 1.1 已重新创建</span><span class="sxs-lookup"><span data-stu-id="9c154-123">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>|<span data-ttu-id="9c154-124">提供有关使用业务规则编辑器来验证分步说明的该版本 1.0 和 1.1 **POVocabulary**重新创建。</span><span class="sxs-lookup"><span data-stu-id="9c154-124">Provides step-by-step instructions for using the Business Rule Composer to verify that versions 1.0 and 1.1 of **POVocabulary** are re-created.</span></span>|  
    |<span data-ttu-id="9c154-125">从 XML 导入以重新创建 ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="9c154-125">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>|<span data-ttu-id="9c154-126">提供你在重新创建 1.3 版的第二个过程中创建的导入策略 XML 文件的分步说明**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="9c154-126">Provides step-by-step instructions for importing the policy XML file you created in the second procedure to re-create version 1.3 of the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="9c154-127">验证 ProcessPurchaseOrder 1.3 已重新创建</span><span class="sxs-lookup"><span data-stu-id="9c154-127">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>|<span data-ttu-id="9c154-128">提供有关使用业务规则编辑器来验证该版本 1.3 的分步说明**ProcessPurchaseOrder**策略是重新创建。</span><span class="sxs-lookup"><span data-stu-id="9c154-128">Provides step-by-step instructions for using the Business Rule Composer to verify that version 1.3 of the **ProcessPurchaseOrder** policy is re-created.</span></span>|  
  
2.  <span data-ttu-id="9c154-129">第二个演练中包含的部署过程**ProcessPurchaseOrder**使用 XML 文件的策略导出从 BizTalk Server 管理控制台下表介绍了在此过程演练。</span><span class="sxs-lookup"><span data-stu-id="9c154-129">The second walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an XML file exported from the BizTalk Server Administration console The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="9c154-130">过程标题</span><span class="sxs-lookup"><span data-stu-id="9c154-130">Procedure title</span></span>|<span data-ttu-id="9c154-131">过程说明</span><span class="sxs-lookup"><span data-stu-id="9c154-131">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="9c154-132">将 ProcessPurchaseOrder 1.3 策略和 POVocabulary 词汇导出到某一 XML 文件</span><span class="sxs-lookup"><span data-stu-id="9c154-132">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>|<span data-ttu-id="9c154-133">提供有关使用 BizTalk Server 管理控制台导出的分步说明**ProcessPurchaseOrder**策略和**POVocabulary** XML 文件的词汇。</span><span class="sxs-lookup"><span data-stu-id="9c154-133">Provides step-by-step instructions for using the BizTalk Server Administration console to export the **ProcessPurchaseOrder** policy and the **POVocabulary** vocabulary to an XML file.</span></span>|  
    |<span data-ttu-id="9c154-134">删除 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="9c154-134">To delete the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="9c154-135">提供有关删除的分步说明**ProcessPurchaseOrder**策略从**RuleTestApp**和规则引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="9c154-135">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy from **RuleTestApp** and the rule engine database.</span></span>|  
    |<span data-ttu-id="9c154-136">导入 XML 文件以便重新创建 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="9c154-136">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="9c154-137">提供有关导入 XML 文件的分步说明重新创建的第一个步骤中导出**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="9c154-137">Provides step-by-step instructions for importing the XML file you exported in the first procedure to re-create the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="9c154-138">将 ProcessPurchaseOrder 策略添加到 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="9c154-138">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>|<span data-ttu-id="9c154-139">提供有关将添加的分步说明**ProcessPurchaseOrder**策略应用到**RuleTestApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c154-139">Provides step-by-step instructions for adding the **ProcessPurchaseOrder** policy to the **RuleTestApp** application.</span></span>|  
  
3.  <span data-ttu-id="9c154-140">第三个演练中包含的部署过程**ProcessPurchaseOrder**从 BizTalk Server 管理控制台导出策略通过使用 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="9c154-140">The third walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an MSI file exported from the BizTalk Server Administration console.</span></span> <span data-ttu-id="9c154-141">下表描述此演练中的各个过程。</span><span class="sxs-lookup"><span data-stu-id="9c154-141">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="9c154-142">过程标题</span><span class="sxs-lookup"><span data-stu-id="9c154-142">Procedure title</span></span>|<span data-ttu-id="9c154-143">过程具有针对以下操作的分步说明</span><span class="sxs-lookup"><span data-stu-id="9c154-143">Procedure has step-by-step instructions for</span></span>|  
    |---------------------|---------------------------------------------------|  
    |<span data-ttu-id="9c154-144">将 RuleTestApp 应用程序导出到某一 MSI 文件</span><span class="sxs-lookup"><span data-stu-id="9c154-144">To export the RuleTestApp application to an MSI file</span></span>|<span data-ttu-id="9c154-145">提供用于导出的分步说明**RuleTestApp**到 MSI 文件，用于更高版本进行重新创建应用程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c154-145">Provides step-by-step instructions for exporting the **RuleTestApp** application to an MSI file, which is used later to re-create the application.</span></span>|  
    |<span data-ttu-id="9c154-146">删除 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="9c154-146">To delete the RuleTestApp application</span></span>|<span data-ttu-id="9c154-147">提供有关删除的分步说明**RuleTestApp**应用程序，以便你可以测试重新创建应用程序使用的 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="9c154-147">Provides step-by-step instructions for deleting the **RuleTestApp** application so that you can test re-creating the application by using the MSI file.</span></span>|  
    |<span data-ttu-id="9c154-148">验证 ProcessPurchaseOrder 策略和 POVocabulary 词汇已删除</span><span class="sxs-lookup"><span data-stu-id="9c154-148">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>|<span data-ttu-id="9c154-149">提供有关使用业务规则编辑器来验证的分步说明**ProcessPurchaseOrder**删除策略和 POVocabulary 词汇。</span><span class="sxs-lookup"><span data-stu-id="9c154-149">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and POVocabulary vocabulary are deleted.</span></span>|  
    |<span data-ttu-id="9c154-150">导入 MSI 文件以便重新创建 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="9c154-150">To import the MSI file to re-create the RuleTestApp application</span></span>|<span data-ttu-id="9c154-151">提供使用 BizTalk Server 管理控制台将导入的 MSI 文件以重新创建的指导**RuleTestApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c154-151">Provides step-by-step instructions for using the BizTalk Server Administration console to import the MSI file to re-create the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="9c154-152">验证 ProcessPurchaseOrder 策略已添加到 RuleTestApp</span><span class="sxs-lookup"><span data-stu-id="9c154-152">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>|<span data-ttu-id="9c154-153">提供有关使用 BizTalk Server 管理控制台以验证的分步说明**ProcessPurchaseOrder**策略添加到**RuleTestApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c154-153">Provides step-by-step instructions for using the BizTalk Server Administration console to verify that the **ProcessPurchaseOrder** policy is added to the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="9c154-154">确认 ProcessPurchaseOrder 策略和 POVocabulary 词汇已重新创建</span><span class="sxs-lookup"><span data-stu-id="9c154-154">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>|<span data-ttu-id="9c154-155">提供有关使用业务规则编辑器来验证的分步说明**ProcessPurchaseOrder**策略和**POVocabulary**词汇将重新创建。</span><span class="sxs-lookup"><span data-stu-id="9c154-155">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary are re-created.</span></span>|  
    |<span data-ttu-id="9c154-156">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="9c154-156">To test the solution</span></span>|<span data-ttu-id="9c154-157">提供用于测试解决方案的分步说明。</span><span class="sxs-lookup"><span data-stu-id="9c154-157">Provides step-by-step instructions for testing the solution.</span></span>|  
  
## <a name="procedures-for-deploying-the-processpurchaseorder-policy-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="9c154-158">使用业务规则引擎部署向导部署 ProcessPurchaseOrder 策略的过程</span><span class="sxs-lookup"><span data-stu-id="9c154-158">Procedures for Deploying the ProcessPurchaseOrder Policy by Using the Business Rules Engine Deployment Wizard</span></span>  
  
#### <a name="to-export-povocabulary-10-and-11-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="9c154-159">若要使用业务规则引擎部署向导导出 POVocabulary 1.0 和 1.1 版</span><span class="sxs-lookup"><span data-stu-id="9c154-159">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="9c154-160">上**启动**菜单上，打开**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="9c154-160">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-161">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9c154-161">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="9c154-162">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="9c154-162">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="9c154-163">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="9c154-163">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="9c154-164">上**部署任务**页上，选择**导出策略/词汇文件从数据库**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-164">On the **Deployment Task** page, select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="9c154-165">上**策略存储区**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-165">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="9c154-166">上**导出策略/词汇**页上，单击**词汇**。</span><span class="sxs-lookup"><span data-stu-id="9c154-166">On the **Export Policy/Vocabulary** page, click **Vocabulary**.</span></span>  
  
6.  <span data-ttu-id="9c154-167">选择**POVocabulary.1.0**从下拉列表中为**策略/词汇**，键入或浏览以将 XML 输出文件名称指定为**C:\BRE-walkthroughs\POVocabulary10.xml**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-167">Select **POVocabulary.1.0** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary10.xml**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="9c154-168">上**准备**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-168">On the **Ready** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="9c154-169">上**导出策略/词汇**页上，单击**下一步。**</span><span class="sxs-lookup"><span data-stu-id="9c154-169">On the **Exporting Policy/Vocabulary** page, click **Next.**</span></span>  
  
9. <span data-ttu-id="9c154-170">选择**再次运行此向导**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="9c154-170">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="9c154-171">由于你选择了**再次运行此向导**，向导的第一个屏幕会再次出现。</span><span class="sxs-lookup"><span data-stu-id="9c154-171">Because you selected **Run this wizard again**, the first screen of the wizard appears again.</span></span>  
  
10. <span data-ttu-id="9c154-172">重复步骤 2 到 6。</span><span class="sxs-lookup"><span data-stu-id="9c154-172">Repeat steps 2-6.</span></span>  
  
11. <span data-ttu-id="9c154-173">选择**POVocabulary.1.1**从下拉列表中为**策略/词汇**，键入或浏览以将 XML 输出文件名称指定为**C:\BRE-walkthroughs\POVocabulary11.xml**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-173">Select **POVocabulary.1.1** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary11.xml**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="9c154-174">重复步骤 8 和 9。</span><span class="sxs-lookup"><span data-stu-id="9c154-174">Repeat steps 8 and 9.</span></span>  
  
13. <span data-ttu-id="9c154-175">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="9c154-175">Click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-176">你需要导出版本 1.0 和 1.1 版**POVocabulary**因为**ProcessPurchaseOrder** 1.3 取决于这两个版本**POVocabulary**。</span><span class="sxs-lookup"><span data-stu-id="9c154-176">You need to export both version 1.0 and version 1.1 of **POVocabulary** because **ProcessPurchaseOrder** 1.3 depends on both versions of **POVocabulary**.</span></span> <span data-ttu-id="9c154-177">**项允许的最大数目**定义使用从版本 1.1 的词汇。</span><span class="sxs-lookup"><span data-stu-id="9c154-177">The **Maximum number of items allowed** definition is used from version 1.1 of the vocabulary.</span></span> <span data-ttu-id="9c154-178">**请求数量**和**请求状态**定义使用从版本 1.0。</span><span class="sxs-lookup"><span data-stu-id="9c154-178">The **Requested Quantity** and **Request Status** definitions are used from version 1.0.</span></span>  
  
#### <a name="to-export-processpurchaseorder-13-by-using-the-business-rule-engine-deployment-wizard"></a><span data-ttu-id="9c154-179">若要使用业务规则引擎部署向导导出 ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="9c154-179">To export ProcessPurchaseOrder 1.3 by using the Business Rule Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="9c154-180">上**启动**菜单上，打开**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="9c154-180">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-181">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9c154-181">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="9c154-182">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="9c154-182">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="9c154-183">上**欢迎规则引擎部署向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-183">On the **Welcome to the Rules Engine Deployment Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="9c154-184">选择**导出策略/词汇文件从数据库**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-184">Select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="9c154-185">上**策略存储区**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-185">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="9c154-186">验证**策略**选项。</span><span class="sxs-lookup"><span data-stu-id="9c154-186">Verify that the **Policy** option is selected.</span></span>  
  
6.  <span data-ttu-id="9c154-187">选择**ProcessPurchaseOrder.1.3**从下拉列表中为**策略/词汇**。</span><span class="sxs-lookup"><span data-stu-id="9c154-187">Select **ProcessPurchaseOrder.1.3** from the drop-down list for **Policy/Vocabulary**.</span></span>  
  
7.  <span data-ttu-id="9c154-188">键入或浏览以指定要**C:\BRE-walkthroughs\ProcessPOPolicy13.xml**作为 XML 输出文件的名称。</span><span class="sxs-lookup"><span data-stu-id="9c154-188">Type or browse to specify **C:\BRE-walkthroughs\ProcessPOPolicy13.xml** as the XML output file name.</span></span>  
  
8.  <span data-ttu-id="9c154-189">单击**下一步**三次，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="9c154-189">Click **Next** thrice, and then click **Finish**.</span></span>  
  
#### <a name="to-delete-processpurchaseorder-and-povocabulary"></a><span data-ttu-id="9c154-190">删除 ProcessPurchaseOrder 和 POVocabulary</span><span class="sxs-lookup"><span data-stu-id="9c154-190">To delete ProcessPurchaseOrder and POVocabulary</span></span>  
  
1.  <span data-ttu-id="9c154-191">上**启动**菜单上，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="9c154-191">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="9c154-192">如果必须业务规则编辑器已打开，按 F5 或单击**重新加载**上**文件**菜单可对其进行刷新。</span><span class="sxs-lookup"><span data-stu-id="9c154-192">If you have Business Rule Composer already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-193">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9c154-193">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="9c154-194">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="9c154-194">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="9c154-195">在策略资源管理器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.0**，然后单击**删除**.</span><span class="sxs-lookup"><span data-stu-id="9c154-195">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Delete**.</span></span> <span data-ttu-id="9c154-196">如果**删除**是禁用，右键单击**版本 1.0**，然后单击**取消部署后再次**。</span><span class="sxs-lookup"><span data-stu-id="9c154-196">If **Delete** is disabled, right-click **Version 1.0**, and then click **Undeploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-197">已部署的策略版本不能删除。</span><span class="sxs-lookup"><span data-stu-id="9c154-197">The deployed policy versions cannot be deleted.</span></span> <span data-ttu-id="9c154-198">您必须首先取消部署策略，然后才能删除策略版本。</span><span class="sxs-lookup"><span data-stu-id="9c154-198">You must undeploy a policy before deleting a policy version.</span></span>  
  
3.  <span data-ttu-id="9c154-199">单击**是**确认消息框中。</span><span class="sxs-lookup"><span data-stu-id="9c154-199">Click **Yes** in the confirmation message box.</span></span>  
  
4.  <span data-ttu-id="9c154-200">重复步骤 2 和 3 以删除**版本 1.1**。</span><span class="sxs-lookup"><span data-stu-id="9c154-200">Repeat steps 2 and 3 to delete **Version 1.1**.</span></span>  
  
5.  <span data-ttu-id="9c154-201">重复步骤 2 和 3 以删除**版本 1.2**。</span><span class="sxs-lookup"><span data-stu-id="9c154-201">Repeat steps 2 and 3 to delete **Version 1.2**.</span></span>  
  
6.  <span data-ttu-id="9c154-202">右键单击**版本 1.3-部署**，然后单击**取消部署后再次**。</span><span class="sxs-lookup"><span data-stu-id="9c154-202">Right-click **Version 1.3 - Deployed**, and then click **Undeploy**.</span></span> <span data-ttu-id="9c154-203">如果**取消部署后再次**选项处于禁用状态，忽略此步骤。</span><span class="sxs-lookup"><span data-stu-id="9c154-203">If the **Undeploy** option is disabled, ignore this step.</span></span>  
  
7.  <span data-ttu-id="9c154-204">在事实浏览器窗口中，展开**词汇**，右键单击**POVocabulary**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="9c154-204">In the Facts Explorer window, expand **Vocabularies**, right-click **POVocabulary**, and then click **Delete**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a><span data-ttu-id="9c154-205">从 XML 导入以重新创建 POVocabulary 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="9c154-205">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>  
  
1.  <span data-ttu-id="9c154-206">上**启动**菜单上，打开**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="9c154-206">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-207">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9c154-207">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="9c154-208">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="9c154-208">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="9c154-209">上**欢迎规则引擎部署向导**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-209">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="9c154-210">上**部署任务**页上，选择**导入并将其从文件发布到数据库的策略/词汇**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-210">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="9c154-211">上**策略存储区**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-211">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="9c154-212">浏览并选择**POVocabulary10.xml**第一个过程中创建的文件。</span><span class="sxs-lookup"><span data-stu-id="9c154-212">Browse and select the **POVocabulary10.xml** file you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="9c154-213">单击**打开**或双击**POVocabulary10.xml**。</span><span class="sxs-lookup"><span data-stu-id="9c154-213">Click **Open** or double-click **POVocabulary10.xml**.</span></span>  
  
7.  <span data-ttu-id="9c154-214">单击**下一步**在业务规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="9c154-214">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="9c154-215">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="9c154-215">Click **Next**.</span></span>  
  
9. <span data-ttu-id="9c154-216">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="9c154-216">Click **Next**.</span></span>  
  
10. <span data-ttu-id="9c154-217">选择**再次运行此向导**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="9c154-217">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="9c154-218">重复步骤 2-9 可以导入**POVocabulary11.xml**。</span><span class="sxs-lookup"><span data-stu-id="9c154-218">Repeat steps 2-9 to import **POVocabulary11.xml**.</span></span>  
  
12. <span data-ttu-id="9c154-219">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="9c154-219">Click **Finish**.</span></span>  
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a><span data-ttu-id="9c154-220">确认 POVocabulary 1.0 和 1.1 已重新创建</span><span class="sxs-lookup"><span data-stu-id="9c154-220">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>  
  
1.  <span data-ttu-id="9c154-221">上**启动**菜单上，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="9c154-221">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="9c154-222">如果你有已打开它，按 F5 或单击**重新加载**上**文件**菜单可对其进行刷新。</span><span class="sxs-lookup"><span data-stu-id="9c154-222">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-223">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9c154-223">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="9c154-224">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="9c154-224">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="9c154-225">在事实浏览器窗口中，单击**词汇**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9c154-225">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
3.  <span data-ttu-id="9c154-226">展开**词汇**，并且你应看到**POVocabulary**。</span><span class="sxs-lookup"><span data-stu-id="9c154-226">Expand **Vocabularies**, and you should see **POVocabulary**.</span></span>  
  
4.  <span data-ttu-id="9c154-227">展开**POVocabulary**，并且你应看到**版本 1.0**和**版本 1.1**。</span><span class="sxs-lookup"><span data-stu-id="9c154-227">Expand **POVocabulary**, and you should see **Version 1.0** and **Version 1.1**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a><span data-ttu-id="9c154-228">从 XML 导入以重新创建 ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="9c154-228">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>  
  
1.  <span data-ttu-id="9c154-229">上**启动**菜单上，打开**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="9c154-229">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-230">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9c154-230">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="9c154-231">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="9c154-231">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="9c154-232">上**欢迎规则引擎部署向导**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-232">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="9c154-233">上**部署任务**页上，选择**导入和从文件中的文件要数据库发布到数据库的策略/词汇**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-233">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from fileto database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="9c154-234">上**策略存储区**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-234">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="9c154-235">浏览并选择**ProcessPOPolicy13.xml**在本演练前面创建的文件。</span><span class="sxs-lookup"><span data-stu-id="9c154-235">Browse and select the **ProcessPOPolicy13.xml** file you created earlier in this walkthrough.</span></span>  
  
6.  <span data-ttu-id="9c154-236">单击**打开**或双击**ProcessPOPolicy13.xml**。</span><span class="sxs-lookup"><span data-stu-id="9c154-236">Click **Open** or double-click **ProcessPOPolicy13.xml**.</span></span>  
  
7.  <span data-ttu-id="9c154-237">单击**下一步**在业务规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="9c154-237">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="9c154-238">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="9c154-238">Click **Next**.</span></span>  
  
9. <span data-ttu-id="9c154-239">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="9c154-239">Click **Next**, and then click **Finish**.</span></span>  
  
#### <a name="to-verify-that-processpurchaseorder-13-is-re-created"></a><span data-ttu-id="9c154-240">验证 ProcessPurchaseOrder 1.3 已重新创建</span><span class="sxs-lookup"><span data-stu-id="9c154-240">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>  
  
1.  <span data-ttu-id="9c154-241">上**启动**菜单上，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="9c154-241">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="9c154-242">如果你有已打开它，按 F5 或单击**重新加载**上**文件**菜单可对其进行刷新。</span><span class="sxs-lookup"><span data-stu-id="9c154-242">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-243">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9c154-243">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="9c154-244">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="9c154-244">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="9c154-245">在策略资源管理器窗口中，展开**策略**，你应看到**ProcessPurchaseOrder**。</span><span class="sxs-lookup"><span data-stu-id="9c154-245">In the Policy Explorer window, expand **Policies** and you should see **ProcessPurchaseOrder**.</span></span>  
  
3.  <span data-ttu-id="9c154-246">展开**ProcessPurchaseOrder** ，你应看到**版本 1.3-发布**。</span><span class="sxs-lookup"><span data-stu-id="9c154-246">Expand **ProcessPurchaseOrder** and you should see **Version 1.3 - Published**.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a><span data-ttu-id="9c154-247">通过使用从 BizTalk Server 管理控制台导出的 XML 文件部署策略的过程</span><span class="sxs-lookup"><span data-stu-id="9c154-247">Procedures for Deploying the Policy by Using an XML file Exported from the BizTalk Server Administration Console</span></span>  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a><span data-ttu-id="9c154-248">将 ProcessPurchaseOrder 1.3 策略和 POVocabulary 词汇导出到某一 XML 文件</span><span class="sxs-lookup"><span data-stu-id="9c154-248">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>  
  
1.  <span data-ttu-id="9c154-249">上**启动**菜单上，打开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9c154-249">On the **Start** menu, open [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span> <span data-ttu-id="9c154-250">如果已打开该工具，请按 F5 键刷新。</span><span class="sxs-lookup"><span data-stu-id="9c154-250">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="9c154-251">展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**应用程序**，然后展开**RuleTestApp**.</span><span class="sxs-lookup"><span data-stu-id="9c154-251">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Applications**, and then expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="9c154-252">单击**策略**并确保你看到 ProcessPurchaseOrder 1.3 策略列表中的。</span><span class="sxs-lookup"><span data-stu-id="9c154-252">Click **Policies** and make sure that you see the ProcessPurchaseOrder 1.3 policy in the list.</span></span>  
  
4.  <span data-ttu-id="9c154-253">右键单击**ProcessPurchaseOrder**，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="9c154-253">Right-click **ProcessPurchaseOrder**, and then click **Export**.</span></span>  
  
5.  <span data-ttu-id="9c154-254">在**导出策略**对话框框中，请确保**ProcessPurchaseOrder**策略和**POVocabulary**选择。</span><span class="sxs-lookup"><span data-stu-id="9c154-254">In the **Export Policies** dialog box, make sure the **ProcessPurchaseOrder** policy and the **POVocabulary** are selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-255">你可以通过右键单击导出为 XML 文件的应用程序中的所有策略**RuleTest** ，然后单击**都导出**上**策略**菜单。</span><span class="sxs-lookup"><span data-stu-id="9c154-255">You can export all the policies in an application to an XML file by right-clicking **RuleTest** and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="9c154-256">这样，您就可以将此应用程序使用的所有策略和词汇都导出到单个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="9c154-256">This way you can export all the policies and vocabulary used by this application to a single XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-257">你可以通过右键单击导出到 XML 文件的所有应用程序中的所有策略**应用程序**节点，然后单击**都导出**上**策略**菜单。</span><span class="sxs-lookup"><span data-stu-id="9c154-257">You can export all the policies in all the applications to an XML file by right-clicking the **Applications** node and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="9c154-258">这样，您就可以将所有应用程序使用的所有策略和词汇都导出到单个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="9c154-258">This way you can export all the policies and vocabularies used by all the applications into a single XML file.</span></span>  
  
6.  <span data-ttu-id="9c154-259">指定输出 XML 文件的名称 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9c154-259">Specify an output XML file name (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**), and then click **Ok**.</span></span>  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a><span data-ttu-id="9c154-260">删除 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="9c154-260">To delete the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="9c154-261">在 BizTalk Server 管理中，右键单击**ProcessPurchaseOrder**在列表中，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="9c154-261">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** in the list, and then click **Remove**.</span></span>  
  
2.  <span data-ttu-id="9c154-262">单击**是**中**删除策略**消息框。</span><span class="sxs-lookup"><span data-stu-id="9c154-262">Click **Yes** in the **Remove Policy** message box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-263">如果该策略为已部署状态，则无法删除它。</span><span class="sxs-lookup"><span data-stu-id="9c154-263">If the policy is in the deployed state, it cannot be removed.</span></span> <span data-ttu-id="9c154-264">右键单击**ProcessPurchaseOrder**，然后单击**取消部署后再次**取消部署策略。</span><span class="sxs-lookup"><span data-stu-id="9c154-264">Right-click **ProcessPurchaseOrder**, and then click **Undeploy** to undeploy the policy.</span></span> <span data-ttu-id="9c154-265">**删除**未部署此策略时，菜单项是否可用。</span><span class="sxs-lookup"><span data-stu-id="9c154-265">The **Remove** menu item is available when the policy is undeployed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-266">在其上的词汇**ProcessPurchaseOrder**策略依赖，在这种情况下**POVocabulary**，也将被删除。</span><span class="sxs-lookup"><span data-stu-id="9c154-266">The vocabularies on which the **ProcessPurchaseOrder** policy depends, in this case **POVocabulary**, are also deleted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-267">在您从某一应用程序删除策略时，该策略以及它所依赖的词汇也将从规则引擎数据库中删除，而不只是从应用程序中删除。</span><span class="sxs-lookup"><span data-stu-id="9c154-267">When you remove a policy from an application, the policy and the vocabularies that it depends on are deleted from the rule engine database as well, not just from the application.</span></span>  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a><span data-ttu-id="9c154-268">导入 XML 文件以便重新创建 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="9c154-268">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="9c154-269">在 BizTalk Server 管理中，展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="9c154-269">In BizTalk Server Administration, expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
2.  <span data-ttu-id="9c154-270">右键单击**应用程序**，指向**导入**，然后单击**策略**。</span><span class="sxs-lookup"><span data-stu-id="9c154-270">Right-click **Applications**, point to **Import**, and then click **Policies**.</span></span>  
  
3.  <span data-ttu-id="9c154-271">浏览，然后双击该 XML 文件 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) 在第一个过程中创建。</span><span class="sxs-lookup"><span data-stu-id="9c154-271">Browse, and double-click the XML file (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) that you created in the first procedure.</span></span>  
  
4.  <span data-ttu-id="9c154-272">展开**\<所有项目 >**下**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9c154-272">Expand **\<All Artifacts>** under **Applications**.</span></span>  
  
5.  <span data-ttu-id="9c154-273">单击**策略**，并且你应看到 1.3 版**ProcessPurchaseOrder**列表中的策略。</span><span class="sxs-lookup"><span data-stu-id="9c154-273">Click **Policies**, and you should see version 1.3 of the **ProcessPurchaseOrder** policy in the list.</span></span>  
  
6.  <span data-ttu-id="9c154-274">按下 F5 键来刷新视图。</span><span class="sxs-lookup"><span data-stu-id="9c154-274">Press F5 to refresh the view.</span></span> <span data-ttu-id="9c154-275">**ProcessPurchaseOrder**策略应为**未发布**状态。</span><span class="sxs-lookup"><span data-stu-id="9c154-275">The **ProcessPurchaseOrder** policy should be in the **Not Published** state.</span></span>  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a><span data-ttu-id="9c154-276">将 ProcessPurchaseOrder 策略添加到 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="9c154-276">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="9c154-277">在 BizTalk Server 管理中，右键单击**ProcessPurchaseOrder**策略，，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="9c154-277">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** policy, and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-278">只有已发布的策略才能添加到 BizTalk 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="9c154-278">Only published policies can be added to a BizTalk application.</span></span>  
  
2.  <span data-ttu-id="9c154-279">在**应用程序**节点，展开**RuleTestApp**。</span><span class="sxs-lookup"><span data-stu-id="9c154-279">In the **Applications** node, expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="9c154-280">单击**策略**中**RuleTestApp**。</span><span class="sxs-lookup"><span data-stu-id="9c154-280">Click **Policies** in **RuleTestApp**.</span></span>  
  
4.  <span data-ttu-id="9c154-281">在右侧的列表中右击，指向**添加**，然后单击**策略**。</span><span class="sxs-lookup"><span data-stu-id="9c154-281">Right-click in the list on the right, point to **Add**, and then click **Policy**.</span></span>  
  
5.  <span data-ttu-id="9c154-282">展开**ProcessPurchaseOrder**节点中，选择的复选框**版本 1.3 （已发布）**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9c154-282">Expand the **ProcessPurchaseOrder** node, select the check box for **Version 1.3 (Published)**, and then click **OK**.</span></span> <span data-ttu-id="9c154-283">实例时都提供 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="9c154-283">.</span></span>  
  
6.  <span data-ttu-id="9c154-284">右键单击**ProcessPurchaseOrder**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="9c154-284">Right-click **ProcessPurchaseOrder**, and then click **Deploy**.</span></span> <span data-ttu-id="9c154-285">如果看不到**ProcessPurchaseOrder**在列表中，按 F5 刷新视图。</span><span class="sxs-lookup"><span data-stu-id="9c154-285">If you do not see **ProcessPurchaseOrder** in the list, press F5 to refresh the view.</span></span>  
  
7.  <span data-ttu-id="9c154-286">单击**是**确认消息框中。</span><span class="sxs-lookup"><span data-stu-id="9c154-286">Click **Yes** in the confirmation message box.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a><span data-ttu-id="9c154-287">通过使用 MSI 文件部署策略的过程</span><span class="sxs-lookup"><span data-stu-id="9c154-287">Procedures for Deploying the Policy by Using an MSI File</span></span>  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a><span data-ttu-id="9c154-288">将 RuleTestApp 应用程序导出到某一 MSI 文件</span><span class="sxs-lookup"><span data-stu-id="9c154-288">To export the RuleTestApp application to an MSI file</span></span>  
  
1.  <span data-ttu-id="9c154-289">上**启动**菜单上，打开**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="9c154-289">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="9c154-290">如果已打开该工具，请按 F5 键刷新。</span><span class="sxs-lookup"><span data-stu-id="9c154-290">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="9c154-291">展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9c154-291">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="9c154-292">右键单击**RuleTestApp**，指向**导出**，然后单击**MSI 文件**。</span><span class="sxs-lookup"><span data-stu-id="9c154-292">Right-click **RuleTestApp**, point to **Export**, and then click **MSI file**.</span></span>  
  
4.  <span data-ttu-id="9c154-293">上**欢迎使用导出 MSI 文件向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-293">On the **Welcome to the Export MSI File Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="9c154-294">上**选择资源**页上，查看所有默认选项，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-294">On the **Select Resources** page, review all the default options, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="9c154-295">上**指定 IIS 主机**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-295">On the **Specify IIS Hosts** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="9c154-296">上**依赖关系**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-296">On the **Dependencies** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="9c154-297">上**目标**页上，指定的目录和名称作为 MSI **C:\BRE-Walkthroughs\RuleTestApp.msi**。</span><span class="sxs-lookup"><span data-stu-id="9c154-297">On the **Destination** page, specify the directory and name for the MSI as **C:\BRE-Walkthroughs\RuleTestApp.msi**.</span></span>  
  
9. <span data-ttu-id="9c154-298">单击 **“导出”**。</span><span class="sxs-lookup"><span data-stu-id="9c154-298">Click **Export**.</span></span>  
  
10. <span data-ttu-id="9c154-299">上**摘要**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="9c154-299">On the **Summary** page, click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-300">在您导出 RuleTestApp 应用程序时，该应用程序所使用的策略和词汇也将导出到 MSI 文件中。</span><span class="sxs-lookup"><span data-stu-id="9c154-300">When you export the RuleTestApp application, the policies and vocabularies used by the application are also exported in the MSI file.</span></span> <span data-ttu-id="9c154-301">以后，在您导入该 MSI 文件时，词汇、策略和应用程序也都会重新创建。</span><span class="sxs-lookup"><span data-stu-id="9c154-301">Later, when you import the MSI file, the vocabulary, policy, and application are all re-created.</span></span>  
  
#### <a name="to-delete-the-ruletestapp-application"></a><span data-ttu-id="9c154-302">删除 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="9c154-302">To delete the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="9c154-303">在 BizTalk Server 管理中，右键单击**RuleTestApp**，并检查如果**删除**菜单是启用还是禁用。</span><span class="sxs-lookup"><span data-stu-id="9c154-303">In BizTalk Server Administration, right-click **RuleTestApp**, and check if the **Delete** menu is enabled or disabled.</span></span>  
  
2.  <span data-ttu-id="9c154-304">如果**删除**是禁用，右键单击**RuleTestApp**，单击**停止**，选择**句号-终止实例**，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="9c154-304">If **Delete** is disabled, right-click **RuleTestApp**, click **Stop**, select **Full Stop - Terminate Instance**, and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="9c154-305">右键单击**RuleTestApp**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="9c154-305">Right-click **RuleTestApp**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="9c154-306">单击**是**以确认删除。</span><span class="sxs-lookup"><span data-stu-id="9c154-306">Click **Yes** to confirm deletion.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-307">在您删除某一应用程序时，该应用程序中的所有策略以及相关词汇也将从规则引擎数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="9c154-307">When you delete an application, all the policies in the application and dependent vocabularies are deleted from the rule engine database as well.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a><span data-ttu-id="9c154-308">验证 ProcessPurchaseOrder 策略和 POVocabulary 词汇已删除</span><span class="sxs-lookup"><span data-stu-id="9c154-308">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>  
  
1.  <span data-ttu-id="9c154-309">上**启动**菜单上，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="9c154-309">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="9c154-310">如果你有已打开，按 F5 刷新其业务规则编辑器。</span><span class="sxs-lookup"><span data-stu-id="9c154-310">If you have Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-311">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9c154-311">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="9c154-312">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="9c154-312">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="9c154-313">在策略资源管理器窗口中，展开**策略**，并确保 ProcessPurchaseOrder 策略不存在。</span><span class="sxs-lookup"><span data-stu-id="9c154-313">In the Policy Explorer window, expand **Policies**, and make sure that the ProcessPurchaseOrder policy does not exist.</span></span>  
  
3.  <span data-ttu-id="9c154-314">在事实浏览器窗口中，展开**词汇**，并确保 POVocabulary 不存在。</span><span class="sxs-lookup"><span data-stu-id="9c154-314">In the Facts Explorer window, expand **Vocabularies**, and make sure that POVocabulary does not exist.</span></span>  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a><span data-ttu-id="9c154-315">导入 MSI 文件以便重新创建 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="9c154-315">To import the MSI file to re-create the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="9c154-316">上**启动**菜单上，打开**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="9c154-316">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="9c154-317">如果 BizTalk Server 管理控制台已经打开，则按下 F5 键以便刷新它。</span><span class="sxs-lookup"><span data-stu-id="9c154-317">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="9c154-318">展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="9c154-318">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
3.  <span data-ttu-id="9c154-319">右键单击**应用程序**，指向**导入**，然后单击**MSI 文件**。</span><span class="sxs-lookup"><span data-stu-id="9c154-319">Right-click **Applications**, point to **Import**, and then click **MSI file**.</span></span>  
  
4.  <span data-ttu-id="9c154-320">上**欢迎使用导入向导**页上，浏览并选择前面导出的 MSI 文件 (RuleTestApp.msi) **MSI 文件以导入**设置。</span><span class="sxs-lookup"><span data-stu-id="9c154-320">On the **Welcome to the Import Wizard** page, browse and select the MSI file (RuleTestApp.msi) you exported earlier for the **MSI file to import** setting.</span></span>  
  
5.  <span data-ttu-id="9c154-321">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="9c154-321">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="9c154-322">上**应用程序设置**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-322">On the **Application Settings** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="9c154-323">上**应用程序目标环境设置**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c154-323">On the **Application Target Environment Settings** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="9c154-324">上**导入摘要**页上，单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="9c154-324">On the **Import Summary** page, click **Import**.</span></span>  
  
9. <span data-ttu-id="9c154-325">上**导入成功**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="9c154-325">On the **Import Succeeded** page, click **Finish**.</span></span> <span data-ttu-id="9c154-326">您应该会看到**RuleTestApp**下创建应用程序**应用程序**BizTalk Server 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="9c154-326">You should see that the **RuleTestApp** application is created under **Applications** in the BizTalk Server Administration console.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-is-added-to-ruletestapp"></a><span data-ttu-id="9c154-327">验证 ProcessPurchaseOrder 策略已添加到 RuleTestApp</span><span class="sxs-lookup"><span data-stu-id="9c154-327">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>  
  
1.  <span data-ttu-id="9c154-328">展开**RuleTestApp** BizTalk Server 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="9c154-328">Expand **RuleTestApp** in the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="9c154-329">选择**策略**，你应看到**ProcessPurchaseOrder**在右窗格中的列表中。</span><span class="sxs-lookup"><span data-stu-id="9c154-329">Select **Policies** and you should see **ProcessPurchaseOrder** in the list in the right pane.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-re-created"></a><span data-ttu-id="9c154-330">确认 ProcessPurchaseOrder 策略和 POVocabulary 词汇已重新创建</span><span class="sxs-lookup"><span data-stu-id="9c154-330">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>  
  
1.  <span data-ttu-id="9c154-331">上**启动**菜单上，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="9c154-331">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="9c154-332">如果已打开业务规则编辑器，请按 F5 键刷新。</span><span class="sxs-lookup"><span data-stu-id="9c154-332">If you have it already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-333">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9c154-333">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="9c154-334">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="9c154-334">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="9c154-335">在策略资源管理器窗口中，展开**策略**，并确保**ProcessPurchaseOrder**存在。</span><span class="sxs-lookup"><span data-stu-id="9c154-335">In the Policy Explorer window, expand **Policies**, and make sure that **ProcessPurchaseOrder** exists.</span></span>  
  
3.  <span data-ttu-id="9c154-336">在事实浏览器窗口中，展开**词汇**，并确保**POVocabulary**存在。</span><span class="sxs-lookup"><span data-stu-id="9c154-336">In the Facts Explorer window, expand **Vocabularies**, and make sure that **POVocabulary** exists.</span></span>  
  
#### <a name="to-test-the-solution"></a><span data-ttu-id="9c154-337">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="9c154-337">To test the solution</span></span>  
  
1.  <span data-ttu-id="9c154-338">上**启动**菜单上，打开**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="9c154-338">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="9c154-339">如果 BizTalk Server 管理控制台已经打开，则按下 F5 键以便刷新它。</span><span class="sxs-lookup"><span data-stu-id="9c154-339">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="9c154-340">展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9c154-340">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="9c154-341">右键单击**RuleTestApp**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="9c154-341">Right-click **RuleTestApp**, and then click **Start**.</span></span>  
  
4.  <span data-ttu-id="9c154-342">单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="9c154-342">Click **Start**.</span></span>  
  
5.  <span data-ttu-id="9c154-343">复制**SamplePO.xml**在中创建[演练： 测试策略](../core/walkthrough-testing-the-policy.md)到业务流程的输入目录。</span><span class="sxs-lookup"><span data-stu-id="9c154-343">Copy **SamplePO.xml** that you created in [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) to the input directory for the orchestration.</span></span>  
  
6.  <span data-ttu-id="9c154-344">你应该在输出目录中看到业务流程的输出文件。</span><span class="sxs-lookup"><span data-stu-id="9c154-344">You should see an output file in the output directory for the orchestration.</span></span> <span data-ttu-id="9c154-345">打开输出 XML 文件，可以看到的值**状态**字段设置为**已批准**。</span><span class="sxs-lookup"><span data-stu-id="9c154-345">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
7.  <span data-ttu-id="9c154-346">重复步骤 3 和 4 个，带有**SamplePO2.xml**，请注意，和的值**状态**输出文档中的字段是与输入文档中的相同 (**XYZ**)。</span><span class="sxs-lookup"><span data-stu-id="9c154-346">Repeat steps 3 and 4 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**XYZ**).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="9c154-347">注释</span><span class="sxs-lookup"><span data-stu-id="9c154-347">Comments</span></span>  
  
-   <span data-ttu-id="9c154-348">它是**非常重要**记住，当从应用程序中移除策略，你不只是删除应用程序和策略之间的关联; 你还删除策略和其关联的词汇规则引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="9c154-348">It is **very important** to remember that when you remove a policy from an application, you do not just remove the association between the application and the policy; you also delete the policy and its associated vocabulary from the rule engine database.</span></span>  
  
-   <span data-ttu-id="9c154-349">在您开始某一应用程序时，默认情况下，该应用程序将自动部署策略。</span><span class="sxs-lookup"><span data-stu-id="9c154-349">When you start an application, by default, it deploys the policies automatically.</span></span> <span data-ttu-id="9c154-350">同样，当你停止应用程序并选择**句号-终止实例**，关联的策略会自动取消部署。</span><span class="sxs-lookup"><span data-stu-id="9c154-350">Similarly, when you stop an application and select **Full Stop - Terminate Instances**, the associated policies are undeployed automatically.</span></span> <span data-ttu-id="9c154-351">当选择**部分停止-暂停正在运行的实例**，关联的策略将不自动取消部署。</span><span class="sxs-lookup"><span data-stu-id="9c154-351">When you select **Partial Stop - Suspend running instances**, the associated policies are not undeployed automatically.</span></span>  
  
-   <span data-ttu-id="9c154-352">您应该在业务规则编辑器和 BizTalk Server 管理控制台中刷新视图，以便确保在执行任何操作前查看最新信息。</span><span class="sxs-lookup"><span data-stu-id="9c154-352">You should refresh the views in Business Rule Composer and BizTalk Server Administration console to make sure you are looking at the latest information before performing any operation.</span></span>  
  
-   <span data-ttu-id="9c154-353">如果您创建其先前版本与某一 BizTalk 应用程序关联的策略的新版本，则应手动将该策略的新版本添加到该应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c154-353">If you create a new version of the policy whose earlier version is associated with a BizTalk application, you should manually add the new version of the policy to the application.</span></span> <span data-ttu-id="9c154-354">您不应删除该策略的旧版本，除非确实要从规则引擎数据库中删除它。</span><span class="sxs-lookup"><span data-stu-id="9c154-354">You should not remove the old version of the policy unless you really want to delete it from the rule engine database.</span></span>  
  
-   <span data-ttu-id="9c154-355">您可以在导入前将两个或多个 BRL（业务规则语言 XML 文件）文件合并到单个 BRL 文件中。</span><span class="sxs-lookup"><span data-stu-id="9c154-355">You can merge two or more BRL (Business Rule Language XML file) files into a single BRL file before importing.</span></span> <span data-ttu-id="9c154-356">下面的代码显示三个 BRL 文件。</span><span class="sxs-lookup"><span data-stu-id="9c154-356">The following code shows three BRL files.</span></span> <span data-ttu-id="9c154-357">第一个 BRL 文件包含**POVocabulary**词汇。</span><span class="sxs-lookup"><span data-stu-id="9c154-357">The first BRL file contains the **POVocabulary** vocabulary.</span></span> <span data-ttu-id="9c154-358">第二个 BRL 文件包含**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="9c154-358">The second BRL file contains the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="9c154-359">第三个 BRL 文件同时包含**POVocabulary**词汇和**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="9c154-359">The third BRL file contains both the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="9c154-360">通过执行以下步骤创建第三个 BRE 文件：</span><span class="sxs-lookup"><span data-stu-id="9c154-360">The third BRE file is created by performing the following steps:</span></span>  
  
    1.  <span data-ttu-id="9c154-361">编辑器创建使用任何文件的新文件并将其保存为 XML 文件 (例如： POPolicyVocabulary.xml)。</span><span class="sxs-lookup"><span data-stu-id="9c154-361">Create a new file using any file editor and save it as an XML file (for example: POPolicyVocabulary.xml).</span></span>  
  
    2.  <span data-ttu-id="9c154-362">从包含词汇的第一个 BRL 文件复制整个 XML 内容。</span><span class="sxs-lookup"><span data-stu-id="9c154-362">Copy the entire XML content from the first BRL file containing the vocabulary.</span></span>  
  
    3.  <span data-ttu-id="9c154-363">复制 ruleset 块 (开头\<ruleset > 标记和以结尾\</ruleset > 标记) 从第二个 BRL 文件。</span><span class="sxs-lookup"><span data-stu-id="9c154-363">Copy the ruleset block (starts with the \<ruleset> tag and ends with the \</ruleset> tag) from the second BRL file.</span></span>  
  
    4.  <span data-ttu-id="9c154-364">保存该新文件。</span><span class="sxs-lookup"><span data-stu-id="9c154-364">Save the new file.</span></span> <span data-ttu-id="9c154-365">你可以导入此单个 XML 文件，以创建**POVocabulary**词汇和**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="9c154-365">You can import this single XML file to create the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c154-366">词汇和规则集节点在合并的 BRL 文件中的列出顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="9c154-366">It does not matter in which order the vocabulary and ruleset nodes are listed in the merged BRL file.</span></span> <span data-ttu-id="9c154-367">您可以将规则集节点置于词汇节点前。</span><span class="sxs-lookup"><span data-stu-id="9c154-367">You can have the ruleset node ahead of the vocabulary node.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
    </brl>  
  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
    ```