---
title: 任务 5：配置转换形状 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e92874e-9021-4cf6-bab6-d4173308c469
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a41921914c2018da9e43442dfa94763fb4dc4f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299807"
---
# <a name="task-5-configure-the-transform-shape"></a>任务 5：配置转换形状
使用以下过程来配置转换形状。  
  
### <a name="to-configure-the-transform-shape"></a>若要配置转换形状  
  
1. 将构造消息形状拖至 ReceiveBeginDocResponse 后。  
  
   -   **构造的消息：** EditLineMsg  
  
   -   **名称：** ConstructEditLineMessageWithData  
  
   1. 在中间，选择右击**插入形状**，然后选择**转换**。  
  
       ![插入形状转换](../core/media/insert-shape-transform.gif "insert_shape_transform")  
  
   2. 使用转换，将数据从发送到发送的数据的数据的映射。  
  
      为你的工作环境将文档发送 （而不是 BeginDoc) 的所有值可能允许您构造所有可能的消息、 BeginDoc、 EditLine 和 EndDoc。 对于此示例中，但是，没有仅硬编码的数据。  
  
2. 双击以打开 Transform_1。  
  
   1.  选择源，然后单击下方的添加行**变量名**，然后选择**BeginDocResponseMsg**。  
  
        ![转换源](../core/media/transform-source.gif "transform_source")  
  
   2.  选择**目标**下方的添加行中单击**变量的名称**，选择**EditLineMsg**，然后单击**确定**。  
  
        ![转换目标](../core/media/transform-destination.gif "transform_destination")  
  
3. 在解决方案资源管理器，双击**Transform_1.btm**以打开映射工具。 链接以下四个项：  
  
   - mnCMJobNo  
  
   - szCMComputerID  
  
   - mnProcessID  
  
   - mnTransactionID  
  
     ![示例转换映射](../core/media/example-transformmapping.gif "example_transformmapping")  
  
     为了方便使用，此示例具有硬编码值。 单击目标架构中的项并设置以下值。  
  
     ![硬编码映射](../core/media/hardcoded-mapping-example.gif "hardcoded_mapping_example")  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:F4211FSEditLine xmlns:ns0="http://schemas.microsoft.com/  
         [JDE://CSALES/B4200310]">  
      <ns0:cCMLineAction>A</ns0:cCMLineAction>  
      <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
      <ns0:cCMWriteToWFFlag>2</ns0:cCMWriteToWFFlag>  
      <ns0:szItemNo>210</ns0:szItemNo>  
      <ns0:mnQtyOrdered>1</ns0:mnQtyOrdered>  
      <ns0:cSalesTaxableYN>N</ns0:cSalesTaxableYN>  
      <ns0:szTransactionUOM>EA</ns0:szTransactionUOM>  
      <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
      <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
   </ns0:F4211FSEditLine>  
   ```  
  
4. 将构造消息拖至 ReceiveEditLine 后。  
  
   -   **构造的消息：** EndDocMsg  
  
   -   **名称：** ConstructEndDocMessageWithData  
  
        右键单击中部，选择**插入形状**，然后选择**转换**。  
  
5. 双击以打开 Transform_2。  
  
   1.  选择**源**下方的添加行中单击**变量的名称**，然后选择**BeginDocResponseMsg**。  
  
   2.  选择**目标**下方的添加行中单击**变量的名称**，选择**EndDocMsg**，然后单击**确定**。  
  
6. 在解决方案资源管理器，双击**Transform_2.btm**以打开映射工具。 链接以下四个项：  
  
   - mnCMJobNo  
  
   - szCMComputerID  
  
   - mnProcessID  
  
   - mnTransactionID  
  
     为了方便使用，此示例具有硬编码值。 单击目标架构中的项并设置以下值。  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:F4211FSEndDoc xmlns:ns0="http://schemas.microsoft.com/  
       [JDE://CSALES/B4200310]">  
      <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
      <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
      <ns0:cCMUseWorkFiles>2</ns0:cCMUseWorkFiles>  
   </ns0:F4211FSEndDoc>  
   ```  
  
## <a name="see-also"></a>请参阅  
 [任务 1:创建端口](../core/task-1-create-the-ports1.md)   
 [任务 2:创建消息](../core/task-2-create-the-messages2.md)   
 [任务 3:配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes2.md)   
 [任务 4:配置构造消息形状](../core/task-4-configure-the-construct-message-shape1.md)