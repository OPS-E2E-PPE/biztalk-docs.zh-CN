---
title: "手动配置到 Siebel 适配器的物理端口绑定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- physical port binding, manually configuring
- how to, manually configure adapters for sending messages to a Siebel system
ms.assetid: a1445b8a-440f-45e8-96e9-a13142ca87c6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed94ca9f6a44919684d36a1be931cbb33f746377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-siebel-adapter"></a>手动配置到 Siebel 适配器的物理端口绑定
本部分提供有关配置信息[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]为 WCF 自定义绑定使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在部署后适配器，你将能够发送和接收来自 Siebel 系统的消息，通过使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 部署该适配器的步骤有所不同具体取决于之间的通信的方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 你可以选择配置发送接收端口。 下表对这些选项进行了概括介绍：  
  
|端口方向|通信模式|可供选择的通信的方向|  
|---|---|---|  
|Send|单向|我将始终发送消息上此端口。|  
|发送-接收|请求-响应|我将发送请求并接收响应。|  
  
 有关详细信息，请参阅[创建和配置发送端口](../../core/creating-and-configuring-send-ports.md)。
  
> [!NOTE]
>  接收端口不支持，因为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不会启用从 Siebel 系统的入站的操作。  
  
> [!NOTE]
>  你还可以通过导入创建的绑定配置文件配置 WCF 自定义发送端口[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。 有关配置使用此绑定文件的端口的说明，请参阅[配置物理端口绑定使用的端口绑定文件，以便 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。
  
 
  
## <a name="see-also"></a>另请参阅  
[构建基块创建带有 Siebel 适配器 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)