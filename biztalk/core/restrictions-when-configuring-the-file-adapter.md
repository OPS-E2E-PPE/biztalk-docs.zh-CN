---
title: 限制在配置文件适配器 |Microsoft 文档
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
ms.openlocfilehash: d6fbf9296e56db816277f9a7a348377bfa4b359d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975124"
---
# <a name="restrictions-when-configuring-the-file-adapter"></a>配置文件适配器时的限制
限制和规则时使用的文件适配器。

## <a name="file-mask-and-file-name-gotchas"></a>文件掩码和文件名称陷阱

文件掩码是一个字符串，用于指定文件接收处理程序将从接收位置提取的文件的类型。 文件名是一个字符串，用于指定文件发送处理程序将在其中写入消息的文件的名称。  
  
 文件名和文件掩码属性具有以下限制：  
  
-   每个接收位置或发送端口只能指定一个文件掩码或文件名。  
  
-   不允许将完整路径或部分路径与文件掩码或文件名一起使用。 文件掩码和文件名始终表示不带路径的名称。  
  
-   文件掩码和文件名不区分大小写。  
  
-   文件名称不能包含任何以下字符： \< \> : / &#124;" ? * ;  
  
-   文件掩码不能包含任何以下字符： \< \> : / &#124;" ; 
  
-   以下保留的设备名称不能作为文件的名称： CON、 PRN、 AUX、 时钟 $、 NUL、 COM1、 COM2、 COM3、 COM4、 COM5、 COM6、 COM7、 COM8、 COM9、 LPT1、 LPT2、 LPT3、 LPT4、 LPT5、 LPT6、 LPT7、 LPT8 和 LPT9。 此外，不允许使用这些保留名称与扩展名的任意组合。  
  
