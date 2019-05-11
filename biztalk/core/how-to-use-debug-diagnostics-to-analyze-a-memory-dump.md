---
title: 如何使用调试诊断分析内存转储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 986a91a7-feab-4014-bbd5-e8b966b8b841
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47b8818979a9d278323d97dae2d1436c1d169829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383412"
---
# <a name="how-to-use-debug-diagnostics-to-analyze-a-memory-dump"></a>如何使用调试诊断分析内存转储
IIS 诊断**调试诊断工具**包含一个功能，可以提供捕获的内存转储文件的基本分析。 若要执行的内存转储文件分析，请执行以下步骤。  
  
### <a name="to-analyze-the-dump-file"></a>若要分析转储文件  
  
1.  启动调试诊断工具**启动**，**程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。  
  
2.  单击**高级分析**选项卡。  
  
3.  下**可用分析脚本**单击此项可选择**崩溃/挂起分析器**以分析崩溃/挂起转储，或单击以选中**内存压力分析**分析内存怀疑泄漏内存的进程转储。  
  
4.  单击**添加数据文件**按钮以浏览到生成的转储文件，并单击**打开**按钮将转储文件添加到要分析数据文件的可能列表。  
  
5.  单击以选择已添加的转储文件。  
  
6.  单击**开始分析**按钮。  
  
    > [!NOTE]
    >  在分析器尝试找到并从 internet 下载适当的符号文件，如果在本地计算机上未安装符号文件。 如果 BTSNTSvc.exe 进程中正在执行自定义代码，更新**符号搜索路径表示调试**中可用的选项**文件夹和搜索路径**选项卡**选项 （& a)设置**对话框包括相应的符号文件。 单击**工具**菜单，然后选择**选项和设置**以显示**选项和设置**对话框。  
  
7.  分析完成后一个报表以.mht 文件格式生成，并在 Internet Explorer 中显示。 默认情况下此报表将保存到本地计算机的 \Program Files\IIS Resources\DebugDiag\Reports 目录。  
  
## <a name="see-also"></a>请参阅  
 [如何捕获 BizTalk 进程的内存转储](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)