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
ms.openlocfilehash: 6b7d4f392e863dd8966f5c011abfd6e602f2514c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006430"
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