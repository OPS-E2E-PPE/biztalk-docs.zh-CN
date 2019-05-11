---
title: 使用文件适配器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aaf448c-0035-4648-910b-ae2f15106342
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef5da0b47efc357da7b3e85f3ceb48f93f3845b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380780"
---
# <a name="known-issues-with-the-file-adapter"></a><span data-ttu-id="fd01c-102">文件适配器的已知的问题</span><span class="sxs-lookup"><span data-stu-id="fd01c-102">Known Issues with the File Adapter</span></span>
<span data-ttu-id="fd01c-103">本部分包含可能帮助您避免错误的信息。</span><span class="sxs-lookup"><span data-stu-id="fd01c-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="fd01c-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="fd01c-104">Known Issues</span></span>  
  
#### <a name="a-file-receive-location-is-disabled"></a><span data-ttu-id="fd01c-105">文件接收位置被禁用</span><span class="sxs-lookup"><span data-stu-id="fd01c-105">A File Receive Location is Disabled</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="fd01c-106">问题</span><span class="sxs-lookup"><span data-stu-id="fd01c-106">Problem</span></span>  
 <span data-ttu-id="fd01c-107">File 接收位置将被禁用。</span><span class="sxs-lookup"><span data-stu-id="fd01c-107">A File receive location becomes disabled.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="fd01c-108">原因</span><span class="sxs-lookup"><span data-stu-id="fd01c-108">Cause</span></span>  
 <span data-ttu-id="fd01c-109">如果发生以下任一情况，文件接收适配器将禁用接收位置：</span><span class="sxs-lookup"><span data-stu-id="fd01c-109">The File receive adapter disables the receive location if any of the following occur:</span></span>  
  
-   <span data-ttu-id="fd01c-110">文件接收适配器无法访问文件系统上的接收位置或网络共享，因为指定的路径不存在。</span><span class="sxs-lookup"><span data-stu-id="fd01c-110">The File receive adapter cannot access the receive location on the file system or network share because the specified path does not exist.</span></span> <span data-ttu-id="fd01c-111">对于网络共享，文件接收适配器已用完所有重试次数后禁用接收位置。</span><span class="sxs-lookup"><span data-stu-id="fd01c-111">For a network share, the File receive adapter disables the receive location after all retry attempts have been exhausted.</span></span>  
  
-   <span data-ttu-id="fd01c-112">文件接收适配器无法访问文件系统上的接收位置或网络共享，因为关联的主机实例使用的帐户没有对该位置的读写权限。</span><span class="sxs-lookup"><span data-stu-id="fd01c-112">The File receive adapter cannot access the receive location on the file system or network share because the account used by the associated host instance does not have read-write permission for that location.</span></span> <span data-ttu-id="fd01c-113">对于网络共享，文件接收适配器已用完所有重试次数后禁用接收位置。</span><span class="sxs-lookup"><span data-stu-id="fd01c-113">For a network share, the File receive adapter disables the receive location after all retry attempts have been exhausted.</span></span>  
  
-   <span data-ttu-id="fd01c-114">在接收位置遇到文件的名称长度超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="fd01c-114">Files with names longer than 256 characters are encountered in the receive location.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="fd01c-115">解决方法</span><span class="sxs-lookup"><span data-stu-id="fd01c-115">Resolution</span></span>  
  
-   <span data-ttu-id="fd01c-116">请确保指定的路径或共享已存在。</span><span class="sxs-lookup"><span data-stu-id="fd01c-116">Ensure that the specified path or share exists.</span></span>  
  
-   <span data-ttu-id="fd01c-117">确保为所使用的帐户**登录：** 帐户文件接收处理程序主机实例具有读取和写入权限到指定接收位置。</span><span class="sxs-lookup"><span data-stu-id="fd01c-117">Ensure that the account used as the **Logon:** account for the File receive handler host instance has read and write permissions to the specified receive location.</span></span>  
  
-   <span data-ttu-id="fd01c-118">请确保接收适配器写入到该文件所监视的文件夹的文件不包含超过 256 个字符的文件名称。</span><span class="sxs-lookup"><span data-stu-id="fd01c-118">Ensure that files written to the folder monitored by the File receive adapter do not have file names exceeding 256 characters.</span></span>  
  
