---
title: 如何更改单一登录接口的行为 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4a4946a-e345-4c7e-835d-a3f7f72ebaca
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 729b5faee2e6adff6e43a987b1defcb90450eb13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387067"
---
# <a name="how-to-change-the-behavior-of-a-single-sign-on-interface"></a><span data-ttu-id="95868-102">如何更改单一登录接口的行为</span><span class="sxs-lookup"><span data-stu-id="95868-102">How to Change the Behavior of a Single Sign-On Interface</span></span>
<span data-ttu-id="95868-103">许多企业单一登录 (SSO) 对象模型中的对象会公开 IPropertyBag 接口，允许您修改指定的对象的行为。</span><span class="sxs-lookup"><span data-stu-id="95868-103">Many of the objects in the Enterprise Single Sign-On (SSO) object model expose the IPropertyBag interface, which allows you to modify the behavior of the specified object.</span></span> <span data-ttu-id="95868-104">如果对 SSO 对象调用 QueryInterface，可以检索 IPropertyBag 接口，并使用它来更改当前对象的行为。</span><span class="sxs-lookup"><span data-stu-id="95868-104">If you call QueryInterface on an SSO object, you can retrieve the IPropertyBag interface and use it to change the behavior of your current object.</span></span>  

### <a name="to-change-the-behavior-for-a-specified-sso-interface"></a><span data-ttu-id="95868-105">若要更改指定 SSO 接口的行为</span><span class="sxs-lookup"><span data-stu-id="95868-105">To change the behavior for a specified SSO interface</span></span>  

1.  <span data-ttu-id="95868-106">使用指定的接口上 QueryInterface 来检索 IPropertyBag 实例。</span><span class="sxs-lookup"><span data-stu-id="95868-106">Use QueryInterface on the specified interface to retrieve an IPropertyBag instance.</span></span>  

2.  <span data-ttu-id="95868-107">使用 IPropertyBag.Write 设置属性、 类型和接口的值。</span><span class="sxs-lookup"><span data-stu-id="95868-107">Use IPropertyBag.Write to set the property, type, and value for the interface.</span></span>  

     <span data-ttu-id="95868-108">下表介绍了 IPropertyBag propName 和 ptrVar 参数的有效值。</span><span class="sxs-lookup"><span data-stu-id="95868-108">The following table describes the valid values for the IPropertyBag propName and ptrVar parameters.</span></span>  

