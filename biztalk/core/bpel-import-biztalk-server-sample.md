---
title: BPEL 导入 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- examples, orchestrations
- examples, BPEL Import Wizard
- BPEL, examples
- BPEL Import Wizard, examples
- BPEL Import Wizard, orchestrations
ms.assetid: 3fc70608-ccd9-4249-b238-c09fc6551db1
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62eb5603ffca6f22e0e22f185886d0cfefb17746
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012550"
---
# <a name="bpel-import-biztalk-server-sample"></a><span data-ttu-id="7bd98-102">BPEL 导入 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="7bd98-102">BPEL Import (BizTalk Server Sample)</span></span>
<span data-ttu-id="7bd98-103">BPEL 导入示例演示如何从业务处理执行语言 (BPEL) 流程说明及其相关项目中创建业务流程。</span><span class="sxs-lookup"><span data-stu-id="7bd98-103">The BPEL Import sample demonstrates how to create an orchestration from a Business Process Execution Language (BPEL) process description and its related artifacts.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="7bd98-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="7bd98-104">What This Sample Does</span></span>  
 <span data-ttu-id="7bd98-105">Wide World Importers 是一家送货公司，为零售商提供自动送货服务。</span><span class="sxs-lookup"><span data-stu-id="7bd98-105">Wide World Importers is a shipping company that provides automated shipping services to retailers.</span></span> <span data-ttu-id="7bd98-106">具体而言，Wide World Importers 使零售商能够：</span><span class="sxs-lookup"><span data-stu-id="7bd98-106">Specifically, Wide World Importers enables retailers to:</span></span>  

- <span data-ttu-id="7bd98-107">请求订单发货</span><span class="sxs-lookup"><span data-stu-id="7bd98-107">Request order shipments</span></span>  

- <span data-ttu-id="7bd98-108">跟踪发货</span><span class="sxs-lookup"><span data-stu-id="7bd98-108">Track shipments</span></span>  

- <span data-ttu-id="7bd98-109">确认发货</span><span class="sxs-lookup"><span data-stu-id="7bd98-109">Confirm shipments</span></span>  

- <span data-ttu-id="7bd98-110">确认发货的发票和付款</span><span class="sxs-lookup"><span data-stu-id="7bd98-110">Confirm invoicing and payment for shipments</span></span>  

  <span data-ttu-id="7bd98-111">这些服务的可用性可使用 Web Services 描述语言 (WSDL) 文档表示，而 BPEL 文档则描述了产品公司申请这些服务的典型方式，以及产品公司应如何从 Wide World Importers 获得响应。</span><span class="sxs-lookup"><span data-stu-id="7bd98-111">While the availability of these services can be represented by using a Web Services Description Language (WSDL) document, a BPEL document describes the typical way in which the product companies are expected to call the services and how to expect responses from Wide World Importers.</span></span>  

  <span data-ttu-id="7bd98-112">当 Northwind Traders 请 Wide World Importers 负责处理其送货业务时，他们将得到描述整个交互过程的一份 BPEL 文件和一些相关材料。</span><span class="sxs-lookup"><span data-stu-id="7bd98-112">When Northwind Traders hires Wide World Importers to handle their shipping, they are provided a BPEL file and some related artifacts that describe the entire interaction.</span></span> <span data-ttu-id="7bd98-113">使用该 BPEL 文件，Northwind Traders 就可以创建一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序 (BPELShipping)，以便自动处理要由 Wide World Importers 负责送货的订单。</span><span class="sxs-lookup"><span data-stu-id="7bd98-113">Using the BPEL file, Northwind Traders creates a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application (BPELShipping) to automatically process orders through Wide World Importers.</span></span>  

  <span data-ttu-id="7bd98-114">本示例将指导你演练此方案，其中，BPELShipping 应用程序将完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="7bd98-114">This sample walks you through this scenario in which the BPELShipping application:</span></span>  

1. <span data-ttu-id="7bd98-115">从 Northwind Traders 客户订单系统接收订单。</span><span class="sxs-lookup"><span data-stu-id="7bd98-115">Receives an order from the Northwind Traders customer order system.</span></span>  

2. <span data-ttu-id="7bd98-116">向 Wide World Importers 发送发货请求并请求确认。</span><span class="sxs-lookup"><span data-stu-id="7bd98-116">Sends a shipping request to Wide World Importers and requests confirmation.</span></span>  

3. <span data-ttu-id="7bd98-117">从 Wide World Importers 接收发货请求确认。</span><span class="sxs-lookup"><span data-stu-id="7bd98-117">Receives shipment request confirmation from Wide World Importers.</span></span>  

4. <span data-ttu-id="7bd98-118">从 Wide World Importers 接收提货通知。</span><span class="sxs-lookup"><span data-stu-id="7bd98-118">Receives pickup notification from Wide World Importers.</span></span>  

5. <span data-ttu-id="7bd98-119">接收送货状态消息（直到客户已接收到该货物为止）。</span><span class="sxs-lookup"><span data-stu-id="7bd98-119">Receives shipment status messages up to and including when the shipment has been received by the customer.</span></span>  

6. <span data-ttu-id="7bd98-120">从 Wide World Importers 接收发票。</span><span class="sxs-lookup"><span data-stu-id="7bd98-120">Receives an invoice from Wide World Importers.</span></span>  

7. <span data-ttu-id="7bd98-121">向 Wide World Importers 发送发票确认响应。</span><span class="sxs-lookup"><span data-stu-id="7bd98-121">Responds to Wide World Importers with an invoice acknowledgment.</span></span>  

8. <span data-ttu-id="7bd98-122">从 Wide World Importers 接收付款确认。</span><span class="sxs-lookup"><span data-stu-id="7bd98-122">Receives a payment confirmation from Wide World Importers.</span></span>  

