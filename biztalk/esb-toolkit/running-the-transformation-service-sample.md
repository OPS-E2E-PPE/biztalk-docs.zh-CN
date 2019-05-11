---
title: 运行转换服务示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42064d32-5ec5-4219-a338-c5769969b958
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6278287e93211356c5c7440020032c798bc7d16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394035"
---
# <a name="running-the-transformation-service-sample"></a><span data-ttu-id="37655-102">运行转换服务示例</span><span class="sxs-lookup"><span data-stu-id="37655-102">Running the Transformation Service Sample</span></span>
<span data-ttu-id="37655-103">您可以执行转换服务示例使用任何工具或实用程序，可以执行 Web 服务方法。</span><span class="sxs-lookup"><span data-stu-id="37655-103">You can execute the Transformation Service sample using any tool or utility that can execute Web service methods.</span></span> <span data-ttu-id="37655-104">例如，可以使用 Storm，可从[CodePlex](http://go.microsoft.com/fwlink/?LinkId=187762) ([http://go.microsoft.com/fwlink/?LinkId=187762](http://go.microsoft.com/fwlink/?LinkId=187762))，也可以创建自己的测试客户端调用转换 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="37655-104">For example, you can use Storm, available from [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187762) ([http://go.microsoft.com/fwlink/?LinkId=187762](http://go.microsoft.com/fwlink/?LinkId=187762)), or you can create your own test client that invokes the Transformation Web service.</span></span>  
  
 <span data-ttu-id="37655-105">若要使用.NET Web 服务 Studio 正确安装转换服务示例的测试，到基于 ASMX 的转换 Web 服务输入的 URL **WSDL 终结点**文本框中，，然后单击**获取**按钮。</span><span class="sxs-lookup"><span data-stu-id="37655-105">To use the .NET Web Service Studio to test for correct installation of the Transformation Service sample, enter the URL for the ASMX-based Transformation Web service into the **WSDL EndPoint** text box, and then click the **Get** button.</span></span> <span data-ttu-id="37655-106">这将生成可用于调用 ESB 转换 Web 服务，如图 1 中所示的客户端前端接口。</span><span class="sxs-lookup"><span data-stu-id="37655-106">This generates a client front-end interface that you can use to call the ESB Transformation Web Service, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="37655-107">![转换服务](../esb-toolkit/media/ch6-transformationservice.gif "Ch6-TransformationService")</span><span class="sxs-lookup"><span data-stu-id="37655-107">![Transformation Service](../esb-toolkit/media/ch6-transformationservice.gif "Ch6-TransformationService")</span></span>  
  
 <span data-ttu-id="37655-108">**图 1**</span><span class="sxs-lookup"><span data-stu-id="37655-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="37655-109">**使用.NET Web 服务 Studio 测试转换服务示例**</span><span class="sxs-lookup"><span data-stu-id="37655-109">**Using the .NET Web Service Studio to test the Transformation Service sample**</span></span>  
  
 <span data-ttu-id="37655-110">转换服务示例包含两个 Microsoft BizTalk 映射和两个测试消息的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="37655-110">The Transformation Service sample contains two Microsoft BizTalk maps and two test XML message documents.</span></span> <span data-ttu-id="37655-111">使用名为 TEST_CanonicalOrder_to_OrderConfirmation.xml 和 TEST_RetailOrder_to_CanonicalOrder.xml （位于 \Source\Samples\TransformServices\Test\Data 文件夹中） 的 XML 消息，来执行转换 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="37655-111">You can execute the Transformation Web service with the XML messages named TEST_CanonicalOrder_to_OrderConfirmation.xml and TEST_RetailOrder_to_CanonicalOrder.xml (located in the \Source\Samples\TransformServices\Test\Data folder).</span></span>  
  
 <span data-ttu-id="37655-112">该服务将自动转换消息使用的架构 CanonicalOrder.xsd 和 RetailOrder.xsd 和 OrderConfirmation.xsd （位于 \Source\Samples\TransformServices\Source\ESB。TransformServices.Schemas 文件夹中），和.NET Web 服务 Studio 将显示在结果的已转换的消息。</span><span class="sxs-lookup"><span data-stu-id="37655-112">The service will automatically transform the messages using the schemas CanonicalOrder.xsd and RetailOrder.xsd and OrderConfirmation.xsd (located in the \Source\Samples\TransformServices\Source\ESB.TransformServices.Schemas folder), and .NET Web Service Studio will display the resulting transformed messages.</span></span> <span data-ttu-id="37655-113">以下过程说明如何测试 CanonicalOrder_To_OrderConfirmation 映射。</span><span class="sxs-lookup"><span data-stu-id="37655-113">The following procedure shows how you can test the CanonicalOrder_To_OrderConfirmation map.</span></span>  
  
 <span data-ttu-id="37655-114">**若要测试 GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_OrderConfirmation 映射**</span><span class="sxs-lookup"><span data-stu-id="37655-114">**To test the GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_OrderConfirmation map**</span></span>  
  
1.  <span data-ttu-id="37655-115">如果未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="37655-115">If the GlobalBank.ESB application is not running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="37655-116">值作为输入 TEST_CanonicalOrder_to_OrderConfirmation.xml 文件的以下字符串表示形式**消息**中的参数**输入**树视图的.NET Web 服务 Studio。</span><span class="sxs-lookup"><span data-stu-id="37655-116">Enter the following string representation of the TEST_CanonicalOrder_to_OrderConfirmation.xml file as the value of the **message** parameter in the **Input** tree view of .NET Web Service Studio.</span></span> <span data-ttu-id="37655-117">此字符串符合 GlobalBank.ESB.TransformServices.Schemas.CanonicalOrder 架构：</span><span class="sxs-lookup"><span data-stu-id="37655-117">This string conforms to the GlobalBank.ESB.TransformServices.Schemas.CanonicalOrder schema:</span></span>  
  
    ```  
    <ns0:CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1"   
        Status="Status_2" xmlns:ns0=  
        "http://schemas.globalbank.esb.transformservices.com">  
        <OrderHeader><CustomerName>CustomerName_0</CustomerName>  
        <CustomerID>CustomerID_0</CustomerID><ShipToLine1>  
        ShipToLine1_0</ShipToLine1><ShipToLine2>ShipToLine2_0  
        </ShipToLine2><BillToLine1>BillToLine1_0</BillToLine1>  
        <BillToLine2>BillToLine2_0</BillToLine2><OrderTotal>OrderTotal_0  
        </OrderTotal></OrderHeader><OrderDetails><LineItem Qty="Qty_0"   
        PartNum="PartNum_1" Description="Description_2"   
        UnitPrice="UnitPrice_3" Ext="Ext_4" /></OrderDetails>  
        <B2BPartnerDetails CreditLimit="CreditLimit_0"   
        AccountBalance="AccountBalance_1"   
        LastOrderedData="LastOrderedData_2"   
        DiscountLevel="DiscountLevel_3" /></ns0:CanonicalOrder>  
    ```  
  
3.  <span data-ttu-id="37655-118">输入以下字符串的值作为**mapName**中的参数**输入**树视图的.NET Web 服务 Studio。</span><span class="sxs-lookup"><span data-stu-id="37655-118">Enter the following string as the value of the **mapName** parameter in the **Input** tree view of .NET Web Service Studio.</span></span> <span data-ttu-id="37655-119">这是对消息执行的 BizTalk 映射的完整键入的名称：</span><span class="sxs-lookup"><span data-stu-id="37655-119">This is the fully typed name of the BizTalk map to execute against the message:</span></span>  
  
    ```  
    GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_  
        OrderConfirmation, GlobalBank.ESB.TransformServices.Maps,   
        Version=1.0.0.0, Culture=neutral, PublicKeyToken=<insertYourPublicKeyTokenHere>  
    ```  
  
4.  <span data-ttu-id="37655-120">单击**Invoke**按钮以执行 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="37655-120">Click the **Invoke** button to execute the Web service.</span></span> <span data-ttu-id="37655-121">**输出**测试框显示结果。</span><span class="sxs-lookup"><span data-stu-id="37655-121">The **Output** test box displays the results.</span></span>