#### <a name="files-are-not-being-read-from-the-specified-receive-location"></a><span data-ttu-id="fd01c-119">从读取文件指定的接收位置</span><span class="sxs-lookup"><span data-stu-id="fd01c-119">Files Are Not Being Read from the Specified Receive Location</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="fd01c-120">问题</span><span class="sxs-lookup"><span data-stu-id="fd01c-120">Problem</span></span>  
 <span data-ttu-id="fd01c-121">文件接收适配器不会读取从指定文件接收位置。</span><span class="sxs-lookup"><span data-stu-id="fd01c-121">The File receive adapter does not read a file from the specified receive location.</span></span> <span data-ttu-id="fd01c-122">当文件接收适配器遇到此类文件时，它将事件日志中记录错误并将该文件留在接收位置。</span><span class="sxs-lookup"><span data-stu-id="fd01c-122">When the File receive adapter encounters such a file, it logs an error in the event log and leaves the file in the receive location.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="fd01c-123">原因</span><span class="sxs-lookup"><span data-stu-id="fd01c-123">Cause</span></span>  
 <span data-ttu-id="fd01c-124">如果任意下列条件为 true，则文件接收适配器不会从接收位置读取文件：</span><span class="sxs-lookup"><span data-stu-id="fd01c-124">The File receive adapter does not read a file from the receive location if any of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="fd01c-125">文件为只读文件。</span><span class="sxs-lookup"><span data-stu-id="fd01c-125">The file is read-only.</span></span>  
  
-   <span data-ttu-id="fd01c-126">该文件具有系统属性。</span><span class="sxs-lookup"><span data-stu-id="fd01c-126">The file has a system attribute.</span></span>  
  
-   <span data-ttu-id="fd01c-127">文件接收适配器没有权限读取和写入文件。</span><span class="sxs-lookup"><span data-stu-id="fd01c-127">The File receive adapter does not have permissions to read and write to the file.</span></span>  
  
-   <span data-ttu-id="fd01c-128">在接收位置遇到文件的名称长度超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="fd01c-128">Files with names longer than 256 characters are encountered in the receive location.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="fd01c-129">解决方法</span><span class="sxs-lookup"><span data-stu-id="fd01c-129">Resolution</span></span>  
  
-   <span data-ttu-id="fd01c-130">请确保在指定文件接收位置未标记为"只读"。</span><span class="sxs-lookup"><span data-stu-id="fd01c-130">Ensure that the files in the specified receive location are not marked as "read only".</span></span>  
  
-   <span data-ttu-id="fd01c-131">请确保在指定文件接收位置未标有系统属性。</span><span class="sxs-lookup"><span data-stu-id="fd01c-131">Ensure that the files in the specified receive location are not marked with a system attribute.</span></span>  
  
-   <span data-ttu-id="fd01c-132">确保为所使用的帐户**登录：** 帐户文件接收处理程序主机实例具有读取和写入权限到指定接收位置。</span><span class="sxs-lookup"><span data-stu-id="fd01c-132">Ensure that the account used as the **Logon:** account for the File receive handler host instance has read and write permissions to the specified receive location.</span></span>  
  
-   <span data-ttu-id="fd01c-133">请确保接收适配器写入到该文件所监视的文件夹的文件不包含超过 256 个字符的文件名称。</span><span class="sxs-lookup"><span data-stu-id="fd01c-133">Ensure that files written to the folder monitored by the File receive adapter do not have file names exceeding 256 characters.</span></span>  
  
