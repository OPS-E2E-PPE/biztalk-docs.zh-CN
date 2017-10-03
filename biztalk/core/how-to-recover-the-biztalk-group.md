---
title: "如何恢复 BizTalk 组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23cd2a6550263f707531101db743a6ecdef39e5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-the-biztalk-group"></a>如何恢复 BizTalk 组
必须在系统恢复过程中将 BizTalk Server 重新连接到现有的 BizTalk 组。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 Administrators 组成员的身份登录，才能执行此过程。  
  
 如果要恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 标准版，必须下载用于帮助恢复该服务器的脚本。 下载[RestoreConfig.vbe](http://go.microsoft.com/fwlink/?LinkID=195799)。  
  
### <a name="to-recover-the-biztalk-group-standard-edition"></a>恢复 BizTalk 组（标准版）  
  
1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符下，键入：  
  
     **RestoreConfig.vbe***\<SavedConfigXML >*   
  
     其中 *\<SavedConfigXML >*是完整路径和保存的配置文件的文件名。  
  
     上述操作应该在不显示任何错误的情况下退出。  
  
    > [!NOTE]
    >  若要恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位计算机上的 Standard Edition，你必须运行**RestoreConfig.vbe**从 32 位命令提示符，以便它能够更新 32 位注册表。 若要打开 32 位命令提示符，请单击**启动**，单击**运行**，类型**c:\windows\syswow64\cmd.exe**，然后单击**确定**。  
  
    > [!NOTE]
    >  失败的计算机名称包含在已保存的配置文件中。 要还原到的计算机的名称必须是相同的名称。 您必须在具有该名称的计算机上运行上述脚本。 但是，您可以在已保存配置文件中更改失败的计算机名称。 如果进行了此操作，您可以在具有不同名称的计算机上运行上述脚本。  
  
### <a name="to-recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a>恢复 BizTalk 组（开发人员版或企业版）  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。  
  
2.  在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，在控制台树中，单击**组**。  
  
3.  在详细信息窗格中，选择**加入现有的 BizTalk 组**，然后指定相应的远程 BizTalk 管理 (BizTalkMgmtDb) 数据库。  
  
4.  单击“应用配置”。  
  
5.  单击**文件**，然后单击**退出**。  
  
## <a name="see-also"></a>另请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)