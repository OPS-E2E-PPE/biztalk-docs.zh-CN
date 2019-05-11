---
title: 调用 Trfc 在 SAP 中使用 WCF 服务模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFCs, invoking by using the WCF service model
- WCF service model, invoking tRFCs
ms.assetid: 456fa869-2f1a-42e0-adbf-86bfe0876846
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bbea3332657a5071e1f25c26136181a5154adab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373303"
---
# <a name="invoke-trfcs-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="76318-102">调用 Trfc 在 SAP 中使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="76318-102">Invoke tRFCs in SAP using the WCF Service Model</span></span>
<span data-ttu-id="76318-103">事务性远程函数调用 (Trfc) 保证*一次性*RFC SAP 系统上执行。</span><span class="sxs-lookup"><span data-stu-id="76318-103">Transactional Remote Function Calls (tRFCs) guarantee a *one-time* execution of an RFC on an SAP system.</span></span> <span data-ttu-id="76318-104">您可以调用任何显示的 Rfc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为 tRFC。</span><span class="sxs-lookup"><span data-stu-id="76318-104">You can invoke any of the RFCs surfaced by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as a tRFC.</span></span> <span data-ttu-id="76318-105">调用 tRFC 的 WCF 服务模型中是类似于调用 RFC 具有以下差异：</span><span class="sxs-lookup"><span data-stu-id="76318-105">Invoking a tRFC in the WCF service model is similar to invoking an RFC with the following differences:</span></span>  
  
- <span data-ttu-id="76318-106">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Trfc 不同节点 (TRFC) 比 Rfc (RFC) 下的图面。</span><span class="sxs-lookup"><span data-stu-id="76318-106">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces tRFCs under a different node (TRFC) than RFCs (RFC).</span></span>  
  
- <span data-ttu-id="76318-107">tRFC 客户端调用不会返回 SAP 导出和更改参数值。</span><span class="sxs-lookup"><span data-stu-id="76318-107">tRFC client calls do not return values for SAP export and changing parameters.</span></span>  
  
- <span data-ttu-id="76318-108">tRFC 操作包括映射到 SAP 事务 ID (TID) 的 GUID 参数通过 trfc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="76318-108">tRFC operations include a GUID parameter that is mapped to the SAP transaction ID (TID) for the tRFC by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="76318-109">调用 tRFC 后，必须调用 RfcConfirmTransID 操作以确认 （提交） tRFC SAP 系统上。</span><span class="sxs-lookup"><span data-stu-id="76318-109">After you invoke a tRFC, you must invoke the RfcConfirmTransID operation to confirm (commit) the tRFC on the SAP system.</span></span> <span data-ttu-id="76318-110">直接在 TRFC 节点下显示此操作。</span><span class="sxs-lookup"><span data-stu-id="76318-110">This operation is surfaced directly under the TRFC node.</span></span>  
  
  <span data-ttu-id="76318-111">有关 tRFC 操作和 RfcConfirmTransID 操作的详细信息，请参阅[Trfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="76318-111">For more information about tRFC operations and the RfcConfirmTransID operation, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
  <span data-ttu-id="76318-112">以下部分说明如何通过使用调用 Trfc SAP 系统上的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="76318-112">The following sections show you how to invoke tRFCs on the SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="76318-113">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="76318-113">The WCF Client Class</span></span>  
 <span data-ttu-id="76318-114">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]单一的服务合同，"Trfc"下的所有 tRFC 操作的图都面。</span><span class="sxs-lookup"><span data-stu-id="76318-114">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces all tRFC operations under a single service contract, "Trfc".</span></span> <span data-ttu-id="76318-115">这意味着，单一的 WCF 客户端类， **TrfcClient**，为所有你想要调用 tRFC 操作的创建。</span><span class="sxs-lookup"><span data-stu-id="76318-115">This means that a single WCF client class, **TrfcClient**, is created for all of the tRFC operations that you want to invoke.</span></span> <span data-ttu-id="76318-116">每个目标 tRFC 表示为此类的方法。</span><span class="sxs-lookup"><span data-stu-id="76318-116">Each target tRFC is represented as a method of this class.</span></span> <span data-ttu-id="76318-117">为每个方法：</span><span class="sxs-lookup"><span data-stu-id="76318-117">For each method:</span></span>  
  
