---
title: "对 tRFCs SAP 中的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e60465716931161e9b9949e16c4630d85c2cfe2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-trfcs-in-sap"></a>对 tRFCs SAP 中的操作
事务 Rfc (tRFCs) 是工作的调用 (LUW) 逻辑单元的一部分的 Rfc。 在 SAP 系统上，LUW 包含所有完成的业务或编程任务所需的步骤。 TRFC 表示一种调用 RFC;它不是一个唯一的 SAP 项目。  
  
 你可以使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]tRFC 客户端，而且作为 tRFC 服务器。  
  
-   **作为 tRFC 客户端**，适配器使应用程序以调用在 SAP 系统上 LUW 单个 RFC。 这可保证 RFC 一次性仅的执行。 它并不意味着事务行为。  
  
-   **为 tRFC 服务器**，该适配器可用于接收 LUW 内的多个 Rfc。 适配器支持事务的上下文; 中的入站的 tRFC 调用这就是提交，并且支持汇总后行为。  
  
## <a name="trfc-operations"></a>tRFC 操作  
 TRFC 表示一种调用 RFC;它不是一个单独的 SAP 项目。 因此，SAP 系统 （为其适配器可以检索元数据） 上的每个 RFC 还呈现为通过 tRFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 tRFCs 中加以表示按 RFC 名称作为 TRFC 元数据类别节点下的操作。 (你可以浏览或搜索在 tRFCs **TRFC**节点使用时[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。)  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]上 tRFCs 支持以下：  
  
-   导入参数  
  
-   更改的参数 （支持仅更改参数的输入的端）  
  
> [!NOTE]
>  以便为其不返回任何输出值 （导出或更改参数），将以异步方式执行 tRFCs。  
  
 GUID 参数显示通过 tRFC 操作的适配器中。 此 GUID 映射到 SAP 事务 ID (TID) 与 tRFC 的适配器。 你可以使用此 GUID 参数为：  
  
-   确认 tRFC tRFC 客户端调用中的 SAP 系统上。 通过调用 RfcConfirmTransId 操作执行此操作。 这是特殊操作显示要确认 TID SAP 系统上的适配器。  
  
-   获取实际用于从 tRFC 客户端和 tRFC 服务器方案中的适配器 tRFC 的 SAP TID。 通过调用 SAP 的实用工具方法，ConvertGuidToTid 执行此操作。  
  
 有关这些操作的详细信息，请参阅[特殊操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)。 有关消息结构和用于 tRFCs 适配器的 SOAP 操作的详细信息，请参阅[trfc 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)。  
  
