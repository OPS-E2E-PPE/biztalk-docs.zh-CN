---
title: 单一登录： 事件 10712 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f890bf20-dfb5-48b9-be6b-de29131a1955
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b044b79ea647a017511a8c4ff69d8ca6deac7096
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002710"
---
# <a name="single-sign-on-event-10712"></a><span data-ttu-id="75b54-102">单一登录： 事件 10712</span><span class="sxs-lookup"><span data-stu-id="75b54-102">Single Sign-On: Event 10712</span></span>
## <a name="details"></a><span data-ttu-id="75b54-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="75b54-103">Details</span></span>  

|                 |                                                                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="75b54-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="75b54-104">Product Name</span></span>   |                                                                             <span data-ttu-id="75b54-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="75b54-105">Enterprise Single Sign-On</span></span>                                                                              |
| <span data-ttu-id="75b54-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="75b54-106">Product Version</span></span> |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    <span data-ttu-id="75b54-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="75b54-107">Event ID</span></span>     |                                                                                       <span data-ttu-id="75b54-108">10712</span><span class="sxs-lookup"><span data-stu-id="75b54-108">10712</span></span>                                                                                        |
|  <span data-ttu-id="75b54-109">事件源</span><span class="sxs-lookup"><span data-stu-id="75b54-109">Event Source</span></span>   |                                                                                       <span data-ttu-id="75b54-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="75b54-110">ENTSSO</span></span>                                                                                       |
|    <span data-ttu-id="75b54-111">组件</span><span class="sxs-lookup"><span data-stu-id="75b54-111">Component</span></span>    |                                                                                        <span data-ttu-id="75b54-112">N\A</span><span class="sxs-lookup"><span data-stu-id="75b54-112">N\A</span></span>                                                                                         |
|  <span data-ttu-id="75b54-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="75b54-113">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="75b54-114">SSO_WARN_PS_NOTIFICATION_TOO_OLD</span><span class="sxs-lookup"><span data-stu-id="75b54-114">SSO_WARN_PS_NOTIFICATION_TOO_OLD</span></span>                                                                          |
|  <span data-ttu-id="75b54-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="75b54-115">Message Text</span></span>   | <span data-ttu-id="75b54-116">通知被丢弃，因为它早已过期。%r</span><span class="sxs-lookup"><span data-stu-id="75b54-116">A notification was discarded because it was too old.%r</span></span><br /><br /> <span data-ttu-id="75b54-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="75b54-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="75b54-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="75b54-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="75b54-119">通知类型: %3 %r</span><span class="sxs-lookup"><span data-stu-id="75b54-119">Notification Type: %3%r</span></span><br /><br /> <span data-ttu-id="75b54-120">其他数据： %4</span><span class="sxs-lookup"><span data-stu-id="75b54-120">Additional Data: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="75b54-121">解释</span><span class="sxs-lookup"><span data-stu-id="75b54-121">Explanation</span></span>  
 <span data-ttu-id="75b54-122">此警告事件表示，密码同步通知由于太旧而被丢弃。</span><span class="sxs-lookup"><span data-stu-id="75b54-122">This Warning event indicates that a Password Sync notification was discarded because it was too old.</span></span>  

## <a name="user-action"></a><span data-ttu-id="75b54-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="75b54-123">User Action</span></span>  

- <span data-ttu-id="75b54-124">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="75b54-124">No user action is necessary.</span></span>  

  <span data-ttu-id="75b54-125">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="75b54-125">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="75b54-126">密码同步</span><span class="sxs-lookup"><span data-stu-id="75b54-126">Password Synchronization</span></span>](../core/password-synchronization2.md)
