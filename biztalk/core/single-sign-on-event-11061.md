---
title: 单一登录：事件 11061 |Microsoft Docs
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
ms.openlocfilehash: 5da9ae664cd16a9fe6fe528650775877bd2322f7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258745"
---
# <a name="single-sign-on-event-11061"></a><span data-ttu-id="e257d-102">单一登录：事件 11061</span><span class="sxs-lookup"><span data-stu-id="e257d-102">Single Sign-On: Event 11061</span></span>
## <a name="details"></a><span data-ttu-id="e257d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e257d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e257d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e257d-104">Product Name</span></span>   |                                                                                                                     <span data-ttu-id="e257d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e257d-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="e257d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e257d-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    <span data-ttu-id="e257d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e257d-107">Event ID</span></span>     |                                                                                                                               <span data-ttu-id="e257d-108">11061</span><span class="sxs-lookup"><span data-stu-id="e257d-108">11061</span></span>                                                                                                                               |
|  <span data-ttu-id="e257d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e257d-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="e257d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e257d-110">ENTSSO</span></span>                                                                                                                               |
|    <span data-ttu-id="e257d-111">组件</span><span class="sxs-lookup"><span data-stu-id="e257d-111">Component</span></span>    |                                                                                                                                <span data-ttu-id="e257d-112">不可用</span><span class="sxs-lookup"><span data-stu-id="e257d-112">N/A</span></span>                                                                                                                                |
|  <span data-ttu-id="e257d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e257d-113">Symbolic Name</span></span>  |                                                                                                                   <span data-ttu-id="e257d-114">SSO_WARN_BAD_PASSWORD_FILTER</span><span class="sxs-lookup"><span data-stu-id="e257d-114">SSO_WARN_BAD_PASSWORD_FILTER</span></span>                                                                                                                    |
|  <span data-ttu-id="e257d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e257d-115">Message Text</span></span>   | <span data-ttu-id="e257d-116">密码筛选器字符串无效。</span><span class="sxs-lookup"><span data-stu-id="e257d-116">The password filter string is not valid.</span></span> <span data-ttu-id="e257d-117">任何密码筛选器将不 used.%r</span><span class="sxs-lookup"><span data-stu-id="e257d-117">No password filter will be used.%r</span></span><br /><br /> <span data-ttu-id="e257d-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e257d-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="e257d-119">密码筛选器字符串: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e257d-119">Password Filter String: %2%r</span></span><br /><br /> <span data-ttu-id="e257d-120">处理标记数: %3 %r</span><span class="sxs-lookup"><span data-stu-id="e257d-120">Number Of Tokens Processed: %3%r</span></span><br /><br /> <span data-ttu-id="e257d-121">其他数据: %4 %r</span><span class="sxs-lookup"><span data-stu-id="e257d-121">Additional Data: %4%r</span></span><br /><br /> <span data-ttu-id="e257d-122">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="e257d-122">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e257d-123">解释</span><span class="sxs-lookup"><span data-stu-id="e257d-123">Explanation</span></span>  
 <span data-ttu-id="e257d-124">已手动创建无效的密码筛选器。</span><span class="sxs-lookup"><span data-stu-id="e257d-124">An invalid password filter has been created manually.</span></span> <span data-ttu-id="e257d-125">在此过程中的某个时候引入错误 （错误的位置的警告文本中，请参阅密码筛选器字符串）。</span><span class="sxs-lookup"><span data-stu-id="e257d-125">At some point in this process an error was introduced (see Password Filter String in the warning text for the location of the error).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e257d-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="e257d-126">User Action</span></span>  
 <span data-ttu-id="e257d-127">若要创建密码筛选器使用创建密码筛选器向导，请参阅[如何使用密码筛选器](../core/how-to-use-password-filters.md)。</span><span class="sxs-lookup"><span data-stu-id="e257d-127">To create the Password Filter using the Create Password Filter Wizard, see [How to Use Password Filters](../core/how-to-use-password-filters.md).</span></span>