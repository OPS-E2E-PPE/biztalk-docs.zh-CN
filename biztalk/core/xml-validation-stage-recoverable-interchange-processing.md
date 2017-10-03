---
title: "XML 验证阶段 （可恢复的交换处理） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ed00971-d85b-4adb-86c4-c56de7ba7c67
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de8f0225e100053fe6dced8165b7fc800c5e4804
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xml-validation-stage-recoverable-interchange-processing"></a>XML 验证阶段（可恢复的交换处理)
**XML 验证器**管道组件处理以下两种模式的交换：  
  
-   **标准模式**。 当**XML 验证器**组件配置为执行标准的验证，将交换中包含的消息验证事务工作单元中。 特殊情况下，如果交换中的消息验证失败，则整个交换（包含所有消息）将会被放在挂起的队列中。  
  
-   **可恢复模式**。 当**XML 验证器**组件配置处理可恢复的交换，失败时要执行消息验证，该消息会放在挂起的队列和**XML 验证器**组件将继续验证交换中的剩余消息。  
  
### <a name="to-configure-recoverable-interchange-processing"></a>若要配置可恢复的交换处理  
  
1.  在 Visual Studio 中使用管道设计器打开接收管道。  
  
2.  拖动**XML 验证器**组件从**工具箱**到**验证**接收管道的阶段。  
  
3.  在属性窗口中，将的值设置**可恢复交换处理**属性**True**如果你想**XML 验证器**组件与过程的交换在恢复模式下，或将属性设置为**False**如果你想要处理在标准模式下的交换的组件。 此属性的默认值是`False`。  
  
 **XMLValidator**在对象模型中，对应于类**XML 验证器**管道组件，具有名为的公共属性**RecoverableInterchangeProcessing**，你可以使用用于以编程方式获取/设置模式。 请参阅文档[Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx)有关详细信息的类。  
  
 成功验证的消息会根据为用于接收父交换的接收端口配置的参与方，来识别其发送方。 如果参与方解析对从交换提取的任何消息都失败，则认为参与方解析对于整个交换失败。  
  
## <a name="see-also"></a>另请参阅  
 [如何将 XML 验证程序管道组件配置](../core/how-to-configure-the-xml-validator-pipeline-component.md)