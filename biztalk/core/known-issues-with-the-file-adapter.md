---
title: 文件适配器的已知问题 |Microsoft 文档
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
ms.openlocfilehash: 2690803346efc5931a88acd70be9d24af107156f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262885"
---
# <a name="known-issues-with-the-file-adapter"></a><span data-ttu-id="6bbed-102">文件适配器的已知的问题</span><span class="sxs-lookup"><span data-stu-id="6bbed-102">Known Issues with the File Adapter</span></span>
<span data-ttu-id="6bbed-103">本部分包含可帮助你避免出现错误的信息。</span><span class="sxs-lookup"><span data-stu-id="6bbed-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="6bbed-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="6bbed-104">Known Issues</span></span>  
  
#### <a name="a-file-receive-location-is-disabled"></a><span data-ttu-id="6bbed-105">文件接收位置被禁用</span><span class="sxs-lookup"><span data-stu-id="6bbed-105">A File Receive Location is Disabled</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6bbed-106">问题</span><span class="sxs-lookup"><span data-stu-id="6bbed-106">Problem</span></span>  
 <span data-ttu-id="6bbed-107">文件接收位置被禁用。</span><span class="sxs-lookup"><span data-stu-id="6bbed-107">A File receive location becomes disabled.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6bbed-108">原因</span><span class="sxs-lookup"><span data-stu-id="6bbed-108">Cause</span></span>  
 <span data-ttu-id="6bbed-109">如果出现以下任一情况，文件接收适配器将禁用接收位置：</span><span class="sxs-lookup"><span data-stu-id="6bbed-109">The File receive adapter disables the receive location if any of the following occur:</span></span>  
  
-   <span data-ttu-id="6bbed-110">由于指定路径不存在，文件接收适配器无法访问文件系统或网络共享上的接收位置。</span><span class="sxs-lookup"><span data-stu-id="6bbed-110">The File receive adapter cannot access the receive location on the file system or network share because the specified path does not exist.</span></span> <span data-ttu-id="6bbed-111">对于网络共享，文件接收适配器在全部重新尝试次数均已耗尽后禁用该接收位置。</span><span class="sxs-lookup"><span data-stu-id="6bbed-111">For a network share, the File receive adapter disables the receive location after all retry attempts have been exhausted.</span></span>  
  
-   <span data-ttu-id="6bbed-112">文件接收适配器无法访问文件系统或网络共享上的接收位置，因为关联的主机实例使用的帐户不具有该位置的读写权限。</span><span class="sxs-lookup"><span data-stu-id="6bbed-112">The File receive adapter cannot access the receive location on the file system or network share because the account used by the associated host instance does not have read-write permission for that location.</span></span> <span data-ttu-id="6bbed-113">对于网络共享，文件接收适配器在全部重新尝试次数均已耗尽后禁用该接收位置。</span><span class="sxs-lookup"><span data-stu-id="6bbed-113">For a network share, the File receive adapter disables the receive location after all retry attempts have been exhausted.</span></span>  
  
-   <span data-ttu-id="6bbed-114">在接收位置上遇到文件名长度超过 256 个字符的文件。</span><span class="sxs-lookup"><span data-stu-id="6bbed-114">Files with names longer than 256 characters are encountered in the receive location.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6bbed-115">解决方法</span><span class="sxs-lookup"><span data-stu-id="6bbed-115">Resolution</span></span>  
  
-   <span data-ttu-id="6bbed-116">请确保指定的路径或共享已存在。</span><span class="sxs-lookup"><span data-stu-id="6bbed-116">Ensure that the specified path or share exists.</span></span>  
  
-   <span data-ttu-id="6bbed-117">请确保帐户用作**登录：** 帐户为 File 接收处理程序主机实例具有读取和写入权限指定接收位置。</span><span class="sxs-lookup"><span data-stu-id="6bbed-117">Ensure that the account used as the **Logon:** account for the File receive handler host instance has read and write permissions to the specified receive location.</span></span>  
  
