---
title: 步骤 4c:为 FileAct 实时方案创建测试实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80e0cb59-8b4f-4273-a7a4-db3446008061
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbdc7c46b23206876e59fe7ac74fdf241787abfe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364808"
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-real-time-scenario"></a>步骤 4c:为 FileAct 实时方案创建测试实例
在开始此步骤之前，必须完成[步骤 4B:启动发送端口和接收端口为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)。  
  
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
  
2.  "PutReqSimple.xml"的名称保存该文件。  
  
3.  请确保文件 (Sample_put.txt) 位于客户端位置文件夹。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：测试 FileAct 实时端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [步骤 4A:启动 SWIFTNet 服务为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [步骤 4B:启动发送端口和接收端口为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)   
 [步骤 4d:为 FileAct 实时方案测试有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario.md)