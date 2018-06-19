---
title: 步骤 4c： 创建 FileAct 应用商店应用和正向方案的测试实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477abefa-63d0-4cf2-9e4f-67467195efa8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0149d93501473e039dca7f4f8c4dbe50e904098
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223733"
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario"></a>步骤 4c： 创建 FileAct 应用商店应用和正向方案的测试实例
在开始此步骤之前，必须完成[步骤 4B： 启动的发送端口和接收端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)。  
  
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
    >  你必须使用在 FILEACT 中配置的实际文件夹名称替换 %physicalfoldername%接收位置。  
  
2.  "PutReqSimple.xml"的名称保存该文件。  
  
3.  请确保该文件 (Sample_put.txt) 位于客户端位置文件夹中。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4： 测试 FileAct 存储区和转发的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)   
 [步骤 4A： 启动 SWIFTNet 服务 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)   
 [步骤 4B： 开始发送端口和接收端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)   
 [步骤 4d： 测试 FileAct 应用商店应用和正向方案的有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario.md)