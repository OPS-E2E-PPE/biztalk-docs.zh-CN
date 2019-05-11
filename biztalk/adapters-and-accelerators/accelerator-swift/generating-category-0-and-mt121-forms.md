---
title: 生成类别 0 和 MT121 表单 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1470b8e1-0008-4f15-8958-ba4c7ecbffd8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15f79784a227833695068681e1738d901f263680
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377630"
---
# <a name="generating-category-0-and-mt121-forms"></a>生成类别 0 和 MT121 表单
类别 0 和 MT121 InfoPath 窗体生成需要不同的模板文件。 类别 0 窗体分为 5 个类别。 常规类别消息生成相同的方式完成 MT 类别的其余部分。 下面给出了其消息名称与其他 4 个类别的示例：  
  
-   **若要生成类别 0 GAHeader 窗体 （MT036、 MT042、 MT047、 MT072、 MT077 和 MT085）：**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\GAHeader” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f GAHeaderForms.txt\`  
  
-   **若要生成类别 0 NoTextBlocks 窗体 （MT035、 MT043、 MT048 和 MT049）：**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTextBlocks” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTextBlocksForms.txt`  
  
-   **若要生成类别 0 NoTrailer 窗体 (MT021):**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTrailer” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTrailerForms.txt`  
  
-   **若要生成类别 0 NoTrailerTextBlocks 窗体 (MT082):**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTrailerTextBlocks” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTrailerTextBlocks.txt`  
  
-   **若要生成类别 1 NoHeaderTextBlock 窗体 (MT121):**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\ NoHeaderTextBlock” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f NoHeaderTextBlockForms.txt`