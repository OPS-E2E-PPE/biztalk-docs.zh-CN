---
title: 环境变量如何指示部署状态 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, variables
ms.assetid: 022b782b-008d-41a7-9880-d1c4e5e4015e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d21baa6ef6e6d82fc179497b4993cf3af6fb1a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983982"
---
# <a name="how-environment-variables-indicate-deployment-state"></a><span data-ttu-id="82aa2-102">环境变量如何指示部署状态</span><span class="sxs-lookup"><span data-stu-id="82aa2-102">How Environment Variables Indicate Deployment State</span></span>
<span data-ttu-id="82aa2-103">调用预处理脚本或后处理脚本时，脚本通过检查环境变量 BTAD_ChangeRequestAction、BTAD_InstallMode 和 BTAD_HostClass，可确定其所运行的部署状态（安装、导入、删除、卸载、导入回滚或安装回滚）。</span><span class="sxs-lookup"><span data-stu-id="82aa2-103">Once invoked, a pre- or post-processing script can determine in which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode and BTAD_HostClass.</span></span>  

 <span data-ttu-id="82aa2-104">下表说明了用来指示不同部署状态的三个变量的组合。</span><span class="sxs-lookup"><span data-stu-id="82aa2-104">The following table describes the combinations of the three variables that indicate the different deployment states.</span></span>  


|       <span data-ttu-id="82aa2-105">部署状态</span><span class="sxs-lookup"><span data-stu-id="82aa2-105">Deployment State</span></span>        |     <span data-ttu-id="82aa2-106">预期值</span><span class="sxs-lookup"><span data-stu-id="82aa2-106">Expected Values</span></span>      |
|-------------------------------|--------------------------|
|                               | <span data-ttu-id="82aa2-107">BTAD_ChangeRequestAction</span><span class="sxs-lookup"><span data-stu-id="82aa2-107">BTAD_ChangeRequestAction</span></span> |
| <span data-ttu-id="82aa2-108">导入（不带覆盖标志）</span><span class="sxs-lookup"><span data-stu-id="82aa2-108">Import without overwrite flag</span></span> |          <span data-ttu-id="82aa2-109">创建</span><span class="sxs-lookup"><span data-stu-id="82aa2-109">Create</span></span>          |
|  <span data-ttu-id="82aa2-110">导入（带覆盖标志）</span><span class="sxs-lookup"><span data-stu-id="82aa2-110">Import with overwrite flag</span></span>   |          <span data-ttu-id="82aa2-111">Update</span><span class="sxs-lookup"><span data-stu-id="82aa2-111">Update</span></span>          |
|            <span data-ttu-id="82aa2-112">Install</span><span class="sxs-lookup"><span data-stu-id="82aa2-112">Install</span></span>            |          <span data-ttu-id="82aa2-113">Update</span><span class="sxs-lookup"><span data-stu-id="82aa2-113">Update</span></span>          |
|           <span data-ttu-id="82aa2-114">Uninstall</span><span class="sxs-lookup"><span data-stu-id="82aa2-114">Uninstall</span></span>           |          <span data-ttu-id="82aa2-115">DELETE</span><span class="sxs-lookup"><span data-stu-id="82aa2-115">Delete</span></span>          |
|        <span data-ttu-id="82aa2-116">导入回滚</span><span class="sxs-lookup"><span data-stu-id="82aa2-116">Import rollback</span></span>        |          <span data-ttu-id="82aa2-117">DELETE</span><span class="sxs-lookup"><span data-stu-id="82aa2-117">Delete</span></span>          |
|       <span data-ttu-id="82aa2-118">安装回滚</span><span class="sxs-lookup"><span data-stu-id="82aa2-118">Install rollback</span></span>        |          <span data-ttu-id="82aa2-119">DELETE</span><span class="sxs-lookup"><span data-stu-id="82aa2-119">Delete</span></span>          |

## <a name="see-also"></a><span data-ttu-id="82aa2-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="82aa2-120">See Also</span></span>  
 <span data-ttu-id="82aa2-121">[使用预处理和后处理脚本自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="82aa2-121">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 <span data-ttu-id="82aa2-122">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span><span class="sxs-lookup"><span data-stu-id="82aa2-122">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span></span>  
 <span data-ttu-id="82aa2-123">[BTAD_InstallMode](../core/btad-installmode.md) </span><span class="sxs-lookup"><span data-stu-id="82aa2-123">[BTAD_InstallMode](../core/btad-installmode.md) </span></span>  
 [<span data-ttu-id="82aa2-124">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="82aa2-124">BTAD_HostClass</span></span>](../core/btad-hostclass.md)