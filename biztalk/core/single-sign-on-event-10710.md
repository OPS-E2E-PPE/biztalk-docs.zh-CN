---
title: 单一登录： 事件 10710 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 469dc407-be7a-45a1-bcf5-2ba7060a19e2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 888468da03c01f654bd550ce210b02c4a03ad40b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989918"
---
# <a name="single-sign-on-event-10710"></a><span data-ttu-id="a0ee8-102">单一登录： 事件 10710</span><span class="sxs-lookup"><span data-stu-id="a0ee8-102">Single Sign-On: Event 10710</span></span>
## <a name="details"></a><span data-ttu-id="a0ee8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a0ee8-103">Details</span></span>  

|                 |                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a0ee8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a0ee8-104">Product Name</span></span>   |                                                                          <span data-ttu-id="a0ee8-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="a0ee8-105">Enterprise Single Sign-On</span></span>                                                                          |
| <span data-ttu-id="a0ee8-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="a0ee8-106">Product Version</span></span> |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                          |
|    <span data-ttu-id="a0ee8-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a0ee8-107">Event ID</span></span>     |                                                                                    <span data-ttu-id="a0ee8-108">10710</span><span class="sxs-lookup"><span data-stu-id="a0ee8-108">10710</span></span>                                                                                    |
|  <span data-ttu-id="a0ee8-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a0ee8-109">Event Source</span></span>   |                                                                                   <span data-ttu-id="a0ee8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a0ee8-110">ENTSSO</span></span>                                                                                    |
|    <span data-ttu-id="a0ee8-111">组件</span><span class="sxs-lookup"><span data-stu-id="a0ee8-111">Component</span></span>    |                                                                                     <span data-ttu-id="a0ee8-112">N\A</span><span class="sxs-lookup"><span data-stu-id="a0ee8-112">N\A</span></span>                                                                                     |
|  <span data-ttu-id="a0ee8-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a0ee8-113">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="a0ee8-114">SSO_INFO_PS_WIN_CHANGE_DAMPED</span><span class="sxs-lookup"><span data-stu-id="a0ee8-114">SSO_INFO_PS_WIN_CHANGE_DAMPED</span></span>                                                                        |
|  <span data-ttu-id="a0ee8-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a0ee8-115">Message Text</span></span>   | <span data-ttu-id="a0ee8-116">Windows 密码更改被阻止（检测为复制和丢弃）。%r</span><span class="sxs-lookup"><span data-stu-id="a0ee8-116">A Windows password change was damped (detected as a duplicate and discarded).%r</span></span><br /><br /> <span data-ttu-id="a0ee8-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a0ee8-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a0ee8-118">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a0ee8-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="a0ee8-119">客户端用户： %3</span><span class="sxs-lookup"><span data-stu-id="a0ee8-119">Client User: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="a0ee8-120">解释</span><span class="sxs-lookup"><span data-stu-id="a0ee8-120">Explanation</span></span>  
 <span data-ttu-id="a0ee8-121">此信息事件表明 Windows 密码更改由于被检测为重复而被丢弃。</span><span class="sxs-lookup"><span data-stu-id="a0ee8-121">This Information event indicates that a Windows password change was discarded because it was detected as a duplicate.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a0ee8-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="a0ee8-122">User Action</span></span>  

- <span data-ttu-id="a0ee8-123">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="a0ee8-123">No user action is necessary.</span></span>  

  <span data-ttu-id="a0ee8-124">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="a0ee8-124">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="a0ee8-125">密码同步</span><span class="sxs-lookup"><span data-stu-id="a0ee8-125">Password Synchronization</span></span>](../core/password-synchronization2.md)
