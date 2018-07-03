---
title: 使用 Oracle 数据库适配器处理事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 971c2fba-640c-4ae5-9ab3-2d8227c1627d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94914c2f0f7bde91ea55032048e30232af60d02
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970702"
---
# <a name="handle-transactions-with-the-oracle-database-adapter"></a>使用 Oracle 数据库适配器处理事务
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] 并不会启动事务时 Oracle 数据库上执行操作。 相反，适配器执行的操作提供的适配器客户端的事务上下文。 若要执行操作在事务中使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，您必须：  
  
-   启用适配器客户端中的事务。 例如，若要启用 BizTalk Server 中的事务，必须选择**使用事务**中的复选框**事务**区域**消息**WCF 自定义选项卡或Wcf-oracledb 端口。  
  
-   设置的值**UseAmbientTransaction**属性绑定到**True**在适配器中。 有关绑定属性的详细信息，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。  
  
> [!IMPORTANT]
>  若要使用该适配器来执行对 Oracle 数据库的事务，您必须安装**Microsoft Transaction Server 的 Oracle 服务**组件，同时运行适配器的计算机上安装 Oracle 客户端，客户端。  
  
## <a name="transactions-in-the-outbound-operations"></a>出站操作中的事务  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在单个事务中执行的出站操作。 复合操作的所有操作都均在单个事务，但使用不同的 ODP.NET 连接。 有关显示的出站操作详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[原理适配器面 Oracle 元数据？](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)。  
  
## <a name="transactions-in-the-inbound-operations"></a>入站操作中的事务  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开以下两个入站的操作：  
  
- **轮询**： 轮询语句和轮询后语句 （如果指定） 的执行在事务中，而轮询的数据可用语句在不同事务中执行。 同样，轮询语句和轮询后语句的执行使用相同的 ODP.NET 连接，而使用不同的 ODP.NET 连接执行轮询的数据可用语句。  
  
- **通知**： 在使用单个 ODP.NET 连接的事务中执行通知操作。  
  
  有关显示的入站操作详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[原理适配器面 Oracle 元数据？](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)。  
  
## <a name="see-also"></a>请参阅  
 [用于 Oracle 数据库的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)