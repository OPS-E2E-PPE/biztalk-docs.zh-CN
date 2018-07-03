---
title: 在 SAP 中 Trfc 的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFCs, invoking transactional RFCs in an SAP System
- TID database
- transactional RFCs
- tRFCs, receiving inbound iransactional RFC calls from an SAP system
- tRFCs
- GUID parameter
- RFCs, processing inbound
- RfcConfirmTransID
- transaction ID (TID)
- tRFC Operations
- IDOCS, receiving IDOCs as a tRFC server
- adapters, operations on tRFCs
- RFC, invoking an RFC
ms.assetid: d6a5c515-d6aa-4b70-9c23-32d1dd94d473
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b99822d838f0681cf9a6ce336ed1a23f4088c659
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996134"
---
# <a name="operations-on-trfcs-in-sap"></a>在 SAP 中 Trfc 的操作
事务 Rfc (Trfc) 是工作的作为一个逻辑单元 (LUW) 的一部分调用的 Rfc。 在 SAP 系统中，LUW 包含所有完成的业务或编程任务所需的步骤。 TRFC 表示一种方法调用 RFC;它不是唯一的 SAP 项目。  
  
 可以使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]作为 tRFC 客户端和 tRFC 服务器。  
  
-   **TRFC 客户端作为**，适配器可以调用 LUW 上的 SAP 系统中单个 RFC 让应用程序。 这可以保证 RFC 的一次性唯一的执行。 它并不意味着事务行为。  
  
-   **为 tRFC 服务器**，适配器可接收多个 Rfc LUW 内的。 适配器在事务性上下文中; 支持入站的 tRFC 调用这就是提交，且支持汇总后行为。  
  
## <a name="trfc-operations"></a>tRFC 操作  
 TRFC 意味着一种方法调用 RFC;它不是单独的 SAP 项目。 因此，每个 SAP 系统 （为其适配器可以检索元数据） 上的 RFC 也可作为通过 tRFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 Trfc 按 RFC 名称显示为 TRFC 元数据类别节点下的操作。 (您可以浏览或搜索下 Trfc **TRFC**当你使用的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。)  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Trfc 上支持以下各项：  
  
-   导入参数  
  
-   更改的参数 （支持仅更改参数在输入的端）  
  
> [!NOTE]
>  Trfc 是以异步方式执行，因此为其不返回任何输出值 （导出或更改参数）。  
  
 GUID 参数显示的用于 tRFC 操作的适配器。 此 GUID 映射到 SAP 事务 ID (TID) 与 tRFC 关联的适配器。 可以使用此 GUID 参数为：  
  
- 确认 tRFC tRFC 客户端调用中的 SAP 系统上。 通过调用 RfcConfirmTransId 操作执行此操作。 这是由适配器以确认 TID SAP 系统上的特殊操作。  
  
- 获取用于从 tRFC 客户端和 tRFC 服务器方案中适配器 tRFC 实际 SAP TID。 通过调用 SAP 实用工具方法，ConvertGuidToTid 执行此操作。  
  
  有关这些操作的详细信息，请参阅[特殊操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)。 有关消息结构和 SOAP 适配器使用 Trfc 的操作的详细信息，请参阅[tRFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)。  
  