9. <span data-ttu-id="7bd98-123">向订单系统发送最终发货确认。</span><span class="sxs-lookup"><span data-stu-id="7bd98-123">Sends a final shipping confirmation to the ordering system.</span></span>  

   <span data-ttu-id="7bd98-124">我们用一个独立的 BizTalk 应用程序 (ShipperProcess) 来模拟本示例中的 Wide World Importers。</span><span class="sxs-lookup"><span data-stu-id="7bd98-124">A separate BizTalk application (ShipperProcess) is used to simulate Wide World Importers for this sample.</span></span> <span data-ttu-id="7bd98-125">BPELShipping 应用程序使用 FILE 传输与 ShipperProcess 进行通信，FILE 传输在通信中使用公用文件系统位置。</span><span class="sxs-lookup"><span data-stu-id="7bd98-125">The BPELShipping application communicates with ShipperProcess by using the FILE transport, which uses common file system locations for the communication.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="7bd98-126">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="7bd98-126">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="7bd98-127">适用于 Web Services 的 BPEL 是一种基于 XML 的语言，用以描述业务流程，使其能够在要使用 Web Services 进行业务往来的各个公司之间轻松共享。</span><span class="sxs-lookup"><span data-stu-id="7bd98-127">BPEL for Web services is an XML-based language to describe the business process so that it can be easily shared across different companies who want to do business with each other using Web services.</span></span> <span data-ttu-id="7bd98-128">BPEL 描述了如何在商业协议级别上处理业务流程，但并不描述公司的内部流程，例如，公司从合作伙伴接收到采购订单后要采取的处理步骤。</span><span class="sxs-lookup"><span data-stu-id="7bd98-128">BPEL describes how to handle the business process at the business protocol level, but it does not describe the internal process in a company, such as the steps a company would take to process a purchase order after receiving it from a partner.</span></span> <span data-ttu-id="7bd98-129">本示例用于向你演示如何导入 BPEL 和相应的 WSDL 文件，如何将它们转换成业务流程，然后开始运行与合作伙伴的业务程序。</span><span class="sxs-lookup"><span data-stu-id="7bd98-129">This sample is designed to show you how to import BPEL and corresponding WSDL files, convert them into an orchestration, and then start to run the business process with the partner.</span></span>  

 <span data-ttu-id="7bd98-130">下面的过程逐步说明如何导入 BPEL 和 WSDL 文件，以及如何将它们转换成业务流程，以便与预先生成的 BizTalk 应用程序 (ShipperProcess) 进行交互。</span><span class="sxs-lookup"><span data-stu-id="7bd98-130">The following is the step-by-step procedure showing how to import the BPEL and WSDL files and convert them into an orchestration to interact with a prebuilt BizTalk application (ShipperProcess).</span></span> <span data-ttu-id="7bd98-131">如果你完成了以下步骤，则不需要执行“生成并初始化 BPELShipping 应用程序”中描述的步骤。</span><span class="sxs-lookup"><span data-stu-id="7bd98-131">If you complete the following steps, you do not need to perform the steps described in "To build and initialize the BPELShipping application".</span></span>  

#### <a name="to-import-from-bpel-and-build-a-working-solution"></a><span data-ttu-id="7bd98-132">导入 BPEL 并生成工作解决方案</span><span class="sxs-lookup"><span data-stu-id="7bd98-132">To import from BPEL and build a working solution</span></span>  

1. <span data-ttu-id="7bd98-133">在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，单击**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-133">In Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, click **New**, and then click **Project**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="7bd98-134">在完成此过程之前，必须对 ShipperProcess 应用程序进行设置，才能创建所支持的流程和架构项目。</span><span class="sxs-lookup"><span data-stu-id="7bd98-134">Before completing this procedure, you must set up the ShipperProcess application to create the supporting processes and schema projects.</span></span>  

2. <span data-ttu-id="7bd98-135">在中**新的项目**对话框中，在项目类型窗格中，选择**BizTalk （项目）**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-135">In the **New Project** dialog box, in the Project Types pane, select **BizTalk (Projects)**.</span></span> <span data-ttu-id="7bd98-136">在模板窗格中选择**BizTalk (Server) BPEL 导入项目**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-136">In the Templates pane, select **BizTalk (Server) BPEL Import Project**.</span></span>  

3. <span data-ttu-id="7bd98-137">在中**名称**框中，输入**BPELShipping**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-137">In the **Name** box, enter **BPELShipping**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="7bd98-138">如果你使用其他名称，则在最后的绑定步骤中可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="7bd98-138">If you use a different name, you may experience problems with the final binding step.</span></span>  

4. <span data-ttu-id="7bd98-139">选择项目的位置，然后单击**确定**启动 BPEL 导入向导。</span><span class="sxs-lookup"><span data-stu-id="7bd98-139">Select a location for the project, and then click **OK** to start the BPEL Import Wizard.</span></span>  

5. <span data-ttu-id="7bd98-140">上**欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-140">On the **Welcome** page, click **Next**.</span></span>  

6. <span data-ttu-id="7bd98-141">上**选择 BPEL、 WSDL 和 XSD 文件**页上，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-141">On the **Select BPEL, WSDL, and XSD Files** page, click **Browse**.</span></span>  

7. <span data-ttu-id="7bd98-142">选择中的所有文件\<*示例路径*\>\Orchestrations\BPELImport\BPELSource 文件夹中，单击**打开**，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="7bd98-142">Select all the files from the \<*Samples Path*\>\Orchestrations\BPELImport\BPELSource folder, click **Open**, and then click **Next**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="7bd98-143">在此步骤中，你将选择用于描述业务流程的 BPEL 和 WSDL 文件以及表述业务文档架构的 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="7bd98-143">In this step, you select the BPEL and WSDL files to describe the business process and the XSD files to represent the business document schemas.</span></span>  

8. <span data-ttu-id="7bd98-144">上**为 Invoked WebServices 选择 WSDL 文件**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-144">On the **Select WSDL Files for Invoked WebServices** page, click **Finish**.</span></span>  

9. <span data-ttu-id="7bd98-145">在 BPEL 导入向导报告成功导入后，关闭该向导。</span><span class="sxs-lookup"><span data-stu-id="7bd98-145">After the BPEL Import Wizard reports a successful import, close the wizard.</span></span> <span data-ttu-id="7bd98-146">现在项目即已创建。</span><span class="sxs-lookup"><span data-stu-id="7bd98-146">The project is now created.</span></span>  

10. <span data-ttu-id="7bd98-147">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 为项目位置。</span><span class="sxs-lookup"><span data-stu-id="7bd98-147">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the project location.</span></span>  

11. <span data-ttu-id="7bd98-148">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7bd98-148">Run the following command:</span></span>  

     <span data-ttu-id="7bd98-149">**sn – k BPELShipping.snk**</span><span class="sxs-lookup"><span data-stu-id="7bd98-149">**sn –k BPELShipping.snk**</span></span>  

12. <span data-ttu-id="7bd98-150">在解决方案资源管理器中右键单击**BPELShipping**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-150">In Solution Explorer, right-click the **BPELShipping** project, and then click **Properties**.</span></span>  

13. <span data-ttu-id="7bd98-151">下**常见属性**，选择程序集密钥文件**BPELShipping.snk**步骤 11 中创建，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-151">Under **Common Properties\Assembly**, select the assembly key file **BPELShipping.snk** created in step 11, and then click **OK**.</span></span>  

14. <span data-ttu-id="7bd98-152">在解决方案资源管理器中，选择所有 .xsd 文件，然后删除它们。</span><span class="sxs-lookup"><span data-stu-id="7bd98-152">In Solution Explorer, select all the .xsd files and delete them.</span></span>  

15. <span data-ttu-id="7bd98-153">在解决方案资源管理器中选择**添加引用**，然后在**项目**选项卡上，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-153">In Solution Explorer, select **Add Reference**, and on the **Projects** tab, click **Browse**.</span></span>  

