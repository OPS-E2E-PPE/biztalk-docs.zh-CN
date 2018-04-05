---
title: 警告-找不到记录正文 XPath |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.recordBodyXPathNotFound
ms.assetid: d46e0732-08ce-4292-84d8-56dc020063e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd6640aa469fe9383b615d70235ab488c8798f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="warning---record-body-xpath-not-found"></a>警告-找不到记录正文 XPath
**错误代码**  
  
 BEC1008  
  
 **说明**  
  
 **正文 XPath**找到此信封架构中指定的根节点的属性为空或引用不存在的节点。 信封架构，由指定**信封**属性**架构**节点，都需要有一个有效的值**正文 XPath**指定根的属性架构中的引用节点。  
  
 如果不指定任何根参考节点**根引用**属性**架构**节点，第一个根节点在架构中，默认根引用节点时，需要在其具有有效的值**正文 XPath**属性。 **正文 XPath**属性值用于标识每个信封中包含的消息的架构。  
  
 **用户执行任何操作**  
  
 选择指定的根节点，然后选择的值**正文 XPath**正确标识关联的消息正文的架构的属性。