#### <a name="messages-are-not-being-sent-by-the-file-send-adapter"></a><span data-ttu-id="fd01c-134">不通过 File 发送适配器发送消息</span><span class="sxs-lookup"><span data-stu-id="fd01c-134">Messages Are Not Being Sent by the File Send Adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="fd01c-135">问题</span><span class="sxs-lookup"><span data-stu-id="fd01c-135">Problem</span></span>  
 <span data-ttu-id="fd01c-136">文件发送适配器无法将消息发送到指定的目录或文件共享。</span><span class="sxs-lookup"><span data-stu-id="fd01c-136">The File send adapter fails to send a message to the specified directory or file share.</span></span>  
  
 <span data-ttu-id="fd01c-137">如果消息无法写入到指定的目录或文件共享，错误写入到 BizTalk server 计算机的事件日志并发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="fd01c-137">If a message fails to be written to the specified directory or file share, an error is written to the Event log of the BizTalk server computer and the following sequence of events occurs:</span></span>  
  
1.  <span data-ttu-id="fd01c-138">文件发送适配器将重试写入操作。</span><span class="sxs-lookup"><span data-stu-id="fd01c-138">The File send adapter will retry the write operation.</span></span>  
  
2.  <span data-ttu-id="fd01c-139">文件适配器将尝试传送文件使用备份传输 （如果已配置）。</span><span class="sxs-lookup"><span data-stu-id="fd01c-139">The File adapter will attempt to deliver the file using the backup transport (if configured).</span></span>  
  
3.  <span data-ttu-id="fd01c-140">该消息将写入到挂起队列。</span><span class="sxs-lookup"><span data-stu-id="fd01c-140">The message will be written to the suspended queue.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="fd01c-141">原因</span><span class="sxs-lookup"><span data-stu-id="fd01c-141">Cause</span></span>  
  
-   <span data-ttu-id="fd01c-142">文件发送适配器无法访问文件会从文件系统或网络共享因为不存在指定的路径的目录。</span><span class="sxs-lookup"><span data-stu-id="fd01c-142">The File send adapter cannot access the directory that files are sent from on the file system or network share because the specified path does not exist.</span></span>  
  
-   <span data-ttu-id="fd01c-143">文件发送适配器无法写入到目标位置中的文件在文件系统或网络共享上因为关联的主机实例不具有该文件或对该位置的写权限。</span><span class="sxs-lookup"><span data-stu-id="fd01c-143">The File send adapter cannot write to a file in the destination location on the file system or network share because the associated host instance does not have write permissions for that file or for that location.</span></span>  
  
-   <span data-ttu-id="fd01c-144">文件发送适配器无法写入文件指定，因为它是只读的或标有**系统**文件属性。</span><span class="sxs-lookup"><span data-stu-id="fd01c-144">The File send adapter cannot write to the file specified because it is read-only or is marked with the **system** file attribute.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="fd01c-145">解决方法</span><span class="sxs-lookup"><span data-stu-id="fd01c-145">Resolution</span></span>  
  
-   <span data-ttu-id="fd01c-146">请确保指定的路径或共享已存在。</span><span class="sxs-lookup"><span data-stu-id="fd01c-146">Ensure that the specified path or share exists.</span></span>  
  
-   <span data-ttu-id="fd01c-147">确保为所使用的帐户**登录：** 文件发送处理程序主机实例帐户具有读取和写入到指定的目录或文件共享的权限。</span><span class="sxs-lookup"><span data-stu-id="fd01c-147">Ensure that the account used as the **Logon:** account for the File send handler host instance has read and write permissions to the specified directory or file share.</span></span>  
  
-   <span data-ttu-id="fd01c-148">请确保指定的目录或文件共享中的现有文件不具有系统属性。</span><span class="sxs-lookup"><span data-stu-id="fd01c-148">Ensure that existing files in the specified directory or file share are not marked with the system attribute.</span></span>  
  
