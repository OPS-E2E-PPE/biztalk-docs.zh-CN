---
title: 字符串 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d73be02-9c93-481f-81e4-39b60bcfa2df
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06bcb1d42a5e72a57765d17c18a48b6f4808d412
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278525"
---
# <a name="string-functoids"></a>“字符串”Functoid

## <a name="overview"></a>概述
**字符串**functoid 用于操作字符串转换为全部大写或全部为小写，字符串串联，确定的字符串长度，空白区域，如的标准方式，依次类推。  
  
 Functoid**所有字母都大写**，**小写**，**大小**，**字符串右侧 Trim**，和**字符串左侧 Trim**接受一个输入的参数。 Functoid**字符串查找**，**字符串左侧**，和**字符串右侧**接受两个输入参数。 **字符串提取**functoid 接受三个输入，而**字符串连接**functoid 接受介于 1 和 100 之间的输入的参数。  
  
 两个**字符串**functoid 指字符串中字符的数值位置：**字符串提取**和**字符串查找**。 这些 functoid 在 1 处而不是在 0 处开始计数字符位置。  
  
 这两个字符串修整 functoid**字符串左侧 Trim**和**字符串右侧 Trim**，删除所有空格字符 （空格、 制表符和等等） 从左侧或右侧 （因为在这种情况可能是） 指定的字符串。  

## <a name="available-functoids"></a>可用的 functoid 
 **字符串**functoid 均： 

* Lowercase
* Size
* 字符串连接
* 字符串提取
* 字符串查找
* 左侧字符串提取
* 字符串左侧空格裁剪
* 右侧字符串提取
* 字符串右侧空格裁剪
* 大写

更多详细信息这些 functoid [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>另请参阅  
-  [如何在向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **字符串 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]