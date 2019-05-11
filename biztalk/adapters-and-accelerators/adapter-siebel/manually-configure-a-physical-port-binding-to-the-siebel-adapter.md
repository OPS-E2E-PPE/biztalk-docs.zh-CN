---
title: 手动配置到 Siebel 适配器的物理端口绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- physical port binding, manually configuring
- how to, manually configure adapters for sending messages to a Siebel system
ms.assetid: a1445b8a-440f-45e8-96e9-a13142ca87c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 576188121d5dd33541440c8bb34d7b59fc97fb47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371466"
---
# <a name="manually-configure-a-physical-port-binding-to-the-siebel-adapter"></a>手动配置到 Siebel 适配器的物理端口绑定
本部分提供有关配置信息[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]为使用自定义 WCF 绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在部署后，适配器，您将能够发送和接收消息从 Siebel 系统使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 部署该适配器的步骤而异的之间的通信方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 您可以选择配置发送端口或发送接收端口。 下表总结了你的选择：  
  
|端口方向|通信模式|可供选择的通信方向|  
|---|---|---|  
|Send|单向|我将始终在发送消息此端口上。|  
|发送接收|请求-响应|我将发送请求并接收响应。|  
  
 有关详细信息，请参阅[创建和配置发送端口](../../core/creating-and-configuring-send-ports.md)。
  
> [!NOTE]
>  接收端口不支持，因为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不会启用从 Siebel 系统的入站的操作。  
> 
> [!NOTE]
>  此外可以通过导入创建的绑定配置文件配置 Wcf-custom 发送端口[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。 有关使用此绑定文件配置端口的说明，请参阅[配置物理端口绑定使用的端口绑定文件到 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。
  
 
  
## <a name="see-also"></a>请参阅  
[若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)