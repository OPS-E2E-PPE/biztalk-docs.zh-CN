---
title: 警告-使用自定义 XSLT 和扩展 XML |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.usingCustomXsltAndExtensionXML
ms.assetid: b86da5fb-6435-4e3b-89b6-d9d036b5152b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce44d40fd726731261536b622fdb9b24c65f4281
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393635"
---
# <a name="warning---using-custom-xslt-and-extension-xml"></a>警告-使用自定义 XSLT 和扩展 XML
**错误代码**  
  
 btm1035  
  
 **说明**  
  
 替代值**自定义 XSLT 路径**并**自定义扩展 XML**属性控制此映射，完全忽略任何映射生成的输出实例消息指定源和目标架构之间。 如果这是有意为之，你可以忽略此警告。  
  
 这是有效的一种方案是使用 BizTalk 映射器来生成初级 XSLT 的映射，修改此 XSLT 手动以满足特定的其他要求，并作为的值指定修改后的文件**自定义 XSLT 路径**属性，从而在随后的映射操作过程中替代初级 XSLT。  
  
 **用户执行任何操作**  
  
 如果不打算重写此映射内指定的映射，删除的替代值**自定义 XSLT 路径**属性和**自定义扩展 XML**属性，根据需要。