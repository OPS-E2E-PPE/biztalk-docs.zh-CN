---
title: "主密钥服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, about Master Secret server
- Master Secret server, SSO
- SSO, encryption key
- Master Secret server, encryption key
- SSO, Master Secret server
ms.assetid: 93685a19-6c27-45db-bfc1-957574362687
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d02d5608546e86801bfc4a2281c42f902594e79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="master-secret-server"></a><span data-ttu-id="d7877-102">主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="d7877-102">Master Secret Server</span></span>
<span data-ttu-id="d7877-103">主密钥服务器是存储主密钥（加密密钥）的企业单一登录 (SSO) 服务器。</span><span class="sxs-lookup"><span data-stu-id="d7877-103">The master secret server is the Enterprise Single Sign-On (SSO) server that stores the master secret (encryption key).</span></span> <span data-ttu-id="d7877-104">主密钥服务器可在 SSO 管理员请求主密钥时生成主密钥。</span><span class="sxs-lookup"><span data-stu-id="d7877-104">The master secret server generates the master secret when an SSO administrator requests it.</span></span> <span data-ttu-id="d7877-105">主密钥服务器将加密主密钥存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="d7877-105">The master secret server stores the encrypted master secret in the registry.</span></span> <span data-ttu-id="d7877-106">只有单一登录管理员才可以访问主密钥。</span><span class="sxs-lookup"><span data-stu-id="d7877-106">Only Single Sign-On administrators can access the master secret.</span></span>  
  
 <span data-ttu-id="d7877-107">其他单一登录服务器将每 30 秒检查一次主密钥是否已更改。</span><span class="sxs-lookup"><span data-stu-id="d7877-107">The other Single Sign-On servers check every 30 seconds to see whether the master secret has changed.</span></span> <span data-ttu-id="d7877-108">如果主密钥已更改，这些服务器将安全地读取该密钥；否则，它们会继续使用内存中缓存的主密钥。</span><span class="sxs-lookup"><span data-stu-id="d7877-108">If it has changed, they read it securely; otherwise, they continue to use the master secret they already have cached in memory.</span></span> <span data-ttu-id="d7877-109">SSO 服务使用主密钥对用户凭据进行加密和解密。</span><span class="sxs-lookup"><span data-stu-id="d7877-109">The SSO service uses the master secret to encrypt and decrypt the user credentials.</span></span>  
  
 <span data-ttu-id="d7877-110">只有在 SSO 管理员配置主密钥服务器并生成主密钥后，您才可以使用 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="d7877-110">You cannot use the SSO system until an SSO administrator configures the master secret server and generates the master secret.</span></span> <span data-ttu-id="d7877-111">主密钥服务器将在配置过程中生成主密钥。</span><span class="sxs-lookup"><span data-stu-id="d7877-111">The master secret server generates the master secret during configuration.</span></span> <span data-ttu-id="d7877-112">只有 SSO 管理员才可以生成主密钥。</span><span class="sxs-lookup"><span data-stu-id="d7877-112">Only SSO administrators can generate the master secret.</span></span> <span data-ttu-id="d7877-113">SSO 管理员必须配置主密钥服务器和 SSO 数据库，应用程序才可以使用 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="d7877-113">An SSO administrator must configure the master secret server and the SSO database before an application can use the SSO service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7877-114">在您生成主密钥后，强烈建议您在安全的位置备份并存储该密钥。</span><span class="sxs-lookup"><span data-stu-id="d7877-114">After you generate the master secret, it is strongly recommended that you back it up and store it in a secure location.</span></span>  
  
 <span data-ttu-id="d7877-115">当 SSO 管理员需要重新生成主密钥时，例如，如果 SSO 管理员希望定期更改主密钥，则可设置主密钥服务器同时存储旧的主密钥和新的主密钥。</span><span class="sxs-lookup"><span data-stu-id="d7877-115">When an SSO administrator needs to regenerate the master secret, for example, if the SSO administrator wants to change the master secret periodically, the master secret server stores both the old and new master secret.</span></span> <span data-ttu-id="d7877-116">这样，主密钥服务器就会检查所有映射，使用旧的主密钥来将这些映射解密，再使用新的主密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="d7877-116">The master secret server then goes through all the mappings, decrypts them using the old master secret, and encrypts them again using the new master secret.</span></span>  
  
 <span data-ttu-id="d7877-117">如果主密钥服务器发生故障，所有已运行的运行时操作将继续运行，但 SSO 服务器将无法对新凭据进行加密。</span><span class="sxs-lookup"><span data-stu-id="d7877-117">If the master secret server fails, all runtime operations already running will continue to run, but SSO servers will not be able to encrypt new credentials.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7877-118">在 SSO 系统中只能有一台主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="d7877-118">There can be only one master secret server in your SSO system.</span></span> <span data-ttu-id="d7877-119">因此，强烈建议您群集主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="d7877-119">Therefore, it is strongly recommended you cluster the master secret server.</span></span> <span data-ttu-id="d7877-120">有关详细信息，请参阅[如何安装群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)。</span><span class="sxs-lookup"><span data-stu-id="d7877-120">For more information, see [How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7877-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7877-121">See Also</span></span>  
 [<span data-ttu-id="d7877-122">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="d7877-122">Using SSO</span></span>](../core/using-sso.md)