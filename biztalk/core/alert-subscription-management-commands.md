---
title: 警报订阅管理命令 |Microsoft 文档
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
ms.openlocfilehash: 02234637e38bb59e71c0f435ee24feef39e09e91
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966651"
---
# <a name="alert-subscription-management-commands"></a><span data-ttu-id="63076-102">警报订阅管理命令</span><span class="sxs-lookup"><span data-stu-id="63076-102">Alert Subscription Management Commands</span></span>
<span data-ttu-id="63076-103">BAM 管理实用程序订阅管理命令可用于处理警报订阅。</span><span class="sxs-lookup"><span data-stu-id="63076-103">The BAM management utility subscription management commands allow you to work with alert subscriptions.</span></span>  
  
-   <span data-ttu-id="63076-104">获取订阅： 获取对警报的订阅服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="63076-104">get-subscription: Gets a list of subscribers to an alert.</span></span>  
  
-   <span data-ttu-id="63076-105">添加订阅： 将订阅服务器添加到警报。</span><span class="sxs-lookup"><span data-stu-id="63076-105">add-subscription: Adds a subscriber to an alert.</span></span>  
  
-   <span data-ttu-id="63076-106">删除订阅： 订阅服务器，则删除警报。</span><span class="sxs-lookup"><span data-stu-id="63076-106">remove-subscription: Removes a subscriber from an alert.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63076-107">你可以通过包括启用任何 BM 实用工具命令的跟踪 **-跟踪： 在 &#124; 关闭**参数交换机。</span><span class="sxs-lookup"><span data-stu-id="63076-107">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="63076-108">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="63076-108">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="63076-109">该开关可与所有标准 BM 命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="63076-109">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63076-110">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="63076-110">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-subscription-command"></a><span data-ttu-id="63076-111">get-subscription 命令</span><span class="sxs-lookup"><span data-stu-id="63076-111">get-subscription Command</span></span>  
 <span data-ttu-id="63076-112">**用法**</span><span class="sxs-lookup"><span data-stu-id="63076-112">**Usage**</span></span>  
  
 <span data-ttu-id="63076-113">**bm.exe 获取订阅的视图：\<视图名称\>-警报：\<警报名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="63076-113">**bm.exe get-subscriptions -View:\<view name\> -Alert:\<alert name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="63076-114">**参数**</span><span class="sxs-lookup"><span data-stu-id="63076-114">**Parameters**</span></span>  
  
|<span data-ttu-id="63076-115">参数</span><span class="sxs-lookup"><span data-stu-id="63076-115">Parameter</span></span>|<span data-ttu-id="63076-116">Description</span><span class="sxs-lookup"><span data-stu-id="63076-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63076-117">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="63076-117">View:\<view name\></span></span>|<span data-ttu-id="63076-118">要对其指定警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="63076-118">The name of the view on which the alert is to be specified.</span></span>|  
|<span data-ttu-id="63076-119">警报：\<警报名称\></span><span class="sxs-lookup"><span data-stu-id="63076-119">Alert:\<alert name\></span></span>|<span data-ttu-id="63076-120">从中获取订阅的警报的名称。</span><span class="sxs-lookup"><span data-stu-id="63076-120">The name of the alert from which to get the subscription.</span></span>|  
|<span data-ttu-id="63076-121">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="63076-121">Server:\<server\></span></span>|<span data-ttu-id="63076-122">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="63076-122">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="63076-123">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="63076-123">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="63076-124">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="63076-124">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="63076-125">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="63076-125">Database:\<database\></span></span>|<span data-ttu-id="63076-126">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="63076-126">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="63076-127">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="63076-127">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="63076-128">列出指定警报的所有订户。</span><span class="sxs-lookup"><span data-stu-id="63076-128">Lists all the subscribers to the specified alert.</span></span>  
  
 <span data-ttu-id="63076-129">**示例**</span><span class="sxs-lookup"><span data-stu-id="63076-129">**Examples**</span></span>  
  
```  
bm.exe get-subscriptions -View:SalesManagerView -Alert:SalesTooLow  
bm.exe get-subscriptions -View:Shipments -Alert:SlowShipment -Server:Ship1  
```  
  