- <span data-ttu-id="76318-118">如结构复杂 SAP 类型为.NET 类相对应的属性与提供给 SAP 类型的字段。</span><span class="sxs-lookup"><span data-stu-id="76318-118">Complex SAP types such as structures are surfaced as .NET classes with properties that correspond to the fields of the SAP type.</span></span> <span data-ttu-id="76318-119">这些类定义以下命名空间中： **microsoft.lobservices.sap._2007._03.Types.Rfc**。</span><span class="sxs-lookup"><span data-stu-id="76318-119">These classes are defined in the following namespace: **microsoft.lobservices.sap._2007._03.Types.Rfc**.</span></span>  
  
  <span data-ttu-id="76318-120">下面的代码显示了一部分**TrfcClient**类和 SAP 系统调用 BAPI_SALESORDER_CREATEFROMDAT2 （作为 tRFC) 的方法。</span><span class="sxs-lookup"><span data-stu-id="76318-120">The following code shows part of the **TrfcClient** class and the method that invokes BAPI_SALESORDER_CREATEFROMDAT2 (as a tRFC) on the SAP system.</span></span> <span data-ttu-id="76318-121">**TransactionalRfcOperationIdentifier**参数包含映射到 SAP TID 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="76318-121">The **TransactionalRfcOperationIdentifier** parameter contains the GUID that is mapped to the SAP TID.</span></span> <span data-ttu-id="76318-122">并非所有方法的参数会显示。</span><span class="sxs-lookup"><span data-stu-id="76318-122">Not all of the parameters to the method are shown.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class TrfcClient : System.ServiceModel.ClientBase<Trfc>, Trfc {  
  
    ....  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    public void BAPI_SALESORDER_CREATEFROMDAT2(  
                string BEHAVE_WHEN_ERROR,   
                string BINARY_RELATIONSHIPTYPE,   
                string CONVERT,   
                string INT_NUMBER_ASSIGNMENT,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDLS LOGIC_SWITCH,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1 ORDER_HEADER_IN,   
  
                …  
  
               microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIADDR1[] PARTNERADDRESSES,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2[] RETURN,   
                ref System.Guid TransactionalRfcOperationIdentifier) { ...  }  
}  
```  
  
 <span data-ttu-id="76318-123">下面的代码演示 RfcConfirmTransID 操作生成的方法。</span><span class="sxs-lookup"><span data-stu-id="76318-123">The following code shows the method that is generated for the RfcConfirmTransID operation.</span></span> <span data-ttu-id="76318-124">必须确保此方法生成的一部分**TrfcClient**。</span><span class="sxs-lookup"><span data-stu-id="76318-124">You must ensure that this method is generated as part of the **TrfcClient**.</span></span> <span data-ttu-id="76318-125">TRFC 节点的正下方显示 RfcConfirmTransID 操作。</span><span class="sxs-lookup"><span data-stu-id="76318-125">The RfcConfirmTransID operation is surfaced directly under the TRFC node.</span></span>  
  
```  
public void RfcConfirmTransID(System.Guid TransactionalRfcOperationIdentifier) {…}  
```  
  
## <a name="how-to-create-a-trfc-client-application"></a><span data-ttu-id="76318-126">如何创建 tRFC 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="76318-126">How to Create a tRFC Client Application</span></span>  
 <span data-ttu-id="76318-127">若要创建的应用程序调用 Trfc 的步骤是类似的步骤遵循以调用 Rfc，但存在以下例外：</span><span class="sxs-lookup"><span data-stu-id="76318-127">The steps to create an application that invokes tRFCs are similar to the steps you follow to invoke RFCs, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="76318-128">您必须检索 TRFC 节点下的目标操作。</span><span class="sxs-lookup"><span data-stu-id="76318-128">You must retrieve the target operations under the TRFC node.</span></span>  
  
-   <span data-ttu-id="76318-129">您必须检索 RfcConfirmTransID 操作。</span><span class="sxs-lookup"><span data-stu-id="76318-129">You must retrieve the RfcConfirmTransID operation.</span></span> <span data-ttu-id="76318-130">这是直接在 TRFC 节点下显示。</span><span class="sxs-lookup"><span data-stu-id="76318-130">This is surfaced directly under the TRFC node.</span></span>  
  
-   <span data-ttu-id="76318-131">若要确认 （提交） 上的 SAP 系统的 tRFC 操作，必须调用该 RfcConfirmTransID 操作，并返回该 tRFC 操作的 GUID。</span><span class="sxs-lookup"><span data-stu-id="76318-131">To confirm (commit) a tRFC operation on the SAP system, you must invoke the RfcConfirmTransID operation with the GUID that was returned for that tRFC operation.</span></span>  
  
#### <a name="to-create-a-trfc-client-application"></a><span data-ttu-id="76318-132">若要创建 tRFC 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="76318-132">To create a tRFC client application</span></span>  
  
1. <span data-ttu-id="76318-133">生成**TrfcClient**类。</span><span class="sxs-lookup"><span data-stu-id="76318-133">Generate a **TrfcClient** class.</span></span> <span data-ttu-id="76318-134">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 生成**TrfcClient**以你想要的 Rfc 目标的类。</span><span class="sxs-lookup"><span data-stu-id="76318-134">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a **TrfcClient** class that targets the RFCs with which you want to work.</span></span> <span data-ttu-id="76318-135">有关如何生成 WCF 客户端的详细信息，请参阅[生成 WCF 客户端或 WCF 服务约定的 SAP 解决方案项目](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="76318-135">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF Service Contract for SAP solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span> <span data-ttu-id="76318-136">确保 RfcConfirmTransID 操作包含在**TrfcClient**类。</span><span class="sxs-lookup"><span data-stu-id="76318-136">Ensure that the RfcConfirmTransID operation is included in the **TrfcClient** class.</span></span>  
  
2. <span data-ttu-id="76318-137">创建的实例**TrfcClient**类在步骤 1 中生成并指定客户端绑定。</span><span class="sxs-lookup"><span data-stu-id="76318-137">Create an instance of the **TrfcClient** class generated in step 1 and specify a client binding.</span></span> <span data-ttu-id="76318-138">指定客户端绑定涉及到指定的绑定和终结点地址**TrfcClient**将使用。</span><span class="sxs-lookup"><span data-stu-id="76318-138">Specifying a client binding involves specifying the binding and endpoint address that the **TrfcClient** will use.</span></span> <span data-ttu-id="76318-139">可以在代码中以强制方式或在配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="76318-139">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="76318-140">有关如何指定客户端绑定的详细信息，请参阅[SAP 系统的配置客户端绑定](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="76318-140">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="76318-141">下面的代码初始化**TrfcClient**从配置和 SAP 系统的凭据集。</span><span class="sxs-lookup"><span data-stu-id="76318-141">The following code initializes the **TrfcClient** from configuration and sets the credentials for the SAP system.</span></span>  
  
   ```  
   TrfcClient trfcClient = new TrfcClient("SAPBinding_Rfc");  
  
   trfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
   trfcClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. <span data-ttu-id="76318-142">打开**TrfcClient**。</span><span class="sxs-lookup"><span data-stu-id="76318-142">Open the **TrfcClient**.</span></span>  
  
   ```  
   trfcClient.Open();  
   ```  
  
