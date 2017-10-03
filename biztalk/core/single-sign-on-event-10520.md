---
title: "单一登录： 事件 10520 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91662072-d87c-4290-8afb-2143143ee858
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9349452d99518f210237c5e8dd0f945d1f92aa46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10520"></a><span data-ttu-id="5719d-102">单一登录： 事件 10520</span><span class="sxs-lookup"><span data-stu-id="5719d-102">Single Sign-On: Event 10520</span></span>
## <a name="details"></a><span data-ttu-id="5719d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5719d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5719d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5719d-104">Product Name</span></span>|<span data-ttu-id="5719d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5719d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5719d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5719d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5719d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5719d-107">Event ID</span></span>|<span data-ttu-id="5719d-108">10520</span><span class="sxs-lookup"><span data-stu-id="5719d-108">10520</span></span>|  
|<span data-ttu-id="5719d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5719d-109">Event Source</span></span>|<span data-ttu-id="5719d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5719d-110">ENTSSO</span></span>|  
|<span data-ttu-id="5719d-111">组件</span><span class="sxs-lookup"><span data-stu-id="5719d-111">Component</span></span>|<span data-ttu-id="5719d-112">N\A</span><span class="sxs-lookup"><span data-stu-id="5719d-112">N\A</span></span>|  
|<span data-ttu-id="5719d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5719d-113">Symbolic Name</span></span>|<span data-ttu-id="5719d-114">SSO_WARN_NO_SECRETS</span><span class="sxs-lookup"><span data-stu-id="5719d-114">SSO_WARN_NO_SECRETS</span></span>|  
|<span data-ttu-id="5719d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5719d-115">Message Text</span></span>|<span data-ttu-id="5719d-116">未在主密钥服务器的注册表中找到任何密钥。</span><span class="sxs-lookup"><span data-stu-id="5719d-116">No secrets were found in the registry of the master secret server.</span></span> <span data-ttu-id="5719d-117">请使用配置工具来生成或还原主密钥。</span><span class="sxs-lookup"><span data-stu-id="5719d-117">Use the configuration tools to generate or restore a master secret.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5719d-118">解释</span><span class="sxs-lookup"><span data-stu-id="5719d-118">Explanation</span></span>  
 <span data-ttu-id="5719d-119">此警告事件表明，未在主密钥服务器的注册表中找到任何密钥。</span><span class="sxs-lookup"><span data-stu-id="5719d-119">This Warning event indicates that no secrets were found in the registry of the master secret server.</span></span> <span data-ttu-id="5719d-120">SSO 主密钥以加密形式存储在 SSO 主密钥服务器的注册表中。</span><span class="sxs-lookup"><span data-stu-id="5719d-120">The SSO master secrets are stored encrypted in the registry of the SSO master secret server.</span></span> <span data-ttu-id="5719d-121">两个机密通常保存在注册表： 当前的主密钥和上一个主密钥。</span><span class="sxs-lookup"><span data-stu-id="5719d-121">Two secrets are typically kept in the registry: the current master secret, and the previous master secret.</span></span> <span data-ttu-id="5719d-122">密钥使用 GUID（主密钥 ID）标识。</span><span class="sxs-lookup"><span data-stu-id="5719d-122">Secrets are identified using a GUID (the master secret id).</span></span> <span data-ttu-id="5719d-123">如果请求指定的主密钥时无法在注册表中找到该主密钥，则将返回此错误代码。</span><span class="sxs-lookup"><span data-stu-id="5719d-123">If the specified master secret cannot be found in the registry when requested, this error code will be returned.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5719d-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="5719d-124">User Action</span></span>  
 <span data-ttu-id="5719d-125">若要解决此警告，请执行下列一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="5719d-125">To resolve this warnming, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="5719d-126">检查主密钥服务器名称是否正确，且是否为预期的名称。</span><span class="sxs-lookup"><span data-stu-id="5719d-126">Check that the master secret server name is correct and as expected.</span></span>  
  
