---
title: 如何捕获 BizTalk 进程的内存转储 |Microsoft 文档
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
ms.openlocfilehash: f87ad0f4a3eb3a49ea789d45a707bbc8b46cb4c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247573"
---
# <a name="how-to-capture-a-memory-dump-of-a-biztalk-process"></a>如何捕获 BizTalk 进程的内存转储
在某些情况下，可能需要捕获 BizTalk Server 上运行的进程的内存转储，以对该进程执行深入分析。 在以下情况下可能需要对内存转储进行分析：  
  
-   在进程无响应时。  
  
-   在进程崩溃时。  
  
-   在进程泄漏内存时。  
  
 本部分介绍捕获适当类型的内存转储时应遵循的步骤。  
  
## <a name="installation-of-the-iis-diagnostics-toolkit"></a>安装 IIS 诊断工具包  
 此部分中的主题的每个需要使用**调试诊断工具**IIS 诊断工具包，若要捕获内存转储。 若要安装**调试诊断工具**的 IIS 诊断工具包，请按照下列步骤：  
  
1.  下载 IIS 诊断工具包从[Internet 信息服务诊断工具](http://go.microsoft.com/fwlink/?LinkId=64426)。  
  
2.  双击**iisdiag.msi**要启动 IIS 诊断工具包安装程序并选择包**自定义**安装类型。  
  
3.  在**自定义安装**对话框中，确保的选项**调试诊断工具 1.0**已启用并完成安装程序中的步骤。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何捕获非响应的进程内存转储](../core/how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive.md)  
  
-   [如何捕获所 Crashing 进程内存转储](../core/how-to-capture-a-memory-dump-of-a-process-that-is-crashing.md)  
  
-   [如何捕获泄露内存的进程内存转储](../core/how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory.md)  
  
-   [如何使用调试诊断分析内存转储](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)