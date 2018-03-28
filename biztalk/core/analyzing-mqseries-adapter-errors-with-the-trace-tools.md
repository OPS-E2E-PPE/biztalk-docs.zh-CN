---
title: 分析跟踪工具 MQSeries 适配器错误 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, about Adapter Trace Utility
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- errors, MQSeries adapters
- MQSeries adapters, Adapter Trace Utility
- Adapter Trace Utility, running
- MQSeries adapters, errors
- Adapter Trace Utility
ms.assetid: fdc73d99-3b73-491d-9b2f-7064364fefa7
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b53d1d2c0bbe19c54804b553041f8dc9ae4db20c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="analyzing-mqseries-adapter-errors-with-the-trace-tools"></a>分析跟踪工具 MQSeries 适配器错误
在运行应用程序时，使用跟踪工具可以分析消息传送故障。 对于 MQSeries 适配器，您必须使用两个工具：一个用于该适配器和 BizTalk 应用程序 (trace.cmd)，另一个用于 MQSAgent (MQSTrace.cmd)。 这两种工具使用 tracelog.exe。 你必须安装 tracelog.exe，如果你还没有它。  
  
 你需要使用 trace.cmd 和 MQSTrace.cmd 设置选项 (**-工具**)，以便这些工具可以找到 tracelog.exe 文件。  
  
## <a name="install-the-trace-utility"></a>安装跟踪实用工具  
 若要安装 BizTalk 适配器跟踪实用工具，请按照以下步骤操作：  
  
1.  若要下载 Tracelog.exe 文件，请访问 Microsoft 平台 SDK 的下载网站： [ http://go.microsoft.com/fwlink/?LinkId=21975 ](http://go.microsoft.com/fwlink/?LinkId=21975)。  
  
2.  通过单击的链接来启动平台 SDK Web 安装程序 **PSDK x86.exe** Web 页面底部的文件。  
  
3.  出现提示时，选择自定义安装选项。  
  
4.  在“自定义安装”  对话框中，单击以清除所有可用的功能。  
  
5.  展开“Microsoft Windows Core SDK”  功能，然后展开“工具”  功能。  
  
6.  选择“工具 (Intel 64 位)”  功能，然后单击“将安装到本地硬盘” 。  
  
7.  先后单击“下一步” 两次  以启动安装。  
  
8.  找到 *驱动器*:\\*MicrosoftPlatformSDKInstallationFolder\bin* 文件夹，，然后将复制到 Microsoft BizTalk Server 安装文件夹的 Tracelog.exe 文件。 BizTalk Server 安装文件夹还包含 Trace.cmd 文件。  
  
## <a name="enable-the-trace-utility"></a>启用跟踪实用工具  
 若要在 BizTalk Server 中启用 BizTalk 适配器跟踪实用工具，请按照以下步骤操作：  
  
1.  将移动到包含 trace.cmd 的目录。 默认位置是 Microsoft BizTalk Server 目录。  
  
2.  键入以下命令（该命令将使用引号中的目录来替换您的计算机上包含 tracelog.exe 文件的目录），然后按 Enter：  
  
     **跟踪-工具"c:\Program Files\Microsoft SDK\Bin"**  
  
3.  转至包含 MQSTrace.cmd 的目录。  
  
4.  键入以下命令（该命令将使用引号中的目录来替换您的计算机上包含 tracelog.exe 文件的目录），然后按 Enter：  
  
     **MQSTrace-工具"c:\Program Files\Microsoft SDK\Bin"**  
  
## <a name="run-the-trace-utility"></a>运行跟踪实用工具  
 若要运行 BizTalk 适配器跟踪实用工具，请按照以下步骤操作：  
  
1.  在命令提示符处，键入 **trace.cmd-启动-高**, ，然后按 ENTER。  
  
2.  运行您的故障方案。  
  
3.  在命令提示符处，键入 **trace.cmd-停止**, ，然后按 ENTER。  
  
4.  bts2006.bin 文件包含了跟踪工具的输出。 请与 Microsoft 产品支持服务联系以进行分析。 有关详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=41645 ](http://go.microsoft.com/fwlink/?LinkId=41645)。  
  
 若要运行 MQSAgent 跟踪实用工具，请按照以下步骤操作：  
  
1.  在命令提示符处，键入 **MQSTrace.cmd-启动-高**, ，然后按 ENTER。  
  
2.  运行您的故障方案。  
  
3.  在命令提示符处，键入 **MQSTrace.cmd-停止**。  
  
4.  MQSAdapterTrace.bin 文件包含了跟踪工具的输出。 请与 Microsoft 产品支持服务联系以进行分析。 有关详细信息请参阅[ http://go.microsoft.com/fwlink/?LinkId=41645 ](http://go.microsoft.com/fwlink/?LinkId=41645)。