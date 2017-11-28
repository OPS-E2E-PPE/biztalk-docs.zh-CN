---
title: "环境变量如何指示部署状态 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: scripts, variables
ms.assetid: 022b782b-008d-41a7-9880-d1c4e5e4015e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 041e77eadb7c1b62e3441ee3b3c138203299f3a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-environment-variables-indicate-deployment-state"></a><span data-ttu-id="77a76-102">环境变量如何指示部署状态</span><span class="sxs-lookup"><span data-stu-id="77a76-102">How Environment Variables Indicate Deployment State</span></span>
<span data-ttu-id="77a76-103">调用预处理脚本或后处理脚本时，脚本通过检查环境变量 BTAD_ChangeRequestAction、BTAD_InstallMode 和 BTAD_HostClass，可确定其所运行的部署状态（安装、导入、删除、卸载、导入回滚或安装回滚）。</span><span class="sxs-lookup"><span data-stu-id="77a76-103">Once invoked, a pre- or post-processing script can determine in which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode and BTAD_HostClass.</span></span>  
  
 <span data-ttu-id="77a76-104">下表说明了用来指示不同部署状态的三个变量的组合。</span><span class="sxs-lookup"><span data-stu-id="77a76-104">The following table describes the combinations of the three variables that indicate the different deployment states.</span></span>  
  
|<span data-ttu-id="77a76-105">部署状态</span><span class="sxs-lookup"><span data-stu-id="77a76-105">Deployment State</span></span>|<span data-ttu-id="77a76-106">预期值</span><span class="sxs-lookup"><span data-stu-id="77a76-106">Expected Values</span></span>|  
|----------------------|---------------------|  
||<span data-ttu-id="77a76-107">BTAD_ChangeRequestAction</span><span class="sxs-lookup"><span data-stu-id="77a76-107">BTAD_ChangeRequestAction</span></span>|<span data-ttu-id="77a76-108">BTAD_InstallMode</span><span class="sxs-lookup"><span data-stu-id="77a76-108">BTAD_InstallMode</span></span>|<span data-ttu-id="77a76-109">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="77a76-109">BTAD_HostClass</span></span>|  
|<span data-ttu-id="77a76-110">导入（不带覆盖标志）</span><span class="sxs-lookup"><span data-stu-id="77a76-110">Import without overwrite flag</span></span>|<span data-ttu-id="77a76-111">创建</span><span class="sxs-lookup"><span data-stu-id="77a76-111">Create</span></span>|<span data-ttu-id="77a76-112">导入</span><span class="sxs-lookup"><span data-stu-id="77a76-112">Import</span></span>|<span data-ttu-id="77a76-113">ConfigurationDb</span><span class="sxs-lookup"><span data-stu-id="77a76-113">ConfigurationDb</span></span>|  
|<span data-ttu-id="77a76-114">导入（带覆盖标志）</span><span class="sxs-lookup"><span data-stu-id="77a76-114">Import with overwrite flag</span></span>|<span data-ttu-id="77a76-115">Update</span><span class="sxs-lookup"><span data-stu-id="77a76-115">Update</span></span>|<span data-ttu-id="77a76-116">导入</span><span class="sxs-lookup"><span data-stu-id="77a76-116">Import</span></span>|<span data-ttu-id="77a76-117">ConfigurationDb</span><span class="sxs-lookup"><span data-stu-id="77a76-117">ConfigurationDb</span></span>|  
|<span data-ttu-id="77a76-118">Install</span><span class="sxs-lookup"><span data-stu-id="77a76-118">Install</span></span>|<span data-ttu-id="77a76-119">Update</span><span class="sxs-lookup"><span data-stu-id="77a76-119">Update</span></span>|<span data-ttu-id="77a76-120">Install</span><span class="sxs-lookup"><span data-stu-id="77a76-120">Install</span></span>|<span data-ttu-id="77a76-121">BizTalkHostInstance</span><span class="sxs-lookup"><span data-stu-id="77a76-121">BizTalkHostInstance</span></span>|  
|<span data-ttu-id="77a76-122">Uninstall</span><span class="sxs-lookup"><span data-stu-id="77a76-122">Uninstall</span></span>|<span data-ttu-id="77a76-123">DELETE</span><span class="sxs-lookup"><span data-stu-id="77a76-123">Delete</span></span>|<span data-ttu-id="77a76-124">Uninstall</span><span class="sxs-lookup"><span data-stu-id="77a76-124">Uninstall</span></span>|<span data-ttu-id="77a76-125">BizTalkHostInstance</span><span class="sxs-lookup"><span data-stu-id="77a76-125">BizTalkHostInstance</span></span>|  
|<span data-ttu-id="77a76-126">导入回滚</span><span class="sxs-lookup"><span data-stu-id="77a76-126">Import rollback</span></span>|<span data-ttu-id="77a76-127">DELETE</span><span class="sxs-lookup"><span data-stu-id="77a76-127">Delete</span></span>|<span data-ttu-id="77a76-128">导入</span><span class="sxs-lookup"><span data-stu-id="77a76-128">Import</span></span>|<span data-ttu-id="77a76-129">ConfigurationDb</span><span class="sxs-lookup"><span data-stu-id="77a76-129">ConfigurationDb</span></span>|  
|<span data-ttu-id="77a76-130">安装回滚</span><span class="sxs-lookup"><span data-stu-id="77a76-130">Install rollback</span></span>|<span data-ttu-id="77a76-131">DELETE</span><span class="sxs-lookup"><span data-stu-id="77a76-131">Delete</span></span>|<span data-ttu-id="77a76-132">Install</span><span class="sxs-lookup"><span data-stu-id="77a76-132">Install</span></span>|<span data-ttu-id="77a76-133">BizTalkHostInstance</span><span class="sxs-lookup"><span data-stu-id="77a76-133">BizTalkHostInstance</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77a76-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77a76-134">See Also</span></span>  
 <span data-ttu-id="77a76-135">[前期和后期处理脚本用于自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="77a76-135">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 <span data-ttu-id="77a76-136">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span><span class="sxs-lookup"><span data-stu-id="77a76-136">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span></span>  
 <span data-ttu-id="77a76-137">[BTAD_InstallMode](../core/btad-installmode.md) </span><span class="sxs-lookup"><span data-stu-id="77a76-137">[BTAD_InstallMode](../core/btad-installmode.md) </span></span>  
 [<span data-ttu-id="77a76-138">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="77a76-138">BTAD_HostClass</span></span>](../core/btad-hostclass.md)