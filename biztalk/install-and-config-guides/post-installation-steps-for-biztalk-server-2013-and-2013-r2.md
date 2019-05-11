---
title: BizTalk Server 2013 和 2013 R2 的安装后步骤 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3b47843-9da5-4144-8b84-135494b8ab43
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cae3a9705e776d8f01e5659341378240eb2fcde1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393995"
---
# <a name="post-installation-steps-for-biztalk-server-2013-and-2013-r2"></a>BizTalk Server 2013 和 2013 R2 的安装后步骤
  
##  <a name="BKMK_NamedPipes"></a> 启用 TCP/IP 和命名的管道  
  
1. 打开 **SQL Server 配置管理器**。  
  
2. 展开**SQL Server 网络配置**，然后选择**MSSQLSERVER 的协议**。  
  
3. 确认两者**TCP/IP**并**Named Pipes**启用。 如果启用，请转到下一步。  
  
    如果未启用：  
  
   -   右键单击协议，然后依次**启用**。  
  
   -   若要启用其他协议，如有必要的重复。  
  
   -   在左侧窗格中，单击**SQL Server Services**。  
  
   -   在右侧窗格中，右键单击**SQL Server (MSSQLSERVER)**，然后单击**停止**。  
  
   -   当服务停止后时，右击**SQL Server (MSSQLSERVER)**，然后单击**启动**。  
  
   > [!IMPORTANT]
   >  如果使用的[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]，则**NS$ BAMAlerts**服务可能会停止。 重新启动服务。  
  
4. 关闭**配置管理器**。  
  
##  <a name="BKMK_DTC"></a> 启用本地主机服务器上的 DTC  
  
1. 打开组件服务：  
  
    [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]：选择 Windows 按钮，并键入**组件服务**。 在结果窗口中，选择**组件服务**。  
  
    **Windows 8.1**:选择 Windows 按钮，并键入**管理工具**。 在搜索窗口中，选择**设置**。 在结果窗口中，单击**管理工具**。 双击**组件服务**。  
  
    **Windows 7 SP1**:选择“开始”。 在中**搜索**文本框中，键入**组件服务**，并单击它打开。  
  
2. 在控制台树中，展开**组件服务**，展开**计算机**，展开**我的电脑**，展开**分布式事务处理协调器**，然后单击**本地 DTC**。  
  
3. 右键单击**本地 DTC** ，然后选择**属性**以打开**本地 DTC 属性**。  
  
4. 选择 **“安全”** 选项卡。  
  
5. 确认已选中以下选项：  
  
   - **网络 DTC 访问**  
  
   - **允许入站**  
  
   - **允许出站**  
  
   - **不要求进行验证**  
  
     可能需要的其他设置，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。  
  
6. 选择**确定**以关闭**本地 DTC 属性**对话框。 如果系统提示您重新启动 MSDTC 服务。  
  
7. 关闭**组件服务**。  
  
##  <a name="BKMK_Firewall"></a> 配置 Windows 防火墙以启用 DTC  
  
1. 打开**Windows 防火墙**:  
  
    [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]：单击 Windows 按钮，并键入**Windows 防火墙**。 在结果窗口中，单击**Windows 防火墙**。  
  
    **Windows 8.1**:单击 Windows 按钮，并键入**Windows 防火墙**。 在搜索窗口中，单击**设置**。 在结果窗口中，单击**Windows 防火墙**。  
  
    **Windows 7 SP1**:单击**启动**。 在中**搜索**文本框中，键入**Windows 防火墙**，并单击它打开。  
  
2. 单击**高级设置**然后单击**入站规则**。  
  
3. 在中**入站规则**窗格中，右键单击**分布式事务处理协调器** \* （根据需要），然后单击**启用规则**。  
  
4. 单击**出站规则**。  
  
5. 在中**出站规则**窗格中，右键单击**分布式事务处理协调器** \* （根据需要），然后单击**启用规则**。  
  
6. 上**Control Panel**图标，将视图更改为列表，然后双击**管理工具**。  
  
7. 双击**Services**。  
  
8. 右键单击**COM + 系统应用程序**，单击**重新启动**，并等待服务重新启动。  
  
9. 右键单击并重启**分布式事务处理协调器**服务。  
  
10. 右键单击并重启**SQL Server (MSSQLSERVER)** 服务。  
  
11. 关闭**服务 （本地）**，然后关闭**管理工具**。  
  
##  <a name="BKMK_SQLAgent"></a> 配置 SQL 代理作业  
  
|            作业            |                                                                                                                                                                                                                                                                                                                     Description                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                 为什么配置                                                                                                                                                                                                  |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **备份 BizTalk Server** |                                     此 SQL 代理作业用于备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和日志文件。 在配置该作业，确定频率和文件位置等参数。<br /><br /> 以下链接介绍了 SQL 代理作业和其参数：<br /><br /> [备份和还原 BizTalk Server 数据库](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)<br /><br /> [如何配置备份 BizTalk Server 作业](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)                                      | 此 SQL 代理作业会截断事务日志，从而可帮助提高性能。<br /><br /> **备份 BizTalk Server**作业不会删除或删除备份文件，包括较早的文件。 若要删除备份文件，请参阅["备份 BizTalk Server"作业失败时的备份文件累积一段时间中的 Microsoft BizTalk Server 数据库服务器](http://support.microsoft.com/kb/982546)。 |
| **DTA 清除和存档** | 此 SQL 代理作业可截断并存档[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]跟踪数据库 (BizTalkDTADb)。 在配置该作业，确定参数喜欢多长时间内将保存已完成的实例以及还有多少天，以保留所有数据。<br /><br /> 以下链接介绍了 SQL 代理作业和其参数：<br /><br /> [存档和清除 BizTalk 跟踪数据库](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)<br /><br /> [如何配置 DTA 清除和存档作业](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx) |              此 SQL 代理作业通过维护跟踪主机和清除跟踪事件会直接影响性能。<br /><br /> 性能主题包括：<br /><br /> [如何维护和故障排除 BizTalk Server 数据库](http://support.microsoft.com/kb/952555)<br /><br /> [跟踪数据库的大小调整准则](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)              |
  
 **其他**  
  
- 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是安装，多个 SQL 代理作业会自动创建，如以下链接中所述：  
  
   [在 BizTalk Server 中的 SQL Server 代理作业的说明](http://support.microsoft.com/kb/919776)  
  
   [数据库结构和作业](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)  
  
##  <a name="BKMK_InstallCU"></a> 安装累积更新  
 在安装后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，安装任何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]累积更新 Windows Update 中列出。 [KB 文章 2555976](http://support.microsoft.com/kb/2555976)列出了可用的 service pack 和累积更新。  
  
## <a name="next"></a>Next  
[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)
  
## <a name="see-also"></a>请参阅  
 [附录 a:无提示安装](../install-and-config-guides/appendix-a-silent-installation.md) 
 
[附录 b:安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)  

[附录 c:可再发行 CAB 文件](../install-and-config-guides/appendix-c-redistributable-cab-files.md)  

[附录 d:创建 SMTP 服务器](../install-and-config-guides/appendix-d-create-the-smtp-server.md)

[卸载并取消配置 BizTalk Server 将其删除](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)
