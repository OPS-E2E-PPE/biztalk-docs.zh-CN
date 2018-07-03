---
title: 对函数和过程的 Oracle 数据库中的记录类型的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD type
ms.assetid: 28ecb76c-de82-43df-83cc-917c482417b3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2635ac4b21173fe1a12603c60263dfa70b5a18e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974198"
---
# <a name="operations-on-functions-and-procedures-with-record-types-in-oracle-database"></a>对函数和过程的 Oracle 数据库中的记录类型的操作
Oracle 记录类型用于表示层次结构中传递到 PL/SQL 函数和过程的参数信息。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现为 XML 的复杂类型的记录类型。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持以下类型的记录类型：  
  
- 声明为表 %行类型参数在存储的过程和函数中的记录类型。  
  
- 例如，声明为类型的记录参数 PL/SQL 包中的记录类型键入 rec_type1 是 RECORD(name varchar2(100), age number(3));  
  
- 包含嵌套的记录的记录类型。  
  
- 缩小，显示作为中的记录类型或为过程或函数在 OUT 参数。  
  
- 是函数的返回值的记录类型。  
  
  > [!NOTE]
  >  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持 BFILE 作为记录成员的类型。  
  
  有关信息：  
  
- 调用的函数或过程涉及使用 WCF 服务模型的记录类型，请参阅[运行操作使用记录的类型在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)。  
  
- 调用的函数或过程涉及记录类型使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[调用的函数和过程的记录类型通过使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md)。  
  
- 记录的 XML 结构类型所支持的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[记录类型的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)