4. <span data-ttu-id="76318-143">在调用适当的方法**TrfcClient**步骤 2 来调用目标 tRFC 上的 SAP 系统中创建。</span><span class="sxs-lookup"><span data-stu-id="76318-143">Invoke the appropriate method on the **TrfcClient** created in step 2 to invoke the target tRFC on the SAP system.</span></span> <span data-ttu-id="76318-144">可以将传递的变量，其中包含一个 GUID 或包含空 GUID **TransactionalRrcOperationIdentifier**参数。</span><span class="sxs-lookup"><span data-stu-id="76318-144">You can pass a variable that contains a GUID or that contains an empty GUID for the **TransactionalRrcOperationIdentifier** parameter.</span></span> <span data-ttu-id="76318-145">如果传递一个空的 GUID，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]会为您生成一个。</span><span class="sxs-lookup"><span data-stu-id="76318-145">If you pass an empty GUID, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] generates one for you.</span></span> <span data-ttu-id="76318-146">下面的代码调用 BAPI_SALESORDER_CREATEFROMDAT2 作为 tRFC （显示方法的参数不是所有） 在 SAP 系统上。</span><span class="sxs-lookup"><span data-stu-id="76318-146">The following code invokes BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC on the SAP system (not all parameters to the method are shown).</span></span> <span data-ttu-id="76318-147">指定一个 GUID。</span><span class="sxs-lookup"><span data-stu-id="76318-147">A GUID is specified.</span></span>  
  
   ```  
   transactionalRfcOperationIdentifier = Guid.NewGuid();  
  
   //invoke RFC_CUSTOMER_GET as a tRFC  
   trfcClient.BAPI_SALESORDER_CREATEFROMDAT2(  
                                   request.BEHAVE_WHEN_ERROR,  
                                   request.BINARY_RELATIONSHIPTYPE,  
                                   request.CONVERT,  
  
                                   ...  
  
                                   ref transactionalRfcOperationIdentifier);  
   ```  
  
