---
title: TIBCO Rendezvous 适配器体系结构 |Microsoft Docs
description: 了解用于 TIBCO Rendezvous 的工作原理，包括传递消息，BizTalk Server 中的 BizTalk 适配器
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d368e27dd0652753d223fa15b7c82d8ddbbe8b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359014"
---
# <a name="architecture-of-the-tibco-rendezvous-adapter"></a>TIBCO Rendezvous 适配器的体系结构

## <a name="overview"></a>概述
用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器提供之间的双向连接[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 TIBCO Rendezvous。 此适配器使用 TIBCO Rendezvous API 和 BizTalk 适配器框架 API 来提供紧密集成。  
  
 TIBCO Rendezvous 是可用于企业应用程序集成 (EAI) 提供消息总线的软件产品。 TIBCO 提供消息传送 Api 在 C 中， C++、 Java、 Visual Basic 和 Microsoft.NET Framework，才能接收 Microsoft Office Excel 工作表和所选的其他应用程序上的数据馈送。  
  
## <a name="message-passing"></a>消息传递  
 消息传递的基本概念是相当简单：  
  
- 消息具有单个主题，其中用句点分隔的元素组成。 （尽管它最终可能其他守护程序广播），它是发送到单个的 Rendezvous 后台程序。  
  
- 侦听器宣布其感兴趣的后台程序 （使用基本的通配符工具） 的主题，并具有匹配主题的消息将传送到它，如果两个守护程序连接，或者它们实际上是同一个守护程序。 有关详细信息，请参阅中的消息[适用于 TIBCO Rendezvous 的 BizTalk 适配器中的消息](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)。  
  
  下图显示用于 TIBCO Rendezvous 的 BizTalk 适配器体系结构。  
  
  ![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")  
  
## <a name="see-also"></a>请参阅  
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)  