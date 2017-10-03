---
title: "SQL Server 和适配器客户端上配置 MSDTC |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c87f455-a8c4-4169-bf18-695926136df1
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf519044dc28d417d85682189dd4a52585310ac0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-msdtc-on-sql-server-and-adapter-client"></a>SQL Server 和适配器客户端上配置 MSDTC
使用 SQL Server 上执行的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)](通过[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型或 WCF 通道模型) 可以在事务范围内执行。 如果客户端程序具有多个事务的资源在同一事务的一部分，获取提升为 MSDTC 事务的事务。 若要启用的适配器执行 MSDTC 事务的范围内的操作，必须配置 MSDTC 这两个运行的计算机上[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 SQL Server。 此外，必须将 MSDTC 添加到 Windows 防火墙例外列表。 本部分提供有关如何在运行的适配器客户端和 SQL Server 的计算机上执行这些任务的信息。  
  
> [!NOTE]
>  在使用 SQL Server 上执行操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]始终涉及两个资源-连接到 SQL Server 和 BizTalk 消息框驻留在 SQL Server 上的适配器。 因此，所有操作都执行使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSDTC 事务的作用域内都执行。 因此，为了使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你必须始终启用 MSDTC。  
  
> [!NOTE]
>  其中适配器客户端不会写入任何数据的 SQL Server 数据库，选择操作，如操作可能不想执行的操作在事务内的其他系统开销。 在这种情况下，你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过设置执行操作而无需事务上下文**UseAmbientTransaction**属性绑定到**false**。 有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 在这种情况下，你不需要以及配置 MSDTC。  
  
## <a name="configure-msdtc"></a>配置 MSDTC  
  
1.  打开**组件服务**。  

    或者，在**服务器管理器**，选择**工具**，然后选择**组件服务**。  
  
2.  展开**组件服务**，展开**计算机**，展开**我的电脑**，展开**分布式事务处理协调器**，右键单击**本地 DTC**，然后选择**属性**。  
  
3.  选择 **“安全”** 选项卡。在此选项卡上，选择如下： 

  - **网络 DTC 访问**
  - **允许远程客户端** 
  - **允许入站** 
  - **允许出站** 
  - **所需的任何 Authetnication**
  
4.  单击“确定”保存更改。  
  
5.  如果系统提示您重新启动 MSDTC 服务，选择**是**。 重新启动 MSDTC 服务后，关闭属性和组件服务 MMC。 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a>将 MSDTC 添加到 Windows 防火墙例外列表  

> [!TIP] 
>  Microsoft 分布式 Tansaction 处理协调器 (MSDTC) 可能已允许在防火墙中。 如果是这样，则将它列出为入站规则。 如果未列出，请使用本部分以允许 MSDTC。 

1.  打开**Windows 防火墙**，然后选择**高级设置**左侧。  

    或者，在**服务器管理器**，选择**工具**，然后选择**高级安全 Windows 防火墙**。  
  
2.  右键单击**入站规则**，然后选择**新规则**。  
  
3.  在向导中： 

    1. 选择**程序**，然后选择**下一步**。 
    2. 设置**程序路径**到`%SystemRoot%\system32\msdtc.exe`，然后选择**下一步**。  
    3. **允许连接**，然后选择**下一步**。
    4. 选择**域**，然后选择**下一步**。
    5. 输入任何名称，如`MSDTC for Oracle EBS`，然后选择**完成**。
  
5.  完成向导，并关闭 Windows 防火墙。 
  
## <a name="see-also"></a>另请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)