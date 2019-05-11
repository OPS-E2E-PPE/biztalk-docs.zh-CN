---
title: 导入 Siebel 数据使用 Visual Studio |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33701361-eca2-4795-a5e0-78162a98e9ba
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3397bfcb75dd68945b87c47ad0af237e677c3a92
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371493"
---
# <a name="import-siebel-data-using-visual-studio"></a>导入 Siebel 数据使用 Visual Studio
本部分提供有关如何使用 Microsoft 信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]从 Siebel 系统到 SQL Server 数据库导入数据。 它还说明了如何创建和执行 SSIS 包将此数据导入。  
  
## <a name="prerequisites"></a>先决条件  
 在执行之前在本主题中提供的过程，请确保：  
  
- [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]的计算机上安装。  
  
- 在计算机上安装 Microsoft Visual Studio。  
  
## <a name="import-in-visual-studio"></a>在 Visual Studio 中的导入  
 
1. 启动[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和创建集成服务项目。  
  
2. 从**项目**菜单中，选择**SSIS 导入和导出向导**。 这将启动 SQL Server 导入和导出向导。  
  
3. 阅读欢迎屏幕上的信息，然后单击**下一步**。  
  
4. 在中**选择数据源**对话框中，从**数据源**下拉列表**Siebel eBusiness 应用程序的.NET Framework 数据提供程序**。 指定的不同的连接属性的值[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]连接字符串。 有关连接字符串属性的详细信息，请参阅[Siebel 连接字符串的数据提供程序属性](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)。  
  
    单击“下一步” 。  
  
5. 在中**选择目标**对话框：  
  
   1.  从**目标**下拉列表中，选择**SQL Native Client**。  
  
   2.  从**服务器名称**下拉列表中，选择 SQL Server 名称。  
  
   3.  选择身份验证模式。  
  
   4.  从**数据库**下拉列表中，选择你想要导入 Siebel 表的数据库。  
  
   5.  单击“下一步” 。  
  
6. 在中**指定表复制或查询**对话框框中，选择**编写查询以指定要传输的数据**选项。  
  
7. 在中**提供源查询**对话框框中，指定用于筛选要导入到 SQL Server 的数据的选择查询。 有关语法的详细信息，为 SELECT 查询[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，请参阅[Siebel 中的选择语句的语法](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)。  
  
8. 若要验证查询，请单击**分析**按钮，再单击**确定**在弹出对话框中，然后单击**下一步**。  
  
9. 在中**选择源表和视图**对话框框中，选择源和目标表对应的复选框。 源是指定从 Siebel 检索数据的查询。 目标将是将 SQL Server 数据库中创建的表。  
  
10. 该向导创建的源和目标之间的默认映射表字段。 但是，您可以根据需要更改映射。 若要更改字段映射，请单击**编辑映射**。  
  
11. 在中**列映射**对话框中，你可以：  
  
    - 更改目标表中的列的名称。  
  
    - 忽略某些列与目标表中。  
  
    - 更改目标表中的字段的数据类型。  
  
    - 更改其他字段属性，如可以为 null，大小、 精度和小数位数。  
  
    - 单击“确定” 。  
  
      ![Siebel 和 SQL 表之间的列映射](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")  
  
12. 在中**选择源表和视图**对话框中，单击**下一步**。  
  
13. 在中**完成该向导**对话框框中，查看操作，该向导将执行，然后单击摘要**完成**。  
  
14. 在中**正在执行操作**对话框中，该向导开始执行任务以从 Siebel 的信息导入到 SQL Server 数据库表中。 在向导中显示每个任务的状态。  
  
15. 已成功执行所有任务后，单击**关闭**。 如果任务失败时，请参阅相应的错误消息、 修复该问题，并重新运行该向导。  
  
16. 该向导将 SSIS 包添加到你的集成服务项目。 保存集成服务项目。  
  
## <a name="run-the-ssis-package"></a>运行 SSIS 包  
 集成服务项目中创建包后，可以执行它，以从 Siebel 系统到 SQL Server 数据库导入数据。 执行以下步骤来执行包导入 Siebel 数据。  
  
1.  导航到解决方案资源管理器中的 SSIS 包。  
  
2.  右键单击包名称，然后选择**执行包**。  
  
[运行 Integration Services (SSIS) 包](https://docs.microsoft.com/sql/integration-services/packages/run-integration-services-ssis-packages)提供详细信息。 
  
## <a name="verify-the-results"></a>验证结果  
 执行包之后, 必须通过登录到 SQL Server 并导航到 Siebel 数据导入到该数据库来验证结果。 执行包应已创建表在目标数据库中。 应使用 Siebel 表中的值填充此表。  
  
## <a name="see-also"></a>请参阅  
 [使用 Siebel 的数据提供程序和 SSIS](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)