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
ms.openlocfilehash: 27e7095c73cd337a1fb08f2d867e817ad5838206
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="msmqt-deprecation"></a>MSMQT 弃用
已从 BizTalk Server 中删除 MSMQT 功能。 业务流程的设计器中 MSMQT 传输选项仍可在设计时端口配置向导时选择下面的图中所示**现在指定**选项**端口绑定**.  
  
 **显示 MSMQT 传输的端口配置向导**  
  
 ![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")  
  
## <a name="biztalk-server-projects"></a>BizTalk Server 项目  
 新的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目不应使用 MSMQT 传输选项。 应用程序部署到[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]将失败并出现错误**协议类型"MSMQT"找不到**。  
  
## <a name="migrated-biztalk-server-projects"></a>迁移的 BizTalk Server 项目  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]能够将项目迁移到[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]转换向导中所述[迁移 BizTalk 服务器项目](../core/migrating-a-biztalk-server-project.md)。 对于包含配置为使用 MSMQT 传输的端口的项目，必须对其手动重新配置，然后才能部署到 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。 建议使用 MSMQ 适配器进行重新配置。  有关 MSMQ 适配器的详细信息请参阅[MSMQ 适配器是什么？](../core/what-is-the-msmq-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [从 MSMQT 适配器迁移到 MSMQ 适配器](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)