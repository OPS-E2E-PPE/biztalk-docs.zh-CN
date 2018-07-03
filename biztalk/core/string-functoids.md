---
title: 字符串 Functoid |Microsoft Docs
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
ms.openlocfilehash: 72e2651c38d3cc69e5c6d7c7d80c6e0d29136033
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966598"
---
# <a name="string-functoids"></a>“字符串”Functoid

## <a name="overview"></a>概述
**字符串**functoid 用于以标准方式转换为全部大写或全部小写、 字符串连接、 确定字符串长度、 空白裁剪等操作字符串和其他操作。  

 这些 functoid**所有字母都大写**，**小写**，**大小**，**字符串右侧空格裁剪**，并**字符串左侧空格裁剪**只接受一个输入的参数。 这些 functoid**字符串查找**，**左侧字符串提取**，并**右侧字符串提取**接受两个输入参数。 **字符串中提取**functoid 接受三个输入，而**字符串连接**functoid 接受 1 到 100 之间的输入的参数。  

 两个**字符串**functoid 引用字符串中字符的数字位置：**字符串提取**并**字符串查找**。 这些 functoid 在 1 处而不是在 0 处开始计数字符位置。  

 这两个字符串裁剪 functoid**字符串左侧空格裁剪**并**字符串右侧空格裁剪**，删除所有空白字符 （空格、 制表符等） 从左侧或右侧 （如可能是这种情况） 的指定字符串。  

## <a name="available-functoids"></a>可用的 functoid 
 **字符串**functoid 包括： 

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

这些 functoid 的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="see-also"></a>请参阅  
- [如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
- **字符串 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
