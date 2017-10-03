---
title: "导入使用 Visual Studio 的 SAP 数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- importing SAP data, using Visual Studio
- Visual Studio, importing SAP data
ms.assetid: 70cce089-232d-4ab9-81bd-6b0d6f0097d7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1295f763815872bacedf2262f7c022d6813bd75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="import-sap-data-using-visual-studio"></a>使用 Visual Studio 的导入 SAP 数据
本部分提供有关如何使用 Microsoft 的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]从某个 SAP 系统到 SQL Server 数据库导入数据。 本部分提供有关如何创建 SSIS 包，您可以执行数据导入指令。 本部分还提供有关如何执行 SSIS 包的信息。  
  
## <a name="prerequisites"></a>先决条件  
 执行本主题中提供过程之前，请确保：  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]计算机上安装。  
  
-   [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]计算机上安装。  
  
### <a name="to-import-data-using-visual-studio"></a>若要使用 Visual Studio 导入数据  
  
1.  启动[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并创建一个集成服务项目。  
  
2.  从**项目**菜单上，选择**SSIS 导入和导出向导**。 这将启动**SQL Server 导入和导出向导**。  
  
3.  阅读欢迎屏幕，然后单击上的信息**下一步**。  
  
4.  在**选择数据源**对话框中，从**数据源**下拉列表**mySAP Business Suite 的.NET Framework 数据提供程序**。 该对话框列出要连接到 SAP 系统的不同的连接参数。 一个典型的连接字符串以连接到 SAP 系统使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要：  
  
    -   连接类型的连接参数。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持连接类型 A、 B 和 d。若要连接到 SAP 系统必须提供连接参数任何*一个*的这些连接类型。 例如，对于 A 的连接类型，必须提供应用程序服务器主机和系统编号的名称。  
  
    -   要连接到 SAP 系统如用户名和密码的登录信息。  
  
     有关连接字符串以连接到 SAP 系统使用的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 连接字符串中读取有关数据提供程序](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
     在**选择数据源**对话框框中，指定：  
  
    -   连接类型的参数的任何一个连接。  
  
    -   要连接到 SAP 系统的登录信息。  
  
    -   是否想要启用 SAP GUI 调试。  
  
    -   是否想要使用 RFC SDK 跟踪。  
  
     单击 **“下一步”**。  
  
5.  在**选择目标**对话框中：  
  
    1.  从**目标**下拉列表中，选择**SQL Native Client**。  
  
    2.  从**服务器名称**下拉列表中，选择 SQL server 名称。  
  
    3.  选择身份验证模式。  
  
    4.  从**数据库**下拉列表中，选择你想要导入 SAP 表的数据库。  
  
    5.  单击 **“下一步”**。  
  
6.  在**指定表复制或查询**对话框框中，选择**编写查询以指定要传输的数据**选项，然后单击**下一步**。  
  
7.  在**提供源查询**对话框框中，指定 SELECT 查询来筛选要导入到 SQL Server 的数据。 有关语法的详细信息，以进行 SELECT 查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[为 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。  
  
     单击**分析**按钮以验证查询，并单击**确定**在弹出对话框中。 单击 **“下一步”**。  
  
8.  在**选择源表和源视图**对话框框中，选中针对源和目标表的复选框。 源是您指定从 SAP 检索数据的查询。 目标是将在 SQL Server 数据库中创建的表。  
  
9. 该向导创建的源和目标之间的默认映射表字段。 但是，你可以根据你的要求更改映射。 若要更改的字段映射，请单击**编辑映射**。  
  
     ![SAP 和 SQL 表之间的列映射](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")  
  
10. 在**列映射**对话框中，你可以：  
  
    -   更改目标表中的列的名称。  
  
    -   忽略目标表中的某些列。  
  
    -   更改目标表中的字段的数据类型。  
  
    -   更改其他字段属性，如可以为 null，大小、 精度和小数位数。  
  
    -   单击 **“确定”**。  
  
11. 在**选择源表和源视图**对话框中，单击**下一步**。  
  
12. 在**完成向导**对话框框中，查看向导将执行，并单击的操作的摘要**完成**。  
  
13. 在**执行操作**对话框中，向导开始执行任务以将信息从 SAP 导入 SQL Server 数据库表。 在向导中显示每个任务的状态。  
  
14. 已成功执行所有任务后，单击**关闭**。 如果任务失败，请参阅相应的错误消息、 修复该问题，并重新运行该向导。  
  
15. 向导将 SSIS 包添加到你的集成服务项目。 保存集成服务项目。  
  
## <a name="running-the-ssis-package"></a>运行 SSIS 包  
 在集成服务项目内创建包后，你可以执行它从某个 SAP 系统到 SQL Server 数据库导入数据。 执行以下步骤来导入 SAP 数据执行包。  
  
#### <a name="to-run-the-package-from-visual-studio"></a>若要从 Visual Studio 运行包  
  
1.  导航到解决方案资源管理器中的 SSIS 包。  
  
2.  右键单击包名称并选择**执行包**。  
  
 有关正在运行的包的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)。 有关相关的 SSIS 包的任何其他信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)。  
  
## <a name="verifying-the-results"></a>验证结果  
 后执行包，你必须通过登录到 SQL Server 并导航到 SAP 数据导入到的数据库验证结果。 执行包应已在目标数据库中创建一个表并使用 SAP 表中的值填充。  
  
## <a name="see-also"></a>另请参阅  
 [为 SAP 使用 SSIS 中使用的数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)