---
title: MT 消息示例 |Microsoft Docs
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
ms.openlocfilehash: d6406a5d1e11ddeefd0aeb86c0d350acf5892361
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378035"
---
# <a name="examples-of-mt-messages"></a>MT 消息示例
**要生成不同的 MT 消息的解决方案 （InfoPath 窗体模板） 的命令：**  
  
 以下示例要求"SWIFT 基本 Types.xsd"、"SWIFT 常见数据 Types.xsd","MT102.xsd"、"MT500.xsd"和"MT103.xsd"架构都在 c:\schemas。 这将为"C:\GeneratedForms"文件夹中的 InfoPath 窗体模板生成解决方案。 该解决方案的文件夹名称会与 InfoPath 窗体需要生成的消息的名称相同。 这些示例假定该实用程序已被放入"C:\FormGeneratorUtility2008"文件夹。 中的实用程序为所选的位置替换为下面的命令。  
  
-   **若要生成用于 MT103 架构的窗体：**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103`  
  
-   **若要生成用于 MT103、 MT102 和 MT500 架构的窗体：**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103 MT102 MT500`  
  
-   **若要生成用于 MT103 架构 （来自文件） 的窗体：**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f P1forms.txt`