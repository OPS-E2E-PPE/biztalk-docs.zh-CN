---
title: "Oracle 数据库中的 SQLEXECUTE 操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DML
- data manipulation language
- operations, DML
- SQLEXECUTE
ms.assetid: d7f881e4-c668-4f8e-b08a-ea6614b65910
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac8d5c8284e1f273d4b9aef17e79e25636dc581
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sqlexecute-operation-in-oracle-database"></a>Oracle 数据库中的 SQLEXECUTE 操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现一组标准的 Oracle 数据库项目上的操作。 通过使用这些操作，你可以执行诸如调用一个 Oracle 函数或过程中，或执行对表的基本 SQL 数据操作语言 (DML) 操作。 但是，可能会要求你执行操作的方案根据你的业务逻辑，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不能显示。 例如，你可能希望：  
  
-   执行上不显示的数据库项目的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 例如，获取 CURVAL 或 NEXTVAL Oracle 序列。  
  
-   执行数据定义语言操作;例如，创建一个表。  
  
-   在未出现在设计时; 一个数据库项目上执行操作例如，更新中创建由业务逻辑的临时表的记录。  
  
-   执行对表比操作的更复杂 DML 操作的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]呈现; 例如，若要执行查询包括对 JOIN 子句。  
  
 对于这些类型的情况下，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]呈现 SQLEXECUTE 操作。 在根节点 （/） 下显示 SQLEXECUTE 操作**选择类别**窗格中的[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。  
  
 通过使用 SQLEXECUTE 操作，你可以对 Oracle 数据库执行参数化的 SQL 语句。 SQLEXECUTE 操作支持包含使你可以执行一次为每个集的相同 SQL 语句的参数集的输入的参数块。 SQLEXECUTE 操作返回泛型记录集内的 SQL 语句的结果。  
  
> [!NOTE]
>  你可以将传递 IN 和到过程、 函数和 SQLEXECUTE 操作中的包在 OUT 参数。 调用的项目将执行与 Oracle 数据库中; 提供的参数但是，SQLEXECUTE 操作不返回扩展的值和到客户端在 OUT 参数。 如果你想要调用过程、 函数或包，我们建议您这样做通过调用专用的操作，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开，以便这些 Oracle 项目。  
  
 有关详细信息：  
  
-   通过执行 SQLEXECUTE 操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[使用 BizTalk server 运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md)。  
  
-   SQLEXECUTE 操作使用执行的 WCF 服务模型，请参阅[使用 WCF 服务模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)。  
  
-   SQLEXECUTE 操作使用执行的 WCF 通道模型，请参阅[使用 WCF 通道模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)。  
  
-   消息结构和执行 SQLEXECUTE 操作的 SOAP 操作，请参阅[SQLEXECUTE 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)