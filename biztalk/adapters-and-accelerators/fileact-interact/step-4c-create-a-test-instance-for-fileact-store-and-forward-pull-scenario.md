---
title: "步骤 4c： 创建 FileAct 应用商店应用和进 （请求） 方案的测试实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50fc72f0-ec00-46f9-b24b-fe8d5e5079ee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c991dd980df9e19f036b3872289f9d0d8aa82d6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-store-and-forward-pull-scenario"></a>步骤 4c： 创建 FileAct 应用商店应用和进 （请求） 方案的测试实例
在开始此步骤之前，必须完成[步骤 4B： 启动的发送端口和接收端口 FileAct 应用商店应用和向前 （请求） 方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)。  
  
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
  
    > [!NOTE]
    >  必须将*%physicalfoldername%*替换在 FILEACT 中配置的实际文件夹名称接收位置。  
  
2.  ExchangeReqSimple.xml 的名称保存该文件。  
  
3.  在文本编辑器中，（如记事本） 打开新文件并粘贴以下：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Sw-ExchangeSnFRequest>  
    <Sw-SnFRequest>  
    <Sw-SnFOpRequest>  
    <Sw-AcquireSnFRequest>  
    <SwInt-Queue Type the queue name, based on your provisioning with SWIFT </SwInt-Queue>  
    <Sw-SessionMode>Pull</Sw-SessionMode>  
    <Sw-ForceAcquire>TRUE</Sw-ForceAcquire>  
    <Sw-OrderBy>InterAct</Sw-OrderBy>  
    <Sw-RecoveryMode>TRUE</Sw-RecoveryMode>  
    </Sw-AcquireSnFRequest>  
    </Sw-SnFOpRequest>  
    </Sw-SnFRequest>  
    </Sw-ExchangeSnFRequest>  
  
    ```  
  
4.  使用名称 acquirequeue.xml 保存文件。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4A： 启动 FileAct 存储和转发 （请求） 方案的 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)   
 [步骤 4B： 开始发送端口和接收 FileAct 应用商店应用和进 （请求） 方案的端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [步骤 4d： 测试 FileAct 应用商店应用和进 （请求） 方案的有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-fileact-store-and-forward-pull-scenario.md)