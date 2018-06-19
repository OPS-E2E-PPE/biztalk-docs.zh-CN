---
title: 单一登录： 事件 11043 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 128d68fb-1905-49b3-9b67-30a9442569cc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc211e4726c68a16f860dd0431a234765e80b76a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276453"
---
# <a name="single-sign-on-event-11043"></a><span data-ttu-id="3d889-102">单一登录： 事件 11043</span><span class="sxs-lookup"><span data-stu-id="3d889-102">Single Sign-On: Event 11043</span></span>
## <a name="details"></a><span data-ttu-id="3d889-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3d889-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3d889-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3d889-104">Product Name</span></span>|<span data-ttu-id="3d889-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3d889-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3d889-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="3d889-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3d889-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3d889-107">Event ID</span></span>|<span data-ttu-id="3d889-108">11043</span><span class="sxs-lookup"><span data-stu-id="3d889-108">11043</span></span>|  
|<span data-ttu-id="3d889-109">事件源</span><span class="sxs-lookup"><span data-stu-id="3d889-109">Event Source</span></span>|<span data-ttu-id="3d889-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3d889-110">ENTSSO</span></span>|  
|<span data-ttu-id="3d889-111">组件</span><span class="sxs-lookup"><span data-stu-id="3d889-111">Component</span></span>|<span data-ttu-id="3d889-112">N/A</span><span class="sxs-lookup"><span data-stu-id="3d889-112">N/A</span></span>|  
|<span data-ttu-id="3d889-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="3d889-113">Symbolic Name</span></span>|<span data-ttu-id="3d889-114">SSO_WARN_PS_ADAPTER_REPORTED_FAILURE</span><span class="sxs-lookup"><span data-stu-id="3d889-114">SSO_WARN_PS_ADAPTER_REPORTED_FAILURE</span></span>|  
|<span data-ttu-id="3d889-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="3d889-115">Message Text</span></span>|<span data-ttu-id="3d889-116">尝试更改外部密码时，密码同步适配器报告失败。</span><span class="sxs-lookup"><span data-stu-id="3d889-116">The password sync adapter reported a failure while attempting to change the external password.</span></span> <span data-ttu-id="3d889-117">未在 SSO 数据库中更新外部密码。%r</span><span class="sxs-lookup"><span data-stu-id="3d889-117">The external password was not updated in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="3d889-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3d889-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="3d889-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="3d889-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="3d889-120">外部帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="3d889-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="3d889-121">错误消息: %4 %r</span><span class="sxs-lookup"><span data-stu-id="3d889-121">Error Message: %4%r</span></span><br /><br /> <span data-ttu-id="3d889-122">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="3d889-122">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3d889-123">解释</span><span class="sxs-lookup"><span data-stu-id="3d889-123">Explanation</span></span>  
 <span data-ttu-id="3d889-124">ENTSSO 向密码同步适配器发送密码更改时，必须成功更改外部密码，然后 ENTSSO 才能在 SSO 数据库中进行相应更新。</span><span class="sxs-lookup"><span data-stu-id="3d889-124">When ENTSSO sends a password change to a password sync adapter, the external password must be successfully changed before ENTSSO makes it in the SSO database.</span></span> <span data-ttu-id="3d889-125">在这种情况下，不会发生这种错误。</span><span class="sxs-lookup"><span data-stu-id="3d889-125">In this case, that did not occur.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3d889-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="3d889-126">User Action</span></span>  
 <span data-ttu-id="3d889-127">注意警告消息中的信息，并咨询系统管理员。</span><span class="sxs-lookup"><span data-stu-id="3d889-127">Note the information in the warning message and consult your system administrator.</span></span>