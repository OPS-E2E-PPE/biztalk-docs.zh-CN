---
title: 升级 BizTalk Accelerator for SWIFT |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede2af21-4c7d-4f9e-b255-1ada86eda68d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 873a9d6ab13e152dadf73d20941da8e6e9ce725f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529753"
---
# <a name="upgrade-biztalk-accelerator-for-swift"></a>升级 BizTalk Accelerator for SWIFT
升级[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]BizTalk 服务器上。 

### <a name="before-you-upgrade"></a>升级之前

* 运行升级的用户必须是 BizTalk Server Administrators 组的成员。
* 在执行时，必须运行 SQL Server (MSSQLSERVER) 服务[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]升级。
* 不运行无提示安装升级到[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]。
* 升级 BizTalk Server 中，然后再升级[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]。
* 必须为安装 BizTalk Server 运行时[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]升级以安装及其运行时组件。 如果之前未安装 BizTalk Server 运行时[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]升级，则[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]组件将不安装，并删除上一个程序集从全局程序集缓存 (GAC) 中。
* 当你安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]，MessagePack 安装。 MessagePack 任何现有版本将替换在升级过程。
* 升级到[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]通过运行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]安装。 安装程序将迁移现有[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]配置信息。 
* 升级可能会删除任何已弃用的功能的文件夹和快捷方式。

## <a name="supported-upgrade-paths"></a>支持的升级路径  
 下表列出了受支持[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]可以升级的版本。 "是"表示该版本可以升级。 "否"表示该版本不可升级。 如果[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]版本未列出，该版本无法升级。  


|                                                                                                       | [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)] | BizTalk Server 2013 |
|-------------------------------------------------------------------------------------------------------|------------------------------------------------------|-------------------------------------------------------|---------------------|
| [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 2013 |                         是                          |                          是                          |         否          |
| [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 2010 |                          否                          |                          是                          |         是         |

## <a name="upgrade-a4swift"></a>升级 A4SWIFT

1. 备份[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]数据库和你 SWIFT 消息架构。 安装程序升级[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]数据库。

2. 备份中的任何文件`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT`和`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT MessagePack`已更新的文件夹。
  
3. 取消部署任何项目、 BizTalk 项目或程序集引用的任何[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]MessagePack 程序集。

4. 在 Visual Studio 中，手动取消部署所有[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]按以下顺序的程序集：

* Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration
* Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas
* Microsoft.Solutions.FinancialServices.SWIFT.MrsrService
* Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.

5. 运行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]安装程序以升级。

> [!NOTE]
> 当你升级[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]，升级会删除访问权限**A4SWIFT 管理员**并**A4SWIFT 用户**组从`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT\Service`文件夹。         
        
## <a name="post-upgrade-steps"></a>升级后的步骤

1. 使用[BTSTask.exe](../../core/btstask-command-line-reference.md) (%programfiles%\Microsoft BizTalk Server)，手动重新部署 A4SWIFT 程序集按以下顺序：
2. Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas
3. Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration

     > [!NOTE]
     > 无需重新部署`Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas`。 安装重新部署此程序集。

     > [!IMPORTANT] 
     > 重建和重新部署架构的项目中以前步骤中，删除较旧版本的前`A4SWIFT Base Types.xsd`和`SWIFT Common Data Types.xsd`从架构项目中，将其替换这些架构的消息包版本为然后生成并部署架构项目。 如果不替换这些架构，您将不能用于生成和部署架构项目。

4. 重新生成并部署任何项目或与较旧版本的一起使用的程序集[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]或消息程序包。
5. 如果对 SWIFT 消息程序包架构进行了任何更改，在新的消息包架构中，进行这些更改然后生成并部署这些架构。
6. 取消部署已安装与以前版本的任何现有的 BRE 策略[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]。 然后安装和部署从更高版本的相应策略[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]安装文件。 手动或使用可执行此操作**BREDeployment**工具。

   > [!NOTE]
   > 即使[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]升级在业务规则引擎 (BRE) 功能不会导致任何问题，我们建议您替换的先前版本的[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]BRE 策略与最新的消息包 BRE 策略，为某些 BRE 策略获取更新的每个消息包。
    
7. 如果自定义中的任何文件`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT`文件夹，然后对较新版本进行这些更改。
8. 删除**a4swift_limited** db_denydatareader 角色，如下所示的成员：
    1. 打开 SQL Server Management Studio。 在 Management Studio 中，展开**数据库**，展开**BizTalk Accelerator for SWIFT**，然后选择**角色**。
    2. 双击**a4swift_limited**。 选择**权限**，并检查 SELECT`Bic11`和`Bic10`。 选择**确定**，并关闭属性。
    3. 双击**db_denydatareader**。 在用户字段中，选择**a4swift_limited**，然后选择**删除**。 选择 **确定**。

9. 运行 QFERollUpDBUpdate 脚本：

    > [!NOTE]
    > 您必须是属于**A4Swift 管理员**组运行 QFERollUpDBUpdate 脚本。
    
   1. 打开 SQL Server Management Studio。 在 Management Studio 中，单击新建查询。 
   2. 选择[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]从下拉列表中的数据库。 
   3. 在 Windows 资源管理器，转到`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT\Scripts`，并将其拖**QFERollUpDBUpdate.sql**文件拖到新的查询窗格中，并选择**Execute**。
    
    
## <a name="upgrading-in-a-multi-server-environment"></a>在多服务器环境中升级

在多服务器[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]环境中的，所有服务器上升级 BizTalk Server 中，然后再升级[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]。 按以下顺序将服务器迁移：

* 承载 BizTalk 组的服务器
* 每个处理节点
* BAM 门户服务器


## <a name="next-steps"></a>后续步骤
[配置 BizTalk Accelerator for SWIFT ](../../adapters-and-accelerators/accelerator-swift/configure-biztalk-accelerator-for-swift.md)