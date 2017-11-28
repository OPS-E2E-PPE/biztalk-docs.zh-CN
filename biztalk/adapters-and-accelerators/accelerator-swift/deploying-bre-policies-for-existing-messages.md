---
title: "部署的现有消息 BRE 策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 585c903d-ee44-4e92-8798-febb176367e3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b03f6f3319e90d4782e1e9e5fd7e2a7e2a27b527
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-bre-policies-for-existing-messages"></a><span data-ttu-id="050a6-102">将 BRE 策略部署的现有消息</span><span class="sxs-lookup"><span data-stu-id="050a6-102">Deploying BRE Policies for Existing Messages</span></span>
<span data-ttu-id="050a6-103">**部署相关的业务规则：**</span><span class="sxs-lookup"><span data-stu-id="050a6-103">**To deploy the related business rules:**</span></span>  
  
1.  <span data-ttu-id="050a6-104">单击**启动**，单击**程序**，单击**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BRE 部署实用工具**。</span><span class="sxs-lookup"><span data-stu-id="050a6-104">Click **Start**, click **Programs**, click **Microsoft BizTalk Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="050a6-105">在 BRE 部署实用程序，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="050a6-105">In BRE Deployment Utility, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="050a6-106">在.NET 全局程序集缓存对话框中，选择**SWIFT MX 架构**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="050a6-106">In the .NET Global Assembly Cache dialog box, select **SWIFT MX Schema**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="050a6-107">单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="050a6-107">Click **Deploy**.</span></span>  
  
     <span data-ttu-id="050a6-108">根据使用该程序集部署的架构，部署实用工具标识相关的规则，并将其发布与 BRE 一起使用。</span><span class="sxs-lookup"><span data-stu-id="050a6-108">Based on the schemas deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="050a6-109">完成后，BRE 部署实用工具，则显示以下消息:"部署已完成。</span><span class="sxs-lookup"><span data-stu-id="050a6-109">When complete, the BRE Deployment Utility displays the following message: "Deployment has completed.</span></span> <span data-ttu-id="050a6-110">查看日志文件或业务规则编辑器的详细信息。"</span><span class="sxs-lookup"><span data-stu-id="050a6-110">View the log file or Business Rules Composer for details."</span></span>  
  
5.  <span data-ttu-id="050a6-111">关闭 SWIFT BRE 部署实用工具的对话框。</span><span class="sxs-lookup"><span data-stu-id="050a6-111">Close the SWIFT BRE Deployment Utility dialog box.</span></span>  
  
6.  <span data-ttu-id="050a6-112">在 Windows 资源管理器，浏览到*\<驱动器 >*: \Documents and Settings\All Users\Application 数据，以确认日志文件 BREDeploymentLog.txt 显示在文件夹中。</span><span class="sxs-lookup"><span data-stu-id="050a6-112">In Windows Explorer, browse to *\<drive>*:\Documents and Settings\All Users\Application Data to confirm that the log file BREDeploymentLog.txt appears in the folder.</span></span>  
  
7.  <span data-ttu-id="050a6-113">单击**启动**，单击**运行**，类型**services.msc**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="050a6-113">Click **Start**, click **Run**, type **services.msc**, and then click **OK**.</span></span> <span data-ttu-id="050a6-114">在服务 （本地） 窗口中，右键单击**规则引擎更新服务**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="050a6-114">In the Services (Local) window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>