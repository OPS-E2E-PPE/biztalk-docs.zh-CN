---
title: 单一登录： 事件 10711 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40722fe1-4be9-40d3-b5c5-a740a4b59f45
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9966cd2f588d34c3be60282bc7acfa54cd1f42b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982574"
---
# <a name="single-sign-on-event-10711"></a><span data-ttu-id="06f3b-102">单一登录： 事件 10711</span><span class="sxs-lookup"><span data-stu-id="06f3b-102">Single Sign-On: Event 10711</span></span>
## <a name="details"></a><span data-ttu-id="06f3b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="06f3b-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="06f3b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="06f3b-104">Product Name</span></span>   |                                                                                                             <span data-ttu-id="06f3b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="06f3b-105">Enterprise Single Sign-On</span></span>                                                                                                             |
| <span data-ttu-id="06f3b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="06f3b-106">Product Version</span></span> |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    <span data-ttu-id="06f3b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="06f3b-107">Event ID</span></span>     |                                                                                                                       <span data-ttu-id="06f3b-108">10711</span><span class="sxs-lookup"><span data-stu-id="06f3b-108">10711</span></span>                                                                                                                       |
|  <span data-ttu-id="06f3b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="06f3b-109">Event Source</span></span>   |                                                                                                                      <span data-ttu-id="06f3b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="06f3b-110">ENTSSO</span></span>                                                                                                                       |
|    <span data-ttu-id="06f3b-111">组件</span><span class="sxs-lookup"><span data-stu-id="06f3b-111">Component</span></span>    |                                                                                                                        <span data-ttu-id="06f3b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="06f3b-112">N\A</span></span>                                                                                                                        |
|  <span data-ttu-id="06f3b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="06f3b-113">Symbolic Name</span></span>  |                                                                                                         <span data-ttu-id="06f3b-114">SSO_WARN_PS_MISSING_INITIAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="06f3b-114">SSO_WARN_PS_MISSING_INITIAL_CREDS</span></span>                                                                                                         |
|  <span data-ttu-id="06f3b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="06f3b-115">Message Text</span></span>   | <span data-ttu-id="06f3b-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="06f3b-116">External password change.</span></span> <span data-ttu-id="06f3b-117">已将此映射的某些缺少的外部凭据字段设置为默认值。%r</span><span class="sxs-lookup"><span data-stu-id="06f3b-117">Some missing external credential fields for this mapping have been set to default values.%r</span></span><br /><br /> <span data-ttu-id="06f3b-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="06f3b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="06f3b-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="06f3b-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="06f3b-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="06f3b-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="06f3b-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="06f3b-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="06f3b-122">解释</span><span class="sxs-lookup"><span data-stu-id="06f3b-122">Explanation</span></span>  
 <span data-ttu-id="06f3b-123">此警告事件表示接收到一个外部密码更改，但凭据丢失。</span><span class="sxs-lookup"><span data-stu-id="06f3b-123">This Warning event indicates that an external password change was received with missing credentials.</span></span> <span data-ttu-id="06f3b-124">这些字段中使用了默认值。</span><span class="sxs-lookup"><span data-stu-id="06f3b-124">Default values were used in those fields.</span></span>  

## <a name="user-action"></a><span data-ttu-id="06f3b-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="06f3b-125">User Action</span></span>  
 <span data-ttu-id="06f3b-126">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="06f3b-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="06f3b-127">如有必要，将凭据设置为匹配。</span><span class="sxs-lookup"><span data-stu-id="06f3b-127">If necessary, set the credentials to match.</span></span>  

  <span data-ttu-id="06f3b-128">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="06f3b-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="06f3b-129">SSO 关联应用程序</span><span class="sxs-lookup"><span data-stu-id="06f3b-129">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  

- [<span data-ttu-id="06f3b-130">密码同步</span><span class="sxs-lookup"><span data-stu-id="06f3b-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
