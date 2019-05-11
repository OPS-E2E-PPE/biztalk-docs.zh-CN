---
title: MIME-SMIME 属性架构和属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26dd25b9-7eb8-4354-9929-dc1985dd1d77
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7631422189de4ab2e92d3a54d34032e949e8e84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394456"
---
# <a name="mime-smime-property-schema-and-properties"></a>MIME-SMIME 属性架构和属性

## <a name="namespace-properties"></a>Namespace 属性
**http://schemas.microsoft.com/BizTalk/2003/mime-properties**命名空间包含可用于设置 MIME/SMIME 编码器管道组件的消息和部分上下文属性的属性。 MIME/SMIME 编码器使用这些属性创建的消息中生成适当的 MIME/SMIME 标头。 下表介绍的 MIME/SMIME 属性。  
  
|属性|范围|类型|Description|  
|--------------|-----------|----------|-----------------|  
|**FileName**|每个消息部分|xs:string|设置 MIME/SMIME 部分的文件名称标头。|  
|**ContentID**|每个消息部分|xs:string|设置 MIME/SMIME 部分的 CONTENT-ID 标头。|  
|**ContentDescription**|每个消息部分|xs:string|设置 MIME/SMIME 部分的内容说明标头。|  
|**ContentTransferEncoding**|每个消息部分|xs:string|设置生成的 MIME/SMIME 部分的内容传输编码标头。<br /><br /> 此值将覆盖**内容传输编码**在管道设计器中配置的值。 对于多部分消息，可以为不同的 MIME/SMIME 部分使用不同的编码。|  
|**ContentLocation**|每个消息部分|xs:string|设置生成的 MIME/SMIME 部分的内容位置标头。|  
|**IsMIMEEncoded**|每个消息部分|xs:boolean|指定消息是否有 MIME/SMIME 负载。 MIME 组件写入此值，因此不需要将其设置。|  
  
 MIME/SMIME 编码器还使用以下部分属性**系统**命名空间。  
  
|属性|类型|Description|  
|--------------|----------|-----------------|  
|ContentType|xs:string|对应于生成的 MIME/SMIME 部分的内容类型标头。|  
|FileName|xs:string|对应于文件名称。|  
  
## <a name="see-also"></a>请参阅  
 [如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)   
 [如何配置 MIME-SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [MIME （BizTalk Server 示例）](../core/mime-biztalk-server-sample.md)   
 **消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]