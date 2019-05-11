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
ms.openlocfilehash: 5fc27a85f36b83b3fd3c0bd782807fa4f5b73364
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387464"
---
# <a name="how-environment-variables-indicate-deployment-state"></a><span data-ttu-id="e2fe0-102">环境变量如何指示部署状态</span><span class="sxs-lookup"><span data-stu-id="e2fe0-102">How Environment Variables Indicate Deployment State</span></span>
<span data-ttu-id="e2fe0-103">在调用之后，预处理或后处理脚本可以确定的部署状态 （安装、 导入、 删除、 卸载、 导入回滚或安装回滚） 正在运行的检查环境变量 BTAD_ChangeRequestAction、 BTAD_InstallMode和 BTAD_HostClass。</span><span class="sxs-lookup"><span data-stu-id="e2fe0-103">Once invoked, a pre- or post-processing script can determine in which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode and BTAD_HostClass.</span></span>  

 <span data-ttu-id="e2fe0-104">下表介绍指示不同的部署状态的三个变量的组合。</span><span class="sxs-lookup"><span data-stu-id="e2fe0-104">The following table describes the combinations of the three variables that indicate the different deployment states.</span></span>  


|       <span data-ttu-id="e2fe0-105">部署状态</span><span class="sxs-lookup"><span data-stu-id="e2fe0-105">Deployment State</span></span>        |     <span data-ttu-id="e2fe0-106">预期值</span><span class="sxs-lookup"><span data-stu-id="e2fe0-106">Expected Values</span></span>      |
|-------------------------------|--------------------------|
|                               | <span data-ttu-id="e2fe0-107">BTAD_ChangeRequestAction</span><span class="sxs-lookup"><span data-stu-id="e2fe0-107">BTAD_ChangeRequestAction</span></span> |
| <span data-ttu-id="e2fe0-108">导入不带覆盖标志</span><span class="sxs-lookup"><span data-stu-id="e2fe0-108">Import without overwrite flag</span></span> |          <span data-ttu-id="e2fe0-109">创建</span><span class="sxs-lookup"><span data-stu-id="e2fe0-109">Create</span></span>          |
|  <span data-ttu-id="e2fe0-110">导入带覆盖标志</span><span class="sxs-lookup"><span data-stu-id="e2fe0-110">Import with overwrite flag</span></span>   |          <span data-ttu-id="e2fe0-111">Update</span><span class="sxs-lookup"><span data-stu-id="e2fe0-111">Update</span></span>          |
|            <span data-ttu-id="e2fe0-112">安装</span><span class="sxs-lookup"><span data-stu-id="e2fe0-112">Install</span></span>            |          <span data-ttu-id="e2fe0-113">Update</span><span class="sxs-lookup"><span data-stu-id="e2fe0-113">Update</span></span>          |
|           <span data-ttu-id="e2fe0-114">Uninstall</span><span class="sxs-lookup"><span data-stu-id="e2fe0-114">Uninstall</span></span>           |          <span data-ttu-id="e2fe0-115">DELETE</span><span class="sxs-lookup"><span data-stu-id="e2fe0-115">Delete</span></span>          |
|        <span data-ttu-id="e2fe0-116">导入回滚</span><span class="sxs-lookup"><span data-stu-id="e2fe0-116">Import rollback</span></span>        |          <span data-ttu-id="e2fe0-117">DELETE</span><span class="sxs-lookup"><span data-stu-id="e2fe0-117">Delete</span></span>          |
|       <span data-ttu-id="e2fe0-118">安装回滚</span><span class="sxs-lookup"><span data-stu-id="e2fe0-118">Install rollback</span></span>        |          <span data-ttu-id="e2fe0-119">DELETE</span><span class="sxs-lookup"><span data-stu-id="e2fe0-119">Delete</span></span>          |

## <a name="see-also"></a><span data-ttu-id="e2fe0-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2fe0-120">See Also</span></span>  
 <span data-ttu-id="e2fe0-121">[使用预处理和后处理脚本自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="e2fe0-121">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 <span data-ttu-id="e2fe0-122">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span><span class="sxs-lookup"><span data-stu-id="e2fe0-122">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span></span>  
 <span data-ttu-id="e2fe0-123">[BTAD_InstallMode](../core/btad-installmode.md) </span><span class="sxs-lookup"><span data-stu-id="e2fe0-123">[BTAD_InstallMode](../core/btad-installmode.md) </span></span>  
 [<span data-ttu-id="e2fe0-124">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="e2fe0-124">BTAD_HostClass</span></span>](../core/btad-hostclass.md)