---
title: 演练： 部署策略 |Microsoft Docs
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 205760e2-9cd4-496f-93cd-0f93bc5d3231
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b35b7d9c3b2b7780ef87b0dedae52f58c20dc835
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996294"
---
# <a name="walkthrough-deploying-the-policy"></a><span data-ttu-id="7a5bf-102">演练： 部署策略</span><span class="sxs-lookup"><span data-stu-id="7a5bf-102">Walkthrough: Deploying the Policy</span></span>
<span data-ttu-id="7a5bf-103">本演练提供了部署的分步说明**ProcessPurchaseOrder**策略中的以下三种方法：</span><span class="sxs-lookup"><span data-stu-id="7a5bf-103">This walkthrough provides step-by-step instructions for deploying the **ProcessPurchaseOrder** policy in the following three ways:</span></span>  
  
-   <span data-ttu-id="7a5bf-104">导出和导入策略，通过使用业务规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-104">Exporting and importing the policy by using the Business Rules Engine Deployment Wizard.</span></span>  
  
-   <span data-ttu-id="7a5bf-105">通过使用 BizTalk Server 管理控制台将策略导出到某一 XML 文件或者从某一 XML 文件导入策略。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-105">Exporting the policy to an XML file and importing the policy from an XML file by using the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="7a5bf-106">通过使用 BizTalk Server 管理控制台将策略作为 XML 文件的一部分导出并导入该 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-106">Exporting the policy as part of an MSI file and importing the MSI file by using BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7a5bf-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="7a5bf-107">Prerequisites</span></span>  
 <span data-ttu-id="7a5bf-108">必须完成[演练： 跟踪策略执行](../core/walkthrough-tracking-policy-execution.md)执行本演练中之前的演练。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-108">You must complete the [Walkthrough: Tracking Policy Execution](../core/walkthrough-tracking-policy-execution.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="7a5bf-109">本演练概述</span><span class="sxs-lookup"><span data-stu-id="7a5bf-109">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="7a5bf-110">本主题包含下列三个演练：</span><span class="sxs-lookup"><span data-stu-id="7a5bf-110">This topic  contains the following three walkthroughs:</span></span>  
  
1.  <span data-ttu-id="7a5bf-111">第一个演练包含用于部署的过程**ProcessPurchaseOrder**策略通过使用业务规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-111">The first walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using the Business Rules Engine Deployment Wizard.</span></span> <span data-ttu-id="7a5bf-112">下表描述此演练中的各个过程。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-112">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="7a5bf-113">过程标题</span><span class="sxs-lookup"><span data-stu-id="7a5bf-113">Procedure title</span></span>|<span data-ttu-id="7a5bf-114">过程说明</span><span class="sxs-lookup"><span data-stu-id="7a5bf-114">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="7a5bf-115">若要使用业务规则引擎部署向导导出 POVocabulary 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="7a5bf-115">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="7a5bf-116">提供了导出的 1.0 和 1.1 版的分步说明**POVocabulary**词汇到 XML 文件使用业务规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-116">Provides step-by-step instructions for exporting versions 1.0 and 1.1 of the **POVocabulary** vocabulary to XML files by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="7a5bf-117">使用业务规则引擎部署向导来导出 ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="7a5bf-117">To export ProcessPurchaseOrder 1.3 by using the Business Rules Engine Deployment Wizard</span></span>|<span data-ttu-id="7a5bf-118">提供了导出的 1.3 版的分步说明**ProcessPurchaseOrder**策略应用到 XML 文件使用业务规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-118">Provides step-by-step instructions for exporting version 1.3 of the **ProcessPurchaseOrder** policy to an XML file by using the Business Rules Engine Deployment Wizard.</span></span>|  
    |<span data-ttu-id="7a5bf-119">删除 ProcessPurchaseOrder 和 POVocabulary</span><span class="sxs-lookup"><span data-stu-id="7a5bf-119">To delete ProcessPurchaseOrder and POVocabulary</span></span>|<span data-ttu-id="7a5bf-120">提供有关删除的分步说明**ProcessPurchaseOrder**策略并**POVocabulary**词汇，以便可以测试导入 XML 文件以重新创建它们。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-120">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary so that you can test importing the XML files to re-create them.</span></span>|  
    |<span data-ttu-id="7a5bf-121">从 XML 导入以重新创建 POVocabulary 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="7a5bf-121">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>|<span data-ttu-id="7a5bf-122">提供在重新创建的第一个过程中创建的词汇 XML 文件导入的分步说明**POVocabulary**词汇。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-122">Provides step-by-step instructions for importing the vocabulary XML file you created in the first procedure to re-create the **POVocabulary** vocabulary.</span></span>|  
    |<span data-ttu-id="7a5bf-123">确认 POVocabulary 1.0 和 1.1 已重新创建</span><span class="sxs-lookup"><span data-stu-id="7a5bf-123">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>|<span data-ttu-id="7a5bf-124">提供使用业务规则编辑器来验证的分步说明的该版本 1.0 和 1.1 **POVocabulary**重新创建。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-124">Provides step-by-step instructions for using the Business Rule Composer to verify that versions 1.0 and 1.1 of **POVocabulary** are re-created.</span></span>|  
    |<span data-ttu-id="7a5bf-125">从 XML 导入以重新创建 ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="7a5bf-125">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>|<span data-ttu-id="7a5bf-126">提供在重新创建的版本 1.3 的第二个过程中创建的导入策略 XML 文件的分步说明**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-126">Provides step-by-step instructions for importing the policy XML file you created in the second procedure to re-create version 1.3 of the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="7a5bf-127">验证 ProcessPurchaseOrder 1.3 已重新创建</span><span class="sxs-lookup"><span data-stu-id="7a5bf-127">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>|<span data-ttu-id="7a5bf-128">提供有关使用业务规则编辑器来验证该版本 1.3 的分步说明**ProcessPurchaseOrder**策略都将重新创建。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-128">Provides step-by-step instructions for using the Business Rule Composer to verify that version 1.3 of the **ProcessPurchaseOrder** policy is re-created.</span></span>|  
  
