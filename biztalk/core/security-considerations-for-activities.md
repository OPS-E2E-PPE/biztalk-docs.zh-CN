---
title: 有关活动的安全注意事项 |Microsoft Docs
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
ms.openlocfilehash: e6c6faca1adf03c216cc0ce6fd4510c937cb1963
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250994"
---
# <a name="security-considerations-for-activities"></a><span data-ttu-id="594cc-102">有关活动的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="594cc-102">Security Considerations for Activities</span></span>
<span data-ttu-id="594cc-103">侦听 WCF 适配器时，使用的安全角色都与用于其他 BAM 解决方案相同。</span><span class="sxs-lookup"><span data-stu-id="594cc-103">The security roles you use when intercepting the WCF adapter are the same as those used for other BAM solutions.</span></span> <span data-ttu-id="594cc-104">侦听 WCF 适配器的其他注意事项包括选择要使用的正确的用户和事件写入者角色。</span><span class="sxs-lookup"><span data-stu-id="594cc-104">The additional considerations for intercepting the WCF adapter involve selecting the correct user and event writer role to use.</span></span>  
  
 <span data-ttu-id="594cc-105">使用 WCF 服务和 WCF 适配器时，所有与 BAM 相关的数据是由所选角色写入 BAM 主导入数据库中。</span><span class="sxs-lookup"><span data-stu-id="594cc-105">When using WCF services and the WCF adapter, all BAM-related data is written to the BAM Primary Import database by the selected role.</span></span>  
  
 <span data-ttu-id="594cc-106">可以通过评估你的解决方案的方案选择适当的用户角色配置：</span><span class="sxs-lookup"><span data-stu-id="594cc-106">You can select the proper user role configuration by assessing your solution scenario:</span></span>  
  
- <span data-ttu-id="594cc-107">如果解决方案需要很多新服务，由许多不同的活动跟踪，并将所有相同的用户帐户下运行，但最好使用 BAM_EVENT_WRITER 超级角色来写入侦听到的事件。</span><span class="sxs-lookup"><span data-stu-id="594cc-107">If your solution requires many new services that are tracked by many different activities, and are all run under the same user account, it is advantageous to use the BAM_EVENT_WRITER super role to write the intercepted events.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="594cc-108">用户必须添加到 BAM 事件写入者超级角色。</span><span class="sxs-lookup"><span data-stu-id="594cc-108">Users must be added to the BAM event writer super role.</span></span> <span data-ttu-id="594cc-109">将用户添加到超级角色时，请务必记住然后将能够在系统中写入到的所有活动用户。</span><span class="sxs-lookup"><span data-stu-id="594cc-109">When adding a user to the super role it is important to remember that the user will then be able to write to all the activities in the system.</span></span>  
  
- <span data-ttu-id="594cc-110">如果解决方案需要更好地控制编写的事件，则应使用特定于活动的角色。</span><span class="sxs-lookup"><span data-stu-id="594cc-110">If your solution requires greater control of the events written, then you should use activity-specific roles.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="594cc-111">用户必须添加到活动特定的事件写入者角色为每个活动。</span><span class="sxs-lookup"><span data-stu-id="594cc-111">Users must be added to the activity specific event writer role for each activity.</span></span>  
  
  <span data-ttu-id="594cc-112">有关配置 BAM 事件写入者角色的详细信息，请参阅[如何确定和活动中设置事件写入者角色](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="594cc-112">For more information about configuring the BAM event writer roles, see [How to Determine and Set Event Writer Roles for Activities](../core/how-to-determine-and-set-event-writer-roles-for-activities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="594cc-113">必须是 BizTalk Application Users 组的成员。</span><span class="sxs-lookup"><span data-stu-id="594cc-113">You must be a member of the BizTalk Application Users group.</span></span>  
  
 <span data-ttu-id="594cc-114">选择要配置 IIS 模拟安全的 BAM WCF 侦听器时使用的用户帐户时应考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="594cc-114">When selecting the user account to use when configuring the BAM WCF interceptor for impersonation security under IIS you should consider the following scenarios:</span></span>  
  
- <span data-ttu-id="594cc-115">自承载：在计算机上可执行文件运行承载 WCF 服务打开。</span><span class="sxs-lookup"><span data-stu-id="594cc-115">Self-Hosted: An executable running on your computer that holds the WCF service open.</span></span>  
  
- <span data-ttu-id="594cc-116">WCF 适配器：使用创建的解决方案**Biztalk WCF 服务发布向导**。</span><span class="sxs-lookup"><span data-stu-id="594cc-116">WCF adapter: Solutions created using the **Biztalk WCF Service Publishing Wizard**.</span></span>  
  
- <span data-ttu-id="594cc-117">IIS 为宿主：使用 WCF 服务的 IIS 应用程序中托管的解决方案。</span><span class="sxs-lookup"><span data-stu-id="594cc-117">IIS hosted: A solution hosted in an IIS application using a WCF Service.</span></span>  
  
  <span data-ttu-id="594cc-118">使用下表有助于确定要使用的帐户：</span><span class="sxs-lookup"><span data-stu-id="594cc-118">Use the following table to help identify the account to use:</span></span>  
  
|<span data-ttu-id="594cc-119">解决方案类型</span><span class="sxs-lookup"><span data-stu-id="594cc-119">Solution type</span></span>|<span data-ttu-id="594cc-120">若要使用的帐户</span><span class="sxs-lookup"><span data-stu-id="594cc-120">Account to use</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="594cc-121">自承载</span><span class="sxs-lookup"><span data-stu-id="594cc-121">Self-hosted</span></span>|<span data-ttu-id="594cc-122">用于运行保持服务的可执行文件的帐户打开。</span><span class="sxs-lookup"><span data-stu-id="594cc-122">The account that is used to run the executable that will hold the service open.</span></span>|  
|<span data-ttu-id="594cc-123">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="594cc-123">WCF adapter</span></span>|<span data-ttu-id="594cc-124">使用应用程序池标识：这是与包含接收位置的 Vroot 相关联的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="594cc-124">Use the AppPool identity: This is the AppPool associated with the Vroot that houses the receive location.</span></span> <span data-ttu-id="594cc-125">当你使用时自动创建此标识**BizTalk WCF 服务发布向导**以发布该站点。</span><span class="sxs-lookup"><span data-stu-id="594cc-125">This identity is created automatically when you use the **BizTalk WCF Service Publishing Wizard** to publish the site.</span></span> <span data-ttu-id="594cc-126">您可以考虑这一种特殊情况的 IIS 承载解决方案。</span><span class="sxs-lookup"><span data-stu-id="594cc-126">You can consider this a special case of the IIS-hosted solution.</span></span>|  
|<span data-ttu-id="594cc-127">IIS-hosted</span><span class="sxs-lookup"><span data-stu-id="594cc-127">IIS-hosted</span></span>|<span data-ttu-id="594cc-128">运行 WCF 服务 VRoot/应用程序的应用程序池用户标识。</span><span class="sxs-lookup"><span data-stu-id="594cc-128">The identity of the AppPool user running the WCF service VRoot/Application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="594cc-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="594cc-129">See Also</span></span>  
 [<span data-ttu-id="594cc-130">BAM 侦听器的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="594cc-130">Security Considerations for BAM Interceptors</span></span>](../core/security-considerations-for-bam-interceptors.md)