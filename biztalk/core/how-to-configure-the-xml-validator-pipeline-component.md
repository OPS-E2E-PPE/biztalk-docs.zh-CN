---
title: 如何配置 XML 验证器管道组件 |Microsoft Docs
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
ms.openlocfilehash: 89c136079a6283fe5e2eebd063718f97008029fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340226"
---
# <a name="how-to-configure-the-xml-validator-pipeline-component"></a>如何配置 XML 验证器管道组件
XML 验证器管道组件可在任何阶段 （除了拆装或组装） 在发送或接收管道。  
  
### <a name="to-configure-the-properties-for-the-xml-validator-pipeline-component"></a>若要配置 XML 验证器管道组件的属性  
  
1.  将 XML 验证器管道组件拖至接收管道的验证阶段。  
  
2.  在属性窗口中**管道组件属性**部分中，进行以下设置。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**文档架构**|指示命名空间和类型名或多个架构应用于文档。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。 如果未指定架构，运行时架构发现将通过使用消息的目标命名空间和根元素名称信息。 **注意：** 如果指定两个或多个架构，可能会收到错误"两个或多个所选架构共享同一目标命名空间"**文档架构：** 属性。 <br /><br /> 默认值：空集合|  
    |可恢复交换处理|如果为"false"-，指示 （如果任何包含的消息失败，整个交换被挂起），作为一个单元验证整个交换。<br /><br /> 如果为"true"的指示，交换中的消息分别提取，验证程序使用的某些传播通过消息传送路径和其他人被挂起。<br /><br /> 可恢复交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。|  
  
## <a name="see-also"></a>请参阅  
 [XML 验证器管道组件](../core/xml-validator-pipeline-component.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)