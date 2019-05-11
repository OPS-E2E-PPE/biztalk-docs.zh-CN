---
title: 单一登录：Event 10663 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85223ded-1226-4dce-affc-46142157d18d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa139a865dd15f6b7f5ac234b4b1fec56d342e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397577"
---
# <a name="single-sign-on-event-10663"></a><span data-ttu-id="3ff25-102">单一登录：事件 10663</span><span class="sxs-lookup"><span data-stu-id="3ff25-102">Single Sign-On: Event 10663</span></span>
## <a name="details"></a><span data-ttu-id="3ff25-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3ff25-103">Details</span></span>  

|                 |                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3ff25-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3ff25-104">Product Name</span></span>   |                                                                                              <span data-ttu-id="3ff25-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3ff25-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="3ff25-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="3ff25-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    <span data-ttu-id="3ff25-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3ff25-107">Event ID</span></span>     |                                                                                                        <span data-ttu-id="3ff25-108">10663</span><span class="sxs-lookup"><span data-stu-id="3ff25-108">10663</span></span>                                                                                                         |
|  <span data-ttu-id="3ff25-109">事件源</span><span class="sxs-lookup"><span data-stu-id="3ff25-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="3ff25-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3ff25-110">ENTSSO</span></span>                                                                                                        |
|    <span data-ttu-id="3ff25-111">组件</span><span class="sxs-lookup"><span data-stu-id="3ff25-111">Component</span></span>    |                                                                                                         <span data-ttu-id="3ff25-112">N\A</span><span class="sxs-lookup"><span data-stu-id="3ff25-112">N\A</span></span>                                                                                                          |
|  <span data-ttu-id="3ff25-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="3ff25-113">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="3ff25-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="3ff25-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED</span></span>                                                                                      |
|  <span data-ttu-id="3ff25-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="3ff25-115">Message Text</span></span>   | <span data-ttu-id="3ff25-116">从 adapter.%r 接收到外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="3ff25-116">An external password change was received from an adapter.%r</span></span><br /><br /> <span data-ttu-id="3ff25-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3ff25-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="3ff25-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="3ff25-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="3ff25-119">外部帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="3ff25-119">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="3ff25-120">客户端用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="3ff25-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="3ff25-121">客户端计算机： %5</span><span class="sxs-lookup"><span data-stu-id="3ff25-121">Client Computer: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="3ff25-122">解释</span><span class="sxs-lookup"><span data-stu-id="3ff25-122">Explanation</span></span>  
 <span data-ttu-id="3ff25-123">此信息事件表明从适配器接收到外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="3ff25-123">This Information event indicates that an external password change was received from an  adapter.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3ff25-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="3ff25-124">User Action</span></span>  

-   <span data-ttu-id="3ff25-125">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="3ff25-125">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="3ff25-126">详细信息</span><span class="sxs-lookup"><span data-stu-id="3ff25-126">More info</span></span>

- [<span data-ttu-id="3ff25-127">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="3ff25-127">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  

- <span data-ttu-id="3ff25-128">**密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="3ff25-128">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
