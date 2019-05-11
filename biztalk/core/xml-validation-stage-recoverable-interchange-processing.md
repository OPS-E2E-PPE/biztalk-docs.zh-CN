---
title: XML 验证阶段 （可恢复的交换处理） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ed00971-d85b-4adb-86c4-c56de7ba7c67
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c2aad27b00012972214e2d86ad78a871bb609fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401559"
---
# <a name="xml-validation-stage-recoverable-interchange-processing"></a>XML 验证阶段 （可恢复的交换处理）
**XML 验证器**管道组件处理两种模式中的交换：  
  
-   **标准模式**。 当**XML 验证器**组件配置为执行标准验证，将交换中包含的消息进行验证的事务的工作单元。 具体而言，如果交换中的消息验证失败，整个交换 （包含所有消息） 被置于挂起队列。  
  
-   **可恢复模式**。 当**XML 验证器**配置组件来执行可恢复交换处理时，如果消息验证失败，消息被放置在挂起队列和**XML 验证器**组件将继续验证交换中的剩余消息。  
  
### <a name="to-configure-recoverable-interchange-processing"></a>若要配置可恢复交换处理  
  
1. 在 Visual Studio 中使用管道设计器打开接收管道。  
  
2. 拖动**XML 验证器**组件从**工具箱**到**Validate**接收管道阶段。  
  
3. 在属性窗口中设置的值**可恢复交换处理**属性设置为**True**如果你想**XML 验证器**组件进程的交换，在可恢复模式下，或将属性设置为**False**如果您希望该组件在标准模式下的交换进行处理。 此属性的默认值为 `False`。  
  
   **器**类在对象模型中，对应于**XML 验证器**管道组件，有一个名为的公共属性**RecoverableInterchangeProcessing**可用来以编程方式获取/设置模式。 请参阅文档[Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx)类的详细信息。  
  
   已成功验证的消息具有标识为在其相应父交换到达的接收端口配置的参与方根据其发送方。 如果从交换提取的任何消息的参与方解析失败，则认为参与方解析对于整个交换失败。  
  
## <a name="see-also"></a>请参阅  
 [如何配置 XML 验证器管道组件](../core/how-to-configure-the-xml-validator-pipeline-component.md)