---
title: 在使用 SQL 适配器的 SQL Server 中执行存储过程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245626a7-f546-4aca-90df-c0579139a872
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6515baa313fc6b68c62556ad5b5883500cfde8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021550"
---
# <a name="execute-stored-procedures-in-sql-server-using-the-sql-adapter"></a>在使用 SQL 适配器的 SQL Server 中执行存储过程
TRANSACT-SQL 和 SQL Server 中的 CLR 存储过程作为中的操作[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]下**过程**时使用的节点[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 操作名称由[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]将与 SQL Server 中的存储过程的名称相同。 在相应的操作中公开的存储过程中的所有参数。 OUT 参数包含存储过程的返回值。 存储过程的结果集是数据集的数组。 有关数据集的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=196853 ](http://go.microsoft.com/fwlink/?LinkId=196853)。 在运行时作为响应消息的一部分获取的目标对象的架构信息。  

 但是，如果你想要获取在设计时目标对象的架构信息，则必须生成的过程的架构**Strongly-Typed 过程**中的节点[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请注意，在显示的相同的存储的过程**过程**并**Strongly-Typed 过程**节点。 存储过程的返回值是强类型化，而不只是数据集的数组。 由于在设计时是可用的架构信息，可用于将存储过程的架构映射到不同的操作的另一个架构。 例如，可以映射到数据库表上插入操作生成的架构为强类型化过程生成的架构。  

> [!NOTE]
>  你将无法再以查看是否在设计时为强类型化的存储过程的架构信息：  
> 
> - 使用游标，这是另一个存储过程的返回值作为输入参数为强类型化的存储过程。  
>   -   它是执行对表的某些操作一个 CLR 存储过程。  

## <a name="support-for-stored-procedures-with-for-xml-clause"></a>支持使用 FOR XML 子句的存储过程  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]还使您可以执行具有带 FOR XML 子句的 SELECT 语句的存储的过程。 在 SELECT 语句中使用 FOR XML 子句以 XML 形式返回结果，而不是行集。 有关 FOR XML 子句的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=131402 ](http://go.microsoft.com/fwlink/?LinkId=131402)。  

> [!NOTE]
>  "本机"[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]适用于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]支持仅这些存储过程返回的 XML，这就是，具有 FOR XML 子句的 SELECT 语句中。 具有 FOR XML 子句的存储过程的支持，则可以执行这些存储的过程使用基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]而无需对存储的过程定义进行任何更改。  

## <a name="support-for-stored-procedures-with-temporary-tables"></a>支持使用临时表的存储过程  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ，可以生成包含其定义中的临时表的存储过程的元数据。 但是，对于此类存储过程必须生成元数据通过选择存储的过程只从**过程**节点，同时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 适配器不支持从在此类存储过程生成的元数据**Strongly-Typed 过程**节点。  

## <a name="support-for-result-sets-containing-columns-without-names-or-with-same-names"></a>对结果集包含列没有名称或具有相同名称的支持  
 下表列出了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]处理不包含名称和存储的过程和强类型化的存储的过程的结果集的相同名称的列。  


|    结果集包含...     |                                                                                                                                                       存储过程                                                                                                                                                       |                                                                                                           强类型的存储的过程                                                                                                            |
|-----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  **没有名称的列**  | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]按以下方式生成列的名称： 为没有列生成唯一 ID (GUID)"-"（连字符），然后此 GUID 字符串前缀为"C"因为生成的 GUID 可能会以数字开头，但 XML 标记名称不能。 |                                [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]会生成以下名称的列:"UnNamedColumn [column_index]"，从该位置 column_index 开始从"0"。                                |
| **具有相同名称的列** |                                                                                第一个以外的列的名称后面附加了"*"（下划线） 后, 跟没有的情况下的随机 GUID"-"（连字符）。例如:"\\*[GUID]"。                                                                                | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持具有相同名称的列中的结果集，并引发异常。 **重要说明：** 必须确保在结果集中的列名称具有唯一的名称。 |

> [!NOTE]
>  一般情况下，建议在结果中的所有列都设置的存储过程和强类型化的存储的过程必须命名为，并且具有唯一的名称。  

 有关详细信息：  

-   如何执行存储的过程，请参阅[在使用 BizTalk Server 的 SQL Server 中执行存储的过程](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)。  

-   如何执行存储的过程具有 FOR XML 子句，请参阅[执行存储的过程中使用 BizTalk Server 的 SQL Server 具有 FOR XML 子句](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)。  

-   消息的存储过程的架构，请参阅[过程和函数的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)。  

## <a name="see-also"></a>请参阅  
 [连接到 SAP 系统使用的适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)