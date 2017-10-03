---
title: "任务 5： 配置转换 Shape1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93a73fd2-0f34-4681-8aed-7d54d69c86d3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e76313ca87ad3138da83480b46a38a802d89ff15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="task-5-configure-the-transform-shape"></a>任务 5： 配置转换形状
使用以下过程可配置转换形状。  
  
### <a name="to-configure-the-transform-shape"></a>若要配置转换形状  
  
1.  将构造消息形状拖至 ReceiveBeginDocResponse 后。  
  
    -   **构造的消息：** EditLineMsg  
  
    -   **名称：** ConstructEditLineMessageWithData  
  
     在中间，选择中右击**插入形状**，然后选择**转换**。  
  
     ![](../core/media/jde-insert-shape-transform.gif "JDE_insert_shape_transform")  
  
     使用“转换”，将数据从正在发送的数据映射到发送的数据。  
  
     对于将发送具有所有可能值的文档（而不是 BeginDoc）的工作环境，允许您构造所有可能的消息 BeginDoc、EditLine 和 EndDoc。 然而，对于该示例，只有硬编码数据。  
  
2.  双击**Transform_1**以打开。  
  
    1.  选择源并单击在添加行**变量名称**和选择**BeginDocResponseMsg**。  
  
         ![](../core/media/jde-transform-source.gif "JDE_transform_source")  
  
    2.  选择**目标**在添加行单击**变量名称**，选择**EditLineMsg**，然后单击**确定**。  
  
         ![](../core/media/jde-transform-destination.gif "JDE_transform_destination")  
  
3.  在解决方案资源管理器中，双击**Transform_1.btm**若要打开的映射工具。 链接以下四项：  
  
    -   mnCMJobNo  
  
    -   szCMComputerID  
  
    -   mnProcessID  
  
    -   mnTransactionID  
  
     ![](../core/media/jde-example-transformmapping.gif "JDE_example_transformmapping")  
  
     为方便使用，该示例具有硬编码值。 单击目标架构中的项并设置以下值。  
  
     ![](../core/media/jde-hardcoded-mapping-example.gif "JDE_hardcoded_mapping_example")  
  
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
  
4.  将构造消息拖至 ReceiveEditLine 后。  
  
    -   **构造的消息：** EndDocMsg  
  
    -   **名称：** ConstructEndDocMessageWithData  
  
     右键单击在中间，选择**插入形状**，然后选择**转换**。  
  
5.  双击**Transform_2**以打开。  
  
    1.  选择**源**在添加行单击**变量名称**和选择**BeginDocResponseMsg**。  
  
    2.  选择**目标**在添加行单击**变量名称**，选择**EndDocMsg**，然后单击**确定**。  
  
6.  在解决方案资源管理器中，双击**Transform_2.btm**若要打开的映射工具。 链接以下四项：  
  
    -   mnCMJobNo  
  
    -   szCMComputerID  
  
    -   mnProcessID  
  
    -   mnTransactionID  
  
     为方便使用，该示例具有硬编码值。 单击目标架构中的项并设置以下值。  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ns0:F4211FSEndDoc xmlns:ns0="http://schemas.microsoft.com/  
        [JDE://CSALES/B4200310]">  
       <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
       <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
       <ns0:cCMUseWorkFiles>2</ns0:cCMUseWorkFiles>  
    </ns0:F4211FSEndDoc>  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [任务 1： 创建端口](../core/task-1-create-the-ports2.md)   
 [任务 2： 创建消息](../core/task-2-create-the-messages1.md)   
 [任务 3： 配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes1.md)   
 [任务 4： 配置构造消息形状](../core/task-4-configure-the-construct-message-shape2.md)