16. <span data-ttu-id="7bd98-154">选择**ShippingSchemas.dll**从位置\<*示例路径*\>\Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development，和然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-154">Select **ShippingSchemas.dll** from the location \<*Samples Path*\>\Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development, and then click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="7bd98-155">“生成并初始化 ShipperProcess 应用程序”部分中说明了如何生成此应用程序。</span><span class="sxs-lookup"><span data-stu-id="7bd98-155">The section "To build and initialize the ShipperProcess application" has instructions on how to build this.</span></span>  

17. <span data-ttu-id="7bd98-156">在解决方案资源管理器中双击**OrderShippingProcess.bpel.odx**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-156">In Solution Explorer, double-click **OrderShippingProcess.bpel.odx**.</span></span>  

18. <span data-ttu-id="7bd98-157">上**视图**菜单中，选择**其他 Windows/业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-157">On the **View** menu, select **Other Windows/Orchestration View**.</span></span>  

19. <span data-ttu-id="7bd98-158">在业务流程视图窗口中，右键单击**业务流程属性**，然后单击**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-158">In the Orchestration View window, right-click **Orchestration Properties** and then click **Properties Window**.</span></span>  

20. <span data-ttu-id="7bd98-159">在属性窗口中设置**业务流程可导出**属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-159">In the Properties window, set the **Orchestration Exportable** property to **False**.</span></span>  

21. <span data-ttu-id="7bd98-160">在解决方案资源管理器中双击**OrderShipping.wsdl.odx**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-160">In Solution Explorer, double-click **OrderShipping.wsdl.odx**.</span></span>  

22. <span data-ttu-id="7bd98-161">在业务流程视图窗口中，展开**类型/多部分消息类型**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-161">In the Orchestration View window, expand **Types/Multipart Message Types**.</span></span>  

23. <span data-ttu-id="7bd98-162">展开**InvoiceAckMessageType** ，然后单击**InvoiceAckMessagePart**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-162">Expand **InvoiceAckMessageType** and then click **InvoiceAckMessagePart**.</span></span>  

24. <span data-ttu-id="7bd98-163">在属性窗口中，展开**类型**字段，然后选择**从引用的程序集的架构/选择**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-163">In the Properties window, expand the **Type** field, and select **Schemas/Select from referenced Assembly**.</span></span>  

25. <span data-ttu-id="7bd98-164">在中**选择项目类型**对话框中，单击**ShippingSchemas**，选择**Imported_InvoiceAckMessage**键入，然后依次**确定**.</span><span class="sxs-lookup"><span data-stu-id="7bd98-164">In the **Select Artifact Type** dialog box, click **ShippingSchemas**, select the **Imported_InvoiceAckMessage** type, and then click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="7bd98-165">通过步骤 23 至 25，将参与 BPEL 流程的服务的消息类型替换为 ShippingSchemas 中描述的相应消息类型。</span><span class="sxs-lookup"><span data-stu-id="7bd98-165">In steps 23 through 25, you replace the message type of the services that participate in the BPEL process to the corresponding message types described in the ShippingSchemas.</span></span>  

26. <span data-ttu-id="7bd98-166">使用以下值对每种消息类型重复步骤 23 至 25。</span><span class="sxs-lookup"><span data-stu-id="7bd98-166">Repeat steps 23 through 25 for each message type using the following values.</span></span>  


    |          <span data-ttu-id="7bd98-167">消息部分</span><span class="sxs-lookup"><span data-stu-id="7bd98-167">Message part</span></span>          |                    <span data-ttu-id="7bd98-168">消息类型</span><span class="sxs-lookup"><span data-stu-id="7bd98-168">Message type</span></span>                     |
    |--------------------------------|-----------------------------------------------------|
    |       <span data-ttu-id="7bd98-169">InvoiceMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-169">InvoiceMessagePart</span></span>       |       <span data-ttu-id="7bd98-170">ShippingSchemas.Imported_InvoiceMessage</span><span class="sxs-lookup"><span data-stu-id="7bd98-170">ShippingSchemas.Imported_InvoiceMessage</span></span>       |
    |      <span data-ttu-id="7bd98-171">OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-171">OrderAckMessagePart</span></span>       |      <span data-ttu-id="7bd98-172">ShippingSchemas.Imported_OrderAckMessage</span><span class="sxs-lookup"><span data-stu-id="7bd98-172">ShippingSchemas.Imported_OrderAckMessage</span></span>       |
    |        <span data-ttu-id="7bd98-173">OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-173">OrderMessagePart</span></span>        |        <span data-ttu-id="7bd98-174">ShippingSchemas.Imported_OrderMessage</span><span class="sxs-lookup"><span data-stu-id="7bd98-174">ShippingSchemas.Imported_OrderMessage</span></span>        |
    | <span data-ttu-id="7bd98-175">PaymentConfirmationMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-175">PaymentConfirmationMessagePart</span></span> | <span data-ttu-id="7bd98-176">ShippingSchemas.Imported_PaymentConfirmationMessage</span><span class="sxs-lookup"><span data-stu-id="7bd98-176">ShippingSchemas.Imported_PaymentConfirmationMessage</span></span> |
    | <span data-ttu-id="7bd98-177">PickupNotificationMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-177">PickupNotificationMessagePart</span></span>  | <span data-ttu-id="7bd98-178">ShippingSchemas.Imported_PickupNotificationMessage</span><span class="sxs-lookup"><span data-stu-id="7bd98-178">ShippingSchemas.Imported_PickupNotificationMessage</span></span>  |
    |  <span data-ttu-id="7bd98-179">ShipConfirmationMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-179">ShipConfirmationMessagePart</span></span>   |  <span data-ttu-id="7bd98-180">ShippingSchemas.Imported_ShipConfirmationMessage</span><span class="sxs-lookup"><span data-stu-id="7bd98-180">ShippingSchemas.Imported_ShipConfirmationMessage</span></span>   |
    |      <span data-ttu-id="7bd98-181">ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="7bd98-181">ShippingHistoryPart</span></span>       |      <span data-ttu-id="7bd98-182">ShippingSchemas.Imported_ShippingHistory</span><span class="sxs-lookup"><span data-stu-id="7bd98-182">ShippingSchemas.Imported_ShippingHistory</span></span>       |
    |   <span data-ttu-id="7bd98-183">ShipRequestAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-183">ShipRequestAckMessagePart</span></span>    |   <span data-ttu-id="7bd98-184">ShippingSchemas.Imported_ShipRequestAckMessage</span><span class="sxs-lookup"><span data-stu-id="7bd98-184">ShippingSchemas.Imported_ShipRequestAckMessage</span></span>    |
    |     <span data-ttu-id="7bd98-185">ShipRequestMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-185">ShipRequestMessagePart</span></span>     |     <span data-ttu-id="7bd98-186">ShippingSchemas.Imported_ShipRequestMessage</span><span class="sxs-lookup"><span data-stu-id="7bd98-186">ShippingSchemas.Imported_ShipRequestMessage</span></span>     |
    |     <span data-ttu-id="7bd98-187">ShipStatusMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-187">ShipStatusMessagePart</span></span>      |     <span data-ttu-id="7bd98-188">ShippingSchemas.Imported_ShipStatusMessage</span><span class="sxs-lookup"><span data-stu-id="7bd98-188">ShippingSchemas.Imported_ShipStatusMessage</span></span>      |


