---
title: 单一登录：事件 10531 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 264941f4-7791-4a1f-a0bf-b992c9ccda64
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34767fb719ffe272720715ed1f4827979c9ff880
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262367"
---
# <a name="single-sign-on-event-10531"></a><span data-ttu-id="f78be-102">单一登录：事件 10531</span><span class="sxs-lookup"><span data-stu-id="f78be-102">Single Sign-On: Event 10531</span></span>
## <a name="details"></a><span data-ttu-id="f78be-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f78be-103">Details</span></span>  

|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f78be-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f78be-104">Product Name</span></span>   |                                                                                    <span data-ttu-id="f78be-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f78be-105">Enterprise Single Sign-On</span></span>                                                                                     |
| <span data-ttu-id="f78be-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f78be-106">Product Version</span></span> |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                    |
|    <span data-ttu-id="f78be-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f78be-107">Event ID</span></span>     |                                                                                              <span data-ttu-id="f78be-108">10531</span><span class="sxs-lookup"><span data-stu-id="f78be-108">10531</span></span>                                                                                               |
|  <span data-ttu-id="f78be-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f78be-109">Event Source</span></span>   |                                                                                              <span data-ttu-id="f78be-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f78be-110">ENTSSO</span></span>                                                                                              |
|    <span data-ttu-id="f78be-111">组件</span><span class="sxs-lookup"><span data-stu-id="f78be-111">Component</span></span>    |                                                                                               <span data-ttu-id="f78be-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f78be-112">N\A</span></span>                                                                                                |
|  <span data-ttu-id="f78be-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f78be-113">Symbolic Name</span></span>  |                                                                                     <span data-ttu-id="f78be-114">SSO_ERROR_GET_SECRET_OK</span><span class="sxs-lookup"><span data-stu-id="f78be-114">SSO_ERROR_GET_SECRET_OK</span></span>                                                                                      |
|  <span data-ttu-id="f78be-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f78be-115">Message Text</span></span>   | <span data-ttu-id="f78be-116">获取主机密 succeeded.%r 的请求</span><span class="sxs-lookup"><span data-stu-id="f78be-116">A request to get a master secret succeeded.%r</span></span><br /><br /> <span data-ttu-id="f78be-117">密钥编号: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f78be-117">Secret Number: %1%r</span></span><br /><br /> <span data-ttu-id="f78be-118">MSID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f78be-118">MSID: %2%r</span></span><br /><br /> <span data-ttu-id="f78be-119">客户端用户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="f78be-119">Client User: %3%r</span></span><br /><br /> <span data-ttu-id="f78be-120">客户端计算机: %4 %r</span><span class="sxs-lookup"><span data-stu-id="f78be-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="f78be-121">跟踪 ID: %5</span><span class="sxs-lookup"><span data-stu-id="f78be-121">Tracking ID: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="f78be-122">解释</span><span class="sxs-lookup"><span data-stu-id="f78be-122">Explanation</span></span>  
 <span data-ttu-id="f78be-123">此事件表示主密钥的请求已成功。</span><span class="sxs-lookup"><span data-stu-id="f78be-123">This event indicates that a request for master secret has succeeded.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f78be-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="f78be-124">User Action</span></span>  

- <span data-ttu-id="f78be-125">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="f78be-125">No user action is necessary.</span></span>  

  <span data-ttu-id="f78be-126">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="f78be-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="f78be-127">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="f78be-127">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="f78be-128">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="f78be-128">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
