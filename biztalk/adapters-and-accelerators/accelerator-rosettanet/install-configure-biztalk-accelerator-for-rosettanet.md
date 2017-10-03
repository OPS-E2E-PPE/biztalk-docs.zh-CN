---
title: "为 RosettaNet (BTARN) BizTalk 服务器上安装 BizTalk 快捷键 |Microsoft 文档"
description: "请参阅的硬件和软件要求、 安装步骤中和 BTARN BizTalk Server 中的配置步骤"
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a40eca3ccd2092cc3024e0ad69d3737bad869180
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-biztalk-accelerator-for-rosettanet"></a>安装适用于 RosettaNet BizTalk 快捷键

## <a name="overview"></a>概述
安装 Microsoft BizTalk Accelerator for RosettaNet (BTARN)。
  
> [!NOTE]
>  在 Enterprise Edition 的 BizTalk Server 中，可以安装仅企业版的 BizTalk 快捷键 RosettaNet (BTARN)。 在标准版的 BizTalk Server 中，可以安装仅标准版的 BizTalk 快捷键 RosettaNet (BTARN)。  
  
 BTARN 安装包括以下：  
  
-   BTARN 管理  
  
-   BizTalk 业务流程设计器 XLANG 调度（合作伙伴接口流程模式）  
  
-   RosettaNet 实现框架 (RNIF)  
  
-   BTARN 数据库  
  
-   HTTP 前端 Web 应用程序  
  
## <a name="hardware-and-software-requirements"></a>硬件和软件要求

最低硬件和软件要求是与 BizTalk Server 相同。

|  |BizTalk 要求  |SQL 和操作系统要求 |  
|---------|---------|--------- | 
| [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [BizTalk Server 2016 的硬件和软件要求](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) | **SQL Server 的硬件和软件要求**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Windows 服务器硬件要求**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx) |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> BizTalk Server 2013 | [硬件和软件要求 BizTalk Server 2013 和 2013 R2](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) |**SQL Server 的硬件和软件要求**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Windows 服务器硬件要求**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx)  |

> [!TIP] 
> 列出的是最低硬件要求。 每个环境都不同，可能你的环境具有更高要求。 请参阅 [Recommendations for Installing, Sizing, Deploying, and Maintaining a BizTalk Server Solution](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)（BizTalk Server 解决方案的安装、大小调整、部署和维护建议）。 

## <a name="install-and-configure"></a>安装和配置

### <a name="before-you-begin"></a>开始之前