27. <span data-ttu-id="7bd98-189">在解决方案资源管理器中右键单击**BPELShipping**项目，指向**添加**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-189">In Solution Explorer, right-click the **BPELShipping** project, point to **Add**, and then click **Existing Item**.</span></span>  

28. <span data-ttu-id="7bd98-190">从位置选择所有.btm 文件\<*示例路径*\>\Orchestrations\BPELImport\Solution\BPELShipping\BPELShipping。</span><span class="sxs-lookup"><span data-stu-id="7bd98-190">Select all the .btm files from the location \<*Samples Path*\>\Orchestrations\BPELImport\Solution\BPELShipping\BPELShipping.</span></span>  

29. <span data-ttu-id="7bd98-191">在业务流程视图窗口中，找到**消息赋值**形状命名的 MessageAssignment_1 揅 constructmessage1 中，然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="7bd98-191">In the Orchestration View window, locate the **Message Assignment** shape named MessageAssignment_1 in ConstructMessage1 and delete it.</span></span>  

30. <span data-ttu-id="7bd98-192">从工具箱拖动**转换**形状揅 constructmessage1 形状。</span><span class="sxs-lookup"><span data-stu-id="7bd98-192">From the Toolbox, drag a **Transform** shape into the ConstructMessage1 shape.</span></span>  

31. <span data-ttu-id="7bd98-193">在属性窗口中，单击省略号按钮 (**...**)，然后打开**转换配置**对话框。</span><span class="sxs-lookup"><span data-stu-id="7bd98-193">In the Properties window, click the ellipsis button (**…**) and open the **Transform Configuration** dialog box.</span></span>  

32. <span data-ttu-id="7bd98-194">选择**现有的映射**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-194">Select **Existing Map**.</span></span>  

33. <span data-ttu-id="7bd98-195">选择作为完全限定的映射名称**BPELShipping.Order2ShipRequest**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-195">Select the fully qualified map name as **BPELShipping.Order2ShipRequest**.</span></span>  

34. <span data-ttu-id="7bd98-196">选择作为源**顺序。OrderMessagePart**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-196">Select the source as **order.OrderMessagePart**.</span></span>  

35. <span data-ttu-id="7bd98-197">选择作为目标**ship_request。ShipRequestMessagePart**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-197">Select the destination as **ship_request.ShipRequestMessagePart** and click **OK**.</span></span>  

36. <span data-ttu-id="7bd98-198">为每个重复步骤 29 至 35**消息赋值**形状并将其替换为**转换**根据下表的形状。</span><span class="sxs-lookup"><span data-stu-id="7bd98-198">Repeat steps 29 through 35 for each of the **Message Assignment** shapes and replace them with **Transform** shapes according to the following table.</span></span>  


    |  <span data-ttu-id="7bd98-199">要替换的形状</span><span class="sxs-lookup"><span data-stu-id="7bd98-199">Shape to replace</span></span>   |              <span data-ttu-id="7bd98-200">使用的映射</span><span class="sxs-lookup"><span data-stu-id="7bd98-200">Map to use</span></span>              |      <span data-ttu-id="7bd98-201">源文档</span><span class="sxs-lookup"><span data-stu-id="7bd98-201">Source document</span></span>       |       <span data-ttu-id="7bd98-202">目标文档</span><span class="sxs-lookup"><span data-stu-id="7bd98-202">Destination document</span></span>        |
    |---------------------|--------------------------------------|----------------------------|-----------------------------------|
    | <span data-ttu-id="7bd98-203">MessageAssignment_2</span><span class="sxs-lookup"><span data-stu-id="7bd98-203">MessageAssignment_2</span></span> |     <span data-ttu-id="7bd98-204">BPELShipping.Order2OrderAck</span><span class="sxs-lookup"><span data-stu-id="7bd98-204">BPELShipping.Order2OrderAck</span></span>      |   <span data-ttu-id="7bd98-205">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-205">order.OrderMessagePart</span></span>   |   <span data-ttu-id="7bd98-206">order_ack.OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-206">order_ack.OrderAckMessagePart</span></span>   |
    | <span data-ttu-id="7bd98-207">MessageAssignment_3</span><span class="sxs-lookup"><span data-stu-id="7bd98-207">MessageAssignment_3</span></span> |     <span data-ttu-id="7bd98-208">BPELShipping.Order2OrderNAck</span><span class="sxs-lookup"><span data-stu-id="7bd98-208">BPELShipping.Order2OrderNAck</span></span>     |   <span data-ttu-id="7bd98-209">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-209">order.OrderMessagePart</span></span>   |   <span data-ttu-id="7bd98-210">order_ack.OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-210">order_ack.OrderAckMessagePart</span></span>   |
    | <span data-ttu-id="7bd98-211">MessageAssignment_4</span><span class="sxs-lookup"><span data-stu-id="7bd98-211">MessageAssignment_4</span></span> |    <span data-ttu-id="7bd98-212">BPELShipping.Order2ShipHistory</span><span class="sxs-lookup"><span data-stu-id="7bd98-212">BPELShipping.Order2ShipHistory</span></span>    |   <span data-ttu-id="7bd98-213">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-213">order.OrderMessagePart</span></span>   | <span data-ttu-id="7bd98-214">ship_history.ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="7bd98-214">ship_history.ShippingHistoryPart</span></span>  |
    | <span data-ttu-id="7bd98-215">MessageAssignment_5</span><span class="sxs-lookup"><span data-stu-id="7bd98-215">MessageAssignment_5</span></span> |  <span data-ttu-id="7bd98-216">BPELShipping.ShipHistory2Completed</span><span class="sxs-lookup"><span data-stu-id="7bd98-216">BPELShipping.ShipHistory2Completed</span></span>  |   <span data-ttu-id="7bd98-217">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-217">order.OrderMessagePart</span></span>   | <span data-ttu-id="7bd98-218">ship_history.ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="7bd98-218">ship_history.ShippingHistoryPart</span></span>  |
    | <span data-ttu-id="7bd98-219">MessageAssignment_6</span><span class="sxs-lookup"><span data-stu-id="7bd98-219">MessageAssignment_6</span></span> |       <span data-ttu-id="7bd98-220">BPELShipping.Invoice2Ack</span><span class="sxs-lookup"><span data-stu-id="7bd98-220">BPELShipping.Invoice2Ack</span></span>       | <span data-ttu-id="7bd98-221">invoice.InvoiceMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-221">invoice.InvoiceMessagePart</span></span> | <span data-ttu-id="7bd98-222">invoice_ack.InvoiceAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-222">invoice_ack.InvoiceAckMessagePart</span></span> |
    | <span data-ttu-id="7bd98-223">MessageAssignment_7</span><span class="sxs-lookup"><span data-stu-id="7bd98-223">MessageAssignment_7</span></span> | <span data-ttu-id="7bd98-224">BPELShipping.Order2FinalConfirmation</span><span class="sxs-lookup"><span data-stu-id="7bd98-224">BPELShipping.Order2FinalConfirmation</span></span> |   <span data-ttu-id="7bd98-225">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-225">order.OrderMessagePart</span></span>   | <span data-ttu-id="7bd98-226">order_shipped.OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="7bd98-226">order_shipped.OrderAckMessagePart</span></span> |


