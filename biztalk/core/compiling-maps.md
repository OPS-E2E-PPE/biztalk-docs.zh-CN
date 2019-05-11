---
title: 编译映射 |Microsoft Docs
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
ms.openlocfilehash: 46b02fecc64ae238d19ccacb565519321ce960af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357866"
---
# <a name="compiling-maps"></a>编译映射
当验证映射时，BizTalk 映射器编译器组件将生成可扩展样式表语言转换 (XSLT) 样式表。 这将创建编译的映射，通过转换到目标架构所定义的实例消息的源架构定义的实例消息。 编译映射将执行的结构规则和转换的网格页中指定。  
  
 转换，如链接，在目标架构中的记录和字段出现的顺序处理。 例如，当 BizTalk 映射器到达目标时，才**记录**或**字段**节点的链接，BizTalk 映射器将编译链接的属性。 该操作可能是记录或字段在源架构中，从一个简单的复制值或操作可能会涉及多个计算使用 functoid 以及多个记录和字段。  
  
 BizTalk 映射器生成中的警告**输出**窗口和**任务列表**窗口，当编译器遇到可能生成不正确的输出的情况。 例如，如果 functoid 需要一个输入的参数，并且没有输入参数，则 BizTalk 映射器生成中的警告**输出**窗口。 一般情况下，不应使用生成警告的生产环境中的地图。  
  
 生成的 XSLT 样式表的链接也将出现在**输出**窗口时正确编译该映射。  
  
 BizTalk Server 使用编译的映射来执行的输入的实例消息到输出实例消息翻译。  
  
## <a name="see-also"></a>请参阅  
 [测试映射](../core/testing-maps.md)   
 [数据转换配置](../core/data-transformation-configuration.md)   
 [节点层次结构级匹配](../core/node-hierarchy-level-matching.md)