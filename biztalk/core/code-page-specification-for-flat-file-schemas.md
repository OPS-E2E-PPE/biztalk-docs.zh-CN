---
title: 代码页规范是平面文件架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 825e75f1-893c-4c61-b566-f893d732a907
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64d5cfbc960346e702ed0d4a39ca74bbc4b3634c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232261"
---
# <a name="code-page-specification-for-flat-file-schemas"></a>平面文件架构的代码页规范

## <a name="overview"></a>概述
中的值**代码页**属性用于创建反汇编和程序集的平面文件文档过程中使用的编码对象。 此编码对象允许平面文件分析器要转换的入站平面文件文档本机编码为规范化的 utf-8 编码，供 Microsoft 内部使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 使用此编码对象，平面文件序列化程序还可以将内部 UTF-8 编码重新转换为平面文件文档的本机编码。  
  
 设置**代码页**属性在起着重要的是，但不是独占的作用确定你平面文件的业务文档所使用的字符编码方案。 您必须考虑平面文件拆装器如何解释入站平面文件消息，以及在将出站消息转换为平面文件格式时平面文件组装器将如何对字符进行编码。  

## <a name="character-encoding"></a>字符编码  
 在确定如何处理指定实例消息的字符编码时，有多种会影响处理方式的因素，如下所示：  
  
-   在拆装平面文件实例消息时，使用以下算法来确定和保留编码信息：  
  
    1.  如果**Charset**消息正文部分中，则使用它的值。  
  
    2.  否则为如果在信封 （或文档） 架构指定代码页使用**代码页**使用属性，其值。  
  
    3.  否则，如果存在字节顺序标记，则使用该标记的值。  
  
    4.  否则，假定为 UTF-8。  
  
-   装配时平面文件实例消息，以下算法用于确定要用于解码的字符集：  
  
-   如果**XMLNorm.TargetCharset**消息上下文属性设置，则使用其值。  
  
-   否则为如果**TargetCharset**汇编程序 （设计时） 属性设置，则使用其值。  
  
-   否则为如果在信封 （或文档） 架构指定代码页使用**代码页**使用属性，其值。  
  
    1.  否则为如果**SourceCharset**消息上下文属性设置，则使用其值。  
  
    2.  否则，使用 UTF-8。  
  
## <a name="see-also"></a>另请参阅  
 **注意事项时创建平面文件消息架构**和**代码页 （的平面文件架构的节点属性）**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]