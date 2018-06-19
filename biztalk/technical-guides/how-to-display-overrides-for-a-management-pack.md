---
title: 如何显示管理包的替代 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8261a514-b4c4-4e6b-ac35-40a3e3e090e0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a28c4ab2ef8f82fdd770203816239ad78e74418e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297685"
---
# <a name="how-to-display-overrides-for-a-management-pack"></a>如何显示管理包的替代
若要显示管理包的替代，请使用以下过程。  
  
### <a name="to-display-overrides-for-a-management-pack"></a>显示管理包的替代  
  
1.  在管理服务器中，单击**程序**，然后单击**System Center**。  
  
2.  单击**命令行界面**。  
  
3.  在命令外壳中，键入以下命令：   
    `$mp = get-scommanagementpack -DisplayName "Operations Manager Internal Library"`   
    `$mp.GetOverrides()`  
  
4.  创建一个.csv 文件。 该.csv 文件可以在 Office Excel 中打开。  
  
    > [!NOTE]  
    >  在 Office Excel 中，你可能需要将指定的.csv 文件是一个文本文件。  
  
 例如，下面的命令显示某一核心管理包的替代：   
`$mp = get-scommanagementpack -DisplayName "Contoso.BizTalk.Overrides.mp"`  
`$mp.GetOverrides()`