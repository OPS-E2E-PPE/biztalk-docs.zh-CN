---
title: "配置 BizTalk Accelerator for SWIFT |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e34b0b2d-f563-468b-b6b9-536f0df96f52
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaa9812243ef7d5ff4bb8b902ac7aee48e54ab99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-biztalk-accelerator-for-swift"></a>配置 BizTalk Accelerator for SWIFT

配置[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]。 

当你安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]，没有一个复选框，让你自动运行配置。 或者，你可以打开 BizTalk Accelerator for SWIFT (A4SWIFT) 配置你的应用程序中列出。

本主题演示如何配置[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]快捷键，如何导出或导入配置，以及列表后配置步骤。

## <a name="configure-a4swift"></a>配置 A4SWIFT

1. 打开 BizTalk Accelerator for SWIFT (A4SWIFT) 配置。
2. 选择**MCRR**。 MCRR 可仅当你安装**消息修复和新提交**组件。
3. 当系统询问**你想要创建新的数据库组**:

  * 选择此选项以创建新组中所示**组**窗格。 
  * 若要加入现有的数据库组，请取消选中此选项。

3. 如果你安装**用于消息修复和新提交的 Web 组件**，然后选择**WebService**。
4. 选择要承载 A4SWIFT Web 服务的 web 站点。 默认情况下，选择 Default Web Site。
5. 选择**应用配置**。
6. 在**摘要**，验证配置设置，然后单击**配置**。 

    > [!TIP] 
    > 如有需要，可以将配置设置另存为 XML 文件。

7. 选择**完成**当配置完成。

## <a name="export-or-import-a-configuration"></a>导出或导入配置
可以将 A4SWIFT 的配置设置导出到 XML 文件。 这些设置然后可以导入配置另一个 A4SWIFT 安装。 

### <a name="export-the-configuration"></a>导出配置

1. 打开 Microsoft BizTalk Accelerator for SWIFT 配置，并选择**导出配置**。
2. 在**另存为**，浏览到你想要保存配置文件中，输入配置文件的名称的文件夹，然后**保存**。
3. 当导出成功，则选择**确定**。

### <a name="import-a-configuration"></a>导入配置
1. 打开 Microsoft BizTalk Accelerator for SWIFT 配置，并选择**导入配置**。
2. 浏览到包含配置文件的文件夹，选择的文件，然后选择**导入**。

## <a name="post-configuration-steps"></a>后配置步骤

### <a name="add-users-to-the-a4swift-users-group"></a>将用户添加到 A4SWIFT 用户组

在配置之后[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]，将运行到 BizTalkServerApplication 主机实例的帐户添加**A4SWIFT 用户**组 (*不* **A4SWIFT 管理员**组)。 

**步骤**:

1. 打开**服务**。 服务还会显示在**服务器管理器**，，然后**工具**。 
2. 在列表中，查找**BizTalk 服务 BizTalk 组： BizTalkServerApplication**。 
3. 双击选择以打开其属性。
4. 在**Log On**选项卡上，注意用户帐户列为**此帐户**。
5. 打开**本地用户和组**（在计算机管理），然后找到**A4SWIFT 用户**组。 将用户帐户添加到此组。

> [!TIP] 
> 主机实例的帐户需要此组成员身份主机消息修复运行时组件以访问 BizTalk Server 数据库。

### <a name="check-the-identity-of-the-application-pool"></a>检查应用程序池的标识
A4SWIFT_MRSR web 服务承载于 IIS 中的应用程序。 应用程序池标识*无法*是网络服务。 将应用程序池标识更改为本地或域帐户是成员的**A4SWIFT 用户**组。

**步骤**:

1. 打开**Internet Information Services 管理器**。 IIS 管理器还会显示在**服务器管理器**，，然后**工具**。 
2. 展开**Default Web Site**，并选择 A4SWIFT_MRSR web 服务。 
3. 选择**基本设置**。 列出应用程序池的名称。
4. 在左窗格中，选择**应用程序池**，然后选择你的应用程序池。
5. 选择**高级设置**，并更改**标识**必要。