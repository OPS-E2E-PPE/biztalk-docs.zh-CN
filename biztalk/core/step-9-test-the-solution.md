---
title: 步骤 9： 测试解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df446ccc-add3-4dd3-b674-253dda385541
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89a3722d6d8e1d4b730341dfaf16d60af1686f21
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973067"
---
# <a name="step-9-test-the-solution"></a><span data-ttu-id="61da3-102">步骤 9： 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="61da3-102">Step 9: Test the Solution</span></span>
<span data-ttu-id="61da3-103">在本主题中，你将通过向部署 EDI 协议所在的 HTTP 终结点发送 X12 840 销售订单消息来测试混合应用程序。</span><span class="sxs-lookup"><span data-stu-id="61da3-103">In this topic you test the hybrid application by sending a X12 840 sales order message to the HTTP endpoint where the EDI agreement is deployed.</span></span> <span data-ttu-id="61da3-104">销售订单消息示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="61da3-104">The sample sales order message looks like the following:</span></span>  
  
```  
ISA*00*          *00*          *ZZ*CONTOSO        *ZZ*NORTHWIND      *991221*1226*U*00401*000000025*0*T*:~  
GS*PO*THEM*US*19991221*1226*1*X*004010~  
ST*840*0002~  
BQT*00*BQT02*20120619*001*20120719~  
PER*1A*John*EM*John@contoso.com~  
N1*001~  
N2*co~  
N3*Contoso*One Contoso Way~  
N4*Redmond*WA*98052*US~  
PO1*PO101*121*01*10*AA*A1*1~  
CTT*475~  
SE*10*0002~  
GE*1*1~  
IEA*1*000000025~  
```  
  
 <span data-ttu-id="61da3-105">在此消息中，突出显示的段 (与开头的行**PO1**) 包含订单数量。</span><span class="sxs-lookup"><span data-stu-id="61da3-105">In this message, the highlighted segment (the line starting with **PO1**) contains the order quantity.</span></span> <span data-ttu-id="61da3-106">此消息中的订单数量是*121*。</span><span class="sxs-lookup"><span data-stu-id="61da3-106">The order quantity in this message is *121*.</span></span> <span data-ttu-id="61da3-107">因此，如果你发送此消息，它必须插入到**SalesOrder**表。</span><span class="sxs-lookup"><span data-stu-id="61da3-107">So, if you send this message, it must be inserted into the **SalesOrder** table.</span></span> <span data-ttu-id="61da3-108">可将该数量更新为小于 100 并重新发送消息，然后必须将其发送到你在 FILE 发送端口中指定的文件位置。</span><span class="sxs-lookup"><span data-stu-id="61da3-108">You can update the quantity to less than 100 and resend the message, it must then be sent to the file location you specified in the FILE send port.</span></span>  
  
 <span data-ttu-id="61da3-109">若要将此消息发送到 EDI 协议中，可以使用**MessageSender**工具附带的示例[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="61da3-109">To send this message to the EDI agreement, you can use the **MessageSender** tool shipped with the samples for [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].</span></span> <span data-ttu-id="61da3-110">您可以下载示例从[http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)。</span><span class="sxs-lookup"><span data-stu-id="61da3-110">You can download the samples from [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057).</span></span>  
  
### <a name="to-send-a-message"></a><span data-ttu-id="61da3-111">发送消息的步骤</span><span class="sxs-lookup"><span data-stu-id="61da3-111">To send a message</span></span>  
  
1.  <span data-ttu-id="61da3-112">找到**MessageSender**示例包中的项目并生成代码。</span><span class="sxs-lookup"><span data-stu-id="61da3-112">Locate the **MessageSender** project in the sample package and build it.</span></span>  
  
2.  <span data-ttu-id="61da3-113">使用生成**MessageSender**命令行可执行文件 （在项目的 \bin\Debug 文件夹） 将消息发送到部署的 EDI 协议。</span><span class="sxs-lookup"><span data-stu-id="61da3-113">Use the resulting **MessageSender** command-line executable (under \bin\Debug folder within the project) to send messages to the deployed EDI agreement.</span></span> <span data-ttu-id="61da3-114">此工具接受以下格式的命令行参数：</span><span class="sxs-lookup"><span data-stu-id="61da3-114">This tool accepts command-line parameter in the following format:</span></span>  
  
    ```  
    MessageSender.exe <ServiceBusNamespace> <IssuerName> <IssuerKey> <EDI agreement endpoint> <MessageFilepath> <ContentType>  
    ```  
  
     <span data-ttu-id="61da3-115">其中，</span><span class="sxs-lookup"><span data-stu-id="61da3-115">Where,</span></span>  
  
    |<span data-ttu-id="61da3-116">参数名称</span><span class="sxs-lookup"><span data-stu-id="61da3-116">Parameter name</span></span>|<span data-ttu-id="61da3-117">Description</span><span class="sxs-lookup"><span data-stu-id="61da3-117">Description</span></span>|  
    |--------------------|-----------------|  
    |<span data-ttu-id="61da3-118">ServiceBusNamespace</span><span class="sxs-lookup"><span data-stu-id="61da3-118">ServiceBusNamespace</span></span>|<span data-ttu-id="61da3-119">Service Bus 命名空间</span><span class="sxs-lookup"><span data-stu-id="61da3-119">The Service Bus namespace</span></span>|  
    |<span data-ttu-id="61da3-120">IssuerName</span><span class="sxs-lookup"><span data-stu-id="61da3-120">IssuerName</span></span>|<span data-ttu-id="61da3-121">指定命名空间的发布者名称</span><span class="sxs-lookup"><span data-stu-id="61da3-121">Issuer Name for the specified namespace</span></span>|  
    |<span data-ttu-id="61da3-122">IssuerKey</span><span class="sxs-lookup"><span data-stu-id="61da3-122">IssuerKey</span></span>|<span data-ttu-id="61da3-123">指定命名空间的发布者密钥</span><span class="sxs-lookup"><span data-stu-id="61da3-123">Issuer Key for the specified namespace</span></span>|  
    |<span data-ttu-id="61da3-124">EDI 协议终结点</span><span class="sxs-lookup"><span data-stu-id="61da3-124">EDI agreement endpoint</span></span>|<span data-ttu-id="61da3-125">部署 EDI 协议所在的终结点。</span><span class="sxs-lookup"><span data-stu-id="61da3-125">The endpoint where the EDI agreement is deployed.</span></span> <span data-ttu-id="61da3-126">你可以获取此终结点 URL，从接收设置选项卡 （和其中，传输页） 中部署的 EDI 协议[步骤 2 (为 Azure): 创建 EDI 协议](../core/step-2-for-azure-create-an-edi-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="61da3-126">You can get this endpoint URL from the Receive Settings tab (and within that, the Transport page) of the EDI agreement you deployed in [Step 2 (For Azure): Create an EDI Agreement](../core/step-2-for-azure-create-an-edi-agreement.md).</span></span>|  
    |<span data-ttu-id="61da3-127">MessageFilePath</span><span class="sxs-lookup"><span data-stu-id="61da3-127">MessageFilePath</span></span>|<span data-ttu-id="61da3-128">包含请求消息示例的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="61da3-128">Path to the file that contains the sample request message.</span></span>|  
    |<span data-ttu-id="61da3-129">ContentType</span><span class="sxs-lookup"><span data-stu-id="61da3-129">ContentType</span></span>|<span data-ttu-id="61da3-130">对于本教程中，将此参数设置为**文本/无格式**。</span><span class="sxs-lookup"><span data-stu-id="61da3-130">For this tutorial, set this parameter to **text/plain**.</span></span>|  
  
     <span data-ttu-id="61da3-131">打开命令提示符并导航到在其中生成该解决方案**MessageSender**项目。</span><span class="sxs-lookup"><span data-stu-id="61da3-131">Open a command prompt and navigate to the solution where you built the **MessageSender** project.</span></span> <span data-ttu-id="61da3-132">运行以下命令，以发送订单数量大于 100 的请求消息：</span><span class="sxs-lookup"><span data-stu-id="61da3-132">Run the following command to send the request message with order quantity more than 100:</span></span>  
  
    ```  
    MessageSender.exe <service bus namespace> owner <issuer key>https://<namespace>.servicebus.appfabriclabs.com/7576ff3d-a0f3-4a46-a4f6-f5be4a50616a/DemoAgreement<path to the sample message> "text/plain"  
    ```  
  
3.  <span data-ttu-id="61da3-133">打开 SQL Server Management Studio，连接到包含的数据库**SalesOrder**表，，然后验证新记录插入表。</span><span class="sxs-lookup"><span data-stu-id="61da3-133">Open SQL Server Management Studio, connect to the database that contains the **SalesOrder** table, and verify that a new record is inserted into the table.</span></span> <span data-ttu-id="61da3-134">请注意中的值**Qty**列; 它必须是*121*。</span><span class="sxs-lookup"><span data-stu-id="61da3-134">Notice the value in the **Qty** column; it must be *121*.</span></span>  
  
4.  <span data-ttu-id="61da3-135">使用**MessageSender**发送另一条消息，但这次设置的值的数量的排序将邮件中*99*。</span><span class="sxs-lookup"><span data-stu-id="61da3-135">Use **MessageSender** to send another message, but this time set the value of the quantity ordered in the message to *99*.</span></span> <span data-ttu-id="61da3-136">你将注意到该现在，在中插入任何记录**SalesOrder**表。</span><span class="sxs-lookup"><span data-stu-id="61da3-136">You will notice that now, no record is inserted in the **SalesOrder** table.</span></span> <span data-ttu-id="61da3-137">相反，消息将复制到用于接收与订单数量小于 100 的消息指定的文件位置。</span><span class="sxs-lookup"><span data-stu-id="61da3-137">Instead, the message is copied to the file location you specified for receiving messages with order quantity less than 100.</span></span> <span data-ttu-id="61da3-138">收到的消息如下所示：</span><span class="sxs-lookup"><span data-stu-id="61da3-138">The received message resembles the following:</span></span>  
  
    ```  
    <ns1:SalesOrder xmlns:ns0="http://schemas.microsoft.com/BizTalk/EDI/X12/2006" xmlns:ns1="http://ECommerceSalesOrder.Inbound">  
      <CompanyCode>co</CompanyCode>  
      <PartID>1</PartID>  
      <Quantity>99</Quantity>  
      <AskPrice>10</AskPrice>  
      <RequestShipmentDate>2012-07-19</RequestShipmentDate>  
      <Address>  
        <Line1>Contoso</Line1>  
        <Line2>One Contoso Way</Line2>  
        <City>Redmond</City>  
        <State>WA</State>  
        <Country>US</Country>  
        <Zipcode>98052</Zipcode>  
      </Address>  
      <Contact>  
        <Firstname>John</Firstname>  
        <Lastname>John@contoso.com</Lastname>  
      </Contact>  
      <Comments>Order from Partnerco</Comments>  
      <DateNow>2012-06-19</DateNow>  
    </ns1:SalesOrder>  
  
    ```  
  
     <span data-ttu-id="61da3-139">请注意中的值**数量**元素。</span><span class="sxs-lookup"><span data-stu-id="61da3-139">Notice the value in the **Quantity** element.</span></span> <span data-ttu-id="61da3-140">它是*99*。</span><span class="sxs-lookup"><span data-stu-id="61da3-140">It is *99*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61da3-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61da3-141">See Also</span></span>  
 [<span data-ttu-id="61da3-142">教程 4： 创建使用 BizTalk Server 2013 的混合应用程序</span><span class="sxs-lookup"><span data-stu-id="61da3-142">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)