|<span data-ttu-id="95868-109">propName</span><span class="sxs-lookup"><span data-stu-id="95868-109">propName</span></span>|<span data-ttu-id="95868-110">类型</span><span class="sxs-lookup"><span data-stu-id="95868-110">Type</span></span>|<span data-ttu-id="95868-111">ptrValue</span><span class="sxs-lookup"><span data-stu-id="95868-111">ptrValue</span></span>|<span data-ttu-id="95868-112">上可用</span><span class="sxs-lookup"><span data-stu-id="95868-112">Usable On</span></span>|  
|--------------|----------|--------------|---------------|  
|<span data-ttu-id="95868-113">CurrentSSOServer</span><span class="sxs-lookup"><span data-stu-id="95868-113">CurrentSSOServer</span></span>|<span data-ttu-id="95868-114">VT_BSTR</span><span class="sxs-lookup"><span data-stu-id="95868-114">VT_BSTR</span></span>|<span data-ttu-id="95868-115">若要将信息发送到的服务器的名称</span><span class="sxs-lookup"><span data-stu-id="95868-115">Name of the server to send the information to</span></span>|<span data-ttu-id="95868-116">All</span><span class="sxs-lookup"><span data-stu-id="95868-116">All</span></span>|  
|<span data-ttu-id="95868-117">事务</span><span class="sxs-lookup"><span data-stu-id="95868-117">Transaction</span></span>|<span data-ttu-id="95868-118">VT_UNKNOWN</span><span class="sxs-lookup"><span data-stu-id="95868-118">VT_UNKNOWN</span></span><br /><br /> <span data-ttu-id="95868-119">VT_EMPTY</span><span class="sxs-lookup"><span data-stu-id="95868-119">VT_EMPTY</span></span>|<span data-ttu-id="95868-120">一个 DTC ITransaction 指针，或者为 NULL 以清除作用域。</span><span class="sxs-lookup"><span data-stu-id="95868-120">A DTC ITransaction pointer, or NULL to clear the scope.</span></span>|<span data-ttu-id="95868-121">ISSOConfigStore::SetConfigInfo</span><span class="sxs-lookup"><span data-stu-id="95868-121">ISSOConfigStore::SetConfigInfo</span></span><br /><span data-ttu-id="95868-122">ISSOConfigStore::GetConfigInfo</span><span class="sxs-lookup"><span data-stu-id="95868-122">ISSOConfigStore::GetConfigInfo</span></span> <br /><span data-ttu-id="95868-123">ISSOConfigStore::DeleteConfigInfo</span><span class="sxs-lookup"><span data-stu-id="95868-123">ISSOConfigStore::DeleteConfigInfo</span></span><br /><br /> <span data-ttu-id="95868-124">ISSOAdmin::CreateApplication</span><span class="sxs-lookup"><span data-stu-id="95868-124">ISSOAdmin::CreateApplication</span></span><br /><span data-ttu-id="95868-125">ISSOAdmin::DeleteApplication</span><span class="sxs-lookup"><span data-stu-id="95868-125">ISSOAdmin::DeleteApplication</span></span> <br /><span data-ttu-id="95868-126">ISSOAdmin::UpdateApplication</span><span class="sxs-lookup"><span data-stu-id="95868-126">ISSOAdmin::UpdateApplication</span></span><br /><span data-ttu-id="95868-127">ISSOAdmin::CreateFieldInfo</span><span class="sxs-lookup"><span data-stu-id="95868-127">ISSOAdmin::CreateFieldInfo</span></span><br /><br /> <span data-ttu-id="95868-128">ISSOMapper::GetFieldInfo</span><span class="sxs-lookup"><span data-stu-id="95868-128">ISSOMapper::GetFieldInfo</span></span>|  
|<span data-ttu-id="95868-129">AppFilterFlags</span><span class="sxs-lookup"><span data-stu-id="95868-129">AppFilterFlags</span></span>|<span data-ttu-id="95868-130">VT_I4</span><span class="sxs-lookup"><span data-stu-id="95868-130">VT_I4</span></span><br /><br /> <span data-ttu-id="95868-131">VT_UI4</span><span class="sxs-lookup"><span data-stu-id="95868-131">VT_UI4</span></span>|<span data-ttu-id="95868-132">若要控制要筛选的应用程序的标志。</span><span class="sxs-lookup"><span data-stu-id="95868-132">Flags to control what application to filter.</span></span>|<span data-ttu-id="95868-133">ISSOMapper::GetApplications</span><span class="sxs-lookup"><span data-stu-id="95868-133">ISSOMapper::GetApplications</span></span><br /><br /> <span data-ttu-id="95868-134">ISSOMapper2::GetApplications2</span><span class="sxs-lookup"><span data-stu-id="95868-134">ISSOMapper2::GetApplications2</span></span>|  
|<span data-ttu-id="95868-135">AppFilterFlagsMask</span><span class="sxs-lookup"><span data-stu-id="95868-135">AppFilterFlagsMask</span></span>|<span data-ttu-id="95868-136">VT_I4</span><span class="sxs-lookup"><span data-stu-id="95868-136">VT_I4</span></span><br /><br /> <span data-ttu-id="95868-137">VT_UI4</span><span class="sxs-lookup"><span data-stu-id="95868-137">VT_UI4</span></span>|<span data-ttu-id="95868-138">若要控制要筛选的应用程序的标志掩码。</span><span class="sxs-lookup"><span data-stu-id="95868-138">Flag mask to control what application to filter.</span></span>|<span data-ttu-id="95868-139">ISSOMapper::GetApplications</span><span class="sxs-lookup"><span data-stu-id="95868-139">ISSOMapper::GetApplications</span></span><br /><br /> <span data-ttu-id="95868-140">ISSOMapper2::GetApplications2</span><span class="sxs-lookup"><span data-stu-id="95868-140">ISSOMapper2::GetApplications2</span></span>|  
|<span data-ttu-id="95868-141">AsyncCall</span><span class="sxs-lookup"><span data-stu-id="95868-141">AsyncCall</span></span>|<span data-ttu-id="95868-142">VT_BOOL</span><span class="sxs-lookup"><span data-stu-id="95868-142">VT_BOOL</span></span>|<span data-ttu-id="95868-143">为 true，则使用异步 RPC;为 false，则使用同步 RPC。</span><span class="sxs-lookup"><span data-stu-id="95868-143">True to call using an async RPC; false to use a synchronous RPC.</span></span>|<span data-ttu-id="95868-144">ISSOConfigOM::GetServerStatus</span><span class="sxs-lookup"><span data-stu-id="95868-144">ISSOConfigOM::GetServerStatus</span></span><br /><br /> <span data-ttu-id="95868-145">ISSOAdmin::GetGlobalInfo</span><span class="sxs-lookup"><span data-stu-id="95868-145">ISSOAdmin::GetGlobalInfo</span></span>|  