## <a name="add-subscription-command"></a><span data-ttu-id="63076-130">add-subscription 命令</span><span class="sxs-lookup"><span data-stu-id="63076-130">add-subscription Command</span></span>  
 <span data-ttu-id="63076-131">**用法**</span><span class="sxs-lookup"><span data-stu-id="63076-131">**Usage**</span></span>  
  
 <span data-ttu-id="63076-132">**bm.exe 添加订阅的视图：\<视图名称\>-警报：\<警报名称\>-AccountName:\<帐户名称\>-类型: [文件 &#124;电子邮件] [-电子邮件：\<电子邮件地址\>] [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="63076-132">**bm.exe add-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\> -Type: [ File &#124; Email ][ -Email:\<e-mail address\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="63076-133">**参数**</span><span class="sxs-lookup"><span data-stu-id="63076-133">**Parameters**</span></span>  
  
|<span data-ttu-id="63076-134">参数</span><span class="sxs-lookup"><span data-stu-id="63076-134">Parameter</span></span>|<span data-ttu-id="63076-135">Description</span><span class="sxs-lookup"><span data-stu-id="63076-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63076-136">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="63076-136">View:\<view name\></span></span>|<span data-ttu-id="63076-137">对其指定警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="63076-137">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="63076-138">警报：\<警报名称\></span><span class="sxs-lookup"><span data-stu-id="63076-138">Alert:\<alert name\></span></span>|<span data-ttu-id="63076-139">订阅的警报的名称。</span><span class="sxs-lookup"><span data-stu-id="63076-139">The name of the alert to which to subscribe.</span></span>|  
|<span data-ttu-id="63076-140">AccountName:\<帐户名称\></span><span class="sxs-lookup"><span data-stu-id="63076-140">AccountName:\<account name\></span></span>|<span data-ttu-id="63076-141">订阅警报的帐户（格式为“域\用户”）。</span><span class="sxs-lookup"><span data-stu-id="63076-141">The account, in domain\user format, to subscribe to the alert.</span></span>|  
|<span data-ttu-id="63076-142">类型: [文件 &#124;电子邮件]</span><span class="sxs-lookup"><span data-stu-id="63076-142">Type: [ File &#124; Email ]</span></span>|<span data-ttu-id="63076-143">警报的传递类型。</span><span class="sxs-lookup"><span data-stu-id="63076-143">The delivery type of the alert.</span></span> <span data-ttu-id="63076-144">如果指定传递类型为电子邮件，则必须在命令行中包含电子邮件参数。</span><span class="sxs-lookup"><span data-stu-id="63076-144">If you specify a delivery type of e-mail, you must include the e-mail parameter on the command line.</span></span>|  
|<span data-ttu-id="63076-145">电子邮件：\<电子邮件地址\></span><span class="sxs-lookup"><span data-stu-id="63076-145">Email:\<e-mail address\></span></span>|<span data-ttu-id="63076-146">可选： 将向其传递警报通知电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="63076-146">Optional: The email address to which the alert notification will be delivered.</span></span>|  
|<span data-ttu-id="63076-147">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="63076-147">Server:\<server\></span></span>|<span data-ttu-id="63076-148">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="63076-148">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="63076-149">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="63076-149">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="63076-150">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="63076-150">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="63076-151">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="63076-151">Database:\<database\></span></span>|<span data-ttu-id="63076-152">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="63076-152">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="63076-153">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="63076-153">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="63076-154">为指定帐户向指定警报添加订阅。</span><span class="sxs-lookup"><span data-stu-id="63076-154">Adds a subscription for the specified account to the specified alert.</span></span>  
  
 <span data-ttu-id="63076-155">**示例**</span><span class="sxs-lookup"><span data-stu-id="63076-155">**Examples**</span></span>  
  
```  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:File  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:Email -Email:useremail@domain.com  
```  
  
## <a name="remove-subscription-command"></a><span data-ttu-id="63076-156">remove-subscription 命令</span><span class="sxs-lookup"><span data-stu-id="63076-156">remove-subscription Command</span></span>  
 <span data-ttu-id="63076-157">**用法**</span><span class="sxs-lookup"><span data-stu-id="63076-157">**Usage**</span></span>  
  
 <span data-ttu-id="63076-158">**bm.exe 删除订阅的视图：\<视图名称\>-警报：\<警报名称\>-AccountName:\<帐户名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="63076-158">**bm.exe remove-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="63076-159">**参数**</span><span class="sxs-lookup"><span data-stu-id="63076-159">**Parameters**</span></span>  
  
|<span data-ttu-id="63076-160">参数</span><span class="sxs-lookup"><span data-stu-id="63076-160">Parameter</span></span>|<span data-ttu-id="63076-161">Description</span><span class="sxs-lookup"><span data-stu-id="63076-161">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63076-162">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="63076-162">View:\<view name\></span></span>|<span data-ttu-id="63076-163">对其指定警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="63076-163">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="63076-164">警报：\<警报名称\></span><span class="sxs-lookup"><span data-stu-id="63076-164">Alert:\<alert name\></span></span>|<span data-ttu-id="63076-165">警报的名称。</span><span class="sxs-lookup"><span data-stu-id="63076-165">The name of the alert.</span></span>|  
|<span data-ttu-id="63076-166">AccountName:\<帐户名称\></span><span class="sxs-lookup"><span data-stu-id="63076-166">AccountName:\<account name\></span></span>|<span data-ttu-id="63076-167">从警报中删除的帐户（格式为“域\用户”）。</span><span class="sxs-lookup"><span data-stu-id="63076-167">The account, in domain\user format, to remove from the alert.</span></span>|  
|<span data-ttu-id="63076-168">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="63076-168">Server:\<server\></span></span>|<span data-ttu-id="63076-169">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="63076-169">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="63076-170">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="63076-170">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="63076-171">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="63076-171">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="63076-172">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="63076-172">Database:\<database\></span></span>|<span data-ttu-id="63076-173">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="63076-173">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="63076-174">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="63076-174">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="63076-175">从指定警报中删除指定帐户的订阅。</span><span class="sxs-lookup"><span data-stu-id="63076-175">Removes the subscription of the specified account from the specified alert.</span></span> <span data-ttu-id="63076-176">指定帐户的所有订阅都将被删除。</span><span class="sxs-lookup"><span data-stu-id="63076-176">All subscriptions for the specified account are removed.</span></span>  
  
 <span data-ttu-id="63076-177">**示例**</span><span class="sxs-lookup"><span data-stu-id="63076-177">**Examples**</span></span>  
  
```  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:domain\user  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:user -Server:s1  
```  
  
## <a name="see-also"></a><span data-ttu-id="63076-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63076-178">See Also</span></span>  
 [<span data-ttu-id="63076-179">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="63076-179">BAM Management Utility</span></span>](../core/bam-management-utility.md)