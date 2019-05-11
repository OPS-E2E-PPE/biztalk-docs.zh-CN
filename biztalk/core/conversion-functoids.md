---
title: 转换 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cd7abcf-f524-4e85-b8d5-d6123767490f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b042428f3a67227db6fb53966149458bc279926
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390250"
---
# <a name="conversion-functoids"></a>转换 Functoid

## <a name="overview"></a>概述
**转换**functoid 用于数字和其 ASCII 等效，之间进行转换和十进制数字转换为其八进制和十六进制的等效值。  
  
 转换 functoid 的所有采用一个输入的参数。  
  
> [!NOTE]
>  由于基础类型系统中的更改**转换**中此版本的 BizTalk 映射器 functoid 的计算产生比以前版本中生成略有不同的结果。 例如，在以前版本的 BizTalk 映射器输入值-20 到**十六进制**functoid 导致输出 0xffec。 在此版本中，同一输入的值-20 会导致输出 0xffffffec。  

## <a name="available-functoids"></a>可用的 functoid  
 **转换**functoid 包括： 

* ASCII 到字符
* 字符到 ASCII
* 十六进制
* 八进制

介绍了这些 functoid [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 

## <a name="see-also"></a>请参阅  
 [如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
