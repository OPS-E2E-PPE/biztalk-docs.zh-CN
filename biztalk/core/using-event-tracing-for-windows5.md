---
title: "事件跟踪用于 Windows5 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW
- events, Event Tracing for Windows
- controller application
- ETW components
- consumer application
- Provider
- Event Tracing for Windows
- Event Tracing for Windows, components
- BTAPeopleSoftTrace command
ms.assetid: 330ef84b-5e2a-4b79-85a9-72271eb489d2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60a317dabd31bc1a6f37645c6b3fb2ce25d6de43
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="using-event-tracing-for-windows"></a>使用适用于 Windows 跟踪的事件
Microsoft BizTalk Adapter for PeopleSoft 企业将错误、 警告和信息消息记录到 Windows 事件查看器。 使用 Windows 事件跟踪 (ETW) 工具，可以看到更多的跟踪消息。 如果启用 ETW，将创建一个 *.etl 文件以接收消息。 该文件为二进制格式，必须经过转换才能进行读取。 若要执行此操作必须提供要解释的使用者应用程序\*.etl 文件; 例如，tracerpt.exe 或 tracedmp.exe。  
  
## <a name="etw-components"></a>ETW 组件  
 Windows 事件跟踪包括以下三个组件：  
  
-   **控制器应用程序**： 激活和停用的提供程序 （例如，tracelog.exe 或 logman.exe）。  
  
     设置 PATH 环境变量以指向 tracelog.exe 的位置。 这将确保`BTAPeopleSoftTrace`调用可以在系统中找到 tracelog.exe。 默认状态下，BTAPeopleSoftTrace 搜索当前路径。  
  
    > [!NOTE]
    >  tracelog.exe 可从 Microsoft SDK 获得，它与用于 PeopleSoft Enterprise 的 BizTalk 适配器提供的命令兼容。 若要使用 logman.exe，请参阅 logman 文档。  
  
-   **使用者应用程序**： 读取记录的事件。  
  
     为了让使用者应用程序能够读取 .etl 文件中的事件，Windows 事件跟踪必须将其转储到该文件中。 通常，当控制器停用跟踪时执行此操作。  
  
     若要使用使用者不停用跟踪的情况下，控制器必须激活了实时选项中，跟踪\<实时\>=-rt。  
  
-   **提供程序：**提供的事件。  
  
     用于 PeopleSoft Enterprise 的 BizTalk 适配器具有五个不同的提供程序。 它们在 Windows Management Instrumentation (WMI) 中进行注册。 若要查找中已注册的提供程序**root\WMI\EventTrace**路径，你可以使用 WMI CIM Studio 等工具。  
  
 用于 PeopleSoft Enterprise 的 BizTalk 适配器具有五个提供程序，从而允许您记录不同种类的消息：  
  
-   **接收方日志记录提供程序**:\<跟踪元素\>交换机**-接收方**。  
  
-   **接收方 CastDetails 提供程序**:\<跟踪元素\>交换机**-castDetailsReceive**。  
  
-   **发送器日志记录提供程序**:\<跟踪元素\>交换机**-发送器**。  
  
-   **发送器 CastDetails 提供程序**:\<跟踪元素\>交换机**-castDetailsTransmit**。  
  
-   **管理日志记录提供程序**:\<跟踪元素\>交换机**-管理**。  
  
## <a name="btapeoplesofttrace-command"></a>BTAPeopleSoftTrace 命令  
 若要使用 ETW，请运行适配器命令**BTAPeopleSoftTrace.cmd**。 如下所示使用此命令：  
  
```  
BTAPeopleSoftTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTAPeopleSoftTrace <Trace element> -stop  
```  
  
 其中：  
  
-   \<跟踪元素\>（必需） 是一种的提供程序。  
  
     选项如下：  
  
    -   **-castDetailsTransmit**  
  
    -   **-发送器**  
  
    -   **-castDetailsReceive**  
  
    -   **-接收方**  
  
    -   **-管理**  
  
    -   **-启动、-停止**： 激活或停用该提供程序。  
  
-   **-cir \<MB\>**： 大小和类型的文件。 -cir 是循环文件。 \<MB\>： 大小以兆字节为单位。  
  
-   **-seq \<MB\>**： 大小和类型的文件。 -seq 是顺序文件。 \<MB\>： 大小以兆字节为单位。  
  
-   **-rt**： 上设置的实时模式。  
  
-   **日志文件**: （C:\rtlog.etl 为默认值） 的日志文件的名称。  
  
 例如：  
  
```  
BTAPeopleSoftTrace -transmitter -start -cir 10 -rt C:\log\mylog.etl  
BTAPeopleSoftTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>另请参阅  
 [故障排除 PeopleSoft](../core/troubleshooting-peoplesoft.md)