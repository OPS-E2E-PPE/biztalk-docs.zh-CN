---
title: 配置文件适配器时的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], restrictions
- File adapters, restrictions
ms.assetid: 8d8137a7-5b16-4ae3-a0a7-6d114324bdf3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c866dc6bfed3e378105b7055b312a832598c22d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399098"
---
# <a name="restrictions-when-configuring-the-file-adapter"></a>配置文件适配器时的限制
限制和规则时使用文件适配器。

## <a name="file-mask-and-file-name-gotchas"></a>文件掩码和文件名称陷阱

文件掩码是文件的一个字符串，指定文件接收处理程序将从接收位置提取的类型。 文件名称是文件的一个字符串，指定文件发送处理程序将在其中写入消息的名称。  
  
 以下限制适用于文件的名称和文件掩码属性：  
  
- 接收位置或发送端口可以每个指定只有一个文件掩码或文件名。  
  
- 不允许的完整路径或文件掩码或文件名以及路径的一部分。 文件掩码和文件名始终表示不带路径的名称。  
  
- 文件掩码和文件名不区分大小写。  
  
- 文件名称不能包含任何以下字符： \< \> : / &#124; "？ * ;  
  
- 文件掩码不能包含任何以下字符： \< \> : / &#124; "; 
  
- 以下保留的设备名称不能用作文件的名称：CON、 PRN、 AUX、 时钟 $、 NUL、 COM1、 COM2、 COM3、 COM4、 COM5、 COM6、 COM7、 COM8、 COM9、 LPT1、 LPT2、 LPT3、 LPT4、 LPT5、 LPT6、 LPT7、 LPT8 和 LPT9。 此外，不允许的那些扩展的任何组合。  
  
