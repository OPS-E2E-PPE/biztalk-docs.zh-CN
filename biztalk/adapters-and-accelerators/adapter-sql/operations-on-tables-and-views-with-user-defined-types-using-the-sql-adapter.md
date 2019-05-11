---
title: 对表和视图使用 SQL 适配器的用户定义类型的操作 |Microsoft Docs
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
ms.openlocfilehash: eb497a951230463e307a18ec6f12db69ab2c8da9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368629"
---
# <a name="operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter"></a>对表和视图使用 SQL 适配器的用户定义类型的操作
可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]具有的用户定义类型 (Udt) 列的表或视图上执行操作。 可以使用标准表操作 （Insert、 Update、 Delete 和 Select） 读取或写入数据列上 UDT 类型。 您还可以在此类表上执行存储的过程和函数。 但是，您需要执行某些任务，然后才能使用该适配器具有 UDT 列的表操作。 一旦您已执行这些任务，可以使用到适配器：  

-   执行 Insert、 Delete、 Update 和选择操作，如中所述[插入、 更新、 删除或将 BizTalk Server 与 SQL 适配器的 select 操作](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)。  

-   执行存储的过程，如中所述[在使用 BizTalk Server 的 SQL Server 中执行存储的过程](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)。  

-   执行复合操作具有 UDT 列的表中所述[运行 SQL Server 使用 BizTalk Server 上的复合操作](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)  

-   轮询具有 UDT 列的表中所述[使用 BizTalk Server 从 SQL Server 基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)。  

-   执行其他操作，如中所述[开发 BizTalk 应用程序](../../core/develop-your-biztalk-applications.md)。  

## <a name="considerations-while-performing-operations-on-tables-with-udts"></a>对包含 Udt 的表执行操作时的注意事项  
 可以使用该适配器具有 UDT 列的表上执行操作之前，必须执行以下任务。  

- **生成操作使用的架构时 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]**  


  |                       UDT 类型                        |                                                                                                                                                                        程序集位置                                                                                                                                                                        |
  |-------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | Udt 随 SQL Server 提供，例如，地理位置  | -请确保 Microsoft.SqlServer.Types.dll 添加到 GAC。<br />-请确保 SqlServerSpatial.dll 位于 System32 文件夹中。<br /><br /> 可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-Basic**并**管理工具-完整**中**功能选择**向导页。 |
  | 未随 SQL Server，但由用户定义的 Udt |                      请确保在与相同的位置对 Udt 的相应程序集都可以[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可执行文件，devenv.exe。 可执行文件是通常位于`<installation drive>:\Program Files\Microsoft Visual Studio <version>\Common7\IDE`。                      |


- **执行操作使用时 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]**  


  |                       UDT 类型                        |                                                                                                                                                                        程序集位置                                                                                                                                                                        |
  |-------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | Udt 随 SQL Server 提供，例如，地理位置  | -请确保 Microsoft.SqlServer.Types.dll 添加到 GAC。<br />-请确保 SqlServerSpatial.dll 位于 System32 文件夹中。<br /><br /> 可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-Basic**并**管理工具-完整**中**功能选择**向导页。 |
  | 未随 SQL Server，但由用户定义的 Udt |                                     请确保对 Udt 的相应程序集位于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装位置。 对于 BizTalk Server，这通常是\<安装驱动器\>: \Program Files\Microsoft BizTalk Server。                                      |


- **执行操作使用时 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]**  

  |UDT 类型|程序集位置|  
  |--------------|----------------------------|  
  |Udt 随 SQL Server 提供，例如，地理位置|-请确保 Microsoft.SqlServer.Types.dll 添加到 GAC。<br />-请确保 SqlServerSpatial.dll 位于 System32 文件夹中。<br /><br /> 可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-Basic**并**管理工具-完整**中**功能选择**向导页。|  
  |未随 SQL Server，但由用户定义的 Udt|请确保对 Udt 的相应程序集作为项目可执行文件，这通常是在项目的 \bin\Debug 文件夹下的同一位置中均可用。|  

  完成这些任务后，你已准备好对 udt 的表执行操作。  

## <a name="see-also"></a>请参阅  
 [连接到 SAP 系统使用的适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)