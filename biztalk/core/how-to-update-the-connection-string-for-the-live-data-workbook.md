---
title: 如何更新实时数据工作簿的连接字符串 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d2702fb-637c-46db-8b62-08ae15f983ba
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2813b4ce0f448c25d75e69b1001ca006608d5993
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383630"
---
# <a name="how-to-update-the-connection-string-for-the-live-data-workbook"></a>如何更新实时数据工作簿的连接字符串
当 BAM 主导入数据库移到另一台服务器时，必须更新 BAM 实时数据工作簿中的连接字符串以指向新的服务器。 您使用 BAM 外接程序 excel 进行此更新。  
  
### <a name="to-update-the-live-data-workbook-to-point-to-a-new-server"></a>若要更新实时数据工作簿，以指向新的服务器  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office Excel**。  
  
2.  单击**文件**菜单，并单击**打开**。 导航到 BAM 实时的数据工作簿，然后单击**打开**。  
  
3.  单击**BAM**中的菜单**外接程序**选项卡，然后依次**BAM 数据库连接**以打开**选择 BAM 数据库**对话框。  
  
4.  在中**SQL Server**文本框中，键入在其 BAM 主导入数据库当前的 SQL server 的名称。  
  
5.  选择从 BAM 主导入数据库**数据库名称**下拉列表。  
  
6.  单击 **“确定”** 关闭对话框。  
  
7.  保存该工作簿。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM](../core/managing-bam.md)   
 [用于 Excel 的 BAM 外接程序的使用要求](../core/requirements-for-using-the-bam-add-in-for-excel.md)