---
title: 警报订阅管理命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cd6ad27-6217-466a-b616-4b26fb31b0af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ffcfea22ac63f3a8f4eb22aaeeae3513705ab2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359278"
---
# <a name="alert-subscription-management-commands"></a><span data-ttu-id="f5a80-102">警报订阅管理命令</span><span class="sxs-lookup"><span data-stu-id="f5a80-102">Alert Subscription Management Commands</span></span>
<span data-ttu-id="f5a80-103">BAM 管理实用程序订阅管理命令允许您处理警报订阅。</span><span class="sxs-lookup"><span data-stu-id="f5a80-103">The BAM management utility subscription management commands allow you to work with alert subscriptions.</span></span>  
  
-   <span data-ttu-id="f5a80-104">get-subscription:获取警报的订户的列表。</span><span class="sxs-lookup"><span data-stu-id="f5a80-104">get-subscription: Gets a list of subscribers to an alert.</span></span>  
  
-   <span data-ttu-id="f5a80-105">添加订阅：向警报添加订户。</span><span class="sxs-lookup"><span data-stu-id="f5a80-105">add-subscription: Adds a subscriber to an alert.</span></span>  
  
-   <span data-ttu-id="f5a80-106">删除订阅：从警报删除订户。</span><span class="sxs-lookup"><span data-stu-id="f5a80-106">remove-subscription: Removes a subscriber from an alert.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5a80-107">通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。</span><span class="sxs-lookup"><span data-stu-id="f5a80-107">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="f5a80-108">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="f5a80-108">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="f5a80-109">此开关可以与所有标准 BM 命令结合使用。</span><span class="sxs-lookup"><span data-stu-id="f5a80-109">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5a80-110">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="f5a80-110">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-subscription-command"></a><span data-ttu-id="f5a80-111">get-subscription 命令</span><span class="sxs-lookup"><span data-stu-id="f5a80-111">get-subscription Command</span></span>  
 <span data-ttu-id="f5a80-112">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f5a80-112">**Usage**</span></span>  
  
 <span data-ttu-id="f5a80-113">**bm.exe get-subscriptions -View:\<view name\> -Alert:\<alert name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="f5a80-113">**bm.exe get-subscriptions -View:\<view name\> -Alert:\<alert name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="f5a80-114">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f5a80-114">**Parameters**</span></span>  
  
|<span data-ttu-id="f5a80-115">参数</span><span class="sxs-lookup"><span data-stu-id="f5a80-115">Parameter</span></span>|<span data-ttu-id="f5a80-116">Description</span><span class="sxs-lookup"><span data-stu-id="f5a80-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5a80-117">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="f5a80-117">View:\<view name\></span></span>|<span data-ttu-id="f5a80-118">此警报是指定的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-118">The name of the view on which the alert is to be specified.</span></span>|  
|<span data-ttu-id="f5a80-119">警报：\<警报名称\></span><span class="sxs-lookup"><span data-stu-id="f5a80-119">Alert:\<alert name\></span></span>|<span data-ttu-id="f5a80-120">获取订阅的警报的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-120">The name of the alert from which to get the subscription.</span></span>|  
|<span data-ttu-id="f5a80-121">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f5a80-121">Server:\<server\></span></span>|<span data-ttu-id="f5a80-122">可选：该视图所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-122">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="f5a80-123">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f5a80-123">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f5a80-124">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f5a80-124">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f5a80-125">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f5a80-125">Database:\<database\></span></span>|<span data-ttu-id="f5a80-126">可选：视图所驻留的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-126">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="f5a80-127">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f5a80-127">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f5a80-128">列出指定警报的所有订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="f5a80-128">Lists all the subscribers to the specified alert.</span></span>  
  
 <span data-ttu-id="f5a80-129">**示例**</span><span class="sxs-lookup"><span data-stu-id="f5a80-129">**Examples**</span></span>  
  
```  
bm.exe get-subscriptions -View:SalesManagerView -Alert:SalesTooLow  
bm.exe get-subscriptions -View:Shipments -Alert:SlowShipment -Server:Ship1  
```  
  
