---
title: "无法获取绑定类型绑定扩展 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a7cfc81-7439-48f9-8cac-42b2419ecd9d
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79b649f69b7503f345f212aa5f014ce7b256148d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="unable-to-get-binding-type-for-binding-extension"></a><span data-ttu-id="2565a-102">无法获取绑定扩展的绑定类型</span><span class="sxs-lookup"><span data-stu-id="2565a-102">Unable to get binding type for binding extension</span></span>
## <a name="details"></a><span data-ttu-id="2565a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2565a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2565a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2565a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2565a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="2565a-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="2565a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2565a-106">Event ID</span></span>|<span data-ttu-id="2565a-107">0</span><span class="sxs-lookup"><span data-stu-id="2565a-107">0</span></span>|  
|<span data-ttu-id="2565a-108">事件源</span><span class="sxs-lookup"><span data-stu-id="2565a-108">Event Source</span></span>|<span data-ttu-id="2565a-109">0</span><span class="sxs-lookup"><span data-stu-id="2565a-109">0</span></span>|  
|<span data-ttu-id="2565a-110">组件</span><span class="sxs-lookup"><span data-stu-id="2565a-110">Component</span></span>|<span data-ttu-id="2565a-111">0</span><span class="sxs-lookup"><span data-stu-id="2565a-111">0</span></span>|  
|<span data-ttu-id="2565a-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="2565a-112">Symbolic Name</span></span>|<span data-ttu-id="2565a-113">0</span><span class="sxs-lookup"><span data-stu-id="2565a-113">0</span></span>|  
|<span data-ttu-id="2565a-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="2565a-114">Message Text</span></span>|<span data-ttu-id="2565a-115">无法获取绑定类型绑定扩展"{0}"。</span><span class="sxs-lookup"><span data-stu-id="2565a-115">Unable to get binding type for binding extension "{0}".</span></span> <span data-ttu-id="2565a-116">如果 machine.config 已更新你的应用程序打开时，重新启动你的应用程序，以拾取更改。</span><span class="sxs-lookup"><span data-stu-id="2565a-116">If machine.config was updated while your application was open, restart your application to pick up changes.</span></span> <span data-ttu-id="2565a-117">验证 machine.config 中已注册绑定扩展</span><span class="sxs-lookup"><span data-stu-id="2565a-117">Verify the binding extension is registered in machine.config</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2565a-118">解释</span><span class="sxs-lookup"><span data-stu-id="2565a-118">Explanation</span></span>  
 <span data-ttu-id="2565a-119">WCF 自定义或 WCF CustomIsolated 传输的自定义绑定扩展是未正确配置。</span><span class="sxs-lookup"><span data-stu-id="2565a-119">A custom binding extension for a WCF-Custom or a WCF-CustomIsolated transport was not configured properly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2565a-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="2565a-120">User Action</span></span>  
 <span data-ttu-id="2565a-121">要解决此错误，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="2565a-121">To resolve this error do one or more of the following:</span></span>  
  
-   <span data-ttu-id="2565a-122">确保**machine.config 文件**中**%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config**具有\< **bindingExtensions** \>正确配置的元素。</span><span class="sxs-lookup"><span data-stu-id="2565a-122">Ensure the **machine.config file** in **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config** has the \<**bindingExtensions**\> element configured properly.</span></span>  
  
-   <span data-ttu-id="2565a-123">在 Windows 资源管理器，转到**%WinDir%\Assembly**，并确保正确安装的程序集实现的自定义绑定扩展。</span><span class="sxs-lookup"><span data-stu-id="2565a-123">In Windows Explorer, go to **%WinDir%\Assembly**, and make sure the assemblies implementing the custom binding extension are installed properly.</span></span>  
  
-   <span data-ttu-id="2565a-124">对于 WCF-Custom 适配器，在 BizTalk 管理控制台中，重新启动运行 WCF 传输的主机实例。</span><span class="sxs-lookup"><span data-stu-id="2565a-124">For the WCF-Custom adapter, in the BizTalk Administration console, restart the host instance running the WCF transport.</span></span>  
  
-   <span data-ttu-id="2565a-125">对于 WCF-CustomIsolated 适配器，在 IIS 管理控制台中，重新启动托管 WCF 传输的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="2565a-125">For the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool hosting the WCF transport.</span></span>  
  
-   <span data-ttu-id="2565a-126">打开并关闭 BizTalk 管理控制台（如果已打开）</span><span class="sxs-lookup"><span data-stu-id="2565a-126">Open and close the BizTalk Administration console if it was opened</span></span>  
  
 <span data-ttu-id="2565a-127">有关详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="2565a-127">For further information, see the following resource:</span></span>  
  
-   [<span data-ttu-id="2565a-128">如何启用与 WCF 适配器 WCF 扩展点</span><span class="sxs-lookup"><span data-stu-id="2565a-128">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)