37. <span data-ttu-id="7bd98-227">保存该业务流程。</span><span class="sxs-lookup"><span data-stu-id="7bd98-227">Save the orchestration.</span></span>  

38. <span data-ttu-id="7bd98-228">双击**Rule_1**中**判定**形状**Decision_1**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-228">Double-click **Rule_1** in the **Decide** shape **Decision_1**.</span></span>  

39. <span data-ttu-id="7bd98-229">在 BizTalk 表达式编辑器中，将</span><span class="sxs-lookup"><span data-stu-id="7bd98-229">In BizTalk Expression Editor, replace</span></span>  

     <span data-ttu-id="7bd98-230">ship_request_ack(BPELShipping.Ship_Acknowledged) == true</span><span class="sxs-lookup"><span data-stu-id="7bd98-230">ship_request_ack(BPELShipping.Ship_Acknowledged) == true</span></span>  

     <span data-ttu-id="7bd98-231">使用</span><span class="sxs-lookup"><span data-stu-id="7bd98-231">with</span></span>  

     <span data-ttu-id="7bd98-232">ship_request_ack(ShippingSchemas.Ship_Acknowledged) == true</span><span class="sxs-lookup"><span data-stu-id="7bd98-232">ship_request_ack(ShippingSchemas.Ship_Acknowledged) == true</span></span>  

40. <span data-ttu-id="7bd98-233">双击**循环**名为形状**Loop_1**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-233">Double-click the **Loop** shape named **Loop_1**.</span></span>  

41. <span data-ttu-id="7bd98-234">在 BizTalk 表达式编辑器中，将</span><span class="sxs-lookup"><span data-stu-id="7bd98-234">In BizTalk Expression Editor, replace</span></span>  

     <span data-ttu-id="7bd98-235">ship_history(BPELShipping.Ship_Completed) == true</span><span class="sxs-lookup"><span data-stu-id="7bd98-235">ship_history(BPELShipping.Ship_Completed) == true</span></span>  

     <span data-ttu-id="7bd98-236">使用</span><span class="sxs-lookup"><span data-stu-id="7bd98-236">with</span></span>  

     <span data-ttu-id="7bd98-237">ship_history(ShippingSchemas.Ship_Completed) == true</span><span class="sxs-lookup"><span data-stu-id="7bd98-237">ship_history(ShippingSchemas.Ship_Completed) == true</span></span>  

42. <span data-ttu-id="7bd98-238">双击**Rule_2**中**判定**形状**Decision_2**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-238">Double-click **Rule_2** in the **Decide** shape **Decision_2**.</span></span>  

43. <span data-ttu-id="7bd98-239">在 BizTalk 表达式编辑器中，将</span><span class="sxs-lookup"><span data-stu-id="7bd98-239">In BizTalk Expression Editor, replace</span></span>  

     <span data-ttu-id="7bd98-240">ship_status(BPELShipping.ShipStatus) == "DONE"</span><span class="sxs-lookup"><span data-stu-id="7bd98-240">ship_status(BPELShipping.ShipStatus) == "DONE"</span></span>  

     <span data-ttu-id="7bd98-241">使用</span><span class="sxs-lookup"><span data-stu-id="7bd98-241">with</span></span>  

     <span data-ttu-id="7bd98-242">ship_status(ShippingSchemas.ShipStatus) == "DONE"</span><span class="sxs-lookup"><span data-stu-id="7bd98-242">ship_status(ShippingSchemas.ShipStatus) == "DONE"</span></span>  

44. <span data-ttu-id="7bd98-243">在业务流程视图中，展开**类型/相关类型**然后单击***OrderCorrelationSet_Type\\***。</span><span class="sxs-lookup"><span data-stu-id="7bd98-243">In the Orchestration View, expand **Types/Correlation Types** and click ***OrderCorrelationSet_Type\\***.</span></span>  

45. <span data-ttu-id="7bd98-244">在属性窗口中，单击省略号按钮 (**...**) 上**相关属性**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-244">In the Properties window, click the ellipsis button (**…**) on **Correlation Properties**.</span></span>  

46. <span data-ttu-id="7bd98-245">在上窗格相关联的属性，单击**BPELShipping.OrderID**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-245">In the Properties to correlate on pane, click **BPELShipping.OrderID**, and then click **Remove**.</span></span>  

47. <span data-ttu-id="7bd98-246">在可用属性窗格中，展开**发货架构**，选择**订单 ID**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-246">In the Available Properties pane, expand **Shipping Schemas**, select **Order ID**, and then click **Add**.</span></span>  

48. <span data-ttu-id="7bd98-247">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="7bd98-247">Click **OK**.</span></span>  

49. <span data-ttu-id="7bd98-248">保存所有文件并生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="7bd98-248">Save all the files and build the solution.</span></span>  

50. <span data-ttu-id="7bd98-249">部署该解决方案。</span><span class="sxs-lookup"><span data-stu-id="7bd98-249">Deploy the solution.</span></span>  

51. <span data-ttu-id="7bd98-250">浏览到的位置\<*示例路径*\>\Orchestrations\BPELImport\Solution\BPELShipping，然后双击**BindAndStartOnly.bat**绑定和启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="7bd98-250">Browse to the location \<*Samples Path*\>\Orchestrations\BPELImport\Solution\BPELShipping and double-click **BindAndStartOnly.bat** to bind and start the orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="7bd98-251">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="7bd98-251">Where to Find This Sample</span></span>  
 <span data-ttu-id="7bd98-252">*\<示例路径\>* \Orchestrations\BPELImport</span><span class="sxs-lookup"><span data-stu-id="7bd98-252">*\<Samples Path\>* \Orchestrations\BPELImport</span></span>  

 <span data-ttu-id="7bd98-253">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="7bd98-253">The following table shows the files in this sample and describes their purpose.</span></span>  

