---
title: 单一登录： 事件 10742 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba62f878-ed12-421f-81ea-9285b2624fe9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43595ad7a6817bd63e200a80ea90e23bd0245ceb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012990"
---
# <a name="single-sign-on-event-10742"></a><span data-ttu-id="8e990-102">单一登录： 事件 10742</span><span class="sxs-lookup"><span data-stu-id="8e990-102">Single Sign-On: Event 10742</span></span>
## <a name="details"></a><span data-ttu-id="8e990-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8e990-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8e990-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8e990-104">Product Name</span></span>   |                                                                                                                                         <span data-ttu-id="8e990-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8e990-105">Enterprise Single Sign-On</span></span>                                                                                                                                          |
| <span data-ttu-id="8e990-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8e990-106">Product Version</span></span> |                                                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                         |
|    <span data-ttu-id="8e990-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8e990-107">Event ID</span></span>     |                                                                                                                                                   <span data-ttu-id="8e990-108">10742</span><span class="sxs-lookup"><span data-stu-id="8e990-108">10742</span></span>                                                                                                                                                    |
|  <span data-ttu-id="8e990-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8e990-109">Event Source</span></span>   |                                                                                                                                                   <span data-ttu-id="8e990-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8e990-110">ENTSSO</span></span>                                                                                                                                                   |
|    <span data-ttu-id="8e990-111">组件</span><span class="sxs-lookup"><span data-stu-id="8e990-111">Component</span></span>    |                                                                                                                                                    <span data-ttu-id="8e990-112">N\A</span><span class="sxs-lookup"><span data-stu-id="8e990-112">N\A</span></span>                                                                                                                                                     |
|  <span data-ttu-id="8e990-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8e990-113">Symbolic Name</span></span>  |                                                                                                                                         <span data-ttu-id="8e990-114">SSO_WARN_NO_UPDATE_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="8e990-114">SSO_WARN_NO_UPDATE_ADAPTER</span></span>                                                                                                                                         |
|  <span data-ttu-id="8e990-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8e990-115">Message Text</span></span>   | <span data-ttu-id="8e990-116">若要更新适配器，客户端用户必须是 SSO 管理员帐户或应用程序管理员帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="8e990-116">The client user must be a member of the SSO Administrators account or the Application Administrators account to update the adapter.%r</span></span><br /><br /> <span data-ttu-id="8e990-117">客户端用户: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8e990-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="8e990-118">SSO Administrators: %2 %r</span><span class="sxs-lookup"><span data-stu-id="8e990-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="8e990-119">应用程序管理员: %3 %r</span><span class="sxs-lookup"><span data-stu-id="8e990-119">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="8e990-120">适配器: %4 %r</span><span class="sxs-lookup"><span data-stu-id="8e990-120">Adapter: %4%r</span></span><br /><br /> <span data-ttu-id="8e990-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="8e990-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="8e990-122">解释</span><span class="sxs-lookup"><span data-stu-id="8e990-122">Explanation</span></span>  
 <span data-ttu-id="8e990-123">此警告事件表示进行了更新指定适配器的尝试，但是无法完成，因为所使用的用户帐户不是 SSO 管理员帐户或应用程序管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="8e990-123">This Warning event indicates that an attempt to update the specified adapter was made, but could not be completed because the user account used is not a member of the SSO Administrators account or the Application Administrators account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="8e990-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="8e990-124">User Action</span></span>  
 <span data-ttu-id="8e990-125">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="8e990-125">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="8e990-126">将用户帐户添加到 SSO 管理员帐户或应用程序管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="8e990-126">Add user account to the SSO Administrators account or the Application Administrators account.</span></span>  

- <span data-ttu-id="8e990-127">重试更新。</span><span class="sxs-lookup"><span data-stu-id="8e990-127">Retry update.</span></span>  

  <span data-ttu-id="8e990-128">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="8e990-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="8e990-129">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="8e990-129">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
