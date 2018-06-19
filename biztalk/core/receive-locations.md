---
title: 接收位置 |Microsoft 文档
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
ms.openlocfilehash: 9866edd5dfa6f953c4e847f191891bd7e6bc25ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268621"
---
# <a name="receive-locations"></a><span data-ttu-id="687a1-102">接收位置</span><span class="sxs-lookup"><span data-stu-id="687a1-102">Receive Locations</span></span>
<span data-ttu-id="687a1-103">创建接收位置涉及指定入站消息到达的地址以及用于处理在该地址接收的消息的消息传送管道。</span><span class="sxs-lookup"><span data-stu-id="687a1-103">Creating a receive location involves specifying an address at which inbound messages arrive and the messaging pipeline that processes the message received at that address.</span></span> <span data-ttu-id="687a1-104">只有管理员才能创建和启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="687a1-104">Only administrators can create and enable receive locations.</span></span>  
  
 <span data-ttu-id="687a1-105">管理员使用 BizTalk 管理控制台来创建接收位置，将接收位置绑定到业务流程，启用接收位置，禁用接收位置，以及为接收位置设置全局属性。</span><span class="sxs-lookup"><span data-stu-id="687a1-105">An administrator uses the BizTalk Administration Console to create receive locations, bind receive locations to orchestrations, enable receive locations, disable receive locations, and set global properties for receive locations.</span></span>  
  
 <span data-ttu-id="687a1-106">若要创建接收位置，管理员（使用该 BizTalk 管理控制台）可以按照这些步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="687a1-106">An administrator (using the BizTalk Administration Console) follows these steps to create a receive location:</span></span>  
  
1.  <span data-ttu-id="687a1-107">创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="687a1-107">Creates a receive location.</span></span>  
  
2.  <span data-ttu-id="687a1-108">将接收位置与某个主机相关联。</span><span class="sxs-lookup"><span data-stu-id="687a1-108">Associates the receive location with a host.</span></span>  
  
3.  <span data-ttu-id="687a1-109">将接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="687a1-109">Binds the receive location to an orchestration.</span></span>  
  
4.  <span data-ttu-id="687a1-110">允许接收位置。</span><span class="sxs-lookup"><span data-stu-id="687a1-110">Enables the receive location.</span></span>  
  
5.  <span data-ttu-id="687a1-111">接收位置接收消息。</span><span class="sxs-lookup"><span data-stu-id="687a1-111">The receive location receives messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="687a1-112">使用 Windows Management Instrumentation (WMI) 对接收位置所做的更改会影响接收位置在 BizTalk 管理控制台中显示的方式。</span><span class="sxs-lookup"><span data-stu-id="687a1-112">Changes to receive locations made by using Windows Management Instrumentation (WMI) affect how receive locations appear in the BizTalk Administration Console.</span></span> <span data-ttu-id="687a1-113">例如，如果管理员使用 WMI 来创建新接收位置，则该接收位置将显示在 BizTalk 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="687a1-113">For example, if an administrator uses WMI to create a new receive location, that receive location appears in the BizTalk Administration Console.</span></span> <span data-ttu-id="687a1-114">同样，如果管理员删除某一接收位置，则该接收位置将从 BizTalk 管理控制台中消失。</span><span class="sxs-lookup"><span data-stu-id="687a1-114">Similarly, if an administrator deletes a receive location, the receive location disappears from the BizTalk Administration Console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="687a1-115">每个接收位置都必须具有唯一名称。</span><span class="sxs-lookup"><span data-stu-id="687a1-115">Each receive location must have a unique name.</span></span> <span data-ttu-id="687a1-116">两个接收位置不能在同一个具有相同名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。</span><span class="sxs-lookup"><span data-stu-id="687a1-116">Two receive locations cannot have the same name in the same [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]deployment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="687a1-117">建议您在存放位置中为接收位置设置加强的访问控制列表 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="687a1-117">We recommend that you set strong access control lists (ACL) in the drop location for the receive locations.</span></span> <span data-ttu-id="687a1-118">例如，在文件接收位置从其中提取消息的目录中，必须设置加强的 ACL，以便只有经过授权的用户才能在此位置中存放消息。</span><span class="sxs-lookup"><span data-stu-id="687a1-118">For example, you must set strong ACLs for the directory where the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
## <a name="receive-location-types"></a><span data-ttu-id="687a1-119">接收位置类型</span><span class="sxs-lookup"><span data-stu-id="687a1-119">Receive Location Types</span></span>  
 <span data-ttu-id="687a1-120">接收位置具有以下两种类型：</span><span class="sxs-lookup"><span data-stu-id="687a1-120">There are two types of receive locations</span></span>  
  
-   <span data-ttu-id="687a1-121">单向。</span><span class="sxs-lookup"><span data-stu-id="687a1-121">One-way.</span></span> <span data-ttu-id="687a1-122">用于存放消息并且不等待同步回复的应用程序。</span><span class="sxs-lookup"><span data-stu-id="687a1-122">Used for applications that drop off a message and do not wait for a synchronous reply.</span></span>  
  
-   <span data-ttu-id="687a1-123">请求-响应。</span><span class="sxs-lookup"><span data-stu-id="687a1-123">Request-response.</span></span> <span data-ttu-id="687a1-124">用于需要消息响应的应用程序。</span><span class="sxs-lookup"><span data-stu-id="687a1-124">Used with applications that require a response to a message.</span></span>  
  
## <a name="receive-location-properties"></a><span data-ttu-id="687a1-125">接收位置属性</span><span class="sxs-lookup"><span data-stu-id="687a1-125">Receive Location Properties</span></span>  
 <span data-ttu-id="687a1-126">接收位置具有全局属性和特定于适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="687a1-126">Receive locations have global and adapter-specific properties.</span></span> <span data-ttu-id="687a1-127">使用 BizTalk 管理控制台中，管理员设置的特定适配器关联的接收位置的所有全局属性。</span><span class="sxs-lookup"><span data-stu-id="687a1-127">Administrators, using the BizTalk Administration Console, set global properties for all of the receive locations associated with a specific adapter.</span></span>  
  
 <span data-ttu-id="687a1-128">对接收位置属性的更改将按序发生。</span><span class="sxs-lookup"><span data-stu-id="687a1-128">Changes to receive location properties happen sequentially.</span></span> <span data-ttu-id="687a1-129">如果解决方案开发人员修改的属性值，对特定接收位置，新属性值将重写的全局属性值，接收管理员设置了 BizTalk 管理控制台中的位置。</span><span class="sxs-lookup"><span data-stu-id="687a1-129">If a solutions developer modifies a property value for a specific receive location, the new property value overrides the global property value for that receive location that the administrator set in the BizTalk Administration Console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="687a1-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="687a1-130">See Also</span></span>  
 <span data-ttu-id="687a1-131">[管理接收位置](../core/managing-receive-locations.md) </span><span class="sxs-lookup"><span data-stu-id="687a1-131">[Managing Receive Locations](../core/managing-receive-locations.md) </span></span>  
 [<span data-ttu-id="687a1-132">项目</span><span class="sxs-lookup"><span data-stu-id="687a1-132">Artifacts</span></span>](../core/artifacts.md)