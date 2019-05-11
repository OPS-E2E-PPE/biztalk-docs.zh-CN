---
title: 文件适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- File adapters
ms.assetid: e4f6e94b-89b8-42ba-a4c2-a629f1107bb1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df810ad31137512713ed7e90a779d82cd48b1b66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345553"
---
# <a name="file-adapter"></a><span data-ttu-id="fb125-102">文件适配器</span><span class="sxs-lookup"><span data-stu-id="fb125-102">File Adapter</span></span>
<span data-ttu-id="fb125-103">文件适配器将文件传入和传出 Microsoft BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="fb125-103">The File adapter transfers files into and out of Microsoft BizTalk Server.</span></span> <span data-ttu-id="fb125-104">文件适配器由两个适配器组成： 一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="fb125-104">The File adapter consists of two adapters — a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="fb125-105">本部分讨论了工作流和批处理支持文件接收适配器和文件发送适配器。</span><span class="sxs-lookup"><span data-stu-id="fb125-105">This section discusses the workflow and batching support for both the File receive adapter and the File send adapter.</span></span>  
 
## <a name="file-receive-adapter"></a><span data-ttu-id="fb125-106">文件接收适配器</span><span class="sxs-lookup"><span data-stu-id="fb125-106">File receive adapter</span></span>  
  
<span data-ttu-id="fb125-107">使用文件接收适配器从文件中读取消息并将其提交到服务器。</span><span class="sxs-lookup"><span data-stu-id="fb125-107">Use the File receive adapter to read messages from files, and submit them to the server.</span></span> <span data-ttu-id="fb125-108">接收适配器读取该文件，并创建一个 BizTalk 消息对象，因此 BizTalk Server 能够处理该消息。</span><span class="sxs-lookup"><span data-stu-id="fb125-108">The receive adapter reads the file, and creates a BizTalk Message object, so that BizTalk Server can process the message.</span></span> <span data-ttu-id="fb125-109">在从文件读取，适配器将锁定该文件以确保可以对文件内容进行任何修改。</span><span class="sxs-lookup"><span data-stu-id="fb125-109">While reading from the file, the adapter locks the file to ensure that no modifications can be made to the file content.</span></span>  
  
> [!NOTE] 
> <span data-ttu-id="fb125-110">文件接收适配器不提取只读文件或系统文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-110">The File receive adapter does not pick up read-only files or system files.</span></span>  
  
 <span data-ttu-id="fb125-111">从本地文件系统或网络共享上的文件，文件接收适配器中读取消息。</span><span class="sxs-lookup"><span data-stu-id="fb125-111">The File receive adapter reads the messages from files on local file systems or on network shares.</span></span> <span data-ttu-id="fb125-112">由于网络问题而不可用的网络共享上的指定的位置时，接收适配器重试读取的操作 （重试次数为可在 BizTalk Server 管理控制台中配置）。</span><span class="sxs-lookup"><span data-stu-id="fb125-112">When the specified location on a network share is unavailable due to network problems, the receive adapter retries the read operation (the number of retries is configurable in the BizTalk Server Administration console).</span></span> <span data-ttu-id="fb125-113">已读取并成功通过 BizTalk 消息引擎接受消息后，接收适配器从文件系统或网络共享中删除文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-113">After the message has been read and successfully accepted by the BizTalk Messaging Engine, the receive adapter deletes the file from the file system or network share.</span></span> <span data-ttu-id="fb125-114">如果已读取消息但管道未成功处理消息，适配器将该消息放在挂起队列中，然后从文件系统或网络共享中删除该文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-114">If the message was read but the pipeline did not successfully process the message, the adapter puts the message in the suspended queue and then deletes the file from the file system or network share.</span></span> <span data-ttu-id="fb125-115">如果文件接收适配器不能提交或挂起到 MessageBox 数据库的消息，不会从文件系统或网络共享中删除原始文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-115">If the File receive adapter cannot submit or suspend the message to the MessageBox database, it does not delete the original file from the file system or network share.</span></span>  
  
 <span data-ttu-id="fb125-116">此外可以配置文件接收适配器若要重命名文件时处理它们。</span><span class="sxs-lookup"><span data-stu-id="fb125-116">You can also configure the File receive adapter to rename files when processing them.</span></span> <span data-ttu-id="fb125-117">应该重命名文件，以确保接收适配器不会如果关闭并重新启动接收位置生成重复的消息。</span><span class="sxs-lookup"><span data-stu-id="fb125-117">You should rename files to ensure that the receive adapter does not generate duplicate messages if the receive location is shut down and restarted.</span></span> <span data-ttu-id="fb125-118">对于文件接收位置，这是一个可配置选项。</span><span class="sxs-lookup"><span data-stu-id="fb125-118">This is a configurable option for File receive locations.</span></span> <span data-ttu-id="fb125-119">默认情况下，禁用重命名。</span><span class="sxs-lookup"><span data-stu-id="fb125-119">By default, renaming is disabled.</span></span> <span data-ttu-id="fb125-120">启用重命名后，文件接收适配器会将扩展名。BTS WIP 的文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-120">When renaming is enabled, the File receive adapter appends the extension .BTS-WIP to the file.</span></span> <span data-ttu-id="fb125-121">然后，接收适配器从接收位置中的已重命名文件中读取消息，并将其提交到服务器。</span><span class="sxs-lookup"><span data-stu-id="fb125-121">The receive adapter then reads the messages from the renamed file in the receive location and submits it to the server.</span></span> <span data-ttu-id="fb125-122">接收适配器已成功提交文件后，接收适配器从文件系统或网络共享中删除重命名的文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-122">After the receive adapter has successfully submitted a file, the receive adapter deletes the renamed file from the file system or network share.</span></span> <span data-ttu-id="fb125-123">如果已读取但失败消息在管道中处理接收适配器将消息放置在 MessageBox 数据库的挂起队列中，并从网络共享中删除重命名的文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-123">If a message has been read but failed processing in the pipeline, the receive adapter places the message in the MessageBox database suspended queue, and deletes the renamed file from the network share.</span></span>  
  
