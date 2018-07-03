---
title: 如何捕获 BizTalk 进程的内存转储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8053fcf3-b331-4245-b3c3-21290463e0c0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3643dab17f8d1592f1e5fddce30aa12e537c817
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969134"
---
# <a name="how-to-capture-a-memory-dump-of-a-biztalk-process"></a>如何捕获 BizTalk 进程的内存转储
在某些情况下，可能需要捕获 BizTalk Server 上运行的进程的内存转储，以对该进程执行深入分析。 在以下情况下可能需要对内存转储进行分析：  
  
- 在进程无响应时。  
  
- 在进程崩溃时。  
  
- 在进程泄漏内存时。  
  
  本部分介绍捕获适当类型的内存转储时应遵循的步骤。  
  
## <a name="installation-of-the-iis-diagnostics-toolkit"></a>安装 IIS 诊断工具包  
 在本部分中的主题的每个需要使用**调试诊断工具**IIS 诊断工具包工具捕获内存转储。 若要安装**调试诊断工具**IIS 诊断工具包，请执行以下步骤：  
  
1.  下载 IIS 诊断工具包从[Internet 信息服务诊断工具](http://go.microsoft.com/fwlink/?LinkId=64426)。  
  
2.  双击**iisdiag.msi**要启动 IIS 诊断工具包安装程序并选择包**自定义**安装类型。  
  
3.  在中**自定义安装**对话框中，确保为选项**调试诊断工具 1.0** ，并完成安装程序中的步骤。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何捕获的非响应进程的内存转储](../core/how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive.md)  
  
-   [如何捕获 Crashing 的进程的内存转储](../core/how-to-capture-a-memory-dump-of-a-process-that-is-crashing.md)  
  
-   [如何捕获泄漏内存的进程的内存转储](../core/how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory.md)  
  
-   [如何使用调试诊断分析内存转储](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)