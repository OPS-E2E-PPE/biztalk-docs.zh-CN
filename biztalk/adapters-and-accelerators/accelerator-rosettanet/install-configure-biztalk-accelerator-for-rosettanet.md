---
title: 安装 BizTalk Accelerator for RosettaNet (BTARN) 在 BizTalk Server 上 |Microsoft Docs
description: 请参阅硬件和软件要求、 安装步骤中，以及 BizTalk Server 中的 BTARN 配置步骤
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecb8e527abe896719da881f0c7df0e4f5566a90f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005798"
---
# <a name="install-biztalk-accelerator-for-rosettanet"></a>安装 BizTalk Accelerator for RosettaNet

## <a name="overview"></a>概述
安装 Microsoft BizTalk Accelerator for RosettaNet (BTARN)。

> [!NOTE]
>  在 Enterprise Edition 的 BizTalk Server 上，可以安装仅 Enterprise Edition 的 BizTalk Accelerator for RosettaNet (BTARN)。 在标准版的 BizTalk Server 上，可以安装仅标准版本的 BizTalk Accelerator for RosettaNet (BTARN)。  

 BTARN 安装包括以下组件：  

-   BTARN 管理  

-   BizTalk 业务流程设计器 XLANG 调度（合作伙伴接口流程模式）  

-   RosettaNet 实现框架 (RNIF)  

-   BTARN 数据库  

-   HTTP 前端 Web 应用程序  

## <a name="hardware-and-software-requirements"></a>硬件和软件要求

与 BizTalk 服务器相同的最低硬件和软件要求。


|                                                                                         |                                                                                BizTalk 要求                                                                                 |                                                                                                                                                                                                                                                            SQL 和操作系统要求                                                                                                                                                                                                                                                            |
|-----------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                  [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]                   |             [BizTalk Server 2016 的硬件和软件要求](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)             |                                      **SQL Server 的硬件和软件要求**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Windows Server 的硬件要求**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)                                      |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> BizTalk Server 2013 | [BizTalk Server 2013 和 2013 R2 的硬件和软件要求](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) | **SQL Server 的硬件和软件要求**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Windows Server 的硬件要求**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx) |

> [!TIP] 
> 列出的是最低硬件要求。 每个环境都不同，可能你的环境具有更高要求。 请参阅 [Recommendations for Installing, Sizing, Deploying, and Maintaining a BizTalk Server Solution](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)（BizTalk Server 解决方案的安装、大小调整、部署和维护建议）。 

## <a name="install-and-configure"></a>安装和配置

### <a name="before-you-begin"></a>开始之前

