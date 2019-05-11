---
title: 使用 BizTalk Server 轮询 Oracle 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c3aef30-956d-4585-b2de-7eebb919fab5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31a4a7d7afe372c6334219ec8cdf84a3e43aef65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376271"
---
# <a name="poll-oracle-database-using-biztalk-server"></a>使用 BizTalk Server 轮询 Oracle 数据库
你可以配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]从 Oracle 数据库接收基于轮询的消息。 适配器提供轮询 Oracle 数据库的两种的方法：  
  
- **使用 SELECT 语句**。 可以指定一个简单的 SELECT 语句来轮询的表和 Oracle 数据库中的视图。 适配器执行 SELECT 语句指定的时间间隔，并将结果返回到适配器客户端。  
  
- **使用存储的过程、 函数或过程或函数的包中**。 您可以指定存储的过程、 函数或过程或函数来轮询 Oracle 数据库的包中。 适配器在指定的时间间隔执行的请求消息并将结果返回到适配器客户端。  
  
  中的两种方法的主要区别是方式适配器客户端指定用于轮询 Oracle 数据库适配器的轮询语句。 简单的 SELECT 语句的轮询语句的第一种方法时，另一种方法的轮询语句是执行存储的过程、 函数或过程或函数的包中的请求消息。 适配器客户端在指定的轮询语句，这两种方法， **PollingStatement**属性绑定。 有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  
  
  在本部分中的主题说明了如何轮询使用 SELECT 语句和存储的过程、 函数或过程或函数的包中。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 SELECT 语句轮询 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-the-select-statement.md)  
  
-   [使用存储的过程、 函数或封装的过程和函数的轮询 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-db-using-stored-procedures-functions-or-packaged-procedures.md)  
  
## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序使用 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)