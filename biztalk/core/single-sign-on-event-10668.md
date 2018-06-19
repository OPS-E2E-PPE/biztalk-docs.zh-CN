---
title: 单一登录： 事件 10668 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eb3dd4d-04b5-4713-93c1-76af012d6920
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 006855842ea2d789290200d5c5a9692b6e046e8a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271437"
---
# <a name="single-sign-on-event-10668"></a><span data-ttu-id="ccd84-102">单一登录： 事件 10668</span><span class="sxs-lookup"><span data-stu-id="ccd84-102">Single Sign-On: Event 10668</span></span>
## <a name="details"></a><span data-ttu-id="ccd84-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ccd84-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ccd84-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ccd84-104">Product Name</span></span>|<span data-ttu-id="ccd84-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ccd84-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ccd84-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ccd84-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ccd84-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ccd84-107">Event ID</span></span>|<span data-ttu-id="ccd84-108">10668</span><span class="sxs-lookup"><span data-stu-id="ccd84-108">10668</span></span>|  
|<span data-ttu-id="ccd84-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ccd84-109">Event Source</span></span>|<span data-ttu-id="ccd84-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ccd84-110">ENTSSO</span></span>|  
|<span data-ttu-id="ccd84-111">组件</span><span class="sxs-lookup"><span data-stu-id="ccd84-111">Component</span></span>|<span data-ttu-id="ccd84-112">N\A</span><span class="sxs-lookup"><span data-stu-id="ccd84-112">N\A</span></span>|  
|<span data-ttu-id="ccd84-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ccd84-113">Symbolic Name</span></span>|<span data-ttu-id="ccd84-114">SSO_WARN_NO_OLD_WINDOWS_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="ccd84-114">SSO_WARN_NO_OLD_WINDOWS_PASSWORD</span></span>|  
|<span data-ttu-id="ccd84-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ccd84-115">Message Text</span></span>|<span data-ttu-id="ccd84-116">不能更改 Windows 密码，因为此帐户的旧 Windows 密码不在 SSO 数据库中。%r</span><span class="sxs-lookup"><span data-stu-id="ccd84-116">Cannot change the Windows password because the old Windows password for this account is not available in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="ccd84-117">请使用 SSO 管理工具为此 Windows 帐户设置外部凭据。%r</span><span class="sxs-lookup"><span data-stu-id="ccd84-117">Use the SSO administration tools to set the external credentials for this Windows account.%r</span></span><br /><br /> <span data-ttu-id="ccd84-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ccd84-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="ccd84-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ccd84-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="ccd84-120">Windows 帐户： %3</span><span class="sxs-lookup"><span data-stu-id="ccd84-120">Windows Account: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ccd84-121">解释</span><span class="sxs-lookup"><span data-stu-id="ccd84-121">Explanation</span></span>  
 <span data-ttu-id="ccd84-122">此警告事件表示密码同步不能更改 Windows 密码，因为此帐户的旧 Windows 密码不在 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="ccd84-122">This Warning event indicates that Password Sync cannot change the Windows password because the old Windows password for this account is not available in the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ccd84-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="ccd84-123">User Action</span></span>  
 <span data-ttu-id="ccd84-124">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ccd84-124">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="ccd84-125">确定哪些应用程序被分配到了此适配器（事件日志消息中的名称），然后使用 SSO 管理工具来为此 Windows 帐户设置外部凭据。</span><span class="sxs-lookup"><span data-stu-id="ccd84-125">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this Windows account.</span></span> <span data-ttu-id="ccd84-126">必须在全部应用程序中为给定的 Windows 帐户设置外部密码。</span><span class="sxs-lookup"><span data-stu-id="ccd84-126">You must set the external password (for the given Windows Account) in all of those Applications.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="ccd84-127">详细信息</span><span class="sxs-lookup"><span data-stu-id="ccd84-127">More info</span></span>
  
-   [<span data-ttu-id="ccd84-128">密码同步</span><span class="sxs-lookup"><span data-stu-id="ccd84-128">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="ccd84-129">**密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="ccd84-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>