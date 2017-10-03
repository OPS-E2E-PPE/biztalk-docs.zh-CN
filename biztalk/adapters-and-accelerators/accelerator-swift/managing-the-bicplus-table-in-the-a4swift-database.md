---
title: "管理 A4SWIFT 数据库中的 Bicplus 表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), Bicplus table
- A4SWIFT database, Bicplus table
- Bicplus table
ms.assetid: a255cdea-5ed4-4481-97f1-8425877a76d6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 730998918beb464b00b871f8ab04060a7cd59af6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-the-bicplus-table-in-the-a4swift-database"></a>管理 A4SWIFT 数据库中的 Bicplus 表
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]使用 BIC 条目的表来执行 BIC 验证。 此表可以是中的 Bicplus 表[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库或自定义数据库表。  
  
 若要管理此表，必须使用从 SWIFT BIC 值填充。 如果你使用自定义数据库，必须还将导出中的 SQL 视图[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到自定义数据库的数据库。  
  
## <a name="importing-bic-data-from-the-swift-bicplus-database"></a>从 SWIFT Bicplus 数据库导入 BIC 数据  
 你必须填充 BIC 条目 （默认值或自定义的表） 中 SWIFT BIC 值的表。 SWIFT BIC 数据可用于[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格或每月更新 Oracle 数据库中。 SWIFT BIC 数据有关的详细信息，请转到[http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)。  
  
 如果你使用自定义数据库，必须将 BIC 数据从 SWIFT Bicplus 数据库导出到自定义的数据库。 你必须  
  
 你可以将数据从 BIC [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] SWIFT Bicplus 表中提供的电子表格[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，因为它们互相兼容。 如果你导入数据从 SWIFT 电子表格到非[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，请确保字段和数据库，尤其是 BIC 列中的列与 SWIFT 电子表格兼容。  
  
 在其发布 SWIFT 表中的代码更新目标表时，导入操作不会删除任何未发布的 BIC 代码。  
  
 向的 Bicplus 表所做的更改[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库登录[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]日志文件。  
  
#### <a name="to-import-bic-data-from-the-swift-bicplus-database"></a>若要从 SWIFT Bicplus 数据库导入 BIC 数据  
  
1.  单击**启动**，指向**所有程序**，指向 inistalled 版本的 SQL Server，然后单击**SQL Server Management Studio**。  
  
2.  在连接到服务器对话框中，单击**连接**。  
  
3.  在 Microsoft SQL Server Management Studio 窗口中，展开服务器节点，然后**数据库**。  
  
4.  右键单击**A4SWIFT**，指向**任务**，然后单击**导入数据**。  
  
5.  在 SQL Server 导入和导出向导欢迎页上，单击**下一步**。  
  
6.  上**选择数据源**页上，如果从 SWIFT Bicplus 导入 BIC 数据[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格中，选择**Microsoft Excel**中**数据源**文本框。 浏览到的位置电子表格中，然后选择电子表格中的文件名称**Excel 文件路径**文本框。 单击 **“下一步”**。  
  
     如果 BIC 数据导入从 Oracle 数据库中，选择**Microsoft ODBC Driver for Oracle**中**数据源**文本框。 输入与 Oracle 数据库的用户名和密码以连接到该服务器，然后单击所需的服务器**下一步**。  
  
7.  上**选择目标**页上，确认**Microsoft OLE DB Provider for SQL Server**中输入**目标**文本框中，且**使用Windows 身份验证**选择。 如果您在安装中的 Bicplus 表[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，请验证**A4SWIFT**中输入**数据库**文本框。 如果你使用的是自定义的数据库，请输入在该数据库的名称**数据库**文本框。 单击 **“下一步”**。  
  
8.  上**选择表复制或查询**页上，确认**将数据从一个或多个表或视图复制**选择。 如果你需要使用查询来指定数据，请选择**编写查询以指定要传输的数据**。 单击 **“下一步”**。  
  
9. 上**选择源表和源视图**页上，单击**Bicplus**中**源**列中，选择**Bicplus**中**目标**列，，然后单击**下一步**。  
  
10. 上**保存和执行包**页上，输入适当的计划信息，然后单击**下一步**。  
  
11. 上**完成向导**页上，查看摘要，然后单击**完成**。  
  
## <a name="importing-sql-views-from-the-a4swift-database-into-a-custom-database"></a>将 SQL 视图从 A4SWIFT 数据库导入自定义数据库  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序将安装中的两个 SQL 视图[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库。 其中一个视图是为 8 个字符 BICs 和另一个是 11 个字符 BICs 有关。  
  
 如果使用自定义数据库，而不是[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，你必须将这些 SQL 视图导入自定义的数据库。 通过在查询分析器执行 CreateBICViews.sql 脚本执行此操作。 此脚本位于\<*驱动器*>: files\microsoft BizTalk Accelerator for SWIFT/脚本。  
  
#### <a name="to-import-sql-views-from-the-a4swift-database-into-a-custom-database"></a>若要将 SQL 视图从 A4SWIFT 数据库导入自定义数据库  
  
1.  在 Windows 资源管理器，移动到\<*驱动器*>: files\microsoft BizTalk Accelerator for SWIFT\Scripts。 双击**CreateBICViews.sql**。  
  
2.  在连接到服务器对话框中，单击**连接**。  
  
3.  在 Microsoft SQL Server Management Studio 窗口中，选择**A4SWIFT**在数据库文本框中。  
  
4.  在查询窗格中，如果名为"Bicplus"以外的表中存储了 BICs，查找**dbo。Bicplus**视图中**dbo。Bic11**，并将它更改为适当的表名称。 为视图执行相同的**dbo。Bic8**。  
  
5.  如果名为"BIC"以外的列中存储了 BICs，查找**BIC**中**选择**，**其中**，和**ORDER BY**子句，并将其更改为相应的列名称。  
  
6.  单击 **“执行”**。  
  
## <a name="see-also"></a>另请参阅  
 [启用的 Bank 标识符代码的验证](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)