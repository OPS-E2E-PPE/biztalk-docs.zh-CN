---
title: 文件适配器 |Microsoft 文档
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
ms.openlocfilehash: ceb4f0728eb6fac66fb0fc5f84b117b37ba84121
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247085"
---
# <a name="file-adapter"></a>文件适配器
文件适配器用于将文件传入和传出 Microsoft BizTalk Server。 文件适配器包含两个适配器-接收适配器和一个发送适配器。  
  
 本部分将介绍文件接收适配器和文件发送适配器的工作流和批处理支持。  
 
## <a name="file-receive-adapter"></a>File 接收适配器  
  
使用文件收到适配器从文件中读取消息并将其提交到服务器。 接收适配器读取该文件，并创建 BizTalk 消息对象，因此该 BizTalk 服务器能够处理该消息。 在从文件中进行读取时，适配器将锁定该文件以确保无法对文件内容进行修改。  
  
> [!NOTE] 
> 文件接收适配器不提取只读文件或系统文件。  
  
 文件接收适配器从本地文件系统或网络共享位置上的文件中读取消息。 如果由于网络问题无法访问网络共享中的指定位置，则接收适配器将重试读取操作（重试次数可在 BizTalk Server 管理控制台中进行配置）。 BizTalk 消息引擎读取并成功接受消息后，接收适配器将从文件系统或网络共享位置中删除该文件。 如果已读取消息但管道未成功处理该消息，则适配器会将该消息放置在挂起队列中，然后从文件系统或网络共享位置中删除该文件。 如果文件接收适配器无法将消息提交到 MessageBox 数据库或挂起消息，则不从文件系统或网络共享位置删除原始文件。  
  
 也可以将文件接收适配器配置为在处理文件时对其进行重命名。 应重命名文件以确保在关闭并重新启动接收位置时接收适配器不生成重复消息。 对于文件接收位置，这是一个可配置选项。 默认情况下，重命名处于禁用状态。 如果启用重命名，则文件接收适配器会将扩展名 .BTS-WIP 附加到该文件。 接收适配器随后会从位于接收位置的重命名的文件中读取消息并将其提交给服务器。 在接收适配器成功提交文件后，该接收适配器将从文件系统或网络共享位置中删除重命名的文件。 如果已读取消息但在管道中处理该消息时失败，则接收适配器会将该消息放置在 MessageBox 数据库的挂起队列中，然后从网络共享位置中删除重命名的文件。  
  
> [!NOTE] 
> 重命名文件不会影响性能。  
  
 如果文件接收适配器已成功读取消息但未将该消息成功存储在 MessageBox 数据库中，则重命名的文件将恢复为其不带 .BTS-WIP 扩展名的原始名称。 请注意，如果启用了重命名选项，则接收适配器将不读取带有 .BTS-WIP 扩展名的文件。  
  
#### <a name="using-file-change-notifications-and-polling"></a>使用文件更改通知和轮询
  
 文件接收适配器依靠 Windows 文件更改通知来确定何时从指定的目录或共享提取文件。 如果文件接收适配器在文件尚未完全写入到指定目录或共享时即收到 Windows 文件更改通知，则该文件将会锁定，并且文件适配器将不检索该文件。 在此方案中，该文件收到适配器将主动轮询指定的目录或共享在**轮询间隔 （毫秒）** 上指定**高级设置**对话框中配置时可用文件接收位置。 文件接收适配器轮询目录或共享时，会从共享上检索未锁定的文件并将其提交至 MessageBox 数据库。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文件适配器仅已测试，并且支持 NTFS 文件系统上。  
  
 下列 Windows 文件更改通知将导致文件接收适配器从指定的位置提取文件：  
  
 `FILE_NOTIFY_CHANGE_ATTRIBUTES`
  
 对受监视的目录或子树中属性的任意更改都会导致返回一个更改通知等待操作。  
  
 `FILE_NOTIFY_CHANGE_FILE_NAME`  
  
 对受监视的目录或子树中文件名的任意更改都会导致返回一个更改通知等待操作。 这些更改包括重命名、创建或删除文件名。  
  
 `FILE_NOTIFY_CHANGE_SIZE`  
  
 对受监视的目录或子树中文件大小的任意更改都会导致返回一个更改通知等待操作。 仅当文件写入磁盘时，操作系统才会检测文件大小的更改。 对于使用大量缓存的操作系统，仅当缓存充分刷新时，才会进行检测。  
  
 `FILE_NOTIFY_CHANGE_LAST_WRITE`  
  
 对受监视的目录或子树中文件的上次写入时间的任意更改都会导致返回一个更改通知等待操作。 仅当文件写入磁盘时，操作系统才会检测上次写入时间的更改。 对于使用大量缓存的操作系统，仅当缓存充分刷新时，才会进行检测。  
  
 有关详细信息**FindFirstChangeNotification**函数，请参阅[https://msdn.microsoft.com/library/windows/desktop/aa364417(v=vs.85).aspx](https://msdn.microsoft.com/library/windows/desktop/aa364417(v=vs.85).aspx).  
  
### <a name="file-receive-adapter-batching-support"></a>文件接收适配器的批处理支持
  
 文件接收适配器将消息分批提交给服务器。 通过收集接收位置中所有可用的可读文件来为每个接收位置生成单独的一批，可启动文件接收适配器。 在收集了所有可用文件后，或当收集的文件量超过最大批大小时，接收适配器会将各批提交给 MessageBox 数据库。  
  
 在成功读取批中的所有消息并将其提交给 MessageBox 数据库后，文件接收适配器将从接收位置中删除相应的文件。 如果处理批中的部分消息时失败，则文件接收适配器将挂起这些消息并从接收位置中删除相应的文件。 如果无法将部分或全部消息存储在 MessageBox 数据库中，则回滚整个批处理操作并将所有相应文件原封不动地保留在接收位置中。  
  
## <a name="file-send-adapter"></a>文件发送适配器
  
 文件发送适配器将消息从 MessageBox 数据库中传输到指定的目标位置 (URL)。 使用与消息上下文属性相关的通配符可定义 URL，该 URL 为文件路径和文件名。 在向该文件写入消息之前，文件发送适配器会将通配符解析为实际的文件名。  
  
 在向文件写入消息时，文件发送适配器将从 BizTalk 消息对象的正文部分中获取该消息的上下文。 文件发送适配器将忽略 BizTalk 消息对象中的其他消息部分。 在将该消息写入文件后，文件适配器将从 MessageBox 数据库中将其删除。 文件适配器可直接将文件写入文件系统；也可使用文件系统缓存将其写入文件系统，这样可提高性能，尤其适用于大型文件。  
  
### <a name="file-send-adapter-batching-support"></a>文件发送适配器的批处理支持
  
 文件发送适配器从 MessageBox 数据库中获取消息批并将其写入文件系统或网络共享位置中的目标位置。 文件发送适配器的批大小不可配置并且预设为 20。 如果 BizTalk Server 无法将批中的部分消息写入文件，则系统会将这些消息重新提交给 MessageBox 数据库以重试对其进行处理。 可使用 BizTalk Server 管理控制台来配置重试时间间隔和重试次数。  
  
 
## <a name="in-this-section"></a>在本节中  
  
-   [配置文件适配器](../core/configure-the-file-adapter.md) 
  
-   [配置文件适配器时的限制](../core/restrictions-when-configuring-the-file-adapter.md)  
