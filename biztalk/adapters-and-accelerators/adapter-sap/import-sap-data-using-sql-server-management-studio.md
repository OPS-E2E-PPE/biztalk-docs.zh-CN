---
title: 导入 SAP 数据使用 SQL Server Management Studio |Microsoft Docs
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
ms.openlocfilehash: 8fe6993334b54761b2a9081ffd7794edde18abe3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373346"
---
# <a name="import-sap-data-using-sql-server-management-studio"></a>使用 SQL Server Management Studio 导入 SAP 数据
本部分提供有关如何使用 SQL Server Management Studio 从 SAP 系统到 SQL Server 数据库导入数据的信息。 本部分提供有关如何创建 SSIS 包可执行导入数据的指令。 本部分还提供有关如何执行 SSIS 包的信息。  
  
## <a name="prerequisites"></a>先决条件  
 在执行之前在本主题中提供的过程，请确保：  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 在计算机上安装。  
  
- 在计算机上安装 SQL Server Business Intelligence Development Studio。  
  
### <a name="to-import-data-using-sql-server-management-studio"></a>若要使用 SQL Server Management Studio 导入数据  
  
1. 启动 SQL Server Management Studio。  
  
2. 在中**连接到服务器**对话框框中，指定值以连接到 SQL Server 数据库，然后单击**Connect**。 **Microsoft SQL Server Management Studio**随即打开。  
  
3. 在中**对象资源管理器**，展开 SQL Server 名称，展开**数据库**，并右键单击在其中你将会导出表从 SAP 系统的数据库。 从上下文菜单中，指向**任务**，然后单击**导入数据**。 这将启动**SQL Server 导入和导出向导**。  
  
4. 阅读欢迎屏幕并单击**下一步**。  
  
5. 在中**选择数据源**对话框中，从**数据源**下拉列表**mySAP Business Suite 的.NET Framework 数据提供程序**。 该对话框列出要连接到 SAP 系统的其他连接参数。 典型的连接字符串连接到 SAP 系统使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]要求：  
  
   - 连接类型的连接参数。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持连接类型 A、 B 和 d。若要连接到 SAP 系统必须提供连接参数的任何*一个*的这些连接类型。 例如，对于连接类型的必须提供应用程序服务器主机和系统编号的名称。  
  
   - 要连接到 SAP 系统，如用户名和密码的登录信息。  
  
     详细了解要连接到 SAP 系统使用的连接字符串[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[了解数据提供程序适用于 SAP 连接字符串](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
     在中**选择数据源**对话框框中，指定：  
  
   - 类型的任何一个连接的连接参数。  
  
   - 要连接到 SAP 系统的登录信息。  
  
   - 是否想要启用 SAP GUI 调试。  
  
   - 是否想要使用 RFC SDK 跟踪。  
  
     单击“下一步” 。  
  
6. 在中**选择目标**对话框：  
  
   1.  从**目标**下拉列表中，选择**SQL Native Client**。  
  
   2.  从**服务器名称**下拉列表中，选择 SQL server 名称。  
  
   3.  选择身份验证模式。  
  
   4.  从**数据库**下拉列表中，选择你想要导入 SAP 表的数据库。  
  
   5.  单击“下一步” 。  
  
7. 在中**指定表复制或查询**对话框框中，选择**编写查询以指定要传输的数据**选项，然后单击**下一步**。  
  
8. 在中**提供源查询**对话框框中，指定用于筛选要导入到 SQL Server 的数据的选择查询。 有关语法的详细信息，为 SELECT 查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[语法的选择语句 SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。  
  
    单击**分析**按钮以验证查询，并单击**确定**中弹出的对话框。 单击“下一步” 。  
  
9. 在中**选择源表和视图**对话框框中，选择源和目标表对应的复选框。 源是指定要从 SAP 检索数据的查询。 目标是将在 SQL Server 数据库中创建的表。  
  
10. 该向导创建的源和目标之间的默认映射表字段。 但是，您可以根据需要更改映射。 若要更改字段映射，请单击**编辑映射**。  
  
     ![SAP 和 SQL 表之间的列映射](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")  
  
11. 在中**列映射**对话框中，你可以：  
  
    -   更改目标表中的列的名称。  
  
    -   忽略某些列与目标表中。  
  
    -   更改目标表中的字段的数据类型。  
  
    -   更改其他字段属性，如可以为 null，大小、 精度和小数位数。  
  
    -   单击“确定” 。  
  
12. 在中**选择源表和视图**对话框中，单击**下一步**。  
  
13. 在中**保存并执行包**对话框中，  
  
    - 选择**立即执行**复选框，以执行查询。  
  
    - 选择**保存 SSIS 包**复选框以将查询另存为包和更高版本执行。 如果您选择保存包，您还必须指定想要将包保存在 SQL Server 或文件系统中。  
  
    - 从**包保护级别**下拉列表中，选择保护级别的包，并指定凭据所需的位置。  
  
    - 单击“下一步” 。  
  
      如果您选择保存包，请继续执行下一步。 否则，请跳到步骤 15。  
  
14. 在中**保存 SSIS 包**对话框框中，指定：  
  
    -   包名称  
  
    -   包描述  
  
    -   如果您选择将包保存到 SQL server，选择从一个 SQL Server**服务器名称**下拉列表。  
  
    -   如果您选择将包保存到文件系统中，指定的名称和位置中的文件**文件名**文本框。  
  
    -   单击“下一步” 。  
  
15. 在中**完成该向导**对话框框中，查看操作，该向导将执行，并单击摘要**完成**。  
  
16. 在中**正在执行操作**对话框中，该向导开始执行任务以将信息从 SAP 导入 SQL Server 数据库表。 在向导中显示每个任务的状态。  
  
17. 已成功执行所有任务后，单击**关闭**。 如果任务失败时，请参阅相应的错误消息、 修复该问题，并重新运行该向导。  
  
## <a name="running-the-ssis-package"></a>运行 SSIS 包  
 如果您选择保存 SSIS 包，可以运行它来从 SAP 系统中检索最新信息。 本部分提供有关如何运行包，如果您选择将其保存到文件系统的信息。  
  
#### <a name="to-run-the-package-from-windows-explorer"></a>若要从 Windows 资源管理器中运行包  
  
1. 从**Windows 资源管理器**，导航到保存包的位置，然后双击包。  
  
2. 上**执行包实用工具**对话框中，单击**Execute**。  
  
3. **包的执行进度**对话框中显示不同的任务的进度。  
  
4. 已成功执行所有任务后，单击**关闭**。  
  
5. 上**执行包实用工具**对话框中，单击**关闭**。  
  
   有关正在运行的包的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=94972 ](http://go.microsoft.com/fwlink/?LinkId=94972)。 SSIS 包与相关的任何其他信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=94973 ](http://go.microsoft.com/fwlink/?LinkId=94973)。  
  
## <a name="verifying-the-results"></a>验证结果  
 执行包之后, 必须通过转到 SAP 数据导入到的 SQL Server 数据库来验证结果。 执行包应已在目标数据库中创建一个表并填入 SAP 表中的值。  
  
## <a name="see-also"></a>请参阅  
 [使用包含 SSIS 的 SAP 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)