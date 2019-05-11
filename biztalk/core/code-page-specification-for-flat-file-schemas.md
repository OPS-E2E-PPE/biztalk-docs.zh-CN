---
title: 代码页规范平面文件架构的 |Microsoft Docs
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
ms.openlocfilehash: 5b0ba2c19c3fc02ff0a72fcd8e93ec9f4b112996
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357176"
---
# <a name="code-page-specification-for-flat-file-schemas"></a>平面文件架构的代码页规范

## <a name="overview"></a>概述
中的值**代码页**属性用于创建在拆装和组装平面文件文档过程中使用的编码对象。 此编码对象，平面文件分析器将转换为规范化 utf-8 编码的本机编码的入站平面文件文档由 Microsoft 在内部使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 编码的对象还允许将转换回本机编码的平面文件文档的内部 utf-8 编码的平面文件序列化程序。  
  
 设置**代码页**属性起着重要的是，但并非唯一作用在确定您的平面文件业务文档使用的字符编码方案。 您必须考虑如何在平面文件组装器将对字符进行编码的出站消息转换为平面文件格式，平面文件拆装器将解释消息的入站平面文件。  

## <a name="character-encoding"></a>字符编码  
 有在确定如何为给定的实例消息的字符编码处理，按如下所示发挥作用的多个因素：  
  
-   在拆装平面文件实例消息，使用以下算法来确定和保留编码信息：  
  
    1.  如果**Charset**消息正文部分中，则使用它的值。  
  
    2.  否则为如果信封 （或文档） 架构指定代码页使用**代码页**使用属性，其值。  
  
    3.  否则，如果存在字节顺序标记，则使用它的值。  
  
    4.  否则，假定 utf-8。  
  
-   在组装平面文件实例消息，使用以下算法来确定要用于解码的字符集：  
  
-   如果**XMLNorm.TargetCharset**消息上下文属性设置，则使用的值。  
  
-   否则为如果**TargetCharset**组装器 （设计时） 属性设置，则使用的值。  
  
-   否则为如果信封 （或文档） 架构指定代码页使用**代码页**使用属性，其值。  
  
    1.  否则为如果**SourceCharset**消息上下文属性设置，则使用的值。  
  
    2.  否则，使用 utf-8。  
  
## <a name="see-also"></a>请参阅  
 **考虑事项时创建平面文件消息架构**和**代码页 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]