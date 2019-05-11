---
title: 用于 Oracle 数据库的 BizTalk 适配器的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, limitations of
ms.assetid: eab4ddea-f986-43c2-82bb-b9fe37961a5b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11cb88205b56b3ff773ad88141f9ef5b845d920b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529052"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-database"></a>用于 Oracle 数据库的 BizTalk 适配器的限制
## <a name="general"></a>常规  
 以下已知的限制[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:  
  
- 不包括一些例外情况，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]兼容使用早期版本的适配器。 自上次发布以来已发生更改的列表，请参阅[Oracle 数据库的 BizTalk 适配器中的主要功能](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持 XML 类型。  
  
- SQLEXECUTE 操作的扩展不返回值或为过程、 函数或包中 OUT 参数。 出于此原因，您必须调用过程、 函数和包使用的专用的操作，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]针对这些 Oracle 项目公开。  
  
- 从使用代理服务器进行编程，Oracle 数据库检索数据时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不会有多个 65536 节点的 XML 消息反序列化。 请确保响应消息具有节点小于或等于为 65536。 可以通过修改你的应用程序的 app.config 文件来解决此限制。 有关说明，请参阅[与 Oracle 数据库适配器的操作问题疑难解答](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]采用输入字符串，并构造的适配器，然后执行 SQL 命令。 但是，在输入的字符串可能包含也会立即执行的其他 SQL 命令，并且可能会破坏操作协定。  
  
   假设其中适配器提供对存储过程输入的 REF CURSOR。 在此类方案中，适配器客户端必须提供一个命令，在执行时，获取 REF CURSOR。 适配器，请对存储过程传递 REF CURSOR。 但是，如果获取 REF CURSOR 的命令执行一些其他修改数据库时，执行存储的过程的操作协定将断开。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持嵌套只有最多两个级别的 UDT。  
  
- 使用与适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，如果在 WCF 自定义的凭据将发送端口不正确，不会处理请求消息。 指定正确的凭据后，将消息发送到 Oracle 数据库和收到的响应。 但是，响应消息不是输出连接到可用的。 在这种情况下，可能需要重新启动主机实例。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持复杂类型 （如记录类型、 表类型、 UDT 和 VARRAY） 的 BFILE 数据类型。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持具有循环引用的用户定义类型 (Udt)。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行不支持记录，其中包含的字段类型的记录类型的 PL/SQL 表。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不会启用客户端可以为 NULL VARRAY 中设置的第一个元素的值。  
  
- 除了 PL/SQL 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持包内定义的 Udt。  
  
## <a name="limitations-due-to-odpnet"></a>由于 ODP.NET 限制  
 以下已知的限制[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]由于 ODP.NET 的限制：  
  
- 对于采用十进制值的 Oracle 数据类型，ODP.NET 时不引发异常的输入的值包含字母字符。 因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 ODP.NET 以便与 Oracle 数据库时，适配器太不会引发异常时将传递字母字符。 例如：  
  
  -   传递插入操作的值"54r"并不会引发异常;而插入的值"54"。  
  
  -   将值"r54"传递的插入操作不会引发异常;而插入的值"0"。  
  
- 由于 ODP.NET 限制，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持使用重载过程使用强类型化和弱类型化 REF CURSOR。 在内部，适配器将这两个强类型化和弱类型化 REF CURSOR 视为只是 REF CURSOR。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持按数值字段不编制索引的 PL/SQL 表。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持不包含任何元素的关联阵列。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持包含使用本地时间区域属性 (TimeStampLTZ) 的时间戳数据类型的 Udt。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持包含的 Udt"。" （句点），其名称中。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持 BLOB、 CLOB、 和 NCLOB 数据类型包含为在 OUT 参数的 Udt。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持以下的简单类型的 Varray Varray:BFILE、 IntervalDS、 IntervalYM、 TimeStampLTZ 和 TimeStampTZ。  
  
- 由于关联阵列的限制，PL/SQL 表或包含任何以下数据类型的记录的 PL/SQL 表中不支持[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
  -   BFILE  
  
  -   BLOB  
  
  -   CLOB  
  
  -   IntervalDS  
  
  -   IntervalYM  
  
  -   Long  
  
  -   NCLOB  
  
  -   RowID  
  
  -   TimeStamp  
  
  -   TimeStampLTZ  
  
  -   TimeStampTZ  
  
## <a name="see-also"></a>请参阅  
 [了解用于 Oracle 数据库的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)