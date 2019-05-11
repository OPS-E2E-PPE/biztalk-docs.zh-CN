---
title: 将 LoadGen 2007 与 MSMQ 使用 |Microsoft Docs
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
ms.openlocfilehash: ec8f56e431a54599711f59a25542213813f9c698
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396843"
---
# <a name="using-loadgen-2007-with-msmq"></a>将 LoadGen 2007 与 MSMQ 使用
负载生成工具 Loadgen，使您可以模拟 BizTalk Server 系统上。  
  
> [!NOTE]
>  LoadGen 2007 工具是可在下载[ http://go.microsoft.com/fwlink/?LinkId=59841 ](http://go.microsoft.com/fwlink/?LinkId=59841)。  
  
 将 LoadGen 与 MSMQ 支持，但我们做不自动注册 MSMQ COM 组件在安装过程中由于您的计算机上未安装 MSMQ 运行时服务。  
  
 若要使用 MSMQ 和 LoadGen，手动注册位于 bins 目录中的 MSMQTransmitter.dll 和 ComMsmqMonitor.dll 文件：  
  
```  
regsvr32 MSMQTransmitter.dll  
```  
  
 如果不注册 MSMQ COM 组件，您将收到以下运行时错误：  
  
```  
Cannot Load Transport DLL C:\Program Files\LoadGen\Bins\MSMQTransport.dll for Section MSMQRxQTxn   
Exception has been thrown by the target of an invocation.  
```  
  
## <a name="see-also"></a>请参阅  
 [测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)