---
title: "平面文件汇编管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component]
ms.assetid: 3c851771-55b2-4d21-9291-d707dd66837c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385b1f8ea6c2ce707069cde522ea2f6712290be7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-assembler-pipeline-component"></a>平面文件汇编管道组件
平面文件组装器可以将单个文档组合到批中，并可以根据需要为批添加头部或尾部（或同时添加头部和尾部）。 有关平面文件的详细信息，请参阅[分隔记录的平面文件消息](../core/flat-file-messages-with-delimited-records.md)。 另请参阅[平面文件消息的位置记录](../core/flat-file-messages-with-positional-records.md)。  
  
 平面文件组装器管道组件不对传入 XML 消息进行验证。 若要确保执行 XML 验证，请在发送管道的预组装阶段包括 XML 验证器组件。  
  
 平面文件组装器管道组件仅支持 Microsoft .NET Framework 所支持的转换。 其他任何转换可以通过写入自定义文本编写器来完成。  
  
 有关配置平面文件汇编器管道组件的信息，请参阅[如何配置平面文件汇编管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)。  
  
> [!NOTE]
>  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你无法将消息组合为一个交换。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [平面文件汇编管道组件中的字符编码](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [平面文件汇编管道组件中的文档结构强制](../core/document-structure-enforcement-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [保留在平面文件汇编管道组件的分隔符](../core/retaining-delimiters-in-the-flat-file-assembler-pipeline-component.md)