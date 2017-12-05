---
title: "第 1 课： 部署相关的业务规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, deploying
- deploying, business rules
ms.assetid: f8f5b103-4b66-4836-8165-99692574961a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17c4b470b802a980306481361c1fafcec4f70269
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-1-deploying-the-related-business-rules"></a><span data-ttu-id="57ceb-102">第 1 课： 部署相关的业务规则</span><span class="sxs-lookup"><span data-stu-id="57ceb-102">Lesson 1: Deploying the Related Business Rules</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="57ceb-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]包括在 A4SWIFT 软件开发工具包 (SDK) 调用业务规则引擎 (BRE) 部署实用工具的程序。</span><span class="sxs-lookup"><span data-stu-id="57ceb-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes a program in the A4SWIFT Software Development Kit (SDK) called the Business Rule Engine (BRE) Deployment Utility.</span></span> <span data-ttu-id="57ceb-104">在本课程中，你可以使用此实用程序来检查程序集的已部署架构，确定所需的规则，并将必要的词汇和每个架构的策略部署。</span><span class="sxs-lookup"><span data-stu-id="57ceb-104">In this lesson, you use this utility to inspect an assembly for deployed schemas, determine the required rules, and deploy the necessary vocabularies and policies for each schema.</span></span>  
  
 <span data-ttu-id="57ceb-105">您还可以通过使用 SWIFT 标准版本指南 (SRG) 来识别所需的规则，然后使用业务规则编辑器工具部署的词汇和策略部署规则。</span><span class="sxs-lookup"><span data-stu-id="57ceb-105">You can also deploy rules by using the SWIFT Standards Release Guides (SRG) to identify the necessary rules and then use the Business Rule Composer tool to deploy the vocabularies and policies.</span></span>  
  
### <a name="to-deploy-the-related-business-rules"></a><span data-ttu-id="57ceb-106">若要部署的相关的业务规则</span><span class="sxs-lookup"><span data-stu-id="57ceb-106">To deploy the related business rules</span></span>  
  
1.  <span data-ttu-id="57ceb-107">单击**启动**，指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for SWIFT**，然后单击**BRE 部署实用工具**。</span><span class="sxs-lookup"><span data-stu-id="57ceb-107">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="57ceb-108">在 BRE 部署实用工具的对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="57ceb-108">In the BRE Deployment Utility dialog box, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="57ceb-109">在.NET 全局程序集缓存对话框中，选择**SWIFTSchemas**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="57ceb-109">In the .NET Global Assembly Cache dialog box, select **SWIFTSchemas**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="57ceb-110">对程序集的 SWIFTSchemas 引用你以前部署。</span><span class="sxs-lookup"><span data-stu-id="57ceb-110">SWIFTSchemas refers to the assembly you previously deployed.</span></span>  
  
4.  <span data-ttu-id="57ceb-111">单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="57ceb-111">Click **Deploy**.</span></span>  
  
     <span data-ttu-id="57ceb-112">根据使用该程序集部署的架构，部署实用工具标识相关的规则，并将其发布与 BRE 一起使用。</span><span class="sxs-lookup"><span data-stu-id="57ceb-112">Based on the schemas you deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="57ceb-113">完成后，BRE 部署实用程序显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="57ceb-113">When complete, the BRE Deployment Utility displays the following message:</span></span>  
  
     <span data-ttu-id="57ceb-114">**部署已完成。有关详细信息中查看日志文件或业务规则编辑器。**</span><span class="sxs-lookup"><span data-stu-id="57ceb-114">**Deployment has completed. View the log file or Business Rules Composer for details.**</span></span>  
  
5.  <span data-ttu-id="57ceb-115">关闭 SWIFT BRE 部署实用工具的对话框。</span><span class="sxs-lookup"><span data-stu-id="57ceb-115">Close the SWIFT BRE Deployment Utility dialog box.</span></span>  
  
6.  <span data-ttu-id="57ceb-116">在 Windows 资源管理器，浏览到\<*驱动器*\>: \Documents and Settings\All Users\Application 数据，以确认日志文件**BREDeploymentLog.txt**出现在文件夹。</span><span class="sxs-lookup"><span data-stu-id="57ceb-116">In Windows Explorer, browse to \<*drive*\>:\Documents and Settings\All Users\Application Data to confirm that the log file **BREDeploymentLog.txt** appears in the folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="57ceb-117">你可以打开日志文件使用文本编辑器以确认每个部署步骤。</span><span class="sxs-lookup"><span data-stu-id="57ceb-117">You can open the log file using a text editor to confirm each of the deployment steps.</span></span>  
  
7.  <span data-ttu-id="57ceb-118">重新启动的规则引擎更新服务。</span><span class="sxs-lookup"><span data-stu-id="57ceb-118">Restart the Rule Engine Update Service.</span></span> <span data-ttu-id="57ceb-119">通过单击来做到**启动**、 单击**运行**、 输入**services.msc**，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="57ceb-119">Do so by clicking **Start**, clicking **Run**, entering **services.msc**, and clicking **OK**.</span></span> <span data-ttu-id="57ceb-120">在**服务 （本地）**窗口中，右键单击**规则引擎更新服务**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="57ceb-120">In the **Services (Local)** window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>  
  
 <span data-ttu-id="57ceb-121">继续执行[第 2 课： 确认使用业务规则 Composer 工具部署](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="57ceb-121">Proceed to [Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md).</span></span>