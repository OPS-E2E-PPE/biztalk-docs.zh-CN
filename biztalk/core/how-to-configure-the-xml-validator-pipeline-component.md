---
title: 如何将 XML 验证程序管道组件配置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Validator [pipeline component]
- send pipelines, validating
- pipeline components, XML Validator
- receive pipelines, validating
ms.assetid: 3b3becaf-703c-4399-a5ed-e7082e31e6e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 821ad6a1353c0aa29866fd36fe84a7ea6317690b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248381"
---
# <a name="how-to-configure-the-xml-validator-pipeline-component"></a>如何将 XML 验证程序管道组件配置
XML 验证器管道组件可以用于发送或接收管道的任何阶段（除了拆装或组装）。  
  
### <a name="to-configure-the-properties-for-the-xml-validator-pipeline-component"></a>配置 XML 验证器管道组件的属性  
  
1.  将 XML 验证器管道组件拖至接收管道的验证阶段。  
  
2.  在属性窗口中，在**管道组件属性**部分中，以下设置。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**文档架构**|指明要应用于文档的一个或多个架构的命名空间和类型名。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。 如果未指定架构，则将使用消息的目标命名空间和根元素名称信息来执行运行时架构发现。 **注意：** 如果你指定两个或多个架构，可能会收到"两个或多个所选架构共享相同的目标命名空间"的错误**文档架构**属性。 <br /><br /> 默认值：空集合|  
    |可恢复的交换处理|当"false"时-表示 （是否已挂起任何包含的消息失败，整个交换），作为一个单元验证整个交换。<br /><br /> 当"true"时-表示中交换, 的消息提取单独的验证程序的某些传播通过消息传递途径和其他挂起的可能性。<br /><br /> 可恢复的交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。|  
  
## <a name="see-also"></a>另请参阅  
 [XML 验证程序管道组件](../core/xml-validator-pipeline-component.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)