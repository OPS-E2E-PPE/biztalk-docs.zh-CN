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
# <a name="operations-on-bapis-in-sap"></a><span data-ttu-id="edcd3-102">在 SAP 中的 Bapi 的操作</span><span class="sxs-lookup"><span data-stu-id="edcd3-102">Operations on BAPIs in SAP</span></span>
<span data-ttu-id="edcd3-103">业务应用程序编程接口 (BAPI) 是一种方法可以调用外部进程的 SAP 业务对象。</span><span class="sxs-lookup"><span data-stu-id="edcd3-103">A Business Application Programming Interface (BAPI) is a method of a SAP business object that can be called by an external process.</span></span> <span data-ttu-id="edcd3-104">Bapi 是 SAP 系统上事务性的。</span><span class="sxs-lookup"><span data-stu-id="edcd3-104">BAPIs are transactional on the SAP system.</span></span>  
  
 <span data-ttu-id="edcd3-105">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] BAPI 调用中的出站方向的支持。</span><span class="sxs-lookup"><span data-stu-id="edcd3-105">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] supports BAPI calls in the outbound direction.</span></span> <span data-ttu-id="edcd3-106">它会显示 Bapi 出以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="edcd3-106">It surfaces BAPIs in two ways:</span></span>  
  
- <span data-ttu-id="edcd3-107">**作为 RFC**。</span><span class="sxs-lookup"><span data-stu-id="edcd3-107">**As an RFC**.</span></span> <span data-ttu-id="edcd3-108">您可以直接通过调用合适的 RFC 调用 BAPI。</span><span class="sxs-lookup"><span data-stu-id="edcd3-108">You can invoke a BAPI directly by invoking the appropriate RFC.</span></span>  
  
