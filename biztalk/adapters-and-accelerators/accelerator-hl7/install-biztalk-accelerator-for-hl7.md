---
title: 安装 BizTalk Accelerator for HL7 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52347742-f858-47bb-bc73-1a6095ea9e8e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d20e2fa78d921c160b8dfe6b96c79c1b15d353e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004990"
---
# <a name="install-biztalk-accelerator-for-hl7"></a>安装 BizTalk Accelerator for HL7

## <a name="hardware-and-software-requirements"></a>硬件和软件要求

最低硬件和软件要求将与相同[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。 


|                                                                                                                                                                   |                                                                                BizTalk 要求                                                                                 |                                                                                                                                                                                                                                                            SQL 和操作系统要求                                                                                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                       [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]                                                        |             [BizTalk Server 2016 的硬件和软件要求](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)             |                                      **SQL Server 的硬件和软件要求**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Windows Server 的硬件要求**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)                                      |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] 2013 | [BizTalk Server 2013 和 2013 R2 的硬件和软件要求](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) | **SQL Server 的硬件和软件要求**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Windows Server 的硬件要求**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx) |

> [!TIP]
> 列出的是最低硬件要求。 每个环境都不同，可能你的环境具有更高要求。 请参阅[有关安装、 大小调整、 部署和维护 BizTalk Server 解决方案的建议](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)

## <a name="install-hl7"></a>安装 HL7

### <a name="before-you-begin"></a>开始之前

* HL7 accelerator 安装文件位于`BizTalk Server <version>\BizTalk Accelerators`上[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]ISO，下载位置，网络共享或任何位置下载[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]程序。
* 用户安装和配置[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]必须是 BizTalk Administrators 组的成员和 SQL Server 上的管理员组的成员位置[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]数据存储。
* 计算机和登录的用户必须有权访问主域控制器 (PDC)。 如果安装程序无法访问 PDC，则安装将失败，并且不会继续。  
* BizTalk Server 应包括具有标准的全新的框适配器，企业单一登录 (SSO)、 组和运行时的 32 位 BizTalkServerApplication 主机的基本组件安装和配置。
* 读取[安装的已知问题](../../adapters-and-accelerators/accelerator-hl7/installation-known-issues.md)。
* [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 目前在 Enterprise 和 Standard Edition。 下表显示了不同版本之间的兼容性[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  


  | [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 版本 | 兼容版本 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] |
  |-----------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
  |                                      Enterprise Edition                                       |                                     Enterprise Edition                                      |
  |                                       Standard Edition                                        |                               Enterprise 或 Standard Edition                                |
  |                                       Developer Edition                                       |                                     Enterprise Edition                                      |

### <a name="default-installation"></a>默认安装

1. 运行[!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)](A4HL7) **setup.exe**以管理员身份。 

   > [!TIP]
   >  从开始[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]及更高版本，[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]安装包括 32 位安装包和 64 位安装包。
   > 
   > 在 32 位计算机上，仅安装 32 位包。 在 64 位计算机上安装 32 位**或**64 位包。 64 位包使适配器和管道在 32 位和 64 位模式下都能运行。  

2. 在欢迎页上，选择**下一步**。  

3. 接受**许可协议**，然后选择**下一步**。  

4. 输入用户名和组织，并选择**下一步**。  

5. 选择**典型**安装程序，并选择**下一步**。  

6. **日志记录服务帐户**页自动提供了以下组的日志记录权限： 

   * BizTalk Server Administrators
   * BizTalk Application Users
   * BizTalk Server B2B Operators
   * BizTalk Server Operators

   选择“下一步” 。 

7. 查看摘要，然后选择**下一步**。  

8. 有关**目标文件夹**，选择**下一步**若要使用的默认文件夹。 或者，选择**更改**选择不同的安装文件夹。 

9. 在中**日志记录数据库信息**，输入以下内容，并选择**下一步**。  


   |         使用此选项         |                                                                                                                                                                                                                   执行的操作                                                                                                                                                                                                                   |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **数据库服务器名称** |                                                                                                                             默认值为服务器名称。 <br/><br/>**请注意**服务器名称默认为 BizTalkMgmtDb 数据库所在的计算机的名称。 不能更改此值。                                                                                                                              |
   |  **HL7 数据库名称**   | 输入包含的数据的数据库的名称在[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]解决方案，或接受默认设置，即**BTAHL7**。 <br/><br/>**请注意**必须使用每个数据库要求; 的 ANSI ASCII 字符集[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]不支持其他字符集。 |
   |   **测试连接**    |                                                                                                                                                                                              选择以确认你拥有 SQL Server 连接。                                                                                                                                                                                               |

    > [!NOTE]
    >  如果为所选的数据库存在，则会显示一个消息框。 选择“确定”继续。  

10. 选择“安装”。

11. 选择**完成**时完成。  

    > [!TIP] 
    > 选择**启动教程**安装端到端教程。 

### <a name="custom-installation"></a>自定义安装
1. 运行[!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)](A4HL7) **setup.exe**以管理员身份。 

   > [!TIP]
   >  从开始[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]及更高版本，[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]安装包括 32 位安装包和 64 位安装包。 
   > 
   > 在 32 位计算机上，仅安装 32 位包。 在 64 位计算机上安装 32 位**或**64 位包。 64 位包使适配器和管道在 32 位和 64 位模式下都能运行。  

