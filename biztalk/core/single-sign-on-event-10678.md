---
title: "单一登录： 事件 10678 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6af92ce1-fdac-432f-be6b-cf8958aee776
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daa6639e361abf364e012ec9a4f19f049bbcd08f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10678"></a><span data-ttu-id="05263-102">单一登录： 事件 10678</span><span class="sxs-lookup"><span data-stu-id="05263-102">Single Sign-On: Event 10678</span></span>
## <a name="details"></a><span data-ttu-id="05263-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="05263-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05263-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="05263-104">Product Name</span></span>|<span data-ttu-id="05263-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="05263-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="05263-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="05263-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="05263-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="05263-107">Event ID</span></span>|<span data-ttu-id="05263-108">10678</span><span class="sxs-lookup"><span data-stu-id="05263-108">10678</span></span>|  
|<span data-ttu-id="05263-109">事件源</span><span class="sxs-lookup"><span data-stu-id="05263-109">Event Source</span></span>|<span data-ttu-id="05263-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="05263-110">ENTSSO</span></span>|  
|<span data-ttu-id="05263-111">组件</span><span class="sxs-lookup"><span data-stu-id="05263-111">Component</span></span>|<span data-ttu-id="05263-112">N\A</span><span class="sxs-lookup"><span data-stu-id="05263-112">N\A</span></span>|  
|<span data-ttu-id="05263-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="05263-113">Symbolic Name</span></span>|<span data-ttu-id="05263-114">SSO_WARN_PASSWORD_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="05263-114">SSO_WARN_PASSWORD_MISMATCH</span></span>|  
|<span data-ttu-id="05263-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="05263-115">Message Text</span></span>|<span data-ttu-id="05263-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="05263-116">External password change.</span></span> <span data-ttu-id="05263-117">适配器提供的旧密码与外部帐户的现有密码不匹配。%r</span><span class="sxs-lookup"><span data-stu-id="05263-117">The old password supplied by the adapter does not match the existing password for the external account.%r</span></span><br /><br /> <span data-ttu-id="05263-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="05263-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="05263-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="05263-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="05263-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="05263-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="05263-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="05263-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="05263-122">解释</span><span class="sxs-lookup"><span data-stu-id="05263-122">Explanation</span></span>  
 <span data-ttu-id="05263-123">此警告事件表明适配器提供的旧密码与外部帐户的现有密码不匹配。</span><span class="sxs-lookup"><span data-stu-id="05263-123">This Warning event indicates that the old password supplied by the adapter does not match the existing password for the external account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="05263-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="05263-124">User Action</span></span>  
 <span data-ttu-id="05263-125">要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="05263-125">To resolve this warning do the following:</span></span>  
  
-   <span data-ttu-id="05263-126">确定分配到此适配器（事件日志消息中的名称）的应用程序，然后使用 SSO 管理工具设置此外部帐户的外部凭据。</span><span class="sxs-lookup"><span data-stu-id="05263-126">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="05263-127">必须在所有这些应用程序中设置外部密码（对于给定帐户）。</span><span class="sxs-lookup"><span data-stu-id="05263-127">You must set the external password (for the given account) in all of those Applications.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="05263-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="05263-128">More info</span></span>
  
-   [<span data-ttu-id="05263-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="05263-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="05263-130">**密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="05263-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>