---
title: MT 消息的示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 629042cc-b941-4c58-b0dd-ede056caf573
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73098c20aeb03e8013f7e20e04c8bb37ce31266e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208885"
---
# <a name="examples-of-mt-messages"></a>MT 消息的示例
**用于生成不同 MT 消息的解决方案 （InfoPath 表单模板） 的命令：**  
  
 下面的示例需要"SWIFT 基 Types.xsd"、"SWIFT 常见数据 Types.xsd","MT102.xsd"、"MT500.xsd"和"MT103.xsd"架构都位于 c:\schemas。 这将为"C:\GeneratedForms"文件夹中的 InfoPath 窗体模板生成解决方案。 解决方案的文件夹名称将与为其 InfoPath 窗体需要为其生成的消息的名称相同。 这些示例假定已置于"C:\FormGeneratorUtility2008"文件夹上的实用工具。 将你选择用于的实用程序中的位置下面的命令。  
  
-   **若要生成用于 MT103 架构的窗体：**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103`  
  
-   **若要生成用于 MT103、 MT102 和 MT500 架构的窗体：**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103 MT102 MT500`  
  
-   **若要生成用于 MT103 架构 （来自文件） 的窗体：**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f P1forms.txt`