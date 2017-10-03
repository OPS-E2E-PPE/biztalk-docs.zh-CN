---
title: "适配器接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7398aeb-7c1c-400e-a552-d0ab39e55a0b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717adcf5d4a706a7cc072b42b224ab0f9f8cc6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-interfaces"></a>适配器接口
有三个自定义适配器必须实现的接口，另外还有两个可选接口。  
  
## <a name="mandatory-interfaces"></a>必需接口  
 所有适配器必须实现以下接口。  
  
### <a name="ibasecomponent"></a>IBaseComponent  
 此接口的详细信息**名称**，**版本**，和**说明**的适配器。  
  
### <a name="ibttransport"></a>IBTTransport  
 此接口的详细信息**传输类型**和**ClassID**的适配器。  
  
### <a name="ibtbatchcallback"></a>IBTBatchCallback  
 此接口为回调接口，适配器通过此接口接收其提交给消息引擎的某批消息的状态和错误信息。  
  
## <a name="optional-interfaces"></a>可选接口  
 适配器可以根据其需要实现或不实现以下接口：  
  
### <a name="ipersistpropertybag"></a>IPersistPropertyBag  
 这是一个配置接口，处理程序配置通过此接口传送给适配器。 只有具有处理程序配置信息的适配器才需要此接口。  
  
### <a name="ibttransportcontrol"></a>IBTTransportControl  
 此接口用于初始化和终止适配器。 适配器的传输代理是通过此接口传递给适配器的。 独立适配器不需要此接口。