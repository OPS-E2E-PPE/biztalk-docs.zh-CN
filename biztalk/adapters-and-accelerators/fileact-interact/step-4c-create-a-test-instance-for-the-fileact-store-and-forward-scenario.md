---
title: 步骤 4c:创建测试实例为 FileAct 存储和转发方案 |Microsoft Docs
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
ms.openlocfilehash: 8bf28aaae49d670933db8315ed3dd333a28462d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364789"
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario"></a>步骤 4c:创建为 FileAct 存储和转发方案测试实例
在开始此步骤之前，必须完成[步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)。  
  
### <a name="to-create-a-test-instance"></a>若要创建测试实例  
  
1.  在文本编辑器中，（如记事本） 打开一个新文件并粘贴以下：  
  
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
    >  您必须将 %physicalfoldername%FILEACT 中配置的实际文件夹名称替换为接收位置。  
  
2.  "PutReqSimple.xml"的名称保存该文件。  
  
3.  请确保文件 (Sample_put.txt) 位于客户端位置文件夹。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：测试 FileAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)   
 [步骤 4A:启动 SWIFTNet 服务为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)   
 [步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)   
 [步骤 4d:测试有效实例为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario.md)