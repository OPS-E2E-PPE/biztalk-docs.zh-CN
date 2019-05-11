---
title: 安装 BizTalk Server 2016 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f5ac913-0734-45b2-8e25-1db146d81858
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97ea71a309d5073f0c1a00adeff5a94ea62cb958
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266218"
---
# <a name="install-biztalk-server-2016"></a>安装 BizTalk Server 2016
一台计算机上安装 BizTalk Server。

## <a name="before-you-get-started"></a>准备工作

* **系统管理员**： 当你安装 SQL Server 安装程序会自动授予你已登录的帐户系统管理员权限。 由于安装 BizTalk Server 时，还需要执行这些权限，请执行以下操作：
  * 使用安装 SQL Server 时所用的相同帐户。
  * 向登录的帐户授予系统管理员权限。
  * 确认登录的帐户是本地管理员组的成员。
* **帐户名**– 使用默认帐户名，只要有可能。 BizTalk Server 安装程序会自动输入默认帐户。 如果在域中的多个 BizTalk Server 组，更改帐户名，以避免冲突。 如果更改名称，BizTalk Server 仅支持*NetBIOS 域 name\user*的服务帐户和 Windows 组。
* **带有 BAM 管理 Web 服务的帐户名称**– BizTalk Server 不支持内置帐户或无密码的帐户为 BAM 管理 Web 服务用户。 Web 服务会访问 BizTalk Server 数据库和这些帐户可能带来安全威胁。

    > [!NOTE] 
    > 使用这些类型的帐户配置 BizTalk Server 可能会成功，但 BAM 管理 Web 服务会失败。 内置帐户或无密码可用于 BAM 应用程序池。

* **BizTalk 程序集查看器**– 在 64 位平台上不受支持。 
* **安装和卸载**– 卸载 BizTalk Server 需要手动删除 BizTalk Server 数据库。 如果以开发人员或评估师身份安装 BizTalk Server，使用虚拟机。 如果你需要重新安装，您可以轻松回滚虚拟机而无需卸载和删除数据库。
* **32 位和 64 位计算机**– 有一些不同之处 32 位或 64 位计算机上安装 BizTalk Server 时。 安装和配置对 32 位和 64 位计算机。 任何对差异进行说明。
* **工作组**-安装和配置 BizTalk Server 的单台计算机上的工作组环境中受支持。 安装并在同一台计算机上配置 SQL Server 和 BizTalk Server 功能和组件。


## <a name="install-biztalk-server"></a>安装 BizTalk Server
1. 关闭任何打开的程序。 以管理员身份运行 BizTalk Server 安装程序。
2. 选择**安装 Microsoft BizTalk Server 2016**。
3. 输入你**用户名**、 你**组织**，和你的产品密钥。 选择“**下一步**”。
4. 接受许可协议，然后选择**下一步**。
5. 选择参与客户体验改善计划，并选择**下一步**。
6. 选择你想要安装的组件：

    ![bts2016install_components](../install-and-config-guides/media/bts2016install-components.gif)
  
    请务必选择**其他软件**。 此外可以更改安装位置： 
  
    ![bts2016install_additional](../install-and-config-guides/media/bts2016install-additional.gif)

    选择“**下一步**”。   
  
   7. 根据你选择的组件，可能有一些其他先决条件，如 ADOMD.NET。 安装程序可以安装可再发行组件会自动为您的所有必备组件。 您的选择包括：
7. **手动安装可再发行的必备组件**:这会关闭安装向导，以便你可以手动安装缺少的必备组件。
8. **自动从 web 安装可再发行的必备组件**:默认值。 需要 internet 访问权限。
9. **下载可再发行的必备组件 CAB 文件**:下载的 CAB 文件，你可以安装更高版本。
10. **自动从 CAB 文件安装可再发行的必备组件**:如果你以前下载的 CAB 文件，可以选择此选项可以使用这些 CAB 文件。 

    选择“**下一步**”。
  
11. 查看摘要页。 若要进行任何更改，请选择**回**来选中或取消选中任何组件。 

      若要使系统重新启动后自动登录，请选择**设置**，并输入登录帐户。 在 BizTalk 安装程序期间才启用此项。 安装程序完成后，禁用此设置。 

     选择“安装”。
  
12. 若要立即配置 BizTalk，请检查**启动 BizTalk Server 配置**。 如果不想要立即配置 BizTalk，然后取消选中此选项，并选择**完成**若要关闭安装向导。 

安装日志文件生成于临时文件夹，类似于： `C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm`
  
## <a name="check-the-installation"></a>检查安装

* BizTalk Server 所示**程序和功能**。
* `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0`注册表项列出了 BizTalk Server 版本、 安装路径、 版本和其他详细信息。
* BizTalk Server 管理、 配置和其他组件在您的应用程序中列出。 

## <a name="next-step"></a>下一步
[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)