## <a name="invoking-transactional-rfcs-in-an-sap-system"></a>SAP 系统中调用事务 Rfc  
 Trfc 通常情况下，用于执行单个 LUW; 内的一个或多个 RFC 调用但是，由于 SAP RFC SDK 中的限制[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持仅每 LUW 单一 tRFC。 出于此原因，适配器会创建每个 tRFC LUW (SAP TID)。 对于此类客户端，SAP 作为一种机制来保证"一次性"执行 RFC 定义 LUW 并不意味着提交和回滚基于事务。  
  
 以下步骤总结了在使用 RFC 客户端调用中执行的任务[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 其中某些步骤由执行适配器客户端，并且一些执行适配器。  
  
1. 适配器客户端发送 tRFC 操作的请求消息。 适配器客户端可以根据需要提供此消息中的 GUID。  
  
2. [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接收请求消息，并使用 RFC SDK 以获取来自 SAP 系统的事务 ID (TID)。 如果请求消息中包含一个 GUID，该适配器会将此 GUID 映射到 SAP TID;否则为适配器创建新的 GUID 并将其映射到 SAP TID  
  
3. 适配器使用 TID 进行 tRFC 调用到 SAP 服务器。 TID 状态标记为**已完成**SAP 系统上。  
  
4. 适配器返回到适配器客户端的响应消息中的 GUID (映射到 TID）。  
  
5. 适配器客户端使用在上一步中返回的 GUID 调用 RfcConfirmTransID 操作在适配器上。  
  
6. 适配器 RfcConfirmTransID 请求消息中使用 GUID 来标识 SAP TID，并确认上的 SAP 系统的 tRFC 调用。 这将导致从其数据库中删除的 TID 条目将 SAP 服务器。  
  
> [!NOTE]
>  tRFC 客户端调用不会返回导出或更改参数。  
  
 有关详细信息：  
  
-   调用 tRFC 使用 BizTalk Server 中，请参阅[调用中使用 BizTalk Server 的 SAP Trfc](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)。  
  
-   调用 tRFC 使用 WCF 服务模型，请参阅[调用中使用 WCF 服务模型的 SAP Trfc](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)。  
  
-   消息结构和用于调用 tRFC SOAP 操作，请参见[tRFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)。  
  
## <a name="receiving-inbound-transactional-rfc-calls-from-an-sap-system"></a>接收来自 SAP 系统的入站事务 RFC 调用  
 可以为 tRFC 服务器使用适配器从 SAP 接收 Trfc。 为 tRFC 服务器，适配器接收 tRFC 时它将调用你的应用程序上的相应 tRFC 操作。 充当 tRFC 服务器时，适配器将支持以下功能：  
  
- LUW （由 SAP TID 标识） 可以包含多个 Trfc （RFC 调用）。  
  
- 适配器为每个 SAP TID 创建可提交的事务。 应用程序代码可以在此事务中登记。  
  
- 支持提交和回滚。  
  
  本部分的其余部分提供了有关为 tRFC 服务器使用的适配器的一般信息。 有关更多具体信息：  
  
- 接收入站的 tRFC 的呼叫，使用 BizTalk Server 中，请参阅[接收入站 tRFC 调用从 SAP 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)。  
  
- 接收入站的 tRFC 的呼叫，使用 WCF 服务模型，请参阅[接收入站 tRFC 调用中使用 WCF 服务模型的 SAP](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)。  
  
### <a name="the-tid-database"></a>TID 数据库  
 当它充当 tRFC 服务器时，则适配器将使用 SQL Server 数据库 — TID 数据库 — 管理事务接收来自 SAP 系统的 Id。 例如，它使用 TID 数据库来帮助管理呼叫从 SAP 系统以提交、 回滚，并确认 TID。 适配器还将存储它会创建并将每个 SAP TID TID 数据库中与相关联的 GUID。  
  
### <a name="prerequisites"></a>必要條件  
 对于作为 tRFC 服务器运行的适配器，必须确保在以下情况成立：  
  
- RFC 必须声明上的 SAP 系统。 这是因此适配器可以检索描述从 SAP 系统的 RFC 的元数据。 在你的应用程序中实际实现 RFC。  
  
- 适配器必须注册 SAP 网关上的 RFC 目标。 注册基于逻辑名称称为程序 id。 提供参数的连接 URI 指定的程序 ID，SAP 网关和此注册的 SAP 服务器。  
  
- 必须在 SQL Server 中创建的 TID 数据库。 若要执行此操作，必须运行安装程序安装的 SQL 脚本。 SQL 脚本通常安装在\<安装驱动器\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[安装 BizTalk 适配器包](http://msdn.microsoft.com/library/2ae27db5-b11b-42c3-a568-e2331badf80e)。  
  
- **TidDatabaseConnectionString**绑定属性必须设置为 TID 数据库的 SQL 数据库连接字符串。 有关详细信息**TidDatabaseConnectionString**绑定属性，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
> [!NOTE]
>  设置**TidDatabaseConnectionString**属性绑定配置进行操作为 tRFC 服务器而不是 RFC 服务器的适配器。 如果**TidDatabaseConnectionString**属性绑定设置和连接 URI 中指定的 RFC 目标，适配器可充当 RFC 目标从传入的调用 tRFC 服务器。 如果未设置此绑定属性，适配器可充当 RFC 服务器。  
  
### <a name="how-the-adapter-processes-inbound-trfcs"></a>如何适配器进程的入站 Trfc  
 以下步骤总结了由 RFC 客户端调用使用执行的任务[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 其中某些步骤由执行适配器客户端，并且一些执行适配器。  
  
1.  已使用到适配器的 SAP 系统调用 enquire 是否是 TID。 适配器返回到 SAP 系统的相应响应。 如果新 TID，适配器会创建可提交的事务。 使用此事务将以事务性方式保留到 TID 数据库 TID，当 SAP 程序执行提交 （提交工作）。 它还公开给处理入站的 Trfc 的应用程序代码。 此外，适配器会创建一个 GUID，它将与 SAP TID 相关联。  
  
2.  SAP 系统发送到适配器的一个或多个事务的 Rfc。 为每个 tRFC，适配器调用你的应用程序上的相应 tRFC 操作。 适配器将向每个操作应用程序的步骤 1 中创建的事务流动。 适配器将传递在步骤 1 中为该操作的请求消息创建的 GUID。  
  
3.  SAP 系统提交 LUW (COMMIT WORK)。 适配器尝试提交事务与 SAP TID （步骤 1 中创建） 相关联。  
  
    1.  如果任何调用在步骤 2 中，该事务已中止 （由你的应用程序），当适配器尝试提交事务时就会出错。 向 SAP 返回的错误。 转到步骤 4。  
  
    2.  如果提交成功，TID 现 TID 数据库中。 转到步骤 5。  
  
4.  如果错误出现在步骤 3，或如果 SAP 回滚 LUW (RESTART_OF_BACKGROUNDTASK) 而不是提交它，该适配器回滚该事务。 在这种情况下 TID 将永远不会保留到 TID 数据库。  
  
5.  SAP 系统将确认 TID。 适配器删除 TID 从 TID 数据库 （假设步骤 3 已成功完成且 TID TID 数据库中存在。  
  
> [!NOTE]
>  如果尝试连接到 TID 数据库 tRFC 服务器操作过程中发生错误，错误代码，指示来自 SAP 的传入调用未处理[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]返回到 SAP。  
  
### <a name="receiving-idocs-as-a-trfc-server"></a>为 tRFC 服务器接收 Idoc  
 您使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为 RFC 服务器或 tRFC 服务器用于从 SAP 系统接收 Idoc。 在任一情况下，必须设置**ReceiveIdocFormat**绑定属性来指定在其中适配器应将 IDOC 数据发送给你的应用程序的格式。 有关使用适配器接收 Idoc 的详细信息，请参阅[sap 的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。 有关详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定属性，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
## <a name="special-trfc-operations"></a>特殊 tRFC 操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还可以执行某些特殊 tRFC 操作上的 SAP 系统。 一个此类操作，RfcConfirmTransID。  
  
- **RfcConfirmTransID。** 在调用此操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]确认 tRFC 调用到 SAP 服务器。 RfcConfirmTransID 可能需要在其中使用该适配器以将 Idoc 发送到 SAP 服务器作为 tRFC 的方案中。 该操作位于下**TRFC**节点时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
  有关消息结构和 RfcConfirmTransID 操作的 SOAP 操作的详细信息，请参阅[tRFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)。  
  
## <a name="see-also"></a>请参阅  
 [连接到 SAP 系统使用的适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)