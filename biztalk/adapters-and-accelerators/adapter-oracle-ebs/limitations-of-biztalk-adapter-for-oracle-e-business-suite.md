---
title: 用于 Oracle E-business Suite 的 BizTalk 适配器的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 149cee03-43cd-4cb3-a937-6565f5e96ce5
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6de75a2955632f4f8e0daae2a2035e90f1f2fca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988390"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-e-business-suite"></a>用于 Oracle E-business Suite 的 BizTalk 适配器的限制
## <a name="general-limitations"></a>一般限制  
 以下已知的限制[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 XML 网关、 高级队列和业务事件。  
  
   但是，就可以绕过业务事件限制如下所示：  
  
  1. 在 Oracle 业务事件系统，创建业务事件发生时调用的自定义的 PL/SQL 过程的订阅。  
  
  2. 编写一个自定义的 PL/SQL 过程，接收业务事件。  
  
  3. 使用自定义的 PL/SQL 过程来在表中存储结果的数据 （事件和事件有效负载）。  
  
  4. 使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]来轮询和 / 或从表中接收通知。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 XML 类型。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会启用客户端可以为 NULL VARRAY 中设置的第一个元素的值。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]执行不支持记录，其中包含的字段类型的记录类型的 PL/SQL 表。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持具有循环引用的用户定义类型 (Udt)。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持复杂类型 （如记录类型、 表类型、 UDT 和 VARRAY） 的 BFILE 数据类型。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持嵌套只有最多两个级别的 UDT。  
  
- 除了 PL/SQL 表[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包内定义的 Udt。  
  
- 当使用适配器与 BizTalk Server，如果在 WCF 自定义凭据的发送端口不正确时，不会处理请求消息。 指定正确的凭据后，将消息发送到 Oracle E-business Suite 和收到的响应。 但是，响应消息不是输出连接到可用的。 在这种情况下，可能需要重新启动主机实例。  
  
## <a name="limitations-due-to-odpnet"></a>由于 ODP.NET 限制  
 以下已知的限制[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]由于 ODP.NET 的限制：  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持按数值字段不编制索引的 PL/SQL 表。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持不包含任何元素的关联阵列。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包含使用本地时间区域属性 (TimeStampLTZ) 的时间戳数据类型的 Udt。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包含的 Udt"。" （句点），其名称中。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 BLOB、 CLOB、 和 NCLOB 数据类型包含为在 OUT 参数的 Udt。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持以下的简单类型的 Varray Varray: BFILE、 IntervalDS、 IntervalYM、 TimeStampLTZ 和 TimeStampTZ。  
  
- 由于关联阵列的限制，PL/SQL 表或包含任何以下数据类型的记录的 PL/SQL 表中不支持[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
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
 [了解用于 Oracle E-Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)