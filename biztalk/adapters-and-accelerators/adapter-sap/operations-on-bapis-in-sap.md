---
title: 在 SAP 中的 Bapi 的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI, operations
- BAPIs, operations on
- Business Application Programming Interface
- BAPIs
- BAPI, transactions
- BAPI transactions, limitations on
ms.assetid: 6be26641-e8d3-4e11-8d82-4fdb13076580
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a319626f23b825187d65e01d687be5a1079df53a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993166"
---
# <a name="operations-on-bapis-in-sap"></a>在 SAP 中的 Bapi 的操作
业务应用程序编程接口 (BAPI) 是一种方法可以调用外部进程的 SAP 业务对象。 Bapi 是 SAP 系统上事务性的。  
  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] BAPI 调用中的出站方向的支持。 它会显示 Bapi 出以下两种方式：  
  
- **作为 RFC**。 您可以直接通过调用合适的 RFC 调用 BAPI。  
  
- **作为业务对象方法**。 适配器为方便起见，以帮助您在使用时检索元数据作为业务对象方法显示 Bapi[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。  
  
> [!IMPORTANT]
>  为 RFC 或业务对象; 方法，可以调用在适配器上 BAPI但无论调用在适配器上的 BAPI 的方式，它始终在 SAP BAPI 通过调用 RFC 接口。  
  
 适配器支持 BAPI 事务。 在 SAP BAPI 事务模型使用户能够将多个 Bapi 组合成一个逻辑工作单元中 (LUW)。 SAP LUW 包含的所有事务，包括更新数据库中所涉及的步骤。  
  
 在本部分中的主题说明如何 Bapi 作为业务对象和适配器如何支持 BAPI 事务 (LUWs)。  
 
  
## <a name="bapi-operations-as-business-object-methods"></a>BAPI 操作 （作为业务对象方法）  
 适配器作为业务对象方法，为方便起见，以帮助您在使用时检索元数据显示 Bapi[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 适配器始终使用 RFC 接口在 SAP 系统上调用 Bapi。  
  
 适配器的名称作为相应的业务对象下的出站操作的操作的图面 Bapi。 业务对象收集的功能组适配器的 BAPI 类别节点下。 (您可以浏览或搜索业务对象和下的 Bapi **BAPI**当你使用的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。)  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Bapi 上支持以下各项：  
  
- 导入参数  
  
- 导出参数  
  
- 更改参数  
  
- 表参数  
  
  有关消息结构和用于 Bapi 作为业务对象方法的 SOAP 操作的详细信息，请参阅[BAPI 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)。  
  
## <a name="bapi-transactions"></a>BAPI 事务  
 当您调用 BAPI 时，它始终是 LUW 上的 SAP 系统的一部分。 是否为 RFC 或业务对象的方法调用 BAPI 也是如此。 RFC SDK 将处理同一连接上的 SAP 相同 LUW 的一部分发送的所有 Bapi。 若要提交或回滚该事务的连接上调用后, 通过连接发送下一步 BAPI 开始新 LUW。  
  
 您调用 BAPI_TRANSACTION_COMMIT 或 BAPI_TRANSACTION_ROLLBACK 提交或回滚事务。 该适配器显示这些两个 Bapi:  
  
- 在作为 RFC 操作的基础节点。  
  
- 在每个业务对象。  
  
  通过确保所有发送同一连接上的 SAP （包括提交或回滚该事务的调用） 来控制在事务中的 Bapi。 可以执行此操作：  
  
- 通过使用 BizTalk 解决方案**ConnectionState**消息上下文属性以确保在事务中的 Bapi 会发送使用相同的连接。 此属性显示的适配器，您提供显式控制用于在 BizTalk 业务流程中发送一条消息的连接。  
  
   用于执行使用 BizTalk Server 的 BAPI 事务[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持以下消息上下文属性。  
  
  |字段|Description|  
  |-----------|-----------------|  
  |OPEN|打开事务的新通道。|  
  |重复使用|重复使用的事务的现有通道。|  
  |CLOSE|提交事务，然后关闭现有通道。|  
  |ABORT|中止事务，并关闭现有通道。|  
  
   有关详细信息，请参阅[SAP 使用 BizTalk Server 中运行 BAPI 事务](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)。  
  
  > [!NOTE]
  >  请确保您设置**EnableBizTalkCompatibilityMode**时执行事务使用 BizTalk Server 绑定属性。  
  
- 通过确保在事务中的 Bapi 都使用同一个 WCF 客户端发送的 WCF 服务模型解决方案。 有关详细信息，请参阅[调用中使用 WCF 服务模型的 SAP 的 Bapi](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)。  
  
- WCF 通道模型的解决方案通过确保在事务中的 Bapi 发送通过相同的 WCF 通道。 有关详细信息，请参阅[开发应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)。  
  
### <a name="limitations-on-bapi-transactions"></a>BAPI 事务的限制  
 以下限制适用于 BAPI 事务：  
  
- 不能使一个 LUW 内的相同实例上的两个写访问。 例如，不能创建订单，并在同一事务中更新。  
  
- 当执行 BAPI 事务使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须通过单个主机实例的发送端口发送的所有消息。  
  
- 如果实例是创建、 更新或删除通过使用写入 BAPI，读取 BAPI 写入 BAPI 操作已提交之前无法查看最新数据。  
  
- 调用 LUW 的外部客户端应在相同的 SAP 连接上调用 LUW 包含的所有 Bapi。  
  
> [!IMPORTANT]
>  属于版本 3.1 的 Bapi 调用 COMMIT WORK 作为其实现的一部分。 这意味着，这些 Bapi 不能包含其他 Bapi 中 LUW （因为它们将提交事务）。 有关详细信息，请参阅 SAP 文档。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)