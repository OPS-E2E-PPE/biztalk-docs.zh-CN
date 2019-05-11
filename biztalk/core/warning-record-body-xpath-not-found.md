---
title: 警告-找不到记录正文 XPath |Microsoft Docs
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
ms.openlocfilehash: a651748c16862bbb3a23b3e792c0ab17fc3687f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393648"
---
# <a name="warning---record-body-xpath-not-found"></a>警告-找不到记录正文 XPath
**错误代码**  
  
 BEC1008  
  
 **说明**  
  
 **正文 XPath**找到此信封架构中指示的根节点的属性为空或引用的节点不存在。 信封架构，由指定**信封**的属性**架构**节点，需要具有有效的值**正文 XPath**指定根的属性在架构中的引用节点。  
  
 如果不指定任何根引用节点**根引用**的属性**架构**节点，第一个根节点在架构中，默认根引用节点，需在其具有有效的值**正文 XPath**属性。 **正文 XPath**属性值用于标识信封中包含的消息的每个架构。  
  
 **用户执行任何操作**  
  
 选择指示的根节点，然后选择的值**正文 XPath**正确地标识相关联的消息正文的架构的属性。