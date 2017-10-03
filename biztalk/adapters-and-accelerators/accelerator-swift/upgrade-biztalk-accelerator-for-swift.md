---
title: "升级 BizTalk Accelerator for SWIFT |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ede2af21-4c7d-4f9e-b255-1ada86eda68d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c4e95d248103d99b4b7f50dc925fb220211530f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="upgrade-biztalk-accelerator-for-swift"></a>升级 BizTalk Accelerator for SWIFT
升级[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]BizTalk 服务器上。 

### <a name="before-you-upgrade"></a>升级之前需完成的操作

* 运行升级的用户必须是 BizTalk Server Administrators 组的成员。
* 执行时，必须运行 SQL Server (MSSQLSERVER) 服务[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]升级。
* 不运行要升级到的无提示安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]。
* 升级 BizTalk Server 中，和[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]。
* 必须为安装 BizTalk Server 运行时[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]升级安装其运行时组件。 如果之前未安装 BizTalk Server 运行时[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]升级，则[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]组件将无法安装，并删除以前的程序集从全局程序集缓存 (GAC) 中。
* 当你安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]，安装 MessagePack。 在升级过程将替换 MessagePack 任何现有版本。
* 升级到[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]通过运行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]安装。 安装程序将迁移现有[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]配置信息。 
* 升级不能删除任何已弃用的功能的文件夹和快捷方式。

## <a name="supported-upgrade-paths"></a>受支持的升级路径  
 下表列出了支持[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]可以升级的版本。 "Yes"，则表示该版本可以升级。 无法升级该版本"否"表示。 如果[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]版本未列出，该版本无法升级。  

||[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]|BizTalk Server 2013|
|---|---|---|---|  
|[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 2013|是|是|是|  
|[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 2010|是|是|是|  


## <a name="upgrade-a4swift"></a>升级 A4SWIFT

1. 备份[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]数据库和你 SWIFT 消息架构。 安装程序升级[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]数据库。

2. 备份中的任何文件`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT`和`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT MessagePack`已更新的文件夹。
  
3. 取消部署任何项目、 BizTalk 项目或对任何引用的程序集[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]MessagePack 程序集。

4. 在 Visual Studio 中，手动取消部署所有[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]按以下顺序的程序集：

* Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration
* Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas
* Microsoft.Solutions.FinancialServices.SWIFT.MrsrService
* Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas。

5. 运行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]安装程序以升级。

> [!NOTE] 
> 当你升级[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]，升级会删除访问权限**A4SWIFT 管理员**和**A4SWIFT 用户**组从`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT\Service`文件夹。         
        
## <a name="post-upgrade-steps"></a>升级后的步骤

1. 使用[BTSTask.exe](../../core/btstask-command-line-reference.md) (%programfiles%\Microsoft BizTalk Server)，手动重新部署 A4SWIFT 程序集按以下顺序：
* Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas
* Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration

    > [!NOTE]
    > 无需重新部署`Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas`。 安装将重新部署此程序集。

    > [!IMPORTANT] 
    > 重建和重新部署架构项目中以前步骤中，删除较旧版本之前`A4SWIFT Base Types.xsd`和`SWIFT Common Data Types.xsd`从架构项目中，将它们替换为这些架构的消息包版本然后生成并部署架构项目。 如果不替换这些架构，你将不能以生成并部署架构项目。

2. 重新生成和部署任何项目或与较旧版本一起使用的程序集[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]或消息包。
3. 如果你已对 SWIFT 消息包架构进行任何更改，进行这些更改，在新的消息包架构中，然后生成并部署这些架构。
4. 取消部署已安装与以前版本的任何现有 BRE 策略[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]。 然后安装和部署中更高版本的相应策略[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]安装文件。 你可以执行此操作手动或通过使用**BREDeployment**工具。

    > [!NOTE] 
    > 即使[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]升级在业务规则引擎 (BRE) 功能不会导致任何问题，我们建议你将以前版本的[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]BRE 策略与最新的消息包 BRE 策略，为一些 BRE 策略获取更新的每个消息包。
    
5. 如果自定义中的任何文件`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT`文件夹，然后对较新版本进行这些更改。
6. 删除**a4swift_limited**作为 db_denydatareader 角色，如下所示的成员：
    1. 打开 SQL Server Management Studio。 在 Management Studio 中，展开**数据库**，展开**BizTalk Accelerator for SWIFT**，然后选择**角色**。
    2. 双击**a4swift_limited**。 选择**权限**，并检查选择`Bic11`和`Bic10`。 选择**确定**，并关闭属性。
    3. 双击**db_denydatareader**。 在用户字段中，选择**a4swift_limited**，然后选择**删除**。 选择“确定”。

7. 运行 QFERollUpDBUpdate 脚本：

    > [!NOTE]
    > 您必须是属于**A4Swift 管理员**QFERollUpDBUpdate 脚本组运行。
    
    1. 打开 SQL Server Management Studio。 在 Management Studio 中，单击新建查询。 
    2. 选择[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]从下拉列表的数据库。 
    3. 在 Windows 资源管理器，转到`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT\Scripts`，并将其拖**QFERollUpDBUpdate.sql**拖到新的查询窗格中，文件，然后选择**执行**。
    
    
## <a name="upgrading-in-a-multi-server-environment"></a>在多服务器环境中升级

在多服务器[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]环境中的，所有服务器上升级 BizTalk Server 中，和[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]。 请按以下顺序迁移服务器：

* 承载 BizTalk 组的服务器
* 各个处理节点
* BAM 门户服务器


## <a name="next-steps"></a>后续步骤
[配置 BizTalk Accelerator for SWIFT](../../adapters-and-accelerators/accelerator-swift/configure-biztalk-accelerator-for-swift.md)