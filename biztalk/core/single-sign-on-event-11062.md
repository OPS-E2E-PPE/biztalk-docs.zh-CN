---
title: 单一登录： 事件 11062 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c7c2ea-c671-4853-ac64-8cb80bba98b0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b695b98e556d9fa23f07ee7af6602bb1ad845eb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276461"
---
# <a name="single-sign-on-event-11062"></a><span data-ttu-id="56201-102">单一登录： 事件 11062</span><span class="sxs-lookup"><span data-stu-id="56201-102">Single Sign-On: Event 11062</span></span>
## <a name="details"></a><span data-ttu-id="56201-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="56201-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56201-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="56201-104">Product Name</span></span>|<span data-ttu-id="56201-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="56201-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="56201-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="56201-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="56201-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="56201-107">Event ID</span></span>|<span data-ttu-id="56201-108">11062</span><span class="sxs-lookup"><span data-stu-id="56201-108">11062</span></span>|  
|<span data-ttu-id="56201-109">事件源</span><span class="sxs-lookup"><span data-stu-id="56201-109">Event Source</span></span>|<span data-ttu-id="56201-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="56201-110">ENTSSO</span></span>|  
|<span data-ttu-id="56201-111">组件</span><span class="sxs-lookup"><span data-stu-id="56201-111">Component</span></span>|<span data-ttu-id="56201-112">N/A</span><span class="sxs-lookup"><span data-stu-id="56201-112">N/A</span></span>|  
|<span data-ttu-id="56201-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="56201-113">Symbolic Name</span></span>|<span data-ttu-id="56201-114">SSO_WARN_PASSWORD_FILTER_FAILED</span><span class="sxs-lookup"><span data-stu-id="56201-114">SSO_WARN_PASSWORD_FILTER_FAILED</span></span>|  
|<span data-ttu-id="56201-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="56201-115">Message Text</span></span>|<span data-ttu-id="56201-116">密码筛选失败。</span><span class="sxs-lookup"><span data-stu-id="56201-116">Password filtering failed.</span></span> <span data-ttu-id="56201-117">将不使用任何密码筛选器。%r</span><span class="sxs-lookup"><span data-stu-id="56201-117">No password filter will be used.%r</span></span><br /><br /> <span data-ttu-id="56201-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="56201-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="56201-119">密码筛选器字符串: %2 %r</span><span class="sxs-lookup"><span data-stu-id="56201-119">Password Filter String: %2%r</span></span><br /><br /> <span data-ttu-id="56201-120">其他数据: %3 %r</span><span class="sxs-lookup"><span data-stu-id="56201-120">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="56201-121">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="56201-121">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="56201-122">解释</span><span class="sxs-lookup"><span data-stu-id="56201-122">Explanation</span></span>  
 <span data-ttu-id="56201-123">未创建筛选器和创建密码筛选器时出错。</span><span class="sxs-lookup"><span data-stu-id="56201-123">An error occurred while creating a password filter, and the filter was not created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="56201-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="56201-124">User Action</span></span>  
 <span data-ttu-id="56201-125">若要创建密码筛选器使用创建密码筛选器向导，请参阅[如何使用密码筛选器](../core/how-to-use-password-filters.md)。</span><span class="sxs-lookup"><span data-stu-id="56201-125">To create the Password Filter using the Create Password Filter Wizard, see [How to Use Password Filters](../core/how-to-use-password-filters.md).</span></span>