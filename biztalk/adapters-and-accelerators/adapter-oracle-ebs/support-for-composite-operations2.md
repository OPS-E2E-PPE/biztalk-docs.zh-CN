---
title: 支持复合 Operations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f65cf10-4e27-4872-bc6a-defe6cbab198
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7624211805af0e16df4cd6853f1a425edf874d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374535"
---
# <a name="support-for-composite-operations"></a>支持复合操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端能够执行可以包含任意数量的以下操作，并按任何顺序的复合操作：  
  
- 选择、 插入、 更新和删除对界面表和数据库表的操作。  
  
- 选择接口视图和数据库视图上的执行操作。  
  
- 存储的过程、 函数和过程中显示为该适配器中的操作的包。  
  
  中的复合运算操作可以针对同一个数据库或不同的数据库中表和视图。 但是，不能共享数据或将其在复合操作中的不同操作中重复使用。 例如，在复合操作中，选择操作的结果集不能用作输入参数的存储过程。  
  
  使用单独的连接执行复合操作中的每个操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]在复合操作中，操作数量作为使用 ODP.NET 连接池中的任意多个连接，并获取在执行操作，然后释放连接。 但是，如果在复合操作的操作返回结果集，使用消息之后才释放该连接。  
  
> [!IMPORTANT]
>  如果你在执行复合操作时遇到超时问题，则可能是因为连接数低于在复合操作涉及的操作的数目：  
> 
> - 存储的过程包含 BFILE、 BLOB、 CLOB、 NCLOB、 和 REF CURSOR 作为 OUT 或 IN OUT 参数。  
>   -   选择操作。  
> 
>   若要解决此问题，必须确保，如果有此类操作的复合运算中的"n"数，指定的值**MinPoolSize**绑定属性是"n + 1"或更高版本。 有关详细信息**MinPoolSize**绑定属性，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
 有关信息：  
  
- 如何执行中的复合操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[使用 BizTalk Server 的 Oracle 数据库上运行复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)。  
  
- 消息复合操作的架构，请参见[复合操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)。  
  
> [!NOTE]
>  此外可以设置中的复合操作的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 它是必需的接口表或界面视图上执行的任何复合操作中的操作将复合操作的应用程序上下文。 有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
## <a name="see-also"></a>请参阅  
 [Oracle E-business Suite 适配器支持哪些操作](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)