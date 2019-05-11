---
title: 对包含记录类型 1> 函数和过程的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afc1c84f-2e36-493c-9ea8-4bc2248331db
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d686ae41a7121f3f38eea4b8e008f51be635c38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375315"
---
# <a name="operations-on-functions-and-procedures-with-record-types"></a>对函数和过程的记录类型的操作
Oracle 记录类型用于表示层次结构中传递到 PL/SQL 函数和过程的参数信息。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现为 XML 的复杂类型的记录类型。 

## <a name="supported-record-types"></a>支持的记录类型
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]支持以下类型的记录类型：  
  
- 声明为表 %行类型参数在存储的过程和函数中的记录类型。  
  
- 声明为类型的记录参数 PL/SQL 包中的记录类型。 例如，键入 rec_type1 是 RECORD(name varchar2(100), age number(3));  
  
- 包含嵌套的记录的记录类型。  
  
- 缩小，显示作为中的记录类型或为过程或函数在 OUT 参数。  
  
- 是函数的返回值的记录类型。  
  
  > [!NOTE]
  >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 BFILE 作为记录成员的类型。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)