---
title: 适配器接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7398aeb-7c1c-400e-a552-d0ab39e55a0b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bdb6f3e26d8862fd538f0279ecbb4c5c9b33af8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361405"
---
# <a name="adapter-interfaces"></a>适配器接口
有三个必须实现自定义适配器的接口和两个接口是可选的。  
  
## <a name="mandatory-interfaces"></a>必需接口  
 所有适配器必须都实现以下接口。  
  
### <a name="ibasecomponent"></a>IBaseComponent  
 此接口用于详细**名称**，**版本**，并**说明**的适配器。  
  
### <a name="ibttransport"></a>IBTTransport  
 此接口用于详细**传输类型**并**ClassID**的适配器。  
  
### <a name="ibtbatchcallback"></a>IBTBatchCallback  
 此接口是通过该适配器接收的状态和错误信息一批消息提交给消息引擎的回调接口。  
  
## <a name="optional-interfaces"></a>可选接口  
 适配器可能会或可能不会实现以下接口，具体取决于他们的需要。  
  
### <a name="ipersistpropertybag"></a>IPersistPropertyBag  
 这是通过哪个处理程序配置传送到适配器配置接口。 仅适用于具有处理程序配置信息的适配器需要此接口。  
  
### <a name="ibttransportcontrol"></a>IBTTransportControl  
 此接口用于初始化和终止适配器。 适配器的传输代理是通过此接口传递给它。 此接口不需要独立适配器。