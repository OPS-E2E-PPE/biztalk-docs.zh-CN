---
title: "安装 BizTalk Accelerator for SWIFT |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: documentation
ms.assetid: 8d492248-fde6-4fd8-be6b-e86ac7d0808b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e28d5dac74bdbceb0fe4938810779d6ccb5c52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-biztalk-accelerator-for-swift"></a>安装 BizTalk Accelerator for SWIFT
安装[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]BizTalk 服务器上。 

\<！---上一个文本
-   [BizTalk Accelerator for SWIFT 的安装指南](http://go.microsoft.com/fwlink/?LinkId=198120)    
-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]自述文件，位于 files\microsoft BizTalk Accelerator for SWIFT \Documentation 文件夹。  
-->

## <a name="hardware-and-software-requirements"></a>硬件和软件要求

最低硬件和软件要求是相同[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。

|  |BizTalk 要求  |SQL 和操作系统要求 |  
|---------|---------|--------- | 
| [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [BizTalk Server 2016 的硬件和软件要求](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) | **SQL Server 的硬件和软件要求**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Windows 服务器硬件要求**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx) |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] 2013 | [硬件和软件要求 BizTalk Server 2013 和 2013 R2](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) |**SQL Server 的硬件和软件要求**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Windows 服务器硬件要求**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx)  |

> [!TIP] 
> 列出的是最低硬件要求。 每个环境都不同，可能你的环境具有更高要求。 请参阅 [Recommendations for Installing, Sizing, Deploying, and Maintaining a BizTalk Server Solution](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)（BizTalk Server 解决方案的安装、大小调整、部署和维护建议）。 

## <a name="install-swift"></a>安装 SWIFT

### <a name="before-you-begin"></a>开始之前

* 使用成员的帐户登录 BizTalk Server Administrators 组。 
* 在你的 BizTalk Server 下载，[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]安装程序正在`\BizTalk Accelerators`文件夹。
* 必须安装 BizTalk Server，并且必须运行 SQL Server。
* 无提示安装支持，但不是建议所需的其他配置步骤的复杂性。
* A4SWIFT 安装程序始终使用运行`/InstallPlatform`自变量。 因此，安装程序始终安装 msvcr71.dll，mfc71u.dll、 msvcp71.dll，并且 atl71.dll，其所需的 Visual Studio。 安装程序将安装到这些 DLL 文件`%WINDIR%\System32`文件夹中，是否 Dll 以前安装或不。

### <a name="default-installation"></a>默认安装

1. 运行[!INCLUDE[btaA4SWIFTNoVersion_md](../../includes/btaa4swiftnoversion-md.md)] **setup.exe**以管理员身份。
2. 选择“安装”。
3. 输入“用户名”、“组织”和产品密钥。 选择“下一步” 。
4. 阅读许可协议，，然后选择**接受**。
5. 选择**完成**，然后选择**下一步**。
6. 查看**摘要**页。 若要进行任何更改，请选择**回**。

    若要使系统在重新启动后自动登录，请选择“设置”，然后输入登录帐户。 在安装过程中仅启用此选项。 安装完成后，会禁用此设置。

    选择“安装”。
 
7. 选择**完成**完成时。 安装程序日志文件生成在临时文件夹中，类似于： `C:\Users\username\AppData\Local\Setup(111016 xxxxxx).log`。

> [!NOTE] 
> 如果**运行配置向导**在安装完成页上，选择[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]当你单击时自动运行配置向导**完成**。 


### <a name="custom-installation"></a>自定义安装

1. 运行[!INCLUDE[btaA4SWIFTNoVersion_md](../../includes/btaa4swiftnoversion-md.md)] **setup.exe**以管理员身份。
2. 选择“安装”。
3. 输入“用户名”、“组织”和产品密钥。 选择“下一步” 。
4. 阅读许可协议，，然后选择**接受**。
5. 选择**自定义**，然后选择**下一步**。
6. 选择你的组件，，然后选择**下一步**:

    | 选择此选项 | 执行的操作 |
    | --- | --- |
    | A4Swift 组件 | 所需的与 BizTalk Server SWIFT 消息的进程 （架构解析、 分析、 验证） |
    | 消息修复和调节 | 安装管道、 业务流程和运行时架构。 创建 A4SWIFT 数据库在 SQL Server 中的消息、 修复和对帐。 |
    | 用于消息修复和新提交的 web 组件 | 安装适用于消息修复和创建用于验证、 证书的安全性、 历史记录和 BIC 查找 web 服务的新提交的组件。 |
    | 软件开发工具包 (SDK) | Visual Studio 包括示例源代码、 工具包和初学者项目。 | 
    | BRE 部署实用工具 | 用于部署与已部署的 SWIFT 消息类型相关联的业务规则引擎 (BRE) 策略的实用工具。 |
    | 教程 | Iincludes 说明和有关开发 SWIFT 解决方案 BizTalk Server 中的示例。 |
    | 工具 | 包含用于 A4SWIFT 开发工具。 |
    | 数据源 | 安装源的示例代码 A4SWIFT 开发。 |
    
6. 查看**摘要**页。 若要进行任何更改，请选择**回**。

    选择“安装”。
 
7. 选择**完成**完成时。 安装程序日志文件生成在临时文件夹中，类似于： `C:\Users\username\AppData\Local\Setup(111016 xxxxxx).log`。

> [!NOTE]
> 如果**运行配置向导**在安装完成页上，选择[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]当你单击时自动运行配置向导**完成**。 

## <a name="next-steps"></a>后续步骤
[配置 BizTalk Accelerator for SWIFT](../../adapters-and-accelerators/accelerator-swift/configure-biztalk-accelerator-for-swift.md)