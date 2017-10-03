---
title: "步骤 4c: FileAct 实时方案为创建的测试实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80e0cb59-8b4f-4273-a7a4-db3446008061
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04952616f1b49eb30b4eb00462e4e5295ade0cfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-real-time-scenario"></a>步骤 4c: FileAct 实时方案为创建的测试实例
在开始此步骤之前，必须完成[步骤 4B: FileAct 实时方案中启动的发送端口和接收端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)。  
  
### <a name="to-create-a-test-instance"></a>若要创建的测试实例  
  
1.  在文本编辑器中，（如记事本） 打开新文件并粘贴以下：  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Sw-ExchangeFileRequest>  
    <Sw-FileRequest>  
    <Sw-FileOpRequest>  
    <Sw-PutFileRequest>  
    <Sw-PhysicalName>%PhysicalFolderName%\sample_put.txt</Sw-PhysicalName>  
    </Sw-PutFileRequest>  
    </Sw-FileOpRequest>  
    </Sw-FileRequest>  
    </Sw-ExchangeFileRequest>  
    ```  
  
2.  "PutReqSimple.xml"的名称保存该文件。  
  
3.  请确保该文件 (Sample_put.txt) 位于客户端位置文件夹中。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4： 测试 FileAct 实时的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [步骤 4A： 启动 FileAct 实时方案 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [步骤 4B： 开始发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)   
 [步骤 4d: FileAct 实时方案的测试的有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario.md)