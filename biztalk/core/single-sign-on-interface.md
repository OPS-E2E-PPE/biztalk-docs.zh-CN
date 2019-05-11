---
title: 单一登录接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2e3c2d3-a7e9-4a45-965d-bfe4bf200c34
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be71b6be0baa733748552f59067b0b3678bed4af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247293"
---
# <a name="single-sign-on-interface"></a><span data-ttu-id="4fc98-102">单一登录接口</span><span class="sxs-lookup"><span data-stu-id="4fc98-102">Single Sign-On Interface</span></span>

## <a name="interfaces"></a><span data-ttu-id="4fc98-103">界面</span><span class="sxs-lookup"><span data-stu-id="4fc98-103">Interfaces</span></span>
<span data-ttu-id="4fc98-104">下表介绍了构成单一登录接口的 COM 和.NET Framework 接口。</span><span class="sxs-lookup"><span data-stu-id="4fc98-104">The following table describes the COM and .NET Framework interfaces that make up the Single Sign-On interface.</span></span>  
  
|<span data-ttu-id="4fc98-105">.NET</span><span class="sxs-lookup"><span data-stu-id="4fc98-105">.NET</span></span>|<span data-ttu-id="4fc98-106">COM</span><span class="sxs-lookup"><span data-stu-id="4fc98-106">COM</span></span>|<span data-ttu-id="4fc98-107">Description</span><span class="sxs-lookup"><span data-stu-id="4fc98-107">Description</span></span>|  
|----------|---------|-----------------|  
|<span data-ttu-id="4fc98-108">Microsoft.EnterpriseSingleSignOn.Interop.ISSOAdmin</span><span class="sxs-lookup"><span data-stu-id="4fc98-108">Microsoft.EnterpriseSingleSignOn.Interop.ISSOAdmin</span></span>|<span data-ttu-id="4fc98-109">ISSOAdmin 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-109">ISSOAdmin Interface (COM)</span></span>|<span data-ttu-id="4fc98-110">创建、 更新和删除 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4fc98-110">Creates, updates, and deletes an SSO application.</span></span> <span data-ttu-id="4fc98-111">此外执行其他管理功能。</span><span class="sxs-lookup"><span data-stu-id="4fc98-111">Also performs other administration functions.</span></span>|  
|<span data-ttu-id="4fc98-112">Microsoft.EnterpriseSingleSignOn.Interop.ISSOConfigStore</span><span class="sxs-lookup"><span data-stu-id="4fc98-112">Microsoft.EnterpriseSingleSignOn.Interop.ISSOConfigStore</span></span>|<span data-ttu-id="4fc98-113">ISSOConfigStore 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-113">ISSOConfigStore Interface (COM)</span></span>|<span data-ttu-id="4fc98-114">获取和设置 SSO 配置存储区中的信息。</span><span class="sxs-lookup"><span data-stu-id="4fc98-114">Gets and sets information in the SSO configuration store.</span></span>|  
|<span data-ttu-id="4fc98-115">Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup1</span><span class="sxs-lookup"><span data-stu-id="4fc98-115">Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup1</span></span>|<span data-ttu-id="4fc98-116">ISSOLookup1 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-116">ISSOLookup1 Interface (COM)</span></span>|<span data-ttu-id="4fc98-117">使您能够查找当前用户对指定应用程序的外部凭据。</span><span class="sxs-lookup"><span data-stu-id="4fc98-117">Enables you to look up the external credentials on a specified application for the current user.</span></span>|  
|<span data-ttu-id="4fc98-118">Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup2</span><span class="sxs-lookup"><span data-stu-id="4fc98-118">Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup2</span></span>|<span data-ttu-id="4fc98-119">ISSOLookup2 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-119">ISSOLookup2 Interface (COM)</span></span>|<span data-ttu-id="4fc98-120">如上所示，而且还使您能够查找指定外部用户的 Windows 凭据。</span><span class="sxs-lookup"><span data-stu-id="4fc98-120">As above, but also enables you to look up the Windows credentials for a specified external user.</span></span>|  
|<span data-ttu-id="4fc98-121">Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapper</span><span class="sxs-lookup"><span data-stu-id="4fc98-121">Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapper</span></span>|<span data-ttu-id="4fc98-122">ISSOMapper 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-122">ISSOMapper Interface (COM)</span></span>|<span data-ttu-id="4fc98-123">可以为指定的应用程序的当前用户设置外部凭据。</span><span class="sxs-lookup"><span data-stu-id="4fc98-123">Enables you to set the external credentials for the current user for a specified application.</span></span>|  
|<span data-ttu-id="4fc98-124">Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapping</span><span class="sxs-lookup"><span data-stu-id="4fc98-124">Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapping</span></span>|<span data-ttu-id="4fc98-125">ISSOMapping 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-125">ISSOMapping Interface (COM)</span></span>|<span data-ttu-id="4fc98-126">创建并维护用户与关联应用程序之间的映射。</span><span class="sxs-lookup"><span data-stu-id="4fc98-126">Creates and maintains the mapping between users and affiliated applications.</span></span>|  
|<span data-ttu-id="4fc98-127">Microsoft.EnterpriseSingleSignOn.Interop.ISSOTicket</span><span class="sxs-lookup"><span data-stu-id="4fc98-127">Microsoft.EnterpriseSingleSignOn.Interop.ISSOTicket</span></span>|<span data-ttu-id="4fc98-128">ISSOTicket 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-128">ISSOTicket Interface (COM)</span></span>|<span data-ttu-id="4fc98-129">创建包含相应的安全信息的票证。</span><span class="sxs-lookup"><span data-stu-id="4fc98-129">Creates the ticket that contains the appropriate security information.</span></span> <span data-ttu-id="4fc98-130">此票证然后发送的相应消息一起从你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4fc98-130">This ticket is then sent on with the appropriate message from your application.</span></span>|  


