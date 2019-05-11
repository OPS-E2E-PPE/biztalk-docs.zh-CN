---
title: 向使用 WCF 服务模型的 SAP 发送 Idoc |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, sending IDOCs to SAP
- IDOCs, sending to SAP by using the WCF service model
ms.assetid: 84077234-b82b-4e88-b858-ce2cb1383fb4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b31823494068dab5f106f79cc404b9b5d35ad7a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372874"
---
# <a name="send-idocs-to-sap-using-the-wcf-service-model"></a><span data-ttu-id="a13b5-102">向使用 WCF 服务模型的 SAP 发送 Idoc</span><span class="sxs-lookup"><span data-stu-id="a13b5-102">Send IDOCs to SAP using the WCF Service Model</span></span>
<span data-ttu-id="a13b5-103">在内部，[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]将 Idoc 发送到 SAP 系统，通过调用两个以下 Rfc 之一：</span><span class="sxs-lookup"><span data-stu-id="a13b5-103">Internally, the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] sends IDOCs to the SAP system by invoking one of the two following RFCs:</span></span>  
  
- <span data-ttu-id="a13b5-104">版本 3 idoc IDOC_INBOUND_ASYNCHRONOUS。</span><span class="sxs-lookup"><span data-stu-id="a13b5-104">IDOC_INBOUND_ASYNCHRONOUS for version 3 IDOCs.</span></span>  
  
- <span data-ttu-id="a13b5-105">版本 2 idoc INBOUND_IDOC_PROCESS。</span><span class="sxs-lookup"><span data-stu-id="a13b5-105">INBOUND_IDOC_PROCESS for version 2 IDOCs.</span></span>  
  
  <span data-ttu-id="a13b5-106">您可以将 IDOC 发送到适配器通过调用适当 RFC （或 tRFC）;但是，您可以使用两个以下操作以将 Idoc 发送到适配器：</span><span class="sxs-lookup"><span data-stu-id="a13b5-106">You can send an IDOC to the adapter by invoking the appropriate RFC (or tRFC); however, you can also use the two following operations to send IDOCs to the adapter:</span></span>  
  
- <span data-ttu-id="a13b5-107">**SendIdoc** IDOC 根节点的正下方显示。</span><span class="sxs-lookup"><span data-stu-id="a13b5-107">**SendIdoc** is surfaced directly under the IDOC root node.</span></span> <span data-ttu-id="a13b5-108">SendIdoc 操作将 IDOC 发送到的字符串 （弱类型化） 数据作为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a13b5-108">The SendIdoc operation sends the IDOC as string (weakly-typed) data to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="a13b5-109">**发送**单独为每个 IDOC 显示。</span><span class="sxs-lookup"><span data-stu-id="a13b5-109">**Send** is surfaced individually for each IDOC.</span></span> <span data-ttu-id="a13b5-110">发送操作将作为强类型化数据添加到发送 IDOC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a13b5-110">The Send operation sends the IDOC as strongly-typed data to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
  <span data-ttu-id="a13b5-111">这些操作确定如何 IDOC 数据发送到适配器，不如何其发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="a13b5-111">These operations determine how the IDOC data is sent to the adapter, not how it is sent to the SAP system.</span></span> <span data-ttu-id="a13b5-112">适配器始终会到 SAP 系统的 IDOC 使用相应 tRFC 发送。</span><span class="sxs-lookup"><span data-stu-id="a13b5-112">The adapter always sends the IDOC to the SAP system by using the appropriate tRFC.</span></span>  
  
  <span data-ttu-id="a13b5-113">因为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]发送 IDOC tRFC 作为发送和 SendIdoc 操作公开用于确认 （提交） IDOC 的 GUID 参数。</span><span class="sxs-lookup"><span data-stu-id="a13b5-113">Because the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] sends the IDOC as a tRFC, both the Send and SendIdoc operations expose a GUID parameter that you use to confirm (commit) the IDOC.</span></span> <span data-ttu-id="a13b5-114">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在内部将映射与 SAP 事务 ID (TID) 与 tRFC 关联此 GUID。</span><span class="sxs-lookup"><span data-stu-id="a13b5-114">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] internally maps this GUID with the SAP transaction ID (TID) that is associated with the tRFC.</span></span> <span data-ttu-id="a13b5-115">你可以确认 IDOC 中两种方式之一：</span><span class="sxs-lookup"><span data-stu-id="a13b5-115">You can confirm the IDOC in one of two ways:</span></span>  
  
