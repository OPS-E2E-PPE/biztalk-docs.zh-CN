---
title: "MIME SMIME 属性架构和属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26dd25b9-7eb8-4354-9929-dc1985dd1d77
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 882b25733a46b8b7b973c992d465132df4c47b75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mime-smime-property-schema-and-properties"></a>MIME SMIME 属性架构和属性

## <a name="namespace-properties"></a>Namespace 属性
**Http://schemas.microsoft.com/BizTalk/2003/mime-properties**命名空间包含可用于设置 MIME/SMIME 编码器管道组件的消息和一部分上下文属性的属性。 MIME/SMIME 编码器使用这些属性在所创建的消息中生成合适的 MIME/SMIME 标头。 下表对 MIME/SMIME 属性进行了说明：  
  
|属性|范围|类型|Description|  
|--------------|-----------|----------|-----------------|  
|**FileName**|每个消息部分|xs:string|设置 MIME/SMIME 部分的文件名标头。|  
|**Id 为**|每个消息部分|xs:string|设置 MIME/SMIME 部分的内容 ID 标头。|  
|**ContentDescription**|每个消息部分|xs:string|设置 MIME/SMIME 部分的内容说明标头。|  
|**ContentTransferEncoding**|每个消息部分|xs:string|设置所生成的 MIME/SMIME 部分的内容传输编码标头。<br /><br /> 此值将覆盖**内容传输编码**在管道设计器中配置值。 对于多部分消息，可以对不同的 MIME/SMIME 部分使用不同的编码。|  
|**ContentLocation**|每个消息部分|xs:string|设置所生成的 MIME/SMIME 部分的内容位置标头。|  
|**IsMIMEEncoded**|每个消息部分|xs:boolean|指定消息是否有 MIME/SMIME 负载。 MIME 组件将写入此值，因此您不必设置它。|  
  
 MIME/SMIME 编码器还使用以下部分属性从**系统**命名空间。  
  
|属性|类型|Description|  
|--------------|----------|-----------------|  
|ContentType|xs:string|对应于所生成的 MIME/SMIME 部分的内容类型标头。|  
|FileName|xs:string|对应于文件名。|  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)   
 [如何配置 MIME SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)   
 [MIME （BizTalk Server 示例）](../core/mime-biztalk-server-sample.md)   
 **消息上下文属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]