---
title: 安装 BizTalk Server 2016 |Microsoft 文档
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
ms.openlocfilehash: f89aa7599040a2cc6c50f11b70c2751fcf2df1ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299973"
---
# <a name="install-biztalk-server-2016"></a>安装 BizTalk Server 2016
在单台计算机上安装 BizTalk Server。

## <a name="before-you-get-started"></a>开始操作之前

* **系统管理员** – 安装 SQL Server 时，安装程序会自动向登录的帐户授予系统管理员权限。 由于安装 BizTalk Server 还需要这些权限，请执行以下操作之一：
  * 使用在安装 SQL Server 时所用的同一帐户。
  * 向登录的帐户授予系统管理员权限。
  * 确定登录的帐户是本地管理员组的成员。
* **帐户名** – 应尽可能使用默认帐户名。 BizTalk Server 安装程序会自动输入默认帐户。 如果域中存在多个 BizTalk Server 组，应更改帐户名，以避免冲突。 如果需要更改名称，BizTalk Server 仅支持 *NetBIOS 域名/用户*格式的服务帐户和 Windows 组。
* **带有 BAM 管理 Web Service 的帐户名** – BizTalk Server 不支持 BAM 管理 Web Service 用户的内置帐户或无密码的帐户。 Web 服务会访问 BizTalk Server 数据库，而此类帐户可能带来安全威胁。

    > [!NOTE] 
    > 使用这些类型的帐户配置 BizTalk Server 可能会成功，但是 BAM 管理 Web Service 会发生故障。 可以对 BAM 应用程序池使用内置帐户或无密码的帐户。

* **BizTalk 程序集查看器** – 在 64 位平台上不受支持。 
* **安装和卸载**卸载 BizTalk Server 需要手动删除 BizTalk Server 数据库。 如果以开发人员或评估人员身份安装 BizTalk Server，请使用虚拟机。 如果需要进行重新安装，可以轻松回滚虚拟机，而无需卸载和删除数据库。
* **32 位和 64 位计算机** – 在 32 位与 64 位计算机上安装 BizTalk Server 之间的差异较少。 安装和配置对 32 位和 64 位计算机均适用。 将介绍两者之间的差别。
* **工作组** - 支持在单台计算机上的工作组环境中安装和配置 BizTalk Server。 SQL Server 和 BizTalk Server 的功能和组件在同一计算机上安装和配置。


## <a name="install-biztalk-server"></a>安装 BizTalk Server
1. 关闭所有打开的程序。 以管理员身份运行 BizTalk Server 安装程序。
2. 选择“安装 Microsoft BizTalk Server 2016”。
3. 输入“用户名”、“组织”和产品密钥。 选择“下一步”。
4. 接受许可协议，然后选择“下一步”。
5. 选择参与客户体验改善计划，然后选择“下一步”。
6. 选择想要安装的组件：

    ![bts2016install_components](../install-and-config-guides/media/bts2016install-components.gif)
  
    请务必选择“其他软件”。 还可以更改安装位置： 
  
    ![bts2016install_additional](../install-and-config-guides/media/bts2016install-additional.gif)

    选择“下一步”。   
  
 7. 具体取决于选择的组件，可能有一些其他系统必备组件，如 ADOMD.NET。 安装程序可自动安装所有可再发行的必备组件。 您的选择包括: 
* **手动安装可再发行必备组件**：此选项会关闭安装向导，以便可以手动安装缺少的必备组件。
* **自动从 Web 安装可再发行的必备组件**：默认选项。 需要 Internet 访问权限。
* **下载可再发行的必备组件 CAB 文件**：下载 CAB 文件，以便稍后进行安装。
* **自动从 CAB 文件安装可再发行的必备组件**：如果之前已下载 CAB 文件，则选择此选项可使用这些 CAB 文件。 

  选择“下一步”。
  
8. 查看摘要页。 若要进行任何更改，请选择“返回”以选中或取消选中任何组件。 

     若要使系统在重新启动后自动登录，请选择“设置”，然后输入登录帐户。 仅在 BizTalk 安装程序中启用此设置。 安装完成后，会禁用此设置。 

    选择“安装”。
  
9. 若要立即配置 BizTalk，请选中“启动 BizTalk Server 配置”。 如果不想立即配置 BizTalk，则取消选中此选项，然后选择“完成”关闭安装向导。 

安装日志文件生成于临时文件夹，如下所示：`C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm`
  
## <a name="check-the-installation"></a>检查安装

* “程序和功能”中会列出 BizTalk Server。
* `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0` 注册表项列出了 BizTalk Server 版本、安装路径、版本和其他详细信息。
* 应用中列出了 BizTalk Server 管理、配置和其他组件。 

## <a name="next-step"></a>下一步
[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)