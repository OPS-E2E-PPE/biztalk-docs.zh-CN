---
title: 配置 BizTalk Accelerator for SWIFT |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e34b0b2d-f563-468b-b6b9-536f0df96f52
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57b56495e66d835451eb8641f3fd9407462593c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997454"
---
# <a name="configure-biztalk-accelerator-for-swift"></a>配置 BizTalk Accelerator for SWIFT

配置[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]。 

当你安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]，可以自动运行配置的复选框。 或者，你可以打开 BizTalk Accelerator for SWIFT (A4SWIFT) 配置应用程序中列出。

本主题演示如何配置[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]accelerator，如何导出或导入配置，以及列出的配置后步骤。

## <a name="configure-a4swift"></a>配置 A4SWIFT

1. 打开 BizTalk Accelerator for SWIFT (A4SWIFT) 配置。
2. 选择**MCRR**。 MCRR 是仅当您安装了可用**消息修复和新提交**组件。
3. 当系统询问**你想要创建一个新数据库组**:

   * 选择此选项可创建新组中所示**组**窗格。 
   * 若要加入现有数据库组，请取消选中此选项。

4. 如果您安装了**用于消息修复和新提交的 Web 组件**，然后选择**WebService**。
5. 选择托管 A4SWIFT Web 服务的 web 站点。 默认情况下，选择默认网站。
6. 选择**应用配置**。
7. 在中**摘要**，验证配置设置，然后单击**配置**。 

    > [!TIP] 
    > 如有需要，可以将配置设置另存为 XML 文件。

8. 选择**完成**配置完成时。

## <a name="export-or-import-a-configuration"></a>导出或导入配置
可以将 A4SWIFT 的配置设置导出到 XML 文件。 这些设置然后可以导入配置另一个 A4SWIFT 安装。 

### <a name="export-the-configuration"></a>导出配置

1. 打开 Microsoft BizTalk Accelerator for SWIFT 配置，然后选择**导出配置**。
2. 在中**另存为**，浏览到要保存配置文件中，输入配置文件的名称的文件夹，然后**保存**。
3. 当导出成功，则选择**确定**。

### <a name="import-a-configuration"></a>导入配置
1. 打开 Microsoft BizTalk Accelerator for SWIFT 配置，然后选择**导入配置**。
2. 浏览到包含配置文件的文件夹，选择该文件，并选择**导入**。

## <a name="post-configuration-steps"></a>配置后步骤

### <a name="add-users-to-the-a4swift-users-group"></a>将用户添加到 A4SWIFT 用户组

在配置之后[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]，添加运行到 BizTalkServerApplication 主机实例的帐户**A4SWIFT 用户**组 (*不* **A4SWIFT 管理员**组)。 

**步骤**:

1. 打开**Services**。 服务也会出现在**服务器管理器**，然后**工具**。 
2. 在列表中，找到**BizTalk 服务 BizTalk 组： BizTalkServerApplication**。 
3. 双击选择以打开其属性。
4. 在中**Log On**选项卡中，记下的用户帐户列为**此帐户**。
5. 打开**本地用户和组**（在计算机管理），然后找到**A4SWIFT 用户**组。 将用户帐户添加到此组。

> [!TIP] 
> 主机实例帐户需要此组成员身份主机消息修复运行时组件来访问 BizTalk Server 数据库。

### <a name="check-the-identity-of-the-application-pool"></a>检查应用程序池的标识
A4SWIFT_MRSR web 服务承载于 IIS 中的应用程序。 应用程序池标识*不能*是网络服务。 将应用程序池标识更改为本地或域帐户的成员**A4SWIFT 用户**组。

**步骤**:

1. 打开**Internet Information Services 管理器**。 IIS 管理器也会出现在**服务器管理器**，然后**工具**。 
2. 展开**Default Web Site**，并选择 A4SWIFT_MRSR web 服务。 
3. 选择**基本设置**。 列出应用程序池的名称。
4. 在左窗格中，选择**应用程序池**，然后选择应用程序池。
5. 选择**高级设置**，并将更改**标识**必要。