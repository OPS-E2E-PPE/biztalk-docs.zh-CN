---
title: "如何显示所有管理包规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fdec550-6713-4f5f-8c04-d9218bf2df3c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08ec94eb3adb87bf6feaff032e00a61bc9b0fead
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-all-management-pack-rules"></a>如何显示所有管理包规则
使用以下过程显示你导入的管理包的规则的列表。 可以在 Office Excel 中查看的规则的列表。  
  
### <a name="to-display-management-pack-rules"></a>若要显示管理包规则  
  
1.  在管理服务器中，单击**程序**，然后单击**System Center**。  
  
2.  单击**命令行界面**。  
  
3.  在命令外壳中，键入以下命令：   
    `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | export-csv "c:\rules.csv"`  
  
4.  创建一个.csv 文件。 你可以在 Office Excel 中打开该.csv 文件。  
  
    > [!NOTE]  
    >  在 Office Excel 中，你可能需要将指定的.csv 文件是一个文本文件。