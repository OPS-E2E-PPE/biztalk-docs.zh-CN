---
title: 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, properties
- receive locations, about receive locations
- receive locations
- receive locations, receive location types
ms.assetid: be5f7e5d-b63f-42f6-985e-895ba3912d34
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fefe11eb38575a7225b6cc88c3977df6bab685b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398213"
---
# <a name="receive-locations"></a><span data-ttu-id="0cc5a-102">接收位置</span><span class="sxs-lookup"><span data-stu-id="0cc5a-102">Receive Locations</span></span>
<span data-ttu-id="0cc5a-103">创建接收位置涉及到指定的地址的入站的消息到达时以及在该地址接收对消息进行处理的消息传送管道。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-103">Creating a receive location involves specifying an address at which inbound messages arrive and the messaging pipeline that processes the message received at that address.</span></span> <span data-ttu-id="0cc5a-104">只有管理员才能创建和启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-104">Only administrators can create and enable receive locations.</span></span>  
  
 <span data-ttu-id="0cc5a-105">管理员使用 BizTalk 管理控制台来创建接收位置、 接收位置绑定到业务流程，启用接收位置、 禁用接收位置，和设置全局属性的接收位置。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-105">An administrator uses the BizTalk Administration Console to create receive locations, bind receive locations to orchestrations, enable receive locations, disable receive locations, and set global properties for receive locations.</span></span>  
  
 <span data-ttu-id="0cc5a-106">管理员 （使用 BizTalk 管理控制台） 遵循以下步骤创建接收位置：</span><span class="sxs-lookup"><span data-stu-id="0cc5a-106">An administrator (using the BizTalk Administration Console) follows these steps to create a receive location:</span></span>  
  
1.  <span data-ttu-id="0cc5a-107">创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-107">Creates a receive location.</span></span>  
  
2.  <span data-ttu-id="0cc5a-108">将接收位置与主机相关联。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-108">Associates the receive location with a host.</span></span>  
  
3.  <span data-ttu-id="0cc5a-109">将接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-109">Binds the receive location to an orchestration.</span></span>  
  
4.  <span data-ttu-id="0cc5a-110">启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-110">Enables the receive location.</span></span>  
  
5.  <span data-ttu-id="0cc5a-111">接收位置接收消息。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-111">The receive location receives messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cc5a-112">更改接收位置所做的如何使用 Windows Management Instrumentation (WMI) 会影响接收位置在 BizTalk 管理控制台中显示。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-112">Changes to receive locations made by using Windows Management Instrumentation (WMI) affect how receive locations appear in the BizTalk Administration Console.</span></span> <span data-ttu-id="0cc5a-113">例如，如果管理员使用 WMI 来创建新接收位置，则该接收位置将显示在 BizTalk 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-113">For example, if an administrator uses WMI to create a new receive location, that receive location appears in the BizTalk Administration Console.</span></span> <span data-ttu-id="0cc5a-114">同样，如果管理员删除某一接收位置，将从 BizTalk 管理控制台中消失的接收位置。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-114">Similarly, if an administrator deletes a receive location, the receive location disappears from the BizTalk Administration Console.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="0cc5a-115">每个接收位置必须具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-115">Each receive location must have a unique name.</span></span> <span data-ttu-id="0cc5a-116">两个接收位置不能在同一个具有相同名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-116">Two receive locations cannot have the same name in the same [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]deployment.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="0cc5a-117">我们建议您设置加强的访问控制列表 (ACL) 中的接收位置的放置位置。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-117">We recommend that you set strong access control lists (ACL) in the drop location for the receive locations.</span></span> <span data-ttu-id="0cc5a-118">例如，您必须设置加强的目录的 Acl 文件接收位置从其中提取消息，以便只有经过授权的用户可以在此位置中存放消息。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-118">For example, you must set strong ACLs for the directory where the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
## <a name="receive-location-types"></a><span data-ttu-id="0cc5a-119">接收位置类型</span><span class="sxs-lookup"><span data-stu-id="0cc5a-119">Receive Location Types</span></span>  
 <span data-ttu-id="0cc5a-120">有两种类型的接收位置</span><span class="sxs-lookup"><span data-stu-id="0cc5a-120">There are two types of receive locations</span></span>  
  
-   <span data-ttu-id="0cc5a-121">单向。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-121">One-way.</span></span> <span data-ttu-id="0cc5a-122">用于存放消息并且不等待同步回复的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-122">Used for applications that drop off a message and do not wait for a synchronous reply.</span></span>  
  
-   <span data-ttu-id="0cc5a-123">请求-响应。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-123">Request-response.</span></span> <span data-ttu-id="0cc5a-124">与需要对一条消息的响应的应用程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-124">Used with applications that require a response to a message.</span></span>  
  
## <a name="receive-location-properties"></a><span data-ttu-id="0cc5a-125">接收位置属性</span><span class="sxs-lookup"><span data-stu-id="0cc5a-125">Receive Location Properties</span></span>  
 <span data-ttu-id="0cc5a-126">接收位置具有全局和特定于适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-126">Receive locations have global and adapter-specific properties.</span></span> <span data-ttu-id="0cc5a-127">管理员使用 BizTalk 管理控制台中，设置全局属性的所有接收位置与特定适配器相关联。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-127">Administrators, using the BizTalk Administration Console, set global properties for all of the receive locations associated with a specific adapter.</span></span>  
  
 <span data-ttu-id="0cc5a-128">按序发生更改，以接收位置属性。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-128">Changes to receive location properties happen sequentially.</span></span> <span data-ttu-id="0cc5a-129">如果解决方案开发人员修改属性值某一特定接收位置、 新的属性值重写的全局属性值的接收位置在 BizTalk 管理控制台中设置管理员。</span><span class="sxs-lookup"><span data-stu-id="0cc5a-129">If a solutions developer modifies a property value for a specific receive location, the new property value overrides the global property value for that receive location that the administrator set in the BizTalk Administration Console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc5a-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="0cc5a-130">See Also</span></span>  
 <span data-ttu-id="0cc5a-131">[管理接收位置](../core/managing-receive-locations.md) </span><span class="sxs-lookup"><span data-stu-id="0cc5a-131">[Managing Receive Locations](../core/managing-receive-locations.md) </span></span>  
 [<span data-ttu-id="0cc5a-132">项目</span><span class="sxs-lookup"><span data-stu-id="0cc5a-132">Artifacts</span></span>](../core/artifacts.md)