2.  <span data-ttu-id="7a5bf-129">第二个演练包含用于部署的过程**ProcessPurchaseOrder**策略通过使用 XML 文件从 BizTalk Server 管理控制台导出以下表介绍了在此过程演练。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-129">The second walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an XML file exported from the BizTalk Server Administration console The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="7a5bf-130">过程标题</span><span class="sxs-lookup"><span data-stu-id="7a5bf-130">Procedure title</span></span>|<span data-ttu-id="7a5bf-131">过程说明</span><span class="sxs-lookup"><span data-stu-id="7a5bf-131">Procedure description</span></span>|  
    |---------------------|---------------------------|  
    |<span data-ttu-id="7a5bf-132">将 ProcessPurchaseOrder 1.3 策略和 POVocabulary 词汇导出到某一 XML 文件</span><span class="sxs-lookup"><span data-stu-id="7a5bf-132">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>|<span data-ttu-id="7a5bf-133">提供使用 BizTalk Server 管理控制台导出的分步说明**ProcessPurchaseOrder**策略并**POVocabulary**词汇到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-133">Provides step-by-step instructions for using the BizTalk Server Administration console to export the **ProcessPurchaseOrder** policy and the **POVocabulary** vocabulary to an XML file.</span></span>|  
    |<span data-ttu-id="7a5bf-134">删除 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="7a5bf-134">To delete the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="7a5bf-135">提供有关删除的分步说明**ProcessPurchaseOrder**从策略**RuleTestApp**和规则引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-135">Provides step-by-step instructions for deleting the **ProcessPurchaseOrder** policy from **RuleTestApp** and the rule engine database.</span></span>|  
    |<span data-ttu-id="7a5bf-136">导入 XML 文件以便重新创建 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="7a5bf-136">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="7a5bf-137">提供在重新创建的第一个过程中导出的导入 XML 文件的分步说明**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-137">Provides step-by-step instructions for importing the XML file you exported in the first procedure to re-create the **ProcessPurchaseOrder** policy.</span></span>|  
    |<span data-ttu-id="7a5bf-138">将 ProcessPurchaseOrder 策略添加到 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="7a5bf-138">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>|<span data-ttu-id="7a5bf-139">提供用于添加的分步说明**ProcessPurchaseOrder**策略**RuleTestApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-139">Provides step-by-step instructions for adding the **ProcessPurchaseOrder** policy to the **RuleTestApp** application.</span></span>|  
  
3.  <span data-ttu-id="7a5bf-140">第三个演练包含用于部署的过程**ProcessPurchaseOrder**从 BizTalk Server 管理控制台导出的策略通过使用 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-140">The third walkthrough contains procedures for deploying the **ProcessPurchaseOrder** policy by using an MSI file exported from the BizTalk Server Administration console.</span></span> <span data-ttu-id="7a5bf-141">下表描述此演练中的各个过程。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-141">The following table describes the procedures in this walkthrough.</span></span>  
  
    |<span data-ttu-id="7a5bf-142">过程标题</span><span class="sxs-lookup"><span data-stu-id="7a5bf-142">Procedure title</span></span>|<span data-ttu-id="7a5bf-143">过程具有针对以下操作的分步说明</span><span class="sxs-lookup"><span data-stu-id="7a5bf-143">Procedure has step-by-step instructions for</span></span>|  
    |---------------------|---------------------------------------------------|  
    |<span data-ttu-id="7a5bf-144">将 RuleTestApp 应用程序导出到某一 MSI 文件</span><span class="sxs-lookup"><span data-stu-id="7a5bf-144">To export the RuleTestApp application to an MSI file</span></span>|<span data-ttu-id="7a5bf-145">提供了导出的分步说明**RuleTestApp**到 MSI 文件，用于在以后重新创建该应用程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-145">Provides step-by-step instructions for exporting the **RuleTestApp** application to an MSI file, which is used later to re-create the application.</span></span>|  
    |<span data-ttu-id="7a5bf-146">删除 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="7a5bf-146">To delete the RuleTestApp application</span></span>|<span data-ttu-id="7a5bf-147">提供有关删除的分步说明**RuleTestApp**应用程序，以便可以测试使用 MSI 文件重新创建该应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-147">Provides step-by-step instructions for deleting the **RuleTestApp** application so that you can test re-creating the application by using the MSI file.</span></span>|  
    |<span data-ttu-id="7a5bf-148">验证 ProcessPurchaseOrder 策略和 POVocabulary 词汇已删除</span><span class="sxs-lookup"><span data-stu-id="7a5bf-148">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>|<span data-ttu-id="7a5bf-149">提供有关使用业务规则编辑器来验证的分步说明**ProcessPurchaseOrder**策略和 POVocabulary 词汇已删除。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-149">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and POVocabulary vocabulary are deleted.</span></span>|  
    |<span data-ttu-id="7a5bf-150">导入 MSI 文件以便重新创建 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="7a5bf-150">To import the MSI file to re-create the RuleTestApp application</span></span>|<span data-ttu-id="7a5bf-151">分步说明如何使用 BizTalk Server 管理控制台导入 MSI 文件以重新创建**RuleTestApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-151">Provides step-by-step instructions for using the BizTalk Server Administration console to import the MSI file to re-create the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="7a5bf-152">验证 ProcessPurchaseOrder 策略已添加到 RuleTestApp</span><span class="sxs-lookup"><span data-stu-id="7a5bf-152">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>|<span data-ttu-id="7a5bf-153">提供有关使用 BizTalk Server 管理控制台来验证的分步说明**ProcessPurchaseOrder**策略添加到**RuleTestApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-153">Provides step-by-step instructions for using the BizTalk Server Administration console to verify that the **ProcessPurchaseOrder** policy is added to the **RuleTestApp** application.</span></span>|  
    |<span data-ttu-id="7a5bf-154">确认 ProcessPurchaseOrder 策略和 POVocabulary 词汇已重新创建</span><span class="sxs-lookup"><span data-stu-id="7a5bf-154">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>|<span data-ttu-id="7a5bf-155">提供有关使用业务规则编辑器来验证的分步说明**ProcessPurchaseOrder**策略并**POVocabulary**词汇已重新创建。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-155">Provides step-by-step instructions for using the Business Rule Composer to verify that the **ProcessPurchaseOrder** policy and **POVocabulary** vocabulary are re-created.</span></span>|  
    |<span data-ttu-id="7a5bf-156">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="7a5bf-156">To test the solution</span></span>|<span data-ttu-id="7a5bf-157">提供用于测试解决方案的分步说明。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-157">Provides step-by-step instructions for testing the solution.</span></span>|  
  
