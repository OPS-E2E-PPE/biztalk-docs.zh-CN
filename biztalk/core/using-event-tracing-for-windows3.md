---
title: 使用事件跟踪用于 Windows3 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- provider
- Receiver Logging Provider
- Transmitter Logging Provider
- controller application
- consumer application
- BTATIBCOEMSTrace command
- Event Tracing for Windows
ms.assetid: 71954431-2015-4d50-b69e-500c883b1e04
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dd37de9c38dce752f61b92e0240f7b2f2fff832
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984350"
---
# <a name="using-event-tracing-for-windows"></a>使用的 Windows 事件跟踪
用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器将错误、警告和信息消息记录到 Windows 事件查看器。 使用 Windows 事件跟踪 (ETW) 工具，可以看到更多的跟踪消息。 激活 ETW 后，会创建一个 *.etl 文件以接收这些消息。 该文件为二进制格式，必须将其转换为可读格式。 若要执行此操作，必须提供要解释的使用者应用程序\*.etl 文件，例如，tracerpt.exe 或 tracedmp.exe。 例如，tracerpt.exe 应用程序将转换\*.etl 文件到两个文本文件： summary.txt 和 dumpfile.csv。  
  
## <a name="etw-components"></a>ETW 组件  
 Windows 事件跟踪包括以下三个组件：  
  
- **控制器应用程序**： 激活和停用 （例如，tracelog.exe 或 logman.exe） 的提供程序。  
  
   设置 PATH 环境变量以指向 tracelog.exe 的位置。 这确保 BTATIBCO EMSTrace 调用可以在系统中找到 tracelog.exe。 默认情况下，BTATIBCO EMSTrace 搜索当前路径。  
  
  > [!NOTE]
  >  tracelog.exe 可以从 Microsoft SDK 中获得，并且与用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器提供的命令兼容。 若要使用 logman.exe，请参阅 logman 文档。  
  
- **使用者应用程序**： 读取记录的事件。  
  
   为了让使用者应用程序能够读取 etl 文件中的事件，Windows 事件跟踪必须将这些事件转储到该文件。 通常，当控制器停用跟踪时执行此操作。  
  
   若要使用使用者应用程序不停用跟踪的情况下，控制器必须激活使用实时选项时，跟踪\<实时\>=-rt。  
  
- **提供程序**： 提供的事件。  
  
   用于 TIBCO Enterprise Message Service 的 BizTalk 适配器包括三个不同的提供程序。 它们在 Windows Management Instrumentation (WMI) 中进行注册。 若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。  
  
  用于 TIBCO Enterprise Message Service 的 BizTalk 适配器具有允许您记录不同类型消息的提供程序：  
  
- **接收方日志记录提供程序**:\<跟踪元素\>交换机 **-接收方**。  
  
   使用 **-接收方**可以从在运行时由适配器接收的日志获取任何消息。  
  
- **发送器日志记录提供程序**:\<跟踪元素\>交换机 **-发送器**。  
  
   使用 **-发送器**可以获取从日志在运行时发送适配器的任何消息。  
  
### <a name="btatibcoemstrace-command"></a>BTATIBCOEMSTrace 命令  
 若要使用 ETW，运行用于 TIBCO Enterprise Message Service 命令，BTATIBCOEMSTrace.cmd 的 BizTalk 适配器。 如下所示使用此命令：  
  
```  
BTATIBCOEMSTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA TIBCOEMSTrace <Trace element> -stop  
```  
  
 其中：  
  
- **\<跟踪元素\>** （必需） 是一种的提供程序。  
  
  其选项如下：  
  
- **-发送器**  
  
- **-接收方**  
  
- **-启动、-停止**： 激活或停用该提供程序。  
  
- **-cir \<MB\>**： 文件的大小和类型。 **-cir**是循环文件。 **\<MB\>**： 大小以兆字节为单位。  
  
- **-seq \<MB\>**： 文件的大小和类型。 **-seq**是顺序文件。 **\<MB\>**： 大小以兆字节为单位。  
  
- **-rt**： 设置实时模式。  
  
- **日志文件**： 日志文件的名称 （c:\rtlog.etl 是默认值）。  
  
  例如：  
  
```  
BTATIBCOEMSTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCOEMSTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>请参阅  
 [TIBCO Enterprise Message Service 的疑难解答](../core/troubleshooting-tibco-enterprise-message-service.md)