-   <span data-ttu-id="6bbed-118">请确保写入由文件接收适配器监视的文件夹的文件的文件名长度不超出 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="6bbed-118">Ensure that files written to the folder monitored by the File receive adapter do not have file names exceeding 256 characters.</span></span>  
  
#### <a name="files-are-not-being-read-from-the-specified-receive-location"></a><span data-ttu-id="6bbed-119">文件没有从指定的接收位置读取</span><span class="sxs-lookup"><span data-stu-id="6bbed-119">Files Are Not Being Read from the Specified Receive Location</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6bbed-120">问题</span><span class="sxs-lookup"><span data-stu-id="6bbed-120">Problem</span></span>  
 <span data-ttu-id="6bbed-121">文件接收适配器没有从指定的接收位置读文件。</span><span class="sxs-lookup"><span data-stu-id="6bbed-121">The File receive adapter does not read a file from the specified receive location.</span></span> <span data-ttu-id="6bbed-122">如果文件接收适配器遇到这种文件，它将在事件日志中记录一个错误，并将该文件留在接收位置。</span><span class="sxs-lookup"><span data-stu-id="6bbed-122">When the File receive adapter encounters such a file, it logs an error in the event log and leaves the file in the receive location.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6bbed-123">原因</span><span class="sxs-lookup"><span data-stu-id="6bbed-123">Cause</span></span>  
 <span data-ttu-id="6bbed-124">如果出现以下任一情况，则文件接收适配器无法从接收位置读取文件。</span><span class="sxs-lookup"><span data-stu-id="6bbed-124">The File receive adapter does not read a file from the receive location if any of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="6bbed-125">文件为只读文件。</span><span class="sxs-lookup"><span data-stu-id="6bbed-125">The file is read-only.</span></span>  
  
-   <span data-ttu-id="6bbed-126">文件具有系统属性。</span><span class="sxs-lookup"><span data-stu-id="6bbed-126">The file has a system attribute.</span></span>  
  
-   <span data-ttu-id="6bbed-127">文件接收适配器没有读写该文件的权限。</span><span class="sxs-lookup"><span data-stu-id="6bbed-127">The File receive adapter does not have permissions to read and write to the file.</span></span>  
  
-   <span data-ttu-id="6bbed-128">在接收位置上遇到文件名长度超过 256 个字符的文件。</span><span class="sxs-lookup"><span data-stu-id="6bbed-128">Files with names longer than 256 characters are encountered in the receive location.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6bbed-129">解决方法</span><span class="sxs-lookup"><span data-stu-id="6bbed-129">Resolution</span></span>  
  
-   <span data-ttu-id="6bbed-130">请确保位于指定接收位置的文件没有被标记为“只读”。</span><span class="sxs-lookup"><span data-stu-id="6bbed-130">Ensure that the files in the specified receive location are not marked as "read only".</span></span>  
  
-   <span data-ttu-id="6bbed-131">请确保位于指定接收位置的文件不具有系统属性。</span><span class="sxs-lookup"><span data-stu-id="6bbed-131">Ensure that the files in the specified receive location are not marked with a system attribute.</span></span>  
  
-   <span data-ttu-id="6bbed-132">请确保帐户用作**登录：** 帐户为 File 接收处理程序主机实例具有读取和写入权限指定接收位置。</span><span class="sxs-lookup"><span data-stu-id="6bbed-132">Ensure that the account used as the **Logon:** account for the File receive handler host instance has read and write permissions to the specified receive location.</span></span>  
  
-   <span data-ttu-id="6bbed-133">请确保写入由文件接收适配器监视的文件夹的文件的文件名长度不超出 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="6bbed-133">Ensure that files written to the folder monitored by the File receive adapter do not have file names exceeding 256 characters.</span></span>  
  
