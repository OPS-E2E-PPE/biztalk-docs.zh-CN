---
title: 单一登录：Event 10525 | Microsoft Docs
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
ms.openlocfilehash: 677177e19b1c476496eb04bd201cf3c3d679e0be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394346"
---
# <a name="single-sign-on-event-10525"></a><span data-ttu-id="13172-102">单一登录：事件 10525</span><span class="sxs-lookup"><span data-stu-id="13172-102">Single Sign-On: Event 10525</span></span>
## <a name="details"></a><span data-ttu-id="13172-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="13172-103">Details</span></span>  

|                 |                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="13172-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="13172-104">Product Name</span></span>   |                                                                      <span data-ttu-id="13172-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="13172-105">Enterprise Single Sign-On</span></span>                                                                       |
| <span data-ttu-id="13172-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="13172-106">Product Version</span></span> |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="13172-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="13172-107">Event ID</span></span>     |                                                                                <span data-ttu-id="13172-108">10525</span><span class="sxs-lookup"><span data-stu-id="13172-108">10525</span></span>                                                                                 |
|  <span data-ttu-id="13172-109">事件源</span><span class="sxs-lookup"><span data-stu-id="13172-109">Event Source</span></span>   |                                                                                <span data-ttu-id="13172-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="13172-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="13172-111">组件</span><span class="sxs-lookup"><span data-stu-id="13172-111">Component</span></span>    |                                                                                 <span data-ttu-id="13172-112">N\A</span><span class="sxs-lookup"><span data-stu-id="13172-112">N\A</span></span>                                                                                  |
|  <span data-ttu-id="13172-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="13172-113">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="13172-114">SSO_INFO_GENERATE_SECRET_OK</span><span class="sxs-lookup"><span data-stu-id="13172-114">SSO_INFO_GENERATE_SECRET_OK</span></span>                                                                      |
|  <span data-ttu-id="13172-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="13172-115">Message Text</span></span>   | <span data-ttu-id="13172-116">新的主密钥已成功 generated.%r</span><span class="sxs-lookup"><span data-stu-id="13172-116">A new master secret was successfully generated.%r</span></span><br /><br /> <span data-ttu-id="13172-117">MSID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="13172-117">MSID: %1%r</span></span><br /><br /> <span data-ttu-id="13172-118">客户端用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="13172-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="13172-119">客户端计算机: %3 %r</span><span class="sxs-lookup"><span data-stu-id="13172-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="13172-120">跟踪 ID: %4</span><span class="sxs-lookup"><span data-stu-id="13172-120">Tracking ID: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="13172-121">解释</span><span class="sxs-lookup"><span data-stu-id="13172-121">Explanation</span></span>  
 <span data-ttu-id="13172-122">此信息事件表明已成功生成新的主密钥。</span><span class="sxs-lookup"><span data-stu-id="13172-122">This Information event indicates that a new master secret was successfully generated.</span></span>  

## <a name="user-action"></a><span data-ttu-id="13172-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="13172-123">User Action</span></span>  

- <span data-ttu-id="13172-124">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="13172-124">No user action is necessary.</span></span>  

  <span data-ttu-id="13172-125">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="13172-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="13172-126">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="13172-126">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="13172-127">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="13172-127">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