## <a name="procedures-for-deploying-the-processpurchaseorder-policy-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="7a5bf-158">通过使用业务规则引擎部署向导部署 ProcessPurchaseOrder 策略的过程</span><span class="sxs-lookup"><span data-stu-id="7a5bf-158">Procedures for Deploying the ProcessPurchaseOrder Policy by Using the Business Rules Engine Deployment Wizard</span></span>  
  
#### <a name="to-export-povocabulary-10-and-11-by-using-the-business-rules-engine-deployment-wizard"></a><span data-ttu-id="7a5bf-159">若要使用业务规则引擎部署向导导出 POVocabulary 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="7a5bf-159">To export POVocabulary 1.0 and 1.1 by using the Business Rules Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="7a5bf-160">上**启动**菜单中，打开**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-160">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-161">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-161">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="7a5bf-162">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-162">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="7a5bf-163">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-163">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="7a5bf-164">上**部署任务**页上，选择**策略/词汇导出到文件从数据库**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-164">On the **Deployment Task** page, select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="7a5bf-165">上**策略存储区**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-165">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="7a5bf-166">上**导出策略/词汇**页上，单击**词汇**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-166">On the **Export Policy/Vocabulary** page, click **Vocabulary**.</span></span>  
  
6.  <span data-ttu-id="7a5bf-167">选择**POVocabulary.1.0**从下拉列表中为**策略/词汇**中，键入或浏览来指定 XML 输出文件的名称作为**C:\BRE-walkthroughs\POVocabulary10.xml**，然后依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-167">Select **POVocabulary.1.0** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary10.xml**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="7a5bf-168">上**准备好**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-168">On the **Ready** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="7a5bf-169">上**导出策略/词汇**页上，单击**下一步。**</span><span class="sxs-lookup"><span data-stu-id="7a5bf-169">On the **Exporting Policy/Vocabulary** page, click **Next.**</span></span>  
  
9. <span data-ttu-id="7a5bf-170">选择**再次运行此向导**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-170">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="7a5bf-171">因为所选**再次运行此向导**，该向导的第一个屏幕会再次出现。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-171">Because you selected **Run this wizard again**, the first screen of the wizard appears again.</span></span>  
  
10. <span data-ttu-id="7a5bf-172">重复步骤 2 到 6。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-172">Repeat steps 2-6.</span></span>  
  
11. <span data-ttu-id="7a5bf-173">选择**POVocabulary.1.1**从下拉列表中为**策略/词汇**中，键入或浏览来指定 XML 输出文件的名称作为**C:\BRE-walkthroughs\POVocabulary11.xml**，然后依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-173">Select **POVocabulary.1.1** from the drop-down list for **Policy/Vocabulary**, type or browse to specify the XML output file name as **C:\BRE-walkthroughs\POVocabulary11.xml**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="7a5bf-174">重复步骤 8 和 9。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-174">Repeat steps 8 and 9.</span></span>  
  
13. <span data-ttu-id="7a5bf-175">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-175">Click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-176">您需要版本 1.0 和 1.1 版导出**POVocabulary**因为**ProcessPurchaseOrder** 1.3 依赖于这两个版本**POVocabulary**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-176">You need to export both version 1.0 and version 1.1 of **POVocabulary** because **ProcessPurchaseOrder** 1.3 depends on both versions of **POVocabulary**.</span></span> <span data-ttu-id="7a5bf-177">**项允许的最大数量**定义用于词汇的 1.1 版中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-177">The **Maximum number of items allowed** definition is used from version 1.1 of the vocabulary.</span></span> <span data-ttu-id="7a5bf-178">**请求的数量**并**请求状态**定义用于从版本 1.0。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-178">The **Requested Quantity** and **Request Status** definitions are used from version 1.0.</span></span>  
  
#### <a name="to-export-processpurchaseorder-13-by-using-the-business-rule-engine-deployment-wizard"></a><span data-ttu-id="7a5bf-179">若要通过使用业务规则引擎部署向导来导出 ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="7a5bf-179">To export ProcessPurchaseOrder 1.3 by using the Business Rule Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="7a5bf-180">上**启动**菜单中，打开**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-180">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-181">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-181">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="7a5bf-182">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-182">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="7a5bf-183">上**欢迎使用规则引擎部署向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-183">On the **Welcome to the Rules Engine Deployment Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="7a5bf-184">选择**策略/词汇导出到文件从数据库**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-184">Select **Export Policy/Vocabulary to file from database**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="7a5bf-185">上**策略存储区**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-185">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="7a5bf-186">确认**策略**选择选项。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-186">Verify that the **Policy** option is selected.</span></span>  
  
6.  <span data-ttu-id="7a5bf-187">选择**ProcessPurchaseOrder.1.3**从下拉列表中为**策略/词汇**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-187">Select **ProcessPurchaseOrder.1.3** from the drop-down list for **Policy/Vocabulary**.</span></span>  
  
7.  <span data-ttu-id="7a5bf-188">键入或浏览以指定要**C:\BRE-walkthroughs\ProcessPOPolicy13.xml**作为 XML 输出文件的名称。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-188">Type or browse to specify **C:\BRE-walkthroughs\ProcessPOPolicy13.xml** as the XML output file name.</span></span>  
  
8.  <span data-ttu-id="7a5bf-189">单击**下一步**三次，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-189">Click **Next** thrice, and then click **Finish**.</span></span>  
  
#### <a name="to-delete-processpurchaseorder-and-povocabulary"></a><span data-ttu-id="7a5bf-190">删除 ProcessPurchaseOrder 和 POVocabulary</span><span class="sxs-lookup"><span data-stu-id="7a5bf-190">To delete ProcessPurchaseOrder and POVocabulary</span></span>  
  