5. <span data-ttu-id="76318-148">若要确认 TID 与 SAP 系统上 tRFC 相关联，请调用**RfcConfirmTransID**方法**TrfcClient**。</span><span class="sxs-lookup"><span data-stu-id="76318-148">To confirm the TID associated with the tRFC on the SAP system, invoke the **RfcConfirmTransID** method on the **TrfcClient**.</span></span> <span data-ttu-id="76318-149">指定的步骤 4 中返回的 GUID **TransactionRfcOperationIdentifier**参数。</span><span class="sxs-lookup"><span data-stu-id="76318-149">Specify the GUID returned in step 4 for the **TransactionRfcOperationIdentifier**parameter.</span></span>  
  
   ```  
   trfcClient.RfcConfirmTransID(transactionalRfcOperationIdentifier);  
   ```  
  
6. <span data-ttu-id="76318-150">关闭**TrfcClient**完成后 （在调用所有 Trfc 完成） 后使用它。</span><span class="sxs-lookup"><span data-stu-id="76318-150">Close the **TrfcClient** when you are done using it (after you have finished invoking all tRFCs).</span></span>  
  
   ```  
   trfcClient.Close();   
   ```  
  
### <a name="example"></a><span data-ttu-id="76318-151">示例</span><span class="sxs-lookup"><span data-stu-id="76318-151">Example</span></span>  
 <span data-ttu-id="76318-152">下面的示例演示如何调用 tRFC 作为 BAPI_SALESORDER_CREATE。</span><span class="sxs-lookup"><span data-stu-id="76318-152">The following example shows how to invoke BAPI_SALESORDER_CREATE as a tRFC.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, the WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for WCF LOB Adapter SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using microsoft.lobservices.sap._2007._03.Types.Rfc;  
  
