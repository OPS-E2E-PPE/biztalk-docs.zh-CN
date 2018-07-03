---
title: 单一登录： 事件 11035 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d551083c-a897-4a76-a40c-2254d3a3e52e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 194d3069f0b74022e6b16a28de1c7f81ae3030f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001718"
---
# <a name="single-sign-on-event-11035"></a><span data-ttu-id="b0dcf-102">单一登录： 事件 11035</span><span class="sxs-lookup"><span data-stu-id="b0dcf-102">Single Sign-On: Event 11035</span></span>
## <a name="details"></a><span data-ttu-id="b0dcf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b0dcf-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b0dcf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b0dcf-104">Product Name</span></span>   |                                                                                                                                               <span data-ttu-id="b0dcf-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b0dcf-105">Enterprise Single Sign-On</span></span>                                                                                                                                                |
| <span data-ttu-id="b0dcf-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b0dcf-106">Product Version</span></span> |                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                               |
|    <span data-ttu-id="b0dcf-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b0dcf-107">Event ID</span></span>     |                                                                                                                                                         <span data-ttu-id="b0dcf-108">11035</span><span class="sxs-lookup"><span data-stu-id="b0dcf-108">11035</span></span>                                                                                                                                                          |
|  <span data-ttu-id="b0dcf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b0dcf-109">Event Source</span></span>   |                                                                                                                                                         <span data-ttu-id="b0dcf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b0dcf-110">ENTSSO</span></span>                                                                                                                                                         |
|    <span data-ttu-id="b0dcf-111">组件</span><span class="sxs-lookup"><span data-stu-id="b0dcf-111">Component</span></span>    |                                                                                                                                                          <span data-ttu-id="b0dcf-112">N/A</span><span class="sxs-lookup"><span data-stu-id="b0dcf-112">N/A</span></span>                                                                                                                                                           |
|  <span data-ttu-id="b0dcf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b0dcf-113">Symbolic Name</span></span>  |                                                                                                                                           <span data-ttu-id="b0dcf-114">SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="b0dcf-114">SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER</span></span>                                                                                                                                            |
|  <span data-ttu-id="b0dcf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b0dcf-115">Message Text</span></span>   | <span data-ttu-id="b0dcf-116">Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="b0dcf-116">Windows password change.</span></span> <span data-ttu-id="b0dcf-117">已检测到此 Windows 帐户的映射，但忽略该映射，因为尚未为此应用程序配置密码同步。%r</span><span class="sxs-lookup"><span data-stu-id="b0dcf-117">A mapping for this Windows account has been detected but ignored because password sync is not configured for this application.%r</span></span><br /><br /> <span data-ttu-id="b0dcf-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b0dcf-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="b0dcf-119">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="b0dcf-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="b0dcf-120">应用程序: %3 %r</span><span class="sxs-lookup"><span data-stu-id="b0dcf-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="b0dcf-121">外部帐户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="b0dcf-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="b0dcf-122">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="b0dcf-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b0dcf-123">解释</span><span class="sxs-lookup"><span data-stu-id="b0dcf-123">Explanation</span></span>  
 <span data-ttu-id="b0dcf-124">已检测到此 Windows 帐户的映射，但忽略该映射，因为尚未为此应用程序配置密码同步。</span><span class="sxs-lookup"><span data-stu-id="b0dcf-124">A mapping for this Windows account has been detected but ignored because password sync is not configured for this application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b0dcf-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="b0dcf-125">User Action</span></span>  
 <span data-ttu-id="b0dcf-126">有关配置密码同步的信息，请参阅[密码同步](../core/password-synchronization2.md)。</span><span class="sxs-lookup"><span data-stu-id="b0dcf-126">For information on configuring Password Sync, see [Password Synchronization](../core/password-synchronization2.md).</span></span>