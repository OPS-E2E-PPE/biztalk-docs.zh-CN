---
title: 使用 BizTalk Server 轮询 Oracle E-business Suite |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a22b99a5-1715-4351-b0e0-6b8dcfacd9eb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9b5d0743d39dfcf6cbab7e1da20a8a3fb1382fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218005"
---
# <a name="poll-oracle-e-business-suite-using-biztalk-server"></a>使用 BizTalk Server 轮询 Oracle E-business Suite
你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]从 Oracle 数据库接收基于轮询的消息。 适配器提供轮询 Oracle 数据库的两种的方法：  
  
-   **使用 SELECT 语句**。 你可以指定一个简单的 SELECT 语句来轮询 Oracle 数据库。 适配器执行 SELECT 语句指定时间间隔，并将结果返回给适配器客户端。  
  
-   **使用存储的过程**。 你可以指定要轮询的 Oracle 数据库的存储的过程。 适配器在指定的时间间隔执行存储的过程，并将结果返回给适配器客户端。  
  
 在两个方法中的关键区别是方式适配器客户端指定适配器使用来轮询 Oracle 数据库的轮询语句。 第一种方法的轮询语句时简单的 SELECT 语句，用于存储的过程方法的轮询语句是在执行存储的过程的请求消息。 适配器客户端为指定的轮询语句，这两种方法， **PollingInput**绑定属性。 有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
 本部分中的主题提供有关如何轮询使用 SELECT 语句和存储的过程的说明。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 SELECT 语句的轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)  
  
-   [使用存储的过程的轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures.md)  
  
## <a name="see-also"></a>另请参阅  
[开发使用 Oracle E-business Suite 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)