- <span data-ttu-id="95868-146">**CurrentSSOServer**： 用于确定哪个服务器将发送到的 SSO 信息按如下所示的标准行为：</span><span class="sxs-lookup"><span data-stu-id="95868-146">**CurrentSSOServer**: the standard behavior for determining which server to send SSO information to is as follows:</span></span>  

  1. <span data-ttu-id="95868-147">在当前用户的注册表中查找。</span><span class="sxs-lookup"><span data-stu-id="95868-147">Look in the registry for the current user.</span></span> <span data-ttu-id="95868-148">可以使用 GUI 或命令行工具的当前用户设置的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="95868-148">The server name can be set for the current user using the command line tools or GUI.</span></span>  

  2. <span data-ttu-id="95868-149">查看注册表中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="95868-149">Look in the registry for all users.</span></span> <span data-ttu-id="95868-150">可以使用命令行工具或 GUI 的所有用户设置的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="95868-150">The server name can be set for all users using the command line tools or GUI.</span></span>  

  3. <span data-ttu-id="95868-151">如果在注册表中不找到任何 SSO 服务器名称，则使用当前计算机。</span><span class="sxs-lookup"><span data-stu-id="95868-151">If no SSO server name is found in the registry then use the current computer.</span></span>  

     <span data-ttu-id="95868-152">将 CurrentSSOServer 设置为指定的服务器将覆盖指定接口的上一过程。</span><span class="sxs-lookup"><span data-stu-id="95868-152">Setting CurrentSSOServer to a specified server overrides the previous process for the specified interface.</span></span> <span data-ttu-id="95868-153">设置 CurrentSSOServer 后，在接口上的所有后续方法调用将发送到指定的服务器。</span><span class="sxs-lookup"><span data-stu-id="95868-153">Once you set CurrentSSOServer, all subsequent method calls on the interface will be sent to the specified server.</span></span>  

- <span data-ttu-id="95868-154">**事务**： 指定的 DTC 事务的作用域执行的操作由 SSO 对象模型。</span><span class="sxs-lookup"><span data-stu-id="95868-154">**Transaction**: specifies a DTC transaction that to scope the operations performed by the SSO object model.</span></span> <span data-ttu-id="95868-155">必须传递一个 DTC ITransaction 指针中的`ptrValue`，或"null"以清除当前事务作用域。</span><span class="sxs-lookup"><span data-stu-id="95868-155">You must pass a DTC ITransaction pointer in `ptrValue`, or "null" to clear the current transaction scope.</span></span>  

- <span data-ttu-id="95868-156">**AppFilterFlags/AppFilterMask**： 控制将哪些类型的应用程序从 ISSOMapper.GetApplications 和 ISSOMapper2.GetApplications 返回。</span><span class="sxs-lookup"><span data-stu-id="95868-156">**AppFilterFlags/AppFilterMask**: controls what types of applications will be returned from ISSOMapper.GetApplications and ISSOMapper2.GetApplications.</span></span> <span data-ttu-id="95868-157">如果应用程序标志匹配的筛选器标志和筛选器标志掩码，则会返回由指定的标志。</span><span class="sxs-lookup"><span data-stu-id="95868-157">If the application flags match the flags specified by the filter flags and the filter flag mask they will be returned.</span></span> <span data-ttu-id="95868-158">执行应用程序的筛选的一种方法是将 AppFilterFlagsMask 设置为 SSO_FLAG_APP_FILTER_BY_TYPE，然后将 AppFilterFlags 设置为一个或多个以下：</span><span class="sxs-lookup"><span data-stu-id="95868-158">One way to perform application filtering is to set AppFilterFlagsMask to SSO_FLAG_APP_FILTER_BY_TYPE and to then set AppFilterFlags to one or more of the following:</span></span>  

   <span data-ttu-id="95868-159">SSO_APP_TYPE_INDIVIDUAL</span><span class="sxs-lookup"><span data-stu-id="95868-159">SSO_APP_TYPE_INDIVIDUAL</span></span>  

   <span data-ttu-id="95868-160">SSO_APP_TYPE_GROUP</span><span class="sxs-lookup"><span data-stu-id="95868-160">SSO_APP_TYPE_GROUP</span></span>  

   <span data-ttu-id="95868-161">SSO_APP_TYPE_CONFIG_STORE</span><span class="sxs-lookup"><span data-stu-id="95868-161">SSO_APP_TYPE_CONFIG_STORE</span></span>  

   <span data-ttu-id="95868-162">SSO_APP_TYPE_HOST_GROUP</span><span class="sxs-lookup"><span data-stu-id="95868-162">SSO_APP_TYPE_HOST_GROUP</span></span>  

   <span data-ttu-id="95868-163">SSO_APP_TYPE_PS_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="95868-163">SSO_APP_TYPE_PS_ADAPTER</span></span>  

   <span data-ttu-id="95868-164">SSO_APP_TYPE_PS_GROUP_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="95868-164">SSO_APP_TYPE_PS_GROUP_ADAPTER</span></span>  

- <span data-ttu-id="95868-165">**AsyncCall**： 如果为 true，则 SSO 将执行使用异步远程过程调用 (RPC) 的方法。</span><span class="sxs-lookup"><span data-stu-id="95868-165">**AsyncCall**: if true, then SSO will perform the method using an asynchronous remote procedure call (RPC).</span></span> <span data-ttu-id="95868-166">该方法将返回 E_PENDING 正在进行。</span><span class="sxs-lookup"><span data-stu-id="95868-166">The method will return E_PENDING while in progress.</span></span> <span data-ttu-id="95868-167">任何其他返回值指示该方法已完成。</span><span class="sxs-lookup"><span data-stu-id="95868-167">Any other return value indicates that the method is completed.</span></span> <span data-ttu-id="95868-168">AsyncCall 还允许您进行轮询的完成情况的方法。</span><span class="sxs-lookup"><span data-stu-id="95868-168">AsyncCall also allows you to poll the method for completion.</span></span>
