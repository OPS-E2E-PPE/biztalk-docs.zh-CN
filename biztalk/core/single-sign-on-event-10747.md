---
title: 单一登录：Event 10747 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63ae1ab4-0f4e-45a7-83c1-31b8037e4dd7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2dd430869a49a7ec6085f29f4ef5403b99a6540
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395520"
---
# <a name="single-sign-on-event-10747"></a><span data-ttu-id="ff588-102">单一登录：事件 10747</span><span class="sxs-lookup"><span data-stu-id="ff588-102">Single Sign-On: Event 10747</span></span>
## <a name="details"></a><span data-ttu-id="ff588-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ff588-103">Details</span></span>  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ff588-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ff588-104">Product Name</span></span>   |                                                       <span data-ttu-id="ff588-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ff588-105">Enterprise Single Sign-On</span></span>                                                        |
| <span data-ttu-id="ff588-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ff588-106">Product Version</span></span> |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    <span data-ttu-id="ff588-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ff588-107">Event ID</span></span>     |                                                                 <span data-ttu-id="ff588-108">10747</span><span class="sxs-lookup"><span data-stu-id="ff588-108">10747</span></span>                                                                  |
|  <span data-ttu-id="ff588-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ff588-109">Event Source</span></span>   |                                                                  <span data-ttu-id="ff588-110">N\A</span><span class="sxs-lookup"><span data-stu-id="ff588-110">N\A</span></span>                                                                   |
|    <span data-ttu-id="ff588-111">组件</span><span class="sxs-lookup"><span data-stu-id="ff588-111">Component</span></span>    |                                                                  <span data-ttu-id="ff588-112">N\A</span><span class="sxs-lookup"><span data-stu-id="ff588-112">N\A</span></span>                                                                   |
|  <span data-ttu-id="ff588-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ff588-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="ff588-114">SSO_ERROR_UNKNOWN_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="ff588-114">SSO_ERROR_UNKNOWN_NOTIFICATION</span></span>                                                     |
|  <span data-ttu-id="ff588-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ff588-115">Message Text</span></span>   | <span data-ttu-id="ff588-116">收到未知的通知类型已 received.%r</span><span class="sxs-lookup"><span data-stu-id="ff588-116">An unknown notification type was received.%r</span></span><br /><br /> <span data-ttu-id="ff588-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ff588-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="ff588-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ff588-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="ff588-119">通知类型： %3</span><span class="sxs-lookup"><span data-stu-id="ff588-119">Notification Type: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="ff588-120">解释</span><span class="sxs-lookup"><span data-stu-id="ff588-120">Explanation</span></span>  
 <span data-ttu-id="ff588-121">此错误事件表示 SSO 服务检测到具有无效的通知类型出现内部错误。</span><span class="sxs-lookup"><span data-stu-id="ff588-121">This Error event indicates that an internal error with an invalid notification type was detected by the SSO service.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ff588-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="ff588-122">User Action</span></span>  
 <span data-ttu-id="ff588-123">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ff588-123">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="ff588-124">检查系统和应用程序事件日志中的相关事件。</span><span class="sxs-lookup"><span data-stu-id="ff588-124">Check the system and application event logs for associated events.</span></span>  

  <span data-ttu-id="ff588-125">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="ff588-125">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="ff588-126">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="ff588-126">Using SSO</span></span>](../core/using-sso.md)
