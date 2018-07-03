---
title: 对函数和 Oracle 数据库中的存储的过程的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF CURSOR
- packaged functions and procedures
- operations, on functions and stored procedures
- stored procedure
- RECORD type
- overloaded functions and procedures
ms.assetid: 18072b58-65b2-4da5-9433-ea0da4e2d4f4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 856e6bf882605737380f0bbe6185dce8a56c5828
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979606"
---
# <a name="operations-on-functions-and-stored-procedures-in-oracle-database"></a>对函数和 Oracle 数据库中的存储的过程的操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]按以下方式支持 Oracle 函数、 过程和包：  
  
- **函数**作为操作。 操作的名称是该 Oracle 函数的名称。 在中，扩展，并在扩展参数支持，以及，返回值。  
  
- **过程**作为操作。 操作的名称是该 Oracle 过程的名称。 在中，扩展，并在扩展中支持参数。  
  
- **打包函数和过程**作为操作。 由 Oracle 包的名称进行限定的名称和命名空间的操作 （函数或过程）。 重载都受支持 （请参阅下一个项目符号） 的包中。  
  
- **重载函数和过程**作为操作会显示在包中。 每个重载函数或过程显示与附加到标识重载其名称的字符串。 此字符串是序列"overload1"、"overload2"、"overload3"等的一部分。  
  
- **REF CURSOR 类型**IN、 OUT，支持，以及在 OUT 参数的过程和函数，以及函数的返回值。 有关详细信息，请参阅[对包含 REF CURSOR 参数函数和过程的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)。  
  
- **记录类型**IN、 OUT，支持，以及在 OUT 参数的过程和函数，以及函数的返回值。 支持简单和复杂 （嵌套） 的记录类型。 [对包含 RECORD 类型的函数和过程的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
  有关详细信息：  
  
- 通过使用调用 Oracle 过程或函数[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[调用的函数和使用 BizTalk Server 的 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)和[调用重载函数和过程中使用 Oracle 数据库BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md)。  
  
- Oracle 过程或函数使用调用的 WCF 服务模型，请参阅[调用的函数和 Oracle 数据库使用 WCF 服务模型中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。  
  
- Oracle 过程或函数使用调用的 WCF 通道模型，请参阅[调用的函数在 Oracle 数据库中使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)。  
  
- 消息结构和 SOAP 操作用于调用 Oracle 过程和函数，请参阅[函数和过程的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)