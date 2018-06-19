---
title: 支持复合 Operations2 |Microsoft 文档
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
ms.openlocfilehash: 5766adec70c1a1fe7eaabe4ffaf07499e33d210c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216437"
---
# <a name="support-for-composite-operations"></a>对复合操作的支持
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]允许适配器客户端执行可以包含任意数量的以下操作，并按任何顺序的复合操作：  
  
-   选择、 插入、 更新和删除接口表和数据库表上的操作。  
  
-   选择接口视图和数据库视图上的操作。  
  
-   存储的过程、 函数和作为适配器中的操作中加以表示的包内的过程。  
  
 中的同一个数据库或不同的数据库表和视图，可以面向的复合运算中的操作。 但是，不能共享数据或将其在不同的操作中的复合运算间重复使用。 例如，在复合操作中，选择操作的结果集不能作为输入参数为存储过程。  
  
 复合操作中的每个操作是使用单独的连接执行的。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]在复合操作中，操作的数目与占用 ODP.NET 连接池中的任意多个连接，然后释放连接，获取在执行操作。 但是，如果该复合操作中的操作返回的结果集，在处理消息之后才释放连接。  
  
> [!IMPORTANT]
>  如果您在执行复合操作时遇到超时问题，则可能是因为连接数低于在复合操作涉及的操作的数目：  
>   
>  -   缩小为包含 BFILE、 BLOB、 CLOB、 NCLOB、 和 REF CURSOR 的存储的过程或 IN OUT 参数。  
> -   选择操作。  
>   
>  若要解决此问题，你必须确保，如果没有此类操作复合操作中的"n"数目，指定的值**MinPoolSize**绑定属性为"n + 1"或更高版本。 有关详细信息**MinPoolSize**绑定属性，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
 有关的信息：  
  
-   如何执行中的复合操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[使用 BizTalk Server 的 Oracle 数据库上运行复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)。  
  
-   消息复合操作的架构，请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)。  
  
> [!NOTE]
>  您还可以设置中的复合操作的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 它是一定要设置的复合操作的应用程序上下文，如果对接口表或接口视图执行的任何复合操作中的操作。 有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
## <a name="see-also"></a>另请参阅  
 [Oracle E-business Suite 适配器支持何种操作](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)