1.  <span data-ttu-id="7a5bf-191">上**启动**菜单中，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-191">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="7a5bf-192">如果您有业务规则编辑器已打开，请按 F5 或单击**重新加载**上**文件**菜单进行刷新。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-192">If you have Business Rule Composer already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-193">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-193">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="7a5bf-194">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-194">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="7a5bf-195">在策略浏览器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.0**，然后单击**删除**.</span><span class="sxs-lookup"><span data-stu-id="7a5bf-195">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Delete**.</span></span> <span data-ttu-id="7a5bf-196">如果**删除**已禁用，右键单击**版本 1.0**，然后单击**Undeploy**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-196">If **Delete** is disabled, right-click **Version 1.0**, and then click **Undeploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-197">已部署的策略版本不能删除。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-197">The deployed policy versions cannot be deleted.</span></span> <span data-ttu-id="7a5bf-198">您必须首先取消部署策略，然后才能删除策略版本。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-198">You must undeploy a policy before deleting a policy version.</span></span>  
  
3.  <span data-ttu-id="7a5bf-199">单击**是**的确认消息框中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-199">Click **Yes** in the confirmation message box.</span></span>  
  
4.  <span data-ttu-id="7a5bf-200">重复步骤 2 和 3，以便删除**1.1 版**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-200">Repeat steps 2 and 3 to delete **Version 1.1**.</span></span>  
  
5.  <span data-ttu-id="7a5bf-201">重复步骤 2 和 3，以便删除**版本 1.2**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-201">Repeat steps 2 and 3 to delete **Version 1.2**.</span></span>  
  
6.  <span data-ttu-id="7a5bf-202">右键单击**版本 1.3-部署**，然后单击**Undeploy**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-202">Right-click **Version 1.3 - Deployed**, and then click **Undeploy**.</span></span> <span data-ttu-id="7a5bf-203">如果**Undeploy**选项处于禁用状态，则忽略此步骤。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-203">If the **Undeploy** option is disabled, ignore this step.</span></span>  
  
7.  <span data-ttu-id="7a5bf-204">在事实浏览器窗口中，展开**词汇**，右键单击**POVocabulary**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-204">In the Facts Explorer window, expand **Vocabularies**, right-click **POVocabulary**, and then click **Delete**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a><span data-ttu-id="7a5bf-205">从 XML 导入以重新创建 POVocabulary 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="7a5bf-205">To import from XML to re-create POVocabulary 1.0 and 1.1</span></span>  
  
1.  <span data-ttu-id="7a5bf-206">上**启动**菜单中，打开**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-206">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-207">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-207">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="7a5bf-208">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-208">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="7a5bf-209">上**欢迎使用规则引擎部署向导**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-209">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="7a5bf-210">上**部署任务**页上，选择**导入策略/词汇并发布到数据库文件从**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-210">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="7a5bf-211">上**策略存储区**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-211">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="7a5bf-212">浏览并选择**POVocabulary10.xml**第一个过程中创建的文件。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-212">Browse and select the **POVocabulary10.xml** file you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="7a5bf-213">单击**开放**或双击**POVocabulary10.xml**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-213">Click **Open** or double-click **POVocabulary10.xml**.</span></span>  
  
7.  <span data-ttu-id="7a5bf-214">单击**下一步**业务规则引擎部署向导中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-214">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="7a5bf-215">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-215">Click **Next**.</span></span>  
  
9. <span data-ttu-id="7a5bf-216">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-216">Click **Next**.</span></span>  
  
10. <span data-ttu-id="7a5bf-217">选择**再次运行此向导**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-217">Select **Run this wizard again**, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="7a5bf-218">重复步骤 2-9 以便导入**POVocabulary11.xml**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-218">Repeat steps 2-9 to import **POVocabulary11.xml**.</span></span>  
  
12. <span data-ttu-id="7a5bf-219">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-219">Click **Finish**.</span></span>  
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a><span data-ttu-id="7a5bf-220">确认 POVocabulary 1.0 和 1.1 已重新创建</span><span class="sxs-lookup"><span data-stu-id="7a5bf-220">To verify that POVocabulary 1.0 and 1.1 are re-created</span></span>  
  
1.  <span data-ttu-id="7a5bf-221">上**启动**菜单中，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-221">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="7a5bf-222">如果必须已经打开，请按 F5 或单击**重新加载**上**文件**菜单进行刷新。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-222">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-223">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-223">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="7a5bf-224">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-224">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="7a5bf-225">在事实浏览器窗口中，单击**词汇**选项卡。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-225">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
3.  <span data-ttu-id="7a5bf-226">展开**词汇**，并且你应看到**POVocabulary**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-226">Expand **Vocabularies**, and you should see **POVocabulary**.</span></span>  
  
4.  <span data-ttu-id="7a5bf-227">展开**POVocabulary**，并且你应看到**版本 1.0**并**版本 1.1**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-227">Expand **POVocabulary**, and you should see **Version 1.0** and **Version 1.1**.</span></span>  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a><span data-ttu-id="7a5bf-228">从 XML 导入以重新创建 ProcessPurchaseOrder 1.3</span><span class="sxs-lookup"><span data-stu-id="7a5bf-228">To import from XML to re-create ProcessPurchaseOrder 1.3</span></span>  
  
1.  <span data-ttu-id="7a5bf-229">上**启动**菜单中，打开**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-229">On the **Start** menu, open **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-230">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-230">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="7a5bf-231">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-231">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="7a5bf-232">上**欢迎使用规则引擎部署向导**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-232">On the **Welcome to the Rules Engine Deployment Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="7a5bf-233">上**部署任务**页上，选择**导入策略/词汇并发布到数据库文件从文件要数据库**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-233">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from fileto database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="7a5bf-234">上**策略存储区**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-234">On the **Policy Store** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="7a5bf-235">浏览并选择**ProcessPOPolicy13.xml**之前在本演练中创建的文件。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-235">Browse and select the **ProcessPOPolicy13.xml** file you created earlier in this walkthrough.</span></span>  
  
6.  <span data-ttu-id="7a5bf-236">单击**开放**或双击**ProcessPOPolicy13.xml**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-236">Click **Open** or double-click **ProcessPOPolicy13.xml**.</span></span>  
  
7.  <span data-ttu-id="7a5bf-237">单击**下一步**业务规则引擎部署向导中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-237">Click **Next** in the Business Rules Engine Deployment Wizard.</span></span>  
  
