---
title: "转换 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0cd7abcf-f524-4e85-b8d5-d6123767490f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 192db4b03f80674f2eb90be2255a8682454bde2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="conversion-functoids"></a>“转换”Functoid

## <a name="overview"></a>概述
**转换**functoid 用于数字和其 ASCII 等效项，之间进行转换和将 10 个基本数字转换为其以 8 为基数和基本 16 等效项。  
  
 所有“转换”functoid 都只有一个输入参数。  
  
> [!NOTE]
>  由于在基础类型系统中，更改**转换**在此版本的 BizTalk 映射程序 functoid 产生在早期版本生成的那些略有不同的结果。 例如，在以前版本的 BizTalk 映射器-20 的输入值到**十六进制**functoid 导致 0xFFEC 的输出。 而在此版本中，同样输入值 -20 则会导致输出 0xFFFFFFEC。  

## <a name="available-functoids"></a>可用的 functoid  
 **转换**functoid 均： 

* ASCII 到字符
* 字符到 ASCII
* Hexadecimal
* 八进制

描述了这些 functoid [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 

## <a name="see-also"></a>另请参阅  
 [如何在向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
