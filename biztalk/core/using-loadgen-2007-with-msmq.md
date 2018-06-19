---
title: 使用 MSMQ LoadGen 2007 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8f23a86-0e6d-478a-87a3-5b02338c9afb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55d67628b7863df3f2396cd9b45b55f42a488b8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287125"
---
# <a name="using-loadgen-2007-with-msmq"></a>将 LoadGen 2007 与 MSMQ 一起使用
使用负载生成工具 Loadgen，您可以模拟 BizTalk Server 系统过载时的情况。  
  
> [!NOTE]
>  LoadGen 2007 工具是可在下载[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841)。  
  
 支持将 LoadGen 与 MSMQ 一起使用，但在安装期间不自动注册 MSMQ COM 组件，因为计算机上可能未安装 MSMQ 运行时服务。  
  
 若要使用 MSMQ 和 LoadGen，请手动注册位于 bins 目录中的 MSMQTransmitter.dll 和 ComMsmqMonitor.dll 文件。  
  
```  
regsvr32 MSMQTransmitter.dll  
```  
  
 如果不注册 MSMQ COM 组件，则将收到以下运行时错误：  
  
```  
Cannot Load Transport DLL C:\Program Files\LoadGen\Bins\MSMQTransport.dll for Section MSMQRxQTxn   
Exception has been thrown by the target of an invocation.  
```  
  
## <a name="see-also"></a>另请参阅  
 [用于测量引擎 MST 测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)