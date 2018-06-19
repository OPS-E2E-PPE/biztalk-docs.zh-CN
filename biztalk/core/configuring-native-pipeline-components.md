---
title: 配置本机管道组件 |Microsoft 文档
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
ms.openlocfilehash: 94475334395f8c360bbb636cfa9cbadcf3bf4fe3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233173"
---
# <a name="configuring-native-pipeline-components"></a>配置本地管道组件
管道组件可以在设计时公开自己的自定义属性。 如果已实现相应属性的读取和写入存取方法，在组件中定义的任何公共属性都将呈现在管道设计器中。 管道设计器将根据组件属性的声明来显示这些属性；例如，如果属性声明为只读，在管道设计器中就会显示为只读。  
  
 必须实现自定义管道组件**IPersistPropertyBag**使这些自定义属性创建的接口。 使用创建属性**IPersistPropertyBag**接口可以在 Microsoft 的属性窗口中设置[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，就像本机管道组件的所有属性。 本部分将介绍配置所包括的各管道组件的过程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何配置本机管道组件](../core/how-to-configure-native-pipeline-components.md)  
  
-   [如何将 BizTalk Framework 汇编程序管道组件配置](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)  
  
-   [如何将 BizTalk Framework 反汇编程序管道组件配置](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)  
  
-   [BizTalk Framework 架构和属性](../core/biztalk-framework-schema-and-properties.md)  
  
-   [如何配置平面文件汇编管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)  
  
-   [如何配置平面文件反汇编程序管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)  
  
-   [如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)  
  
-   [如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)  
  
-   [MIME SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md)  
  
-   [如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
  
-   [如何将 XML 汇编程序管道组件配置](../core/how-to-configure-the-xml-assembler-pipeline-component.md)  
  
-   [如何将 XML 反汇编程序管道组件配置](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)  
  
-   [XML、 平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
-   [如何将 XML 验证程序管道组件配置](../core/how-to-configure-the-xml-validator-pipeline-component.md)