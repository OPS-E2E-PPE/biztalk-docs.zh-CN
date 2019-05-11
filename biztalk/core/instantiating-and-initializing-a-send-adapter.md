---
title: 实例化和初始化发送适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f10e6507-3351-4173-95f5-48546ca5f5c4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3808af04a8b2bcf6f866629f254212d5b10b8d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382072"
---
# <a name="instantiating-and-initializing-a-send-adapter"></a>实例化和初始化发送适配器
默认情况下，发送适配器不会实例化，直到第一条消息传递到它们，该过程称为"懒创建。 默认的懒创建方法有助于节省系统资源。 创建发送适配器后，它将被缓存，位于直到 BizTalk Server 服务已停止。  
  
 **InitTransmitterOnServiceStart**的成员**功能**枚举指示消息引擎在服务启动，而不是使用默认延迟创建，创建发送适配器如果这所需。  
  
 发送一条消息是与接收消息的消息批处理方面不同的模型。 对于接收适配器的传入消息将从消息引擎获取一批中插入。 在发送的情况下，消息引擎从适配器获得批并将消息发送到传输的适配器。 同时使用传输代理来获取消息批对象。  
  
## <a name="how-a-send-adapter-is-initialized"></a>如何初始化发送适配器  
 若要启用配置和绑定到传输代理，适配器必须实现以下配置接口：  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
  以下步骤介绍在初始化发送适配器所涉及的事件序列：  
  
1. 当消息引擎初始化发送适配器时，它首先会执行**QueryInterface**有关**IPersistPropertyBag**，这是一个可选接口。 如果适配器实现了接口，处理程序配置传递给适配器**负载**方法调用。 适配器使用此信息以确保配置正确。  
  
2. 消息引擎执行**QueryInterface**有关**IBTTransportControl**，这是必需的接口。  
  
3. 引擎将调用**IBTTransportControl.Initialize**、 传入适配器的传输代理。  
  
4. 消息引擎执行**QueryInterface**有关**IBTTransmitter**。  
  
    如果消息引擎找到该接口，适配器将被视为不支持批的发送器。  
  
    如果消息引擎不会发现此接口，消息引擎将执行**QueryInterface**有关**IBTBatchTransmitter**，发现其中表示适配器是可识别批发送器。  
  
    如果消息引擎发现任一这些接口，产生的错误条件，从而导致初始化失败。 初始化失败，则如果未发现任何必需接口。  
  
   下图说明了这一序列的 API 调用异步方法。蓝色的接口由适配器实现。  
  
   ![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")  
  
   一旦初始化和配置，适配器可以发送消息。  
  
   下图显示了在初始化发送适配器所涉及的对象交互。  
  
   ![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")  
   用于初始化发送适配器的工作流  
  
> [!NOTE]
>  适配器不应阻止消息引擎在调用如**IBTTransportControl.Initialize**并**ipersistpropertybag.load 这样**。 执行过多的处理中这些调用会影响服务启动时间。