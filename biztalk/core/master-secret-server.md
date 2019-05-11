---
title: 主密钥服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, about Master Secret server
- Master Secret server, SSO
- SSO, encryption key
- Master Secret server, encryption key
- SSO, Master Secret server
ms.assetid: 93685a19-6c27-45db-bfc1-957574362687
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1cc7cfdd23db46f574bf57ccc97ef5959391d0b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531107"
---
# <a name="master-secret-server"></a><span data-ttu-id="e40bd-102">主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="e40bd-102">Master Secret Server</span></span>
<span data-ttu-id="e40bd-103">主密钥服务器是存储主密钥 （加密密钥） 的企业单一登录 (SSO) 服务器。</span><span class="sxs-lookup"><span data-stu-id="e40bd-103">The master secret server is the Enterprise Single Sign-On (SSO) server that stores the master secret (encryption key).</span></span> <span data-ttu-id="e40bd-104">当 SSO 管理员请求它时，主密钥服务器生成主密钥。</span><span class="sxs-lookup"><span data-stu-id="e40bd-104">The master secret server generates the master secret when an SSO administrator requests it.</span></span> <span data-ttu-id="e40bd-105">主密钥服务器将加密的主密钥存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="e40bd-105">The master secret server stores the encrypted master secret in the registry.</span></span> <span data-ttu-id="e40bd-106">只有单一登录管理员才可以访问主密钥。</span><span class="sxs-lookup"><span data-stu-id="e40bd-106">Only Single Sign-On administrators can access the master secret.</span></span>  
  
 <span data-ttu-id="e40bd-107">其他单一登录服务器请每隔 30 秒检查主密钥是否已更改。</span><span class="sxs-lookup"><span data-stu-id="e40bd-107">The other Single Sign-On servers check every 30 seconds to see whether the master secret has changed.</span></span> <span data-ttu-id="e40bd-108">如果已更改，它们读取它安全地;否则，它们继续使用他们已有缓存在内存中的主密钥。</span><span class="sxs-lookup"><span data-stu-id="e40bd-108">If it has changed, they read it securely; otherwise, they continue to use the master secret they already have cached in memory.</span></span> <span data-ttu-id="e40bd-109">SSO 服务使用主密钥进行加密和解密的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="e40bd-109">The SSO service uses the master secret to encrypt and decrypt the user credentials.</span></span>  
  
 <span data-ttu-id="e40bd-110">只有 SSO 管理员配置主密钥服务器并生成主密钥，才能使用 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="e40bd-110">You cannot use the SSO system until an SSO administrator configures the master secret server and generates the master secret.</span></span> <span data-ttu-id="e40bd-111">在配置期间，主密钥服务器生成主密钥。</span><span class="sxs-lookup"><span data-stu-id="e40bd-111">The master secret server generates the master secret during configuration.</span></span> <span data-ttu-id="e40bd-112">只有 SSO 管理员才可以生成主密钥。</span><span class="sxs-lookup"><span data-stu-id="e40bd-112">Only SSO administrators can generate the master secret.</span></span> <span data-ttu-id="e40bd-113">应用程序可以使用 SSO 服务之前，SSO 管理员必须配置主密钥服务器和 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="e40bd-113">An SSO administrator must configure the master secret server and the SSO database before an application can use the SSO service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e40bd-114">生成主密钥后，强烈建议您将其备份并将其存储在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="e40bd-114">After you generate the master secret, it is strongly recommended that you back it up and store it in a secure location.</span></span>  
  
 <span data-ttu-id="e40bd-115">当 SSO 管理员需要重新生成主密钥时，例如，如果 SSO 管理员希望定期更改主密钥对主密钥服务器同时存储旧的和新的主密钥。</span><span class="sxs-lookup"><span data-stu-id="e40bd-115">When an SSO administrator needs to regenerate the master secret, for example, if the SSO administrator wants to change the master secret periodically, the master secret server stores both the old and new master secret.</span></span> <span data-ttu-id="e40bd-116">主密钥服务器然后经历的所有映射、 进行解密使用旧的主密钥，并再次使用新的主密钥对其进行加密。</span><span class="sxs-lookup"><span data-stu-id="e40bd-116">The master secret server then goes through all the mappings, decrypts them using the old master secret, and encrypts them again using the new master secret.</span></span>  
  
 <span data-ttu-id="e40bd-117">如果主密钥服务器发生故障，已在运行的所有运行时操作将继续运行，但 SSO 服务器将无法再新凭据进行加密。</span><span class="sxs-lookup"><span data-stu-id="e40bd-117">If the master secret server fails, all runtime operations already running will continue to run, but SSO servers will not be able to encrypt new credentials.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e40bd-118">SSO 系统中可以有一个主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="e40bd-118">There can be only one master secret server in your SSO system.</span></span> <span data-ttu-id="e40bd-119">因此，强烈建议您群集主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="e40bd-119">Therefore, it is strongly recommended you cluster the master secret server.</span></span> <span data-ttu-id="e40bd-120">有关详细信息，请参阅[如何群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)。</span><span class="sxs-lookup"><span data-stu-id="e40bd-120">For more information, see [How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e40bd-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e40bd-121">See Also</span></span>  
 [<span data-ttu-id="e40bd-122">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="e40bd-122">Using SSO</span></span>](../core/using-sso.md)