---
title: 单一登录： 事件 10525 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3cba8ef4-4e48-44a7-b791-bab7dc4b9cc0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae350ce6b1688d908dedb3961007401300d8d2fc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968190"
---
# <a name="single-sign-on-event-10525"></a><span data-ttu-id="486b8-102">单一登录： 事件 10525</span><span class="sxs-lookup"><span data-stu-id="486b8-102">Single Sign-On: Event 10525</span></span>
## <a name="details"></a><span data-ttu-id="486b8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="486b8-103">Details</span></span>  

|                 |                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="486b8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="486b8-104">Product Name</span></span>   |                                                                      <span data-ttu-id="486b8-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="486b8-105">Enterprise Single Sign-On</span></span>                                                                       |
| <span data-ttu-id="486b8-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="486b8-106">Product Version</span></span> |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="486b8-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="486b8-107">Event ID</span></span>     |                                                                                <span data-ttu-id="486b8-108">10525</span><span class="sxs-lookup"><span data-stu-id="486b8-108">10525</span></span>                                                                                 |
|  <span data-ttu-id="486b8-109">事件源</span><span class="sxs-lookup"><span data-stu-id="486b8-109">Event Source</span></span>   |                                                                                <span data-ttu-id="486b8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="486b8-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="486b8-111">组件</span><span class="sxs-lookup"><span data-stu-id="486b8-111">Component</span></span>    |                                                                                 <span data-ttu-id="486b8-112">N\A</span><span class="sxs-lookup"><span data-stu-id="486b8-112">N\A</span></span>                                                                                  |
|  <span data-ttu-id="486b8-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="486b8-113">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="486b8-114">SSO_INFO_GENERATE_SECRET_OK</span><span class="sxs-lookup"><span data-stu-id="486b8-114">SSO_INFO_GENERATE_SECRET_OK</span></span>                                                                      |
|  <span data-ttu-id="486b8-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="486b8-115">Message Text</span></span>   | <span data-ttu-id="486b8-116">新的主密钥已成功 generated.%r</span><span class="sxs-lookup"><span data-stu-id="486b8-116">A new master secret was successfully generated.%r</span></span><br /><br /> <span data-ttu-id="486b8-117">MSID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="486b8-117">MSID: %1%r</span></span><br /><br /> <span data-ttu-id="486b8-118">客户端用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="486b8-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="486b8-119">客户端计算机: %3 %r</span><span class="sxs-lookup"><span data-stu-id="486b8-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="486b8-120">跟踪 ID: %4</span><span class="sxs-lookup"><span data-stu-id="486b8-120">Tracking ID: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="486b8-121">解释</span><span class="sxs-lookup"><span data-stu-id="486b8-121">Explanation</span></span>  
 <span data-ttu-id="486b8-122">此信息事件表示已成功生成新主密钥。</span><span class="sxs-lookup"><span data-stu-id="486b8-122">This Information event indicates that a new master secret was successfully generated.</span></span>  

## <a name="user-action"></a><span data-ttu-id="486b8-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="486b8-123">User Action</span></span>  

- <span data-ttu-id="486b8-124">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="486b8-124">No user action is necessary.</span></span>  

  <span data-ttu-id="486b8-125">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="486b8-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="486b8-126">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="486b8-126">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="486b8-127">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="486b8-127">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
