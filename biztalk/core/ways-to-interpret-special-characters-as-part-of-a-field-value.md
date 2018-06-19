---
title: 如何解释的特殊字符作为字段值的一部分 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e19a202-4e4d-42e0-ba1e-fddc52792b21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b96a3c7502a47541e8e58ec3df3eccf6098e3abc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288381"
---
# <a name="ways-to-interpret-special-characters-as-part-of-a-field-value"></a>如何解释的特殊字符作为字段值的一部分
位置记录和分隔记录中的字段均可包含不同类型的特殊字符，例如，填充字符、环绕符和转义符。 分隔记录还可以包含一个或多个不同的分隔符，这些字符用于将记录中的各字段分开以及分隔记录。 有时，这些特殊字符是数据自身的一部分，在这种情况下，不应将其作为特殊字符进行解释。  
  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 所使用的平面文件架构支持两种不同的技术，用于将原本是特殊字符的出现标记为字段所包含数据的简单部分。 这两种技术分别使用了转义符和环绕符。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [转义字符](../core/escape-characters.md)  
  
-   [自动换行字符](../core/wrap-characters.md)