* 对于 BTARN 数据库中，BTARN 仅配置 SQL Server 计算机名称和数据库名称属性。 有关这些属性的信息存储在注册表中。
* 使用成员的帐户登录 BizTalk Server Administrators 组。 
* 在你的 BizTalk Server 下载 BTARN 安装程序位于`\BizTalk Accelerators`文件夹。
* 必须安装 BizTalk Server，并且必须运行 SQL Server。
* BTARN 和 BizTalk Server 作为软件必备组件需要 Microsoft.NET Framework。 如果你有多个版本在计算机上安装的.NET Framework，请确保 BtarnAPP Web 应用程序正在引用.NET Framework 4.0 经典。 你可以使用 Internet 信息服务 (IIS) 管理器对此进行配置。  
* BizTalk 主机实例帐户和 BizTalk 独立主机实例帐户应该相同。 否则，BTARN 无法正常工作。  
* BTARN，可将仅各个服务帐户，而不要使用组，添加到 BizTalk Server Administrators 组或 BizTalk 应用程序用户组。  
* 你需要为 BTSHTTPReceive.dll 创建 WebService 扩展，并配置 IIS 隔离模式。 有关详细信息，请参阅在"故障排除:: 问题和解决方法"主题中的"404 找不到错误时发送的 HTTP 请求"条目[http://go.microsoft.com/fwlink/?LinkId=188560](http://go.microsoft.com/fwlink/?LinkId=188560)。 另请参阅[如何将 IIS 配置的 HTTP 接收位置](../../core/how-to-configure-iis-for-an-http-receive-location.md)。  
* 将服务器添加 (http:// <*服务器名称*>) 到本地 Internet 区域中的 Internet Explorer 安全选项。  
*  如果配置 BTARN 时使用的是采用非默认端口的远程 SQL 实例，则必须本地安装 SQL Server 客户端工具。 有关详细信息，请参阅[多计算机环境用于 BizTalk Server 安装指南](../../install-and-config-guides/install-biztalk-server-in-a-multi-computer-environment.md)。
*  单独的组必须在配置 BizTalk Server 用于角色-BizTalk 管理员、 BizTalk 主机用户和 BizTalk 独立主机用户。  
*  BTARN 不支持别名创建针对 SQL 实例配置 BTARN 数据库的使用。  

### <a name="install-btarn"></a>安装 BTARN

1.  运行 BTARN **setup.exe**以管理员身份。
  
2.  选择“安装”。  
  
3.  上**客户信息**页上，键入你的用户名、 组织和产品密钥，然后单击**下一步**。  
  
4.  上**许可协议**页上，阅读最终用户许可协议，，然后单击**接受**。  
  
    > [!NOTE]
    >  如果不接受许可协议，则无法继续安装。  
  
5.  上**安装选项**页上，选择**完成**的完整安装或**自定义**部分安装。 确保安装路径正确无误，，然后单击**下一步**。  
  
    > [!NOTE]
    >  如果你选择**自定义**，选择要从安装的组件**自定义安装**页。 如果你选择安装 SDK 或文档组件，则必须在运行安装程序之前安装.NET Framework。  
  
6.  上**摘要**页上，查看你要安装，然后单击的组件**安装**。 **安装进度**屏幕显示的安装过程的进度。  
  
7.  上**安装完成**页上，确保**运行配置向导**框被选中，并且然后单击**完成**。  
  
     BTARN 配置向导将打开。 下一步将配置 BTARN。  
  
    > [!IMPORTANT]
    >  如果执行自定义安装安装仅 BTARN HTTP 前端功能，BTARN 配置可能会失败，在安装完毕后，显示"无法创建功能的对象： WebApp"错误。 如果发生这种情况，将两个文件复制 (**Microsoft.VC80.ATL.manifest**和**atl80.dll**) 从与 BizTalk Server 的计算机上安装它，其中安装 BTARN HTTP 前端功能的计算机。  
    >   
    >  如果在 BizTalk Server 所在的计算机上安装 Visual Studio，两个文件的源文件夹是*< 驱动器\>*: files\microsoft Visual Studio 11.0\VC\redist\x86\Microsoft.VC100.ATL。 如果在 BizTalk server 上未安装 Visual Studio，BizTalk 服务器上的两个文件的源文件夹是下的某个文件夹*< 驱动器\>*: \WINDOWS\WinSxS。 这两个文件的版本应该是 8.0.50727.42。 在装有 HTTP 前端功能的计算机上的目标文件夹是 BTARN 安装目录 (默认情况下， *< 驱动器\>*: files\microsoft BTARN)。  
    >   
    >  你已安装了 HTTP 前端功能这些文件复制到计算机后，重新运行**Configuration.exe**。  
  
### <a name="configure-btarn"></a>配置 BTARN  

> [!TIP]
 >  在配置之前 BTARN，请确保映射在 IIS 中的处理程序映射下的.NET Framework。 此外，在配置 BTARN 时，你可能需要手动创建 IIS_WPG 组。  
   
1.  上**Microsoft BTARN 配置向导**页上，选择**基本配置**要使用默认设置，配置服务器或**自定义配置**到配置使用高级的配置选项的服务器。  
  
    > [!NOTE]
    >  如果你想要配置使用本地管理员帐户的 BTARN，输入作为帐户*< 计算机名称\>\\< 管理员名称\>*中**用户 ID**字段**服务凭据**区域。  
  
2.  在**数据库服务器名称**文本中，确认显示的服务器名称正确无误。 在**服务凭据**区域中，输入下运行服务的帐户 （与域） 的用户名和密码。 单击**配置**。  
  
3.  如果你的帐户具有管理权限，请单击**是**继续进行配置。  
  
4.  如果你选择**基本配置**在步骤 1 中，验证要在中配置的部分列表**摘要**对话框中，然后单击**下一步**。 转到步骤 10。  
  
5.  如果你选择**自定义配置**在步骤 1 中，执行以下步骤：  
  
    > [!NOTE]
    >  如果你在任何 BTARN 数据库的名称中使用特殊字符，则 BTARN 配置将失败。  
  
6.  在配置运行时， **Microsoft BTRAN 配置**对话框中，单击**运行时**的左窗格中。 在右侧**运行时**窗格中，单击**启用这台计算机上的运行时功能**。 若要加入现有的数据库组，清除**你想要创建新的数据库组**。 选择适当的 Web 服务器名称、端口号、数据存储区、应用程序池服务帐户和 BizTalk HTTP 接收虚拟文件夹。  
  
7.  若要配置中 WebApps 功能， **Microsoft BTRAN 配置**对话框中，单击**WebApps**在左窗格中，然后单击**启用此计算机上的运行时功能**. 输入适当的 BizTalk Server 名称和端口号，或选择默认值。 选择适当的 Web 应用程序虚拟文件夹。  
  
8.  单击“应用配置”。  
  
9. 上**摘要**页上，单击**下一步**。  
  
10. 上**完成配置**页上，单击**完成**。  
  
    > [!NOTE]
    >  安装了 BTARN 后，系统管理员必须将用户添加到 BAS Business User、Business Manager 和 Business Administrator 组。 如果你是系统管理员，则必须填充这些组并注销，然后登录将自己添加到这些组中。
  
    > [!WARNING]
    >  BizTalk 管理员、 BizTalk 主机用户和 BizTalk 独立主机用户配置 BizTalk Server 时，必须使用三个不同的组。  

## <a name="start-the-artifacts"></a>启动项目
BTARN 业务流程，发送端口和接收位置不会自动启动配置 BTARN 后。
  
> [!NOTE]
>  必须先启动 PrivateInitiator_To_LOB 和 PrivateResponder_To_LOB 发送端口，然后才能启动 PrivateInitiatorProcess 和 PrivateResponderProcess 业务流程。  
  
-   对于某些计算机，如果已通过安全套接字层 (SSL) 配置了 Internet Information Services (IIS) 虚拟服务器，则必须先配置虚拟服务器以接受客户端证书。 请参阅[步骤 4： 启用安全套接字在 IIS 中的层](step-4-enabling-secure-sockets-layer-in-iis.md)中[双击操作教程](double-action-tutorial.md)。
  
 
1.  打开**BizTalk Server 管理**以管理员身份。  
  
2.  展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。  
  
3.  单击**发送端口**。 在右窗格中，对于每个发送端口，未启动，右键单击，然后单击**启动**。  
  
4.  单击**接收端口**和**接收位置**。 在右窗格中，为每个接收未启动的位置，右键单击并依次**启动**。  
  
    > [!NOTE]
    >  你必须启动 PrivateInitiator_To_LOB 和 PrivateResponder_To_LOB 发送端口，然后才能开始 PrivateInitiatorProcess 和 PrivateResponderProcess 业务流程。  
  
5.  单击**业务流程**和**接收位置**。 在右窗格中，不会启动每个业务流程，右键单击，然后单击**启动**。  
  
## <a name="restart-your-computer"></a>重新启动计算机  
  
请重新启动计算机，以应用对配置和权限所做的任何修改。  
  
> [!NOTE]
>  开发人员可能出于开发、阶段调试或测试目的，选择在单个服务器上安装并配置 BTARN。 开发人员可使用此服务器编写自定义代码，并在用于生产之前对其进行测试。  
  
 有关一台服务器上安装 BTARN 的详细信息，请参阅[环回教程](loopback-tutorial.md)。
  
## <a name="next-steps"></a>后续步骤  
  
* [升级 RosettaNet 快捷键](upgrade-biztalk-accelerator-for-rosettanet.md)
* [卸载 RosettaNet 加速器](uninstall-biztalk-accelerator-for-rosettanet.md)
* [解决安装问题和发现的已知的安装问题](troubleshoot-known-issues-installation.md)