#### <a name="sending-a-file-using-the-file-adapter-is-very-slow"></a><span data-ttu-id="fd01c-149">发送文件使用文件适配器时速度缓慢</span><span class="sxs-lookup"><span data-stu-id="fd01c-149">Sending a file using the File adapter is very slow</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="fd01c-150">问题</span><span class="sxs-lookup"><span data-stu-id="fd01c-150">Problem</span></span>  
 <span data-ttu-id="fd01c-151">文件发送适配器的性能条件时速度较慢**允许写入时缓存**属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="fd01c-151">Performance of the File send adapter is slower when the **Allow cache on write** property is set to **False**.</span></span> <span data-ttu-id="fd01c-152">**允许写入时缓存**属性设置为**False**默认情况下。</span><span class="sxs-lookup"><span data-stu-id="fd01c-152">The **Allow cache on write** property is set to **False** by default.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="fd01c-153">原因</span><span class="sxs-lookup"><span data-stu-id="fd01c-153">Cause</span></span>  
 <span data-ttu-id="fd01c-154">设置**允许写入时缓存**属性设置为**False**可以降低性能，因为此设置不允许使用内存中缓存的文件由操作系统。</span><span class="sxs-lookup"><span data-stu-id="fd01c-154">Setting the **Allow cache on write** property to **False** can reduce performance as this setting disallows the use of in-memory caching of files by the operating system.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="fd01c-155">解决方法</span><span class="sxs-lookup"><span data-stu-id="fd01c-155">Resolution</span></span>  
 <span data-ttu-id="fd01c-156">若要提高性能的文件发送适配器更改**允许写入时缓存**属性设置为**True** （选中复选框）。</span><span class="sxs-lookup"><span data-stu-id="fd01c-156">To increase performance of the File send adapter change the **Allow cache on write** property to **True** (check the box).</span></span> <span data-ttu-id="fd01c-157">有关详细信息**允许写入时缓存**属性，请参阅[如何配置 File 发送端口](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9)。</span><span class="sxs-lookup"><span data-stu-id="fd01c-157">For more information about the **Allow cache on write** property, see [How to Configure a File Send Port](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd01c-158">设置**允许写入时缓存**属性设置为**True**增加可能会丢失数据的情况在操作系统发生故障。</span><span class="sxs-lookup"><span data-stu-id="fd01c-158">Setting the **Allow cache on write** property to **True** increases the possibility of data loss in the event that the operating system experiences a failure.</span></span> <span data-ttu-id="fd01c-159">在此方案中，存储在内存中文件缓存中的任何数据将会丢失。</span><span class="sxs-lookup"><span data-stu-id="fd01c-159">In this scenario, any data that is stored in the in-memory file cache will be lost.</span></span>  
  
#### <a name="zero-byte-files-received-by-the-file-adapter-are-deleted"></a><span data-ttu-id="fd01c-160">文件适配器接收到的零字节文件将被删除</span><span class="sxs-lookup"><span data-stu-id="fd01c-160">Zero byte files received by the File adapter are deleted</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="fd01c-161">问题</span><span class="sxs-lookup"><span data-stu-id="fd01c-161">Problem</span></span>  
 <span data-ttu-id="fd01c-162">如果为空 （零个字节） 文件将提取该文件接收适配器、 删除文件和 BizTalk server 的应用程序日志中写入类似于以下警告：</span><span class="sxs-lookup"><span data-stu-id="fd01c-162">If an empty (zero byte) file is picked up by the File receive adapter, the file is deleted and a warning similar to the following is written to the application log of the BizTalk server:</span></span>  
  
```  
Event Type:Warning  
Event Source:BizTalk Server 2009  
Event Category:BizTalk Server 2009   
Event ID:7182  
Date:8/30/2006  
Time:1:32:32 PM  
User:N/A  
Computer:BIZTALKSERVER  
Description:  
The FILE receive adapter deleted the empty file "C:\filesource\emptyfile.xml.BTS-WIP" without performing any processing.  
```  
  
##### <a name="cause"></a><span data-ttu-id="fd01c-163">原因</span><span class="sxs-lookup"><span data-stu-id="fd01c-163">Cause</span></span>  
 <span data-ttu-id="fd01c-164">按照设计，文件接收适配器删除零字节文件。</span><span class="sxs-lookup"><span data-stu-id="fd01c-164">The File receive adapter deletes zero byte files by design.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="fd01c-165">解决方法</span><span class="sxs-lookup"><span data-stu-id="fd01c-165">Resolution</span></span>  
 <span data-ttu-id="fd01c-166">不不需要任何操作，此行为是有意设计。</span><span class="sxs-lookup"><span data-stu-id="fd01c-166">No action is required, this behavior is by design.</span></span>