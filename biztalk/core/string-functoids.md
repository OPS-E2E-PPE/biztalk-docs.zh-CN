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
ms.openlocfilehash: f2da7881495d2c685faaba6f9c9cf00eb565a7af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244153"
---
# <a name="string-functoids"></a>字符串 Functoid

## <a name="overview"></a>概述
**字符串**functoid 用于以标准方式转换为全部大写或全部小写、 字符串连接、 确定字符串长度、 空白裁剪等操作字符串和其他操作。  

 这些 functoid**所有字母都大写**，**小写**，**大小**，**字符串右侧空格裁剪**，并**字符串左侧空格裁剪**只接受一个输入的参数。 这些 functoid**字符串查找**，**左侧字符串提取**，并**右侧字符串提取**接受两个输入参数。 **字符串中提取**functoid 接受三个输入，而**字符串连接**functoid 接受 1 到 100 之间的输入的参数。  

 两个**字符串**functoid 引用字符串中字符的数字位置：**字符串提取**并**字符串查找**。 这些 functoid 开始计数字符位置 1，而不是 0。  

 这两个字符串裁剪 functoid**字符串左侧空格裁剪**并**字符串右侧空格裁剪**，删除所有空白字符 （空格、 制表符等） 从左侧或右侧 （如可能是这种情况） 的指定字符串。  

## <a name="available-functoids"></a>可用的 functoid 
 **字符串**functoid 包括： 

* Lowercase
* 大小
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
