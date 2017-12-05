---
title: "MSMQT 弃用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 007d65ce-d2a2-4602-80c8-55b26617f397
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f869dde7cb4c793e1e36beee6a20bc89d19272e8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="msmqt-deprecation"></a>MSMQT 弃用
已从 BizTalk Server 中删除 MSMQT 功能。 业务流程的设计器中 MSMQT 传输选项仍可在设计时端口配置向导时选择下面的图中所示**现在指定**选项**端口绑定**.  
  
 **显示 MSMQT 传输的端口配置向导**  
  
 ![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")  
  
## <a name="biztalk-server-projects"></a>BizTalk Server 项目  
 新的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目不应使用 MSMQT 传输选项。 向 BizTalk 服务器应用程序部署将失败并出现错误**协议类型"MSMQT"找不到**。  
  
## <a name="migrated-biztalk-server-projects"></a>迁移的 BizTalk Server 项目  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目可以通过使用迁移到 BizTalk Server[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]转换向导中所述[迁移 BizTalk 服务器项目](../core/migrating-a-biztalk-server-project.md)。 必须手动重新项目包含配置为使用 MSMQT 传输的端口配置之前部署到 BizTalk Server。 建议使用 MSMQ 适配器进行重新配置。  有关 MSMQ 适配器的详细信息请参阅[MSMQ 适配器是什么？](../core/what-is-the-msmq-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [从 MSMQT 适配器迁移到 MSMQ 适配器](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)