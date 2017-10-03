---
title: "处理反汇编程序管道组件中编码 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], encoding
- pipeline components [custom], disassembling
ms.assetid: 33420357-421f-4ad0-8eee-d445376676db
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcbfb8f86847668436fae04db7bee1703dfb60ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="handling-encoding-in-a-disassembler-pipeline-component"></a>处理反汇编程序管道组件中编码
确保您的自定义拆装器组件采用如下格式之一对出站文档编码：  
  
-   UTF-8  
  
-   UTF 16  
  
-   UTF-32  
  
-   UTF-16LE  
  
-   UTF-16BE  
  
 业务流程引擎可能无法处理采用其他编码格式的文档。  
  
 .NET Framework 不支持 UTF-32LE 和 UTF-32BE；若要使用这些格式，您必须创建自定义编码实现。  
  
## <a name="see-also"></a>另请参阅  
 [开发分解的管道组件](../core/developing-a-disassembling-pipeline-component.md)