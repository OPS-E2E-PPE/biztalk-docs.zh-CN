---
title: 使用事件跟踪用于 Windows2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- Event Tracing for Windows
ms.assetid: 88b91b74-2b2e-40e0-a3e9-1ebd6367abe8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8f022035dd432e818c02289246a2d3a43849557
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980768"
---
# <a name="using-event-tracing-for-windows"></a>使用的 Windows 事件跟踪
适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器将错误、警告和信息消息记录到 Windows 事件查看器中。 可以使用 Windows 事件跟踪 (ETW) 工具来查看更多的跟踪消息。 激活 ETW 后，会创建一个 *.etl 文件以接收这些消息。 该文件为二进制格式，必须将其转换为可读格式。 若要执行此操作，必须提供要解释的使用者应用程序\*.etl 文件： 例如，tracerpt.exe 或 tracedmp.exe。  
  
## <a name="etw-components"></a>ETW 组件  
 Windows 事件跟踪包括以下三个组件：  
  
- **控制器应用程序。** 激活和停用提供程序（例如 tracelog.exe 或 logman.exe）。  
  
   设置 PATH 环境变量以指向 tracelog.exe 的位置。 这可以确保 BTAJDEdwardsOneWorldTrace 调用可以在系统中找到 tracelog.exe。 默认情况下，BTAJDEdwardsOneWorldTrace 搜索当前路径。  
  
  > [!NOTE]
  >  tracelog.exe 可以从 Microsoft SDK 中获得，并与用于 JD Edwards OneWorld 的 BizTalk 适配器提供的命令兼容。 若要使用 logman.exe，请参阅 logman 文档。  
  
- **使用者应用程序。** 读取记录的事件。  
  
   为了让使用者应用程序能够读取 .etl 文件中的事件，Windows 事件跟踪必须将其转储到该文件中。 通常，该操作在控制器停用跟踪时完成。  
  
   若要使用使用者应用程序不停用跟踪的情况下，控制器必须激活使用实时选项时，跟踪**\<实时\>=-rt**。  
  
- **提供程序。** 提供事件。  
  
  用于 JD Edwards OneWorld 的 BizTalk 适配器包括五个不同的提供程序。 它们在 Windows Management Instrumentation (WMI) 中进行注册。 若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。  
  
  用于 JD Edwards OneWorld 的 BizTalk 适配器包含五种提供程序，允许您记录不同种类的消息：  
  
- **接收方日志记录提供程序。** \<跟踪元素\>交换机 **-接收方**。  
  
- **接收器 CastDetails 提供程序。** \<跟踪元素\>交换机 **-castDetailsReceive**。  
  
- **发送器日志记录提供程序。** \<跟踪元素\>交换机 **-发送器**。  
  
- **发送器 CastDetails 提供程序。** \<跟踪元素\>交换机 **-castDetailsTransmit**。  
  
- **管理日志记录提供程序。** \<跟踪元素\>交换机 **-管理**。  
  
  BTAJDEOneWorldTrace 命令  
  
  若要使用 ETW，运行用于 JD Edwards OneWorld 命令，BTAJDEOneWorldTrace.cmd 的 BizTalk 适配器。 如下所示使用此命令：  
  
```  
BTAJDEOneWorldTrace <Trace element> -start [-cir <MB>|   
      -seq <MB>] [-rt] logfile  
BTAJDEOneWorldTrace <Trace element> -stop  
```  
  
 其中：  
  
- **\<跟踪元素\>** （必需） 是一种的提供程序。  
  
- 其选项是：  
  
  -   **-castDetailsTransmit**  
  
  -   **-发送器**  
  
  -   **-castDetailsReceive**  
  
  -   **-接收方**  
  
  -   **-管理**  
  
  -   **-启动、-停止**： 激活或停用该提供程序。  
  
  -   **-cir \<MB\>**： 文件的大小和类型。 -cir 是循环文件。 \<MB\>: meg 中的大小。  
  
  -   **-seq \<MB\>**： 文件的大小和类型。 -seq 是顺序文件。 \<MB\>: meg 中的大小。  
  
  -   **-rt**： 设置实时模式。  
  
  -   **日志文件**： 日志文件的名称 （c:\rtlog.etl 是默认值）。  
  
  例如：  
  
```  
BTAJDEOneWorldTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEOneWorldTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>请参阅  
 [JD Edwards OneWorld 疑难解答](../core/troubleshooting-jd-edwards-oneworld.md)