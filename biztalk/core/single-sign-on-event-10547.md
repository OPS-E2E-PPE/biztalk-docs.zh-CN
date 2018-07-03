---
title: 单一登录： 事件 10547 |Microsoft Docs
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
ms.openlocfilehash: 1af15d6a6259142d243738ab83cabe3e0c63e9c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010942"
---
# <a name="single-sign-on-event-10547"></a><span data-ttu-id="0113d-102">单一登录： 事件 10547</span><span class="sxs-lookup"><span data-stu-id="0113d-102">Single Sign-On: Event 10547</span></span>
## <a name="details"></a><span data-ttu-id="0113d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0113d-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="0113d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0113d-104">Product Name</span></span>   |                         <span data-ttu-id="0113d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0113d-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="0113d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0113d-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="0113d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0113d-107">Event ID</span></span>     |                                   <span data-ttu-id="0113d-108">10547</span><span class="sxs-lookup"><span data-stu-id="0113d-108">10547</span></span>                                   |
|  <span data-ttu-id="0113d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0113d-109">Event Source</span></span>   |                                  <span data-ttu-id="0113d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0113d-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="0113d-111">组件</span><span class="sxs-lookup"><span data-stu-id="0113d-111">Component</span></span>    |                                    <span data-ttu-id="0113d-112">CO</span><span class="sxs-lookup"><span data-stu-id="0113d-112">CO</span></span>                                     |
|  <span data-ttu-id="0113d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0113d-113">Symbolic Name</span></span>  |                          <span data-ttu-id="0113d-114">SSO_WARN_UPDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="0113d-114">SSO_WARN_UPDATE_FAILED</span></span>                           |
|  <span data-ttu-id="0113d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0113d-115">Message Text</span></span>   | <span data-ttu-id="0113d-116">无法在重新加密过程中更新 SSO 数据库中的凭据。</span><span class="sxs-lookup"><span data-stu-id="0113d-116">Failed to update the credentials in the SSO database during re-encryption</span></span> |

## <a name="explanation"></a><span data-ttu-id="0113d-117">解释</span><span class="sxs-lookup"><span data-stu-id="0113d-117">Explanation</span></span>  
 <span data-ttu-id="0113d-118">此警告事件表示不可能更新凭据以完成新的加密。</span><span class="sxs-lookup"><span data-stu-id="0113d-118">This Warning event indicates that it was not possible to update the credentials with the result of the new encryption.</span></span> <span data-ttu-id="0113d-119">当更改主密钥（通过生成新密钥或还原旧密钥）时，将在 SSO 数据库上执行重新加密，以解密使用旧密钥加密的所有密钥，并使用新密钥对其重新加密。</span><span class="sxs-lookup"><span data-stu-id="0113d-119">When the master secret is changed, either by generating a new secret or by restoring an old secret, a re-encryption is performed on the SSO database to decrypt all the secrets encrypted with the old secret, and re-encrypt them with the new secret.</span></span> <span data-ttu-id="0113d-120">如果已经删除凭据，则会发生此事件，因为凭据正处于重新加密的过程中。</span><span class="sxs-lookup"><span data-stu-id="0113d-120">This event can occur if the credentials were deleted as they were in the process of being re-encrypted.</span></span>  

## <a name="user-action"></a><span data-ttu-id="0113d-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="0113d-121">User Action</span></span>  
 <span data-ttu-id="0113d-122">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0113d-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="0113d-123">稍候一小段时间等待另一次重新加密；如果未自动发生，请重新启动 SSO 服务，这将触发新的重新加密（如果需要的话）。</span><span class="sxs-lookup"><span data-stu-id="0113d-123">Wait for another re-encryption to occur after a short delay; if that does not occur automatically, restart the SSO service which will trigger a new re-encryption if one is required.</span></span>  

  <span data-ttu-id="0113d-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="0113d-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="0113d-125">了解 SSO</span><span class="sxs-lookup"><span data-stu-id="0113d-125">Understanding SSO</span></span>](../core/understanding-sso.md)
