---
title: 单一登录接口 |Microsoft 文档
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
ms.openlocfilehash: ee479a29a424228b31bc3fcd5752f8da7cc3ce28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276789"
---
# <a name="single-sign-on-interface"></a><span data-ttu-id="b491f-102">单一登录接口</span><span class="sxs-lookup"><span data-stu-id="b491f-102">Single Sign-On Interface</span></span>

## <a name="interfaces"></a><span data-ttu-id="b491f-103">界面</span><span class="sxs-lookup"><span data-stu-id="b491f-103">Interfaces</span></span>
<span data-ttu-id="b491f-104">下表说明了构成单一登录接口的 COM 接口和 .NET Framework 接口。</span><span class="sxs-lookup"><span data-stu-id="b491f-104">The following table describes the COM and .NET Framework interfaces that make up the Single Sign-On interface.</span></span>  
  
|<span data-ttu-id="b491f-105">.NET</span><span class="sxs-lookup"><span data-stu-id="b491f-105">.NET</span></span>|<span data-ttu-id="b491f-106">COM</span><span class="sxs-lookup"><span data-stu-id="b491f-106">COM</span></span>|<span data-ttu-id="b491f-107">Description</span><span class="sxs-lookup"><span data-stu-id="b491f-107">Description</span></span>|  
|----------|---------|-----------------|  
|<span data-ttu-id="b491f-108">Microsoft.EnterpriseSingleSignOn.Interop.ISSOAdmin</span><span class="sxs-lookup"><span data-stu-id="b491f-108">Microsoft.EnterpriseSingleSignOn.Interop.ISSOAdmin</span></span>|<span data-ttu-id="b491f-109">ISSOAdmin 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-109">ISSOAdmin Interface (COM)</span></span>|<span data-ttu-id="b491f-110">创建、更新和删除 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b491f-110">Creates, updates, and deletes an SSO application.</span></span> <span data-ttu-id="b491f-111">还执行其他管理功能。</span><span class="sxs-lookup"><span data-stu-id="b491f-111">Also performs other administration functions.</span></span>|  
|<span data-ttu-id="b491f-112">Microsoft.EnterpriseSingleSignOn.Interop.ISSOConfigStore</span><span class="sxs-lookup"><span data-stu-id="b491f-112">Microsoft.EnterpriseSingleSignOn.Interop.ISSOConfigStore</span></span>|<span data-ttu-id="b491f-113">ISSOConfigStore 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-113">ISSOConfigStore Interface (COM)</span></span>|<span data-ttu-id="b491f-114">获取和设置 SSO 配置存储中的信息。</span><span class="sxs-lookup"><span data-stu-id="b491f-114">Gets and sets information in the SSO configuration store.</span></span>|  
|<span data-ttu-id="b491f-115">Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup1</span><span class="sxs-lookup"><span data-stu-id="b491f-115">Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup1</span></span>|<span data-ttu-id="b491f-116">ISSOLookup1 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-116">ISSOLookup1 Interface (COM)</span></span>|<span data-ttu-id="b491f-117">允许您查找当前用户对指定应用程序的外部凭据。</span><span class="sxs-lookup"><span data-stu-id="b491f-117">Enables you to look up the external credentials on a specified application for the current user.</span></span>|  
|<span data-ttu-id="b491f-118">Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup2</span><span class="sxs-lookup"><span data-stu-id="b491f-118">Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup2</span></span>|<span data-ttu-id="b491f-119">ISSOLookup2 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-119">ISSOLookup2 Interface (COM)</span></span>|<span data-ttu-id="b491f-120">同上，但您还可查找指定外部用户的 Windows 凭据。</span><span class="sxs-lookup"><span data-stu-id="b491f-120">As above, but also enables you to look up the Windows credentials for a specified external user.</span></span>|  
|<span data-ttu-id="b491f-121">Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapper</span><span class="sxs-lookup"><span data-stu-id="b491f-121">Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapper</span></span>|<span data-ttu-id="b491f-122">ISSOMapper 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-122">ISSOMapper Interface (COM)</span></span>|<span data-ttu-id="b491f-123">允许您设置当前用户对指定应用程序的外部凭据。</span><span class="sxs-lookup"><span data-stu-id="b491f-123">Enables you to set the external credentials for the current user for a specified application.</span></span>|  
|<span data-ttu-id="b491f-124">Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapping</span><span class="sxs-lookup"><span data-stu-id="b491f-124">Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapping</span></span>|<span data-ttu-id="b491f-125">ISSOMapping 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-125">ISSOMapping Interface (COM)</span></span>|<span data-ttu-id="b491f-126">创建并维护用户与关联应用程序之间的映射。</span><span class="sxs-lookup"><span data-stu-id="b491f-126">Creates and maintains the mapping between users and affiliated applications.</span></span>|  
|<span data-ttu-id="b491f-127">Microsoft.EnterpriseSingleSignOn.Interop.ISSOTicket</span><span class="sxs-lookup"><span data-stu-id="b491f-127">Microsoft.EnterpriseSingleSignOn.Interop.ISSOTicket</span></span>|<span data-ttu-id="b491f-128">ISSOTicket 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-128">ISSOTicket Interface (COM)</span></span>|<span data-ttu-id="b491f-129">创建包含相应安全信息的票证。</span><span class="sxs-lookup"><span data-stu-id="b491f-129">Creates the ticket that contains the appropriate security information.</span></span> <span data-ttu-id="b491f-130">此票证随后与应用程序中的相应消息一起发送。</span><span class="sxs-lookup"><span data-stu-id="b491f-130">This ticket is then sent on with the appropriate message from your application.</span></span>|  


