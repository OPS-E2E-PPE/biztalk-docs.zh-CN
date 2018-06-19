---
title: 步骤 4d： 交互应用商店应用和正向方案中测试的有效实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa49df8-ccf6-455a-99ff-38879d2b7bf9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5d27b23195adffc5915d8cb2170dca9e975ec94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224277"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario"></a>步骤 4d： 交互应用商店应用和正向方案中测试的有效实例
在开始此步骤之前，必须完成[步骤 4c： 创建交互应用商店应用和转发方案的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试的有效实例  
  
1.  删除 c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF 将文件 ExchangeReqSimple.xml  
  
2.  验证在一段时间后，ExchangeReqSimple.xml 文件将从文件夹中消失。  
  
3.  浏览到 C:\SWIFTAdapterTutorial\Interact\HandleRequest。 验证该 Sw:HandleRequest 位于文件夹中。  
  
4.  在文本编辑器中，（如记事本） 打开 Sw:HandleRequest 消息，并验证的负载部分与文件 ExchangeReqSimple.xml 相同。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4： 测试的交互，存储和转发的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)   
 [步骤 4A： 启动 SWIFTNet 服务交互，应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [步骤 4B： 开始发送端口和交互应用商店应用和向前情况下接收端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)   
 [步骤 4c： 交互应用商店应用和向前情况下创建的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)