---
title: 事件跟踪用于 Windows2 |Microsoft 文档
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
ms.openlocfilehash: 3c5f610d75048b250fc90aba7f723cee39c4f2e1
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25974411"
---
# <a name="using-event-tracing-for-windows"></a>使用适用于 Windows 跟踪的事件
适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器将错误、警告和信息消息记录到 Windows 事件查看器中。 可以通过使用 Windows 事件跟踪 (ETW) 工具来查看其他跟踪消息。 激活 ETW 后，会创建一个 *.etl 文件以接收这些消息。 该文件为二进制格式，必须将其转换为可读格式。 若要执行此操作，你必须提供要解释的使用者应用程序 \*.etl 文件︰ 例如，tracerpt.exe 或 tracedmp.exe。  
  
## <a name="etw-components"></a>ETW 组件  
 Windows 事件跟踪包括以下三个组件：  
  
-   **控制器应用程序。** 激活和停用提供程序（例如 tracelog.exe 或 logman.exe）。  
  
     设置 PATH 环境变量以指向 tracelog.exe 的位置。 这可确保 BTAJDEdwardsOneWorldTrace 调用可以找到你的系统中的 tracelog.exe。 默认情况下，BTAJDEdwardsOneWorldTrace 搜索当前路径。  
  
    > [!NOTE]
    >  tracelog.exe 可以从 Microsoft SDK 中获得，并与用于 JD Edwards OneWorld 的 BizTalk 适配器提供的命令兼容。 若要使用 logman.exe，请参阅 logman 文档。  
  
-   **使用者应用程序。** 读取记录的事件。  
  
     为了让使用者应用程序能够读取 .etl 文件中的事件，Windows 事件跟踪必须将其转储到该文件中。 通常，该操作在控制器停用跟踪时完成。  
  
     若要使用使用者应用程序而无需停用跟踪，控制器必须激活跟踪与实时选项， **\<实时\>=-rt**。  
  
-   **提供程序。** 提供事件。  
  
 用于博士 Edwards OneWorld 的 BizTalk Adapter 包括五个不同的提供程序。 它们在 Windows Management Instrumentation (WMI) 中进行注册。 若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。  
  
 用于 JD Edwards OneWorld 的 BizTalk 适配器包含五种提供程序，允许您记录不同种类的消息：  
  
-   **接收方日志记录提供程序。** \<跟踪元素\>交换机 **-接收方**。  
  
-   **接收方 CastDetails 提供程序。** \<跟踪元素\>交换机 **-castDetailsReceive**。  
  
-   **发送器日志记录提供程序。** \<跟踪元素\>交换机 **-发送器**。  
  
-   **发送器 CastDetails 提供程序。** \<跟踪元素\>交换机 **-castDetailsTransmit**。  
  
-   **管理日志记录提供程序。** \<跟踪元素\>交换机 **-管理**。  
  
 BTAJDEOneWorldTrace 命令  
  
 若要使用 ETW，运行博士 Edwards OneWorld 命令，BTAJDEOneWorldTrace.cmd BizTalk 适配器。 如下所示使用此命令：  
  
```  
BTAJDEOneWorldTrace <Trace element> -start [-cir <MB>|   
      -seq <MB>] [-rt] logfile  
BTAJDEOneWorldTrace <Trace element> -stop  
```  
  
 其中：  
  
-   **\<跟踪元素\>** （必需） 是一种的提供程序。  
  
-   其选项为︰  
  
    -   **-castDetailsTransmit**  
  
    -   **-发送器**  
  
    -   **-castDetailsReceive**  
  
    -   **-接收方**  
  
    -   **-管理**  
  
    -   **-启动、-停止**︰ 激活或停用该提供程序。  
  
    -   **-cir \<MB\>**： 大小和类型的文件。 -cir 是循环文件。 \<MB\>: meg 中的大小。  
  
    -   **-seq \<MB\>**： 大小和类型的文件。 -seq 是顺序文件。 \<MB\>: meg 中的大小。  
  
    -   **-rt**︰ 上设置的实时模式。  
  
    -   **日志文件**︰ 日志文件的名称 （c:\rtlog.etl 是默认值）。  
  
 例如：  
  
```  
BTAJDEOneWorldTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEOneWorldTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>另请参阅  
 [故障排除博士 Edwards OneWorld](../core/troubleshooting-jd-edwards-oneworld.md)