-   <span data-ttu-id="5719d-127">如果正确，则检查该主密钥服务器的注册表中是否存在该主密钥。</span><span class="sxs-lookup"><span data-stu-id="5719d-127">If it is correct, check that the master secret is present in the registry of that master secret server.</span></span> <span data-ttu-id="5719d-128">该主密钥位于 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS 下（此密钥仅存在于 SSO 主密钥服务器上）。</span><span class="sxs-lookup"><span data-stu-id="5719d-128">The master secret is located under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS (this key is present only on the SSO master secret server).</span></span>  
  
-   <span data-ttu-id="5719d-129">如果该密钥缺失，则主密钥不存在。</span><span class="sxs-lookup"><span data-stu-id="5719d-129">If that key is missing then the master secret is not present.</span></span> <span data-ttu-id="5719d-130">SSOSS 下应存在一个或多个包含加密密钥的名为 GUID 的密钥。</span><span class="sxs-lookup"><span data-stu-id="5719d-130">There should be one or more keys under SSOSS named as GUIDs which contain the encrypted keys.</span></span> <span data-ttu-id="5719d-131">如果这些密钥不存在，则主密钥不存在。</span><span class="sxs-lookup"><span data-stu-id="5719d-131">If these are not present then the master secret is not present.</span></span> <span data-ttu-id="5719d-132">主密钥以 GUID（主密钥 ID）标识，因此，这些 GUID（如果存在）应与所请求的密钥的主密钥 ID 匹配。</span><span class="sxs-lookup"><span data-stu-id="5719d-132">Master secrets are identified with GUIDs (the master secret id) so these GUIDs (if present) should match the master secret id of the secret that was requested.</span></span> <span data-ttu-id="5719d-133">如果存在名为 GUID 的密钥，但它们与所请求的主密钥 ID 不匹配，则将混合注册表中的主密钥与用于对 SSO 数据库 (SSODB) 中的数据进行加密的密钥。</span><span class="sxs-lookup"><span data-stu-id="5719d-133">If there are keys named as GUIDs but they don’t match the requested master secret id, then there is a mixup between the master secret in the registry and the secret that was used to encrypt the data in the SSO database (SSODB).</span></span> <span data-ttu-id="5719d-134">在这种情况下，可能必须还原另一个主密钥，或者 SSODB 已从下层备份还原。</span><span class="sxs-lookup"><span data-stu-id="5719d-134">It may be necessary to restore a different master secret in this case, or maybe the SSODB has been restored from a downlevel backup.</span></span> <span data-ttu-id="5719d-135">如果根本不存在主密钥，则可以使用 SSO 配置工具（命令行或 MMC）从备份还原该主密钥，或者生成一个新密钥。</span><span class="sxs-lookup"><span data-stu-id="5719d-135">If the master secret is not present at all, then it can be restored form backup using the SSO configuration tools (command line or MMC) or a new secret can be generated.</span></span> <span data-ttu-id="5719d-136">请注意，如果这是新安装，且 SSO 数据库中不存在任何现有的已加密数据，则通常只需要生成一个新主密钥。</span><span class="sxs-lookup"><span data-stu-id="5719d-136">Note that you would normally only want to generate a new master secret if this is a new installation and there is no existing encrypted data in the SSO database.</span></span> <span data-ttu-id="5719d-137">主密钥通常是在初始配置过程中首次生成的。</span><span class="sxs-lookup"><span data-stu-id="5719d-137">The master secret is normally generated for the first time during initial configuration.</span></span>  
  
 <span data-ttu-id="5719d-138">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="5719d-138">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="5719d-139">主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="5719d-139">Master Secret Server</span></span>](../core/master-secret-server.md)  
  
-   [<span data-ttu-id="5719d-140">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="5719d-140">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  
  
-   [<span data-ttu-id="5719d-141">配置 SSO</span><span class="sxs-lookup"><span data-stu-id="5719d-141">Configuring SSO</span></span>](../core/configuring-sso.md)