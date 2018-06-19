---
title: 对表和视图的用户定义的类型使用的 SQL 适配器操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4006bbe-91ca-4cd9-844d-5ed63142001f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa05cf28e267e84dd73ad1a3ffd753ee89febb71
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006830"
---
# <a name="operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter"></a>对表和视图的用户定义的类型使用的 SQL 适配器操作
你可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在表或视图具有用户定义类型 (Udt) 的列上执行操作。 你可以使用标准的表操作 （插入、 更新、 删除和选择） 读取或写入数据列上 UDT 类型。 你还可以在此类表上执行存储的过程和函数。 但是，你需要执行某些任务，你可以使用该适配器上包含 UDT 列的表进行操作之前。 一旦你已执行这些任务，你可以使用为该适配器：  
  
-   执行插入、 删除、 更新和 Select 操作中所述[插入、 更新、 删除或 BizTalk 服务器与 SQL 适配器一起使用的 select 操作](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)。  
  
-   执行存储的过程中所述[在 SQL Server 使用 BizTalk Server 中执行存储的过程](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)。  
  
-   执行对具有 UDT 列的表的复合操作中所述[运行 SQL Server 使用 BizTalk Server 上的复合操作](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)  
  
-   轮询包含 UDT 列的表中所述[使用 BizTalk Server 从 SQL Server 基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)。  
  
-   中所述执行其他操作，[开发 BizTalk 应用程序](../../core/develop-your-biztalk-applications.md)。  
  
## <a name="considerations-while-performing-operations-on-tables-with-udts"></a>执行对表使用 Udt 的操作时的注意事项  
 在你可以使用适配器对包含 UDT 列的表执行操作之前，必须执行以下任务。  
  
-   **生成操作使用的架构时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]**  
  
    |UDT 类型|程序集位置|  
    |--------------|----------------------------|  
    |Udt 随 SQL Server，例如 Geography|-请确保 Microsoft.SqlServer.Types.dll 添加到 GAC。<br />-请确保 SqlServerSpatial.dll 位于 System32 文件夹中。<br /><br /> 可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-基本**和**管理工具 – 完整**中**功能选择**向导页。|  
    |不随 SQL Server 但由用户定义的 Udt|请确保提供与相同的位置中可以找到 Udt 的相应程序集[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可执行文件、 devenv.exe。 可执行文件位于通常`<installation drive>:\Program Files\Microsoft Visual Studio <version>\Common7\IDE`。|  
  
-   **执行操作使用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]**  
  
    |UDT 类型|程序集位置|  
    |--------------|----------------------------|  
    |Udt 随 SQL Server，例如 Geography|-请确保 Microsoft.SqlServer.Types.dll 添加到 GAC。<br />-请确保 SqlServerSpatial.dll 位于 System32 文件夹中。<br /><br /> 可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-基本**和**管理工具 – 完整**中**功能选择**向导页。|  
    |不随 SQL Server 但由用户定义的 Udt|请确保 Udt 的相应程序集下有[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装位置。 对于 BizTalk Server 中，通常这是\<安装驱动器\>: files\microsoft BizTalk Server。|  
  
-   **执行操作使用时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]**  
  
    |UDT 类型|程序集位置|  
    |--------------|----------------------------|  
    |Udt 随 SQL Server，例如 Geography|-请确保 Microsoft.SqlServer.Types.dll 添加到 GAC。<br />-请确保 SqlServerSpatial.dll 位于 System32 文件夹中。<br /><br /> 可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-基本**和**管理工具 – 完整**中**功能选择**向导页。|  
    |不随 SQL Server 但由用户定义的 Udt|请确保在同一位置的项目可执行文件，这通常是在项目的 \bin\Debug 文件夹下 Udt 的相应程序集均可用。|  
  
 完成这些任务后，你都设置为对具有 Udt 的表执行操作。  
  
## <a name="see-also"></a>另请参阅  
 [连接到 SAP 系统使用适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)