* 对于 BTARN 数据库中，BTARN 仅可配置 SQL Server 计算机名称和数据库名称属性。 有关这些属性的信息存储在注册表中。
* 使用的成员帐户登录的 BizTalk Server Administrators 组。 
* 在 BizTalk Server 下载中，BTARN 安装过程中`\BizTalk Accelerators`文件夹。
* 必须安装 BizTalk Server，并且必须运行 SQL Server。
* BTARN 和 BizTalk Server 需要 Microsoft.NET Framework 软件必备组件。 如果必须在计算机上安装的.NET Framework 的多个版本，请确保 BtarnAPP Web 应用程序引用的.NET Framework 4.0 经典。 你可以使用 Internet 信息服务 (IIS) 管理器对此进行配置。  
* BizTalk 主机实例帐户和 BizTalk 独立主机实例帐户应该相同。 否则，BTARN 将无法正常工作。  
* BTARN，可将只有单个服务帐户，而不要使用组，添加到 BizTalk Server Administrators 组或 BizTalk Application Users 组。  
* 你需要为 BTSHTTPReceive.dll 创建 WebService 扩展，并配置 IIS 隔离模式。 有关详细信息，请参阅上的"故障排除:: 问题和解决办法"主题中的"404 找不到错误时发送 HTTP 请求"条目[ http://go.microsoft.com/fwlink/?LinkId=188560 ](http://go.microsoft.com/fwlink/?LinkId=188560)。 此外，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../../core/how-to-configure-iis-for-an-http-receive-location.md)。  
* 添加你的服务器 (http:// <*服务器名称*>) 到本地 Internet 区域中的 Internet Explorer 安全选项。  
*  如果配置 BTARN 时使用的是采用非默认端口的远程 SQL 实例，则必须本地安装 SQL Server 客户端工具。 有关详细信息，请参阅[针对多计算机环境的 BizTalk Server 安装指南](../../install-and-config-guides/install-biztalk-server-in-a-multi-computer-environment.md)。
*  在 BizTalk Server 配置的过程，必须为角色 BizTalk Administrator、 BizTalk Host Users 和 BizTalk Isolated Host Users 使用单独的组。  
*  BTARN 不支持使用针对 SQL 实例，若要配置 BTARN 数据库中创建的别名。  

### <a name="install-btarn"></a>安装 BTARN

1.  运行 BTARN **setup.exe**以管理员身份。

2.  选择“安装”。  

3.  上**客户信息**页上，键入你的用户名、 组织和产品密钥，然后单击**下一步**。  

4.  上**许可协议**页上，阅读最终用户许可协议，，然后单击**接受**。  

    > [!NOTE]
    >  如果不接受许可协议，则无法继续安装。  

5.  上**安装选项**页上，选择**完成**的完整安装或**自定义**部分安装。 请确保安装路径正确，然后依次**下一步**。  

    > [!NOTE]
    >  如果选择**自定义**，选择要从安装的组件**自定义安装**页。 如果您选择安装 SDK 或文档组件，您必须运行安装程序之前安装.NET Framework。  

6.  上**摘要**页上，查看的组件安装，然后依次**安装**。 **安装进度**屏幕将显示安装过程的进度。  

7.  上**安装已完成**页上，确保**运行配置向导**中已选中，然后单击**完成**。  

     BTARN 配置向导将打开。 下一步将配置 BTARN。  

    > [!IMPORTANT]
    >  如果执行自定义安装来仅安装 BTARN HTTP 前端功能，BTARN 配置可能会失败，安装程序完成后，显示"未能为功能创建对象： WebApp"错误。 如果发生这种情况，将两个文件复制 (**Microsoft.VC80.ATL.manifest**并**atl80.dll**) 与 BizTalk Server 的计算机上安装它，到安装了 BTARN HTTP 前端功能的计算机。  
    >   
    >  如果在 BizTalk Server 所在的计算机上安装 Visual Studio，两个文件的源文件夹是 *< 驱动器\>*: \Program Files\Microsoft Visual Studio 11.0\VC\redist\x86\Microsoft.VC100.ATL。 如果在 BizTalk server 上未安装 Visual Studio，在 BizTalk server 上的两个文件的源文件夹是下的文件夹 *< 驱动器\>*: \WINDOWS\WinSxS。 这两个文件的版本应该是 8.0.50727.42。 在已安装 HTTP 前端功能的计算机上的目标文件夹为 BTARN 安装目录 (默认情况下 *< 驱动器\>*: \Program Files\Microsoft BTARN)。  
    >   
    >  这些文件复制到计算机安装了 HTTP 前端功能后，重新运行**Configuration.exe**。  

### <a name="configure-btarn"></a>配置 BTARN  

> [!TIP]
 >  配置 BTARN 之前，请确保映射在 IIS 中的处理程序映射的.NET Framework。 此外，在配置 BTARN 时，您可能需要手动创建 IIS_WPG 组。  

1.  上**Microsoft BTARN 配置向导**页上，选择**基本配置**若要配置服务器的默认设置，或**自定义配置**到使用高级的配置选项将服务器配置。  

    > [!NOTE]
    >  如果你想要配置 btarn，让使用本地管理员帐户，输入与帐户 *< 计算机名称\>\\< 管理员名称\>* 中**用户 ID**字段**服务凭据**区域。  

2.  在中**数据库服务器名称**文字框中，验证显示的服务器名称是否正确。 在中**服务凭据**区域中，输入将在运行此服务帐户 （含有域名） 的用户名和密码。 单击**配置**。  

3.  如果你的帐户具有管理权限，请单击**是**以继续进行配置。  

4.  如果所选**基本配置**在步骤 1 中，验证要在中配置的组件列表**摘要**对话框中，然后单击**下一步**。 转到步骤 10。  

5.  如果所选**自定义配置**在步骤 1 中，执行以下步骤：  

    > [!NOTE]
    >  如果你在任何 BTARN 数据库的名称中使用特殊字符，则 BTARN 配置将失败。  

6.  若要在中配置运行时， **Microsoft BTRAN 配置**对话框中，单击**运行时**的左窗格中。 在右侧**运行时**窗格中，单击**启用此计算机上的运行时功能**。 若要加入现有数据库组，请清除**你想要创建一个新数据库组**。 选择适当的 Web 服务器名称、端口号、数据存储区、应用程序池服务帐户和 BizTalk HTTP 接收虚拟文件夹。  

7.  若要配置 WebApps 功能，在**Microsoft BTRAN 配置**对话框中，单击**WebApps**在左窗格中，然后单击**启用此计算机上的运行时功能**. 输入相应的 BizTalk Server 名称和端口号，或选择默认值。 选择适当的 Web 应用程序虚拟文件夹。  

8.  单击“应用配置”。  

9. 上**摘要**页上，单击**下一步**。  

10. 上**配置已完成**页上，单击**完成**。  

    > [!NOTE]
    >  安装了 BTARN 后，系统管理员必须将用户添加到 BAS Business User、Business Manager 和 Business Administrator 组。 如果你是系统管理员，则必须填充这些组并注销，然后登录将自己添加到这些组中。

    > [!WARNING]
    >  为 BizTalk Administrator、 BizTalk Host Users 和 BizTalk Isolated Host Users 配置 BizTalk Server 时，必须使用三个不同的组。  

## <a name="start-the-artifacts"></a>启动项目
BTARN 业务流程、 发送端口和接收位置配置 BTARN 后不自动启动。

> [!NOTE]
>  必须先启动 PrivateInitiator_To_LOB 和 PrivateResponder_To_LOB 发送端口，然后才能启动 PrivateInitiatorProcess 和 PrivateResponderProcess 业务流程。  

-   对于某些计算机，如果已通过安全套接字层 (SSL) 配置了 Internet Information Services (IIS) 虚拟服务器，则必须先配置虚拟服务器以接受客户端证书。 请参阅[步骤 4： 启用安全套接字在 IIS 中的层](step-4-enabling-secure-sockets-layer-in-iis.md)中[双操作教程](double-action-tutorial.md)。


1.  打开**BizTalk Server 管理**以管理员身份。  

2.  展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk Application 1**。  

3.  单击**发送端口**。 在右窗格中，对于每个未启动的发送端口，右键单击，然后单击**启动**。  

4.  单击**接收端口**并**接收位置**。 在右窗格中，每个接收位置未启动的右键单击，然后再单击**启动**。  

    > [!NOTE]
    >  必须启动 PrivateInitiator_To_LOB 和 PrivateResponder_To_LOB 发送端口，然后才能启动 PrivateInitiatorProcess 和 PrivateResponderProcess 业务流程。  

5.  单击**业务流程**并**接收位置**。 在右窗格中，未启动的每个业务流程，右键单击，然后单击**启动**。  

## <a name="restart-your-computer"></a>重新启动计算机  

请重新启动计算机，以应用对配置和权限所做的任何修改。  

> [!NOTE]
>  开发人员可能出于开发、阶段调试或测试目的，选择在单个服务器上安装并配置 BTARN。 开发人员可使用此服务器编写自定义代码，并在用于生产之前对其进行测试。  

 有关在单个服务器上安装 BTARN 的详细信息，请参阅[Loopback 教程](loopback-tutorial.md)。

## <a name="next-steps"></a>后续步骤  

* [升级 RosettaNet 加速器](upgrade-biztalk-accelerator-for-rosettanet.md)
* [卸载 RosettaNet 加速器](uninstall-biztalk-accelerator-for-rosettanet.md)
* [安装疑难解答和了解已知安装问题](troubleshoot-known-issues-installation.md)