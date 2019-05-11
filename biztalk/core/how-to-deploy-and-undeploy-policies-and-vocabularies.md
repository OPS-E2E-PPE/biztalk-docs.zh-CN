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
ms.openlocfilehash: ff5e213cc0ad820bbaa6129ee5e6cf816c3ba0b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385285"
---
# <a name="how-to-deploy-and-undeploy-policies-and-vocabularies"></a><span data-ttu-id="266ab-102">如何部署和取消部署策略及词汇</span><span class="sxs-lookup"><span data-stu-id="266ab-102">How to Deploy and Undeploy Policies and Vocabularies</span></span>
<span data-ttu-id="266ab-103">规则引擎部署向导可用于部署或取消部署策略。</span><span class="sxs-lookup"><span data-stu-id="266ab-103">You can use the Rule Engine Deployment Wizard to deploy or undeploy a policy.</span></span>  
  
 <span data-ttu-id="266ab-104">在规则引擎部署向导中，当您尝试部署，唯一的已发布的策略版本下拉列表中显示。</span><span class="sxs-lookup"><span data-stu-id="266ab-104">In the Rule Engine Deployment Wizard, when you try to deploy, only published policy versions are shown in the drop-down list.</span></span> <span data-ttu-id="266ab-105">当尝试取消部署时，仅部署的策略版本显示在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="266ab-105">When you try to undeploy, only deployed policy versions are shown in the drop-down list.</span></span>  
  
### <a name="to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="266ab-106">若要部署或取消部署策略</span><span class="sxs-lookup"><span data-stu-id="266ab-106">To deploy or undeploy a policy</span></span>  
  
1. <span data-ttu-id="266ab-107">单击**启动**，依次指向**Program Files**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="266ab-107">Click **Start**, point to **Program Files**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="266ab-108">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="266ab-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="266ab-109">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="266ab-109">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2. <span data-ttu-id="266ab-110">上**规则引擎部署向导**欢迎页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="266ab-110">On the **Rules Engine Deployment Wizard** welcome page, click **Next**.</span></span>  
  
3. <span data-ttu-id="266ab-111">选择任一**部署策略**或**取消部署策略**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="266ab-111">Select either **Deploy Policy** or **Undeploy Policy**, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="266ab-112">从下拉列表中，选择可用的 SQL Server 计算机和数据库，然后依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="266ab-112">From the drop-down lists, select an available SQL Server computer and database, and then click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="266ab-113">您可以只部署到所配置的规则存储数据库。</span><span class="sxs-lookup"><span data-stu-id="266ab-113">You can only deploy to the rule store database that you are configured against.</span></span> <span data-ttu-id="266ab-114">尝试部署到其他数据库将产生错误。</span><span class="sxs-lookup"><span data-stu-id="266ab-114">An attempt to deploy to a different DB will give an error.</span></span>  
  
5. <span data-ttu-id="266ab-115">从下拉列表中，选择一个策略，然后依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="266ab-115">From the drop-down list, select a policy, and then click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="266ab-116">当你尝试部署时，仅已发布的策略版本显示在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="266ab-116">When you try to deploy, only published policy versions are shown in the drop-down list.</span></span> <span data-ttu-id="266ab-117">当尝试取消部署时，仅部署的策略版本显示在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="266ab-117">When you try to undeploy, only deployed policy versions are shown in the drop-down list.</span></span>  
  
6. <span data-ttu-id="266ab-118">查看服务器、 数据库和策略信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="266ab-118">Review the server, database, and policy information, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="266ab-119">查看部署或取消部署的进度。</span><span class="sxs-lookup"><span data-stu-id="266ab-119">Watch the progress of the deployment or undeployment.</span></span> <span data-ttu-id="266ab-120">完成后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="266ab-120">When it is finished, click **Next**.</span></span>  
  
8. <span data-ttu-id="266ab-121">查看部署或取消部署的完成状态，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="266ab-121">Review the completion status of the deployment or undeployment, and then click **Finish**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="266ab-122">此外可以部署或通过右键单击策略版本，然后单击取消部署策略版本从业务规则编辑器内的**部署**或**Undeploy**。</span><span class="sxs-lookup"><span data-stu-id="266ab-122">You can also deploy or undeploy a policy version from within the Business Rule Composer by right-clicking the policy version and then clicking **Deploy** or **Undeploy**.</span></span>