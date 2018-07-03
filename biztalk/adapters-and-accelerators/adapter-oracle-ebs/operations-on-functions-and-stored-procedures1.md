---
title: 对函数和存储的 Procedures1 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e6bdaa7-ed3c-43bc-bed5-70fe43f9c2d1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3356b41fc7929c55794c65e804245ed231b19b18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007822"
---
# <a name="operations-on-functions-and-stored-procedures"></a>对函数和存储的过程的操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]支持 Oracle 函数和过程。

## <a name="functions-and-procedures"></a>函数和过程

[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]按以下方式支持 Oracle 函数和过程：  
  
- **函数**作为操作。 操作的名称是该 Oracle 函数的名称。 在中，扩展，并在扩展参数支持，以及，返回值。  
  
  > [!IMPORTANT]
  >  如果在函数中传递了无效的参数 （即，将传递数值字段的字符串值）[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可能引发取决于 ODP.NET 行为异常。 这是因为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 ODP.NET 与 Oracle E-business Suite 进行通信。  
  
- **过程**作为操作。 操作的名称是该 Oracle 过程的名称。 在中，扩展，并在扩展中支持参数。  
  
  > [!IMPORTANT]
  >  过程，如果在插入或更新到接口表或数据库表的数值字段的十进制值 (例如，15.2)[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将引发异常。 这是因为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 ODP.NET 通信与 Oracle E-business Suite 和 ODP.NET 不支持接受数值字段的十进制值。  
  
- **REF CURSOR 类型**支持 IN 和 OUT 参数的过程和函数，以及函数的返回值。 有关详细信息，请参阅[对包含 REF CURSOR 参数函数和过程的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)。  
  
- **记录类型**IN、 OUT，支持，以及在 OUT 参数的过程和函数，以及函数的返回值。 支持简单和复杂 （嵌套） 的记录类型。 [对包含 RECORD 类型的函数和过程的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
> [!NOTE]
>  此外可以设置为函数和存储的过程中的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)