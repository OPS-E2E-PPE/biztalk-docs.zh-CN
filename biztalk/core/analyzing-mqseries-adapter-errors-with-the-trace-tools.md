---
title: 使用分析 MQSeries 适配器错误跟踪工具 |Microsoft Docs
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
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de3ac3f94edb6ca1c3f7f366ef5c0578eb69d76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999030"
---
# <a name="analyzing-mqseries-adapter-errors-with-the-trace-tools"></a>使用跟踪工具分析 MQSeries 适配器错误
在运行应用程序时，使用跟踪工具可以分析消息传送故障。 对于 MQSeries 适配器，您必须使用两个工具：一个用于该适配器和 BizTalk 应用程序 (trace.cmd)，另一个用于 MQSAgent (MQSTrace.cmd)。 这两个工具使用 tracelog.exe。 您必须安装 tracelog.exe，如果你还没有它。  

 使用 trace.cmd 和 mqstrace.cmd 时您必须设置一个选项 (**-工具**)，以便这些工具能够找到 tracelog.exe 文件。  

## <a name="install-the-trace-utility"></a>安装跟踪实用工具  
 若要安装 BizTalk 适配器跟踪实用工具，请按照以下步骤操作：  

1.  若要下载 Tracelog.exe 文件，请访问 Microsoft Platform SDK 下载网站上[ http://go.microsoft.com/fwlink/?LinkId=21975 ](http://go.microsoft.com/fwlink/?LinkId=21975)。  

2.  首先单击的链接的 Platform SDK Web 安装程序**PSDK-x86.exe** Web 页面底部的文件。  

3.  出现提示时，选择自定义安装选项。  

4.  在“自定义安装”  对话框中，单击以清除所有可用的功能。  

5.  展开“Microsoft Windows Core SDK”  功能，然后展开“工具”  功能。  

6.  选择“工具 (Intel 64 位)”  功能，然后单击“将安装到本地硬盘” 。  

7.  先后单击“下一步” 两次  以启动安装。  

8.  找到*驱动器*:\\*MicrosoftPlatformSDKInstallationFolder\bin*文件夹，并复制 Tracelog.exe 文件的 Microsoft BizTalk Server 安装文件夹。 BizTalk Server 安装文件夹还包含 Trace.cmd 文件。  

## <a name="enable-the-trace-utility"></a>启用跟踪实用工具  
 若要在 BizTalk Server 中启用 BizTalk 适配器跟踪实用工具，请按照以下步骤操作：  

1.  将移动到包含 trace.cmd 的目录。 默认位置是 Microsoft BizTalk Server 目录。  

2.  键入以下命令（该命令将使用引号中的目录来替换您的计算机上包含 tracelog.exe 文件的目录），然后按 Enter：  

     **trace-tools"c:\Program Files\Microsoft SDK\Bin"**  

3.  转至包含 MQSTrace.cmd 的目录。  

4.  键入以下命令（该命令将使用引号中的目录来替换您的计算机上包含 tracelog.exe 文件的目录），然后按 Enter：  

     **MQSTrace-工具"c:\Program Files\Microsoft SDK\Bin"**  

## <a name="run-the-trace-utility"></a>运行跟踪实用工具  
 若要运行 BizTalk 适配器跟踪实用工具，请按照以下步骤操作：  

1. 在命令提示符处，键入**trace.cmd-start-high**，然后按 ENTER。  

2. 运行您的故障方案。  

3. 在命令提示符处，键入**trace.cmd-停止**，然后按 ENTER。  

4. bts2006.bin 文件包含了跟踪工具的输出。 请与 Microsoft 产品支持服务联系以进行分析。 有关详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=41645 ](http://go.microsoft.com/fwlink/?LinkId=41645)。  

   若要运行 MQSAgent 跟踪实用工具，请按照以下步骤操作：  

5. 在命令提示符处，键入**MQSTrace.cmd-start-high**，然后按 ENTER。  

6. 运行您的故障方案。  

7. 在命令提示符处，键入**MQSTrace.cmd-停止**。  

8. MQSAdapterTrace.bin 文件包含了跟踪工具的输出。 请与 Microsoft 产品支持服务联系以进行分析。 有关详细信息请参阅[ http://go.microsoft.com/fwlink/?LinkId=41645 ](http://go.microsoft.com/fwlink/?LinkId=41645)。