8.  <span data-ttu-id="7a5bf-238">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-238">Click **Next**.</span></span>  
  
9. <span data-ttu-id="7a5bf-239">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-239">Click **Next**, and then click **Finish**.</span></span>  
  
#### <a name="to-verify-that-processpurchaseorder-13-is-re-created"></a><span data-ttu-id="7a5bf-240">验证 ProcessPurchaseOrder 1.3 已重新创建</span><span class="sxs-lookup"><span data-stu-id="7a5bf-240">To verify that ProcessPurchaseOrder 1.3 is re-created</span></span>  
  
1.  <span data-ttu-id="7a5bf-241">上**启动**菜单中，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-241">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="7a5bf-242">如果必须已经打开，请按 F5 或单击**重新加载**上**文件**菜单进行刷新。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-242">If you have it already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-243">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-243">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="7a5bf-244">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-244">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="7a5bf-245">在策略浏览器窗口中，展开**策略**，你应该看到**ProcessPurchaseOrder**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-245">In the Policy Explorer window, expand **Policies** and you should see **ProcessPurchaseOrder**.</span></span>  
  
3.  <span data-ttu-id="7a5bf-246">展开**ProcessPurchaseOrder** ，你应该看到**版本 1.3-已发布**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-246">Expand **ProcessPurchaseOrder** and you should see **Version 1.3 - Published**.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a><span data-ttu-id="7a5bf-247">通过使用从 BizTalk Server 管理控制台导出的 XML 文件部署策略的过程</span><span class="sxs-lookup"><span data-stu-id="7a5bf-247">Procedures for Deploying the Policy by Using an XML file Exported from the BizTalk Server Administration Console</span></span>  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a><span data-ttu-id="7a5bf-248">将 ProcessPurchaseOrder 1.3 策略和 POVocabulary 词汇导出到某一 XML 文件</span><span class="sxs-lookup"><span data-stu-id="7a5bf-248">To export the ProcessPurchaseOrder 1.3 policy and the POVocabulary vocabulary to an XML file</span></span>  
  
1. <span data-ttu-id="7a5bf-249">上**启动**菜单中，打开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-249">On the **Start** menu, open [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span> <span data-ttu-id="7a5bf-250">如果已打开该工具，请按 F5 键刷新。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-250">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="7a5bf-251">展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**应用程序**，然后展开**RuleTestApp**.</span><span class="sxs-lookup"><span data-stu-id="7a5bf-251">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Applications**, and then expand **RuleTestApp**.</span></span>  
  
3. <span data-ttu-id="7a5bf-252">单击**策略**，并确保你看到 ProcessPurchaseOrder 1.3 策略列表中的。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-252">Click **Policies** and make sure that you see the ProcessPurchaseOrder 1.3 policy in the list.</span></span>  
  
4. <span data-ttu-id="7a5bf-253">右键单击**ProcessPurchaseOrder**，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-253">Right-click **ProcessPurchaseOrder**, and then click **Export**.</span></span>  
  
5. <span data-ttu-id="7a5bf-254">在中**导出策略**对话框框中，请确保**ProcessPurchaseOrder**策略并**POVocabulary**选择。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-254">In the **Export Policies** dialog box, make sure the **ProcessPurchaseOrder** policy and the **POVocabulary** are selected.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="7a5bf-255">可以通过右键单击导出到 XML 文件的应用程序中的所有策略**RuleTest** ，然后单击**都导出**上**策略**菜单。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-255">You can export all the policies in an application to an XML file by right-clicking **RuleTest** and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="7a5bf-256">这样，您就可以将此应用程序使用的所有策略和词汇都导出到单个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-256">This way you can export all the policies and vocabulary used by this application to a single XML file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="7a5bf-257">可以通过右键单击导出到 XML 文件的所有应用程序中的所有策略**应用程序**节点，然后单击**都导出**上**策略**菜单。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-257">You can export all the policies in all the applications to an XML file by right-clicking the **Applications** node and then clicking **Export** on the **Policies** menu.</span></span> <span data-ttu-id="7a5bf-258">这样，您就可以将所有应用程序使用的所有策略和词汇都导出到单个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-258">This way you can export all the policies and vocabularies used by all the applications into a single XML file.</span></span>  
  
6. <span data-ttu-id="7a5bf-259">指定输出 XML 文件的名称 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-259">Specify an output XML file name (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**), and then click **Ok**.</span></span>  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a><span data-ttu-id="7a5bf-260">删除 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="7a5bf-260">To delete the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="7a5bf-261">在 BizTalk Server 管理，右键单击**ProcessPurchaseOrder**在列表中，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-261">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** in the list, and then click **Remove**.</span></span>  
  
2.  <span data-ttu-id="7a5bf-262">单击**是**中**删除策略**消息框。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-262">Click **Yes** in the **Remove Policy** message box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-263">如果该策略为已部署状态，则无法删除它。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-263">If the policy is in the deployed state, it cannot be removed.</span></span> <span data-ttu-id="7a5bf-264">右键单击**ProcessPurchaseOrder**，然后单击**Undeploy**取消部署策略。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-264">Right-click **ProcessPurchaseOrder**, and then click **Undeploy** to undeploy the policy.</span></span> <span data-ttu-id="7a5bf-265">**删除**取消部署该策略时，菜单项是否可用。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-265">The **Remove** menu item is available when the policy is undeployed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-266">在其上的词汇**ProcessPurchaseOrder**策略所依赖，这种情况下**POVocabulary**，也会被删除。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-266">The vocabularies on which the **ProcessPurchaseOrder** policy depends, in this case **POVocabulary**, are also deleted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-267">在您从某一应用程序删除策略时，该策略以及它所依赖的词汇也将从规则引擎数据库中删除，而不只是从应用程序中删除。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-267">When you remove a policy from an application, the policy and the vocabularies that it depends on are deleted from the rule engine database as well, not just from the application.</span></span>  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a><span data-ttu-id="7a5bf-268">导入 XML 文件以便重新创建 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="7a5bf-268">To import the XML file to re-create the ProcessPurchaseOrder policy</span></span>  
  
