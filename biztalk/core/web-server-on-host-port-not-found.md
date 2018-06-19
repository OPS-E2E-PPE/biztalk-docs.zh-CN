---
title: 找不到的主机端口上的 web 服务器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c253fd5e-b815-4697-a06d-67af65a35589
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dce09ce00a169ad14bbc8ae2ab28fe70c039c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288557"
---
# <a name="web-server-on-host-port-not-found"></a><span data-ttu-id="514c0-102">主机端口上找不到 Web 服务器</span><span class="sxs-lookup"><span data-stu-id="514c0-102">Web server on host port not found</span></span>
## <a name="details"></a><span data-ttu-id="514c0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="514c0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="514c0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="514c0-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="514c0-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="514c0-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="514c0-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="514c0-106">Event ID</span></span>|<span data-ttu-id="514c0-107">0</span><span class="sxs-lookup"><span data-stu-id="514c0-107">0</span></span>|  
|<span data-ttu-id="514c0-108">事件源</span><span class="sxs-lookup"><span data-stu-id="514c0-108">Event Source</span></span>|<span data-ttu-id="514c0-109">0</span><span class="sxs-lookup"><span data-stu-id="514c0-109">0</span></span>|  
|<span data-ttu-id="514c0-110">组件</span><span class="sxs-lookup"><span data-stu-id="514c0-110">Component</span></span>|<span data-ttu-id="514c0-111">0</span><span class="sxs-lookup"><span data-stu-id="514c0-111">0</span></span>|  
|<span data-ttu-id="514c0-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="514c0-112">Symbolic Name</span></span>|<span data-ttu-id="514c0-113">0</span><span class="sxs-lookup"><span data-stu-id="514c0-113">0</span></span>|  
|<span data-ttu-id="514c0-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="514c0-114">Message Text</span></span>|<span data-ttu-id="514c0-115">Web 服务器上找不到主机"{0}"端口 {1}</span><span class="sxs-lookup"><span data-stu-id="514c0-115">Web server on host "{0}" port {1} not found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="514c0-116">解释</span><span class="sxs-lookup"><span data-stu-id="514c0-116">Explanation</span></span>  
 <span data-ttu-id="514c0-117">此错误表示“万维网 (WWW) 服务”未运行。</span><span class="sxs-lookup"><span data-stu-id="514c0-117">This error indicates the World Wide Web (WWW) service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="514c0-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="514c0-118">User Action</span></span>  
 <span data-ttu-id="514c0-119">使用以下过程启动“万维网服务”。</span><span class="sxs-lookup"><span data-stu-id="514c0-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="514c0-120">启动“万维网服务”的步骤</span><span class="sxs-lookup"><span data-stu-id="514c0-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="514c0-121">单击**启动**，单击**控制面板**，双击**管理工具**，双击**服务。**</span><span class="sxs-lookup"><span data-stu-id="514c0-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services.**</span></span>  
  
2.  <span data-ttu-id="514c0-122">在名称列中，找到**World Wide Web Publishing**。</span><span class="sxs-lookup"><span data-stu-id="514c0-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="514c0-123">确保状态是**已启动**。</span><span class="sxs-lookup"><span data-stu-id="514c0-123">Ensure that the status is **Started**.</span></span>  
  
3.  <span data-ttu-id="514c0-124">返回到**管理工具**窗口。</span><span class="sxs-lookup"><span data-stu-id="514c0-124">Return to the **Administrative Tools** window.</span></span> <span data-ttu-id="514c0-125">双击**Internet Information Services**。</span><span class="sxs-lookup"><span data-stu-id="514c0-125">Double-click **Internet Information Services**.</span></span>  
  
4.  <span data-ttu-id="514c0-126">展开文件夹区域，然后找到 Web 站点。</span><span class="sxs-lookup"><span data-stu-id="514c0-126">Expand the folder area and locate the web site.</span></span>  
  
5.  <span data-ttu-id="514c0-127">确保状态是**已启动**。</span><span class="sxs-lookup"><span data-stu-id="514c0-127">Ensure that the status is **Started**.</span></span>