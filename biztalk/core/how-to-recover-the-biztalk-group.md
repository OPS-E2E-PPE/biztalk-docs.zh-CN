---
title: 恢复 BizTalk 组 |Microsoft Docs
ms.custom: ''
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e96e647358a0fd0601933dc0b1744537d63ae630
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023587"
---
# <a name="how-to-recover-the-biztalk-group"></a>如何恢复 BizTalk 组
必须在系统恢复过程中将 BizTalk Server 重新连接到现有的 BizTalk 组。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 Administrators 组成员的身份登录，才能执行此过程。  
  
 如果要恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 标准版，必须下载用于帮助恢复该服务器的脚本。 下载[RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462)。  
  
## <a name="recover-the-biztalk-group-standard-edition"></a>恢复 BizTalk 组 （标准版）  
  
1. 单击**启动**，类型**cmd**，然后选择**命令提示符下**。  
  
2. 在命令提示符下，键入：  
  
    **RestoreConfig.vbe**  *\<SavedConfigXML\>*  
  
    其中*\<SavedConfigXML\>* 是完整路径和保存的配置文件的文件名。  
  
    上述操作应该在不显示任何错误的情况下退出。  
  
   > [!NOTE]
   >  若要恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位计算机上的 Standard Edition，您必须运行**RestoreConfig.vbe**从 32 位命令提示符，以便它能够更新 32 位注册表。 若要打开 32 位命令提示符下，单击**启动**，单击**运行**，类型**c:\windows\syswow64\cmd.exe**，然后单击**确定**。  
   > 
   > [!NOTE]
   >  失败的计算机名称包含在已保存的配置文件中。 要还原到的计算机的名称必须是相同的名称。 您必须在具有该名称的计算机上运行上述脚本。 但是，您可以在已保存配置文件中更改失败的计算机名称。 如果进行了此操作，您可以在具有不同名称的计算机上运行上述脚本。  
  
## <a name="recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a>恢复 BizTalk 组 （开发人员版或企业版）  
  
1.  打开**BizTalk Server 配置**（开始菜单）。
  
2.  在 BizTalk Server 管理中选择**组**。  
  
3.  在细节窗格中，选择**加入现有 BizTalk 组**，然后输入远程 BizTalk 管理 (BizTalkMgmtDb) 数据库。  
  
4.  选择**应用配置**。  
  
5.  选择**文件**，然后选择**退出**。  
  
## <a name="see-also"></a>请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)