|<span data-ttu-id="7bd98-254">文件</span><span class="sxs-lookup"><span data-stu-id="7bd98-254">File(s)</span></span>|<span data-ttu-id="7bd98-255">Description</span><span class="sxs-lookup"><span data-stu-id="7bd98-255">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7bd98-256">BPELSource\InvoiceAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-256">BPELSource\InvoiceAckMessage.xsd</span></span>|<span data-ttu-id="7bd98-257">发票确认架构。</span><span class="sxs-lookup"><span data-stu-id="7bd98-257">Invoice acknowledgment schema.</span></span>|  
|<span data-ttu-id="7bd98-258">BPELSource\InvoiceMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-258">BPELSource\InvoiceMessage.xsd</span></span>|<span data-ttu-id="7bd98-259">发票架构。</span><span class="sxs-lookup"><span data-stu-id="7bd98-259">Invoice schema.</span></span>|  
|<span data-ttu-id="7bd98-260">BPELSource\OrderAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-260">BPELSource\OrderAckMessage.xsd</span></span>|<span data-ttu-id="7bd98-261">订单确认架构。</span><span class="sxs-lookup"><span data-stu-id="7bd98-261">Order acknowledgment schema.</span></span>|  
|<span data-ttu-id="7bd98-262">BPELSource\OrderHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-262">BPELSource\OrderHeader.xsd</span></span>|<span data-ttu-id="7bd98-263">订单头部架构。</span><span class="sxs-lookup"><span data-stu-id="7bd98-263">Order header schema.</span></span>|  
|<span data-ttu-id="7bd98-264">BPELSource\OrderMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-264">BPELSource\OrderMessage.xsd</span></span>|<span data-ttu-id="7bd98-265">订单消息架构。</span><span class="sxs-lookup"><span data-stu-id="7bd98-265">Order message schema.</span></span>|  
|<span data-ttu-id="7bd98-266">BPELSource\OrderShipping.wsdl</span><span class="sxs-lookup"><span data-stu-id="7bd98-266">BPELSource\OrderShipping.wsdl</span></span>|<span data-ttu-id="7bd98-267">BPEL 引用的 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="7bd98-267">WSDL file referred to by BPEL.</span></span>|  
|<span data-ttu-id="7bd98-268">BPELSource\OrderShippingProcess.bpel</span><span class="sxs-lookup"><span data-stu-id="7bd98-268">BPELSource\OrderShippingProcess.bpel</span></span>|<span data-ttu-id="7bd98-269">BPEL 处理流程。</span><span class="sxs-lookup"><span data-stu-id="7bd98-269">BPEL process flow.</span></span>|  
|<span data-ttu-id="7bd98-270">BPELSource\PaymentConfirmationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-270">BPELSource\PaymentConfirmationMessage.xsd</span></span>|<span data-ttu-id="7bd98-271">付款确认消息。</span><span class="sxs-lookup"><span data-stu-id="7bd98-271">Payment confirmation message.</span></span>|  
|<span data-ttu-id="7bd98-272">BPELSource\PickupNotificationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-272">BPELSource\PickupNotificationMessage.xsd</span></span>|<span data-ttu-id="7bd98-273">提货通知消息。</span><span class="sxs-lookup"><span data-stu-id="7bd98-273">Pickup notification message.</span></span>|  
|<span data-ttu-id="7bd98-274">BPELSource\ShipConfirmationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-274">BPELSource\ShipConfirmationMessage.xsd</span></span>|<span data-ttu-id="7bd98-275">发货确认消息。</span><span class="sxs-lookup"><span data-stu-id="7bd98-275">Shipment confirmation message.</span></span>|  
|<span data-ttu-id="7bd98-276">BPELSource\ShippingHistory.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-276">BPELSource\ShippingHistory.xsd</span></span>|<span data-ttu-id="7bd98-277">发货历史记录文档。</span><span class="sxs-lookup"><span data-stu-id="7bd98-277">Shipping history document.</span></span>|  
|<span data-ttu-id="7bd98-278">BPELSource\ShipRequestAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-278">BPELSource\ShipRequestAckMessage.xsd</span></span>|<span data-ttu-id="7bd98-279">发货请求确认。</span><span class="sxs-lookup"><span data-stu-id="7bd98-279">Ship request acknowledgment.</span></span>|  
|<span data-ttu-id="7bd98-280">BPELSource\ShipRequestMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-280">BPELSource\ShipRequestMessage.xsd</span></span>|<span data-ttu-id="7bd98-281">发货请求消息。</span><span class="sxs-lookup"><span data-stu-id="7bd98-281">Ship request message.</span></span>|  
|<span data-ttu-id="7bd98-282">BPELSource\ShipStatusMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="7bd98-282">BPELSource\ShipStatusMessage.xsd</span></span>|<span data-ttu-id="7bd98-283">发货状态消息。</span><span class="sxs-lookup"><span data-stu-id="7bd98-283">Ship status message.</span></span>|  
|<span data-ttu-id="7bd98-284">Solution\bindings\BPELBindings.xml</span><span class="sxs-lookup"><span data-stu-id="7bd98-284">Solution\bindings\BPELBindings.xml</span></span>|<span data-ttu-id="7bd98-285">指定 BPELShipping 业务流程的端口绑定的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="7bd98-285">Binding file specifying port bindings for the BPELShipping orchestration.</span></span>|  
|<span data-ttu-id="7bd98-286">Solution\bindings\ShipperBindings.xml</span><span class="sxs-lookup"><span data-stu-id="7bd98-286">Solution\bindings\ShipperBindings.xml</span></span>|<span data-ttu-id="7bd98-287">指定 ShipperProcess 业务流程的端口绑定的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="7bd98-287">Binding file specifying port bindings for the ShipperProcess orchestration.</span></span>|  
|<span data-ttu-id="7bd98-288">Solution\BPELShipping\BindAndStartOnly.bat</span><span class="sxs-lookup"><span data-stu-id="7bd98-288">Solution\BPELShipping\BindAndStartOnly.bat</span></span>|<span data-ttu-id="7bd98-289">在已手动生成和部署 BPELImport 业务流程后，用于绑定和启动该业务流程的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="7bd98-289">Batch file to use for binding and starting the BPELImport orchestration after it has been built manually and deployed.</span></span>|  
|<span data-ttu-id="7bd98-290">Solution\BPELShipping\cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="7bd98-290">Solution\BPELShipping\cleanup.bat</span></span>|<span data-ttu-id="7bd98-291">用于删除 BPELShipping 流程的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="7bd98-291">Batch file to use to remove the BPELShipping process.</span></span>|  
|<span data-ttu-id="7bd98-292">Solution\BPELShipping\Setup.bat</span><span class="sxs-lookup"><span data-stu-id="7bd98-292">Solution\BPELShipping\Setup.bat</span></span>|<span data-ttu-id="7bd98-293">用于安装和启动所提供的 BPELShipping 示例的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="7bd98-293">Batch file to use to install and start the provided BPELShipping sample.</span></span>|  
|<span data-ttu-id="7bd98-294">Solution\BPELShipping\BPELShipping.sln</span><span class="sxs-lookup"><span data-stu-id="7bd98-294">Solution\BPELShipping\BPELShipping.sln</span></span>|<span data-ttu-id="7bd98-295">预先生成的 BPELShipping 示例。</span><span class="sxs-lookup"><span data-stu-id="7bd98-295">The prebuilt BPELShipping sample.</span></span>|  
<span data-ttu-id="7bd98-296">olution\BPELShipping\BPELShipping\Invoice2Ack.btm</span><span class="sxs-lookup"><span data-stu-id="7bd98-296">olution\BPELShipping\BPELShipping\Invoice2Ack.btm</span></span>|<span data-ttu-id="7bd98-297">从开发票到发票确认的映射。</span><span class="sxs-lookup"><span data-stu-id="7bd98-297">Invoice to invoice acknowledgment map.</span></span>|  
|<span data-ttu-id="7bd98-298">Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm</span><span class="sxs-lookup"><span data-stu-id="7bd98-298">Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm</span></span>|<span data-ttu-id="7bd98-299">将订单消息转换为最终发货确认的映射。</span><span class="sxs-lookup"><span data-stu-id="7bd98-299">Map to convert from Order message to final shipment confirmation.</span></span>|  
|<span data-ttu-id="7bd98-300">Solution\BPELShipping\BPELShipping\Order2OrderAck.btm</span><span class="sxs-lookup"><span data-stu-id="7bd98-300">Solution\BPELShipping\BPELShipping\Order2OrderAck.btm</span></span>|<span data-ttu-id="7bd98-301">将订单消息转换为订单确认的映射。</span><span class="sxs-lookup"><span data-stu-id="7bd98-301">Map to convert from Order message to order acknowledgment.</span></span>|  
|<span data-ttu-id="7bd98-302">Solution\BPELShipping\BPELShipping\Order2OrderNack.btm</span><span class="sxs-lookup"><span data-stu-id="7bd98-302">Solution\BPELShipping\BPELShipping\Order2OrderNack.btm</span></span>|<span data-ttu-id="7bd98-303">将订单消息转换为订单否定确认的映射。</span><span class="sxs-lookup"><span data-stu-id="7bd98-303">Map to convert from Order message to order negative acknowledgment.</span></span>|  
|<span data-ttu-id="7bd98-304">Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm</span><span class="sxs-lookup"><span data-stu-id="7bd98-304">Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm</span></span>|<span data-ttu-id="7bd98-305">将订单消息转换为发货历史记录文档的映射。</span><span class="sxs-lookup"><span data-stu-id="7bd98-305">Map to convert from Order message to Shipping history document.</span></span>|  
|<span data-ttu-id="7bd98-306">Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm</span><span class="sxs-lookup"><span data-stu-id="7bd98-306">Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm</span></span>|<span data-ttu-id="7bd98-307">将订单消息转换为订单发货请求的映射。</span><span class="sxs-lookup"><span data-stu-id="7bd98-307">Map to convert from Order message to order Shipping request.</span></span>|  
|<span data-ttu-id="7bd98-308">Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm</span><span class="sxs-lookup"><span data-stu-id="7bd98-308">Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm</span></span>|<span data-ttu-id="7bd98-309">将发货历史记录设置为已完成的映射。</span><span class="sxs-lookup"><span data-stu-id="7bd98-309">Map to set the Shipping history to completed.</span></span>|  
|<span data-ttu-id="7bd98-310">Solution\ShipperProcess\setup.bat</span><span class="sxs-lookup"><span data-stu-id="7bd98-310">Solution\ShipperProcess\setup.bat</span></span>|<span data-ttu-id="7bd98-311">用于生成、部署、绑定和启动 ShipperProcess 助手业务流程及其端口的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="7bd98-311">Batch file to build, deploy, bind, and start the ShipperProcess helper orchestration and its ports.</span></span>|  
|<span data-ttu-id="7bd98-312">Solution\ShipperProcess\cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="7bd98-312">Solution\ShipperProcess\cleanup.bat</span></span>|<span data-ttu-id="7bd98-313">用于停止、取消登记和取消部署 ShipperProcess 助手业务流程及其端口的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="7bd98-313">Batch file to stop, unenlist, and undeploy the ShipperProcess helper orchestration and its ports.</span></span>|  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="7bd98-314">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="7bd98-314">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="7bd98-315">第一步是生成并初始化用于模拟 Wide World Importers 的 ShipperProcess 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7bd98-315">The first step is to build and initialize the ShipperProcess application used to simulate Wide World Importers.</span></span>  

