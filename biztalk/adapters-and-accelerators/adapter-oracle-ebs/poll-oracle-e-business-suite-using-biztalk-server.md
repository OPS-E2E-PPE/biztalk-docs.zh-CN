---
title: 使用 BizTalk Server 轮询 Oracle E-business Suite |Microsoft Docs
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
ms.openlocfilehash: b8180b3b671c87b5dcd0d41477e20b6d175f1cce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974214"
---
# <a name="poll-oracle-e-business-suite-using-biztalk-server"></a>使用 BizTalk Server 轮询 Oracle E-business Suite
你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]从 Oracle 数据库接收基于轮询的消息。 适配器提供轮询 Oracle 数据库的两种的方法：  
  
- **使用 SELECT 语句**。 可以指定一个简单的 SELECT 语句来轮询 Oracle 数据库。 适配器执行 SELECT 语句指定的时间间隔，并将结果返回到适配器客户端。  
  
- **使用存储的过程**。 您可以指定用于轮询 Oracle 数据库的存储的过程。 适配器在指定的时间间隔执行存储的过程，并将结果返回到适配器客户端。  
  
  中的两种方法的主要区别是方式适配器客户端指定用于轮询 Oracle 数据库适配器的轮询语句。 简单的 SELECT 语句的轮询语句的第一种方法时，存储的过程方法的轮询语句是执行存储的过程的请求消息。 适配器客户端为指定的轮询语句，这两种方法， **PollingInput**属性绑定。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
  在本部分中的主题提供有关如何使用 SELECT 语句和存储的过程轮询的说明。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 SELECT 语句轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)  
  
-   [使用存储的过程轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures.md)  
  
## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)