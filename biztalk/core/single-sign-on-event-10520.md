---
title: 单一登录：Event 10520 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91662072-d87c-4290-8afb-2143143ee858
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a711e7ef49d32b85d774438e4e9f42e9805a99a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400233"
---
# <a name="single-sign-on-event-10520"></a><span data-ttu-id="cef02-102">单一登录：事件 10520</span><span class="sxs-lookup"><span data-stu-id="cef02-102">Single Sign-On: Event 10520</span></span>
## <a name="details"></a><span data-ttu-id="cef02-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cef02-103">Details</span></span>  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cef02-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cef02-104">Product Name</span></span>   |                                                       <span data-ttu-id="cef02-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="cef02-105">Enterprise Single Sign-On</span></span>                                                        |
| <span data-ttu-id="cef02-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="cef02-106">Product Version</span></span> |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    <span data-ttu-id="cef02-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cef02-107">Event ID</span></span>     |                                                                 <span data-ttu-id="cef02-108">10520</span><span class="sxs-lookup"><span data-stu-id="cef02-108">10520</span></span>                                                                  |
|  <span data-ttu-id="cef02-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cef02-109">Event Source</span></span>   |                                                                 <span data-ttu-id="cef02-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cef02-110">ENTSSO</span></span>                                                                 |
|    <span data-ttu-id="cef02-111">组件</span><span class="sxs-lookup"><span data-stu-id="cef02-111">Component</span></span>    |                                                                  <span data-ttu-id="cef02-112">N\A</span><span class="sxs-lookup"><span data-stu-id="cef02-112">N\A</span></span>                                                                   |
|  <span data-ttu-id="cef02-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cef02-113">Symbolic Name</span></span>  |                                                          <span data-ttu-id="cef02-114">SSO_WARN_NO_SECRETS</span><span class="sxs-lookup"><span data-stu-id="cef02-114">SSO_WARN_NO_SECRETS</span></span>                                                           |
|  <span data-ttu-id="cef02-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cef02-115">Message Text</span></span>   | <span data-ttu-id="cef02-116">主密钥服务器的注册表中未不找到任何密钥。</span><span class="sxs-lookup"><span data-stu-id="cef02-116">No secrets were found in the registry of the master secret server.</span></span> <span data-ttu-id="cef02-117">使用配置工具来生成或还原主密钥。</span><span class="sxs-lookup"><span data-stu-id="cef02-117">Use the configuration tools to generate or restore a master secret.</span></span> |

## <a name="explanation"></a><span data-ttu-id="cef02-118">解释</span><span class="sxs-lookup"><span data-stu-id="cef02-118">Explanation</span></span>  
 <span data-ttu-id="cef02-119">此警告事件表明主密钥服务器的注册表中未找到任何密钥。</span><span class="sxs-lookup"><span data-stu-id="cef02-119">This Warning event indicates that no secrets were found in the registry of the master secret server.</span></span> <span data-ttu-id="cef02-120">SSO 主密钥存储在 SSO 主密钥服务器的注册表中加密。</span><span class="sxs-lookup"><span data-stu-id="cef02-120">The SSO master secrets are stored encrypted in the registry of the SSO master secret server.</span></span> <span data-ttu-id="cef02-121">两个密钥通常保存在注册表中： 当前主密钥和之前的主密钥。</span><span class="sxs-lookup"><span data-stu-id="cef02-121">Two secrets are typically kept in the registry: the current master secret, and the previous master secret.</span></span> <span data-ttu-id="cef02-122">使用 GUID (主密钥 id) 标识的机密。</span><span class="sxs-lookup"><span data-stu-id="cef02-122">Secrets are identified using a GUID (the master secret id).</span></span> <span data-ttu-id="cef02-123">如果请求时在注册表中找不到指定的主密钥，则将返回此错误代码。</span><span class="sxs-lookup"><span data-stu-id="cef02-123">If the specified master secret cannot be found in the registry when requested, this error code will be returned.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cef02-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="cef02-124">User Action</span></span>  
 <span data-ttu-id="cef02-125">若要解决此警告，请执行一个或多个以下操作：</span><span class="sxs-lookup"><span data-stu-id="cef02-125">To resolve this warnming, do one or more of the following:</span></span>  