#### <a name="to-build-and-initialize-the-shipperprocess-application"></a><span data-ttu-id="7bd98-316">生成并初始化 ShipperProcess 应用程序</span><span class="sxs-lookup"><span data-stu-id="7bd98-316">To build and initialize the ShipperProcess application</span></span>  

1. <span data-ttu-id="7bd98-317">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="7bd98-317">Start **Visual Studio Command Prompt**.</span></span>  

2. <span data-ttu-id="7bd98-318">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="7bd98-318">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the following folder:</span></span>  

    <span data-ttu-id="7bd98-319">*\<示例路径\>* \Orchestrations\BPELImport\Solution\ShipperProcess</span><span class="sxs-lookup"><span data-stu-id="7bd98-319">*\<Samples Path\>* \Orchestrations\BPELImport\Solution\ShipperProcess</span></span>  

3. <span data-ttu-id="7bd98-320">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7bd98-320">Run the file Setup.bat, which performs the following actions:</span></span>  

   -   <span data-ttu-id="7bd98-321">生成 ShippingSchemas 项目，它包含 ShipperProcess 和 BPELShipping 流程使用的架构</span><span class="sxs-lookup"><span data-stu-id="7bd98-321">Builds the ShippingSchemas project, which contains the schemas used in the ShipperProcess and the BPELShipping process</span></span>  

   -   <span data-ttu-id="7bd98-322">生成 ShipperProcess</span><span class="sxs-lookup"><span data-stu-id="7bd98-322">Builds the ShipperProcess</span></span>  

   -   <span data-ttu-id="7bd98-323">部署 ShippingSchemas 和 ShipperProcess 项目</span><span class="sxs-lookup"><span data-stu-id="7bd98-323">Deploys the ShippingSchemas and ShipperProcess projects</span></span>  

   -   <span data-ttu-id="7bd98-324">创建并绑定 ShipperProcess 使用的发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="7bd98-324">Creates and binds the send and receive ports used by ShipperProcess</span></span>  

   -   <span data-ttu-id="7bd98-325">启动 ShipperProcess 使用的端口</span><span class="sxs-lookup"><span data-stu-id="7bd98-325">Starts the ports used by ShipperProcess</span></span>  

   -   <span data-ttu-id="7bd98-326">登记并启动 ShipperProcess 业务流程</span><span class="sxs-lookup"><span data-stu-id="7bd98-326">Enlists and starts the ShipperProcess orchestration</span></span>  

   <span data-ttu-id="7bd98-327">在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="7bd98-327">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span> <span data-ttu-id="7bd98-328">可能会显示下面的一条或多条警告，你可以忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="7bd98-328">One or more of the following warnings may be displayed; you can ignore these.</span></span>  