## <a name="invoking-transactional-rfcs-in-an-sap-system"></a>调用中某个 SAP 系统的事务性 Rfc  
 通常情况下，使用 tRFCs 来执行单个 LUW; 内的一个或多个 RFC 调用但是，由于在 SAP RFC SDK 中，限制[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持仅每 LUW 单个 tRFC。 为此，适配器会创建每个 tRFC LUW (SAP TID)。 对于此类客户端，SAP 作为一种机制来确保在"一次性"执行 RFC 定义 LUW，并不意味着提交和基于回滚的事务。  
  
 以下步骤总结了在 RFC 客户端调用使用执行的任务[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 由适配器客户端上，执行这些步骤中的一部分，并且一些执行适配器。  
  
1.  适配器客户端发送 tRFC 操作的请求消息。 适配器客户端可以根据需要提供此消息中的 GUID。  
  
2.  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接收请求消息，并使用 RFC SDK 以获取从 SAP 系统的事务 ID (TID)。 如果请求消息中包含一个 GUID，该适配器将此 GUID 映射到 SAP TID;否则为该适配器创建新的 GUID，并将其映射到 SAP TID  
  
3.  适配器使用 TID 进行 tRFC 调用到 SAP 服务器。 TID 的状态标记为**已完成**SAP 系统上。  
  
4.  适配器到适配器客户端的响应消息中返回的 GUID （即映射到 TID）。  
  
5.  适配器客户端时，将调用该适配器上的 RfcConfirmTransID 操作替换为上一步骤返回的 GUID。  
  
6.  适配器使用 RfcConfirmTransID 请求消息中的 GUID 来标识 SAP TID，并确认 SAP 系统的 tRFC 调用。 这将导致要从其数据库中删除 TID 条目的 SAP 服务器。  
  
> [!NOTE]
>  tRFC 客户端调用不返回导出或更改参数。  
  
 有关详细信息：  
  
-   调用 tRFC 使用 BizTalk Server 中，请参阅[调用 SAP 使用 BizTalk Server 中的 tRFCs](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)。  
  
-   调用 tRFC 使用 WCF 服务模型时，请参阅[调用中使用 WCF 服务模型的 SAP tRFCs](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)。  
  
-   消息结构和用于调用 tRFC SOAP 操作，请参阅[trfc 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)。  
  
## <a name="receiving-inbound-transactional-rfc-calls-from-an-sap-system"></a>从 SAP 系统的接收入站事务 RFC 调用  
 可以将用作 tRFC 服务器适配器从 SAP 接收 tRFCs。 为 tRFC 服务器，当适配器收到 tRFC，它将调用你的应用程序上的相应 tRFC 操作。 当它充当 tRFC 服务器时，该适配器将支持以下功能：  
  
-   （由 SAP TID 标识） LUW 可以包含多个 tRFCs （RFC 调用）。  
  
-   适配器创建为每个 SAP TID 可提交的事务。 应用程序代码可以在此事务中登记。  
  
-   支持提交和回滚。  
  
 本部分的其余部分提供有关将适配器用作 tRFC 服务器的常规信息。 有关详细信息：  
  
-   接收入站的 tRFC 呼叫，使用 BizTalk Server 中，请参阅[接收入站 tRFC 来自 SAP 使用 BizTalk Server 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)。  
  
-   接收入站的 tRFC 呼叫，使用 WCF 服务模型，请参阅[接收入站 tRFC 调用中使用 WCF 服务模型的 SAP](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)。  
  
### <a name="the-tid-database"></a>TID 数据库  
 适配器时它充当 tRFC 服务器时，使用 SQL Server 数据库 — TID 数据库-管理事务收到来自 SAP 系统的 Id。 例如，它使用 TID 数据库来帮助管理呼叫从 SAP 系统以提交、 回滚，并确认 TID。 适配器还存储它会创建并将与 TID 数据库中每个 SAP TID 相关联的 GUID。  
  
### <a name="prerequisites"></a>先决条件  
 对于作为 tRFC 服务器运行的适配器，必须确保在以下情况成立：  
  
-   RFC 必须声明 SAP 系统上。 这是因此该适配器可以检索元数据描述从 SAP 系统的 RFC。 RFC 实际是在你的应用程序中实现的。  
  
-   适配器必须注册上的 SAP 网关的 RFC 目标。 注册基于逻辑名称称为程序 id。 提供连接 URI 指定的程序 ID 中的参数 SAP 网关和此注册的 SAP 服务器。  
  
-   必须在 SQL Server 中创建 TID 数据库。 若要执行此操作，必须运行安装程序安装的 SQL 脚本。 SQL 脚本通常安装在\<安装驱动器 >: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[安装 BizTalk 适配器包](http://msdn.microsoft.com/library/2ae27db5-b11b-42c3-a568-e2331badf80e)。  
  
-   **TidDatabaseConnectionString**绑定属性必须设置为 TID 数据库的 SQL 数据库连接字符串。 有关详细信息**TidDatabaseConnectionString**绑定属性，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
> [!NOTE]
>  设置**TidDatabaseConnectionString**绑定属性配置的适配器以充当 tRFC 服务器，而不是 RFC 服务器。 如果**TidDatabaseConnectionString**绑定属性设置和连接 URI 中指定的 RFC 目标，该适配器可作为 tRFC 服务器对于 RFC 目标中的传入调用。 如果未设置此绑定属性，该适配器将充当 RFC 服务器。  
  
### <a name="how-the-adapter-processes-inbound-trfcs"></a>如何适配器进程入站 tRFCs  
 以下步骤总结了 RFC 客户端调用使用执行的任务[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 由适配器客户端上，执行这些步骤中的一部分，并且一些执行适配器。  
  
1.  已用于插入适配器的 SAP 系统调用，以查询是否 TID。 适配器返回对 SAP 系统的相应响应。 如果新 TID，该适配器将创建可提交的事务。 此事务用于以事务性方式保留到 TID 数据库 TID，当 SAP 程序执行提交 （提交工作）。 它还公开对处理入站的 tRFCs 的应用程序代码。 此外，适配器会创建一个 GUID，它将与 SAP TID 相关联。  
  
2.  SAP 系统会将一个或多个事务 Rfc 发送到适配器中。 为每个 tRFC 适配器时，将调用你的应用程序上的相应 tRFC 操作。 适配器将向每个操作应用程序的步骤 1 中创建的事务流动。 适配器传递操作的请求消息中的步骤 1 中创建的 GUID。  
  
3.  SAP 系统会将提交 LUW （提交工作）。 适配器尝试提交与 SAP TID （步骤 1 中创建） 关联的事务。  
  
    1.  如果任何步骤 2 中的调用，该事务已中止 （由你的应用程序），当适配器尝试提交事务时就会出错。 向 SAP 返回的错误。 转到步骤 4。  
  
    2.  如果提交成功，则 TID 现在是 TID 数据库中。 转到步骤 5。  
  
4.  如果错误发生在步骤 3，或如果 SAP 回滚 LUW (RESTART_OF_BACKGROUNDTASK) 而不是提交它，该适配器回滚事务。 在这种情况下 TID 将永远不会保留到 TID 数据库。  
  
5.  SAP 系统确认 TID。 适配器 TID 从数据库中删除 TID （假设步骤 3 已成功完成并 TID TID 数据库中存在。  
  
> [!NOTE]
>  如果尝试连接到 TID 数据库在 tRFC 服务器操作期间发生错误，错误代码指示来自 SAP 的传入调用未处理[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]返回到 SAP。  
  
### <a name="receiving-idocs-as-a-trfc-server"></a>为 tRFC 服务器接收到的 Idoc  
 你使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]RFC 服务器或 tRFC 服务器以接收到的 Idoc 从 SAP 系统。 在任一情况下，你必须设置**ReceiveIdocFormat**绑定属性，以指定在其中适配器应发出到你的应用程序的 IDOC 数据的格式。 有关与适配器接收到的 Idoc 的详细信息，请参阅[SAP 中的 Idoc 上的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。 有关详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定属性，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
## <a name="special-trfc-operations"></a>特殊 tRFC 操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还可以执行某些 SAP 系统上的特殊 tRFC 操作。 此类的一个操作是 RfcConfirmTransID。  
  
-   **RfcConfirmTransID。** 在调用此操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以确认 tRFC 到 SAP 服务器所做的调用。 RfcConfirmTransID 可能需要在其中使用该适配器将 Idoc 发送到与 tRFC 的 SAP 服务器的情况下。 操作都可用下**TRFC**节点时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
 有关消息结构和 RfcConfirmTransID 操作的 SOAP 操作的详细信息，请参阅[trfc 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)。  
  
## <a name="see-also"></a>另请参阅  
 [连接到 SAP 系统使用适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)