- <span data-ttu-id="cef02-126">检查主密钥服务器名称正确且是否为预期。</span><span class="sxs-lookup"><span data-stu-id="cef02-126">Check that the master secret server name is correct and as expected.</span></span>  

- <span data-ttu-id="cef02-127">如果正确无误，检查是否存在该主密钥服务器的注册表中的主密钥。</span><span class="sxs-lookup"><span data-stu-id="cef02-127">If it is correct, check that the master secret is present in the registry of that master secret server.</span></span> <span data-ttu-id="cef02-128">主密钥位于 hkey_local_machine\software\microsoft\entsso\ssoss 下 （此密钥是仅在 SSO 主密钥服务器上存在）。</span><span class="sxs-lookup"><span data-stu-id="cef02-128">The master secret is located under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS (this key is present only on the SSO master secret server).</span></span>  

- <span data-ttu-id="cef02-129">如果缺少该密钥，则主密钥不存在。</span><span class="sxs-lookup"><span data-stu-id="cef02-129">If that key is missing then the master secret is not present.</span></span> <span data-ttu-id="cef02-130">应存在名为 Guid 的包含加密的密钥的 SSOSS 下的一个或多个密钥。</span><span class="sxs-lookup"><span data-stu-id="cef02-130">There should be one or more keys under SSOSS named as GUIDs which contain the encrypted keys.</span></span> <span data-ttu-id="cef02-131">如果这些不存在，则主密钥不存在。</span><span class="sxs-lookup"><span data-stu-id="cef02-131">If these are not present then the master secret is not present.</span></span> <span data-ttu-id="cef02-132">为主密钥标识 Guid (主密钥 id) 因此，这些 Guid （如果存在） 应与请求的机密的主密钥 id 匹配。</span><span class="sxs-lookup"><span data-stu-id="cef02-132">Master secrets are identified with GUIDs (the master secret id) so these GUIDs (if present) should match the master secret id of the secret that was requested.</span></span> <span data-ttu-id="cef02-133">如果没有名为 Guid 的密钥，但它们与请求的主密钥 id 不匹配，则将混合注册表中的主密钥和用来加密 SSO 数据库 (SSODB) 中的数据的机密。</span><span class="sxs-lookup"><span data-stu-id="cef02-133">If there are keys named as GUIDs but they don’t match the requested master secret id, then there is a mixup between the master secret in the registry and the secret that was used to encrypt the data in the SSO database (SSODB).</span></span> <span data-ttu-id="cef02-134">可能有必要在这种情况下，还原另一个主密钥，或可能已从下层备份还原 SSODB。</span><span class="sxs-lookup"><span data-stu-id="cef02-134">It may be necessary to restore a different master secret in this case, or maybe the SSODB has been restored from a downlevel backup.</span></span> <span data-ttu-id="cef02-135">如果根本不存在主密钥，然后它可以是从备份还原使用 SSO 配置工具 （命令行或 MMC），也可以生成一个新的机密。</span><span class="sxs-lookup"><span data-stu-id="cef02-135">If the master secret is not present at all, then it can be restored form backup using the SSO configuration tools (command line or MMC) or a new secret can be generated.</span></span> <span data-ttu-id="cef02-136">请注意，则通常只需要生成新的主密钥，如果这是新安装并且没有任何现有加密 SSO 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="cef02-136">Note that you would normally only want to generate a new master secret if this is a new installation and there is no existing encrypted data in the SSO database.</span></span> <span data-ttu-id="cef02-137">通常，第一次在初始配置过程生成主密钥。</span><span class="sxs-lookup"><span data-stu-id="cef02-137">The master secret is normally generated for the first time during initial configuration.</span></span>  

  <span data-ttu-id="cef02-138">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="cef02-138">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="cef02-139">主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="cef02-139">Master Secret Server</span></span>](../core/master-secret-server.md)  

- [<span data-ttu-id="cef02-140">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="cef02-140">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  

- [<span data-ttu-id="cef02-141">配置 SSO</span><span class="sxs-lookup"><span data-stu-id="cef02-141">Configuring SSO</span></span>](../core/configuring-sso.md)