```  
The 'http://contoso.org/samples/Fragments:XXXX' element is not declared. An error occurred at , (35, 16).  
<SAMPLE_LOCATION>\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(667,22): convoy found at 'activate receive(Receive_ShipOrder.Operation_1, Request, initialize Correl)'  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): and 'receive(ReceiveInvoiceAck.Operation_1, Invoice_Ack, Correl)'  
```  

> [!NOTE]
>  <span data-ttu-id="7bd98-329">如果已完成“导入 BPEL 并生成工作解决方案”中的步骤，则无需执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7bd98-329">You do not need to perform the following steps if you completed the steps described in "To import from BPEL and build a working solution."</span></span>  

#### <a name="to-build-and-initialize-the-bpelshipping-application"></a><span data-ttu-id="7bd98-330">生成并初始化 BPELShipping 应用程序</span><span class="sxs-lookup"><span data-stu-id="7bd98-330">To build and initialize the BPELShipping application</span></span>  

1. > [!WARNING]
   >  <span data-ttu-id="7bd98-331">执行这些步骤之前，你必须完成以上标题为“生成并初始化 ShipperProcess 应用程序”的步骤。</span><span class="sxs-lookup"><span data-stu-id="7bd98-331">Before executing these steps, you must complete the steps above entitled “To build and initialize the ShipperProcess application”.</span></span>  

    <span data-ttu-id="7bd98-332">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="7bd98-332">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the following folder:</span></span>  

    <span data-ttu-id="7bd98-333">*\<示例路径\>* \Orchestrations\BPELImport\Solution\BPELShipping</span><span class="sxs-lookup"><span data-stu-id="7bd98-333">*\<Samples Path\>* \Orchestrations\BPELImport\Solution\BPELShipping</span></span>  

2. <span data-ttu-id="7bd98-334">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7bd98-334">Run the file Setup.bat, which performs the following actions:</span></span>  

   -   <span data-ttu-id="7bd98-335">生成 BPELShipping 项目</span><span class="sxs-lookup"><span data-stu-id="7bd98-335">Builds the BPELShipping project</span></span>  

   -   <span data-ttu-id="7bd98-336">部署 BPELShipping 项目</span><span class="sxs-lookup"><span data-stu-id="7bd98-336">Deploys the BPELShipping project</span></span>  

   -   <span data-ttu-id="7bd98-337">创建并绑定 BPELShipping 流程使用的发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="7bd98-337">Creates and binds the send and receive ports used by the BPELShipping process</span></span>  

   -   <span data-ttu-id="7bd98-338">启动 BPELShipping 流程使用的端口</span><span class="sxs-lookup"><span data-stu-id="7bd98-338">Starts the ports used by the BPELShipping process</span></span>  

   -   <span data-ttu-id="7bd98-339">登记并启动 BPELShipping 业务流程</span><span class="sxs-lookup"><span data-stu-id="7bd98-339">Enlists and starts the BPELShipping orchestration</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="7bd98-340">运行本示例</span><span class="sxs-lookup"><span data-stu-id="7bd98-340">Running This Sample</span></span>  

#### <a name="to-run-the-bpel-import-sample"></a><span data-ttu-id="7bd98-341">运行 BPEL 导入示例</span><span class="sxs-lookup"><span data-stu-id="7bd98-341">To run the BPEL Import sample</span></span>  

1.  <span data-ttu-id="7bd98-342">复制**Order.xml**文件从*\<示例路径\>* \Orchestrations\BPELImport\Solution 文件夹\<*示例路径\>* \Orchestrations\BPELImport\Solution\Ports\ReceiveOrder 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7bd98-342">Copy the **Order.xml** file from the *\<Samples Path\>* \Orchestrations\BPELImport\Solution folder to the \<*Samples Path\>* \Orchestrations\BPELImport\Solution\Ports\ReceiveOrder folder.</span></span>  

2.  <span data-ttu-id="7bd98-343">BPELShipping 业务流程提取此文件作为订单从客户订单处理系统中，运行发货流程，并生成一个文件中的每个\<*示例路径*\>\Orchestrations\BPELImport\Solution\Ports\SendOrder 文件夹和\<*示例路径*\>\Orchestrations\BPELImport\Solution\Ports\FinalConfirmation 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7bd98-343">The BPELShipping orchestration picks up this file as an order from the customer order processing system, runs through the shipping process, and produces one file each in the \<*Samples Path*\>\Orchestrations\BPELImport\Solution\Ports\SendOrder folder and the \<*Samples Path*\>\Orchestrations\BPELImport\Solution\Ports\FinalConfirmation folder.</span></span> <span data-ttu-id="7bd98-344">这些文件的名称的格式是\< *MessageID*\>.xml，其中*\<MessageID\>* 生成的 GUID 来唯一地标识消息。</span><span class="sxs-lookup"><span data-stu-id="7bd98-344">The format of the name of these files is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  

## <a name="uninstalling-this-sample"></a><span data-ttu-id="7bd98-345">卸载本示例</span><span class="sxs-lookup"><span data-stu-id="7bd98-345">Uninstalling This Sample</span></span>  

#### <a name="to-uninstall-the-bpel-import-sample"></a><span data-ttu-id="7bd98-346">卸载 BPEL 导入示例</span><span class="sxs-lookup"><span data-stu-id="7bd98-346">To uninstall the BPEL Import sample</span></span>  

1. <span data-ttu-id="7bd98-347">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 对\<*示例路径*\>\Orchestrations\BPELImport\BPELShipping。</span><span class="sxs-lookup"><span data-stu-id="7bd98-347">At a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to \<*Samples Path*\>\Orchestrations\BPELImport\BPELShipping.</span></span>  

2. <span data-ttu-id="7bd98-348">运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="7bd98-348">Run Cleanup.bat.</span></span>  

3. <span data-ttu-id="7bd98-349">浏览到\<*示例路径*\>\Orchestrations\BPELImport\ShipperProcess。</span><span class="sxs-lookup"><span data-stu-id="7bd98-349">Browse to \<*Samples Path*\>\Orchestrations\BPELImport\ShipperProcess.</span></span>  

4. <span data-ttu-id="7bd98-350">运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="7bd98-350">Run Cleanup.bat.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7bd98-351">请参阅</span><span class="sxs-lookup"><span data-stu-id="7bd98-351">See Also</span></span>  
 [<span data-ttu-id="7bd98-352">业务流程（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="7bd98-352">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)