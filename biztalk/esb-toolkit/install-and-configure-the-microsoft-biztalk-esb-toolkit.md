---
title: 安装和配置 Microsoft BizTalk ESB 工具包 |Microsoft 文档
description: 步骤的步骤说明上安装和配置 ESB 工具包 BizTalk Server
caps.latest.revision: 8
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 698843f7-8361-4d02-9278-0e66f2a9f472
ms.author: mandia
ms.openlocfilehash: 33805fe58298e4f4729161a62742d3b204996b00
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22296997"
---
# <a name="install-and-configure-the-microsoft-biztalk-esb-toolkit"></a>安装和配置 Microsoft BizTalk ESB 工具包
使用 BizTalk Server 2013 和更高版本中，启动[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]与集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。 本主题说明如何安装和配置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并且还包括社区编写的链接，以升级 ESB 工具包。  
  
> [!IMPORTANT]
>  你必须先安装 BizTalk Server，然后才能开始安装 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。  
  
## <a name="install"></a>Install 
  
1.  运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以管理员身份的 setup.exe 文件。 在设置中，选择**安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** 。  
  
2.  接受许可协议，然后选择**下一步**。  
  
3.  在“组件安装”中，选择要安装的组件，然后单击“下一步”。  
  
4.  在**摘要**，查看您选择，，然后选择**安装**。  
  
5.  选择“完成”关闭安装向导。  

An install log file is created, similar to `C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm'. 
  
## <a name="configure"></a>配置 
  
> [!IMPORTANT]
>  你必须先配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后才能配置 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。  
  
1.  从**启动**菜单上，选择**Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** ，然后选择**ESB 配置工具**。  
  
    > [!IMPORTANT]
    >  以管理员身份运行 ESB 配置工具。  
  
2.  在配置中，选择**数据库服务器**。 输入数据库服务器名称承载[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]数据库。   
  
3.  在**IIS Web 服务**，输入用户帐户和运行创建的 IIS 应用程序的密码[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。 接下来，输入承载应用程序的 IIS 网站。  
  
4.  **BizTalk 用户组**列出通常用于 ESB 配置的默认用户组。  
  
    > [!IMPORTANT]
    >  在此阶段，你可以选择**应用配置**配置[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]使用这些默认设置。 但是，如果你想要自定义配置，则完成剩余步骤。 在后续步骤中输入的 Rhe 值优先于默认值。  
  
5.  在左窗格中，展开**ESB 配置**，展开 * * 异常管理 * *，然后：  
  
    -   如果你不想要配置异常管理数据库，然后选择**数据库**，并取消选中**启用异常管理数据库**。
  
    -   如果你想要使用现有数据库，而不是创建一个新数据库，然后选择**数据库**，然后选择**使用现有数据库**。 输入数据库服务器名称和数据库名称。  
  
    -   如果你不想要配置异常 web 服务，然后选择**异常 Web 服务**，并取消选中**启用异常服务**。  如果你想要运行这些服务在不同的网站下，你可以在此处输入的。  
  
6.  在左窗格中，展开**ESB 核心组件**，，然后：  
  
    -   如果你不想要配置路线数据库，然后选择**路线数据库**，并取消选中**路线数据库**。  
  
    -   如果你想要使用现有路线数据库，然后选择**路线数据库**，然后选择**使用现有数据库**。 输入数据库服务器名称和数据库名称。  
  
    -   如果你不想要配置这些 web 服务，然后选择**核心 Web 服务**，并取消选中**启用核心服务**。 如果你想要运行这些服务在不同的网站下，你可以在此处输入的。
  
7.  在左窗格中，选择**配置**。  
    如果你安装和配置[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]在单个服务器环境中，选择**文件配置源**。 如果您设置了多计算机部署，选择**SSO 配置源**，然后输入以下：  
  
    -   **SSO 服务器**： 输入 SSO 服务器的名称
  
    -   **配置文件**： 选择省略号 **（...）**，然后浏览到 esb.config 文件 (\Program Files (x86) \Microsoft BizTalk ESB 工具包)
  
    -   **应用程序名称**： 输入 SSO 应用程序的名称。 例如，输入`ESB Toolkit`。  
  
    -   **联系信息**： 采用以下格式输入有效的电子邮件地址的合适的联系信息： `someone@example.com`。  
  
    -   **管理员组名称**： 选择省略号 **（...）**，然后浏览到相应的管理员组  
  
    -   **用户组名称**： 选择省略号 **（...）**，然后浏览到相应的组  

8.  选择**应用配置**。 打开 IIS，并请注意，现在已在配置 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]时指定的网站下创建了 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]所需的应用程序。  
  
9. 在**ESB 配置工具**，选择**ESB BizTalk 应用程序**，，然后：  
  
    -   选择**BizTalk Server 中启用 ESB 的核心组件**创建中的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 选择**使用默认绑定**要绑定到默认主机此应用程序。 选择**不使用默认绑定**如果你不想要绑定到默认主机应用程序。 在此方案中，你必须显式将绑定到主机应用程序后创建应用程序。  
  
    -   选择**BizTalk Server 中启用 ESB JMS/WMQ 组件**创建中的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 选择**使用默认绑定**要绑定到默认主机此应用程序。 选择**不使用默认绑定**如果你不想要绑定到默认主机应用程序。 在此方案中，你必须显式将绑定到主机应用程序后创建应用程序。  
  
    -   选择**应用配置**创建你选定的应用程序。 验证是否在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建了该应用程序。  
  
## <a name="upgrade-esb-toolkit--community-addition"></a>升级 ESB 工具包 – 社区加码  
 [就地将 ESB 工具包 2.1 升级到 2.2](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html) (http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)

## <a name="see-also"></a>另请参阅
[解决安装问题，以及常见的错误和解决方法](troubleshooting-the-biztalk-esb-toolkit.md)