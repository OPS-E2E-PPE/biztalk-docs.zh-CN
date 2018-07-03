---
title: 如何部署和取消部署策略及词汇 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, policies
- policies, deploying
- deploying, vocabularies
- policies, undeploying
- vocabularies, deploying
ms.assetid: 9a7e3310-54b7-482c-8210-b4b11fde4c49
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a2c6200f41a4b473175528ac6d2c8ee75c17894
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013062"
---
# <a name="how-to-deploy-and-undeploy-policies-and-vocabularies"></a><span data-ttu-id="3cc9e-102">如何部署和取消部署策略及词汇</span><span class="sxs-lookup"><span data-stu-id="3cc9e-102">How to Deploy and Undeploy Policies and Vocabularies</span></span>
<span data-ttu-id="3cc9e-103">你可以使用规则引擎部署向导来部署策略或取消部署策略。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-103">You can use the Rule Engine Deployment Wizard to deploy or undeploy a policy.</span></span>  
  
 <span data-ttu-id="3cc9e-104">在规则引擎部署向导中尝试进行部署时，下拉列表中将只显示已发布的策略版本。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-104">In the Rule Engine Deployment Wizard, when you try to deploy, only published policy versions are shown in the drop-down list.</span></span> <span data-ttu-id="3cc9e-105">在尝试取消部署时，下拉列表中则只显示已部署的策略版本。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-105">When you try to undeploy, only deployed policy versions are shown in the drop-down list.</span></span>  
  
### <a name="to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="3cc9e-106">部署或取消部署策略</span><span class="sxs-lookup"><span data-stu-id="3cc9e-106">To deploy or undeploy a policy</span></span>  
  
1. <span data-ttu-id="3cc9e-107">单击**启动**，依次指向**Program Files**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-107">Click **Start**, point to **Program Files**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3cc9e-108">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="3cc9e-109">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-109">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2. <span data-ttu-id="3cc9e-110">上**规则引擎部署向导**欢迎页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-110">On the **Rules Engine Deployment Wizard** welcome page, click **Next**.</span></span>  
  
3. <span data-ttu-id="3cc9e-111">选择任一**部署策略**或**取消部署策略**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-111">Select either **Deploy Policy** or **Undeploy Policy**, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="3cc9e-112">从下拉列表中，选择可用的 SQL Server 计算机和数据库，然后依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-112">From the drop-down lists, select an available SQL Server computer and database, and then click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3cc9e-113">只能部署到所配置的规则存储数据库中。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-113">You can only deploy to the rule store database that you are configured against.</span></span> <span data-ttu-id="3cc9e-114">如果尝试部署到其他数据库，则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-114">An attempt to deploy to a different DB will give an error.</span></span>  
  
5. <span data-ttu-id="3cc9e-115">从下拉列表中，选择一个策略，然后依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-115">From the drop-down list, select a policy, and then click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3cc9e-116">在尝试部署时，下拉列表中将只显示已发布的策略版本。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-116">When you try to deploy, only published policy versions are shown in the drop-down list.</span></span> <span data-ttu-id="3cc9e-117">在尝试取消部署时，下拉列表中则只显示已部署的策略版本。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-117">When you try to undeploy, only deployed policy versions are shown in the drop-down list.</span></span>  
  
6. <span data-ttu-id="3cc9e-118">查看服务器、 数据库和策略信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-118">Review the server, database, and policy information, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="3cc9e-119">监视部署或取消部署的进度。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-119">Watch the progress of the deployment or undeployment.</span></span> <span data-ttu-id="3cc9e-120">完成后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-120">When it is finished, click **Next**.</span></span>  
  
8. <span data-ttu-id="3cc9e-121">查看部署或取消部署的完成状态，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-121">Review the completion status of the deployment or undeployment, and then click **Finish**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cc9e-122">此外可以部署或通过右键单击策略版本，然后单击取消部署策略版本从业务规则编辑器内的**部署**或**Undeploy**。</span><span class="sxs-lookup"><span data-stu-id="3cc9e-122">You can also deploy or undeploy a policy version from within the Business Rule Composer by right-clicking the policy version and then clicking **Deploy** or **Undeploy**.</span></span>