1. <span data-ttu-id="7a5bf-269">在 BizTalk Server 管理中，展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-269">In BizTalk Server Administration, expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
2. <span data-ttu-id="7a5bf-270">右键单击**应用程序**，依次指向**导入**，然后单击**策略**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-270">Right-click **Applications**, point to **Import**, and then click **Policies**.</span></span>  
  
3. <span data-ttu-id="7a5bf-271">浏览，然后双击 XML 文件 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) 在第一个过程中创建。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-271">Browse, and double-click the XML file (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) that you created in the first procedure.</span></span>  
  
4. <span data-ttu-id="7a5bf-272">展开**\<的所有项目\>** 下**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-272">Expand **\<All Artifacts\>** under **Applications**.</span></span>  
  
5. <span data-ttu-id="7a5bf-273">单击**策略**，并且你应看到的 1.3 版**ProcessPurchaseOrder**策略列表中的。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-273">Click **Policies**, and you should see version 1.3 of the **ProcessPurchaseOrder** policy in the list.</span></span>  
  
6. <span data-ttu-id="7a5bf-274">按下 F5 键来刷新视图。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-274">Press F5 to refresh the view.</span></span> <span data-ttu-id="7a5bf-275">**ProcessPurchaseOrder**策略应采用**不发布**状态。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-275">The **ProcessPurchaseOrder** policy should be in the **Not Published** state.</span></span>  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a><span data-ttu-id="7a5bf-276">将 ProcessPurchaseOrder 策略添加到 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="7a5bf-276">To add the ProcessPurchaseOrder policy to the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="7a5bf-277">在 BizTalk Server 管理，右键单击**ProcessPurchaseOrder**策略，并单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-277">In BizTalk Server Administration, right-click **ProcessPurchaseOrder** policy, and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-278">只有已发布的策略才能添加到 BizTalk 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-278">Only published policies can be added to a BizTalk application.</span></span>  
  
2.  <span data-ttu-id="7a5bf-279">在中**应用程序**节点，展开**RuleTestApp**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-279">In the **Applications** node, expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="7a5bf-280">单击**策略**中**RuleTestApp**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-280">Click **Policies** in **RuleTestApp**.</span></span>  
  
4.  <span data-ttu-id="7a5bf-281">在右侧的列表中右键单击，指向**外**，然后单击**策略**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-281">Right-click in the list on the right, point to **Add**, and then click **Policy**.</span></span>  
  
5.  <span data-ttu-id="7a5bf-282">展开**ProcessPurchaseOrder**节点中，选中的复选框**版本 1.3 （已发布）**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-282">Expand the **ProcessPurchaseOrder** node, select the check box for **Version 1.3 (Published)**, and then click **OK**.</span></span> <span data-ttu-id="7a5bf-283">实例时都提供 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-283">.</span></span>  
  
6.  <span data-ttu-id="7a5bf-284">右键单击**ProcessPurchaseOrder**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-284">Right-click **ProcessPurchaseOrder**, and then click **Deploy**.</span></span> <span data-ttu-id="7a5bf-285">如果没有看到**ProcessPurchaseOrder**在列表中，按 F5 刷新视图。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-285">If you do not see **ProcessPurchaseOrder** in the list, press F5 to refresh the view.</span></span>  
  
7.  <span data-ttu-id="7a5bf-286">单击**是**的确认消息框中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-286">Click **Yes** in the confirmation message box.</span></span>  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a><span data-ttu-id="7a5bf-287">通过使用 MSI 文件部署策略的过程</span><span class="sxs-lookup"><span data-stu-id="7a5bf-287">Procedures for Deploying the Policy by Using an MSI File</span></span>  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a><span data-ttu-id="7a5bf-288">将 RuleTestApp 应用程序导出到某一 MSI 文件</span><span class="sxs-lookup"><span data-stu-id="7a5bf-288">To export the RuleTestApp application to an MSI file</span></span>  
  
1. <span data-ttu-id="7a5bf-289">上**启动**菜单中，打开**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-289">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="7a5bf-290">如果已打开该工具，请按 F5 键刷新。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-290">If you have the tool already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="7a5bf-291">展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-291">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="7a5bf-292">右键单击**RuleTestApp**，依次指向**导出**，然后单击**MSI 文件**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-292">Right-click **RuleTestApp**, point to **Export**, and then click **MSI file**.</span></span>  
  
4. <span data-ttu-id="7a5bf-293">上**欢迎使用导出 MSI 文件向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-293">On the **Welcome to the Export MSI File Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="7a5bf-294">上**选择资源**页上，查看所有默认选项，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-294">On the **Select Resources** page, review all the default options, and then click **Next**.</span></span>  
  
6. <span data-ttu-id="7a5bf-295">上**指定 IIS 主机**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-295">On the **Specify IIS Hosts** page, click **Next**.</span></span>  
  
7. <span data-ttu-id="7a5bf-296">上**依赖项**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-296">On the **Dependencies** page, click **Next**.</span></span>  
  
8. <span data-ttu-id="7a5bf-297">上**目标**页上，指定的目录和名称作为 MSI **C:\BRE-Walkthroughs\RuleTestApp.msi**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-297">On the **Destination** page, specify the directory and name for the MSI as **C:\BRE-Walkthroughs\RuleTestApp.msi**.</span></span>  
  
9. <span data-ttu-id="7a5bf-298">单击 **“导出”**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-298">Click **Export**.</span></span>  
  
10. <span data-ttu-id="7a5bf-299">上**摘要**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-299">On the **Summary** page, click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-300">在您导出 RuleTestApp 应用程序时，该应用程序所使用的策略和词汇也将导出到 MSI 文件中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-300">When you export the RuleTestApp application, the policies and vocabularies used by the application are also exported in the MSI file.</span></span> <span data-ttu-id="7a5bf-301">以后，在您导入该 MSI 文件时，词汇、策略和应用程序也都会重新创建。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-301">Later, when you import the MSI file, the vocabulary, policy, and application are all re-created.</span></span>  
  
#### <a name="to-delete-the-ruletestapp-application"></a><span data-ttu-id="7a5bf-302">删除 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="7a5bf-302">To delete the RuleTestApp application</span></span>  
  
