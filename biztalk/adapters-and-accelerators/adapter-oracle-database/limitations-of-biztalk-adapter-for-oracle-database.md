---
title: 用于 Oracle 数据库的 BizTalk Adapter 限制 |Microsoft 文档
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
ms.openlocfilehash: cd6cfea523333752c0ee18fefbc6a1848057fe36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-oracle-database"></a>用于 Oracle 数据库的 BizTalk Adapter 限制
## <a name="general"></a>常规  
 以下已知的限制[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:  
  
-   禁止一些例外情况，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与以前的版本中的适配器兼容。 自最后一个版本以来发生了更改的列表，请参阅[用于 Oracle 数据库的 BizTalk Adapter 中的密钥功能](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持 XML 类型。  
  
-   SQLEXECUTE 操作不返回扩展值或对过程、 函数或包 IN OUT 参数。 为此，你必须调用过程、 函数和包使用的专用的操作，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开，以便这些 Oracle 项目。  
  
-   从使用代理编程，Oracle 数据库检索数据时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不具有多个 65536 节点的 XML 消息反序列化。 请确保响应消息有节点小于或等于为 65536。 可以通过修改你的应用程序的 app.config 文件来解决此限制。 有关说明，请参阅[排除操作问题与 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]采用输入字符串和构造的适配器，然后执行的 SQL 命令。 但是，输入的字符串可能包含其他还会立即执行的 SQL 命令，并且可能会破坏操作协定。  
  
     请考虑该适配器上提供了对存储过程输入的 REF CURSOR 的方案。 在此类方案中，适配器客户端必须提供命令，在执行时，获取 REF CURSOR。 适配器，然后在 REF CURSOR 传递给该存储过程。 但是，如果用于获取 REF CURSOR 的命令执行一些其他修改数据库时，执行存储的过程的操作协定将断开。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持嵌套仅达两个级别的 UDT。  
  
-   使用具有适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，如果在 WCF 自定义的凭据将发送端口不正确，不会处理请求消息。 指定正确的凭据后，将消息发送到 Oracle 数据库和收到的响应。 但是，响应消息不可用到的输出端口。 在这种情况下，你可能需要重新启动主机实例。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持复杂类型 （如记录类型，表类型、 UDT 和 VARRAY） 中的 BFILE 数据类型。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持具有循环引用的用户定义类型 (Udt)。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持包含的字段的记录类型的记录类型的 PL/SQL 表。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不会启用客户端设置中为 NULL VARRAY 的第一个元素的值。  
  
-   除 PL/SQL 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持某个包内定义的 Udt。  
  
## <a name="limitations-due-to-odpnet"></a>由于 ODP.NET 的限制  
 以下已知的限制[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]由于 ODP.NET 的限制：  
  
-   对于采用十进制值的 Oracle 数据类型，ODP.NET 不引发异常如果输入的值包含字母字符。 因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用与 Oracle 数据库时，适配器 ODP.NET 太不会引发异常时传递字母字符。 例如：  
  
    -   传递插入操作的值"54r"并不会引发异常;而被插入的值"54"。  
  
    -   将值"r54"传递的插入操作不会引发异常;而被插入的值"0"。  
  
-   鉴于 ODP.NET 限制，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持重载过程使用强类型和弱类型化的 REF CURSOR 的使用。 在内部，该适配器将这两个强类型和弱类型 REF CURSOR 视为只 REF CURSOR。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持 PL/SQL 表按数值字段不编制索引。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持不包含任何元素的关联阵列。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持包含使用本地时间区域属性 (TimeStampLTZ) 的时间戳数据类型的 Udt。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持包含的 Udt"。" （句点），在其名称中。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持为 IN OUT 参数中包含 BLOB、 CLOB、 和 NCLOB 数据类型的 Udt。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持以下简单类型的 Varray 的 Varray: BFILE、 IntervalDS、 IntervalYM、 TimeStampLTZ 和 TimeStampTZ。  
  
-   由于关联的数组的限制，PL/SQL 表或包含任何以下数据类型的记录的 PL/SQL 表中不支持[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
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
  
## <a name="see-also"></a>另请参阅  
 [了解 BizTalk 适配器用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)