---
title: "单一登录： 事件 11008 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7e11dbc-7596-45fa-ae54-a6e79498e60e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88d2dfa2cfb71d66b43cfaa77b24b1dfce70fd7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11008"></a><span data-ttu-id="1c71d-102">单一登录： 事件 11008</span><span class="sxs-lookup"><span data-stu-id="1c71d-102">Single Sign-On: Event 11008</span></span>
## <a name="details"></a><span data-ttu-id="1c71d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1c71d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1c71d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1c71d-104">Product Name</span></span>|<span data-ttu-id="1c71d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1c71d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="1c71d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="1c71d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="1c71d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1c71d-107">Event ID</span></span>|<span data-ttu-id="1c71d-108">11008</span><span class="sxs-lookup"><span data-stu-id="1c71d-108">11008</span></span>|  
|<span data-ttu-id="1c71d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1c71d-109">Event Source</span></span>|<span data-ttu-id="1c71d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1c71d-110">ENTSSO</span></span>|  
|<span data-ttu-id="1c71d-111">组件</span><span class="sxs-lookup"><span data-stu-id="1c71d-111">Component</span></span>|<span data-ttu-id="1c71d-112">N/A</span><span class="sxs-lookup"><span data-stu-id="1c71d-112">N/A</span></span>|  
|<span data-ttu-id="1c71d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1c71d-113">Symbolic Name</span></span>|<span data-ttu-id="1c71d-114">SSO_WARN_CHECK_GROUP</span><span class="sxs-lookup"><span data-stu-id="1c71d-114">SSO_WARN_CHECK_GROUP</span></span>|  
|<span data-ttu-id="1c71d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1c71d-115">Message Text</span></span>|<span data-ttu-id="1c71d-116">检查组成员失败。%r</span><span class="sxs-lookup"><span data-stu-id="1c71d-116">Check group membership failed.%r</span></span><br /><br /> <span data-ttu-id="1c71d-117">组名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1c71d-117">Group Name: %1%r</span></span><br /><br /> <span data-ttu-id="1c71d-118">帐户名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="1c71d-118">Account Name: %2%r</span></span><br /><br /> <span data-ttu-id="1c71d-119">其他数据: %3 %r</span><span class="sxs-lookup"><span data-stu-id="1c71d-119">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="1c71d-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="1c71d-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1c71d-121">解释</span><span class="sxs-lookup"><span data-stu-id="1c71d-121">Explanation</span></span>  
 <span data-ttu-id="1c71d-122">引起此问题的主要原因可能是网络问题、跨域使用或混合使用不同级别的域控制器（例如，您的系统使用来自 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 和 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 的域控制器）。</span><span class="sxs-lookup"><span data-stu-id="1c71d-122">This is most likely caused by network issues, cross-domain use, or a mixed level of domain controllers (for example, if your system uses domain controllers from both [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1c71d-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="1c71d-123">User Action</span></span>  
 <span data-ttu-id="1c71d-124">请与网络管理员核对以查看是否存在任何网络问题，或您的系统是否存在跨域使用或混合使用不同级别的域控制器。</span><span class="sxs-lookup"><span data-stu-id="1c71d-124">Check with your network administrator to see if there are any network issues, or if your system has any cross-domain use or mixed level of domain controllers.</span></span>