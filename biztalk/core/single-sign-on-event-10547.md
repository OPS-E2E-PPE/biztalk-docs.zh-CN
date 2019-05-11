---
title: 单一登录：Event 10547 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be25cdc9-d6c1-488d-9ead-877a2454c3d1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8ec8133a6d2456e2cdafca56ae956f6be1d31a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243428"
---
# <a name="single-sign-on-event-10547"></a><span data-ttu-id="dc3f8-102">单一登录：事件 10547</span><span class="sxs-lookup"><span data-stu-id="dc3f8-102">Single Sign-On: Event 10547</span></span>
## <a name="details"></a><span data-ttu-id="dc3f8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="dc3f8-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="dc3f8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="dc3f8-104">Product Name</span></span>   |                         <span data-ttu-id="dc3f8-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="dc3f8-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="dc3f8-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="dc3f8-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="dc3f8-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="dc3f8-107">Event ID</span></span>     |                                   <span data-ttu-id="dc3f8-108">10547</span><span class="sxs-lookup"><span data-stu-id="dc3f8-108">10547</span></span>                                   |
|  <span data-ttu-id="dc3f8-109">事件源</span><span class="sxs-lookup"><span data-stu-id="dc3f8-109">Event Source</span></span>   |                                  <span data-ttu-id="dc3f8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="dc3f8-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="dc3f8-111">组件</span><span class="sxs-lookup"><span data-stu-id="dc3f8-111">Component</span></span>    |                                    <span data-ttu-id="dc3f8-112">CO</span><span class="sxs-lookup"><span data-stu-id="dc3f8-112">CO</span></span>                                     |
|  <span data-ttu-id="dc3f8-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="dc3f8-113">Symbolic Name</span></span>  |                          <span data-ttu-id="dc3f8-114">SSO_WARN_UPDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="dc3f8-114">SSO_WARN_UPDATE_FAILED</span></span>                           |
|  <span data-ttu-id="dc3f8-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="dc3f8-115">Message Text</span></span>   | <span data-ttu-id="dc3f8-116">未能重新加密过程中更新 SSO 数据库中的凭据</span><span class="sxs-lookup"><span data-stu-id="dc3f8-116">Failed to update the credentials in the SSO database during re-encryption</span></span> |

## <a name="explanation"></a><span data-ttu-id="dc3f8-117">解释</span><span class="sxs-lookup"><span data-stu-id="dc3f8-117">Explanation</span></span>  
 <span data-ttu-id="dc3f8-118">此警告事件表示没有可以使用新的加密结果更新凭据。</span><span class="sxs-lookup"><span data-stu-id="dc3f8-118">This Warning event indicates that it was not possible to update the credentials with the result of the new encryption.</span></span> <span data-ttu-id="dc3f8-119">当更改主密钥时，通过生成新密钥或还原旧密钥，重新加密对 SSO 数据库进行解密使用旧密钥加密的所有密钥和使用新密钥重新加密。</span><span class="sxs-lookup"><span data-stu-id="dc3f8-119">When the master secret is changed, either by generating a new secret or by restoring an old secret, a re-encryption is performed on the SSO database to decrypt all the secrets encrypted with the old secret, and re-encrypt them with the new secret.</span></span> <span data-ttu-id="dc3f8-120">如果凭据已删除，因为它们是在重新加密的过程中，会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="dc3f8-120">This event can occur if the credentials were deleted as they were in the process of being re-encrypted.</span></span>  

## <a name="user-action"></a><span data-ttu-id="dc3f8-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="dc3f8-121">User Action</span></span>  
 <span data-ttu-id="dc3f8-122">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dc3f8-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="dc3f8-123">等待一小段延迟; 后进行另一个重新加密如果未自动放弃，重新启动 SSO 服务，这将触发新的重新加密，如果需要。</span><span class="sxs-lookup"><span data-stu-id="dc3f8-123">Wait for another re-encryption to occur after a short delay; if that does not occur automatically, restart the SSO service which will trigger a new re-encryption if one is required.</span></span>  

  <span data-ttu-id="dc3f8-124">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="dc3f8-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="dc3f8-125">了解 SSO</span><span class="sxs-lookup"><span data-stu-id="dc3f8-125">Understanding SSO</span></span>](../core/understanding-sso.md)
