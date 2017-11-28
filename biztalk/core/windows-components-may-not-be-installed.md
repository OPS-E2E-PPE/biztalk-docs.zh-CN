---
title: "可能未安装 Windows 组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc78ac0a-ee21-4633-afb3-1357efd29903
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506f9c310a75c9f65564e4feb047157731bafa66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="windows-components-may-not-be-installed"></a><span data-ttu-id="431eb-102">可能未安装 Windows 组件</span><span class="sxs-lookup"><span data-stu-id="431eb-102">Windows components may not be installed</span></span>
## <a name="details"></a><span data-ttu-id="431eb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="431eb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="431eb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="431eb-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="431eb-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="431eb-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="431eb-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="431eb-106">Event ID</span></span>|<span data-ttu-id="431eb-107">0</span><span class="sxs-lookup"><span data-stu-id="431eb-107">0</span></span>|  
|<span data-ttu-id="431eb-108">事件源</span><span class="sxs-lookup"><span data-stu-id="431eb-108">Event Source</span></span>|<span data-ttu-id="431eb-109">0</span><span class="sxs-lookup"><span data-stu-id="431eb-109">0</span></span>|  
|<span data-ttu-id="431eb-110">组件</span><span class="sxs-lookup"><span data-stu-id="431eb-110">Component</span></span>|<span data-ttu-id="431eb-111">0</span><span class="sxs-lookup"><span data-stu-id="431eb-111">0</span></span>|  
|<span data-ttu-id="431eb-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="431eb-112">Symbolic Name</span></span>|<span data-ttu-id="431eb-113">0</span><span class="sxs-lookup"><span data-stu-id="431eb-113">0</span></span>|  
|<span data-ttu-id="431eb-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="431eb-114">Message Text</span></span>|<span data-ttu-id="431eb-115">以下 Windows 组件可能未安装： 应用程序服务器-&gt; Internet 信息服务 (IIS)-&gt;公共文件。</span><span class="sxs-lookup"><span data-stu-id="431eb-115">The following Windows component may not be installed: Application Server -&gt; Internet Information Services (IIS) -&gt; Common Files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="431eb-116">解释</span><span class="sxs-lookup"><span data-stu-id="431eb-116">Explanation</span></span>  
 <span data-ttu-id="431eb-117">尝试发布时如果在本地计算机上未安装 Internet 信息服务 (IIS)，则会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="431eb-117">This error will occur when publishing is attempted without Internet Information Services (IIS) installed on the local computer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="431eb-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="431eb-118">User Action</span></span>  
 <span data-ttu-id="431eb-119">对于 Windows 7 和 Windows Vista SP2，请在本地计算机上安装 IIS 并按以下方式配置 IIS：</span><span class="sxs-lookup"><span data-stu-id="431eb-119">For Windows 7 and Windows Vista SP2, Install IIS on the local machine and configure IIS as follows:</span></span>  
  
1.  <span data-ttu-id="431eb-120">单击**启动**，单击**控制面板**，然后单击**程序**。</span><span class="sxs-lookup"><span data-stu-id="431eb-120">Click **Start**, click **Control Panel**, and click **Programs**.</span></span>  
  
2.  <span data-ttu-id="431eb-121">单击**打开或关闭 Windows 功能**。</span><span class="sxs-lookup"><span data-stu-id="431eb-121">Click **Turn Windows features on and off**.</span></span> <span data-ttu-id="431eb-122">随即显示 Windows 功能向导。</span><span class="sxs-lookup"><span data-stu-id="431eb-122">The Windows Features Wizard appears.</span></span>  
  
3.  <span data-ttu-id="431eb-123">若要添加 IIS 组件，请选中该组件。</span><span class="sxs-lookup"><span data-stu-id="431eb-123">To add, check the IIS component.</span></span>  
  
 <span data-ttu-id="431eb-124">对于 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 和 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请在本地计算机上安装 IIS 并按以下方式配置 IIS：</span><span class="sxs-lookup"><span data-stu-id="431eb-124">For [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], Install IIS on the local machine and configure IIS as follows:</span></span>  
  
1.  <span data-ttu-id="431eb-125">单击**启动**，单击**控制面板**，然后单击**管理工具**。</span><span class="sxs-lookup"><span data-stu-id="431eb-125">Click **Start**, click **Control Panel**, and click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="431eb-126">单击**服务器管理器**。</span><span class="sxs-lookup"><span data-stu-id="431eb-126">Click **Server Manager**.</span></span> <span data-ttu-id="431eb-127">随即显示“服务器管理器”窗口。</span><span class="sxs-lookup"><span data-stu-id="431eb-127">The Server Manger window appears.</span></span>  
  
3.  <span data-ttu-id="431eb-128">单击**添加角色**，添加角色向导将显示。</span><span class="sxs-lookup"><span data-stu-id="431eb-128">Click **Add Roles**, Add Roles Wizard appears.</span></span>  
  
4.  <span data-ttu-id="431eb-129">若要添加，请选择 IIS 组件。</span><span class="sxs-lookup"><span data-stu-id="431eb-129">To add, Select IIS component.</span></span>