2. 在欢迎页上，选择**下一步**。  

3. 接受**许可协议**，然后选择**下一步**。  

4. 输入用户名和密码，并选择**下一步**。  

5. 选择**自定义**，然后选择**下一步**。  

6. 选择你想要安装，然后选择的功能**下一步**。  


   |       功能        |      子功能       |                                                                                                   Description                                                                                                    | 典型安装 | 自定义安装 |
   |----------------------|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|----------------|
   |      **引擎**      |                        |                                 验证、 处理并将消息路由。<br /><br /> 必须是 BizTalk Server Administrators 组的成员，才能安装此功能。                                  |        ✓        |       ✓        |
   |      **引擎**      |   引擎组件    |                                      进程[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]平面文件和 XML 编码的消息。                                      |        ✓        |       ✓        |
   |      **引擎**      |   出站批处理    |                                       创建并将路由[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]批处理格式的文档。                                        |        ✓        |       ✓        |
   |      **引擎**      |       管道        |                                      示例管道用于生成在[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]解决方案。                                       |        ✓        |       ✓        |
   |     **适配器**      |                        |                                                                                    若要启用终结点连接的实用工具。                                                                                    |        ✓        |       ✓        |
   |     **适配器**      |          MLLP          |                          若要启用基于 IP 的连接使用的 MLLP 适配器[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]MLLP 协议。                           |        ✓        |       ✓        |
   |     **适配器**      |     MLLP 测试工具     |                                                   测试工具，它模拟基于 MLLP 发送和接收客户端应用程序通过基于 IP 的连接。                                                    |                 |                |
   |     **架构**      |                        |                                                                                HL7 V2 的所选内容。基于 XSD 架构 X 平面文件。                                                                                |        ✓        |       ✓        |
   |    **项目**     |                        |                                             使用工具[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。                                              |                 |       ✓        |
   |    **项目**     |     业务流程      |                               示例业务流程可用来生成你[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]解决方案。                                |                 |       ✓        |
   | **其他组件** |     测试实例     |                           示例/测试数据，可以使用作为起始点，为你[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]解决方案。                           |                 |                |
   | **其他组件** |           -            |                                                  中的其他组件[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]。                                                   |        ✓        |       ✓        |
   | **其他组件** | 配置资源管理器 |                           应用程序，用于定义数据存储的日志记录配置特定于参与方的验证、 标头映射、 批处理和确认要求。                            |        ✓        |       ✓        |
   | **其他组件** |          SDK           |                                    包含用于 HL7 2.xml 架构，实用程序，例如组件和项目和所需的端到端教程 MLLP 实用程序。                                     |        ✓        |       ✓        |
   | **其他组件** |   日志记录框架    |                                       支持的日志记录组件[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]事件。                                        |        ✓        |       ✓        |
   | **其他组件** |    初学者项目     | 插件[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，它使[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]项目开发。 |        ✓        |       ✓        |


7. 在中**日志记录服务帐户**，输入以下内容，并选择**下一步**。  


   |     使用此选项     |                              执行的操作                              |
   |------------------|----------------------------------------------------------------------|
   | **帐户名** | 输入想要用来启动日志记录服务的帐户名称。 |
   |   **密码**   |                 输入此帐户的密码。                 |
   |    **域**    |               输入此帐户的域名。                |


8. 出现提示时**帐户名已被授予登录，为服务正确**，选择**确定**。  

9. 查看摘要，然后选择**下一步**。  

10. 有关**目标文件夹**，选择**下一步**若要使用的默认文件夹。 或者，选择**更改**选择不同的安装文件夹。

11. 在中**日志记录数据库信息**页上，输入以下内容，并选择**下一步**。  


    |         使用此选项         |                                                                                                                                                                                                                   执行的操作                                                                                                                                                                                                                    |
    |--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | **数据库服务器名称** |                                                                                                                              默认值为服务器名称。 <br/><br/>**请注意**服务器名称默认为 BizTalkMgmtDb 数据库所在的计算机的名称。 不能更改此值。                                                                                                                              |
    |  **HL7 数据库名称**   | 输入包含的数据的数据库的名称在[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]解决方案，或接受默认设置; 这是**BTAHL7**。 <br/><br/> **请注意**必须使用每个数据库要求; 的 ANSI ASCII 字符集[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]不支持其他字符集。 |


12. 选择“安装”。  

13. 选择**完成**时完成。  

    > [!TIP] 
    > 选择**启动教程**安装端到端教程。   

## <a name="next-steps"></a>后续步骤
单步执行在一些教程[开始使用 BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)。