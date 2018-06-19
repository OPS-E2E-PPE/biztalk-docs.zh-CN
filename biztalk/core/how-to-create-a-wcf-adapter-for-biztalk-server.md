---
title: 如何为 BizTalk Server 中创建的 WCF 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ddaeb72-d263-4291-bd79-485fc736e6e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebe1bbb9282db88f1b4370cea4b59ff4fcbfe6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249341"
---
# <a name="how-to-create-a-wcf-adapter-for-biztalk-server"></a>如何为 BizTalk Server 创建 WCF 适配器
有三个部分创建 BizTalk[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]适配器。  
  
-   创建[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]Web 服务使用 BizTalk[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务发布向导。 有关使用 BizTalk 信息[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务发布向导中，请参阅[发布 WCF 服务](../core/publishing-wcf-services.md)。  
  
-   使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收和发送位置及端口。 有关如何执行此操作的示例，请参阅[如何配置接收和发送位置并 BAM WCF 侦听的端口](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md)。  
  
-   如果您是以 IIS 承载解决方案，则必须使用 IIS Manager 配置 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web 服务。  
  
    -   您必须对应用程序池用户授予权限。 若要执行此操作，请参阅[IIS 模拟的安全注意事项](../core/security-considerations-for-iis-impersonation.md)。  
  
    -   您必须为应用程序设置目录安全性，如下面的过程所述。  
  
## <a name="setting-the-directory-security"></a>设置目录安全性  
 请确保 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的目录安全性访问控制允许匿名访问；这样可以简化应用程序访问。  
  
 例如，如果你的应用程序名称为 MyBizTalkService3 并且必须是在默认网站 MyBizTalkService3，你可以按照此过程设置的访问控制。  
  
#### <a name="to-set-the-access-control-in-windows-server-2008"></a>在 Windows Server 2008 中设置访问控制  
  
1.  单击**启动**，单击**所有程序**，展开**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在 Internet 信息服务 (IIS) 管理器窗口中，展开你的服务器名称，展开**站点**，展开**Internet Information Services**，然后展开**Default Web Site**.  
  
3.  右键单击**MyBizTalkService3**，然后单击**编辑权限**。  
  
4.  上**安全**选项卡**MyBizTalkService3 属性**对话框中，单击**编辑**。  
  
5.  在**权限 MyBizTalkService3**对话框中，单击**添加**。  
  
6.  在**选择用户、 计算机或组**对话框中，键入`anonymous logon`，然后单击**确定**。  
  
7.  选择**匿名登录**中**组或用户名**部分中，选择**读取 & 执行**中**匿名登录权限**部分，并依次**确定**。  
  
8.  单击**确定**关闭**MyBizTalkService3 属性**对话框。  
  
 要确认该服务配置正确，请右键单击该服务，然后单击**浏览**。  
  
 如果正确配置了该服务，您将看到一个类似于如下的屏幕。  
  
 ![BizTalkServiceInstance 服务屏幕](../core/media/ff0e4ba0-59e7-47d9-a252-2859179f5645.gif "ff0e4ba0-59e7-47d9-a252-2859179f5645")  
  
## <a name="see-also"></a>另请参阅  
 [配置 WCF 适配器以截获 BAM 数据](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)