1.  <span data-ttu-id="7a5bf-303">在 BizTalk Server 管理，右键单击**RuleTestApp**，然后检查**删除**菜单是启用还是禁用状态。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-303">In BizTalk Server Administration, right-click **RuleTestApp**, and check if the **Delete** menu is enabled or disabled.</span></span>  
  
2.  <span data-ttu-id="7a5bf-304">如果**删除**已禁用，右键单击**RuleTestApp**，单击**停止**，选择**完全停止-终止实例**，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-304">If **Delete** is disabled, right-click **RuleTestApp**, click **Stop**, select **Full Stop - Terminate Instance**, and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="7a5bf-305">右键单击**RuleTestApp**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-305">Right-click **RuleTestApp**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="7a5bf-306">单击**是**以确认删除。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-306">Click **Yes** to confirm deletion.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-307">在您删除某一应用程序时，该应用程序中的所有策略以及相关词汇也将从规则引擎数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-307">When you delete an application, all the policies in the application and dependent vocabularies are deleted from the rule engine database as well.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a><span data-ttu-id="7a5bf-308">验证 ProcessPurchaseOrder 策略和 POVocabulary 词汇已删除</span><span class="sxs-lookup"><span data-stu-id="7a5bf-308">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are deleted</span></span>  
  
1.  <span data-ttu-id="7a5bf-309">上**启动**菜单中，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-309">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="7a5bf-310">如果你有业务规则编辑器已打开，请按 f5 键刷新。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-310">If you have Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-311">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-311">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="7a5bf-312">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-312">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="7a5bf-313">在策略浏览器窗口中，展开**策略**，并确保 ProcessPurchaseOrder 策略不存在。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-313">In the Policy Explorer window, expand **Policies**, and make sure that the ProcessPurchaseOrder policy does not exist.</span></span>  
  
3.  <span data-ttu-id="7a5bf-314">在事实浏览器窗口中，展开**词汇**，并确保 POVocabulary 不存在。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-314">In the Facts Explorer window, expand **Vocabularies**, and make sure that POVocabulary does not exist.</span></span>  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a><span data-ttu-id="7a5bf-315">导入 MSI 文件以便重新创建 RuleTestApp 应用程序</span><span class="sxs-lookup"><span data-stu-id="7a5bf-315">To import the MSI file to re-create the RuleTestApp application</span></span>  
  
1. <span data-ttu-id="7a5bf-316">上**启动**菜单中，打开**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-316">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="7a5bf-317">如果 BizTalk Server 管理控制台已经打开，则按下 F5 键以便刷新它。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-317">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="7a5bf-318">展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-318">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span>  
  
3. <span data-ttu-id="7a5bf-319">右键单击**应用程序**，依次指向**导入**，然后单击**MSI 文件**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-319">Right-click **Applications**, point to **Import**, and then click **MSI file**.</span></span>  
  
4. <span data-ttu-id="7a5bf-320">上**欢迎使用导入向导**页上，浏览并选择前面导出的 MSI 文件 (RuleTestApp.msi)**要导入的 MSI 文件**设置。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-320">On the **Welcome to the Import Wizard** page, browse and select the MSI file (RuleTestApp.msi) you exported earlier for the **MSI file to import** setting.</span></span>  
  
5. <span data-ttu-id="7a5bf-321">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-321">Click **Next**.</span></span>  
  
6. <span data-ttu-id="7a5bf-322">上**应用程序设置**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-322">On the **Application Settings** page, click **Next**.</span></span>  
  
7. <span data-ttu-id="7a5bf-323">上**应用程序目标环境设置**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-323">On the **Application Target Environment Settings** page, click **Next**.</span></span>  
  
8. <span data-ttu-id="7a5bf-324">上**导入摘要**页上，单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-324">On the **Import Summary** page, click **Import**.</span></span>  
  
9. <span data-ttu-id="7a5bf-325">上**导入成功**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-325">On the **Import Succeeded** page, click **Finish**.</span></span> <span data-ttu-id="7a5bf-326">您应该会看到**RuleTestApp**下创建应用程序**应用程序**BizTalk Server 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-326">You should see that the **RuleTestApp** application is created under **Applications** in the BizTalk Server Administration console.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-is-added-to-ruletestapp"></a><span data-ttu-id="7a5bf-327">验证 ProcessPurchaseOrder 策略已添加到 RuleTestApp</span><span class="sxs-lookup"><span data-stu-id="7a5bf-327">To verify that the ProcessPurchaseOrder policy is added to RuleTestApp</span></span>  
  
1.  <span data-ttu-id="7a5bf-328">展开**RuleTestApp** BizTalk Server 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-328">Expand **RuleTestApp** in the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="7a5bf-329">选择**策略**，你应该看到**ProcessPurchaseOrder**右窗格中列表中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-329">Select **Policies** and you should see **ProcessPurchaseOrder** in the list in the right pane.</span></span>  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-re-created"></a><span data-ttu-id="7a5bf-330">确认 ProcessPurchaseOrder 策略和 POVocabulary 词汇已重新创建</span><span class="sxs-lookup"><span data-stu-id="7a5bf-330">To verify that the ProcessPurchaseOrder policy and POVocabulary vocabulary are re-created</span></span>  
  
1.  <span data-ttu-id="7a5bf-331">上**启动**菜单中，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-331">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="7a5bf-332">如果已打开业务规则编辑器，请按 F5 键刷新。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-332">If you have it already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-333">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-333">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="7a5bf-334">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-334">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="7a5bf-335">在策略浏览器窗口中，展开**策略**，并确保选中**ProcessPurchaseOrder**存在。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-335">In the Policy Explorer window, expand **Policies**, and make sure that **ProcessPurchaseOrder** exists.</span></span>  
  
3.  <span data-ttu-id="7a5bf-336">在事实浏览器窗口中，展开**词汇**，并确保选中**POVocabulary**存在。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-336">In the Facts Explorer window, expand **Vocabularies**, and make sure that **POVocabulary** exists.</span></span>  
  
#### <a name="to-test-the-solution"></a><span data-ttu-id="7a5bf-337">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="7a5bf-337">To test the solution</span></span>  
  
