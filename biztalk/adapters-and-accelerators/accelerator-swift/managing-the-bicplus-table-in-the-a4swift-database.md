---
title: 管理 Bicplus 表在 A4SWIFT 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), Bicplus table
- A4SWIFT database, Bicplus table
- Bicplus table
ms.assetid: a255cdea-5ed4-4481-97f1-8425877a76d6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a3988a7b86d3f31365019c10cdfb640313dc2d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010678"
---
# <a name="managing-the-bicplus-table-in-the-a4swift-database"></a>管理 Bicplus 表 A4SWIFT 数据库中
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 使用 BIC 条目的表来执行 BIC 验证。 此表，可以在 Bicplus 表[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库或自定义数据库中的表。  
  
 若要管理此表，必须使用从 SWIFT BIC 值填充它。 如果使用自定义数据库，则必须导出中的 SQL 视图[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到自定义数据库的数据库。  
  
## <a name="importing-bic-data-from-the-swift-bicplus-database"></a>从 SWIFT Bicplus 数据库导入 BIC 数据  
 您必须填充 BIC 条目 （默认或自定义的表） 使用从 SWIFT BIC 值的表。 SWIFT BIC 数据现已推出[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格或 Oracle 数据库中每月进行更新。 SWIFT BIC 数据有关的详细信息，请转到[ http://go.microsoft.com/fwlink/?LinkId=27885 ](http://go.microsoft.com/fwlink/?LinkId=27885)。  
  
 如果使用自定义数据库，必须将 BIC 数据从 SWIFT Bicplus 数据库导出到自定义数据库。 您必须  
  
 可以从 BIC 导入数据[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格到 Bicplus 表中提供的 SWIFT[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，因为它们是否兼容。 如果您导入数据从 SWIFT 电子表格到非[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，请确保字段和数据库，尤其是 BIC 列中的列与 SWIFT 电子表格兼容。  
  
 与发布 SWIFT 表中的代码更新目标表时，导入操作不会删除任何未发布的 BIC 代码。  
  
 Bicplus 表所做的更改[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库中记录[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]日志文件。  
  
#### <a name="to-import-bic-data-from-the-swift-bicplus-database"></a>若要从 SWIFT Bicplus 数据库导入 BIC 数据  
  
1. 单击**启动**，依次指向**所有程序**，指向 SQL Server 的 inistalled 版本，然后单击**SQL Server Management Studio**。  
  
2. 在连接到服务器对话框中，单击**Connect**。  
  
3. 在 Microsoft SQL Server Management Studio 窗口中，展开服务器节点，然后**数据库**。  
  
4. 右键单击**A4SWIFT**，依次指向**任务**，然后单击**导入数据**。  
  
5. 在 SQL Server 导入和导出向导欢迎页上，单击**下一步**。  
  
6. 上**选择数据源**页上，如果 BIC 数据导入从 SWIFT Bicplus[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格中，选择**Microsoft Excel**中**数据源**文本框。 浏览到该电子表格的位置并选择该电子表格中的文件名**Excel 文件路径**文本框。 单击“下一步” 。  
  
    如果从 Oracle 数据库导入 BIC 数据，请选择**适用于 Oracle 的 Microsoft ODBC Driver**中**数据源**文本框。 输入与 Oracle 数据库的用户名和密码以连接到该服务器，然后单击所需的服务器**下一步**。  
  
7. 上**选择目标**页上，确认**Microsoft OLE DB Provider for SQL Server**中输入**目标**文本框中，并确保**使用Windows 身份验证**处于选中状态。 如果您在安装中的 Bicplus 表[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库中，确认**A4SWIFT**中输入**数据库**文本框。 如果使用自定义数据库，请输入在该数据库的名称**数据库**文本框。 单击“下一步” 。  
  
8. 上**选择表复制或查询**页上，确认**将数据从一个或多个表或视图复制**处于选中状态。 如果你需要使用查询指定的数据，请选择**编写查询以指定要传输的数据**。 单击“下一步” 。  
  
9. 上**选择源表和视图**页上，单击**Bicplus**中**源**列中，选择**Bicplus**中**目标**列中，并单击**下一步**。  
  
10. 上**保存并执行包**页上，输入适当的计划信息，然后单击**下一步**。  
  
11. 上**完成该向导**页上，查看摘要，然后单击**完成**。  
  
## <a name="importing-sql-views-from-the-a4swift-database-into-a-custom-database"></a>SQL 视图从 A4SWIFT 数据库导入自定义数据库  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序将安装中的两个 SQL 视图[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库。 其中一个视图是为八个字符 BICs 和另一个是有关 BICs 11 个字符。  
  
 如果使用自定义数据库，而不是[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，您必须导入自定义数据库的这些 SQL 视图。 通过在查询分析器执行 CreateBICViews.sql 脚本中执行操作。 此脚本位于\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT/脚本。  
  
#### <a name="to-import-sql-views-from-the-a4swift-database-into-a-custom-database"></a>若要从 A4SWIFT 数据库的 SQL 视图导入自定义数据库  
  
1.  在 Windows 资源管理器，转至\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\Scripts。 双击**CreateBICViews.sql**。  
  
2.  在连接到服务器对话框中，单击**Connect**。  
  
3.  在 Microsoft SQL Server Management Studio 窗口中，选择**A4SWIFT**在数据库文本框中。  
  
4.  在查询窗格中，如果名为"Bicplus"以外的表中存储了 BICs，找到**dbo。Bicplus**视图中**dbo。Bic11**，并将其更改为适当的表名称。 执行相同的视图**dbo。Bic8**。  
  
5.  如果名为"BIC"以外的列中存储了 BICs，查找**BIC**中**选择**，**其中**，以及**ORDER BY**子句，并将其更改为相应的列名称。  
  
6.  单击 **“执行”**。  
  
## <a name="see-also"></a>请参阅  
 [启用银行标识代码验证](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)