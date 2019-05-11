---
title: 若要将特殊字符解释为字段值的一部分的方式 |Microsoft Docs
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
ms.openlocfilehash: f802eca93622a893787ebc06f3cf6cebf4004918
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393634"
---
# <a name="ways-to-interpret-special-characters-as-part-of-a-field-value"></a>如何将特殊字符解释为字段值的一部分
位置和分隔记录中的字段可以包含不同类型，例如面板、 环绕符和转义符的特殊字符。 分隔的记录还可以包含用于从另一条记录分隔记录和一条记录中的字段的一个或多个不同的分隔符字符。 有时这些特殊字符是数据本身的一部分，不应将被解释为特殊在这些情况下。  
  
 使用 Microsoft 的平面文件架构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]标记出现的特殊字符为字段所包含的数据的简单部分支持两种不同方法。 这两种方法使用了转义符和环绕符分别。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [转义字符](../core/escape-characters.md)  
  
-   [换行符](../core/wrap-characters.md)