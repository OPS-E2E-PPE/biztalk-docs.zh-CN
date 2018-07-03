---
title: 不可用的主机上的 World Wide Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b14eaae-2158-4aef-9561-610d033998be
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6c3623a7f39f773f720fa33cd64a7e93c3668d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991102"
---
# <a name="world-wide-web-service-on-host-not-available"></a><span data-ttu-id="67aae-102">主机上的 World Wide Web 服务不可用</span><span class="sxs-lookup"><span data-stu-id="67aae-102">World Wide Web service on host not available</span></span>
## <a name="details"></a><span data-ttu-id="67aae-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="67aae-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="67aae-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="67aae-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="67aae-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="67aae-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="67aae-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="67aae-106">Event ID</span></span>     |                                         <span data-ttu-id="67aae-107">0</span><span class="sxs-lookup"><span data-stu-id="67aae-107">0</span></span>                                          |
|  <span data-ttu-id="67aae-108">事件源</span><span class="sxs-lookup"><span data-stu-id="67aae-108">Event Source</span></span>   |                                         <span data-ttu-id="67aae-109">0</span><span class="sxs-lookup"><span data-stu-id="67aae-109">0</span></span>                                          |
|    <span data-ttu-id="67aae-110">组件</span><span class="sxs-lookup"><span data-stu-id="67aae-110">Component</span></span>    |                                         <span data-ttu-id="67aae-111">0</span><span class="sxs-lookup"><span data-stu-id="67aae-111">0</span></span>                                          |
|  <span data-ttu-id="67aae-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="67aae-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="67aae-113">0</span><span class="sxs-lookup"><span data-stu-id="67aae-113">0</span></span>                                          |
|  <span data-ttu-id="67aae-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="67aae-114">Message Text</span></span>   |             <span data-ttu-id="67aae-115">World Wide Web 服务 (W3SVC) 主机上的"{0}"不可用</span><span class="sxs-lookup"><span data-stu-id="67aae-115">World Wide Web service (W3SVC) on host "{0}" not available</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="67aae-116">解释</span><span class="sxs-lookup"><span data-stu-id="67aae-116">Explanation</span></span>  
 <span data-ttu-id="67aae-117">此错误表示“万维网服务”未运行。</span><span class="sxs-lookup"><span data-stu-id="67aae-117">This error indicates the World Wide Web service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67aae-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="67aae-118">User Action</span></span>  
 <span data-ttu-id="67aae-119">使用以下过程启动“万维网服务”。</span><span class="sxs-lookup"><span data-stu-id="67aae-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="67aae-120">启动“万维网服务”的步骤</span><span class="sxs-lookup"><span data-stu-id="67aae-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="67aae-121">单击**启动**，单击**控制面板**，双击**管理工具**，然后双击**服务**。</span><span class="sxs-lookup"><span data-stu-id="67aae-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services**.</span></span>  
  
2.  <span data-ttu-id="67aae-122">在名称列中找到**World Wide Web Publishing**。</span><span class="sxs-lookup"><span data-stu-id="67aae-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="67aae-123">确保状态为**已启动**。</span><span class="sxs-lookup"><span data-stu-id="67aae-123">Ensure that the status is **Started**.</span></span>