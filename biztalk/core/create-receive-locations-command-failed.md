---
title: 创建接收位置命令失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f73ff211-af7f-40be-ad7e-7bde7bf75a2d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95b50fcb051b77b4d6516145a2c7fabfc52c2e7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976246"
---
# <a name="create-receive-locations-command-failed"></a><span data-ttu-id="ce934-102">创建接收位置命令失败</span><span class="sxs-lookup"><span data-stu-id="ce934-102">Create receive locations command failed</span></span>
## <a name="details"></a><span data-ttu-id="ce934-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ce934-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="ce934-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ce934-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="ce934-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ce934-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="ce934-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ce934-106">Event ID</span></span>     |                                         <span data-ttu-id="ce934-107">0</span><span class="sxs-lookup"><span data-stu-id="ce934-107">0</span></span>                                          |
|  <span data-ttu-id="ce934-108">事件源</span><span class="sxs-lookup"><span data-stu-id="ce934-108">Event Source</span></span>   |                                         <span data-ttu-id="ce934-109">0</span><span class="sxs-lookup"><span data-stu-id="ce934-109">0</span></span>                                          |
|    <span data-ttu-id="ce934-110">组件</span><span class="sxs-lookup"><span data-stu-id="ce934-110">Component</span></span>    |                                         <span data-ttu-id="ce934-111">0</span><span class="sxs-lookup"><span data-stu-id="ce934-111">0</span></span>                                          |
|  <span data-ttu-id="ce934-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="ce934-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="ce934-113">0</span><span class="sxs-lookup"><span data-stu-id="ce934-113">0</span></span>                                          |
|  <span data-ttu-id="ce934-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="ce934-114">Message Text</span></span>   |  <span data-ttu-id="ce934-115">创建接收位置命令失败： FileName ={0}自变量 ={1} ExitCode ={2}</span><span class="sxs-lookup"><span data-stu-id="ce934-115">Create receive locations command failed: FileName={0} Arguments={1} ExitCode={2}</span></span>  |
  
## <a name="explanation"></a><span data-ttu-id="ce934-116">解释</span><span class="sxs-lookup"><span data-stu-id="ce934-116">Explanation</span></span>  
 <span data-ttu-id="ce934-117">发布向导无法创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="ce934-117">The publishing wizard failed to create a receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce934-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="ce934-118">User Action</span></span>  
 <span data-ttu-id="ce934-119">若要解决此错误，请执行以下： 在 BizTalk 管理控制台中，请确保 Web.config 文件中 receiveLocationName 属性指定的接收位置 BizTalk WCF 发布向导生成存在并且已启动。</span><span class="sxs-lookup"><span data-stu-id="ce934-119">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="ce934-120">有关创建接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="ce934-120">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="ce934-121">通过独立 WCF 接收适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="ce934-121">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="ce934-122">如何配置 Wcf-basichttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="ce934-122">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="ce934-123">如何配置 Wcf-wshttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="ce934-123">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="ce934-124">如何配置 Wcf-customisolated 接收位置</span><span class="sxs-lookup"><span data-stu-id="ce934-124">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="ce934-125">演练：通过 WCF-BasicHttp 适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="ce934-125">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)