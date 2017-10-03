---
title: "如何恢复 BizTalk Server 配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1d39e50-4296-49c7-bd1e-63b1325af168
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9935c2c565d78d0bc102d4aef86959c2a9066e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a>如何恢复 BizTalk Server 配置
作为恢复 BizTalk 服务器的一部分，你还必须导入安装 BizTalk Server 时所创建的配置文件。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-recover-the-biztalk-server-configuration"></a>若要恢复的 BizTalk Server 配置  
  
1.  使用记事本编辑您以前备份的 BizTalk Server 配置文件，并输入的 BizTalk Server 服务的所有用户帐户密码。  
  
2.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。  
  
3.  在**Microsoft BizTalk Server 配置**，单击**导入配置**。  
  
     验证有任何功能的前面显示任何失效图标。 如果有配置错误的任何功能，现在是时间来更正它们。  
  
4.  单击“应用配置”。  
  
     在所有的 BizTalk Server 配置功能，请关闭配置窗口。  
  
## <a name="see-also"></a>另请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)   
 [如何备份的 BizTalk Server 配置](../core/how-to-back-up-the-biztalk-server-configuration.md)