---
title: 如何更新实时数据工作簿的连接字符串 |Microsoft 文档
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
ms.openlocfilehash: 60de5d1ae904bdefffcf490e3a39d000b28a341d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255309"
---
# <a name="how-to-update-the-connection-string-for-the-live-data-workbook"></a>如何更新实时数据工作簿的连接字符串
BAM 主导入数据库移动到另一个服务器时，必须更新 BAM 实时数据工作簿中的连接字符串以指向新的服务器。 你使用 BAM add-in for Excel 进行此更新。  
  
### <a name="to-update-the-live-data-workbook-to-point-to-a-new-server"></a>若要更新实时数据工作簿，以指向新的服务器  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office Excel**。  
  
2.  单击**文件**菜单，，然后单击**打开**。 导航到你 BAM 生存期的数据的工作簿并单击**打开**。  
  
3.  单击**BAM**菜单中的**外接程序**选项卡上，并依次**BAM 数据库连接**以打开**选择 BAM 数据库**对话框。  
  
4.  在**SQL Server**文本框中，键入驻留在其上 BAM 主导入数据库现在的 SQL server 的名称。  
  
5.  选择从 BAM 主导入数据库**数据库名称**下拉列表。  
  
6.  单击 **“确定”** 关闭对话框。  
  
7.  保存该工作簿。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM](../core/managing-bam.md)   
 [使用 for Excel 的 BAM 外接程序的要求](../core/requirements-for-using-the-bam-add-in-for-excel.md)