---
title: 安装 BizTalk Accelerator for SWIFT |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- documentation
ms.assetid: 8d492248-fde6-4fd8-be6b-e86ac7d0808b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cfd0ddfbdbe55480d249c01e68a0e571da63591
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006094"
---
# <a name="install-biztalk-accelerator-for-swift"></a>安装 BizTalk Accelerator for SWIFT
安装[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]BizTalk 服务器上。 

\<！---上一个文本
- [BizTalk accelerator for SWIFT 安装指南](http://go.microsoft.com/fwlink/?LinkId=198120)    
- Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]自述文件，位于 \Program Files\Microsoft BizTalk Accelerator for SWIFT 的 \Documentation 文件夹。  
  -->

## <a name="hardware-and-software-requirements"></a>硬件和软件要求

最低硬件和软件要求将与相同[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。


|                                                                                                                                                                   |                                                                                BizTalk 要求                                                                                 |                                                                                                                                                                                                                                                            SQL 和操作系统要求                                                                                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                       [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]                                                        |             [BizTalk Server 2016 的硬件和软件要求](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)             |                                      **SQL Server 的硬件和软件要求**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Windows Server 的硬件要求**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)                                      |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] 2013 | [BizTalk Server 2013 和 2013 R2 的硬件和软件要求](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) | **SQL Server 的硬件和软件要求**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Windows Server 的硬件要求**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx) |

> [!TIP] 
> 列出的是最低硬件要求。 每个环境都不同，可能你的环境具有更高要求。 请参阅 [Recommendations for Installing, Sizing, Deploying, and Maintaining a BizTalk Server Solution](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)（BizTalk Server 解决方案的安装、大小调整、部署和维护建议）。 

## <a name="install-swift"></a>安装 SWIFT

### <a name="before-you-begin"></a>开始之前

* 使用的成员帐户登录的 BizTalk Server Administrators 组。 
* 在您的 BizTalk Server 下载[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]安装过程中`\BizTalk Accelerators`文件夹。
* 必须安装 BizTalk Server，并且必须运行 SQL Server。
* 无提示安装受支持，但不是建议所需的其他配置步骤的复杂性。
* A4SWIFT 安装程序始终使用运行`/InstallPlatform`参数。 因此，安装程序始终安装 msvcr71.dll、 mfc71u.dll、 msvcp71.dll 和 atl71.dll，所需的 Visual Studio。 安装程序将安装到这些 DLL 文件`%WINDIR%\System32`文件夹中，是否 Dll 以前安装了与否。

### <a name="default-installation"></a>默认安装

1. 运行[!INCLUDE[btaA4SWIFTNoVersion_md](../../includes/btaa4swiftnoversion-md.md)] **setup.exe**以管理员身份。
2. 选择“安装”。
3. 输入“用户名”、“组织”和产品密钥。 选择“下一步” 。
4. 阅读许可协议，然后选择**接受**。
5. 选择**完成**，然后选择**下一步**。
6. 审阅**摘要**页。 若要进行任何更改，请选择**回**。

    若要使系统在重新启动后自动登录，请选择“设置”，然后输入登录帐户。 在安装过程才启用此项。 安装完成后，会禁用此设置。

    选择“安装”。

7. 选择**完成**时完成。 安装日志文件生成于临时文件夹，类似于： `C:\Users\username\AppData\Local\Setup(111016 xxxxxx).log`。

> [!NOTE]
> 如果**运行配置向导**上的安装已完成页中，选择[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]单击时自动运行配置向导**完成**。 


### <a name="custom-installation"></a>自定义安装

1. 运行[!INCLUDE[btaA4SWIFTNoVersion_md](../../includes/btaa4swiftnoversion-md.md)] **setup.exe**以管理员身份。
2. 选择“安装”。
3. 输入“用户名”、“组织”和产品密钥。 选择“下一步” 。
4. 阅读许可协议，然后选择**接受**。
5. 选择**自定义**，然后选择**下一步**。
6. 选择你的组件，并选择**下一步**:


   |                     选择此选项                      |                                                                      执行的操作                                                                      |
   |------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                  A4Swift 组件                  |                          所需的 SWIFT 消息与 BizTalk Server 的过程 （架构解析、 分析、 验证）                          |
   |          消息修复和对帐           |    安装管道、 业务流程和运行时架构。 创建 A4SWIFT 数据库在 SQL Server 中的消息传送、 修复和对帐。     |
   | 消息修复和新提交的 web 组件 | 用于消息修复和新提交创建验证、 证书安全、 历史记录和 BIC 查找的 web 服务的安装组件。 |
   |            软件开发工具包 (SDK)            |                                    包括用于 Visual Studio 示例源的代码、 工具包和初学者项目。                                    |
   |                BRE 部署实用工具                |               用于部署与已部署的 SWIFT 消息类型相关联的业务规则引擎 (BRE) 策略的实用工具。               |
   |                       教程                       |                                Iincludes 说明和开发 SWIFT 解决方案在 BizTalk Server 中的示例。                                 |
   |                        工具                         |                                                       包括用于 A4SWIFT 开发的工具。                                                        |
   |                        数据源                        |                                                 安装示例的源代码 A4SWIFT 开发。                                                 |


7. 审阅**摘要**页。 若要进行任何更改，请选择**回**。

    选择“安装”。

8. 选择**完成**时完成。 安装日志文件生成于临时文件夹，类似于： `C:\Users\username\AppData\Local\Setup(111016 xxxxxx).log`。

> [!NOTE]
> 如果**运行配置向导**上的安装已完成页中，选择[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]单击时自动运行配置向导**完成**。 

## <a name="next-steps"></a>后续步骤
[配置 BizTalk Accelerator for SWIFT ](../../adapters-and-accelerators/accelerator-swift/configure-biztalk-accelerator-for-swift.md)