#### <a name="messages-are-not-being-sent-by-the-file-send-adapter"></a><span data-ttu-id="6bbed-134">消息未被文件发送适配器发送</span><span class="sxs-lookup"><span data-stu-id="6bbed-134">Messages Are Not Being Sent by the File Send Adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6bbed-135">问题</span><span class="sxs-lookup"><span data-stu-id="6bbed-135">Problem</span></span>  
 <span data-ttu-id="6bbed-136">文件发送适配器无法将消息发送到指定的目录或文件共享。</span><span class="sxs-lookup"><span data-stu-id="6bbed-136">The File send adapter fails to send a message to the specified directory or file share.</span></span>  
  
 <span data-ttu-id="6bbed-137">如果消息无法写入指定的目录或文件共享，就会在 BizTalk Server 计算机的事件日志中写入一个错误，并发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="6bbed-137">If a message fails to be written to the specified directory or file share, an error is written to the Event log of the BizTalk server computer and the following sequence of events occurs:</span></span>  
  
1.  <span data-ttu-id="6bbed-138">文件发送适配器将重试写操作。</span><span class="sxs-lookup"><span data-stu-id="6bbed-138">The File send adapter will retry the write operation.</span></span>  
  
2.  <span data-ttu-id="6bbed-139">文件适配器将尝试使用备份传输（如果已配置）传送文件。</span><span class="sxs-lookup"><span data-stu-id="6bbed-139">The File adapter will attempt to deliver the file using the backup transport (if configured).</span></span>  
  
3.  <span data-ttu-id="6bbed-140">消息将写到挂起队列。</span><span class="sxs-lookup"><span data-stu-id="6bbed-140">The message will be written to the suspended queue.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6bbed-141">原因</span><span class="sxs-lookup"><span data-stu-id="6bbed-141">Cause</span></span>  
  
-   <span data-ttu-id="6bbed-142">由于指定路径不存在，文件发送适配器无法访问文件系统或网络共享上从中发送文件的目录。</span><span class="sxs-lookup"><span data-stu-id="6bbed-142">The File send adapter cannot access the directory that files are sent from on the file system or network share because the specified path does not exist.</span></span>  
  
-   <span data-ttu-id="6bbed-143">文件发送适配器无法写入文件系统或网络共享上的目标位置中的文件，因为关联的主机实例不具有该文件或该位置的写权限。</span><span class="sxs-lookup"><span data-stu-id="6bbed-143">The File send adapter cannot write to a file in the destination location on the file system or network share because the associated host instance does not have write permissions for that file or for that location.</span></span>  
  
-   <span data-ttu-id="6bbed-144">File 发送适配器无法写入指定，因为它是只读的或用标记文件**系统**文件属性。</span><span class="sxs-lookup"><span data-stu-id="6bbed-144">The File send adapter cannot write to the file specified because it is read-only or is marked with the **system** file attribute.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6bbed-145">解决方法</span><span class="sxs-lookup"><span data-stu-id="6bbed-145">Resolution</span></span>  
  
-   <span data-ttu-id="6bbed-146">请确保指定的路径或共享已存在。</span><span class="sxs-lookup"><span data-stu-id="6bbed-146">Ensure that the specified path or share exists.</span></span>  
  
-   <span data-ttu-id="6bbed-147">请确保帐户用作**登录：** 文件发送处理程序主机实例的帐户具有读取和写入到指定的目录或文件共享的权限。</span><span class="sxs-lookup"><span data-stu-id="6bbed-147">Ensure that the account used as the **Logon:** account for the File send handler host instance has read and write permissions to the specified directory or file share.</span></span>  
  
-   <span data-ttu-id="6bbed-148">请确保位于指定目录或文件共享的现有文件不具有系统属性。</span><span class="sxs-lookup"><span data-stu-id="6bbed-148">Ensure that existing files in the specified directory or file share are not marked with the system attribute.</span></span>  
  
