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
ms.openlocfilehash: 83215952b28da21e143af118c31519cd31fca911
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978694"
---
# <a name="post-installation-steps-for-biztalk-server-2013-and-2013-r2"></a>BizTalk Server 2013 和 2013 R2 的安装后步骤
  
##  <a name="BKMK_NamedPipes"></a>启用 TCP/IP 和命名管道  
  
1. 打开 **SQL Server 配置管理器**。  
  
2. 展开“SQL Server 网络配置”，然后选择“MSSQLSERVER 的协议”。  
  
3. 验证“TCP/IP”和“命名管道”是否都已启用。 如果已启用，继续进行下一步。  
  
    如果未启用：  
  
   -   右键单击该协议，然后单击“启用”。  
  
   -   如有必要，请重复此步骤以启用另一个协议。  
  
   -   在左侧窗格中，单击“SQL Server 服务”。  
  
   -   在右侧窗格中，右键单击“SQL Server (MSSQLSERVER)”，然后单击“停止”。  
  
   -   服务停止后，右键单击“SQL Server (MSSQLSERVER)”，然后单击“启动”。  
  
   > [!IMPORTANT]
   >  如果使用的是 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]，可以停止“NS$BAMAlerts”服务。 重新启动服务。  
  
4. 关闭“配置管理器”。  
  
##  <a name="BKMK_DTC"></a>启用本地主机服务器上的 DTC  
  
1. 打开“组件服务”：  
  
    **[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**：选择 Windows 按钮，并键入“组件服务”。 在“结果”窗口中，选择“组件服务”。  
  
    **Windows 8.1**：选择 Windows 按钮，并键入“管理工具”。 在“搜索”窗口中，选择“设置”。 在“结果”窗口中，单击“管理工具”。 双击“组件服务”。  
  
    **Windows 7 SP1**：选择“启动”。 在“搜索”文本框中，键入“组件服务”，然后单击以打开。  
  
2. 在控制台树中，依次展开“组件服务”、“计算机”、“我的计算机”、“分布式事务处理协调器”，然后单击“本地 DTC”。  
  
3. 右键单击“本地 DTC”，选择“属性”打开“本地 DTC 属性”。  
  
4. 选择“安全”选项卡。  
  
5. 确认已选中以下选项：  
  
   - **网络 DTC 访问**  
  
   - **允许入站**  
  
   - **允许出站**  
  
   - **不要求进行验证**  
  
     有关可能需要的其他设置，请参阅 [MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。  
  
6. 选择“确定”关闭“本地 DTC 属性”对话框。 如果系统提示，请重启 MSDTC 服务。  
  
7. 关闭“组件服务”。  
  
##  <a name="BKMK_Firewall"></a>将 Windows 防火墙配置为启用 DTC  
  
1. 打开“Windows 防火墙”：  
  
    **[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**：单击 Windows 按钮，并键入“Windows 防火墙”。 在“结果”窗口中，单击“Windows 防火墙”。  
  
    **Windows 8.1**：单击 Windows 按钮，并键入“Windows 防火墙”。 在“搜索”窗口中，单击“设置”。 在“结果”窗口中，单击“Windows 防火墙”。  
  
    **Windows 7 SP1**：单击“启动”。 在“搜索”文本框中，键入“Windows 防火墙”，然后单击打开。  
  
2. 单击“高级设置”，然后单击“入站规则”。  
  
3. 在“入站规则”窗格中，（根据需要）右键单击“分布式事务处理协调器”\*，然后单击“启用规则”。  
  
4. 单击“出站规则”。  
  
5. 在“出站规则”窗格中，（根据需要）右键单击“分布式事务处理协调器”\*，然后单击“启用规则”。  
  
6. 在“控制面板”中，将视图更改为按图标列出，然后双击“管理工具”。  
  
7. 双击“服务”。  
  
8. 右键单击“COM+ 系统应用程序”，再单击“重启”，然后等待服务重启。  
  
9. 右键单击并重启“分布式事务处理协调器”服务。  
  
10. 右键单击并重启“SQL Server (MSSQLSERVER)”服务。  
  
11. 关闭“服务(本地)”，然后关闭“管理工具”。  
  
##  <a name="BKMK_SQLAgent"></a>配置 SQL 代理作业  
  
|            作业            |                                                                                                                                                                                                                                                                                                                     Description                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                 配置原因                                                                                                                                                                                                  |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **备份 BizTalk Server** |                                     此 SQL 代理作业用于备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库和日志文件。 在配置该作业时，需要确定频率和文件位置等参数。<br /><br /> 以下链接介绍了 SQL 代理作业及其参数：<br /><br /> [备份和还原 BizTalk Server 数据库](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)<br /><br /> [如何配置备份 BizTalk Server 作业](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)                                      | 此 SQL 代理作业还会截断事务日志，这有助于改进性能。<br /><br /> **备份 BizTalk Server** 作业不会移除或删除备份文件，包括较早的文件。 若要删除备份文件，请参阅[当备份文件在 Microsoft BizTalk Server 数据库服务器中累积一段时间后，“备份 BizTalk Server”作业失败](http://support.microsoft.com/kb/982546)。 |
| **DTA 清除和存档** | 此 SQL 代理作业可截断并存档 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 跟踪数据库 (BizTalkDTADb)。 在配置该作业时，需要确定已完成实例的保留天数以及所有数据的保留天数等参数。<br /><br /> 以下链接介绍了 SQL 代理作业及其参数：<br /><br /> [存档和清除 BizTalk 跟踪数据库](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)<br /><br /> [如何配置 DTA 清除和存档作业](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx) |              此 SQL 代理作业通过维护跟踪主机和清除跟踪事件直接影响性能。<br /><br /> 性能主题包括：<br /><br /> [如何对 BizTalk Server 数据库进行维护和故障排除](http://support.microsoft.com/kb/952555)<br /><br /> [跟踪数据库的大小调整准则](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)              |
  
 **补充说明**  
  
- 安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，会自动创建若干个 SQL 代理作业，如以下链接所述：  
  
   [BizTalk Server 中的 SQL Server 代理作业的说明](http://support.microsoft.com/kb/919776)  
  
   [数据库结构和作业](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)  
  
##  <a name="BKMK_InstallCU"></a>安装累积更新  
 安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 之后，安装 Windows Update 中列出的所有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 累积更新。 [KB article 2555976](http://support.microsoft.com/kb/2555976) 列出了可用的 Service Pack 和累积更新。  
  
## <a name="next"></a>Next  
[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)
  
## <a name="see-also"></a>请参阅  
 [附录 A：无提示安装](../install-and-config-guides/appendix-a-silent-installation.md) 
 
[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)  

[附录 C：可再发行的 CAB 文件](../install-and-config-guides/appendix-c-redistributable-cab-files.md)  

[附录 D：创建 SMTP 服务器](../install-and-config-guides/appendix-d-create-the-smtp-server.md)

[卸载 BizTalk Server 并取消配置以将其删除](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)
