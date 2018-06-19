---
title: 警告-使用自定义 XSLT 和扩展的 XML |Microsoft 文档
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
ms.openlocfilehash: 90644aec738345e3a36286cc62aaa7a355e04348
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288581"
---
# <a name="warning---using-custom-xslt-and-extension-xml"></a>警告-使用自定义 XSLT 和扩展 XML
**错误代码**  
  
 btm1035  
  
 **说明**  
  
 值替代存在**自定义 XSLT 路径**和**自定义扩展 XML**属性控制此映射，完全忽略任何映射生成的输出实例消息指定源和目标架构之间。 如果是故意如此，则可忽略此警告。  
  
 这是有效的一种情况是使用 BizTalk 映射程序来生成的映射的初步 XSLT，修改此 XSLT 手动来满足特定的其他要求，然后指定作为的值的修改后的文件**自定义 XSLT 路径**属性，从而在后续的映射操作期间替代初级 XSLT。  
  
 **用户执行任何操作**  
  
 如果不打算重写此映射内指定的映射，删除的替代值**自定义 XSLT 路径**属性和**自定义扩展 XML**属性，根据需要。