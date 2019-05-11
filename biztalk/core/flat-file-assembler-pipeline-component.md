---
title: 平面文件组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component]
ms.assetid: 3c851771-55b2-4d21-9291-d707dd66837c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 666a6612be354b1c5cda9f1c4f40a3702cadfb78
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387921"
---
# <a name="flat-file-assembler-pipeline-component"></a>平面文件组装器管道组件
平面文件组装器将单个文档组合到一批，并根据需要向其添加一个标头或尾部 （或两者）。 有关平面文件的详细信息，请参阅[带有分隔记录的平面文件消息](../core/flat-file-messages-with-delimited-records.md)。 另请参阅[带有位置记录的平面文件消息](../core/flat-file-messages-with-positional-records.md)。  
  
 平面文件组装器管道组件不会验证传入的 XML 消息。 若要确保执行 XML 验证，发送管道的预组装阶段包括 XML 验证器组件。  
  
 平面文件组装器管道组件仅支持 Microsoft.NET Framework 支持的转换。 通过写入自定义文本编写器可以进行其他任何转换。  
  
 有关配置平面文件组装器管道组件的信息，请参阅[如何配置平面文件组装器管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)。  
  
> [!NOTE]
>  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，不能将消息组装为一个交换。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [平面文件汇编程序管道组件中的字符编码](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [平面文件汇编程序 管道组件中的文档结构强制规定](../core/document-structure-enforcement-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [保留平面文件汇编程序管道组件中的分隔符](../core/retaining-delimiters-in-the-flat-file-assembler-pipeline-component.md)