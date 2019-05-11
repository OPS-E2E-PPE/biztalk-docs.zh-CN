---
title: 接收器接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7ab77d4-705a-4b39-8c33-a7532ae6484c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540da1fac24c69bd352a5fd0db9f2831f62f920f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398082"
---
# <a name="receiver-interfaces"></a>接收器接口
除了标准适配器接口，接收适配器需要实现**IBTTransportConfig**。 这是在其 BizTalk 消息引擎将接收位置配置适配器的接口。  
  
## <a name="request-response-adapters"></a>请求-响应适配器  
 接收适配器可能还需要处理在某些情况下发送消息。 执行此操作通常称为双向，或请求-响应适配器。 若要能够发送消息，接收适配器需要实现**IBTTransmitter**。  
  
 下图显示了实现的接口接收适配器。  
  
> [!NOTE]
>  **IBTBatchTransmitter**请求-响应适配器不支持接口。  
  
 ![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")