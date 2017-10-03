---
title: "在使用 WCF 服务模型的 SAP 中收到入站的 tRFC 调用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving inbound using the WCF service model
- WCF service model, receiving inbound tRFC calls
ms.assetid: 02dc282b-b659-466a-8bd1-f400a05f71ec
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fb2091d0701831985a1975aa33bd5ecb667b443
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="df691-102">在使用 WCF 服务模型的 SAP 中收到入站的 tRFC 调用</span><span class="sxs-lookup"><span data-stu-id="df691-102">Receive Inbound tRFC Calls in SAP using the WCF Service Model</span></span>
<span data-ttu-id="df691-103">你可以使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]作为事务的 RFC (tRFC) 服务器以接收来自 SAP 的入站的 tRFC 调用。</span><span class="sxs-lookup"><span data-stu-id="df691-103">You can use the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as a transactional RFC (tRFC) server to receive inbound tRFC calls from SAP.</span></span> <span data-ttu-id="df691-104">为入站 tRFCs[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持同一 SAP 逻辑工作单元中 (LUW) 中的多个 tRFCs。</span><span class="sxs-lookup"><span data-stu-id="df691-104">For inbound tRFCs, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports multiple tRFCs in the same SAP logical unit of work (LUW).</span></span>  
  
 <span data-ttu-id="df691-105">本主题中的部分提供有关如何使用适配器为 WCF 服务模型中的 tRFC 服务器信息。</span><span class="sxs-lookup"><span data-stu-id="df691-105">The sections in this topic provide information about how to use the adapter as a tRFC server in the WCF service model.</span></span>  
  
 <span data-ttu-id="df691-106">你可以找到有关使用的详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为以下主题中的 tRFC 服务器：</span><span class="sxs-lookup"><span data-stu-id="df691-106">You can find more information about using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as a tRFC server in the following topics:</span></span>  
  
-   <span data-ttu-id="df691-107">有关对 tRFCs 上支持的概述[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[对 tRFCs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="df691-107">For an overview of support for tRFCs on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span> <span data-ttu-id="df691-108">在继续之前，应阅读本主题。</span><span class="sxs-lookup"><span data-stu-id="df691-108">You should read this topic before continuing.</span></span>  
  
-   <span data-ttu-id="df691-109">有关 tRFC 服务器操作的消息架构的详细信息，请参阅[对 tRFCs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="df691-109">For more information about the message schemas for tRFC server operations, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
## <a name="the-wcf-service-contract-for-a-trfc"></a><span data-ttu-id="df691-110">TRFC WCF 服务协定</span><span class="sxs-lookup"><span data-stu-id="df691-110">The WCF Service Contract for a tRFC</span></span>  
 <span data-ttu-id="df691-111">你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe) 生成你想要收到来自 SAP 系统 tRFCs 的 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="df691-111">You use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF service contract for the tRFCs that you want to receive from the SAP system.</span></span> <span data-ttu-id="df691-112">为入站的 tRFC 是类似于为入站 RFC 生成生成的协定，只不过：</span><span class="sxs-lookup"><span data-stu-id="df691-112">The contract generated for an inbound tRFC is similar to that generated for an inbound RFC except that:</span></span>  
  
-   <span data-ttu-id="df691-113">tRFC 操作将显示在 TRFC 节点下。</span><span class="sxs-lookup"><span data-stu-id="df691-113">tRFC operations are surfaced under the TRFC node.</span></span>  
  
-   <span data-ttu-id="df691-114">WCF 服务协定 （接口） 为传入 tRFCs 生成名为"Trfc"。</span><span class="sxs-lookup"><span data-stu-id="df691-114">The WCF service contract (interface) generated for incoming tRFCs is named "Trfc".</span></span> <span data-ttu-id="df691-115">将服务终结点添加到服务主机时，你必须指定此接口。</span><span class="sxs-lookup"><span data-stu-id="df691-115">You must specify this interface when you add the service endpoint to the service host.</span></span> <span data-ttu-id="df691-116">这也是您的 WCF 服务必须实现的接口。</span><span class="sxs-lookup"><span data-stu-id="df691-116">This is also the interface that your WCF service must implement.</span></span>  
  
    ```  
    public interface Trfc {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Trfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
        [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD/response")]  
        Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
    }  
    ```  
  
-   <span data-ttu-id="df691-117">TRFC 操作的请求消息协定有一个 GUID 参数。</span><span class="sxs-lookup"><span data-stu-id="df691-117">The request message contract for TRFC operations has a GUID parameter.</span></span> <span data-ttu-id="df691-118">这是映射到 tRFC SAP TID 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="df691-118">This is the GUID that maps to the SAP TID for the tRFC.</span></span> <span data-ttu-id="df691-119">在 tRFC 服务器操作，该适配器管理提交、 回滚，并确认 TID SAP 系统，因此没有理由你显式地使用此 GUID 的所有调用。</span><span class="sxs-lookup"><span data-stu-id="df691-119">In tRFC server operations, the adapter manages all calls to commit, rollback, and confirm the TID by the SAP system so there is no reason for you to explicitly use this GUID.</span></span> <span data-ttu-id="df691-120">但是，可以使用它来检索从 SAP TID[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过调用**SapAdapterUtilities.ConvertGuidToTid**。</span><span class="sxs-lookup"><span data-stu-id="df691-120">However, you can use it to retrieve the SAP TID from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by calling **SapAdapterUtilities.ConvertGuidToTid**.</span></span> <span data-ttu-id="df691-121">这可用于帮助你解决 SAP 系统上的问题。</span><span class="sxs-lookup"><span data-stu-id="df691-121">This can be useful to help you troubleshoot issues on the SAP system.</span></span>  
  
    ```  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
    [System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADD", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Trfc/", IsWrapped=true)]  
    public partial class Z_RFC_MKD_ADDRequest {  
  
        ...  
  
        public Z_RFC_MKD_ADDRequest(string DEST, System.Nullable<int> X, System.Nullable<int> Y, System.Guid TransactionalRfcOperationIdentifier) {  
            this.DEST = DEST;  
            this.X = X;  
            this.Y = Y;  
            this.TransactionalRfcOperationIdentifier = TransactionalRfcOperationIdentifier;  
        }  
    }  
  
    ```  
  
## <a name="how-do-i-enable-the-adapter-to-act-as-a-trfc-server"></a><span data-ttu-id="df691-122">如何启用到 Act 适配器作为 tRFC 服务器？</span><span class="sxs-lookup"><span data-stu-id="df691-122">How do I Enable the Adapter to Act as a tRFC Server?</span></span>  
 <span data-ttu-id="df691-123">若要启用充当 tRFC 服务器的适配器，必须设置**TidDatabaseConnectionString**将属性绑定到 TID 数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="df691-123">To enable the adapter to act as a tRFC server, you must set the **TidDatabaseConnectionString** binding property to the connection string for the TID database.</span></span> <span data-ttu-id="df691-124">在打开服务主机之前，你应执行此操作。</span><span class="sxs-lookup"><span data-stu-id="df691-124">You should do this before you open the service host.</span></span> <span data-ttu-id="df691-125">这是该适配器将每个 tRFC 的 SAP 事务 ID (TID) 存储在其中的数据库。</span><span class="sxs-lookup"><span data-stu-id="df691-125">This is the database in which the adapter stores the SAP transaction ID (TID) for each tRFC.</span></span> <span data-ttu-id="df691-126">有关此绑定属性的详细信息，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="df691-126">For more information about this binding property, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
## <a name="how-do-i-enlist-in-the-transaction-for-inbound-trfcs"></a><span data-ttu-id="df691-127">如何为入站 tRFCs 的事务中登记？</span><span class="sxs-lookup"><span data-stu-id="df691-127">How do I Enlist in the Transaction for Inbound tRFCs?</span></span>  
 <span data-ttu-id="df691-128">SAP 逻辑单元的工作 (LUW) 可以包含多个 tRFCs。</span><span class="sxs-lookup"><span data-stu-id="df691-128">An SAP Logical Unit of Work (LUW) can contain multiple tRFCs.</span></span> <span data-ttu-id="df691-129">SAP 系统上 LUW 标识通过唯一事务 ID (TID)。</span><span class="sxs-lookup"><span data-stu-id="df691-129">On the SAP system a LUW is identified by a unique Transaction ID (TID).</span></span> <span data-ttu-id="df691-130">适配器为每个 SAP 系统时，它将调用 tRFC 调用在适配器上的使用 Tid 创建可提交的事务。</span><span class="sxs-lookup"><span data-stu-id="df691-130">The adapter creates a committable transaction for each of the TIDs that the SAP system uses when it invokes tRFC calls on the adapter.</span></span> <span data-ttu-id="df691-131">SAP 系统时在该适配器; tRFC 时，将调用适配器流动与 SAP TID 到你的服务关联的事务。</span><span class="sxs-lookup"><span data-stu-id="df691-131">When the SAP system invokes a tRFC on the adapter; the adapter flows the transaction associated with the SAP TID to your service.</span></span> <span data-ttu-id="df691-132">你可以访问此事务为环境事务从内部操作方法。</span><span class="sxs-lookup"><span data-stu-id="df691-132">You can access this transaction as the ambient transaction from inside your operation method.</span></span> <span data-ttu-id="df691-133">通过在此环境事务中登记，在操作中执行的操作可以参与 SAP LUW。</span><span class="sxs-lookup"><span data-stu-id="df691-133">By enlisting in this ambient transaction, the actions performed in the operation can participate in the SAP LUW.</span></span>  
  
 <span data-ttu-id="df691-134">若要在操作方法中的环境事务中登记，你必须：</span><span class="sxs-lookup"><span data-stu-id="df691-134">To enlist in the ambient transaction in an operation method, you must:</span></span>  
  
1.  <span data-ttu-id="df691-135">批注具有的操作方法**TransactionScopeRequired**属性**OperationBehavior**属性。</span><span class="sxs-lookup"><span data-stu-id="df691-135">Annotate the operation method with the **TransactionScopeRequired** property of the **OperationBehavior** attribute.</span></span> <span data-ttu-id="df691-136">这将告知 WCF 希望对环境事务从操作内的访问。</span><span class="sxs-lookup"><span data-stu-id="df691-136">This tells WCF that you want access to the ambient transaction from inside the operation.</span></span>  
  
2.  <span data-ttu-id="df691-137">通过批注具有的操作方法创建一个事务范围**TransactionAutoComplete**属性**OperationBehavior**属性或通过显式使用**TransactionScope**内将操作方法。</span><span class="sxs-lookup"><span data-stu-id="df691-137">Create a transaction scope either by annotating the operation method with the **TransactionAutoComplete** property of the **OperationBehavior** attribute or by explicitly using a **TransactionScope** inside the operation method.</span></span>  
  
 <span data-ttu-id="df691-138">下面的示例演示实现两个操作的服务。</span><span class="sxs-lookup"><span data-stu-id="df691-138">The following example shows a service that implements two operations.</span></span> <span data-ttu-id="df691-139">这两种操作方法使用批注**TransactionScopeRequired**属性来访问环境事务。</span><span class="sxs-lookup"><span data-stu-id="df691-139">Both operation methods are annotated with the **TransactionScopeRequired** property to access the ambient transaction.</span></span>  
  
-   <span data-ttu-id="df691-140">**Z_TRFC_EXAMPLE1**显式在事务中登记使用**TransactionScope**对象。</span><span class="sxs-lookup"><span data-stu-id="df691-140">**Z_TRFC_EXAMPLE1** explicitly enlists in the transaction by using a **TransactionScope** object.</span></span>  
  
-   <span data-ttu-id="df691-141">**Z_TRFC_EXAMPLE2**使用批注**TransactionAutoComplete**属性在事务中登记</span><span class="sxs-lookup"><span data-stu-id="df691-141">**Z_TRFC_EXAMPLE2** is annotated with the **TransactionAutoComplete** property to enlist in the transaction</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, UseSynchronizationContext = false)]  
class Z_Example_ServiceContractClass : Trfc  
{  
  
    // This operation method explicitly creates a TransactionScope to enlist in the ambient transaction  
    // You must explictly call ts.Complete to complete the transaction before you return from the operation  
    // Otherwise the transaction is aborted.  
    // You can throw an exception or return without calling ts.complete to abort the transacation  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public Z_TRFC_EXAMPLE1Response Z_TRFC_EXAMPLE1(Z_TRFC_EXAMPLE1Request request)  
    {  
        using (TransactionScope ts = new TransactionScope(TransactionScopeOption.Required))  
        {  
            // Process tRFC  
  
            ...  
  
            Z_TRFC_EXAMPLE1Response response = new Z_TRFC_EXAMPLE1Response();  
            response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
            return response;  
            //since there is no ts.Complete(), this is equivalent to a rollback.  
        }  
    }  
  
    // This operation method sets the TransactionAutoComplete property of the OperationBehavior attribute  
    // to enlist in the transaction. There is no need to explictly create a TransactionScope in the code.  
    // If the method returns with no unhandled exceptions, the transaction completes; otherwise it aborts  
    // You can throw an exception to abort the transaction.  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public Z_TRFC_EXAMPLE2Response Z_TRFC_EXAMPLE2(Z_TRFC_EXAMPLE2Request request)  
    {  
        // Process tRFC  
  
        ...  
  
        Z_TRFC_EXAMPLE2Response response = new Z_TRFC_EXAMPLE2Response();  
        response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
        return response;  
        //if there is no unhandled exception, the transaction completes when the operation returns.  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="df691-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df691-142">See Also</span></span>  
[<span data-ttu-id="df691-143">使用 WCF 服务模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="df691-143">Develop applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)