---
title: 无法获取绑定扩展的绑定类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7cfc81-7439-48f9-8cac-42b2419ecd9d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdf0e0fd1ebf88c9231d70e9102d76fa67157cb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006230"
---
# <a name="unable-to-get-binding-type-for-binding-extension"></a><span data-ttu-id="89e03-102">无法获取绑定扩展的绑定类型</span><span class="sxs-lookup"><span data-stu-id="89e03-102">Unable to get binding type for binding extension</span></span>
## <a name="details"></a><span data-ttu-id="89e03-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="89e03-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="89e03-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="89e03-104">Product Name</span></span>   |                                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                        |
| <span data-ttu-id="89e03-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="89e03-105">Product Version</span></span> |                                                                                    [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                    |
|    <span data-ttu-id="89e03-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="89e03-106">Event ID</span></span>     |                                                                                                                <span data-ttu-id="89e03-107">0</span><span class="sxs-lookup"><span data-stu-id="89e03-107">0</span></span>                                                                                                                 |
|  <span data-ttu-id="89e03-108">事件源</span><span class="sxs-lookup"><span data-stu-id="89e03-108">Event Source</span></span>   |                                                                                                                <span data-ttu-id="89e03-109">0</span><span class="sxs-lookup"><span data-stu-id="89e03-109">0</span></span>                                                                                                                 |
|    <span data-ttu-id="89e03-110">组件</span><span class="sxs-lookup"><span data-stu-id="89e03-110">Component</span></span>    |                                                                                                                <span data-ttu-id="89e03-111">0</span><span class="sxs-lookup"><span data-stu-id="89e03-111">0</span></span>                                                                                                                 |
|  <span data-ttu-id="89e03-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="89e03-112">Symbolic Name</span></span>  |                                                                                                                <span data-ttu-id="89e03-113">0</span><span class="sxs-lookup"><span data-stu-id="89e03-113">0</span></span>                                                                                                                 |
|  <span data-ttu-id="89e03-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="89e03-114">Message Text</span></span>   | <span data-ttu-id="89e03-115">无法获取绑定扩展的绑定类型"{0}"。</span><span class="sxs-lookup"><span data-stu-id="89e03-115">Unable to get binding type for binding extension "{0}".</span></span> <span data-ttu-id="89e03-116">如果你的应用程序打开时，已更新 machine.config，重新启动应用程序要选取更改。</span><span class="sxs-lookup"><span data-stu-id="89e03-116">If machine.config was updated while your application was open, restart your application to pick up changes.</span></span> <span data-ttu-id="89e03-117">验证 machine.config 中已注册绑定扩展</span><span class="sxs-lookup"><span data-stu-id="89e03-117">Verify the binding extension is registered in machine.config</span></span> |

## <a name="explanation"></a><span data-ttu-id="89e03-118">解释</span><span class="sxs-lookup"><span data-stu-id="89e03-118">Explanation</span></span>  
 <span data-ttu-id="89e03-119">适用于 Wcf-custom 或 Wcf-customisolated 传输的自定义绑定扩展是未正确配置。</span><span class="sxs-lookup"><span data-stu-id="89e03-119">A custom binding extension for a WCF-Custom or a WCF-CustomIsolated transport was not configured properly.</span></span>  

## <a name="user-action"></a><span data-ttu-id="89e03-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="89e03-120">User Action</span></span>  
 <span data-ttu-id="89e03-121">要解决此错误，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="89e03-121">To resolve this error do one or more of the following:</span></span>  

- <span data-ttu-id="89e03-122">请确保**machine.config 文件**中 **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config**具有\< **bindingExtensions** \>正确配置的元素。</span><span class="sxs-lookup"><span data-stu-id="89e03-122">Ensure the **machine.config file** in **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config** has the \<**bindingExtensions**\> element configured properly.</span></span>  

- <span data-ttu-id="89e03-123">在 Windows 资源管理器，转到 **%WinDir%\Assembly**，并确保实现自定义绑定扩展的程序集已正确安装。</span><span class="sxs-lookup"><span data-stu-id="89e03-123">In Windows Explorer, go to **%WinDir%\Assembly**, and make sure the assemblies implementing the custom binding extension are installed properly.</span></span>  

- <span data-ttu-id="89e03-124">对于 WCF-Custom 适配器，在 BizTalk 管理控制台中，重新启动运行 WCF 传输的主机实例。</span><span class="sxs-lookup"><span data-stu-id="89e03-124">For the WCF-Custom adapter, in the BizTalk Administration console, restart the host instance running the WCF transport.</span></span>  

- <span data-ttu-id="89e03-125">对于 WCF-CustomIsolated 适配器，在 IIS 管理控制台中，重新启动托管 WCF 传输的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="89e03-125">For the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool hosting the WCF transport.</span></span>  

- <span data-ttu-id="89e03-126">打开并关闭 BizTalk 管理控制台（如果已打开）</span><span class="sxs-lookup"><span data-stu-id="89e03-126">Open and close the BizTalk Administration console if it was opened</span></span>  

  <span data-ttu-id="89e03-127">有关详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="89e03-127">For further information, see the following resource:</span></span>  

- [<span data-ttu-id="89e03-128">如何启用 WCF 适配器的 WCF 扩展点</span><span class="sxs-lookup"><span data-stu-id="89e03-128">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)