// This example demonstrates sending BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC. The client has   
// methods to:  
//      send the BAPI (BAPI_SALESORDER_CREATEFROMDAT2)and to  
//      Confirm the transaction (RfcConfirmTransID)  
// An instance of BAPI_SALESORDER_CREATEFROMDAT2Request (generated)   
// is used to format the BAPI before invoking BAPI_SALESORDER_CREATEFROMDAT2. This   
// is not necessary, but is done to make it easier to read the code.  
// tRFC invocations always includes a ref parameter that contains a GUID. You can optionally   
// set this parameter when you invoke the method; however, you must use the value returned by  
// the adapter when you call RfcConfirmTransID to confirm the transaction on the SAP system.   
// You can call the utility method, SAPAdapterUtilities.ConvertGuidToTid, to get the value  
// of the SAP transaction Id from the GUID that the adapter returns.  
namespace SapTrfcClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            TrfcClient sapTrfcClient = null;  
  
            try  
            {  
                Console.WriteLine("SAP TRFC client sample started");  
                Console.WriteLine("Creating the TRFC client");  
                // Create the SAP Trfc Client from configuration  
                sapTrfcClient = new TrfcClient("SAPBinding_Trfc");  
                sapTrfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
                sapTrfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                Console.WriteLine("Opening the TRFC client");  
                // Open the Trfc Client  
                sapTrfcClient.Open();  
  
                // Create a GUID -- note: this is optional. If you do not pass a GUID,  
                // for the TransactionalRfcOperationIdentifier parameter, the SAP adapter will   
                // generate one, associate it with the SAP TID, and set the   
                // TransactionalRfcOperationIdentifier parameter.  
                Guid tidGuid = Guid.NewGuid();  
  
                BAPI_SALESORDER_CREATEFROMDAT2Request request = new BAPI_SALESORDER_CREATEFROMDAT2Request();  
  
                request.ORDER_HEADER_IN = new BAPISDHD1();  
                request.ORDER_HEADER_IN.DOC_TYPE = "TA";  
                request.ORDER_HEADER_IN.SALES_ORG = "1000";  
                request.ORDER_HEADER_IN.DISTR_CHAN = "10";  
                request.ORDER_HEADER_IN.DIVISION = "00";  
                request.ORDER_HEADER_IN.SALES_OFF = "1000";  
                request.ORDER_HEADER_IN.REQ_DATE_H = DateTime.Now;  
                request.ORDER_HEADER_IN.PURCH_DATE = DateTime.Now;  
                request.ORDER_HEADER_IN.PURCH_NO_C = "Cust PO";  
                request.ORDER_HEADER_IN.CURRENCY = "EUR";  
  
                BAPISDITM[] orderItems = new BAPISDITM[1];  
                orderItems[0] = new BAPISDITM();  
                orderItems[0].MATERIAL = "P-109";  
                orderItems[0].PLANT = "1000";  
                orderItems[0].TARGET_QU = "ST";  
                request.ORDER_ITEMS_IN = orderItems;  
  
                BAPIPARNR[] orderPartners = new BAPIPARNR[1];  
                orderPartners[0] = new microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPARNR();  
                orderPartners[0].PARTN_ROLE = "AG";  
                orderPartners[0].PARTN_NUMB = "0000001390";  
                request.ORDER_PARTNERS = orderPartners;  
  
                // Create a GUID -- note: this is optional. If you do not pass a GUID,  
                // for the TransactionalRfcOperationIdentifier parameter, the SAP adapter will   
                // generate one, associate it with the SAP TID, and set the   
                // TransactionalRfcOperationIdentifier parameter.  
                request.TransactionalRfcOperationIdentifier = Guid.NewGuid();  
  
                Console.WriteLine("Invoking BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC");  
  
                //invoke RFC_CUSTOMER_GET as a tRFC  
                sapTrfcClient.BAPI_SALESORDER_CREATEFROMDAT2(request.BEHAVE_WHEN_ERROR,  
                                                                request.BINARY_RELATIONSHIPTYPE,  
                                                                request.CONVERT,  
                                                                request.INT_NUMBER_ASSIGNMENT,  
                                                                request.LOGIC_SWITCH,  
                                                                request.ORDER_HEADER_IN,  
                                                                request.ORDER_HEADER_INX,  
                                                                request.SALESDOCUMENTIN,  
                                                                request.SENDER,  
                                                                request.TESTRUN,  
                                                                request.EXTENSIONIN,  
                                                                request.ORDER_CCARD,  
                                                                request.ORDER_CFGS_BLOB,  
                                                                request.ORDER_CFGS_INST,  
                                                                request.ORDER_CFGS_PART_OF,  
                                                                request.ORDER_CFGS_REF,  
                                                                request.ORDER_CFGS_REFINST,  
                                                                request.ORDER_CFGS_VALUE,  
                                                                request.ORDER_CFGS_VK,  
                                                                request.ORDER_CONDITIONS_IN,  
                                                                request.ORDER_CONDITIONS_INX,  
                                                                request.ORDER_ITEMS_IN,  
                                                                request.ORDER_ITEMS_INX,  
                                                                request.ORDER_KEYS,  
                                                                request.ORDER_PARTNERS,  
                                                                request.ORDER_SCHEDULES_IN,  
                                                                request.ORDER_SCHEDULES_INX,  
                                                                request.ORDER_TEXT,  
                                                                request.PARTNERADDRESSES,  
                                                                request.RETURN,  
                                                                ref request.TransactionalRfcOperationIdentifier);  
  
                string sapTxId = null;  
                sapTxId = SAPAdapterUtilities.ConvertGuidToTid(request.TransactionalRfcOperationIdentifier);  
  
                Console.WriteLine("BAPI_SALESORDER_CREATEFROMDAT2 Sent");  
                Console.WriteLine("The SAP Transaction Id is " + sapTxId);  
  
                // Invoke the RfcConfirmTransID method to confirm (commit) the transaction on  
                // the SAP system. This step is required to complete the transaction. The SAP  
                // adapter will always return a TranactionalRfcOperationIdentifier, whether   
                // one was supplied in the call or not.  
                sapTrfcClient.RfcConfirmTransID(request.TransactionalRfcOperationIdentifier);  
  
                Console.WriteLine("SAP Transaction {0} has been committed", sapTxId);  
  
                Console.WriteLine("\nHit <RETURN> to end");  
                Console.ReadLine();  
  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
                throw;  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw;  
            }  
            finally  
            {  
                // Close the client  
                if (sapTrfcClient != null)  
                {  
                    if (sapTrfcClient.State == CommunicationState.Opened)  
                        sapTrfcClient.Close();  
                    else  
                        sapTrfcClient.Abort();  
                }  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="76318-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="76318-153">See Also</span></span>  
<span data-ttu-id="76318-154">[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="76318-154">[Develop applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 [<span data-ttu-id="76318-155">在 SAP 中 Trfc 的操作</span><span class="sxs-lookup"><span data-stu-id="76318-155">Operations on tRFCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)