---
title: "接收方接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7ab77d4-705a-4b39-8c33-a7532ae6484c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77b42530d721a6dcee52e082fe46deae9ae06405
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receiver-interfaces"></a>接收器接口
除了标准适配器接口，接收适配器需要实现**IBTTransportConfig**。 BizTalk 消息引擎在此接口上将接收位置配置传送给适配器。  
  
## <a name="request-response-adapters"></a>请求-响应适配器  
 在某些情况下，接收适配器可能还需要处理发送消息。 执行此操作的适配器通常称为双向适配器或请求-响应适配器。 若要能够发送消息，接收适配器需要实现**IBTTransmitter**。  
  
 下图显示由实现的接口接收适配器。  
  
> [!NOTE]
>  **IBTBatchTransmitter**请求-响应适配器不支持界面。  
  
 ![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")