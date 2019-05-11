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
ms.openlocfilehash: aaa903b07d0f7661bcf9750b5c8bcd5762e438c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387560"
---
# <a name="handling-encoding-in-a-disassembler-pipeline-component"></a>处理拆装器管道组件中的编码
请确保你的自定义拆装器组件将采用以下格式之一的出站文档编码：  
  
- UTF-8  
  
- UTF-16  
  
- UTF-32  
  
- UTF-16LE  
  
- UTF 16BE  
  
  业务流程引擎可能无法处理采用其他编码格式的文档。  
  
  由.NET Framework 中; 不支持 UTF 32LE 和 UTF 32BE若要使用这些格式，必须创建自定义编码实现。  
  
## <a name="see-also"></a>请参阅  
 [开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md)