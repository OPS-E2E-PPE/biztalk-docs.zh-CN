---
title: "对函数和 Oracle 数据库中的存储的过程的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- REF CURSOR
- packaged functions and procedures
- operations, on functions and stored procedures
- stored procedure
- RECORD type
- overloaded functions and procedures
ms.assetid: 18072b58-65b2-4da5-9433-ea0da4e2d4f4
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78181aae7921cad3996e4bd408e604857a2bd15e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-functions-and-stored-procedures-in-oracle-database"></a>对函数和 Oracle 数据库中的存储的过程的操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]按以下方式支持 Oracle 函数、 过程和包：  
  
-   **函数**作为操作。 该操作的名称是 Oracle 函数的名称。 在扩展和扩展参数支持，以及，返回值。  
  
-   **过程**作为操作。 该操作的名称是 Oracle 过程的名称。 在中，扩展，然后在扩展支持参数。  
  
-   **打包函数和过程**作为操作。 由 Oracle 包的名称进行限定的名称和命名空间的操作 （函数或过程）。 重载都受支持 （请参阅下一步的项目符号） 的包中。  
  
-   **重载函数和过程**作为操作进行展示在包中。 每个重载函数或过程显示使用字符串追加到标识重载其名称。 此字符串是序列"overload1"、"overload2"、"overload3"等的一部分。  
  
-   **REF CURSOR 类型**IN、 OUT，支持和在 OUT 参数过程和函数，以及函数的返回值。 有关详细信息，请参阅[函数和过程与 REF CURSOR 参数上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)。  
  
-   **记录类型**IN、 OUT，支持和在 OUT 参数过程和函数，以及函数的返回值。 支持简单和复杂 （嵌套） 的记录类型。 [对函数和过程的记录类型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
 有关详细信息：  
  
-   通过使用调用的 Oracle 过程或函数[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[调用函数和 Oracle 数据库使用 BizTalk Server 中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)和[调用重载函数和过程在 Oracle 数据库中使用BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md)。  
  
-   调用的 Oracle 过程或函数，通过使用 WCF 服务模型，请参阅[调用函数和 Oracle 数据库使用 WCF 服务模型中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。  
  
-   调用的 Oracle 过程或函数，通过使用 WCF 通道模型，请参阅[调用使用 WCF 通道模型的 Oracle 数据库中的函数](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)。  
  
-   消息结构和 SOAP 操作用于调用 Oracle 过程和函数，请参阅[函数和过程的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)