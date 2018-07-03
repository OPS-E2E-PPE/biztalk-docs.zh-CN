---
title: 如何为 BizTalk Server 创建 WCF 适配器 |Microsoft Docs
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
ms.openlocfilehash: b07c838f9c53f7416ee0fea0e4efe71c49f60404
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989790"
---
# <a name="how-to-create-a-wcf-adapter-for-biztalk-server"></a>如何为 BizTalk Server 创建 WCF 适配器
有三个部分创建 BizTalk[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]适配器。  
  
- 创建[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]使用 BizTalk Web 服务[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务发布向导。 了解如何使用 BizTalk[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务发布向导，请参阅[发布 WCF 服务](../core/publishing-wcf-services.md)。  
  
- 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收和发送位置及端口。 有关如何执行此操作的示例，请参阅[如何配置接收和发送位置及用于 BAM WCF 侦听的端口](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md)。  
  
- 如果您是以 IIS 承载解决方案，则必须使用 IIS Manager 配置 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web 服务。  
  
  -   您必须对应用程序池用户授予权限。 若要执行此操作，请参阅[IIS 模拟的安全注意事项](../core/security-considerations-for-iis-impersonation.md)。  
  
  -   您必须为应用程序设置目录安全性，如下面的过程所述。  
  
## <a name="setting-the-directory-security"></a>设置目录安全性  
 请确保 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的目录安全性访问控制允许匿名访问；这样可以简化应用程序访问。  
  
 例如，如果你的应用程序名为 MyBizTalkService3 且具有 MyBizTalkService3 是在默认网站，您应按照以下过程来设置访问控制。  
  
#### <a name="to-set-the-access-control-in-windows-server-2008"></a>在 Windows Server 2008 中设置访问控制  
  
1. 单击**启动**，单击**所有程序**，展开**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2. 在 Internet 信息服务 (IIS) 管理器窗口中，展开服务器名称，展开**站点**，展开**Internet Information Services**，然后展开**Default Web Site**.  
  
3. 右键单击**MyBizTalkService3**，然后单击**编辑权限**。  
  
4. 上**安全**选项卡**MyBizTalkService3 属性**对话框中，单击**编辑**。  
  
5. 在中**MyBizTalkService3 的权限**对话框中，单击**添加**。  
  
6. 在中**选择用户、 计算机或组**对话框中，键入`anonymous logon`，然后单击**确定**。  
  
7. 选择**ANONYMOUS LOGON**中**组或用户名**部分中，选择**读取 & 执行**中**ANONYMOUS logon 权限**部分，并单击**确定**。  
  
8. 单击**确定**以关闭**MyBizTalkService3 属性**对话框。  
  
   若要确认正确配置该服务，右键单击该服务，然后依次**浏览**。  
  
   如果正确配置了该服务，您将看到一个类似于如下的屏幕。  
  
   ![BizTalkServiceInstance 服务屏幕](../core/media/ff0e4ba0-59e7-47d9-a252-2859179f5645.gif "ff0e4ba0-59e7-47d9-a252-2859179f5645")  
  
## <a name="see-also"></a>请参阅  
 [配置 WCF 适配器以侦听 BAM 数据](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)