-   Windows 磁盘卷使用 8.3 （8.3 文件名） 默认情况下，使用短期和长期的文件的名称命名约定。 非系统磁盘卷禁用 8.3 文件名命名约定，并且因此仅使用长文件名。 

    启用 8.3 文件名后，文件和其文件扩展名地转换为短名称。 例如，`testabcdefgh.docx`获取转换为`testab~1.doc`。 请注意，将缩短文件名，并且文件扩展名将缩短从`.docx`到`doc`。

    此行为会影响如何文件适配器接收文件。 如果文件掩码设置为`*.xml`，然后文件匹配同时`*.xml`和`*.xmln`选取扩展。 

    若要查看是否对你的磁盘启用了 8.3 文件名命名约定，打开命令提示符，作为管理员，并键入`fsutil 8dot3name query c:`，或`fsutil 8dot3name query d:`，依次类推。 示例输出如下所示：

    ```
    C:\WINDOWS\system32>fsutil 8dot3name query c:
    The volume state is: 0 (8dot3 name creation is enabled).
    The registry state is: 2 (Per volume setting - the default).
    
    Based on the above two settings, 8dot3 name creation is enabled on c:
    ```
    
    文件适配器使用[FindFirstFile 函数](https://msdn.microsoft.com/library/windows/desktop/aa364418(v=vs.85).aspx)。 此函数包括具有短期和长期的文件名的搜索结果。 若要查看的短期和长期的文件名称的文件夹中，打开命令提示符处，转到文件夹，然后键入`dir /x`。 在命令提示符下，你可以键入`dir c:\foldername /x`。
    
    如果你更改 8dot3name 设置的卷上，新的文件将使用新的设置。 直到将它们移动，任何现有文件将保留其名称。 
    
    若要仅选取你预期的文件，并在更高版本的加载过程中获得更好的性能 （开销较低），则可能为最佳配置文件适配器，以使用卷其中 8dot3name 处于禁用状态。 
  
-   文件路径、文件掩码和文件名（没有宏替换）的总长度不能超过 256 个字符。 （这是 MessageBox 数据库的限制。）  
  
-   文件路径不能以“`\\`?”开头。  
  
-   网络映射驱动器号不能用在文件路径中，因为它们是基于用户会话的。  
  
 BizTalk 消息引擎在设计时始终通过使用前面列出的项来验证文件名和文件掩码属性。 此外，如果适配器在动态端口上发送消息，则文件适配器将在运行时验证文件名和文件掩码属性。  
  
> [!NOTE]
>  文件适配器不提取系统文件或只读文件。 只提取基于磁盘的文件，而不提取设备文件。  

## <a name="using-macros-in-file-names"></a>在文件名中使用宏

您可以使用预定义的宏集合动态创建文件发送处理程序在其中写入消息的文件。 在文件系统中创建文件之前，文件发送处理程序将使用单独的值来替换文件名中的所有宏。 可以在一个文件名中使用若干不同的宏。  
  
 在使用 BizTalk 浏览器对象模型配置文件发送处理程序时，可以使用文件名宏。  
  
 如果存在以下任何一种情况，文件发送处理程序将不会使用值替换宏：  
  
-   未设置相应的系统属性。  
  
-   宏拼写错误。  
  
-   宏的值所包含的符号在文件名中无效。  
  
 如果出现上述任何情况，文件发送处理程序都会将文件名中的宏保持不变，例如 Myfile_%MessageID%.xml。  
  
 下表列出了所支持的宏，并介绍文件发送处理程序如何替换这些宏：  
  
|宏名称|替代值|  
|----------------|----------------------|  
|%datetime%|YYYY-MM-DDThhmmss 格式的世界时 (UTC) 日期时间（例如 1997-07-12T103508）。|  
|%datetime_bts2000%|YYYYMMDDhhmmsss 格式的 UTC 日期时间，其中，sss 表示秒和毫秒（例如，199707121035234 表示 1997/07/12 10:35:23 和 400 毫秒）。|  
|%datetime.tz%|本地日期时间加上 GMT 时区，格式为 YYYY-MM-DDThhmmssTZD（例如 1997-07-12T103508+800）。|  
|%DestinationParty%|目标参与方的名称。 该值来自消息上下文属性 **BTS.DestinationParty**。|  
|%DestinationPartyQualifier%|目标参与方的限定符。 该值来自消息上下文属性 **BTS.DestinationPartyQualifier**。|  
|%MessageID%|BizTalk Server 中消息的全局唯一标识符 (GUID)。 值直接来自消息上下文属性**BTS。MessageID**。|  
|%SourceFileName%|文件适配器从中读取消息的文件的名称。 文件名称包括扩展名，并排除的文件路径，例如，Sample.xml。 文件适配器时替换此属性，从存储中的绝对文件路径中提取的文件名称**文件。ReceivedFileName**上下文属性。 如果上下文属性不具有值-例如，如果而不是文件适配器适配器上接收的消息 — 宏将不会替换，并且将保持原样的文件名称中 (例如，C:\Drop\\%sourcefilename%)。 **注意：** 此宏的正确实现需要输出消息是作为对收到的消息，同一消息。|  
|%SourceParty%|文件适配器从其接收消息的源参与方的名称。 **注意：** 此宏的正确实现需要输出消息是作为对收到的消息，同一消息。|  
|%SourcePartyQualifier%|文件适配器从其接收消息的源参与方的限定符。 **注意：** 此宏的正确实现需要输出消息是作为对收到的消息，同一消息。|  
|%time%|hhmmss 格式的 UTC 时间。|  
|%time.tz%|本地时间加上 GMT 时区，格式为 hhmmssTZD（例如 124525+530）。|  
  
 
## <a name="receive-folder-and-destination-location-properties-gotchas"></a>接收文件夹和目标位置属性陷阱

文件接收位置字符串包含指向文件接收处理程序从中读取文件的文件系统或网络共享位置上文件夹的路径。 文件目标位置字符串包含指向文件发送处理程序要向其中写入文件的文件系统或网络共享位置上文件夹的路径。  
  
 接收文件夹和目标位置属性具有以下限制：  
  
-   当在用户指定属性时则不需要的文件系统或网络共享上的文件路径存在。  
  
-   文件路径始终必须是绝对路径。  
  
-   你可以使用通用命名约定 (UNC) 格式指定的文件路径 (例如， \\ \\ <*服务器*\> \\ < *共享*\>)。  
  
-   如果该文件路径是 UNC 格式，服务器名称不得包含以下字符: ' ~ ！ @ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< \> / ? ;  
  
-   不能使用父 (\\...\\) 和当前 (\\。\\) 文件夹中的文件路径的任何部分的符号。  
  
-   文件路径不区分大小写。  
  
-   文件路径不能包含任何以下字符： \< \> : / &#124;" ? * ;  
  
-   在文件路径中不能使用以下保留的设备名称：CON、PRN、AUX、CLOCK$、NUL、COM1、COM2、COM3、COM4、COM5、COM6、COM7、COM8、COM9、LPT1、LPT2、LPT3、LPT4、LPT5、LPT6、LPT7、LPT8 和 LPT9。  
  
-   文件路径、文件掩码或文件名（没有宏替换）的总长度不能超过 256 个字符。 （MessageBox 数据库规定了此限制。）  
  
-   文件适配器不支持 Unicode 规范的文件路径 (例如，"\\\\？\\")。  
  
 以下限制只适用于接收文件夹属性：  
  
-   请不要将接收文件夹属性设置为使用 Microsoft Windows NT 分布式文件系统的带符号链接的文件夹 。 如果使用 Windows NT 分布式文件系统 ， 则在文件适配器接收位置中只能使用具有直接网络路径的文件夹 。  
  
-   如果将文档发送到 UNC 路径，并且有多台服务器通过文件适配器的接收位置接收文档，则只有一台服务器将提取并处理发送到该 UNC 路径的大多数文档。 有关重命名文件的详细信息，请参阅的文件接收适配器部分[文件适配器](../core/file-adapter.md)。  
  
 以下限制只适用于发送文件夹属性：  
  
-   文件适配器可能没有足够的操作系统资源来处理所有批处理中的消息，同时在非服务器操作系统如 Microsoft Windows Vista 上运行时。  
  
 文件适配器将在设计时通过使用上文所述的规则对文件路径进行验证。 此外，如果文件适配器通过动态端口发送消息，还会在运行时对消息进行验证。  
  
