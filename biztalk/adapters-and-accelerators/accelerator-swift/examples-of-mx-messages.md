---
title: MX 消息示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b592034f-2dd3-40e4-8f0b-eb6d65c38fff
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26d86af52d8f93986d7028977166df8cfb28045c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377887"
---
# <a name="examples-of-mx-messages"></a>MX 消息示例
命令行以生成不同 MX 消息的解决方案 （InfoPath 窗体模板）  
  
 以下示例要求在架构"pacs.004.001.01"和"pain.002.001.01"架构都在 c:\schemas。 这将为"C:\GeneratedForms"文件夹中的 InfoPath 窗体模板生成解决方案。 该解决方案的文件夹名称会与 InfoPath 窗体需要生成的消息的名称相同。 这些示例假定该实用程序已被放入"C:\Program Files\Microsoft BizTalk Accelerator 的 SWIFT\SDK\FormGeneratorUtility"文件夹。 中的实用程序为所选的位置替换为下面的命令。  
  
-   **若要生成用于 pacs.004.001.01 架构的窗体：**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01`  
  
-   **若要生成用于 pacs.004.001.01 和 pain.002.001.01 架构的窗体：**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01 pain.002.001.01`