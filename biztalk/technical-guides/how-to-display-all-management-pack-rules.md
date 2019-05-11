---
title: 如何显示所有管理包规则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7fdec550-6713-4f5f-8c04-d9218bf2df3c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c22102080d5852ab838ce8fa3ce1d421e9a42900
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253500"
---
# <a name="how-to-display-all-management-pack-rules"></a>如何显示所有管理包规则
使用以下过程显示已导入的管理包的规则的列表。 可以在 Office Excel 中查看规则的列表。  
  
### <a name="to-display-management-pack-rules"></a>若要显示管理包规则  
  
1.  在管理服务器中，单击**程序**，然后单击**System Center**。  
  
2.  单击**命令行界面**。  
  
3.  在命令外壳中，键入以下命令：   
    `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | export-csv "c:\rules.csv"`  
  
4.  创建一个.csv 文件。 可以在 Office Excel 中打开.csv 文件。  
  
    > [!NOTE]  
    >  在 Office Excel 中，您可能需要指定的.csv 文件是一个文本文件。