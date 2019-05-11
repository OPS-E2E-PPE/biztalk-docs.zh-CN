---
title: 如何维护策略版本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, publishing
- publishing policies
- updating, policies
- versioning, policies
- policies, versioning
- policies, updating
ms.assetid: 6e35b2bd-1ecd-45ea-aff3-4ad2437568a4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78750e9db681ad12b1a134ef27360a57a3163bc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336831"
---
# <a name="how-to-maintain-policy-versions"></a><span data-ttu-id="ff242-102">如何维护策略版本</span><span class="sxs-lookup"><span data-stu-id="ff242-102">How to Maintain Policy Versions</span></span>
<span data-ttu-id="ff242-103">将规则添加到你的策略的版本后，可以将该版本保存到规则存储中供进一步开发，也可以发布它以创建明确定义的、 不可变的一组可部署在基于规则的应用程序中使用的规则。</span><span class="sxs-lookup"><span data-stu-id="ff242-103">After you add rules to a version of your policy, you can save the version to the rule store for further development, or you can publish it to create a well-defined, immutable set of rules that can be deployed for use in a rule-based application.</span></span>  
  
 <span data-ttu-id="ff242-104">本主题包含以下任务的过程：</span><span class="sxs-lookup"><span data-stu-id="ff242-104">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="ff242-105">若要创建新的空策略版本</span><span class="sxs-lookup"><span data-stu-id="ff242-105">To create an empty new version of a policy</span></span>  
  
-   <span data-ttu-id="ff242-106">若要保存策略版本</span><span class="sxs-lookup"><span data-stu-id="ff242-106">To save a policy version</span></span>  
  
-   <span data-ttu-id="ff242-107">若要发布策略版本</span><span class="sxs-lookup"><span data-stu-id="ff242-107">To publish a policy version</span></span>  
  
-   <span data-ttu-id="ff242-108">若要创建策略的更新的版本</span><span class="sxs-lookup"><span data-stu-id="ff242-108">To create an updated version of a policy</span></span>  
  
-   <span data-ttu-id="ff242-109">更新策略以使用更新的程序集</span><span class="sxs-lookup"><span data-stu-id="ff242-109">To update a policy to use an updated assembly</span></span>  
  
### <a name="to-create-an-empty-new-version-of-a-policy"></a><span data-ttu-id="ff242-110">若要创建新的空策略版本</span><span class="sxs-lookup"><span data-stu-id="ff242-110">To create an empty new version of a policy</span></span>  
  
-   <span data-ttu-id="ff242-111">右键单击策略文件夹，然后依次**添加新版本**。</span><span class="sxs-lookup"><span data-stu-id="ff242-111">Right-click the policy folder, and then click **Add New Version**.</span></span>  
  
### <a name="to-save-a-policy-version"></a><span data-ttu-id="ff242-112">若要保存策略版本</span><span class="sxs-lookup"><span data-stu-id="ff242-112">To save a policy version</span></span>  
  
-   <span data-ttu-id="ff242-113">右键单击策略版本中，然后依次**保存**。</span><span class="sxs-lookup"><span data-stu-id="ff242-113">Right-click the policy version, and then click **Save**.</span></span>  
  
### <a name="to-publish-a-policy-version"></a><span data-ttu-id="ff242-114">若要发布策略版本</span><span class="sxs-lookup"><span data-stu-id="ff242-114">To publish a policy version</span></span>  
  
-   <span data-ttu-id="ff242-115">右键单击策略版本中，然后依次**发布**。</span><span class="sxs-lookup"><span data-stu-id="ff242-115">Right-click the policy version, and then click **Publish**.</span></span>  
  
### <a name="to-create-an-updated-version-of-a-policy"></a><span data-ttu-id="ff242-116">若要创建策略的更新的版本</span><span class="sxs-lookup"><span data-stu-id="ff242-116">To create an updated version of a policy</span></span>  
  
1.  <span data-ttu-id="ff242-117">右键单击现有的策略版本，然后依次**复制**。</span><span class="sxs-lookup"><span data-stu-id="ff242-117">Right-click an existing policy version, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="ff242-118">右键单击策略文件夹，然后依次**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="ff242-118">Right-click the policy folder, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="ff242-119">创建一个新版本，具有与复制的版本相同的元素。</span><span class="sxs-lookup"><span data-stu-id="ff242-119">A new version is created, with the same elements as the copied version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff242-120">如果您的策略使用.NET 程序集，并且更新的程序集，应将策略绑定到程序集的较新版本。</span><span class="sxs-lookup"><span data-stu-id="ff242-120">If your policy uses a .NET assembly, and the assembly is updated, you should bind your policy to the newer version of the assembly.</span></span>  
  
### <a name="to-update-a-policy-to-use-an-updated-assembly"></a><span data-ttu-id="ff242-121">更新策略以使用更新的程序集</span><span class="sxs-lookup"><span data-stu-id="ff242-121">To update a policy to use an updated assembly</span></span>  
  
1.  <span data-ttu-id="ff242-122">单击**启动**，依次指向**管理工具**，指向 **.NET Framework 配置**，然后单击**配置程序集**.</span><span class="sxs-lookup"><span data-stu-id="ff242-122">Click **Start**, point to **Administrative Tools**, point to **.NET Framework Configuration**, and then click **Configured Assemblies**.</span></span>  
  
2.  <span data-ttu-id="ff242-123">转到属性目标程序集并单击**绑定策略**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ff242-123">Go to properties for the target assembly and click the **Binding Policy** tab.</span></span>  
  
3.  <span data-ttu-id="ff242-124">在全局程序集缓存中，更改到较新版本的版本号。</span><span class="sxs-lookup"><span data-stu-id="ff242-124">In the global assembly cache, change the version number to the newer version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff242-125">使用策略的所有程序集应添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="ff242-125">All assemblies used by policies should be added to the global assembly cache.</span></span>