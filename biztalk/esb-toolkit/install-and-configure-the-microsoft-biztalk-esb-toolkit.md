---
title: 安装和配置 Microsoft BizTalk ESB 工具包 |Microsoft Docs
description: 若要安装和配置 BizTalk Server 上的 ESB 工具包的步骤的步骤说明
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
ms.openlocfilehash: 7018a6bfa9d55b58cadfa9b808d7c295f88a2c0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981374"
---
# <a name="install-and-configure-the-microsoft-biztalk-esb-toolkit"></a>安装和配置 Microsoft BizTalk ESB 工具包
使用 BizTalk Server 2013 和较新版本中，启动[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]与集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。 本主题说明如何安装和配置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并且还包括用于升级 ESB 工具包的社区编写的链接。  
  
> [!IMPORTANT]
>  你必须先安装 BizTalk Server，然后才能开始安装 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。  
  
## <a name="install"></a>Install 
  
1. 运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]setup.exe 文件，以管理员身份。 在安装过程中，选择**安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** 。  
  
2. 接受许可协议，然后选择**下一步**。  
  
3. 在“组件安装”中，选择要安装的组件，然后单击“下一步”。  
  
4. 在中**摘要**，查看您选择，然后选择**安装**。  
  
5. 选择“完成”关闭安装向导。  

安装日志会创建一个文件，类似于 C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm。 
  
## <a name="configure"></a>配置 
  
> [!IMPORTANT]
>  你必须先配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后才能配置 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。  
  
1. 从**启动**菜单中，选择**Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** ，然后选择**ESB 配置工具**。  
  
   > [!IMPORTANT]
   >  以管理员身份运行 ESB 配置工具。  
  
2. 在配置中，选择**数据库服务器**。 输入承载的数据库服务器名称[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]数据库。   
  
3. 在中**IIS Web 服务**，输入用户帐户和运行创建的 IIS 应用程序的密码[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。 接下来，输入承载应用程序的 IIS 网站。  
  
4. **BizTalk 用户组**列出了通常用于 ESB 配置的默认用户组。  
  
   > [!IMPORTANT]
   >  在此阶段，你可以选择**应用配置**若要配置[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]使用这些默认设置。 但是，如果你想要进行自定义配置，完成剩余步骤。 按照下一步骤中输入的值优先于默认值。  
  
5. 在左窗格中，展开**ESB 配置**，展开 * * 异常管理 * *，然后：  
  
   -   如果不想配置例外管理数据库，然后选择**数据库**，并取消选中**启用例外管理数据库**。
  
   -   如果你想要使用现有数据库，而不是创建一个新数据库，然后选择**数据库**，然后选择**使用现有数据库**。 输入数据库服务器名称和数据库名称。  
  
   -   如果不想配置异常 web 服务，然后选择**异常 Web 服务**，并取消选中**启用异常服务**。  如果你想要不同的网站下运行这些服务，你可以在此处输入的。  
  
6. 在左窗格中，展开**ESB 核心组件**，，然后：  
  
   -   如果不想配置行程数据库，然后选择**行程数据库**，并取消选中**行程数据库**。  
  
   -   如果你想要使用现有的行程数据库，然后选择**行程数据库**，然后选择**使用现有数据库**。 输入数据库服务器名称和数据库名称。  
  
   -   如果不想配置这些 web 服务，然后选择**核心 Web 服务**，并取消选中**启用核心服务**。 如果你想要不同的网站下运行这些服务，你可以在此处输入的。
  
7. 在左窗格中，选择**配置**。  
   如果在安装和配置[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]在单服务器环境中，选择**文件配置源**。 如果您设置了多计算机部署，请选择**SSO 配置源**，然后输入以下：  
  
   -   **SSO 服务器**： 输入 SSO 服务器的名称
  
   -   **配置文件**： 选择省略号 **（...）**，然后浏览到 esb.config 文件 (\Program 文件 (x86) \Microsoft BizTalk ESB 工具包)
  
   -   **应用程序名称**： 输入的 SSO 应用程序的名称。 例如，输入`ESB Toolkit`。  
  
   -   **联系信息**： 采用以下格式输入有效的电子邮件地址的相应的联系信息： `someone@example.com`。  
  
   -   **管理员组名称**： 选择省略号 **（...）**，然后浏览到适当的管理组  
  
   -   **用户组名称**： 选择省略号 **（...）**，然后浏览到相应的组  

8. 选择**应用配置**。 打开 IIS，并请注意，现在已在配置 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]时指定的网站下创建了 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]所需的应用程序。  
  
9. 在中**ESB 配置工具**，选择**ESB BizTalk 应用程序**，，然后：  
  
   - 选择**BizTalk Server 中启用 ESB 核心组件**若要创建中的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 选择**使用默认绑定**要绑定到默认主机的此应用程序。 选择**不使用默认绑定**如果确实想要绑定到默认主机应用程序。 在此方案中，您必须显式将绑定到主机应用程序后创建的应用程序。  
  
   - 选择**在 BizTalk Server 中启用 ESB JMS/WMQ 组件**若要创建中的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 选择**使用默认绑定**要绑定到默认主机的此应用程序。 选择**不使用默认绑定**如果确实想要绑定到默认主机应用程序。 在此方案中，您必须显式将绑定到主机应用程序后创建的应用程序。  
  
   - 选择**应用配置**创建所选的应用程序。 验证是否在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建了该应用程序。  
  
## <a name="upgrade-esb-toolkit--community-addition"></a>升级 ESB 工具包 – 社区添加内容  
 [就地将 ESB 工具包 2.1 升级到 2.2](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html) (http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)

## <a name="see-also"></a>另请参阅
[排查安装问题和常见错误和解决方法](troubleshooting-the-biztalk-esb-toolkit.md)