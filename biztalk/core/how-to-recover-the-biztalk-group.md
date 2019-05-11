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
ms.openlocfilehash: 2e637b974fc49fcfa3b1b6c27452ccc7d036359f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384423"
---
# <a name="how-to-recover-the-biztalk-group"></a>如何恢复 BizTalk 组
必须重新加入到现有 BizTalk 组作为系统恢复过程的一部分在 BizTalk Server。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要执行此过程的管理员组的成员身份登录。  
  
 如果要恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Standard Edition 中，你必须下载一个有助于恢复服务器脚本。 下载[RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462)。  
  
## <a name="recover-the-biztalk-group-standard-edition"></a>恢复 BizTalk 组 （标准版）  
  
1. 单击**启动**，类型**cmd**，然后选择**命令提示符下**。  
  
2. 在命令提示符下，键入：  
  
    **RestoreConfig.vbe**  *\<SavedConfigXML\>*  
  
    其中*\<SavedConfigXML\>* 是完整路径和保存的配置文件的文件名。  
  
    上述应退出而不显示任何错误。  
  
   > [!NOTE]
   >  若要恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位计算机上的 Standard Edition，您必须运行**RestoreConfig.vbe**从 32 位命令提示符，以便它能够更新 32 位注册表。 若要打开 32 位命令提示符下，单击**启动**，单击**运行**，类型**c:\windows\syswow64\cmd.exe**，然后单击**确定**。  
   > 
   > [!NOTE]
   >  已保存的配置文件中包含失败的计算机的名称。 要还原到的计算机的名称必须具有该名称。 您必须具有该名称的计算机上运行上述脚本。 但是，可以更改已保存的配置文件中失败的计算机的名称。 如果这样做，您可以运行上述脚本的计算机上使用不同的名称。  
  
## <a name="recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a>恢复 BizTalk 组 （开发人员版或企业版）  
  
1.  打开**BizTalk Server 配置**（开始菜单）。
  
2.  在 BizTalk Server 管理中选择**组**。  
  
3.  在细节窗格中，选择**加入现有 BizTalk 组**，然后输入远程 BizTalk 管理 (BizTalkMgmtDb) 数据库。  
  
4.  选择**应用配置**。  
  
5.  选择**文件**，然后选择**退出**。  
  
## <a name="see-also"></a>请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)
