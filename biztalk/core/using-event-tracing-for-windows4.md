---
title: 事件跟踪用于 Windows4 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- BTAJDEEnterpriseOneTrace command
- Event Tracing for Windows
ms.assetid: 5f07d317-5ae2-4d1e-a343-941f3079dc4b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e98340654df792b8ec58014d4804394b5a6c6099
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="using-event-tracing-for-windows"></a>使用适用于 Windows 跟踪的事件
适用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器将错误、警告和信息消息记录到 Windows 事件查看器中。 可以通过使用 Windows 事件跟踪 (ETW) 工具来查看其他跟踪消息。 激活 ETW 后，会创建一个 *.etl 文件以接收这些消息。 该文件为二进制格式，必须将其转换为可读格式。 若要执行此操作，你必须提供要解释的使用者应用程序 \*.etl 文件; 例如，tracerpt.exe 或 tracedmp.ex。 Tracept.exe 应用程序将转换 \*到两个文本文件的.etl: summary.txt 和 dumpfile.csv。  
  
## <a name="etw-components"></a>ETW 组件  
 Windows 事件跟踪包括以下三个组件：  
  
-   **控制器应用程序**。 激活和停用提供程序（例如 tracelog.exe 或 logman.exe）。  
  
     设置 PATH 环境变量以指向 tracelog.exe 的位置。 这可确保 BTAJDEEnterpriseOneTrace 调用可以找到你的系统中的 tracelog.exe。 默认情况下，BTAJDEEnterpriseOneTrace 搜索当前路径。  
  
> [!NOTE]
>  tracelog.exe 可以从 Microsoft SDK 中获得，并与用于 JD Edwards EnterpriseOne 的 BizTalk 适配器提供的命令兼容。 若要使用 logman.exe，请参阅 logman 文档。  
  
-   **使用者应用程序**。 读取记录的事件。 为了让使用者应用程序能够读取 etl 文件中的事件，Windows 事件跟踪必须将这些事件转储到该文件。 通常，该操作在控制器停用跟踪时完成。  
  
     若要使用使用者应用程序而无需停用跟踪，控制器必须激活跟踪与实时选项， **\<实时\>=-rt**。  
  
-   **提供程序**。 用于提供事件。 用于 JD Edwards EnterpriseOne 的 BizTalk 适配器包括三种不同的提供程序。 它们在 Windows Management Instrumentation (WMI) 中进行注册。 若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。  
  
 用于 JD Edwards EnterpriseOne 的 BizTalk 适配器包含三种提供程序，允许您记录不同种类的消息：  
  
-   **接收方日志记录提供程序**:\<跟踪元素\>交换机**-接收方**。 使用 **-接收方** 以获取日志收到的已适配器在运行时中的任何消息。  
  
-   **发送器日志记录提供程序**:\<跟踪元素\>交换机**-发送器**。 使用 **-发送器** 以获取已传输的适配器在运行时日志中的任何消息。  
  
-   **管理日志记录提供程序**:\<跟踪元素\>交换机**-管理**使用**-管理**若要获取生成日志中的任何消息期间浏览的服务器系统。  
  
### <a name="btajdeenterpriseonetrace-command"></a>BTAJDEEnterpriseOneTrace 命令  
 若要使用 ETW，请运行博士 Edwards EnterpriseOne 命令 BizTalk 适配器 **BTAJDEEnterpriseOneTrace.cmd**。 如下所示使用此命令：  
  
```  
BTAJDEEnterpriseOneTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTAJDEEnterpriseOneTrace <Trace element> -stop  
  
```  
  
 其中： **\<跟踪元素\>** （必需） 是一种的提供程序。  
  
 其选项为︰  
  
-   **-发送器**  
  
-   **-接收方**  
  
-   **-管理**  
  
-   **-启动、-停止**︰ 激活或停用该提供程序。  
  
-   **-cir \<MB\>**： 大小和类型的文件。 -cir 是循环文件。 \<MB\>: meg 中的大小。  
  
-   **-seq \<MB\>**： 大小和类型的文件。 -seq 是顺序文件。 \<MB\>: meg 中的大小。  
  
-   **-rt**︰ 上设置的实时模式。  
  
-   **日志文件**︰ 日志文件的名称 （c:\rtlog.etl 是默认值）。  
  
 例如：  
  
```  
BTAJDEEnterpriseOneTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEEnterpriseOneTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>另请参阅  
 [故障排除博士 Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md)