- <span data-ttu-id="a13b5-116">通过使用**AutoConfirmSentIdocs**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="a13b5-116">By using the **AutoConfirmSentIdocs** binding property.</span></span> <span data-ttu-id="a13b5-117">如果此绑定属性设置为 **，则返回 true**，适配器会自动确定用于发送 IDOC tRFC。</span><span class="sxs-lookup"><span data-stu-id="a13b5-117">If this binding property is set to **true**, the adapter automatically confirms the tRFC used to send the IDOC.</span></span>  
  
- <span data-ttu-id="a13b5-118">通过调用 RfcConfirmTransID。</span><span class="sxs-lookup"><span data-stu-id="a13b5-118">By invoking RfcConfirmTransID.</span></span> <span data-ttu-id="a13b5-119">使用与 IDOC 关联的 GUID 调用此操作。</span><span class="sxs-lookup"><span data-stu-id="a13b5-119">You invoke this operation with the GUID associated with the IDOC.</span></span>  
  
  <span data-ttu-id="a13b5-120">以下各节演示如何使用 SendIdoc 和发送操作将 Idoc 发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="a13b5-120">The following sections show you how to send IDOCs to an SAP system by using the SendIdoc and Send operations.</span></span> <span data-ttu-id="a13b5-121">若要帮助您将 IDOC 发送作为 tRFC 的详细信息，请参阅[使用 WCF 服务模型调用 Trfc 在 SAP 中的](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="a13b5-121">For more information to help you send an IDOC as a tRFC, see [Invoke tRFCs in SAP by using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="a13b5-122">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="a13b5-122">The WCF Client Class</span></span>  
  
### <a name="the-sendidoc-operation"></a><span data-ttu-id="a13b5-123">SendIdoc 操作</span><span class="sxs-lookup"><span data-stu-id="a13b5-123">The SendIdoc Operation</span></span>  
 <span data-ttu-id="a13b5-124">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]单个操作 （和服务协定） 以字符串格式发送 IDOC 的图面。</span><span class="sxs-lookup"><span data-stu-id="a13b5-124">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a single operation (and service contract) to send an IDOC in string format.</span></span> <span data-ttu-id="a13b5-125">服务协定的名称是"Idoc"和 WCF 客户端类是**IdocClient**。</span><span class="sxs-lookup"><span data-stu-id="a13b5-125">The name of the service contract is "Idoc" and the WCF client class is **IdocClient**.</span></span>  
  
 <span data-ttu-id="a13b5-126">可以通过使用此客户端向 SAP 发送任何 IDOC。</span><span class="sxs-lookup"><span data-stu-id="a13b5-126">You can send any IDOC to SAP by using this client.</span></span> <span data-ttu-id="a13b5-127">它包含一个方法， **SendIdoc**，采用两个参数：</span><span class="sxs-lookup"><span data-stu-id="a13b5-127">It contains a single method, **SendIdoc**, that takes two parameters:</span></span>  
  
- <span data-ttu-id="a13b5-128">**idocData**是一个字符串，包含 IDOC 数据</span><span class="sxs-lookup"><span data-stu-id="a13b5-128">**idocData** is a string that contains the IDOC data</span></span>  
  
- <span data-ttu-id="a13b5-129">**guid**是映射到 SAP TID 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a13b5-129">**guid** is the GUID that is mapped to the SAP TID.</span></span>  
  
  <span data-ttu-id="a13b5-130">下面的代码演示为 SendIdoc 操作生成的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="a13b5-130">The following code shows the WCF client that is generated for the SendIdoc operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocClient : System.ServiceModel.ClientBase<Idoc>, Idoc {  
  
    public void SendIdoc(string idocData, ref System.Nullable\<System.Guid\> guid) {…}  
}  
```  
  
### <a name="the-send-operation"></a><span data-ttu-id="a13b5-131">发送操作</span><span class="sxs-lookup"><span data-stu-id="a13b5-131">The Send Operation</span></span>  
 <span data-ttu-id="a13b5-132">发送操作使用强类型化数据，因为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]面为每个 IDOC，唯一的服务协定。</span><span class="sxs-lookup"><span data-stu-id="a13b5-132">Because the Send operation uses strongly-typed data, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a unique service contract for each IDOC.</span></span> <span data-ttu-id="a13b5-133">为 IDOC 类型、 版本、 发行版号和 CIM 类型 （如果相关） 上基于此协定生成的接口 （和 WCF 客户端类） 的名称。</span><span class="sxs-lookup"><span data-stu-id="a13b5-133">The name of the interface (and the WCF client class) generated for this contract is based on the IDOC type, version, release number, and CIM type (if relevant).</span></span> <span data-ttu-id="a13b5-134">例如对于 ORDERS03.v3.620 IDOC，该接口名为"IdocORDERS03V3R620"和 WCF 客户端类是**IdocORDERS03V3R620Client**。</span><span class="sxs-lookup"><span data-stu-id="a13b5-134">For example for the ORDERS03.v3.620 IDOC, the interface is named "IdocORDERS03V3R620" and the WCF client class is **IdocORDERS03V3R620Client**.</span></span>  
  
 <span data-ttu-id="a13b5-135">必须为每种不同类型的 IDOC 生成唯一的客户端。</span><span class="sxs-lookup"><span data-stu-id="a13b5-135">You must generate a unique client for each different type of IDOC.</span></span> <span data-ttu-id="a13b5-136">此客户端包含单个方法**发送**，采用两个参数：</span><span class="sxs-lookup"><span data-stu-id="a13b5-136">This client contains a single method, **Send**, that takes two parameters:</span></span>  
  
- <span data-ttu-id="a13b5-137">**idocData**是表示的强类型化 IDOC 数据的类。</span><span class="sxs-lookup"><span data-stu-id="a13b5-137">**idocData** is a class that represents the strongly-typed IDOC data.</span></span>  
  
- <span data-ttu-id="a13b5-138">**guid**是映射到 SAP TID 的 GUID 的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="a13b5-138">**guid** is a string representation of the GUID that is mapped to the SAP TID.</span></span>  
  
  <span data-ttu-id="a13b5-139">下面的代码演示显示 ORDERS03.v3.620 IDOC 发送操作生成的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="a13b5-139">The following code shows the WCF client that is generated for the Send operation surfaced for the ORDERS03.v3.620 IDOC.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocORDERS03V3R620Client : System.ServiceModel.ClientBase<IdocORDERS03V3R620>, IdocORDERS03V3R620 {  
  
    ...  
  
    public void Send(ORDERS03 idocData, ref string guid) { ... }  
}  
```  
  
## <a name="how-to-create-an-application-to-send-idocs"></a><span data-ttu-id="a13b5-140">如何创建应用程序能够发送 Idoc</span><span class="sxs-lookup"><span data-stu-id="a13b5-140">How to Create an Application to Send IDOCs</span></span>  
 <span data-ttu-id="a13b5-141">若要将 IDOC 发送到 SAP 系统，执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a13b5-141">To send an IDOC to an SAP system, perform the following steps.</span></span>  
  
#### <a name="to-send-an-idoc-to-an-sap-system"></a><span data-ttu-id="a13b5-142">若要将 IDOC 发送到 SAP 系统</span><span class="sxs-lookup"><span data-stu-id="a13b5-142">To send an IDOC to an SAP system</span></span>  
  
1. <span data-ttu-id="a13b5-143">生成 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="a13b5-143">Generate a WCF client class.</span></span> <span data-ttu-id="a13b5-144">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 来生成 WCF 客户端类面向想要的 Idoc。</span><span class="sxs-lookup"><span data-stu-id="a13b5-144">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate the WCF client class that targets the IDOCs with which you want to work.</span></span> <span data-ttu-id="a13b5-145">有关如何生成 WCF 客户端的详细信息，请参阅[的 SAP 解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="a13b5-145">For more information about how to generate a WCF client, see [Generating a WCF Client or a WCF Service Contract for SAP Solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span> <span data-ttu-id="a13b5-146">如果你想要显式确认 Idoc，请确保生成 RfcConfirmTransID 操作 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="a13b5-146">If you want to explicitly confirm IDOCs, make sure that you generate the WCF client for the RfcConfirmTransID operation.</span></span> <span data-ttu-id="a13b5-147">操作可以找到以下节点下：</span><span class="sxs-lookup"><span data-stu-id="a13b5-147">Operations can be found under the following nodes:</span></span>  
  
   -   <span data-ttu-id="a13b5-148">SendIdoc 操作。</span><span class="sxs-lookup"><span data-stu-id="a13b5-148">SendIdoc operation.</span></span> <span data-ttu-id="a13b5-149">正下方的 IDOC 节点。</span><span class="sxs-lookup"><span data-stu-id="a13b5-149">Directly under the IDOC node.</span></span>  
  
   -   <span data-ttu-id="a13b5-150">发送操作。</span><span class="sxs-lookup"><span data-stu-id="a13b5-150">Send operation.</span></span> <span data-ttu-id="a13b5-151">在目标 IDOC 类型、 版本和发行版号与对应的节点。</span><span class="sxs-lookup"><span data-stu-id="a13b5-151">Under the node corresponding to the type, version and release number of the target IDOC.</span></span>  
  
   -   <span data-ttu-id="a13b5-152">RfcConfirmTransID 操作。</span><span class="sxs-lookup"><span data-stu-id="a13b5-152">RfcConfirmTransID operation.</span></span> <span data-ttu-id="a13b5-153">直接在 TRFC 节点中。</span><span class="sxs-lookup"><span data-stu-id="a13b5-153">Directly under the TRFC node.</span></span>  
  
2. <span data-ttu-id="a13b5-154">创建生成步骤 1 中的 WCF 客户端类的实例并指定客户端绑定。</span><span class="sxs-lookup"><span data-stu-id="a13b5-154">Create an instance of the WCF client class generated in step 1, and specify a client binding.</span></span> <span data-ttu-id="a13b5-155">指定客户端绑定涉及到指定的绑定和 WCF 客户端将使用的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="a13b5-155">Specifying a client binding involves specifying the binding and endpoint address that the WCF client will use.</span></span> <span data-ttu-id="a13b5-156">可以在代码中以强制方式或在配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a13b5-156">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="a13b5-157">有关如何指定客户端绑定的详细信息，请参阅[SAP 系统的配置客户端绑定](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="a13b5-157">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="a13b5-158">以下代码初始化从配置 IdocClient （适用于发送操作中），并设置 SAP 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="a13b5-158">The following code initializes an IdocClient (for the Send operation) from configuration and sets the credentials for the SAP system.</span></span>  
  
   ```  
   SAPBinding binding = new SAPBinding();  
  
   // Set endpoint address  
   EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
   // Create client and set credentials  
   idocClient = new IdocClient(binding, endpointAddress);  
   idocClient.ClientCredentials.UserName.UserName = "YourUserName";  
   idocClient.ClientCredentials.UserName.Password = "YourPassword";;  
   ```  
  
3. <span data-ttu-id="a13b5-159">如果你想要确认后，SAP 系统 tRFC 的适配器发送 IDOC，设置**AutoConfirmSentIdocs**属性绑定到**true**。</span><span class="sxs-lookup"><span data-stu-id="a13b5-159">If you want the adapter to confirm the tRFC on the SAP system after it sends the IDOC, set the **AutoConfirmSentIdocs** binding property to **true**.</span></span> <span data-ttu-id="a13b5-160">在打开 WCF 客户端之前，您必须执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a13b5-160">You must do this before you open the WCF client.</span></span>  
  
   ```  
   // Set AutoConfirmSentIdocs property to true  
   binding.AutoConfirmSentIdocs = true;  
   ```  
  
4. <span data-ttu-id="a13b5-161">打开 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="a13b5-161">Open the WCF client.</span></span>  
  
   ```  
   idocClient.Open();  
   ```  
  
5. <span data-ttu-id="a13b5-162">调用在步骤 2 中创建的 WCF 客户端以将 IDOC 发送到 SAP 系统上的相应方法。</span><span class="sxs-lookup"><span data-stu-id="a13b5-162">Invoke the appropriate method on the WCF client created in step 2 to send the IDOC to the SAP system.</span></span> <span data-ttu-id="a13b5-163">可以将传递的变量，其中包含一个 GUID 或设置为**null**有关**guid**参数。</span><span class="sxs-lookup"><span data-stu-id="a13b5-163">You can pass a variable that contains a GUID or that is set to **null** for the **guid** parameter.</span></span> <span data-ttu-id="a13b5-164">如果未指定一个 GUID[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]生成一个操作 (**guid**是**ref**参数)。</span><span class="sxs-lookup"><span data-stu-id="a13b5-164">If you do not specify a GUID, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] generates one for the operation (**guid** is a **ref** parameter).</span></span> <span data-ttu-id="a13b5-165">以下代码从文件读取的 IDOC （采用字符串格式），并将其发送到 SAP 系统，通过使用 SendIdoc 操作。</span><span class="sxs-lookup"><span data-stu-id="a13b5-165">The following code reads an IDOC (in string format) from a file and sends it to the SAP system by using the SendIdoc operation.</span></span>  
  
   ```  
   // Read IDOC into string variable  
   using (StreamReader reader = new StreamReader("ORDERS03.txt"))  
   {  
   idocData = reader.ReadToEnd();  
   }  
  
   //Get a new GUID to pass to SendIdoc. You can also assign a null  
   //value to have the adapter generate a GUID.  
   adapterTxGuid = Guid.NewGuid();  
  
   //Invoke SendIdoc on the client to send the IDOC to the SAP system  
   idocClient.SendIdoc(idocData, ref adapterTxGuid);  
   ```  
  
6. <span data-ttu-id="a13b5-166">如果未设置**AutoConfirmSentIdocs**属性绑定到**true** （在步骤 3 中），然后你必须确认 tRFC SAP 系统上的。</span><span class="sxs-lookup"><span data-stu-id="a13b5-166">If you did not set the **AutoConfirmSentIdocs** binding property to **true** (in step 3), then you must confirm the tRFC on the SAP system.</span></span> <span data-ttu-id="a13b5-167">为此必须调用**RfcConfirmTransID**方法**TrfcClient** （创建未显示）。</span><span class="sxs-lookup"><span data-stu-id="a13b5-167">To do this you must invoke the **RfcConfirmTransID** method on a **TrfcClient** (creation not shown).</span></span> <span data-ttu-id="a13b5-168">指定在步骤 4 中的参数返回的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a13b5-168">Specify the GUID returned in step 4 for the parameter.</span></span>  
  
   ```  
   trfcClient.RfcConfirmTransID(adapterTxGuid);  
   ```  
  
7. <span data-ttu-id="a13b5-169">关闭 WCF 客户端 (以及**TrfcClient**，如果使用) 完成后 （在已完成发送 Idoc） 后使用它。</span><span class="sxs-lookup"><span data-stu-id="a13b5-169">Close the WCF client (and **TrfcClient**, if used) when you are done using it (after you have finished sending IDOCs).</span></span>  
  
   ```  
   idocClient.Close();   
   ```  
  
### <a name="example"></a><span data-ttu-id="a13b5-170">示例</span><span class="sxs-lookup"><span data-stu-id="a13b5-170">Example</span></span>  
 <span data-ttu-id="a13b5-171">下面的示例使用 SendIdoc 方法将 IDOC 发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="a13b5-171">The following example sends an IDOC to an SAP system by using the SendIdoc method.</span></span> <span data-ttu-id="a13b5-172">从一个文件，ORDERS03.txt 读取 IDOC。</span><span class="sxs-lookup"><span data-stu-id="a13b5-172">The IDOC is read from a file, ORDERS03.txt.</span></span> <span data-ttu-id="a13b5-173">此文件包含 ORDERS03。V3.620 IDOC，且包含示例;但是，SendIdoc 操作可用于发送任何 IDOC。</span><span class="sxs-lookup"><span data-stu-id="a13b5-173">This file contains an ORDERS03.V3.620 IDOC and is included with the samples; however, the SendIdoc operation can be used to send any IDOC.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.IO;  
  
// Add WCF, WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for WCF LOB Adapter SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// This example sends a flat IDOC to the SAP system by using the SendIdoc operation.  
namespace SapIdocStringClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // variable for the IDOC client  
            IdocClient idocClient = null;  
  
            Console.WriteLine("IDOC string client sample started");  
            try  
            {  
                // Variable for the GUID  
                System.Nullable<System.Guid> adapterTxGuid;  
                // string to hold the Idoc data  
                string idocData;  
                // string to hold the SAP transaction ID (TID)  
                string sapTxId;  
  
                // The client can be configured from app.config, but it is   
                // explicitly configured here for demonstration.  
                // set AutoConfirmSentIdocs property to true  
                SAPBinding binding = new SAPBinding();  
                binding.AutoConfirmSentIdocs = true;  
  
                // Set endpoint address  
                EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPServer/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
                // Create client and set credentials  
                idocClient = new IdocClient(binding, endpointAddress);  
                idocClient.ClientCredentials.UserName.UserName = "YourUserName";  
                idocClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                // Open the client and send the Idoc  
                idocClient.Open();  
  
                // Read IDOC into string variable  
                using (StreamReader reader = new StreamReader("ORDERS03.txt"))  
                {  
                    idocData = reader.ReadToEnd();  
                }  
  
                //Get a new GUID to pass to SendIdoc. You can also assign a null.  
                //value to have the adapter generate a GUID.  
                adapterTxGuid = Guid.NewGuid();  
  
                //Invoke SendIdoc on the client to send the IDOC to the SAP system.  
                idocClient.SendIdoc(idocData, ref adapterTxGuid);  
  
                // The AutoConfirmSentIdocs binding property is set to true, so there is no need to  
                // confirm the IDOC. If this property is not set to true, you must call the   
                // RfcConfirmTransID method of a TrfcClient with adapterTxGuid to   
                // confirm the transaction on the SAP system.   
  
                // Get SAP tx id from GUID  
                sapTxId = SAPAdapterUtilities.ConvertGuidToTid((Guid) adapterTxGuid);  
  
                Console.WriteLine("IDOC sent");  
                Console.WriteLine("The SAP Transaction Id is : " + sapTxId);  
  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
                // Close the IDOC client  
                if (idocClient != null)  
                {  
                    if (idocClient.State == CommunicationState.Opened)  
                        idocClient.Close();  
                    else  
                        idocClient.Abort();  
                }  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a13b5-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="a13b5-174">See Also</span></span>  
[<span data-ttu-id="a13b5-175">使用 WCF 服务模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="a13b5-175">Develop applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)