---
title: 单一登录： 事件 11032 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d58cf9d-6806-4580-8014-7eff88d5cc5f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dc69ecf447f0917f843a0f80a0a25b1ed0b6e0a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022043"
---
# <a name="single-sign-on-event-11032"></a><span data-ttu-id="08116-102">单一登录： 事件 11032</span><span class="sxs-lookup"><span data-stu-id="08116-102">Single Sign-On: Event 11032</span></span>
## <a name="details"></a><span data-ttu-id="08116-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="08116-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="08116-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="08116-104">Product Name</span></span>   |                                                                                                                            <span data-ttu-id="08116-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="08116-105">Enterprise Single Sign-On</span></span>                                                                                                                             |
| <span data-ttu-id="08116-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="08116-106">Product Version</span></span> |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    <span data-ttu-id="08116-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="08116-107">Event ID</span></span>     |                                                                                                                                      <span data-ttu-id="08116-108">11032</span><span class="sxs-lookup"><span data-stu-id="08116-108">11032</span></span>                                                                                                                                       |
|  <span data-ttu-id="08116-109">事件源</span><span class="sxs-lookup"><span data-stu-id="08116-109">Event Source</span></span>   |                                                                                                                                      <span data-ttu-id="08116-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="08116-110">ENTSSO</span></span>                                                                                                                                      |
|    <span data-ttu-id="08116-111">组件</span><span class="sxs-lookup"><span data-stu-id="08116-111">Component</span></span>    |                                                                                                                                       <span data-ttu-id="08116-112">N/A</span><span class="sxs-lookup"><span data-stu-id="08116-112">N/A</span></span>                                                                                                                                        |
|  <span data-ttu-id="08116-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="08116-113">Symbolic Name</span></span>  |                                                                                                                     <span data-ttu-id="08116-114">SSO_INFO_PS_WIN_CHANGE_MAPPING_DISABLED</span><span class="sxs-lookup"><span data-stu-id="08116-114">SSO_INFO_PS_WIN_CHANGE_MAPPING_DISABLED</span></span>                                                                                                                      |
|  <span data-ttu-id="08116-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="08116-115">Message Text</span></span>   | <span data-ttu-id="08116-116">Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="08116-116">Windows password change.</span></span> <span data-ttu-id="08116-117">已检测到此 Windows 帐户的映射，但被忽略，因为它已被禁用。%r</span><span class="sxs-lookup"><span data-stu-id="08116-117">A mapping for this Windows account has been detected but ignored because it is disabled.%r</span></span><br /><br /> <span data-ttu-id="08116-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="08116-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="08116-119">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="08116-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="08116-120">应用程序: %3 %r</span><span class="sxs-lookup"><span data-stu-id="08116-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="08116-121">外部帐户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="08116-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="08116-122">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="08116-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="08116-123">解释</span><span class="sxs-lookup"><span data-stu-id="08116-123">Explanation</span></span>  
 <span data-ttu-id="08116-124">已检测到此 Windows 帐户的映射，但被忽略，因为它已被禁用。</span><span class="sxs-lookup"><span data-stu-id="08116-124">A mapping for this Windows account has been detected but ignored because it is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08116-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="08116-125">User Action</span></span>  
  
-   <span data-ttu-id="08116-126">若要启用此映射，请参阅[如何启用用户映射](../core/how-to-enable-a-user-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="08116-126">To enable the mapping, see [How to Enable a User Mapping](../core/how-to-enable-a-user-mapping.md).</span></span>