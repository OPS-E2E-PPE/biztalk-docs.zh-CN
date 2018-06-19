---
title: 单一登录： 事件 11061 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52fb18e2-4482-4cdb-b8ed-d579a95acd7c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e86ad25248952697e27fc732ddead6732065acf7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277469"
---
# <a name="single-sign-on-event-11061"></a><span data-ttu-id="5a375-102">单一登录： 事件 11061</span><span class="sxs-lookup"><span data-stu-id="5a375-102">Single Sign-On: Event 11061</span></span>
## <a name="details"></a><span data-ttu-id="5a375-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5a375-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a375-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5a375-104">Product Name</span></span>|<span data-ttu-id="5a375-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5a375-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5a375-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5a375-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5a375-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5a375-107">Event ID</span></span>|<span data-ttu-id="5a375-108">11061</span><span class="sxs-lookup"><span data-stu-id="5a375-108">11061</span></span>|  
|<span data-ttu-id="5a375-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5a375-109">Event Source</span></span>|<span data-ttu-id="5a375-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5a375-110">ENTSSO</span></span>|  
|<span data-ttu-id="5a375-111">组件</span><span class="sxs-lookup"><span data-stu-id="5a375-111">Component</span></span>|<span data-ttu-id="5a375-112">N/A</span><span class="sxs-lookup"><span data-stu-id="5a375-112">N/A</span></span>|  
|<span data-ttu-id="5a375-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5a375-113">Symbolic Name</span></span>|<span data-ttu-id="5a375-114">SSO_WARN_BAD_PASSWORD_FILTER</span><span class="sxs-lookup"><span data-stu-id="5a375-114">SSO_WARN_BAD_PASSWORD_FILTER</span></span>|  
|<span data-ttu-id="5a375-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5a375-115">Message Text</span></span>|<span data-ttu-id="5a375-116">密码筛选器字符串无效。</span><span class="sxs-lookup"><span data-stu-id="5a375-116">The password filter string is not valid.</span></span> <span data-ttu-id="5a375-117">将不使用任何密码筛选器。%r</span><span class="sxs-lookup"><span data-stu-id="5a375-117">No password filter will be used.%r</span></span><br /><br /> <span data-ttu-id="5a375-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5a375-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="5a375-119">密码筛选器字符串: %2 %r</span><span class="sxs-lookup"><span data-stu-id="5a375-119">Password Filter String: %2%r</span></span><br /><br /> <span data-ttu-id="5a375-120">处理标记数: %3 %r</span><span class="sxs-lookup"><span data-stu-id="5a375-120">Number Of Tokens Processed: %3%r</span></span><br /><br /> <span data-ttu-id="5a375-121">其他数据: %4 %r</span><span class="sxs-lookup"><span data-stu-id="5a375-121">Additional Data: %4%r</span></span><br /><br /> <span data-ttu-id="5a375-122">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="5a375-122">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5a375-123">解释</span><span class="sxs-lookup"><span data-stu-id="5a375-123">Explanation</span></span>  
 <span data-ttu-id="5a375-124">已手动创建无效的密码筛选器。</span><span class="sxs-lookup"><span data-stu-id="5a375-124">An invalid password filter has been created manually.</span></span> <span data-ttu-id="5a375-125">此进程中的某点已引入错误（请参阅警告文本中的“密码筛选器字符串”以了解错误位置）。</span><span class="sxs-lookup"><span data-stu-id="5a375-125">At some point in this process an error was introduced (see Password Filter String in the warning text for the location of the error).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5a375-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="5a375-126">User Action</span></span>  
 <span data-ttu-id="5a375-127">若要创建密码筛选器使用创建密码筛选器向导，请参阅[如何使用密码筛选器](../core/how-to-use-password-filters.md)。</span><span class="sxs-lookup"><span data-stu-id="5a375-127">To create the Password Filter using the Create Password Filter Wizard, see [How to Use Password Filters](../core/how-to-use-password-filters.md).</span></span>