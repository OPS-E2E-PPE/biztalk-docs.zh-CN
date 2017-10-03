---
title: "如何备份的 BizTalk Server 配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14f89050-c204-4d44-a875-299e690489ef
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad54aba8f8f49adeb8534bdbe28add15f0fe9638
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-the-biztalk-server-configuration"></a>如何备份 BizTalk Server 配置
作为备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的一部分，应当备份与运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机相关联的配置设置。 如果具有原始配置文件的副本，则在计算机发生硬件故障需要更换计算机时，将会极大地简化还原过程。  
  
 运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的每台计算机的配置设置都存储在由 BizTalk Server 配置管理器创建的 XML 文件中。 每当更改 BizTalk Server 的配置时，都应当将更新的配置文件导出到备份位置。 这有助于确保在必须替换 BizTalk Server 时配置文件可用。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 BizTalk Server Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-back-up-the-biztalk-server-configuration"></a>备份 BizTalk Server 配置  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft BizTalk Server**，然后单击**BizTalk Server 配置**。  
  
2.  在**Microsoft BizTalk Server 配置**，单击**导出配置**。  
  
3.  在**另存为**对话框中，浏览到你在其中存储你的备份的位置。  
  
4.  在**文件名**框中，为配置文件中，键入一个名称，然后单击**保存**。  
  
## <a name="see-also"></a>另请参阅  
 [备份运行 BizTalk Server 的计算机](../core/backing-up-a-computer-running-biztalk-server.md)   
 [如何恢复 BizTalk Server 配置](../core/how-to-recover-the-biztalk-server-configuration.md)