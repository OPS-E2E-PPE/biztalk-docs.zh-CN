---
title: "使用 BizTalk 适配器跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- Adapter Trace Utility, running
- enabling, Adapter Trace Utility
ms.assetid: ddc6b2c7-9dee-43c1-950b-8fd580bfcb26
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45d83e1a250850d372c2e12c7ffebc79f823c287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-adapter-tracing"></a>使用 BizTalk 适配器跟踪
本主题介绍如何安装 Trace Log 工具以及如何启用 BizTalk 适配器跟踪。  
  
## <a name="install-the-trace-log-tool"></a>安装 Trace Log 工具  
  
#### <a name="to-install-the-trace-log-tool-tracelogexe"></a>安装 Trace Log 工具 (tracelog.exe)  
  
1.  从 [适用于 Windows Vista 的 Microsoft® Windows® 软件开发包更新](http://go.microsoft.com/fwlink/?LinkId=128279) 网站下载跟踪日志工具。  
  
    > [!NOTE]
    >  即使您运行的是 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，也要安装 6.0 版本的 SDK。 如果你安装**Windows Server 2008 的 Windows SDK 和.NET Framework 3.5**版本 (v。 6.1)，它将不安装跟踪日志工具。  
  
2.  通过在网页底部单击 **PSDK-x86.exe** 文件的链接，启动 **适用于 Windows Vista 的 Microsoft® Windows® 软件开发包更新** Web 安装程序。  
  
    > [!NOTE]
    >  如果您使用的是 64 位版本的 Windows，请为您的系统选择正确的下载文件。  
  
3.  在“选择安装类型”  对话框中，选择“自定义”  安装选项，然后单击“下一步” 。  
  
4.  接受默认安装位置，然后单击“下一步” 。  
  
5.  在“自定义安装”  对话框中，单击以清除所有可用的功能。  
  
6.  展开“Microsoft Windows Core SDK”  功能，然后展开“工具”  功能。  
  
7.  选择“工具 (Intel 64 位)”  功能，然后单击“将安装到本地硬盘” 。  
  
8.  先后单击“下一步” 两次  以启动安装。  
  
    > [!NOTE]
    >  安装 **适用于 Windows Vista 的 Microsoft® Windows® 软件开发包更新** 后，系统可能会提示您重新启动计算机，具体取决于您选择随跟踪日志工具一起安装的其他功能。 这是因为， **适用于 Windows Vista 的 Microsoft® Windows® 软件开发包更新** 的某些组件只有在完成重新启动后才能正常工作。 不需要重新启动即可使用 Trace Log 工具。  
  
## <a name="enable-biztalk-adapter-tracing-with-tracecmd"></a>使用 trace.cmd 启用 BizTalk 适配器跟踪  
  
#### <a name="to-enable-biztalk-adapter-tracing"></a>启用 BizTalk 适配器跟踪  
  
1.  在命令提示符下，将当前目录更改为目录其中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装。 默认情况下，[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 安装在 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] 目录中。  如果使用的是 64 位版本的 Windows 和 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，则安装路径为 [!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)]。  
  
2.  键入以下命令，然后按 Enter：  
  
     **跟踪-工具"的跟踪日志工具的路径"**  
  
     默认情况下，跟踪日志工具 (tracelog.exe) 位于 **C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin** 目录下。 如果使用的是 64 位版本的 Windows，则跟踪日志工具位于 **C:\Program Files (x86)\Microsoft SDKs\Windows\v6.0\Bin**下。  必须将 Trace Log 工具的路径用引号引起来。  
  
     例如，请键入以下命令，然后按 Enter：  
  
     **跟踪-工具"C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"**  
  
    > [!NOTE]
    >  **-tools** 开关向 Trace.cmd 文件指明 Tracelog.exe 文件的位置。  
    >   
    >  如果成功运行该命令，输出结果将类似于以下内容：  
    >   
    >  **跟踪 2.0-管理 BizTalk 2006 版本 Bits 跟踪。**  
    >   
    >  **设置到"C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"TRACE_TOOL_SEARCH_PATH**  
  
## <a name="capture-trace-output-with-tracecmd"></a>使用 trace.cmd 捕获跟踪输出  
  
#### <a name="to-capture-trace-output"></a>捕获跟踪输出  
  
1.  在命令提示符下，将当前目录更改为目录其中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装。  
  
2.  在命令提示符下，键入以下命令，然后按 Enter：  
  
     **跟踪-启动**  
  
3.  重现要捕获其跟踪输出的方案。  
  
4.  在命令提示符下，键入以下命令，然后按 Enter：  
  
     **跟踪-停止**  
  
5.  停止跟踪，名为的二进制文件后**Btstrace.bin**文件夹中生成其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。  
  
6.  将 **Btstrace.bin** 文件发送到 Microsoft 产品支持服务部门进行分析。  
  
## <a name="see-also"></a>另请参阅  
 [使用适配器](../core/using-adapters.md)   
 [故障排除 Windows SharePoint Services Adapter](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)