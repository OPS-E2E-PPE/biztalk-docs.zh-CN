---
title: "导入使用 Visual Studio 的 Siebel 数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33701361-eca2-4795-a5e0-78162a98e9ba
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4479fbbfd704cea30b8981866d3b7a354ca7269f
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2017
---
# <a name="import-siebel-data-using-visual-studio"></a>使用 Visual Studio 的 Siebel 数据导入
本部分提供有关如何使用 Microsoft 的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]从 Siebel 系统到 SQL Server 数据库导入数据。 它还提供有关如何创建和执行 SSIS 包导入此数据的说明。  
  
## <a name="prerequisites"></a>先决条件  
 执行本主题中提供过程之前，请确保：  
  
-   [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]计算机上安装。  
  
-   在计算机上安装 Microsoft Visual Studio。  
  
## <a name="import-in-visual-studio"></a>Visual Studio 中的导入  
 
1.  启动[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并创建一个集成服务项目。  
  
2.  从**项目**菜单上，选择**SSIS 导入和导出向导**。 这将启动 SQL Server 导入和导出向导。  
  
3.  阅读欢迎屏幕上的信息，然后单击**下一步**。  
  
4.  在**选择数据源**对话框中，从**数据源**下拉列表**Siebel eBusiness Applications 的.NET Framework 数据提供程序**。 指定的不同的连接属性的值[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]连接字符串。 有关连接字符串属性的详细信息，请参阅[Siebel 连接字符串的数据提供程序属性](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)。  
  
     单击 **“下一步”**。  
  
5.  在**选择目标**对话框中：  
  
    1.  从**目标**下拉列表中，选择**SQL Native Client**。  
  
    2.  从**服务器名称**下拉列表中，选择 SQL Server 名称。  
  
    3.  选择身份验证模式。  
  
    4.  从**数据库**下拉列表中，选择你想要导入 Siebel 表的数据库。  
  
    5.  单击 **“下一步”**。  
  
6.  在**指定表复制或查询**对话框框中，选择**编写查询以指定要传输的数据**选项。  
  
7.  在**提供源查询**对话框框中，指定 SELECT 查询来筛选要导入到 SQL Server 的数据。 有关语法的详细信息，以进行 SELECT 查询[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，请参阅[为 Siebel 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)。  
  
8.  若要验证查询，请单击**分析**菜单上，单击**确定**在弹出对话框中，然后单击**下一步**。  
  
9. 在**选择源表和源视图**对话框框中，选中针对源和目标表的复选框。 源是您指定从 Siebel 检索数据的查询。 目标将是将 SQL Server 数据库中创建的表。  
  
10. 该向导创建的源和目标之间的默认映射表字段。 但是，你可以根据你的要求更改映射。 若要更改的字段映射，请单击**编辑映射**。  
  
11. 在**列映射**对话框中，你可以：  
  
    -   更改目标表中的列的名称。  
  
    -   忽略目标表中的某些列。  
  
    -   更改目标表中的字段的数据类型。  
  
    -   更改其他字段属性，如可以为 null，大小、 精度和小数位数。  
  
    -   单击 **“确定”**。  
  
     ![Siebel 和 SQL 表之间的列映射](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")  
  
12. 在**选择源表和源视图**对话框中，单击**下一步**。  
  
13. 在**完成向导**对话框框中，检查的操作，该向导将执行，然后单击摘要**完成**。  
  
14. 在**执行操作**对话框中，向导开始执行任务以将信息从 Siebel 导入 SQL Server 数据库表。 在向导中显示每个任务的状态。  
  
15. 已成功执行所有任务后，单击**关闭**。 如果任务失败，请参阅相应的错误消息、 修复该问题，并重新运行该向导。  
  
16. 向导将 SSIS 包添加到你的集成服务项目。 保存集成服务项目。  
  
## <a name="run-the-ssis-package"></a>运行 SSIS 包  
 在集成服务项目内创建包后，你可以执行它从 Siebel 系统到 SQL Server 数据库导入数据。 执行以下步骤 Siebel 数据导入通过执行包。  
  
1.  导航到解决方案资源管理器中的 SSIS 包。  
  
2.  右键单击包名称，然后选择**执行包**。  
  
[运行 Integration Services (SSIS) 包](https://docs.microsoft.com/sql/integration-services/packages/run-integration-services-ssis-packages)提供了详细的信息。 
  
## <a name="verify-the-results"></a>验证结果  
 后执行包，你必须通过登录到 SQL Server 并导航到 Siebel 数据导入到的数据库验证结果。 执行包应已创建表目标数据库中。 应使用 Siebel 表中的值填充此表。  
  
## <a name="see-also"></a>另请参阅  
 [使用用于 Siebel 使用 SSIS 数据提供程序](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)