---
title: 单一登录： 事件 10521 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00d427ff-74d0-45f5-bb55-ab12b564d767
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 827771fe479084719db18152fd86da7d1fc01a2d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271093"
---
# <a name="single-sign-on-event-10521"></a><span data-ttu-id="0a2f0-102">单一登录： 事件 10521</span><span class="sxs-lookup"><span data-stu-id="0a2f0-102">Single Sign-On: Event 10521</span></span>
## <a name="details"></a><span data-ttu-id="0a2f0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0a2f0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a2f0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0a2f0-104">Product Name</span></span>|<span data-ttu-id="0a2f0-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0a2f0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0a2f0-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0a2f0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0a2f0-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0a2f0-107">Event ID</span></span>|<span data-ttu-id="0a2f0-108">10521</span><span class="sxs-lookup"><span data-stu-id="0a2f0-108">10521</span></span>|  
|<span data-ttu-id="0a2f0-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0a2f0-109">Event Source</span></span>|<span data-ttu-id="0a2f0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0a2f0-110">ENTSSO</span></span>|  
|<span data-ttu-id="0a2f0-111">组件</span><span class="sxs-lookup"><span data-stu-id="0a2f0-111">Component</span></span>|<span data-ttu-id="0a2f0-112">N\A</span><span class="sxs-lookup"><span data-stu-id="0a2f0-112">N\A</span></span>|  
|<span data-ttu-id="0a2f0-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0a2f0-113">Symbolic Name</span></span>|<span data-ttu-id="0a2f0-114">SSO_ERROR_SECRETS_NOT_LOADED</span><span class="sxs-lookup"><span data-stu-id="0a2f0-114">SSO_ERROR_SECRETS_NOT_LOADED</span></span>|  
|<span data-ttu-id="0a2f0-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0a2f0-115">Message Text</span></span>|<span data-ttu-id="0a2f0-116">无法从主密钥服务器的注册表加载密钥。</span><span class="sxs-lookup"><span data-stu-id="0a2f0-116">Could not load secrets from the registry of the master secret server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0a2f0-117">解释</span><span class="sxs-lookup"><span data-stu-id="0a2f0-117">Explanation</span></span>  
 <span data-ttu-id="0a2f0-118">当无法从注册表获取主密钥时，会在主密钥服务器上发生此错误事件。</span><span class="sxs-lookup"><span data-stu-id="0a2f0-118">This Error event occurs on the master secret server when the master secrets cannot be obtained from the registry.</span></span> <span data-ttu-id="0a2f0-119">事件日志中可能有相关的错误消息，能够为您提供更多信息。</span><span class="sxs-lookup"><span data-stu-id="0a2f0-119">There may be related errors messages in the event log with further information.</span></span> <span data-ttu-id="0a2f0-120">导致此错误的原因很可能是，当 SSO 服务帐户尝试访问注册表时，发生了权限错误或加密错误。</span><span class="sxs-lookup"><span data-stu-id="0a2f0-120">The most likely cause of this is that there has been a permissions error or an encryption error when the SSO service account attempted to access the registry.</span></span> <span data-ttu-id="0a2f0-121">这会 SSO 服务帐户已更改时发生。</span><span class="sxs-lookup"><span data-stu-id="0a2f0-121">This can occur when the SSO service account has been changed.</span></span> <span data-ttu-id="0a2f0-122">此主密钥是使用基于 SSO 服务帐户标识的某个密钥进行加密的。</span><span class="sxs-lookup"><span data-stu-id="0a2f0-122">The master secret is encrypted with a key that is based on the identity of the SSO service account.</span></span> <span data-ttu-id="0a2f0-123">如果更改了该帐户，则不能再对注册表中的现有主密钥进行解密。</span><span class="sxs-lookup"><span data-stu-id="0a2f0-123">If that account is changed, then the existing master secret in the registry can no longer be decrypted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a2f0-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="0a2f0-124">User Action</span></span>  
 <span data-ttu-id="0a2f0-125">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0a2f0-125">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="0a2f0-126">通过先备份主密钥，然后更改 SSO 服务帐户，最后再还原主密钥来更改 SSO 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="0a2f0-126">Change the SSO service account by backing-up the master secret, then changing the SSO service account, and then restoring the master secret.</span></span> <span data-ttu-id="0a2f0-127">这样可以还原主密钥，并且应该能够修复此错误。</span><span class="sxs-lookup"><span data-stu-id="0a2f0-127">This can restore the master secret and should fix this error.</span></span>  
  
 <span data-ttu-id="0a2f0-128">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="0a2f0-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="0a2f0-129">主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="0a2f0-129">Master Secret Server</span></span>](../core/master-secret-server.md)  
  
-   [<span data-ttu-id="0a2f0-130">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="0a2f0-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  
  
-   [<span data-ttu-id="0a2f0-131">配置 SSO</span><span class="sxs-lookup"><span data-stu-id="0a2f0-131">Configuring SSO</span></span>](../core/configuring-sso.md)  
  
-   [<span data-ttu-id="0a2f0-132">SSO 安全建议</span><span class="sxs-lookup"><span data-stu-id="0a2f0-132">SSO Security Recommendations</span></span>](../core/sso-security-recommendations.md)