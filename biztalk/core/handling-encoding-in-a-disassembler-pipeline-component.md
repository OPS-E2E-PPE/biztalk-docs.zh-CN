---
title: 处理拆装器管道组件中的编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], encoding
- pipeline components [custom], disassembling
ms.assetid: 33420357-421f-4ad0-8eee-d445376676db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 596161cd2ccf5d4f9a492bbdd23cd8f6f22c5c2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995230"
---
# <a name="handling-encoding-in-a-disassembler-pipeline-component"></a>处理拆装器管道组件中的编码
确保您的自定义拆装器组件采用如下格式之一对出站文档编码：  
  
- UTF-8  
  
- UTF-16  
  
- UTF-32  
  
- UTF-16LE  
  
- UTF-16BE  
  
  业务流程引擎可能无法处理采用其他编码格式的文档。  
  
  .NET Framework 不支持 UTF-32LE 和 UTF-32BE；若要使用这些格式，您必须创建自定义编码实现。  
  
## <a name="see-also"></a>请参阅  
 [开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md)