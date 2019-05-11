---
title: 单一登录：事件 11008 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7e11dbc-7596-45fa-ae54-a6e79498e60e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 367bb91906d659f0848e1745796c639d5e08f0b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306657"
---
# <a name="single-sign-on-event-11008"></a><span data-ttu-id="9b83b-102">单一登录：事件 11008</span><span class="sxs-lookup"><span data-stu-id="9b83b-102">Single Sign-On: Event 11008</span></span>
## <a name="details"></a><span data-ttu-id="9b83b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9b83b-103">Details</span></span>  
  
|                 |                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9b83b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9b83b-104">Product Name</span></span>   |                                                                 <span data-ttu-id="9b83b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="9b83b-105">Enterprise Single Sign-On</span></span>                                                                 |
| <span data-ttu-id="9b83b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="9b83b-106">Product Version</span></span> |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    <span data-ttu-id="9b83b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9b83b-107">Event ID</span></span>     |                                                                           <span data-ttu-id="9b83b-108">11008</span><span class="sxs-lookup"><span data-stu-id="9b83b-108">11008</span></span>                                                                           |
|  <span data-ttu-id="9b83b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="9b83b-109">Event Source</span></span>   |                                                                          <span data-ttu-id="9b83b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9b83b-110">ENTSSO</span></span>                                                                           |
|    <span data-ttu-id="9b83b-111">组件</span><span class="sxs-lookup"><span data-stu-id="9b83b-111">Component</span></span>    |                                                                            <span data-ttu-id="9b83b-112">不可用</span><span class="sxs-lookup"><span data-stu-id="9b83b-112">N/A</span></span>                                                                            |
|  <span data-ttu-id="9b83b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="9b83b-113">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="9b83b-114">SSO_WARN_CHECK_GROUP</span><span class="sxs-lookup"><span data-stu-id="9b83b-114">SSO_WARN_CHECK_GROUP</span></span>                                                                    |
|  <span data-ttu-id="9b83b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="9b83b-115">Message Text</span></span>   | <span data-ttu-id="9b83b-116">检查组成员身份 failed.%r</span><span class="sxs-lookup"><span data-stu-id="9b83b-116">Check group membership failed.%r</span></span><br /><br /> <span data-ttu-id="9b83b-117">组名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9b83b-117">Group Name: %1%r</span></span><br /><br /> <span data-ttu-id="9b83b-118">帐户名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="9b83b-118">Account Name: %2%r</span></span><br /><br /> <span data-ttu-id="9b83b-119">其他数据: %3 %r</span><span class="sxs-lookup"><span data-stu-id="9b83b-119">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="9b83b-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="9b83b-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9b83b-121">解释</span><span class="sxs-lookup"><span data-stu-id="9b83b-121">Explanation</span></span>  
 <span data-ttu-id="9b83b-122">这很可能是因网络问题、 跨域使用或混合的级别的域控制器 (例如，如果您的系统使用从这两个域控制器[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]和[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="9b83b-122">This is most likely caused by network issues, cross-domain use, or a mixed level of domain controllers (for example, if your system uses domain controllers from both [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9b83b-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="9b83b-123">User Action</span></span>  
 <span data-ttu-id="9b83b-124">请与网络管理员联系，以查看是否有任何网络问题，或您的系统具有任何跨域使用或混合的级别的域控制器。</span><span class="sxs-lookup"><span data-stu-id="9b83b-124">Check with your network administrator to see if there are any network issues, or if your system has any cross-domain use or mixed level of domain controllers.</span></span>