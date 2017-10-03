---
title: "Oracle E-business Suite 的 BizTalk Adapter 限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 149cee03-43cd-4cb3-a937-6565f5e96ce5
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7611c56fbd24c7c7cf09d38d376df585b72b284
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-oracle-e-business-suite"></a>Oracle E-business Suite 的 BizTalk 适配器的限制
## <a name="general-limitations"></a>常规限制  
 以下已知的限制[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 XML 网关、 高级队列和业务事件。  
  
     但是，你可以将业务事件限制避开方式如下：  
  
    1.  在 Oracle 业务事件系统中，创建订阅以业务事件发生时调用自定义的 PL/SQL 过程。  
  
    2.  编写一个自定义的 PL/SQL 过程接收业务事件。  
  
    3.  使用自定义的 PL/SQL 过程来在表中存储 （事件和事件负载），最后生成的数据。  
  
    4.  使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以轮询和/或从表中接收通知。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 XML 类型。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会启用客户端设置中为 NULL VARRAY 的第一个元素的值。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包含的字段的记录类型的记录类型的 PL/SQL 表。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持具有循环引用的用户定义类型 (Udt)。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持复杂类型 （如记录类型，表类型、 UDT 和 VARRAY） 中的 BFILE 数据类型。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持嵌套仅达两个级别的 UDT。  
  
-   除 PL/SQL 表[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持某个包内定义的 Udt。  
  
-   当适配器使用 BizTalk Server 中，如果在 WCF 自定义的凭据发送端口不正确时，不会处理请求消息。 指定正确的凭据后，将消息发送到 Oracle E-business Suite 和收到的响应。 但是，响应消息不可用到的输出端口。 在这种情况下，你可能需要重新启动主机实例。  
  
## <a name="limitations-due-to-odpnet"></a>由于 ODP.NET 的限制  
 以下已知的限制[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]由于 ODP.NET 的限制：  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 PL/SQL 表按数值字段不编制索引。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持不包含任何元素的关联阵列。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包含使用本地时间区域属性 (TimeStampLTZ) 的时间戳数据类型的 Udt。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包含的 Udt"。" （句点），在其名称中。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持为 IN OUT 参数中包含 BLOB、 CLOB、 和 NCLOB 数据类型的 Udt。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持以下简单类型的 Varray 的 Varray: BFILE、 IntervalDS、 IntervalYM、 TimeStampLTZ 和 TimeStampTZ。  
  
-   由于关联的数组的限制，PL/SQL 表或包含任何以下数据类型的记录的 PL/SQL 表中不支持[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
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
 [了解有关 Oracle E-business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)