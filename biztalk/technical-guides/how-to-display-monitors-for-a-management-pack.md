---
title: 如何显示管理包的监视器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7c4d2b3-9c01-40f5-b983-bf29a3a5cacc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d98cca640b7fa818ad49d3b9c95c3e3bdcbf5c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253477"
---
# <a name="how-to-display-monitors-for-a-management-pack"></a>如何显示管理包的监视器
若要管理包的监视器和替代使用命令行界面中显示的输出列表，请使用以下过程。  
  
### <a name="to-display-monitors-for-a-management-pack"></a>若要显示管理包的监视器  
  
1. 在管理服务器中，单击**程序**，然后单击**System Center。**  
  
2. 单击**命令行界面**。  
  
3. 在命令外壳中，键入以下命令：   
   `get-scommanagementpack –DisplayName “DisplayName” | get-scommonitor | export.csv filename`  
  
4. 创建一个.csv 文件。 可以在 Microsoft Office Excel 中打开.csv 文件。  
  
   > [!NOTE]  
   >  在 Excel 中，您可能需要指定的.csv 文件是一个文本文件。  
  
   例如，以下命令将检索数据与某一核心管理包关联的监视器：   
   `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-ScomMonitor | export-csv "c:\monitors.csv"`