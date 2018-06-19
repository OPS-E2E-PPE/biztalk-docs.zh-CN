---
title: 导入 SAP 数据使用 SQL Server Management Studio |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- SQL Server Management Studio, importing data
ms.assetid: c8151c6d-4b33-40fe-9b83-9bed27df9a99
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28981d2130e82a094e470de1e2b6904382be56b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217829"
---
# <a name="import-sap-data-using-sql-server-management-studio"></a>使用 SQL Server Management Studio 导入 SAP 数据
此部分提供有关如何使用 SQL Server Management Studio 从某个 SAP 系统到 SQL Server 数据库导入数据的信息。 本部分提供有关如何创建 SSIS 包，您可以执行数据导入指令。 本部分还提供有关如何执行 SSIS 包的信息。  
  
## <a name="prerequisites"></a>先决条件  
 执行本主题中提供过程之前，请确保：  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]计算机上安装。  
  
-   在计算机上安装 SQL Server Business Intelligence Development Studio。  
  
### <a name="to-import-data-using-sql-server-management-studio"></a>若要使用 SQL Server Management Studio 导入数据  
  
1.  启动 SQL Server Management Studio。  
  
2.  在**连接到服务器**对话框框中，指定的值连接到 SQL Server 数据库并单击**连接**。 **Microsoft SQL Server Management Studio**打开。  
  
3.  在**对象资源管理器**，展开 SQL Server 名称，展开**数据库**，然后右键单击在其中你将会导出表从 SAP 系统数据库。 从上下文菜单中，指向**任务**，然后单击**导入数据**。 这将启动**SQL Server 导入和导出向导**。  
  
4.  阅读欢迎屏幕，然后单击上的信息**下一步**。  
  
5.  在**选择数据源**对话框中，从**数据源**下拉列表**mySAP Business Suite 的.NET Framework 数据提供程序**。 该对话框列出要连接到 SAP 系统的不同的连接参数。 一个典型的连接字符串以连接到 SAP 系统使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要：  
  
    -   连接类型的连接参数。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持连接类型 A、 B 和 d。若要连接到 SAP 系统必须提供连接参数任何*一个*的这些连接类型。 例如，对于 A 的连接类型，必须提供应用程序服务器主机和系统编号的名称。  
  
    -   要连接到 SAP 系统如用户名和密码的登录信息。  
  
     有关连接字符串以连接到 SAP 系统使用的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 连接字符串中读取有关数据提供程序](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
     在**选择数据源**对话框框中，指定：  
  
    -   连接类型的参数的任何一个连接。  
  
    -   要连接到 SAP 系统的登录信息。  
  
    -   是否想要启用 SAP GUI 调试。  
  
    -   是否想要使用 RFC SDK 跟踪。  
  
     单击 **“下一步”**。  
  
6.  在**选择目标**对话框中：  
  
    1.  从**目标**下拉列表中，选择**SQL Native Client**。  
  
    2.  从**服务器名称**下拉列表中，选择 SQL server 名称。  
  
    3.  选择身份验证模式。  
  
    4.  从**数据库**下拉列表中，选择你想要导入 SAP 表的数据库。  
  
    5.  单击 **“下一步”**。  
  
7.  在**指定表复制或查询**对话框框中，选择**编写查询以指定要传输的数据**选项，然后单击**下一步**。  
  
8.  在**提供源查询**对话框框中，指定 SELECT 查询来筛选要导入到 SQL Server 的数据。 有关语法的详细信息，以进行 SELECT 查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[选择语句 SAP 语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。  
  
     单击**分析**按钮以验证查询，并单击**确定**在弹出对话框中。 单击 **“下一步”**。  
  
9. 在**选择源表和源视图**对话框框中，选中针对源和目标表的复选框。 源是您指定从 SAP 检索数据的查询。 目标是将在 SQL Server 数据库中创建的表。  
  
10. 该向导创建的源和目标之间的默认映射表字段。 但是，你可以根据你的要求更改映射。 若要更改的字段映射，请单击**编辑映射**。  
  
     ![SAP 和 SQL 表之间的列映射](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")  
  
11. 在**列映射**对话框中，你可以：  
  
    -   更改目标表中的列的名称。  
  
    -   忽略目标表中的某些列。  
  
    -   更改目标表中的字段的数据类型。  
  
    -   更改其他字段属性，如可以为 null，大小、 精度和小数位数。  
  
    -   单击 **“确定”**。  
  
12. 在**选择源表和源视图**对话框中，单击**下一步**。  
  
13. 在**保存和执行包**对话框中，  
  
    -   选择**立即执行**复选框，以执行查询。  
  
    -   选择**保存 SSIS 包**复选框以将查询另存为包和更高版本执行。 如果你选择以保存包，你还必须指定是否想要将包保存在 SQL Server 或文件系统。  
  
    -   从**包保护级别**下拉列表中，选择保护级别包并指定凭据需要。  
  
    -   单击 **“下一步”**。  
  
     如果你选择以保存包，则继续执行下一步。 否则，请跳到步骤 15。  
  
14. 在**保存 SSIS 包**对话框框中，指定：  
  
    -   包名称  
  
    -   程序包描述  
  
    -   如果你选择将包保存到 SQL server，选择从 SQL Server**服务器名称**下拉列表。  
  
    -   如果你选择将包保存到文件系统，指定的名称和位置中的文件**文件名**文本框。  
  
    -   单击 **“下一步”**。  
  
15. 在**完成向导**对话框框中，查看向导将执行，并单击的操作的摘要**完成**。  
  
16. 在**执行操作**对话框中，向导开始执行任务以将信息从 SAP 导入 SQL Server 数据库表。 在向导中显示每个任务的状态。  
  
17. 已成功执行所有任务后，单击**关闭**。 如果任务失败，请参阅相应的错误消息、 修复该问题，并重新运行该向导。  
  
## <a name="running-the-ssis-package"></a>运行 SSIS 包  
 如果你选择保存 SSIS 包，你可以运行它从 SAP 系统中检索的最新信息。 此部分提供有关如何运行包，如果你选择将其保存到文件系统信息。  
  
#### <a name="to-run-the-package-from-windows-explorer"></a>若要从 Windows 资源管理器运行包  
  
1.  从**Windows 资源管理器**，导航到保存包的位置，然后双击包。  
  
2.  上**执行包实用工具**对话框中，单击**执行**。  
  
3.  **包的执行进度**对话框中显示的不同任务的进度。  
  
4.  已成功执行所有任务后，单击**关闭**。  
  
5.  上**执行包实用工具**对话框中，单击**关闭**。  
  
 有关正在运行的包的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)。 有关相关的 SSIS 包的任何其他信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)。  
  
## <a name="verifying-the-results"></a>验证结果  
 后执行包，你必须通过转到 SAP 数据导入到的 SQL Server 数据库来验证结果。 执行包应已在目标数据库中创建一个表并使用 SAP 表中的值填充。  
  
## <a name="see-also"></a>另请参阅  
 [使用 Data Provider for SSIS 与 SAP](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)