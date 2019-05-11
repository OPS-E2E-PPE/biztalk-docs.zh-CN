---
title: 单一登录：事件 11018 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83b98a1f-6390-4271-8e81-b855c4d30ec3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae7ed042e8972b233099dd41d24d5ad72c386225
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267251"
---
# <a name="single-sign-on-event-11018"></a><span data-ttu-id="dc23d-102">单一登录：事件 11018</span><span class="sxs-lookup"><span data-stu-id="dc23d-102">Single Sign-On: Event 11018</span></span>
## <a name="details"></a><span data-ttu-id="dc23d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="dc23d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="dc23d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="dc23d-104">Product Name</span></span>   |                                                                                                                              <span data-ttu-id="dc23d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="dc23d-105">Enterprise Single Sign-On</span></span>                                                                                                                              |
| <span data-ttu-id="dc23d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="dc23d-106">Product Version</span></span> |                                                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                              |
|    <span data-ttu-id="dc23d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="dc23d-107">Event ID</span></span>     |                                                                                                                                        <span data-ttu-id="dc23d-108">11018</span><span class="sxs-lookup"><span data-stu-id="dc23d-108">11018</span></span>                                                                                                                                        |
|  <span data-ttu-id="dc23d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="dc23d-109">Event Source</span></span>   |                                                                                                                                       <span data-ttu-id="dc23d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="dc23d-110">ENTSSO</span></span>                                                                                                                                        |
|    <span data-ttu-id="dc23d-111">组件</span><span class="sxs-lookup"><span data-stu-id="dc23d-111">Component</span></span>    |                                                                                                                                         <span data-ttu-id="dc23d-112">不可用</span><span class="sxs-lookup"><span data-stu-id="dc23d-112">N/A</span></span>                                                                                                                                         |
|  <span data-ttu-id="dc23d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="dc23d-113">Symbolic Name</span></span>  |                                                                                                                           <span data-ttu-id="dc23d-114">SSO_PS_WARN_GROUP_CHECK_FAILED</span><span class="sxs-lookup"><span data-stu-id="dc23d-114">SSO_PS_WARN_GROUP_CHECK_FAILED</span></span>                                                                                                                            |
|  <span data-ttu-id="dc23d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="dc23d-115">Message Text</span></span>   | <span data-ttu-id="dc23d-116">无法检查该映射是否是应用程序用户帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="dc23d-116">Failed to check whether the mapping was a member of the Application Users account.</span></span> <span data-ttu-id="dc23d-117">映射将 ignored.%r</span><span class="sxs-lookup"><span data-stu-id="dc23d-117">The mapping will be ignored.%r</span></span><br /><br /> <span data-ttu-id="dc23d-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="dc23d-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="dc23d-119">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="dc23d-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="dc23d-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="dc23d-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="dc23d-121">应用程序用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="dc23d-121">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="dc23d-122">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="dc23d-122">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="dc23d-123">解释</span><span class="sxs-lookup"><span data-stu-id="dc23d-123">Explanation</span></span>  
 <span data-ttu-id="dc23d-124">在 Windows 端已出现未知的错误。</span><span class="sxs-lookup"><span data-stu-id="dc23d-124">An unspecified error has occurred on the Windows side.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc23d-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="dc23d-125">User Action</span></span>  
 <span data-ttu-id="dc23d-126">从警告 （跟踪 ID、 Windows 帐户、 应用程序名称、 应用程序用户和错误代码） 收集信息并与 Microsoft 产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="dc23d-126">Gather the information from the warning (Tracking ID, Windows Account, Application Name, Application Users, and Error Code) and contact Microsoft Product Support Services.</span></span>