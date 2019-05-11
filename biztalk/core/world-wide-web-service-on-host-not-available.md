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
ms.openlocfilehash: 1ad2616191dc146774c9b3d90664322992bb753d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302333"
---
# <a name="world-wide-web-service-on-host-not-available"></a><span data-ttu-id="4cdd7-102">主机上的 World Wide Web 服务不可用</span><span class="sxs-lookup"><span data-stu-id="4cdd7-102">World Wide Web service on host not available</span></span>
## <a name="details"></a><span data-ttu-id="4cdd7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4cdd7-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="4cdd7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4cdd7-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="4cdd7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="4cdd7-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="4cdd7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4cdd7-106">Event ID</span></span>     |                                         <span data-ttu-id="4cdd7-107">0</span><span class="sxs-lookup"><span data-stu-id="4cdd7-107">0</span></span>                                          |
|  <span data-ttu-id="4cdd7-108">事件源</span><span class="sxs-lookup"><span data-stu-id="4cdd7-108">Event Source</span></span>   |                                         <span data-ttu-id="4cdd7-109">0</span><span class="sxs-lookup"><span data-stu-id="4cdd7-109">0</span></span>                                          |
|    <span data-ttu-id="4cdd7-110">组件</span><span class="sxs-lookup"><span data-stu-id="4cdd7-110">Component</span></span>    |                                         <span data-ttu-id="4cdd7-111">0</span><span class="sxs-lookup"><span data-stu-id="4cdd7-111">0</span></span>                                          |
|  <span data-ttu-id="4cdd7-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="4cdd7-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="4cdd7-113">0</span><span class="sxs-lookup"><span data-stu-id="4cdd7-113">0</span></span>                                          |
|  <span data-ttu-id="4cdd7-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="4cdd7-114">Message Text</span></span>   |             <span data-ttu-id="4cdd7-115">World Wide Web 服务 (W3SVC) 主机上的"{0}"不可用</span><span class="sxs-lookup"><span data-stu-id="4cdd7-115">World Wide Web service (W3SVC) on host "{0}" not available</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="4cdd7-116">解释</span><span class="sxs-lookup"><span data-stu-id="4cdd7-116">Explanation</span></span>  
 <span data-ttu-id="4cdd7-117">此错误表示未运行 World Wide Web 服务。</span><span class="sxs-lookup"><span data-stu-id="4cdd7-117">This error indicates the World Wide Web service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4cdd7-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="4cdd7-118">User Action</span></span>  
 <span data-ttu-id="4cdd7-119">使用以下过程启动 World Wide Web 服务。</span><span class="sxs-lookup"><span data-stu-id="4cdd7-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="4cdd7-120">若要启动 World Wide Web 服务</span><span class="sxs-lookup"><span data-stu-id="4cdd7-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="4cdd7-121">单击**启动**，单击**控制面板**，双击**管理工具**，然后双击**服务**。</span><span class="sxs-lookup"><span data-stu-id="4cdd7-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services**.</span></span>  
  
2.  <span data-ttu-id="4cdd7-122">在名称列中找到**World Wide Web Publishing**。</span><span class="sxs-lookup"><span data-stu-id="4cdd7-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="4cdd7-123">确保状态为**已启动**。</span><span class="sxs-lookup"><span data-stu-id="4cdd7-123">Ensure that the status is **Started**.</span></span>