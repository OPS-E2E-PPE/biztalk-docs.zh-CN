---
title: 找不到主机端口上的 web 服务器 |Microsoft Docs
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
ms.openlocfilehash: 62f9260f477669debf709ba592568a15fbaf7194
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987142"
---
# <a name="web-server-on-host-port-not-found"></a><span data-ttu-id="7ae4e-102">主机端口上找不到 Web 服务器</span><span class="sxs-lookup"><span data-stu-id="7ae4e-102">Web server on host port not found</span></span>
## <a name="details"></a><span data-ttu-id="7ae4e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7ae4e-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="7ae4e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7ae4e-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="7ae4e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7ae4e-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="7ae4e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7ae4e-106">Event ID</span></span>     |                                         <span data-ttu-id="7ae4e-107">0</span><span class="sxs-lookup"><span data-stu-id="7ae4e-107">0</span></span>                                          |
|  <span data-ttu-id="7ae4e-108">事件源</span><span class="sxs-lookup"><span data-stu-id="7ae4e-108">Event Source</span></span>   |                                         <span data-ttu-id="7ae4e-109">0</span><span class="sxs-lookup"><span data-stu-id="7ae4e-109">0</span></span>                                          |
|    <span data-ttu-id="7ae4e-110">组件</span><span class="sxs-lookup"><span data-stu-id="7ae4e-110">Component</span></span>    |                                         <span data-ttu-id="7ae4e-111">0</span><span class="sxs-lookup"><span data-stu-id="7ae4e-111">0</span></span>                                          |
|  <span data-ttu-id="7ae4e-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="7ae4e-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="7ae4e-113">0</span><span class="sxs-lookup"><span data-stu-id="7ae4e-113">0</span></span>                                          |
|  <span data-ttu-id="7ae4e-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="7ae4e-114">Message Text</span></span>   |                    <span data-ttu-id="7ae4e-115">主机上的 web 服务器"{0}"端口{1}找不到</span><span class="sxs-lookup"><span data-stu-id="7ae4e-115">Web server on host "{0}" port {1} not found</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="7ae4e-116">解释</span><span class="sxs-lookup"><span data-stu-id="7ae4e-116">Explanation</span></span>  
 <span data-ttu-id="7ae4e-117">此错误表示“万维网 (WWW) 服务”未运行。</span><span class="sxs-lookup"><span data-stu-id="7ae4e-117">This error indicates the World Wide Web (WWW) service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7ae4e-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="7ae4e-118">User Action</span></span>  
 <span data-ttu-id="7ae4e-119">使用以下过程启动“万维网服务”。</span><span class="sxs-lookup"><span data-stu-id="7ae4e-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="7ae4e-120">启动“万维网服务”的步骤</span><span class="sxs-lookup"><span data-stu-id="7ae4e-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="7ae4e-121">单击**启动**，单击**控制面板**，双击**管理工具**，然后双击**服务。**</span><span class="sxs-lookup"><span data-stu-id="7ae4e-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services.**</span></span>  
  
2.  <span data-ttu-id="7ae4e-122">在名称列中找到**World Wide Web Publishing**。</span><span class="sxs-lookup"><span data-stu-id="7ae4e-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="7ae4e-123">确保状态为**已启动**。</span><span class="sxs-lookup"><span data-stu-id="7ae4e-123">Ensure that the status is **Started**.</span></span>  
  
3.  <span data-ttu-id="7ae4e-124">返回到**管理工具**窗口。</span><span class="sxs-lookup"><span data-stu-id="7ae4e-124">Return to the **Administrative Tools** window.</span></span> <span data-ttu-id="7ae4e-125">双击**Internet 信息服务**。</span><span class="sxs-lookup"><span data-stu-id="7ae4e-125">Double-click **Internet Information Services**.</span></span>  
  
4.  <span data-ttu-id="7ae4e-126">展开文件夹区域，然后找到 Web 站点。</span><span class="sxs-lookup"><span data-stu-id="7ae4e-126">Expand the folder area and locate the web site.</span></span>  
  
5.  <span data-ttu-id="7ae4e-127">确保状态为**已启动**。</span><span class="sxs-lookup"><span data-stu-id="7ae4e-127">Ensure that the status is **Started**.</span></span>