## <a name="password-sync-helper"></a><span data-ttu-id="b491f-131">密码同步助手</span><span class="sxs-lookup"><span data-stu-id="b491f-131">Password Sync Helper</span></span>  
 <span data-ttu-id="b491f-132">此外，Host Integration Server 还支持密码同步助手（PS 助手）组件。</span><span class="sxs-lookup"><span data-stu-id="b491f-132">In addition, Host Integration Server supports the Password Sync Helper (PS Helper) component.</span></span> <span data-ttu-id="b491f-133">设计密码同步组件时可使用 PS 助手。</span><span class="sxs-lookup"><span data-stu-id="b491f-133">You can use PS Helper when you design password synchronization components.</span></span> <span data-ttu-id="b491f-134">下表说明了 PS 助手公开的 COM 和 .NET Framework 接口。</span><span class="sxs-lookup"><span data-stu-id="b491f-134">The following table describes the COM and .NET Framework interfaces exposed by PS Helper.</span></span>  
  
|<span data-ttu-id="b491f-135">.NET</span><span class="sxs-lookup"><span data-stu-id="b491f-135">.NET</span></span>|<span data-ttu-id="b491f-136">COM</span><span class="sxs-lookup"><span data-stu-id="b491f-136">COM</span></span>|<span data-ttu-id="b491f-137">Description</span><span class="sxs-lookup"><span data-stu-id="b491f-137">Description</span></span>|  
|----------|---------|-----------------|  
|<span data-ttu-id="b491f-138">Microsoft.EnterpriseSingleSignOn.Interop.ISSOPSWrapper</span><span class="sxs-lookup"><span data-stu-id="b491f-138">Microsoft.EnterpriseSingleSignOn.Interop.ISSOPSWrapper</span></span>|<span data-ttu-id="b491f-139">ISSONotification 接口 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-139">ISSONotification Interface (COM)</span></span>|<span data-ttu-id="b491f-140">处理与非 Windows 操作系统之间的密码更改。</span><span class="sxs-lookup"><span data-stu-id="b491f-140">Handles password changes to and from non-Windows operating systems.</span></span>|  
||<span data-ttu-id="b491f-141">SExternalAccount 结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-141">SExternalAccount Structure (COM)</span></span>|<span data-ttu-id="b491f-142">描述外部帐户。</span><span class="sxs-lookup"><span data-stu-id="b491f-142">Describes an external account.</span></span>|  
||<span data-ttu-id="b491f-143">SPasswordChange 结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-143">SPasswordChange Structure (COM)</span></span>|<span data-ttu-id="b491f-144">描述密码更改。</span><span class="sxs-lookup"><span data-stu-id="b491f-144">Describes a password change.</span></span>|  
||<span data-ttu-id="b491f-145">SPasswordChangeComplete 结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-145">SPasswordChangeComplete Structure (COM)</span></span>|<span data-ttu-id="b491f-146">描述密码更改的完成过程。</span><span class="sxs-lookup"><span data-stu-id="b491f-146">Describes the completion of a password change.</span></span>|  
||<span data-ttu-id="b491f-147">状态结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-147">SStatus Structure (COM)</span></span>|<span data-ttu-id="b491f-148">描述错误或事件。</span><span class="sxs-lookup"><span data-stu-id="b491f-148">Describes an error or event.</span></span>|  
||<span data-ttu-id="b491f-149">SAdapterInGroup 结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-149">SAdapterInGroup Structure (COM)</span></span>|<span data-ttu-id="b491f-150">描述给定组中的适配器。</span><span class="sxs-lookup"><span data-stu-id="b491f-150">Describes the adapters in a given group.</span></span>|  
||<span data-ttu-id="b491f-151">SAdapter 结构 (COM)</span><span class="sxs-lookup"><span data-stu-id="b491f-151">SAdapter Structure (COM)</span></span>|<span data-ttu-id="b491f-152">描述特定的适配器。</span><span class="sxs-lookup"><span data-stu-id="b491f-152">Describes a specific adapter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="b491f-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b491f-153">See also</span></span>
<span data-ttu-id="b491f-154">请参阅 SSO COM 对象[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="b491f-154">See the SSO COM objects [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 