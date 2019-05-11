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
# <a name="file-adapter"></a>文件适配器
文件适配器将文件传入和传出 Microsoft BizTalk Server。 文件适配器由两个适配器组成： 一个接收适配器和一个发送适配器。  
  
 本部分讨论了工作流和批处理支持文件接收适配器和文件发送适配器。  
 
## <a name="file-receive-adapter"></a>文件接收适配器  
  
使用文件接收适配器从文件中读取消息并将其提交到服务器。 接收适配器读取该文件，并创建一个 BizTalk 消息对象，因此 BizTalk Server 能够处理该消息。 在从文件读取，适配器将锁定该文件以确保可以对文件内容进行任何修改。  
  
> [!NOTE] 
> 文件接收适配器不提取只读文件或系统文件。  
  
 从本地文件系统或网络共享上的文件，文件接收适配器中读取消息。 由于网络问题而不可用的网络共享上的指定的位置时，接收适配器重试读取的操作 （重试次数为可在 BizTalk Server 管理控制台中配置）。 已读取并成功通过 BizTalk 消息引擎接受消息后，接收适配器从文件系统或网络共享中删除文件。 如果已读取消息但管道未成功处理消息，适配器将该消息放在挂起队列中，然后从文件系统或网络共享中删除该文件。 如果文件接收适配器不能提交或挂起到 MessageBox 数据库的消息，不会从文件系统或网络共享中删除原始文件。  
  
 此外可以配置文件接收适配器若要重命名文件时处理它们。 应该重命名文件，以确保接收适配器不会如果关闭并重新启动接收位置生成重复的消息。 对于文件接收位置，这是一个可配置选项。 默认情况下，禁用重命名。 启用重命名后，文件接收适配器会将扩展名。BTS WIP 的文件。 然后，接收适配器从接收位置中的已重命名文件中读取消息，并将其提交到服务器。 接收适配器已成功提交文件后，接收适配器从文件系统或网络共享中删除重命名的文件。 如果已读取但失败消息在管道中处理接收适配器将消息放置在 MessageBox 数据库的挂起队列中，并从网络共享中删除重命名的文件。  
  
> [!NOTE] 
> 重命名文件对性能没有任何影响。  
  
 如果文件接收适配器已成功读取消息但未成功存储该消息在 MessageBox 数据库中，重命名的文件而不恢复为其原始名称。BTS WIP 扩展。 请注意，接收适配器不读取带有扩展名的文件。BTS-WIP 如果启用了重命名的选项。  
  
#### <a name="using-file-change-notifications-and-polling"></a>使用文件更改通知和轮询
  
 文件接收适配器依靠 Windows 文件更改通知，以确定何时将选取从指定的目录或共享的文件。 如果文件接收适配器收到 Windows 文件更改通知前文件已完全写入到指定的目录或共享，然后将锁定该文件，文件接收适配器不会检索该文件。 在此方案中，文件接收适配器将主动轮询指定的目录或共享**轮询间隔 （毫秒）** 中所指定**高级设置**配置时可用的对话框文件接收位置。 当文件接收适配器轮询目录或共享它从共享中检索未锁定的文件并将提交到 MessageBox 数据库的文件。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文件适配器具有仅进行了测试，并支持 NTFS 文件系统上。  
  
 以下 Windows 文件更改通知将导致文件接收适配器将选取指定位置中的文件：  
  
 `FILE_NOTIFY_CHANGE_ATTRIBUTES`
  
 受监视的目录或子树中的任意属性更改都会导致返回一个更改通知等待操作。  
  
 `FILE_NOTIFY_CHANGE_FILE_NAME`  
  
 任何文件名称中受监视的目录或子树会导致返回一个更改通知等待操作的更改。 更改包括重命名、 创建或删除的文件名称。  
  
 `FILE_NOTIFY_CHANGE_SIZE`  
  
 受监视的目录或子树中任意文件大小更改都会导致返回一个更改通知等待操作。 操作系统中文件大小仅当文件写入到磁盘时，检测到更改。 对于使用大量缓存的操作系统，仅当缓存充分刷新时，将会检测。  
  
 `FILE_NOTIFY_CHANGE_LAST_WRITE`  
  
 对受监视的目录或子树中的文件的上次编写时间的任何更改会导致返回一个更改通知等待操作。 仅当文件写入到磁盘时，操作系统检测到上次写入时间的更改。 对于使用大量缓存的操作系统，仅当缓存充分刷新时，将会检测。  
  
 有关详细信息**FindFirstChangeNotification**函数，请参阅[ https://msdn.microsoft.com/library/windows/desktop/aa364417(v=vs.85).aspx ](https://msdn.microsoft.com/library/windows/desktop/aa364417(v=vs.85).aspx)。  
  
### <a name="file-receive-adapter-batching-support"></a>文件接收适配器的批处理支持
  
 文件接收适配器将消息提交到批处理中的服务器。 文件接收适配器首先会生成单个批次，每个接收位置，通过收集所有的可读文件可在接收位置。 批处理提交到 MessageBox 数据库接收适配器已收集了所有可用的文件时或当收集的文件量超过最大批次大小。  
  
 批中的所有消息已成功读取并提交到 MessageBox 数据库后，文件接收适配器从接收位置删除相应的文件。 如果批中消息的部分失败处理，文件接收适配器将它们挂起和从接收位置删除相应的文件。 如果部分或全部消息无法存储在 MessageBox 数据库，回滚整个批处理操作和所有相应文件原封不动地保留在接收位置。  
  
## <a name="file-send-adapter"></a>文件发送适配器
  
 文件发送适配器将消息从 MessageBox 数据库为指定的目标地址 (URL) 传输。 定义 URL，它是文件路径和文件名，使用与消息上下文属性相关的通配符字符。 文件适配器解析通配符字符之前发送到实际的文件名称将消息写入到该文件。  
  
 当向文件中写入一条消息，该文件发送适配器获取消息内容从 BizTalk 消息对象正文部分。 文件发送适配器将忽略 BizTalk 消息对象中的其他消息部分。 在文件后适配器将消息写入到文件中，它从 MessageBox 数据库中删除消息。 文件适配器将文件写入到文件系统或者直接或通过使用文件系统缓存，这样可以提高性能，特别是对于大型文件。  
  
### <a name="file-send-adapter-batching-support"></a>文件发送适配器的批处理支持
  
 文件发送适配器获取消息批将从 MessageBox 数据库，并将其写入到文件中的目标位置位于文件系统或网络共享。 文件发送适配器的批大小不可配置并且预设为 20。 如果 BizTalk Server 无法向文件写入一些批处理内的消息，系统将重新提交给 MessageBox 数据库以重试处理这些消息。 你可以配置重试间隔和通过使用 BizTalk Server 管理控制台的重试次数。  
  
 
## <a name="in-this-section"></a>本节内容  
  
-   [配置文件适配器](../core/configure-the-file-adapter.md) 
  
-   [配置文件适配器时的限制](../core/restrictions-when-configuring-the-file-adapter.md)  
