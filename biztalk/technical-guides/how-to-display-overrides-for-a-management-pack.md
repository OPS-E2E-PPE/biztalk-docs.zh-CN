---
title: 如何显示管理包的替代 |Microsoft Docs
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
ms.openlocfilehash: bc2a40fde14001668f94549240643160fd1af73a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979654"
---
# <a name="how-to-display-overrides-for-a-management-pack"></a>如何显示管理包的替代
若要显示管理包的替代，请使用以下过程。  
  
### <a name="to-display-overrides-for-a-management-pack"></a>显示管理包的替代  
  
1. 在管理服务器中，单击**程序**，然后单击**System Center**。  
  
2. 单击**命令行界面**。  
  
3. 在命令外壳中，键入以下命令：   
   `$mp = get-scommanagementpack -DisplayName "Operations Manager Internal Library"`   
   `$mp.GetOverrides()`  
  
4. 创建一个.csv 文件。 可以在 Office Excel 中打开.csv 文件。  
  
   > [!NOTE]  
   >  在 Office Excel 中，您可能需要指定的.csv 文件是一个文本文件。  
  
   例如，以下命令将显示一个核心管理包替代：   
   `$mp = get-scommanagementpack -DisplayName "Contoso.BizTalk.Overrides.mp"`  
   `$mp.GetOverrides()`