---
title: MSMQT 弃用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 007d65ce-d2a2-4602-80c8-55b26617f397
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a54e775d9a7f683b11440f1d6ad0e43bdbecb43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263637"
---
# <a name="msmqt-deprecation"></a>MSMQT 弃用
已从 BizTalk Server 删除 MSMQT 功能。 在业务流程设计器中，MSMQT 传输选项仍可在设计时端口配置向导时选择下图中所示**立即指定**选项**端口绑定**.  
  
 **显示 MSMQT 传输的端口配置向导**  
  
 ![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")  
  
## <a name="biztalk-server-projects"></a>BizTalk Server 项目  
 新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目不应使用 MSMQT 传输选项。 应用程序部署到 BizTalk Server 将失败并出现错误**协议类型"MSMQT"找不到**。  
  
## <a name="migrated-biztalk-server-projects"></a>迁移的 BizTalk Server 项目  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目可以使用迁移到 BizTalk Server[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]转换向导中所述[迁移 BizTalk Server 项目](../core/migrating-a-biztalk-server-project.md)。 必须手动重新包含配置为使用 MSMQT 传输的端口的项目配置，然后才能部署到 BizTalk Server。 建议的重新配置是使用 MSMQ 适配器。  有关 MSMQ 适配器的详细信息请参阅[什么是 MSMQ 适配器？](../core/what-is-the-msmq-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [从 MSMQT 适配器迁移到 MSMQ 适配器](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)