## <a name="add-subscription-command"></a><span data-ttu-id="f5a80-130">添加订阅命令</span><span class="sxs-lookup"><span data-stu-id="f5a80-130">add-subscription Command</span></span>  
 <span data-ttu-id="f5a80-131">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f5a80-131">**Usage**</span></span>  
  
 <span data-ttu-id="f5a80-132">**bm.exe 添加订阅的视图：\<视图名称\>-警报：\<警报名称\>-AccountName:\<帐户名称\>-类型: [文件&#124;电子邮件] [-电子邮件：\<电子邮件地址\>] [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="f5a80-132">**bm.exe add-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\> -Type: [ File &#124; Email ][ -Email:\<e-mail address\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="f5a80-133">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f5a80-133">**Parameters**</span></span>  
  
|<span data-ttu-id="f5a80-134">参数</span><span class="sxs-lookup"><span data-stu-id="f5a80-134">Parameter</span></span>|<span data-ttu-id="f5a80-135">Description</span><span class="sxs-lookup"><span data-stu-id="f5a80-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5a80-136">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="f5a80-136">View:\<view name\></span></span>|<span data-ttu-id="f5a80-137">对其指定警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-137">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="f5a80-138">警报：\<警报名称\></span><span class="sxs-lookup"><span data-stu-id="f5a80-138">Alert:\<alert name\></span></span>|<span data-ttu-id="f5a80-139">警报的订阅的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-139">The name of the alert to which to subscribe.</span></span>|  
|<span data-ttu-id="f5a80-140">AccountName:\<帐户名称\></span><span class="sxs-lookup"><span data-stu-id="f5a80-140">AccountName:\<account name\></span></span>|<span data-ttu-id="f5a80-141">域 \ 用户格式，以订阅警报中的帐户。</span><span class="sxs-lookup"><span data-stu-id="f5a80-141">The account, in domain\user format, to subscribe to the alert.</span></span>|  
|<span data-ttu-id="f5a80-142">类型: [文件&#124;电子邮件]</span><span class="sxs-lookup"><span data-stu-id="f5a80-142">Type: [ File &#124; Email ]</span></span>|<span data-ttu-id="f5a80-143">警报的传递类型。</span><span class="sxs-lookup"><span data-stu-id="f5a80-143">The delivery type of the alert.</span></span> <span data-ttu-id="f5a80-144">如果指定传递类型为电子邮件，必须包括在命令行上的电子邮件参数。</span><span class="sxs-lookup"><span data-stu-id="f5a80-144">If you specify a delivery type of e-mail, you must include the e-mail parameter on the command line.</span></span>|  
|<span data-ttu-id="f5a80-145">电子邮件：\<电子邮件地址\></span><span class="sxs-lookup"><span data-stu-id="f5a80-145">Email:\<e-mail address\></span></span>|<span data-ttu-id="f5a80-146">可选：将向其传递警报通知电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f5a80-146">Optional: The email address to which the alert notification will be delivered.</span></span>|  
|<span data-ttu-id="f5a80-147">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f5a80-147">Server:\<server\></span></span>|<span data-ttu-id="f5a80-148">可选：该视图所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-148">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="f5a80-149">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f5a80-149">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f5a80-150">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f5a80-150">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f5a80-151">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f5a80-151">Database:\<database\></span></span>|<span data-ttu-id="f5a80-152">可选：视图所驻留的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-152">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="f5a80-153">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f5a80-153">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f5a80-154">将指定的帐户的订阅添加到指定的警报。</span><span class="sxs-lookup"><span data-stu-id="f5a80-154">Adds a subscription for the specified account to the specified alert.</span></span>  
  
 <span data-ttu-id="f5a80-155">**示例**</span><span class="sxs-lookup"><span data-stu-id="f5a80-155">**Examples**</span></span>  
  
```  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:File  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:Email -Email:useremail@domain.com  
```  
  
## <a name="remove-subscription-command"></a><span data-ttu-id="f5a80-156">remove-subscription 命令</span><span class="sxs-lookup"><span data-stu-id="f5a80-156">remove-subscription Command</span></span>  
 <span data-ttu-id="f5a80-157">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f5a80-157">**Usage**</span></span>  
  
 <span data-ttu-id="f5a80-158">**bm.exe remove-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="f5a80-158">**bm.exe remove-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="f5a80-159">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f5a80-159">**Parameters**</span></span>  
  
|<span data-ttu-id="f5a80-160">参数</span><span class="sxs-lookup"><span data-stu-id="f5a80-160">Parameter</span></span>|<span data-ttu-id="f5a80-161">Description</span><span class="sxs-lookup"><span data-stu-id="f5a80-161">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5a80-162">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="f5a80-162">View:\<view name\></span></span>|<span data-ttu-id="f5a80-163">对其指定警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-163">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="f5a80-164">警报：\<警报名称\></span><span class="sxs-lookup"><span data-stu-id="f5a80-164">Alert:\<alert name\></span></span>|<span data-ttu-id="f5a80-165">警报的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-165">The name of the alert.</span></span>|  
|<span data-ttu-id="f5a80-166">AccountName:\<帐户名称\></span><span class="sxs-lookup"><span data-stu-id="f5a80-166">AccountName:\<account name\></span></span>|<span data-ttu-id="f5a80-167">以 domain\user 格式，若要从警报中删除帐户。</span><span class="sxs-lookup"><span data-stu-id="f5a80-167">The account, in domain\user format, to remove from the alert.</span></span>|  
|<span data-ttu-id="f5a80-168">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f5a80-168">Server:\<server\></span></span>|<span data-ttu-id="f5a80-169">可选：该视图所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-169">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="f5a80-170">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f5a80-170">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f5a80-171">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f5a80-171">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f5a80-172">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f5a80-172">Database:\<database\></span></span>|<span data-ttu-id="f5a80-173">可选：视图所驻留的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a80-173">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="f5a80-174">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f5a80-174">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f5a80-175">从指定的警报中删除指定的帐户的订阅。</span><span class="sxs-lookup"><span data-stu-id="f5a80-175">Removes the subscription of the specified account from the specified alert.</span></span> <span data-ttu-id="f5a80-176">删除指定的帐户的所有订阅。</span><span class="sxs-lookup"><span data-stu-id="f5a80-176">All subscriptions for the specified account are removed.</span></span>  
  
 <span data-ttu-id="f5a80-177">**示例**</span><span class="sxs-lookup"><span data-stu-id="f5a80-177">**Examples**</span></span>  
  
```  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:domain\user  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:user -Server:s1  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5a80-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5a80-178">See Also</span></span>  
 [<span data-ttu-id="f5a80-179">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="f5a80-179">BAM Management Utility</span></span>](../core/bam-management-utility.md)