> [!NOTE] 
> <span data-ttu-id="fb125-124">重命名文件对性能没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="fb125-124">Renaming files has no impact on performance.</span></span>  
  
 <span data-ttu-id="fb125-125">如果文件接收适配器已成功读取消息但未成功存储该消息在 MessageBox 数据库中，重命名的文件而不恢复为其原始名称。BTS WIP 扩展。</span><span class="sxs-lookup"><span data-stu-id="fb125-125">If the File receive adapter successfully reads the message but did not successfully store the message in the MessageBox database, the renamed file reverts to its original name, without the .BTS-WIP extension.</span></span> <span data-ttu-id="fb125-126">请注意，接收适配器不读取带有扩展名的文件。BTS-WIP 如果启用了重命名的选项。</span><span class="sxs-lookup"><span data-stu-id="fb125-126">Note that the receive adapter does not read files with the extension .BTS-WIP if the renaming option is turned on.</span></span>  
  
#### <a name="using-file-change-notifications-and-polling"></a><span data-ttu-id="fb125-127">使用文件更改通知和轮询</span><span class="sxs-lookup"><span data-stu-id="fb125-127">Using file change notifications and polling</span></span>
  
 <span data-ttu-id="fb125-128">文件接收适配器依靠 Windows 文件更改通知，以确定何时将选取从指定的目录或共享的文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-128">The File receive adapter relies on Windows File Change Notifications to determine when to pick up a file from the specified directory or share.</span></span> <span data-ttu-id="fb125-129">如果文件接收适配器收到 Windows 文件更改通知前文件已完全写入到指定的目录或共享，然后将锁定该文件，文件接收适配器不会检索该文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-129">If the File receive adapter receives a Windows File Change Notification before the file has been completely written to the specified directory or share then the file will be locked and the File receive adapter will not retrieve the file.</span></span> <span data-ttu-id="fb125-130">在此方案中，文件接收适配器将主动轮询指定的目录或共享**轮询间隔 （毫秒）** 中所指定**高级设置**配置时可用的对话框文件接收位置。</span><span class="sxs-lookup"><span data-stu-id="fb125-130">In this scenario, the File receive adapter will actively poll the specified directory or share at the **Polling interval (ms)** specified on the **Advanced settings** dialog box available when configuring a File receive location.</span></span> <span data-ttu-id="fb125-131">当文件接收适配器轮询目录或共享它从共享中检索未锁定的文件并将提交到 MessageBox 数据库的文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-131">When the File receive adapter polls a directory or share it retrieves unlocked files from the share and submits the files to the MessageBox database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb125-132">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文件适配器具有仅进行了测试，并支持 NTFS 文件系统上。</span><span class="sxs-lookup"><span data-stu-id="fb125-132">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] File adapter has only been tested on, and is supported on, the NTFS file system.</span></span>  
  
 <span data-ttu-id="fb125-133">以下 Windows 文件更改通知将导致文件接收适配器将选取指定位置中的文件：</span><span class="sxs-lookup"><span data-stu-id="fb125-133">The following Windows File Change Notifications will cause the File receive adapter to pick up a file from the specified location:</span></span>  
  
 `FILE_NOTIFY_CHANGE_ATTRIBUTES`
  
 <span data-ttu-id="fb125-134">受监视的目录或子树中的任意属性更改都会导致返回一个更改通知等待操作。</span><span class="sxs-lookup"><span data-stu-id="fb125-134">Any attribute change in the watched directory or subtree causes a change notification wait operation to return.</span></span>  
  
 `FILE_NOTIFY_CHANGE_FILE_NAME`  
  
 <span data-ttu-id="fb125-135">任何文件名称中受监视的目录或子树会导致返回一个更改通知等待操作的更改。</span><span class="sxs-lookup"><span data-stu-id="fb125-135">Any file name change in the watched directory or subtree causes a change notification wait operation to return.</span></span> <span data-ttu-id="fb125-136">更改包括重命名、 创建或删除的文件名称。</span><span class="sxs-lookup"><span data-stu-id="fb125-136">Changes include renaming, creating, or deleting a file name.</span></span>  
  
 `FILE_NOTIFY_CHANGE_SIZE`  
  
 <span data-ttu-id="fb125-137">受监视的目录或子树中任意文件大小更改都会导致返回一个更改通知等待操作。</span><span class="sxs-lookup"><span data-stu-id="fb125-137">Any file-size change in the watched directory or subtree causes a change notification wait operation to return.</span></span> <span data-ttu-id="fb125-138">操作系统中文件大小仅当文件写入到磁盘时，检测到更改。</span><span class="sxs-lookup"><span data-stu-id="fb125-138">The operating system detects a change in file size only when the file is written to the disk.</span></span> <span data-ttu-id="fb125-139">对于使用大量缓存的操作系统，仅当缓存充分刷新时，将会检测。</span><span class="sxs-lookup"><span data-stu-id="fb125-139">For operating systems that use extensive caching, detection occurs only when the cache is sufficiently flushed.</span></span>  
  
 `FILE_NOTIFY_CHANGE_LAST_WRITE`  
  
 <span data-ttu-id="fb125-140">对受监视的目录或子树中的文件的上次编写时间的任何更改会导致返回一个更改通知等待操作。</span><span class="sxs-lookup"><span data-stu-id="fb125-140">Any change to the last write-time of files in the watched directory or subtree causes a change notification wait operation to return.</span></span> <span data-ttu-id="fb125-141">仅当文件写入到磁盘时，操作系统检测到上次写入时间的更改。</span><span class="sxs-lookup"><span data-stu-id="fb125-141">The operating system detects a change to the last write-time only when the file is written to the disk.</span></span> <span data-ttu-id="fb125-142">对于使用大量缓存的操作系统，仅当缓存充分刷新时，将会检测。</span><span class="sxs-lookup"><span data-stu-id="fb125-142">For operating systems that use extensive caching, detection occurs only when the cache is sufficiently flushed.</span></span>  
  
 <span data-ttu-id="fb125-143">有关详细信息**FindFirstChangeNotification**函数，请参阅[ https://msdn.microsoft.com/library/windows/desktop/aa364417(v=vs.85).aspx ](https://msdn.microsoft.com/library/windows/desktop/aa364417(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="fb125-143">For more information about the **FindFirstChangeNotification** function see [https://msdn.microsoft.com/library/windows/desktop/aa364417(v=vs.85).aspx](https://msdn.microsoft.com/library/windows/desktop/aa364417(v=vs.85).aspx).</span></span>  
  
### <a name="file-receive-adapter-batching-support"></a><span data-ttu-id="fb125-144">文件接收适配器的批处理支持</span><span class="sxs-lookup"><span data-stu-id="fb125-144">File Receive Adapter Batching Support</span></span>
  
 <span data-ttu-id="fb125-145">文件接收适配器将消息提交到批处理中的服务器。</span><span class="sxs-lookup"><span data-stu-id="fb125-145">The File receive adapter submits messages to the server in batches.</span></span> <span data-ttu-id="fb125-146">文件接收适配器首先会生成单个批次，每个接收位置，通过收集所有的可读文件可在接收位置。</span><span class="sxs-lookup"><span data-stu-id="fb125-146">The File receive adapter starts by building a single batch per receive location by collecting all the readable files available in the receive location.</span></span> <span data-ttu-id="fb125-147">批处理提交到 MessageBox 数据库接收适配器已收集了所有可用的文件时或当收集的文件量超过最大批次大小。</span><span class="sxs-lookup"><span data-stu-id="fb125-147">Batches are submitted to the MessageBox database by the receive adapter when all the available files have been collected or when the amount of files collected exceeds the maximum batch size.</span></span>  
  
 <span data-ttu-id="fb125-148">批中的所有消息已成功读取并提交到 MessageBox 数据库后，文件接收适配器从接收位置删除相应的文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-148">After all the messages within the batch have been successfully read and submitted into the MessageBox database, the File receive adapter deletes the corresponding files from the receive location.</span></span> <span data-ttu-id="fb125-149">如果批中消息的部分失败处理，文件接收适配器将它们挂起和从接收位置删除相应的文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-149">If some of the messages within the batch failed processing, the File receive adapter suspends them and deletes the corresponding files from the receive location.</span></span> <span data-ttu-id="fb125-150">如果部分或全部消息无法存储在 MessageBox 数据库，回滚整个批处理操作和所有相应文件原封不动地保留在接收位置。</span><span class="sxs-lookup"><span data-stu-id="fb125-150">If some or all of the messages fail to be stored in the MessageBox database, the entire batch operation is rolled back and all corresponding files are left unchanged in the receive location.</span></span>  
  
## <a name="file-send-adapter"></a><span data-ttu-id="fb125-151">文件发送适配器</span><span class="sxs-lookup"><span data-stu-id="fb125-151">File Send Adapter</span></span>
  
 <span data-ttu-id="fb125-152">文件发送适配器将消息从 MessageBox 数据库为指定的目标地址 (URL) 传输。</span><span class="sxs-lookup"><span data-stu-id="fb125-152">The File send adapter transmits messages from the MessageBox database to a specified destination address (URL).</span></span> <span data-ttu-id="fb125-153">定义 URL，它是文件路径和文件名，使用与消息上下文属性相关的通配符字符。</span><span class="sxs-lookup"><span data-stu-id="fb125-153">You define the URL, which is a file path and file name, by using wildcard characters related to the message context properties.</span></span> <span data-ttu-id="fb125-154">文件适配器解析通配符字符之前发送到实际的文件名称将消息写入到该文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-154">The File send adapter resolves the wildcard characters to the actual file name before writing the message to the file.</span></span>  
  
 <span data-ttu-id="fb125-155">当向文件中写入一条消息，该文件发送适配器获取消息内容从 BizTalk 消息对象正文部分。</span><span class="sxs-lookup"><span data-stu-id="fb125-155">When writing a message to a file, the File send adapter gets the message content from the body part of the BizTalk Message object.</span></span> <span data-ttu-id="fb125-156">文件发送适配器将忽略 BizTalk 消息对象中的其他消息部分。</span><span class="sxs-lookup"><span data-stu-id="fb125-156">The File send adapter ignores other message parts in the BizTalk Message object.</span></span> <span data-ttu-id="fb125-157">在文件后适配器将消息写入到文件中，它从 MessageBox 数据库中删除消息。</span><span class="sxs-lookup"><span data-stu-id="fb125-157">After the File adapter writes the message to a file, it deletes the message from the MessageBox database.</span></span> <span data-ttu-id="fb125-158">文件适配器将文件写入到文件系统或者直接或通过使用文件系统缓存，这样可以提高性能，特别是对于大型文件。</span><span class="sxs-lookup"><span data-stu-id="fb125-158">The File adapter writes files to the file system either directly or by using the file system cache, which can improve performance, particularly for large files.</span></span>  
  
### <a name="file-send-adapter-batching-support"></a><span data-ttu-id="fb125-159">文件发送适配器的批处理支持</span><span class="sxs-lookup"><span data-stu-id="fb125-159">File Send Adapter Batching Support</span></span>
  
 <span data-ttu-id="fb125-160">文件发送适配器获取消息批将从 MessageBox 数据库，并将其写入到文件中的目标位置位于文件系统或网络共享。</span><span class="sxs-lookup"><span data-stu-id="fb125-160">The File send adapter gets batches of messages from the MessageBox database and writes them to files in destination locations on the file system or the network share.</span></span> <span data-ttu-id="fb125-161">文件发送适配器的批大小不可配置并且预设为 20。</span><span class="sxs-lookup"><span data-stu-id="fb125-161">The size of File send adapter batches is not configurable and is preset to 20.</span></span> <span data-ttu-id="fb125-162">如果 BizTalk Server 无法向文件写入一些批处理内的消息，系统将重新提交给 MessageBox 数据库以重试处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="fb125-162">If BizTalk Server fails to write some of the messages within a batch to files, the system resubmits those messages to the MessageBox database for retry processing.</span></span> <span data-ttu-id="fb125-163">你可以配置重试间隔和通过使用 BizTalk Server 管理控制台的重试次数。</span><span class="sxs-lookup"><span data-stu-id="fb125-163">You can configure the retry interval and retry count by using the BizTalk Server Administration console.</span></span>  
  
 
## <a name="in-this-section"></a><span data-ttu-id="fb125-164">本节内容</span><span class="sxs-lookup"><span data-stu-id="fb125-164">In this section</span></span>  
  
-   [<span data-ttu-id="fb125-165">配置文件适配器</span><span class="sxs-lookup"><span data-stu-id="fb125-165">Configure the File adapter</span></span>](../core/configure-the-file-adapter.md) 
  
-   [<span data-ttu-id="fb125-166">配置文件适配器时的限制</span><span class="sxs-lookup"><span data-stu-id="fb125-166">Restrictions when configuring the File adapter</span></span>](../core/restrictions-when-configuring-the-file-adapter.md)  
