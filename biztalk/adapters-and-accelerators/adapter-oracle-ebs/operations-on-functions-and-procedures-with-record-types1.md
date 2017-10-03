---
title: "对函数和过程与记录类型 1> 操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afc1c84f-2e36-493c-9ea8-4bc2248331db
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43974d1c392a357b9781ff7f6fae5286e282513a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-functions-and-procedures-with-record-types"></a>对函数和过程的记录类型的操作
Oracle 记录类型用于表示传递给 PL/SQL 函数和过程的参数中的分层信息。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现为复杂的 XML 类型的记录类型。 

## <a name="supported-record-types"></a>支持的记录类型
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]支持以下类型的记录类型：  
  
-   声明为表中存储的过程和函数的 %rowtype 参数的记录类型。  
  
-   声明为类型的记录参数 PL/SQL 包中的记录类型。 例如，键入 rec_type1 是 RECORD(name varchar2(100), age number(3));  
  
-   包含嵌套的记录的记录类型。  
  
-   记录中显示类型，作为，出或在 OUT 参数为过程或函数。  
  
-   是函数的返回值的记录类型。  
  
    > [!NOTE]
    >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持作为记录成员 BFILE 类型。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)