- Windows 磁盘卷使用 8.3 （8.3 文件名） 默认情况下使用短期和长期的文件的名称命名约定。 非系统磁盘卷禁用 8.3 文件名的命名约定，并因此仅使用长文件名。 

  启用 8dot3 后，文件和其文件扩展名地转换为短名称。 例如，`testabcdefgh.docx`将转换为`testab~1.doc`。 请注意，缩短文件名，并且从缩短的文件扩展名`.docx`到`doc`。

  此行为会影响文件适配器接收文件的方式。 如果文件掩码设置为`*.xml`，然后文件匹配两者`*.xml`和`*.xmln`提取扩展。 

  若要查看是否对磁盘上启用 8dot3 命名约定，打开命令提示符下，作为管理员，并键入`fsutil 8dot3name query c:`，或`fsutil 8dot3name query d:`，依次类推。 示例输出如以下所示：

  ```
  C:\WINDOWS\system32>fsutil 8dot3name query c:
  The volume state is: 0 (8dot3 name creation is enabled).
  The registry state is: 2 (Per volume setting - the default).
    
  Based on the above two settings, 8dot3 name creation is enabled on c:
  ```
    
  文件适配器将使用[FindFirstFile 函数](https://msdn.microsoft.com/library/windows/desktop/aa364418(v=vs.85).aspx)。 此函数包含具有短期和长期的文件名的搜索结果。 若要查看文件夹中的短期和长期文件名称，打开命令提示符处，转到您的文件夹，然后键入`dir /x`。 在命令提示符中，您可以键入`dir c:\foldername /x`。
    
  如果您更改的卷上的 8dot3name 设置，新的文件使用新的设置。 任何现有文件将其名称，直至它们也会移动。 
    
  若要仅选取你预期的文件，并在更高版本的加载过程中获得更佳性能 （更少的开销），则它可能是最佳配置文件适配器以使用卷在禁用 8dot3name。 
  
- 文件路径、 文件掩码和文件名 （没有宏替换） 的总长度不能超过 256 个字符。 （这是 MessageBox 数据库的限制）。  
  
- 文件路径不能以开头"`\\`？"。  
  
- 不能在文件路径中，使用网络映射的驱动器号，因为它们是基于用户会话。  
  
  BizTalk 消息引擎始终会验证文件名和文件掩码属性在设计时通过使用前面列出的项。 此外，文件适配器验证文件名和文件掩码属性在运行时如果适配器在动态端口上发送消息。  
  
> [!NOTE]
>  文件适配器不提取系统文件或只读文件。 将选择仅基于磁盘的文件，而不是设备文件。  

## <a name="using-macros-in-file-names"></a>在文件名称中使用宏

可以使用一组预定义的宏来动态创建的文件发送处理程序在其中写入消息文件。 然后再创建文件系统上的文件，文件发送处理程序替换所有宏使用单独的值在文件名中。 可以在一个文件名中使用多个不同的宏。  
  
 配置文件发送处理程序使用 BizTalk 浏览器对象模型时，可以使用文件名宏。  
  
 文件发送处理程序不会使用值替换宏，如果以下任何条件成立：  
  
- 未设置相应的系统属性。  
  
- 宏拼写错误。  
  
- 该宏的值包含在文件名中无效的符号。  
  
  如果出现下列任一条件，文件发送处理程序将保留在文件名称不变，例如 Myfile_%MessageID%.xml 宏。  
  
  下表列出了受支持的宏，并介绍文件发送处理程序如何替换它们。  
  
|宏名|替换值|  
|----------------|----------------------|  
|%datetime%|协调世界时 (UTC) 日期时间格式 YYYY MM DDThhmmss (例如，1997年-07-12T103508)。|  
|%datetime_bts2000%|YYYYMMDDhhmmsss 格式的 UTC 日期时间，其中，sss 表示秒和毫秒（例如，199707121035234 表示 1997/07/12 10:35:23 和 400 毫秒）。|  
|%datetime.tz%|本地日期时间加上 GMT 时区，格式为 YYYY-MM-DDThhmmssTZD（例如 1997-07-12T103508+800）。|  
|%DestinationParty%|目标参与方的名称。 该值来自消息上下文属性 **BTS.DestinationParty**。|  
|%DestinationPartyQualifier%|目标参与方的限定符。 该值来自消息上下文属性 **BTS.DestinationPartyQualifier**。|  
|%MessageID%|BizTalk Server 中消息的全局唯一标识符 (GUID)。 该值直接来自消息上下文属性**BTS。MessageID**。|  
|%SourceFileName%|文件适配器从中读取消息的文件的名称。 文件名包括扩展和排除的文件路径，例如 Sample.xml。 文件适配器在替代此属性，从存储中的绝对文件路径提取文件名**文件。ReceivedFileName**上下文属性。 如果上下文属性的值 — 例如，如果文件适配器之外的适配器上接收的消息 — 宏将不进行替换，并将保持原样的文件名称中 (例如，C:\Drop\\%sourcefilename%)。 **注意：** 此宏的正确实现需要输出消息为收到的消息的消息相同。|  
|%SourceParty%|文件适配器从其接收消息的源参与方的名称。 **注意：** 此宏的正确实现需要输出消息为收到的消息的消息相同。|  
|%SourcePartyQualifier%|文件适配器从其接收消息的源参与方的限定符。 **注意：** 此宏的正确实现需要输出消息为收到的消息的消息相同。|  
|%time%|hhmmss 格式的 UTC 时间。|  
|%time.tz%|本地时间加上 GMT 时区，格式为 hhmmssTZD（例如 124525+530）。|  
  
 
## <a name="receive-folder-and-destination-location-properties-gotchas"></a>接收文件夹和目标位置属性难题

File 接收位置是一个字符串，包含文件系统上的文件夹的路径或网络共享的文件接收处理程序读取文件。 文件目标位置是一个字符串，包含文件系统上的文件夹的路径或网络共享，文件发送处理程序会将文件写入。  
  
 以下限制适用于接收文件夹和目标位置属性：  
  
- 当用户在指定属性时则不需要的文件系统或网络共享上的文件路径存在。  
  
- 必须始终为绝对文件路径。  
  
- 可以通过使用通用命名约定 (UNC) 格式指定的文件路径 (例如， \\ \\ < *server* \> \\ < *共享*\>)。  
  
- 如果文件路径采用 UNC 格式，服务器名称不得包含以下字符: ' ~ ！ @ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< \> / ? ;  
  
- 不能使用父 (\\...\\) 和当前 (\\。\\) 文件夹中的文件路径的任何部分的符号。  
  
- 文件路径不区分大小写。  
  
- 文件路径不能包含任何以下字符： \< \> : / &#124; "？ * ;  
  
- 不能在文件路径中使用以下保留的设备名称：CON、 PRN、 AUX、 时钟 $、 NUL、 COM1、 COM2、 COM3、 COM4、 COM5、 COM6、 COM7、 COM8、 COM9、 LPT1、 LPT2、 LPT3、 LPT4、 LPT5、 LPT6、 LPT7、 LPT8 和 LPT9。  
  
- 文件路径、 文件掩码或文件名 （没有宏替换） 的总长度不能超过 256 个字符。 （MessageBox 数据库规定了此限制。）  
  
- 文件适配器不支持 Unicode 规范的文件路径 (例如，"\\\\？\\")。  
  
  对接收文件夹属性的限制：  
  
- 未设置接收文件夹属性为使用 Microsoft Windows NT 分布式文件系统的带符号链接的文件夹。 如果使用的 Windows NT 分布式文件系统，则可以仅使用文件夹具有直接网络路径在文件适配器接收位置。  
  
- 文档发送到 UNC 路径时，你有多个服务器接收文件适配器的接收位置的文档时，只有一台服务器将选取并处理的大多数文档发送到该 UNC 路径。 有关文件重命名的详细信息，请参阅文件接收适配器的一部分[文件适配器](../core/file-adapter.md)。  
  
  限制只发送文件夹属性：  
  
- 文件适配器可能没有足够的操作系统资源来同时处理所有批中消息的 Microsoft Windows Vista 等非服务器操作系统上运行。  
  
  文件适配器在设计时通过使用前面所述的规则来验证文件路径。 此外，文件适配器验证消息在运行时如果适配器使用文件适配器通过动态端口发送消息。  
  
