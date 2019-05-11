---
title: 配置本地管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, pipeline components
- pipeline components, configuring
- Pipeline Designer, code sample
- IPersistPropertyBag interface
ms.assetid: a3332a60-8cd6-43fa-9ecf-e1e54e71fef7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9d60c963231f61684cc58187d40bc23141ff1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355298"
---
# <a name="configuring-native-pipeline-components"></a>配置本地管道组件
管道组件可以在设计时公开自己的自定义属性。 在组件中定义的任何公共属性将呈现在管道设计器中的读取和写入存取方法，实现属性。 管道设计器将显示其声明; 根据组件属性例如，如果属性声明为只读的它将显示这种情况下在管道设计器中。  
  
 自定义管道组件必须实现**IPersistPropertyBag**接口，以使这些自定义属性创建。 使用创建的属性**IPersistPropertyBag**接口可以在 Microsoft 的属性窗口中设置[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，就像本地管道组件的所有属性。 本部分包含配置的每个包含的管道组件的过程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何配置本地管道组件](../core/how-to-configure-native-pipeline-components.md)  
  
-   [如何配置 BizTalk 框架组装器管道组件](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)  
  
-   [如何配置 BizTalk 框架拆装器管道组件](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)  
  
-   [BizTalk 框架架构和属性](../core/biztalk-framework-schema-and-properties.md)  
  
-   [如何配置平面文件组装器管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)  
  
-   [如何配置平面文件拆装器管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)  
  
-   [如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)  
  
-   [如何配置 MIME-SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)  
  
-   [MIME-SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md)  
  
-   [如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
  
-   [如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)  
  
-   [如何配置 XML 拆装器管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 和平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
-   [如何配置 XML 验证器管道组件](../core/how-to-configure-the-xml-validator-pipeline-component.md)