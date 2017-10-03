---
title: "如何更改服务帐户和密码 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dff53d6b-c262-4b66-b822-1c61f54ae105
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ce9dc143765f9db49c5880da4fa4202e26c0f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-service-accounts-and-passwords"></a>如何更改服务帐户和密码
在配置 BizTalk Server 之后，很常见的组织需要通过帐户策略，例如密码策略和帐户锁定策略来更改服务帐户或密码。 有关帐户策略的详细信息，请参阅 Microsoft TechNet 网站，网址[http://go.microsoft.com/fwlink/?LinkId=62172](http://go.microsoft.com/fwlink/?LinkId=62172)。  
  
 在更改服务帐户或密码时，你必须执行以下操作：  
  
1.  创建新的服务帐户或更改现有帐户的密码。  
  
2.  确保服务帐户是必需的 Windows 组的成员。 您必须将服务帐户添加到其中的本地或域组有关的信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
    > [!NOTE]
    >  在域组环境中，你将使用 Active Directory 用户和计算机控制台。 在本地组环境中，你将使用计算机管理控制台。  
  
3.  执行以下任务，具体取决于服务帐户的类型。  
  
    |服务或帐户|如何更改用户帐户|更改用户帐户后所需的任务|如何更改密码|更改密码后所需的任务|  
    |------------------------|---------------------------------|-------------------------------------------------|-----------------------------|---------------------------------------------|  
    |企业单一登录服务主密钥服务器上|1.确保你有主密钥的备份。 有关详细信息，请参阅[如何返回向上主密钥](../core/how-to-back-up-the-master-secret.md)。<br />2.更改服务帐户使用服务控制台。<br />3.还原主密钥。 有关详细信息，请参阅[如何还原主密钥](../core/how-to-restore-the-master-secret.md)。|重新启动服务。|使用“服务”控制台更改帐户的密码。|重新启动服务。|  
    |企业单一登录服务|更改服务帐户使用服务控制台。|重新启动服务。|使用“服务”控制台更改帐户的密码。|重新启动服务。|  
    |BizTalk 主机实例|更改服务帐户使用 BizTalk Server 管理控制台|重新启动 BizTalk 主机实例。|使用 BizTalk Server 管理控制台或“服务”控制台更改帐户的密码。|重新启动 BizTalk 主机实例|  
    |BizTalk 隔离主机实例和相应的应用程序池承载 SOAP 接收适配器|1.更改服务帐户使用 BizTalk Server 管理控制台<br />2.更改为使用 IIS 管理控制台应用程序池帐户**注意：**应用程序池的服务帐户应与相应的独立主机匹配的服务帐户。|1.更改服务帐户使用 IIS 管理控制台的相应应用程序池。<br />2.重新启动应用程序池使用 IIS 管理控制台。|更改应用程序池运行的帐户的密码。 使用 IIS 管理控制台**注意：**无需更改密码后更改 BizTalk Server 管理控制台中的密码。|1.更改在其下的相应的应用程序池运行使用 IIS 管理控制台的帐户的密码。<br />2.重新启动应用程序池使用 IIS 管理控制台。|  
    |规则引擎更新服务|使用配置管理器或“服务”控制台更改服务帐户。<br /><br /> Configuration Manager 自动重新启动该服务。|如果使用“服务”控制台，则必须手动启动该服务。|使用配置管理器或“服务”控制台更改帐户的密码。<br /><br /> Configuration Manager 自动重新启动该服务。|如果你使用服务控制台，你必须手动重新启动服务。|  
    |BAM 通知服务|1.将新帐户添加到 SQL server 安装 BAM 通知服务的位置。<br />2.授予对新的帐户的权限。 有关所需的权限的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)<br />3.更改服务帐户使用服务控制台。|重新启动服务。|使用“服务”控制台更改帐户的密码|重新启动服务。|  
    |BAM 管理 Web 服务|1.将新帐户添加到相应的 SQL 服务器，将在特权授予[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。<br />2.使用 Configuration Manager 的用户帐户进行更改。||更改使用 Configuration Manager 的用户帐户的密码。||  
    |BAM 应用程序池|更改使用 Configuration Manager 的应用程序池的服务帐户。<br /><br /> Configuration Manager 会自动回收应用程序池。||更改使用 Configuration Manager 的帐户的密码。<br /><br /> Configuration Manager 会自动回收应用程序池。||  
  
 以下过程介绍如何更改服务帐户和使用 Configuration Manager 的密码。  
  
### <a name="to-change-service-accounts-and-passwords-using-configuration-manager"></a>若要更改服务帐户和使用配置管理器密码  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。  
  
2.  在**Microsoft BizTalk Server 配置**，单击**视图**，单击**服务帐户**，然后将更改服务帐户和密码在**服务帐户**对话框。 关于 Configuration Manager 的详细信息，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。  
  
    > [!NOTE]
    >  配置管理器不提供到控制多台计算机一个集中的位置。 如果你在多台计算机上安装 Microsoft BizTalk Server，你必须更改服务帐户和运行时中的每台计算机上的密码。  
  
## <a name="see-also"></a>另请参阅  
 [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)   
 [管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)   
 [管理 Windows 组和用户帐户的最佳做法](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)   
 [管理主机和服务帐户](../core/managing-hosts-and-service-accounts.md)