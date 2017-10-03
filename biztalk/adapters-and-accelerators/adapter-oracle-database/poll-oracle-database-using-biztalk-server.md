---
title: "使用 BizTalk Server 轮询 Oracle 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c3aef30-956d-4585-b2de-7eebb919fab5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2578d00518a9f1632e690e84db04426575619109
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="poll-oracle-database-using-biztalk-server"></a>使用 BizTalk Server 轮询 Oracle 数据库
你可以配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]从 Oracle 数据库接收基于轮询的消息。 适配器提供轮询 Oracle 数据库的两种的方法：  
  
-   **使用 SELECT 语句**。 你可以指定要轮询的表和视图的 Oracle 数据库中的简单 SELECT 语句。 适配器执行 SELECT 语句指定时间间隔，并将结果返回给适配器客户端。  
  
-   **使用存储的过程、 函数或过程或函数在一个包内的**。 你可以指定存储的过程、 函数或过程或函数在包轮询 Oracle 数据库中。 适配器在指定的时间间隔执行的请求消息，并将结果返回给适配器客户端。  
  
 在两个方法中的关键区别是方式适配器客户端指定适配器使用来轮询 Oracle 数据库的轮询语句。 第一种方法的轮询语句时简单的 SELECT 语句，另一种方法的轮询语句将是执行存储的过程、 函数或过程或函数在一个包内的请求消息。 适配器客户端在指定的轮询语句，这两种方法， **PollingStatement**绑定属性。 有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  
  
 此部分中的主题提供有关如何轮询使用 SELECT 语句和存储的过程、 函数或过程的说明或函数在一个包内。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 SELECT 语句的轮询 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-the-select-statement.md)  
  
-   [使用存储的过程、 函数或打包的过程和函数的轮询 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-db-using-stored-procedures-functions-or-packaged-procedures.md)  
  
## <a name="see-also"></a>另请参阅  
[开发使用 Oracle 数据库适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)