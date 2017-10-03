---
title: "对 BAPIs SAP 中的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAPI, operations
- BAPIs, operations on
- Business Application Programming Interface
- BAPIs
- BAPI, transactions
- BAPI transactions, limitations on
ms.assetid: 6be26641-e8d3-4e11-8d82-4fdb13076580
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8504dd05c671307085d621c474969a70026d2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-bapis-in-sap"></a>对 BAPIs SAP 中的操作
业务应用程序编程接口 (BAPI) 是一种方法可以由外部进程的 SAP 业务对象。 BAPIs 是 SAP 系统上事务性的。  
  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] BAPI 调用中的出站方向的支持。 它会显示 BAPIs 出两种方式：  
  
-   **作为 RFC**。 你可以直接通过调用适当的 RFC 调用 BAPI。  
  
-   **为业务对象的方法**。 该适配器显示为业务对象的方法为方便起见，来帮助你检索元数据，当你使用的 BAPIs[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。  
  
> [!IMPORTANT]
>  你可以在作为 RFC 或业务对象; 方法调用在适配器上 BAPI但是，而不考虑如何在适配器上的 BAPI 调用时，它始终调用上 SAP BAPI 通过 RFC 界面。  
  
 适配器支持 BAPI 事务。 上 SAP 的 BAPI 事务模型使用户能够将多个 BAPIs 合并到一个逻辑工作单元中 (LUW)。 SAP LUW 包含包括更新的数据库事务中涉及的所有步骤。  
  
 本部分中的主题介绍如何 BAPIs 中加以表示作为业务对象以及如何将 BAPI 事务 (LUWs) 支持适配器。  
 
  
## <a name="bapi-operations-as-business-object-methods"></a>BAPI 操作 （作为业务对象方法）  
 业务为方便起见，来帮助你检索元数据，当你使用的对象的方法，该适配器呈现 BAPIs[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 适配器始终调用 BAPIs 上使用 RFC 接口的 SAP 系统。  
  
 适配器显示按名称中 BAPIs 设为适当的业务对象下的出站操作的操作。 适配器 BAPI 类别节点下的功能组收集的业务对象。 (你可以浏览或搜索业务对象和下的 BAPIs **BAPI**节点使用时[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。)  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]上 BAPIs 支持以下：  
  
-   导入参数  
  
-   导出参数  
  
-   更改参数  
  
-   表参数  
  
 有关消息结构和用于 BAPIs 作为业务对象方法的 SOAP 操作的详细信息，请参阅[BAPI 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)。  
  
## <a name="bapi-transactions"></a>BAPI 事务  
 在调用时 BAPI，它始终是 SAP 系统上 LUW 的一部分。 是否作为 RFC 或业务对象的一个方法调用 BAPI，也是如此。 RFC SDK 将通过相同的 SAP 连接同一 LUW 的一部分发送的所有 BAPIs。 若要提交或回滚事务的连接上调用后, 通过连接发送下一步 BAPI 开始新 LUW。  
  
 你调用 BAPI_TRANSACTION_COMMIT 或 BAPI_TRANSACTION_ROLLBACK 提交或回滚事务。 适配器呈现这些两个 BAPIs:  
  
-   在作为 RFC 操作的基础节点。  
  
-   在每个业务对象。  
  
 通过确保，它们将所有通过发送相同的 SAP 连接 （包括用于提交或回滚事务的调用） 控制 BAPIs 在事务中。 你可以执行此操作：  
  
-   使用 BizTalk 解决方案**ConnectionState**消息上下文属性，以确保在事务中的 BAPIs 会发送使用相同的连接。 此属性显示适配器，你提供显式控制用于将消息发送 BizTalk 业务流程中的连接。  
  
     来执行 BAPI 事务使用 BizTalk Server 中，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持以下消息上下文属性。  
  
    |字段|Description|  
    |-----------|-----------------|  
    |OPEN|将打开的事务的新通道。|  
    |重复使用|重复使用的事务的现有通道。|  
    |CLOSE|提交事务，然后关闭现有的通道。|  
    |中止|中止事务，并关闭的现有通道。|  
  
     有关详细信息，请参阅[SAP 使用 BizTalk Server 中运行 BAPI 事务](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)。  
  
    > [!NOTE]
    >  请确保你设置**EnableBizTalkCompatibilityMode**绑定属性时执行事务使用 BizTalk Server。  
  
-   通过确保在事务中的 BAPIs 都使用同一个 WCF 客户端发送的 WCF 服务模型解决方案。 有关详细信息，请参阅[SAP 使用 WCF 服务模型中调用 BAPIs](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)。  
  
-   WCF 通道模型解决方案通过确保在事务中的 BAPIs 通过相同的 WCF 通道发送。 有关详细信息，请参阅[开发应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)。  
  
### <a name="limitations-on-bapi-transactions"></a>BAPI 事务的限制  
 以下限制适用 BAPI 事务上：  
  
-   不能使在一个 LUW 内的同一实例上的两个写访问。 例如，不能创建订单，并在同一个事务中更新。  
  
-   当执行 BAPI 事务使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须通过发送端口的单个主机实例发送的所有消息。  
  
-   如果实例是创建、 更新或删除通过使用写入 BAPI，读取 BAPI 写入 BAPI 操作已提交之前无法查看最新数据。  
  
-   外部客户端调用 LUW 应调用 LUW 包含的所有 BAPIs 同一个 SAP 连接上。  
  
> [!IMPORTANT]
>  属于 3.1 版的 BAPIs 调用作为其实现的一部分提交的工作。 这意味着，（因为它们将提交该事务），这些 BAPIs 不能包含其他 BAPIs LUW 中。 有关详细信息，请参阅 SAP 文档。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)