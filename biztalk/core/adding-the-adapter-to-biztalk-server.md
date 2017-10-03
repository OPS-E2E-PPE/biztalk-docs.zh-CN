---
title: "将适配器添加到 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards OneWorld adapters], installing
- installing, JD Edwards OneWorld adapters
- JD Edwards OneWorld adapters, installing
ms.assetid: e2018856-1943-48e9-b43f-7d527880e4bd
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63de8824112c9891c6d67eee424a84dd4968976c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-the-adapter-to-biztalk-server"></a>将适配器添加到 BizTalk Server
适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器包含“接收处理程序”文件夹和“发送处理程序”文件夹。 “发送处理程序”文件夹包含 BizTalkServerApplication。 适用于 JD Edwards OneWorld 的 BizTalk 适配器是可以创建的，它在与 BizTalk 服务器相关的进程中运行，而不在隔离的主机进程中运行。  
  
 您可以使用以下过程将适配器添加到 BizTalk Server。  
  
### <a name="to-add-biztalk-adapter-for-jd-edwards-oneworld"></a>要添加适用于 JD Edwards OneWorld 的 BizTalk 适配器，请执行以下操作：  
  
1.  上**启动**菜单上，指向**Program Files**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**平台设置**。  
  
3.  右键单击**适配器**，指向**新建**，然后单击**适配器**。  
  
4.  在**适配器属性**对话框中，键入的适配器名称。 例如，JDEdwards。  
  
5.  选择**JDEOneWorld**从**适配器**列表，，然后单击**确定**。  
  
## <a name="verifying-the-adapter"></a>验证适配器  
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你可以验证适配器是否正确运作，可以通过查看**逻辑系统**窗口。 在初始安装时，该窗口为空，因为您还没有建立到服务器系统的连接，也没有建立任何逻辑系统。  
  
#### <a name="to-verify-that-the-adapter-is-running-correctly"></a>若要验证该适配器正确运行，请执行以下操作：  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开**平台设置**，展开**适配器**，然后选择**JDEOneWorld**。  
  
2.  在细节窗格中，右键单击**BizTalkServerApplication**，然后选择**属性**。  
  
3.  单击 **“属性”** 选项卡。  
  
4.  设置 SQL 连接参数。  
  
    -   **定义 SQL 数据库参数-**的 SQL Server 名称和数据库是那些在安装设置。 在这个文本区域，您可以重新定义适用于该适配器的服务器和数据库。  
  
5.  单击**关闭**退出**逻辑系统**窗口。  
  
     下一步是使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 添加逻辑系统。  
  
## <a name="see-also"></a>另请参阅  
 [规划和体系结构](../core/planning-and-architecture17.md)   
 [用于博士 Edwards OneWorld 的 BizTalk Adapter 中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [为博士 Edwards OneWorld 添加 BizTalk 适配器](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)