---
title: 编译映射 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, compiling
- XSLT, generating
- maps, validating
- BizTalk Mapper, compiling
- BizTalk Mapper, validating
ms.assetid: 967181d6-22a9-4a76-ae45-3317c0c6321b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346769519343afe9456a7b1e7cf9a3bd5bb159ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231861"
---
# <a name="compiling-maps"></a>编译地图
在验证映射时，BizTalk 映射器的编译器组件将生成可扩展样式表语言转换 (XSLT) 样式表。 这将创建一个已编译的映射，该映射可将源架构定义的实例消息转换为目标架构定义的实例消息。 编译映射将执行在网格页中指定的结构规则和转换。  
  
 转换（例如链接）是按记录和字段在目标架构中的显示顺序进行处理的。 例如，在 BizTalk 映射程序到达目标**记录**或**字段**节点的链接，BizTalk 映射程序将编译的链接的属性。 该操作可能仅仅是从源架构的记录或字段中复制值，也可能包含使用 functoid 以及多个记录和字段进行的多个计算。  
  
 BizTalk 映射程序生成中的警告**输出**窗口和**任务列表**当编译器遇到的情况下，可能会生成错误的输出窗口。 例如，如果 functoid 需要一个输入的参数，但没有输入参数，BizTalk 映射程序生成中的某个警告**输出**窗口。 通常，如果生产环境中生成警告，则不应在其中使用映射。  
  
 生成的 XSLT 样式表的链接也将出现在**输出**窗口时正确编译该映射。  
  
 BizTalk Server 使用编译的映射来将输入实例消息转换为输出实例消息。  
  
## <a name="see-also"></a>另请参阅  
 [测试映射](../core/testing-maps.md)   
 [数据转换配置](../core/data-transformation-configuration.md)   
 [节点层次结构级别匹配](../core/node-hierarchy-level-matching.md)