- <span data-ttu-id="edcd3-109">**作为业务对象方法**。</span><span class="sxs-lookup"><span data-stu-id="edcd3-109">**As methods of business objects**.</span></span> <span data-ttu-id="edcd3-110">适配器为方便起见，以帮助您在使用时检索元数据作为业务对象方法显示 Bapi[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="edcd3-110">The adapter surfaces BAPIs as methods of business objects as a convenience to help you retrieve metadata when you use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="edcd3-111">为 RFC 或业务对象; 方法，可以调用在适配器上 BAPI但无论调用在适配器上的 BAPI 的方式，它始终在 SAP BAPI 通过调用 RFC 接口。</span><span class="sxs-lookup"><span data-stu-id="edcd3-111">You can invoke a BAPI on the adapter as an RFC or as a method of a business object; but regardless of how you invoke the BAPI on the adapter, it always invokes the BAPI on SAP through the RFC interface.</span></span>  
  
 <span data-ttu-id="edcd3-112">适配器支持 BAPI 事务。</span><span class="sxs-lookup"><span data-stu-id="edcd3-112">The adapter supports BAPI transactions.</span></span> <span data-ttu-id="edcd3-113">在 SAP BAPI 事务模型使用户能够将多个 Bapi 组合成一个逻辑工作单元中 (LUW)。</span><span class="sxs-lookup"><span data-stu-id="edcd3-113">The BAPI transaction model on SAP enables users to combine several BAPIs into one logical unit of work (LUW).</span></span> <span data-ttu-id="edcd3-114">SAP LUW 包含的所有事务，包括更新数据库中所涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="edcd3-114">An SAP LUW consists of all the steps involved in a transaction including updating the database.</span></span>  
  
 <span data-ttu-id="edcd3-115">在本部分中的主题说明如何 Bapi 作为业务对象和适配器如何支持 BAPI 事务 (LUWs)。</span><span class="sxs-lookup"><span data-stu-id="edcd3-115">The topics in this section explain how BAPIs are surfaced as business objects and how BAPI transactions (LUWs) are supported by the adapter.</span></span>  
 
  
## <a name="bapi-operations-as-business-object-methods"></a><span data-ttu-id="edcd3-116">BAPI 操作 （作为业务对象方法）</span><span class="sxs-lookup"><span data-stu-id="edcd3-116">BAPI Operations (as Business Object Methods)</span></span>  
 <span data-ttu-id="edcd3-117">适配器作为业务对象方法，为方便起见，以帮助您在使用时检索元数据显示 Bapi[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="edcd3-117">The adapter surfaces BAPIs as business objects methods as a convenience to help you retrieve metadata when you use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="edcd3-118">适配器始终使用 RFC 接口在 SAP 系统上调用 Bapi。</span><span class="sxs-lookup"><span data-stu-id="edcd3-118">The adapter always invokes BAPIs on the SAP system using the RFC interface.</span></span>  
  
 <span data-ttu-id="edcd3-119">适配器的名称作为相应的业务对象下的出站操作的操作的图面 Bapi。</span><span class="sxs-lookup"><span data-stu-id="edcd3-119">The adapter surfaces BAPIs by name as operations under the appropriate business object for outbound operations.</span></span> <span data-ttu-id="edcd3-120">业务对象收集的功能组适配器的 BAPI 类别节点下。</span><span class="sxs-lookup"><span data-stu-id="edcd3-120">Business objects are collected by functional group under the BAPI category node by the adapter.</span></span> <span data-ttu-id="edcd3-121">(您可以浏览或搜索业务对象和下的 Bapi **BAPI**当你使用的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。)</span><span class="sxs-lookup"><span data-stu-id="edcd3-121">(You can browse or search for business objects and BAPIs under the **BAPI** node when you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)</span></span>  
  
 <span data-ttu-id="edcd3-122">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Bapi 上支持以下各项：</span><span class="sxs-lookup"><span data-stu-id="edcd3-122">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following on BAPIs:</span></span>  
  
- <span data-ttu-id="edcd3-123">导入参数</span><span class="sxs-lookup"><span data-stu-id="edcd3-123">IMPORT parameters</span></span>  
  
- <span data-ttu-id="edcd3-124">导出参数</span><span class="sxs-lookup"><span data-stu-id="edcd3-124">EXPORT parameters</span></span>  
  
- <span data-ttu-id="edcd3-125">更改参数</span><span class="sxs-lookup"><span data-stu-id="edcd3-125">CHANGING parameters</span></span>  
  
- <span data-ttu-id="edcd3-126">表参数</span><span class="sxs-lookup"><span data-stu-id="edcd3-126">Table parameters</span></span>  
  
  <span data-ttu-id="edcd3-127">有关消息结构和用于 Bapi 作为业务对象方法的 SOAP 操作的详细信息，请参阅[BAPI 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="edcd3-127">For more information about the message structures and SOAP actions used for BAPIs surfaced as business object methods, see [Message Schemas for BAPI Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md).</span></span>  
  
## <a name="bapi-transactions"></a><span data-ttu-id="edcd3-128">BAPI 事务</span><span class="sxs-lookup"><span data-stu-id="edcd3-128">BAPI Transactions</span></span>  
 <span data-ttu-id="edcd3-129">当您调用 BAPI 时，它始终是 LUW 上的 SAP 系统的一部分。</span><span class="sxs-lookup"><span data-stu-id="edcd3-129">When you invoke a BAPI, it is always part of an LUW on the SAP system.</span></span> <span data-ttu-id="edcd3-130">是否为 RFC 或业务对象的方法调用 BAPI 也是如此。</span><span class="sxs-lookup"><span data-stu-id="edcd3-130">This is true whether you invoke the BAPI as an RFC or as a method of a business object.</span></span> <span data-ttu-id="edcd3-131">RFC SDK 将处理同一连接上的 SAP 相同 LUW 的一部分发送的所有 Bapi。</span><span class="sxs-lookup"><span data-stu-id="edcd3-131">The RFC SDK treats all BAPIs sent over the same SAP connection as part of the same LUW.</span></span> <span data-ttu-id="edcd3-132">若要提交或回滚该事务的连接上调用后, 通过连接发送下一步 BAPI 开始新 LUW。</span><span class="sxs-lookup"><span data-stu-id="edcd3-132">After a call to commit or roll back the transaction on a connection, the next BAPI sent over the connection begins a new LUW.</span></span>  
  
 <span data-ttu-id="edcd3-133">您调用 BAPI_TRANSACTION_COMMIT 或 BAPI_TRANSACTION_ROLLBACK 提交或回滚事务。</span><span class="sxs-lookup"><span data-stu-id="edcd3-133">You call BAPI_TRANSACTION_COMMIT or BAPI_TRANSACTION_ROLLBACK to commit or roll back the transaction.</span></span> <span data-ttu-id="edcd3-134">该适配器显示这些两个 Bapi:</span><span class="sxs-lookup"><span data-stu-id="edcd3-134">The adapter surfaces these two BAPIs:</span></span>  
  
- <span data-ttu-id="edcd3-135">在作为 RFC 操作的基础节点。</span><span class="sxs-lookup"><span data-stu-id="edcd3-135">Under the Basis node as RFC operations.</span></span>  
  
- <span data-ttu-id="edcd3-136">在每个业务对象。</span><span class="sxs-lookup"><span data-stu-id="edcd3-136">Under each business object.</span></span>  
  
  <span data-ttu-id="edcd3-137">通过确保所有发送同一连接上的 SAP （包括提交或回滚该事务的调用） 来控制在事务中的 Bapi。</span><span class="sxs-lookup"><span data-stu-id="edcd3-137">You control the BAPIs in a transaction by ensuring that they are all sent over the same SAP connection (including the call to commit or roll back the transaction).</span></span> <span data-ttu-id="edcd3-138">可以执行此操作：</span><span class="sxs-lookup"><span data-stu-id="edcd3-138">You can do this in:</span></span>  
  
- <span data-ttu-id="edcd3-139">通过使用 BizTalk 解决方案**ConnectionState**消息上下文属性以确保在事务中的 Bapi 会发送使用相同的连接。</span><span class="sxs-lookup"><span data-stu-id="edcd3-139">BizTalk Solutions by using the **ConnectionState** message context property to ensure that the BAPIs in a transaction are sent using the same connection.</span></span> <span data-ttu-id="edcd3-140">此属性显示的适配器，您提供显式控制用于在 BizTalk 业务流程中发送一条消息的连接。</span><span class="sxs-lookup"><span data-stu-id="edcd3-140">This property is surfaced by the adapter and provides you with explicit control over the connection used to send a message in a BizTalk orchestration.</span></span>  
  
   <span data-ttu-id="edcd3-141">用于执行使用 BizTalk Server 的 BAPI 事务[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持以下消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="edcd3-141">For performing BAPI transactions using BizTalk Server, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following message context properties.</span></span>  
  
  |<span data-ttu-id="edcd3-142">字段</span><span class="sxs-lookup"><span data-stu-id="edcd3-142">Field</span></span>|<span data-ttu-id="edcd3-143">Description</span><span class="sxs-lookup"><span data-stu-id="edcd3-143">Description</span></span>|  
  |-----------|-----------------|  
  |<span data-ttu-id="edcd3-144">OPEN</span><span class="sxs-lookup"><span data-stu-id="edcd3-144">OPEN</span></span>|<span data-ttu-id="edcd3-145">打开事务的新通道。</span><span class="sxs-lookup"><span data-stu-id="edcd3-145">Opens a new channel for the transaction.</span></span>|  
  |<span data-ttu-id="edcd3-146">重复使用</span><span class="sxs-lookup"><span data-stu-id="edcd3-146">REUSE</span></span>|<span data-ttu-id="edcd3-147">重复使用的事务的现有通道。</span><span class="sxs-lookup"><span data-stu-id="edcd3-147">Reuse existing channel for the transaction.</span></span>|  
  |<span data-ttu-id="edcd3-148">CLOSE</span><span class="sxs-lookup"><span data-stu-id="edcd3-148">CLOSE</span></span>|<span data-ttu-id="edcd3-149">提交事务，然后关闭现有通道。</span><span class="sxs-lookup"><span data-stu-id="edcd3-149">Commit the transaction and close the existing channel.</span></span>|  
  |<span data-ttu-id="edcd3-150">ABORT</span><span class="sxs-lookup"><span data-stu-id="edcd3-150">ABORT</span></span>|<span data-ttu-id="edcd3-151">中止事务，并关闭现有通道。</span><span class="sxs-lookup"><span data-stu-id="edcd3-151">Abort the transaction and close the existing channel.</span></span>|  
  
   <span data-ttu-id="edcd3-152">有关详细信息，请参阅[SAP 使用 BizTalk Server 中运行 BAPI 事务](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="edcd3-152">For more information, see [Run BAPI Transactions in SAP using BizTalk Server](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="edcd3-153">请确保您设置**EnableBizTalkCompatibilityMode**时执行事务使用 BizTalk Server 绑定属性。</span><span class="sxs-lookup"><span data-stu-id="edcd3-153">Make sure you set the **EnableBizTalkCompatibilityMode**binding property when performing transactions using BizTalk Server.</span></span>  
  
- <span data-ttu-id="edcd3-154">通过确保在事务中的 Bapi 都使用同一个 WCF 客户端发送的 WCF 服务模型解决方案。</span><span class="sxs-lookup"><span data-stu-id="edcd3-154">WCF service model solutions by ensuring that the BAPIs in a transaction are sent using the same WCF client.</span></span> <span data-ttu-id="edcd3-155">有关详细信息，请参阅[调用中使用 WCF 服务模型的 SAP 的 Bapi](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="edcd3-155">For more information, see [Invoke BAPIs in SAP using WCF Service Model](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md).</span></span>  
  
- <span data-ttu-id="edcd3-156">WCF 通道模型的解决方案通过确保在事务中的 Bapi 发送通过相同的 WCF 通道。</span><span class="sxs-lookup"><span data-stu-id="edcd3-156">WCF channel model solutions by ensuring that the BAPIs in a transaction are sent over the same WCF channel.</span></span> <span data-ttu-id="edcd3-157">有关详细信息，请参阅[开发应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="edcd3-157">For more information, see [Develop applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).</span></span>  
  
### <a name="limitations-on-bapi-transactions"></a><span data-ttu-id="edcd3-158">BAPI 事务的限制</span><span class="sxs-lookup"><span data-stu-id="edcd3-158">Limitations on BAPI Transactions</span></span>  
 <span data-ttu-id="edcd3-159">以下限制适用于 BAPI 事务：</span><span class="sxs-lookup"><span data-stu-id="edcd3-159">The following restrictions apply on BAPI transactions:</span></span>  
  
- <span data-ttu-id="edcd3-160">不能使一个 LUW 内的相同实例上的两个写访问。</span><span class="sxs-lookup"><span data-stu-id="edcd3-160">It is not possible to make two write accesses on the same instance within one LUW.</span></span> <span data-ttu-id="edcd3-161">例如，不能创建订单，并在同一事务中更新。</span><span class="sxs-lookup"><span data-stu-id="edcd3-161">For example, you cannot create an order and update it in the same transaction.</span></span>  
  
- <span data-ttu-id="edcd3-162">当执行 BAPI 事务使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须通过单个主机实例的发送端口发送的所有消息。</span><span class="sxs-lookup"><span data-stu-id="edcd3-162">When performing BAPI a transaction using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], all the messages must be sent over a single host instance of the send port.</span></span>  
  
- <span data-ttu-id="edcd3-163">如果实例是创建、 更新或删除通过使用写入 BAPI，读取 BAPI 写入 BAPI 操作已提交之前无法查看最新数据。</span><span class="sxs-lookup"><span data-stu-id="edcd3-163">If an instance is created, updated, or deleted by using a write BAPI, a read BAPI cannot view the most recent data until the write BAPI is committed.</span></span>  
  
- <span data-ttu-id="edcd3-164">调用 LUW 的外部客户端应在相同的 SAP 连接上调用 LUW 包含的所有 Bapi。</span><span class="sxs-lookup"><span data-stu-id="edcd3-164">An external client that invokes an LUW should call all the BAPIs that the LUW contains on the same SAP connection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="edcd3-165">属于版本 3.1 的 Bapi 调用 COMMIT WORK 作为其实现的一部分。</span><span class="sxs-lookup"><span data-stu-id="edcd3-165">BAPIs that belong to Release 3.1 call COMMIT WORK as part of their implementation.</span></span> <span data-ttu-id="edcd3-166">这意味着，这些 Bapi 不能包含其他 Bapi 中 LUW （因为它们将提交事务）。</span><span class="sxs-lookup"><span data-stu-id="edcd3-166">This means that these BAPIs cannot be included with other BAPIs in an LUW (because they will commit the transaction).</span></span> <span data-ttu-id="edcd3-167">有关详细信息，请参阅 SAP 文档。</span><span class="sxs-lookup"><span data-stu-id="edcd3-167">For more information, see the SAP documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edcd3-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="edcd3-168">See Also</span></span>  
 <span data-ttu-id="edcd3-169">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="edcd3-169">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>