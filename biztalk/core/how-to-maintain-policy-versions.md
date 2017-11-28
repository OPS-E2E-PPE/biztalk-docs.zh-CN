---
title: "如何维护策略版本 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, publishing
- publishing policies
- updating, policies
- versioning, policies
- policies, versioning
- policies, updating
ms.assetid: 6e35b2bd-1ecd-45ea-aff3-4ad2437568a4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c73b3575ec484ab611fccac920cef6d96d3800
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-maintain-policy-versions"></a><span data-ttu-id="f995a-102">如何维护策略版本</span><span class="sxs-lookup"><span data-stu-id="f995a-102">How to Maintain Policy Versions</span></span>
<span data-ttu-id="f995a-103">向策略版本添加规则后，您可以将该版本保存到规则存储中以供进一步开发使用，或者也可发布该版本以创建定义明确并且不可改变的规则集（可以部署此规则集以便在基于规则的应用程序中使用）。</span><span class="sxs-lookup"><span data-stu-id="f995a-103">After you add rules to a version of your policy, you can save the version to the rule store for further development, or you can publish it to create a well-defined, immutable set of rules that can be deployed for use in a rule-based application.</span></span>  
  
 <span data-ttu-id="f995a-104">本主题包含以下任务的过程：</span><span class="sxs-lookup"><span data-stu-id="f995a-104">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="f995a-105">创建新的空策略版本</span><span class="sxs-lookup"><span data-stu-id="f995a-105">To create an empty new version of a policy</span></span>  
  
-   <span data-ttu-id="f995a-106">保存策略版本</span><span class="sxs-lookup"><span data-stu-id="f995a-106">To save a policy version</span></span>  
  
-   <span data-ttu-id="f995a-107">发布策略版本</span><span class="sxs-lookup"><span data-stu-id="f995a-107">To publish a policy version</span></span>  
  
-   <span data-ttu-id="f995a-108">创建策略的更新版本</span><span class="sxs-lookup"><span data-stu-id="f995a-108">To create an updated version of a policy</span></span>  
  
-   <span data-ttu-id="f995a-109">更新策略以使用更新的程序集</span><span class="sxs-lookup"><span data-stu-id="f995a-109">To update a policy to use an updated assembly</span></span>  
  
### <a name="to-create-an-empty-new-version-of-a-policy"></a><span data-ttu-id="f995a-110">创建新的空策略版本</span><span class="sxs-lookup"><span data-stu-id="f995a-110">To create an empty new version of a policy</span></span>  
  
-   <span data-ttu-id="f995a-111">右键单击策略文件夹，然后单击**添加新版本**。</span><span class="sxs-lookup"><span data-stu-id="f995a-111">Right-click the policy folder, and then click **Add New Version**.</span></span>  
  
### <a name="to-save-a-policy-version"></a><span data-ttu-id="f995a-112">保存策略版本</span><span class="sxs-lookup"><span data-stu-id="f995a-112">To save a policy version</span></span>  
  
-   <span data-ttu-id="f995a-113">右键单击策略版本中，并依次**保存**。</span><span class="sxs-lookup"><span data-stu-id="f995a-113">Right-click the policy version, and then click **Save**.</span></span>  
  
### <a name="to-publish-a-policy-version"></a><span data-ttu-id="f995a-114">发布策略版本</span><span class="sxs-lookup"><span data-stu-id="f995a-114">To publish a policy version</span></span>  
  
-   <span data-ttu-id="f995a-115">右键单击策略版本中，并依次**发布**。</span><span class="sxs-lookup"><span data-stu-id="f995a-115">Right-click the policy version, and then click **Publish**.</span></span>  
  
### <a name="to-create-an-updated-version-of-a-policy"></a><span data-ttu-id="f995a-116">创建策略的更新版本</span><span class="sxs-lookup"><span data-stu-id="f995a-116">To create an updated version of a policy</span></span>  
  
1.  <span data-ttu-id="f995a-117">右键单击现有策略版本，并依次**复制**。</span><span class="sxs-lookup"><span data-stu-id="f995a-117">Right-click an existing policy version, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="f995a-118">右键单击策略文件夹，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="f995a-118">Right-click the policy folder, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="f995a-119">使用与复制的版本相同的元素，创建新的版本。</span><span class="sxs-lookup"><span data-stu-id="f995a-119">A new version is created, with the same elements as the copied version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f995a-120">如果您的策略使用一个 .NET 程序集，而该程序集进行了更新，则应将策略绑定到该程序集的更新版本。</span><span class="sxs-lookup"><span data-stu-id="f995a-120">If your policy uses a .NET assembly, and the assembly is updated, you should bind your policy to the newer version of the assembly.</span></span>  
  
### <a name="to-update-a-policy-to-use-an-updated-assembly"></a><span data-ttu-id="f995a-121">更新策略以使用更新的程序集</span><span class="sxs-lookup"><span data-stu-id="f995a-121">To update a policy to use an updated assembly</span></span>  
  
1.  <span data-ttu-id="f995a-122">单击**启动**，指向**管理工具**，指向**.NET Framework 配置**，然后单击**配置程序集**.</span><span class="sxs-lookup"><span data-stu-id="f995a-122">Click **Start**, point to **Administrative Tools**, point to **.NET Framework Configuration**, and then click **Configured Assemblies**.</span></span>  
  
2.  <span data-ttu-id="f995a-123">转到属性目标的程序集和单击**绑定策略**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f995a-123">Go to properties for the target assembly and click the **Binding Policy** tab.</span></span>  
  
3.  <span data-ttu-id="f995a-124">在全局程序集缓存中，将版本号更改为更新版本的版本号。</span><span class="sxs-lookup"><span data-stu-id="f995a-124">In the global assembly cache, change the version number to the newer version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f995a-125">策略使用的所有程序集都应添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="f995a-125">All assemblies used by policies should be added to the global assembly cache.</span></span>