1. <span data-ttu-id="7a5bf-338">上**启动**菜单中，打开**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-338">On the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="7a5bf-339">如果 BizTalk Server 管理控制台已经打开，则按下 F5 键以便刷新它。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-339">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2. <span data-ttu-id="7a5bf-340">展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-340">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="7a5bf-341">右键单击**RuleTestApp**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-341">Right-click **RuleTestApp**, and then click **Start**.</span></span>  
  
4. <span data-ttu-id="7a5bf-342">单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-342">Click **Start**.</span></span>  
  
5. <span data-ttu-id="7a5bf-343">复制**SamplePO.xml**中创建[演练： 测试策略](../core/walkthrough-testing-the-policy.md)到业务流程的输入目录。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-343">Copy **SamplePO.xml** that you created in [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) to the input directory for the orchestration.</span></span>  
  
6. <span data-ttu-id="7a5bf-344">你应该在输出目录中看到业务流程的输出文件。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-344">You should see an output file in the output directory for the orchestration.</span></span> <span data-ttu-id="7a5bf-345">打开输出 XML 文件，可以看到的值**状态**字段设置为**Approved**。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-345">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
7. <span data-ttu-id="7a5bf-346">重复步骤 3 和 4 个，带有**SamplePO2.xml**，您会发现的值**状态**输出文档中的字段是与输入文档中的相同 (**XYZ**)。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-346">Repeat steps 3 and 4 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**XYZ**).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="7a5bf-347">注释</span><span class="sxs-lookup"><span data-stu-id="7a5bf-347">Comments</span></span>  
  
-   <span data-ttu-id="7a5bf-348">它是**非常重要**请切记，当从应用程序中删除策略时，不只是删除该应用程序和策略之间的关联; 你还删除了策略及其关联的词汇从规则引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-348">It is **very important** to remember that when you remove a policy from an application, you do not just remove the association between the application and the policy; you also delete the policy and its associated vocabulary from the rule engine database.</span></span>  
  
-   <span data-ttu-id="7a5bf-349">在您开始某一应用程序时，默认情况下，该应用程序将自动部署策略。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-349">When you start an application, by default, it deploys the policies automatically.</span></span> <span data-ttu-id="7a5bf-350">同样，你停止应用程序并选择**完全停止-终止实例**，关联的策略会自动取消部署。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-350">Similarly, when you stop an application and select **Full Stop - Terminate Instances**, the associated policies are undeployed automatically.</span></span> <span data-ttu-id="7a5bf-351">当选择**部分停止-挂起正在运行的实例**，关联的策略都不会自动取消部署。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-351">When you select **Partial Stop - Suspend running instances**, the associated policies are not undeployed automatically.</span></span>  
  
-   <span data-ttu-id="7a5bf-352">您应该在业务规则编辑器和 BizTalk Server 管理控制台中刷新视图，以便确保在执行任何操作前查看最新信息。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-352">You should refresh the views in Business Rule Composer and BizTalk Server Administration console to make sure you are looking at the latest information before performing any operation.</span></span>  
  
-   <span data-ttu-id="7a5bf-353">如果您创建其先前版本与某一 BizTalk 应用程序关联的策略的新版本，则应手动将该策略的新版本添加到该应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-353">If you create a new version of the policy whose earlier version is associated with a BizTalk application, you should manually add the new version of the policy to the application.</span></span> <span data-ttu-id="7a5bf-354">您不应删除该策略的旧版本，除非确实要从规则引擎数据库中删除它。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-354">You should not remove the old version of the policy unless you really want to delete it from the rule engine database.</span></span>  
  
-   <span data-ttu-id="7a5bf-355">您可以在导入前将两个或多个 BRL（业务规则语言 XML 文件）文件合并到单个 BRL 文件中。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-355">You can merge two or more BRL (Business Rule Language XML file) files into a single BRL file before importing.</span></span> <span data-ttu-id="7a5bf-356">下面的代码显示三个 BRL 文件。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-356">The following code shows three BRL files.</span></span> <span data-ttu-id="7a5bf-357">第一个 BRL 文件包含**POVocabulary**词汇。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-357">The first BRL file contains the **POVocabulary** vocabulary.</span></span> <span data-ttu-id="7a5bf-358">第二个 BRL 文件包含**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-358">The second BRL file contains the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="7a5bf-359">第三个 BRL 文件同时包含**POVocabulary**词汇和**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-359">The third BRL file contains both the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="7a5bf-360">通过执行以下步骤创建第三个 BRE 文件：</span><span class="sxs-lookup"><span data-stu-id="7a5bf-360">The third BRE file is created by performing the following steps:</span></span>  
  
    1.  <span data-ttu-id="7a5bf-361">创建新的文件使用的任何文件编辑器，并将其保存为 XML 文件 (例如： POPolicyVocabulary.xml)。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-361">Create a new file using any file editor and save it as an XML file (for example: POPolicyVocabulary.xml).</span></span>  
  
    2.  <span data-ttu-id="7a5bf-362">从包含词汇的第一个 BRL 文件复制整个 XML 内容。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-362">Copy the entire XML content from the first BRL file containing the vocabulary.</span></span>  
  
    3.  <span data-ttu-id="7a5bf-363">复制规则集块 (开头\<ruleset\>标记和以结尾\</ruleset\>标记) 从第二个 BRL 文件。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-363">Copy the ruleset block (starts with the \<ruleset\> tag and ends with the \</ruleset\> tag) from the second BRL file.</span></span>  
  
    4.  <span data-ttu-id="7a5bf-364">保存该新文件。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-364">Save the new file.</span></span> <span data-ttu-id="7a5bf-365">可以导入此单个 XML 文件以创建**POVocabulary**词汇和**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-365">You can import this single XML file to create the **POVocabulary** vocabulary and the **ProcessPurchaseOrder** policy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5bf-366">词汇和规则集节点在合并的 BRL 文件中的列出顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-366">It does not matter in which order the vocabulary and ruleset nodes are listed in the merged BRL file.</span></span> <span data-ttu-id="7a5bf-367">您可以将规则集节点置于词汇节点前。</span><span class="sxs-lookup"><span data-stu-id="7a5bf-367">You can have the ruleset node ahead of the vocabulary node.</span></span>  
  
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