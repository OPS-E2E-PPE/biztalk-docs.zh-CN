---
title: 可能未安装 Windows 组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc78ac0a-ee21-4633-afb3-1357efd29903
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d61ded5b2ddb077ff0851c20d673fad4f9de9d26
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975502"
---
# <a name="windows-components-may-not-be-installed"></a><span data-ttu-id="e27b6-102">可能未安装 Windows 组件</span><span class="sxs-lookup"><span data-stu-id="e27b6-102">Windows components may not be installed</span></span>
## <a name="details"></a><span data-ttu-id="e27b6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e27b6-103">Details</span></span>  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e27b6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e27b6-104">Product Name</span></span>   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| <span data-ttu-id="e27b6-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e27b6-105">Product Version</span></span> |                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    <span data-ttu-id="e27b6-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e27b6-106">Event ID</span></span>     |                                                                   <span data-ttu-id="e27b6-107">0</span><span class="sxs-lookup"><span data-stu-id="e27b6-107">0</span></span>                                                                    |
|  <span data-ttu-id="e27b6-108">事件源</span><span class="sxs-lookup"><span data-stu-id="e27b6-108">Event Source</span></span>   |                                                                   <span data-ttu-id="e27b6-109">0</span><span class="sxs-lookup"><span data-stu-id="e27b6-109">0</span></span>                                                                    |
|    <span data-ttu-id="e27b6-110">组件</span><span class="sxs-lookup"><span data-stu-id="e27b6-110">Component</span></span>    |                                                                   <span data-ttu-id="e27b6-111">0</span><span class="sxs-lookup"><span data-stu-id="e27b6-111">0</span></span>                                                                    |
|  <span data-ttu-id="e27b6-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="e27b6-112">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="e27b6-113">0</span><span class="sxs-lookup"><span data-stu-id="e27b6-113">0</span></span>                                                                    |
|  <span data-ttu-id="e27b6-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="e27b6-114">Message Text</span></span>   | <span data-ttu-id="e27b6-115">可能未安装以下 Windows 组件： 应用程序服务器-&gt; Internet 信息服务 (IIS)-&gt;公共文件。</span><span class="sxs-lookup"><span data-stu-id="e27b6-115">The following Windows component may not be installed: Application Server -&gt; Internet Information Services (IIS) -&gt; Common Files.</span></span> |

## <a name="explanation"></a><span data-ttu-id="e27b6-116">解释</span><span class="sxs-lookup"><span data-stu-id="e27b6-116">Explanation</span></span>  
 <span data-ttu-id="e27b6-117">尝试发布时如果在本地计算机上未安装 Internet 信息服务 (IIS)，则会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="e27b6-117">This error will occur when publishing is attempted without Internet Information Services (IIS) installed on the local computer.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e27b6-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="e27b6-118">User Action</span></span>  
 <span data-ttu-id="e27b6-119">对于 Windows 7 和 Windows Vista SP2，请在本地计算机上安装 IIS 并按以下方式配置 IIS：</span><span class="sxs-lookup"><span data-stu-id="e27b6-119">For Windows 7 and Windows Vista SP2, Install IIS on the local machine and configure IIS as follows:</span></span>  

1. <span data-ttu-id="e27b6-120">单击**启动**，单击**控制面板**，然后单击**程序**。</span><span class="sxs-lookup"><span data-stu-id="e27b6-120">Click **Start**, click **Control Panel**, and click **Programs**.</span></span>  

2. <span data-ttu-id="e27b6-121">单击**打开或关闭打开的 Windows 功能**。</span><span class="sxs-lookup"><span data-stu-id="e27b6-121">Click **Turn Windows features on and off**.</span></span> <span data-ttu-id="e27b6-122">随即显示 Windows 功能向导。</span><span class="sxs-lookup"><span data-stu-id="e27b6-122">The Windows Features Wizard appears.</span></span>  

3. <span data-ttu-id="e27b6-123">若要添加 IIS 组件，请选中该组件。</span><span class="sxs-lookup"><span data-stu-id="e27b6-123">To add, check the IIS component.</span></span>  

   <span data-ttu-id="e27b6-124">对于 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 和 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请在本地计算机上安装 IIS 并按以下方式配置 IIS：</span><span class="sxs-lookup"><span data-stu-id="e27b6-124">For [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], Install IIS on the local machine and configure IIS as follows:</span></span>  

4. <span data-ttu-id="e27b6-125">单击**启动**，单击**控制面板**，然后单击**管理工具**。</span><span class="sxs-lookup"><span data-stu-id="e27b6-125">Click **Start**, click **Control Panel**, and click **Administrative Tools**.</span></span>  

5. <span data-ttu-id="e27b6-126">单击**服务器管理器**。</span><span class="sxs-lookup"><span data-stu-id="e27b6-126">Click **Server Manager**.</span></span> <span data-ttu-id="e27b6-127">随即显示“服务器管理器”窗口。</span><span class="sxs-lookup"><span data-stu-id="e27b6-127">The Server Manger window appears.</span></span>  

6. <span data-ttu-id="e27b6-128">单击**添加角色**，显示添加角色向导。</span><span class="sxs-lookup"><span data-stu-id="e27b6-128">Click **Add Roles**, Add Roles Wizard appears.</span></span>  

7. <span data-ttu-id="e27b6-129">若要添加，请选择 IIS 组件。</span><span class="sxs-lookup"><span data-stu-id="e27b6-129">To add, Select IIS component.</span></span>
