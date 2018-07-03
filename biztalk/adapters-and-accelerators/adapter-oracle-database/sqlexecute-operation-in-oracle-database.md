---
title: Oracle 数据库中的 SQLEXECUTE 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DML
- data manipulation language
- operations, DML
- SQLEXECUTE
ms.assetid: d7f881e4-c668-4f8e-b08a-ea6614b65910
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfae55d12ce3b244001bf04aef48ff40b97d97a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000508"
---
# <a name="sqlexecute-operation-in-oracle-database"></a>Oracle 数据库中的 SQLEXECUTE 操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]显示一组标准的 Oracle 数据库项目上的操作。 通过使用这些操作，可以执行诸如调用 Oracle 函数或过程，或执行对表的基本 SQL 数据操作语言 (DML) 操作。 但是，可能有需要你执行操作的方案由您的业务逻辑驱动的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不能显示。 例如，您可能希望：  
  
- 不显示的数据库项目上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 例如，获取 CURVAL 或 NEXTVAL Oracle 序列。  
  
- 执行数据定义语言操作;例如，创建一个表。  
  
- 如果没有安装在设计时用于数据库项目上执行操作例如，更新您的业务逻辑创建一个临时表中的记录。  
  
- 执行更复杂的表比操作的 DML 操作的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]显示; 例如，若要执行查询，包括对 JOIN 子句。  
  
  对于这些类型的情况下， [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] SQLEXECUTE 操作的图面。 SQLEXECUTE 操作 （/） 在根节点下显示在**选择一个类别**窗格中的[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。  
  
  通过使用 SQLEXECUTE 操作，可以对 Oracle 数据库执行参数化的 SQL 语句。 SQLEXECUTE 操作支持的参数集，您可以执行一次为每个集的同一 SQL 语句包含一个输入的参数块。 SQLEXECUTE 操作返回中泛型的记录集的 SQL 语句的结果。  
  
> [!NOTE]
>  可以将传递在和中 OUT 参数到过程、 函数和 SQLEXECUTE 操作中的包。 调用的项目将执行与 Oracle 数据库中; 提供的参数但是，SQLEXECUTE 操作不返回输出的值并向客户端在 OUT 参数。 如果你想要调用过程、 函数或包，我们建议通过调用专用的操作来执行操作的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]针对这些 Oracle 项目公开。  
  
 有关详细信息：  
  
- 使用执行 SQLEXECUTE 操作的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[通过使用 BizTalk Server 运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md)。  
  
- 执行 SQLEXECUTE 操作的使用 WCF 服务模型，请参阅[通过使用 WCF 服务模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)。  
  
- 执行 SQLEXECUTE 操作的使用 WCF 通道模型，请参阅[通过使用 WCF 通道模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)。  
  
- 消息结构和执行 SQLEXECUTE 操作的 SOAP 操作，请参见[SQLEXECUTE 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)