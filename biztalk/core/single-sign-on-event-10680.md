---
title: 单一登录： 事件 10680 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88ea12ff-d181-423f-9054-b0c656cc4558
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ce2871618722af1fce4175be715c8ac1fa55a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974894"
---
# <a name="single-sign-on-event-10680"></a><span data-ttu-id="c6bb5-102">单一登录： 事件 10680</span><span class="sxs-lookup"><span data-stu-id="c6bb5-102">Single Sign-On: Event 10680</span></span>
## <a name="details"></a><span data-ttu-id="c6bb5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c6bb5-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c6bb5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c6bb5-104">Product Name</span></span>   |                                                                                                                                        <span data-ttu-id="c6bb5-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c6bb5-105">Enterprise Single Sign-On</span></span>                                                                                                                                        |
| <span data-ttu-id="c6bb5-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c6bb5-106">Product Version</span></span> |                                                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                        |
|    <span data-ttu-id="c6bb5-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c6bb5-107">Event ID</span></span>     |                                                                                                                                                  <span data-ttu-id="c6bb5-108">10680</span><span class="sxs-lookup"><span data-stu-id="c6bb5-108">10680</span></span>                                                                                                                                                  |
|  <span data-ttu-id="c6bb5-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c6bb5-109">Event Source</span></span>   |                                                                                                                                                 <span data-ttu-id="c6bb5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c6bb5-110">ENTSSO</span></span>                                                                                                                                                  |
|    <span data-ttu-id="c6bb5-111">组件</span><span class="sxs-lookup"><span data-stu-id="c6bb5-111">Component</span></span>    |                                                                                                                                                   <span data-ttu-id="c6bb5-112">N\A</span><span class="sxs-lookup"><span data-stu-id="c6bb5-112">N\A</span></span>                                                                                                                                                   |
|  <span data-ttu-id="c6bb5-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c6bb5-113">Symbolic Name</span></span>  |                                                                                                                                      <span data-ttu-id="c6bb5-114">SSO_WARN_PS_GET_CREDS_FAILED</span><span class="sxs-lookup"><span data-stu-id="c6bb5-114">SSO_WARN_PS_GET_CREDS_FAILED</span></span>                                                                                                                                       |
|  <span data-ttu-id="c6bb5-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c6bb5-115">Message Text</span></span>   | <span data-ttu-id="c6bb5-116">外部帐户的密码未更改，因为无法从 SSO 数据库获取现有的外部凭据。%r</span><span class="sxs-lookup"><span data-stu-id="c6bb5-116">The password was not changed for the external account because the existing external credentials could not be obtained from the SSO database.%r</span></span><br /><br /> <span data-ttu-id="c6bb5-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c6bb5-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="c6bb5-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="c6bb5-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="c6bb5-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="c6bb5-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="c6bb5-120">外部帐户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="c6bb5-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="c6bb5-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="c6bb5-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="c6bb5-122">解释</span><span class="sxs-lookup"><span data-stu-id="c6bb5-122">Explanation</span></span>  
 <span data-ttu-id="c6bb5-123">此警告事件表明，由于无法从 SSO 数据库获得现有外部凭据，因此，未更改外部帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="c6bb5-123">This Warning event indicates that the password was not changed for the external account because the existing external credentials could not be obtained from the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c6bb5-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="c6bb5-124">User Action</span></span>  
 <span data-ttu-id="c6bb5-125">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c6bb5-125">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="c6bb5-126">验证外部凭据。</span><span class="sxs-lookup"><span data-stu-id="c6bb5-126">Verify external credentials.</span></span>  

-   <span data-ttu-id="c6bb5-127">外部凭据无效，请使用 SSO 管理工具为此外部帐户设置外部凭据。</span><span class="sxs-lookup"><span data-stu-id="c6bb5-127">The external credentials are not valid, use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="c6bb5-128">您必须在所有相关的应用程序中为给定的帐户设置外部密码。</span><span class="sxs-lookup"><span data-stu-id="c6bb5-128">You must set the external password (for the given account) in all associated applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="c6bb5-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="c6bb5-129">More info</span></span>

- [<span data-ttu-id="c6bb5-130">密码同步</span><span class="sxs-lookup"><span data-stu-id="c6bb5-130">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="c6bb5-131">**密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c6bb5-131">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