#### <a name="sending-a-file-using-the-file-adapter-is-very-slow"></a><span data-ttu-id="6bbed-149">使用文件适配器发送文件速度很慢</span><span class="sxs-lookup"><span data-stu-id="6bbed-149">Sending a file using the File adapter is very slow</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6bbed-150">问题</span><span class="sxs-lookup"><span data-stu-id="6bbed-150">Problem</span></span>  
 <span data-ttu-id="6bbed-151">File 发送适配器的性能速度较慢时**允许写入缓存**属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="6bbed-151">Performance of the File send adapter is slower when the **Allow cache on write** property is set to **False**.</span></span> <span data-ttu-id="6bbed-152">**允许写入缓存**属性设置为**False**默认情况下。</span><span class="sxs-lookup"><span data-stu-id="6bbed-152">The **Allow cache on write** property is set to **False** by default.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6bbed-153">原因</span><span class="sxs-lookup"><span data-stu-id="6bbed-153">Cause</span></span>  
 <span data-ttu-id="6bbed-154">设置**允许写入缓存**属性**False**可以减小性能，因为此设置不允许使用内存中缓存文件的操作系统。</span><span class="sxs-lookup"><span data-stu-id="6bbed-154">Setting the **Allow cache on write** property to **False** can reduce performance as this setting disallows the use of in-memory caching of files by the operating system.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6bbed-155">解决方法</span><span class="sxs-lookup"><span data-stu-id="6bbed-155">Resolution</span></span>  
 <span data-ttu-id="6bbed-156">若要提高性能的文件，将发送适配器更改**允许写入缓存**属性**True** （复选框）。</span><span class="sxs-lookup"><span data-stu-id="6bbed-156">To increase performance of the File send adapter change the **Allow cache on write** property to **True** (check the box).</span></span> <span data-ttu-id="6bbed-157">有关详细信息**允许写入缓存**属性，请参阅[如何配置文件发送端口](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9)。</span><span class="sxs-lookup"><span data-stu-id="6bbed-157">For more information about the **Allow cache on write** property, see [How to Configure a File Send Port](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bbed-158">设置**允许写入缓存**属性**True**增加可能出现数据丢失的事件中操作系统遇到失败。</span><span class="sxs-lookup"><span data-stu-id="6bbed-158">Setting the **Allow cache on write** property to **True** increases the possibility of data loss in the event that the operating system experiences a failure.</span></span> <span data-ttu-id="6bbed-159">在这种情况下，存储在内存中文件缓存的任何数据都会丢失。</span><span class="sxs-lookup"><span data-stu-id="6bbed-159">In this scenario, any data that is stored in the in-memory file cache will be lost.</span></span>  
  
#### <a name="zero-byte-files-received-by-the-file-adapter-are-deleted"></a><span data-ttu-id="6bbed-160">删除文件适配器接收的零字节文件</span><span class="sxs-lookup"><span data-stu-id="6bbed-160">Zero byte files received by the File adapter are deleted</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6bbed-161">问题</span><span class="sxs-lookup"><span data-stu-id="6bbed-161">Problem</span></span>  
 <span data-ttu-id="6bbed-162">如果文件接收适配器接收到一个空（零字节）文件，则该文件将被删除，并且在 BizTalk Server 的应用程序日志中将写入类似下面的警告：</span><span class="sxs-lookup"><span data-stu-id="6bbed-162">If an empty (zero byte) file is picked up by the File receive adapter, the file is deleted and a warning similar to the following is written to the application log of the BizTalk server:</span></span>  
  
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
  
##### <a name="cause"></a><span data-ttu-id="6bbed-163">原因</span><span class="sxs-lookup"><span data-stu-id="6bbed-163">Cause</span></span>  
 <span data-ttu-id="6bbed-164">由于设计的结果，文件接收适配器删除零字节文件。</span><span class="sxs-lookup"><span data-stu-id="6bbed-164">The File receive adapter deletes zero byte files by design.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6bbed-165">解决方法</span><span class="sxs-lookup"><span data-stu-id="6bbed-165">Resolution</span></span>  
 <span data-ttu-id="6bbed-166">无需任何操作，此行为是有意设计成这样的。</span><span class="sxs-lookup"><span data-stu-id="6bbed-166">No action is required, this behavior is by design.</span></span>