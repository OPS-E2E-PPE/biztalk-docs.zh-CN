---
title: 有关活动的安全注意事项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fc49afd-a1c3-4ac7-8b89-11be667221e2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26ea453b24ac3e8df25e7a4da98f27731f3828be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270053"
---
# <a name="security-considerations-for-activities"></a><span data-ttu-id="1d153-102">有关活动的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="1d153-102">Security Considerations for Activities</span></span>
<span data-ttu-id="1d153-103">侦听 WCF 适配器时所使用的安全角色与用于其他 BAM 解决方案的安全角色相同。</span><span class="sxs-lookup"><span data-stu-id="1d153-103">The security roles you use when intercepting the WCF adapter are the same as those used for other BAM solutions.</span></span> <span data-ttu-id="1d153-104">侦听 WCF 适配器时需要考虑的其他注意事项还包括选择要使用的正确的用户和事件写入者角色。</span><span class="sxs-lookup"><span data-stu-id="1d153-104">The additional considerations for intercepting the WCF adapter involve selecting the correct user and event writer role to use.</span></span>  
  
 <span data-ttu-id="1d153-105">当使用 WCF 服务和 WCF 适配器时，所有与 BAM 相关的数据将由选定的角色写入 BAM 主导入数据库中。</span><span class="sxs-lookup"><span data-stu-id="1d153-105">When using WCF services and the WCF adapter, all BAM-related data is written to the BAM Primary Import database by the selected role.</span></span>  
  
 <span data-ttu-id="1d153-106">通过对您的解决方案进行评估，您可以选择合适的用户角色配置：</span><span class="sxs-lookup"><span data-stu-id="1d153-106">You can select the proper user role configuration by assessing your solution scenario:</span></span>  
  
-   <span data-ttu-id="1d153-107">如果您的解决方案需要多个由多个不同类型活动所跟踪的新服务，且这些服务均运行在同一用户帐户下，则最好使用 BAM_EVENT_WRITER 超级角色来写入侦听到的事件。</span><span class="sxs-lookup"><span data-stu-id="1d153-107">If your solution requires many new services that are tracked by many different activities, and are all run under the same user account, it is advantageous to use the BAM_EVENT_WRITER super role to write the intercepted events.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1d153-108">用户必须添加到 BAM 事件写入者超级角色。</span><span class="sxs-lookup"><span data-stu-id="1d153-108">Users must be added to the BAM event writer super role.</span></span> <span data-ttu-id="1d153-109">请记住，当将用户添加到超级角色之后，用户将能够写入系统中的所有活动，这一点至关重要。</span><span class="sxs-lookup"><span data-stu-id="1d153-109">When adding a user to the super role it is important to remember that the user will then be able to write to all the activities in the system.</span></span>  
  
-   <span data-ttu-id="1d153-110">如果您的解决方案需要对写入的事件拥有更大的控制权，则应使用特定于活动的角色。</span><span class="sxs-lookup"><span data-stu-id="1d153-110">If your solution requires greater control of the events written, then you should use activity-specific roles.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1d153-111">对于每个活动，必须将用户添加到特定于活动的事件写入者角色中。</span><span class="sxs-lookup"><span data-stu-id="1d153-111">Users must be added to the activity specific event writer role for each activity.</span></span>  
  
 <span data-ttu-id="1d153-112">有关配置 BAM 事件写入者角色的详细信息，请参阅[如何确定和活动设置事件的编写器角色](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="1d153-112">For more information about configuring the BAM event writer roles, see [How to Determine and Set Event Writer Roles for Activities](../core/how-to-determine-and-set-event-writer-roles-for-activities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1d153-113">你必须是 BizTalk 应用程序用户组的成员。</span><span class="sxs-lookup"><span data-stu-id="1d153-113">You must be a member of the BizTalk Application Users group.</span></span>  
  
 <span data-ttu-id="1d153-114">若要配置针对 IIS 模拟安全的 BAM WCF 侦听器，在选择用于该目的的用户帐户时应考虑以下情况：</span><span class="sxs-lookup"><span data-stu-id="1d153-114">When selecting the user account to use when configuring the BAM WCF interceptor for impersonation security under IIS you should consider the following scenarios:</span></span>  
  
-   <span data-ttu-id="1d153-115">自承载： 在计算机上可执行文件运行，承载 WCF 服务打开。</span><span class="sxs-lookup"><span data-stu-id="1d153-115">Self-Hosted: An executable running on your computer that holds the WCF service open.</span></span>  
  
-   <span data-ttu-id="1d153-116">WCF 适配器： 使用创建的解决方案**Biztalk WCF 服务发布向导**。</span><span class="sxs-lookup"><span data-stu-id="1d153-116">WCF adapter: Solutions created using the **Biztalk WCF Service Publishing Wizard**.</span></span>  
  
-   <span data-ttu-id="1d153-117">承载的 IIS： 使用 WCF 服务的 IIS 应用程序中托管的解决方案。</span><span class="sxs-lookup"><span data-stu-id="1d153-117">IIS hosted: A solution hosted in an IIS application using a WCF Service.</span></span>  
  
 <span data-ttu-id="1d153-118">请用下表帮助您确定要使用的帐户：</span><span class="sxs-lookup"><span data-stu-id="1d153-118">Use the following table to help identify the account to use:</span></span>  
  
|<span data-ttu-id="1d153-119">解决方案类型</span><span class="sxs-lookup"><span data-stu-id="1d153-119">Solution type</span></span>|<span data-ttu-id="1d153-120">要使用的帐户</span><span class="sxs-lookup"><span data-stu-id="1d153-120">Account to use</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="1d153-121">自宿主</span><span class="sxs-lookup"><span data-stu-id="1d153-121">Self-hosted</span></span>|<span data-ttu-id="1d153-122">用于运行保持服务打开的可执行文件的帐户。</span><span class="sxs-lookup"><span data-stu-id="1d153-122">The account that is used to run the executable that will hold the service open.</span></span>|  
|<span data-ttu-id="1d153-123">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="1d153-123">WCF adapter</span></span>|<span data-ttu-id="1d153-124">使用应用程序池标识： 这是与 Vroot 保存接收位置的关联应用程序池。</span><span class="sxs-lookup"><span data-stu-id="1d153-124">Use the AppPool identity: This is the AppPool associated with the Vroot that houses the receive location.</span></span> <span data-ttu-id="1d153-125">当你使用自动创建此标识**BizTalk WCF 服务发布向导**以发布站点。</span><span class="sxs-lookup"><span data-stu-id="1d153-125">This identity is created automatically when you use the **BizTalk WCF Service Publishing Wizard** to publish the site.</span></span> <span data-ttu-id="1d153-126">您可以把这种情况看作是以 IIS 为宿主的解决方案的特殊情况。</span><span class="sxs-lookup"><span data-stu-id="1d153-126">You can consider this a special case of the IIS-hosted solution.</span></span>|  
|<span data-ttu-id="1d153-127">以 IIS 为宿主</span><span class="sxs-lookup"><span data-stu-id="1d153-127">IIS-hosted</span></span>|<span data-ttu-id="1d153-128">运行 WCF 服务 VRoot/应用程序的 AppPool 用户的标识。</span><span class="sxs-lookup"><span data-stu-id="1d153-128">The identity of the AppPool user running the WCF service VRoot/Application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d153-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d153-129">See Also</span></span>  
 [<span data-ttu-id="1d153-130">BAM 拦截器的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="1d153-130">Security Considerations for BAM Interceptors</span></span>](../core/security-considerations-for-bam-interceptors.md)