## <a name="password-sync-helper"></a><span data-ttu-id="4fc98-131">密码同步助手</span><span class="sxs-lookup"><span data-stu-id="4fc98-131">Password Sync Helper</span></span>  
 <span data-ttu-id="4fc98-132">此外，Host Integration Server 还支持密码同步助手 （PS 助手） 组件。</span><span class="sxs-lookup"><span data-stu-id="4fc98-132">In addition, Host Integration Server supports the Password Sync Helper (PS Helper) component.</span></span> <span data-ttu-id="4fc98-133">设计密码同步组件时，可以使用 PS 助手。</span><span class="sxs-lookup"><span data-stu-id="4fc98-133">You can use PS Helper when you design password synchronization components.</span></span> <span data-ttu-id="4fc98-134">下表描述了 PS 助手公开的 COM 和.NET Framework 接口。</span><span class="sxs-lookup"><span data-stu-id="4fc98-134">The following table describes the COM and .NET Framework interfaces exposed by PS Helper.</span></span>  
  
|<span data-ttu-id="4fc98-135">.NET</span><span class="sxs-lookup"><span data-stu-id="4fc98-135">.NET</span></span>|<span data-ttu-id="4fc98-136">COM</span><span class="sxs-lookup"><span data-stu-id="4fc98-136">COM</span></span>|<span data-ttu-id="4fc98-137">Description</span><span class="sxs-lookup"><span data-stu-id="4fc98-137">Description</span></span>|  
|----------|---------|-----------------|  
|<span data-ttu-id="4fc98-138">Microsoft.EnterpriseSingleSignOn.Interop.ISSOPSWrapper</span><span class="sxs-lookup"><span data-stu-id="4fc98-138">Microsoft.EnterpriseSingleSignOn.Interop.ISSOPSWrapper</span></span>|<span data-ttu-id="4fc98-139">ISSONotification 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-139">ISSONotification Interface (COM)</span></span>|<span data-ttu-id="4fc98-140">处理从非 Windows 操作系统中的密码更改。</span><span class="sxs-lookup"><span data-stu-id="4fc98-140">Handles password changes to and from non-Windows operating systems.</span></span>|  
||<span data-ttu-id="4fc98-141">SExternalAccount 结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-141">SExternalAccount Structure (COM)</span></span>|<span data-ttu-id="4fc98-142">描述外部帐户。</span><span class="sxs-lookup"><span data-stu-id="4fc98-142">Describes an external account.</span></span>|  
||<span data-ttu-id="4fc98-143">SPasswordChange 结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-143">SPasswordChange Structure (COM)</span></span>|<span data-ttu-id="4fc98-144">描述密码更改。</span><span class="sxs-lookup"><span data-stu-id="4fc98-144">Describes a password change.</span></span>|  
||<span data-ttu-id="4fc98-145">SPasswordChangeComplete 结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-145">SPasswordChangeComplete Structure (COM)</span></span>|<span data-ttu-id="4fc98-146">描述密码更改的完成。</span><span class="sxs-lookup"><span data-stu-id="4fc98-146">Describes the completion of a password change.</span></span>|  
||<span data-ttu-id="4fc98-147">SStatus 结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-147">SStatus Structure (COM)</span></span>|<span data-ttu-id="4fc98-148">描述错误或事件。</span><span class="sxs-lookup"><span data-stu-id="4fc98-148">Describes an error or event.</span></span>|  
||<span data-ttu-id="4fc98-149">SAdapterInGroup 结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-149">SAdapterInGroup Structure (COM)</span></span>|<span data-ttu-id="4fc98-150">描述给定组中的适配器。</span><span class="sxs-lookup"><span data-stu-id="4fc98-150">Describes the adapters in a given group.</span></span>|  
||<span data-ttu-id="4fc98-151">SAdapter 结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="4fc98-151">SAdapter Structure (COM)</span></span>|<span data-ttu-id="4fc98-152">描述特定的适配器。</span><span class="sxs-lookup"><span data-stu-id="4fc98-152">Describes a specific adapter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="4fc98-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fc98-153">See also</span></span>
<span data-ttu-id="4fc98-154">请参阅 SSO COM 对象[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="4fc98-154">See the SSO COM objects [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 