---
title: 步骤 2： 配置双向的 WCF WebHttp 发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bcab296-7921-4df4-abcc-eea78cc827e8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f355275f9480cfa13f3a15bcc6522fbe7ec83b8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278885"
---
# <a name="step-2-configure-a-two-way-wcf-webhttp-send-port"></a><span data-ttu-id="49c3c-102">步骤 2： 配置双向的 WCF WebHttp 发送端口</span><span class="sxs-lookup"><span data-stu-id="49c3c-102">Step 2: Configure a Two-way WCF-WebHttp Send Port</span></span>
<span data-ttu-id="49c3c-103">在此步骤中你配置的双向**WCF WebHttp**发送端口来调用 REST 资源 URL，以检索在美国无线运营商的计划中的延迟。</span><span class="sxs-lookup"><span data-stu-id="49c3c-103">In this step you configure a two-way **WCF-WebHttp** send port to invoke the REST resource URL to retrieve delays in the US air carriers’ schedules.</span></span>  
  
### <a name="to-configure-wcf-webhttp-send-port"></a><span data-ttu-id="49c3c-104">配置 WCF-WebHttp 发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="49c3c-104">To configure WCF-WebHttp send port</span></span>  
  
1.  <span data-ttu-id="49c3c-105">从 BizTalk Server 管理控制台，在**BizTalk 应用程序 1**节点，右键单击**发送端口**，指向**新建**，然后单击**静态请求作出响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="49c3c-105">From BizTalk Server Administration Console, under the **BizTalk Application 1** node, right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
2.  <span data-ttu-id="49c3c-106">在 **“常规”** 选项卡上，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="49c3c-106">On the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="49c3c-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="49c3c-107">Use this</span></span>|<span data-ttu-id="49c3c-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="49c3c-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="49c3c-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="49c3c-109">**Name**</span></span>|<span data-ttu-id="49c3c-110">类型**SendPortRESTAzureMarketPlace**。</span><span class="sxs-lookup"><span data-stu-id="49c3c-110">Type **SendPortRESTAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="49c3c-111">**类型**</span><span class="sxs-lookup"><span data-stu-id="49c3c-111">**Type**</span></span>|<span data-ttu-id="49c3c-112">选择**WCF WebHttp**。</span><span class="sxs-lookup"><span data-stu-id="49c3c-112">Select **WCF-WebHttp**.</span></span>|  
    |<span data-ttu-id="49c3c-113">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="49c3c-113">**Send handler**</span></span>|<span data-ttu-id="49c3c-114">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="49c3c-114">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="49c3c-115">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="49c3c-115">**Send pipeline**</span></span>|<span data-ttu-id="49c3c-116">选择**PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="49c3c-116">Select **PassThruTransmit**.</span></span>|  
    |<span data-ttu-id="49c3c-117">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="49c3c-117">**Receive pipeline**</span></span>|<span data-ttu-id="49c3c-118">选择**PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="49c3c-118">Select **PassThruReceive**.</span></span>|  
  
     <span data-ttu-id="49c3c-119">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="49c3c-119">Click **Configure**.</span></span>  
  
3.  <span data-ttu-id="49c3c-120">从**WCF WebHttp 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="49c3c-120">From the **WCF-WebHttp Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="49c3c-121">上**常规**选项卡上，为**地址 (URI)**，输入`https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`。</span><span class="sxs-lookup"><span data-stu-id="49c3c-121">On the **General** tab, for **Address (URI)**, enter `https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`.</span></span>  
  
    2.  <span data-ttu-id="49c3c-122">在常规选项卡上，为**HTTP 方法和 URL 映射**，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="49c3c-122">On the General tab, for **HTTP Method and URL Mapping**, enter the following:</span></span>  
  
        ```  
        <BtsHttpUrlMapping>  
        <Operation Method="GET" Url="/On_Time_Performance" />  
        </BtsHttpUrlMapping>  
  
        ```  
  
         <span data-ttu-id="49c3c-123">在这里，**获取**是 HTTP 动词和**On_Time_Performance**追加到要构造一个唯一的资源 URL 以检索航班延迟的基 URI。</span><span class="sxs-lookup"><span data-stu-id="49c3c-123">Here, **GET** is the HTTP verb and **On_Time_Performance** is appended to the base URI to construct a unique resource URL to retrieve flight delays.</span></span>  
         
         > [!TIP] 
         > <span data-ttu-id="49c3c-124">在 URL 字段中，任何特殊的 XML 字符必须是"转义"。</span><span class="sxs-lookup"><span data-stu-id="49c3c-124">Within the URL field, any special XML characters must be "escaped".</span></span> <span data-ttu-id="49c3c-125">这将确保特殊 XML 字符是处理，并通过端口保留。</span><span class="sxs-lookup"><span data-stu-id="49c3c-125">This ensures that the special XML characters are processed, and preserved by the port.</span></span> <span data-ttu-id="49c3c-126">例如，`&`必须作为转义特殊字符`&amp;`。</span><span class="sxs-lookup"><span data-stu-id="49c3c-126">For example, the `&` special character must be escaped as `&amp;`.</span></span> 
           >
           ><span data-ttu-id="49c3c-127">从：`Url=”/Customer?{ID}& group=Location”`</span><span class="sxs-lookup"><span data-stu-id="49c3c-127">From: `Url=”/Customer?{ID}& group=Location”`</span></span>
           >
           >
           ><span data-ttu-id="49c3c-128">自：`Url=”/Customer?{ID}&amp;group=Location”`</span><span class="sxs-lookup"><span data-stu-id="49c3c-128">To: `Url=”/Customer?{ID}&amp;group=Location”`</span></span>
  
    3.  <span data-ttu-id="49c3c-129">上**绑定**选项卡上，为**最大接收消息大小**字段中，选择一个足够大的值。</span><span class="sxs-lookup"><span data-stu-id="49c3c-129">On the **Bindings** tab, for the **Maximum Received Message Size** field, select a sufficiently large value.</span></span> <span data-ttu-id="49c3c-130">这是因为，包含航班状态的响应消息通常都相当大，并且可能超出指定的默认消息大小。</span><span class="sxs-lookup"><span data-stu-id="49c3c-130">That’s because typically the response message containing the flight status is considerably large and might exceed the default message size specified.</span></span>  
  
    4.  <span data-ttu-id="49c3c-131">上**安全**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="49c3c-131">On the **Security** tab, do the following:</span></span>  
  
        1.  <span data-ttu-id="49c3c-132">有关**安全模式**，选择**传输**。</span><span class="sxs-lookup"><span data-stu-id="49c3c-132">For the **Security mode**, select **Transport**.</span></span>  
  
        2.  <span data-ttu-id="49c3c-133">有关**传输客户端凭据类型**，选择**基本**。</span><span class="sxs-lookup"><span data-stu-id="49c3c-133">For **Transport client credential type**, select **Basic**.</span></span>  
  
        3.  <span data-ttu-id="49c3c-134">下**用户名凭据**框中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="49c3c-134">Under the **User name credentials** box, click **Edit**.</span></span> <span data-ttu-id="49c3c-135">在**客户端凭据**对话框中，选择**不使用单一登录**，然后输入用户名和密码从检索到**我的帐户**选项卡后必须登录到[Windows Azure 应用商店](http://go.microsoft.com/fwlink/p/?LinkId=257913)。</span><span class="sxs-lookup"><span data-stu-id="49c3c-135">In the **Client Credentials** dialog box, select **Do no use Single-Sign On**, and enter the username and password that you retrieved from the **My Account** tab after you have logged into [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913).</span></span> <span data-ttu-id="49c3c-136">凭据列出针对**客户 ID** （用户名称） 和**主帐户密钥**（密码） 标签。</span><span class="sxs-lookup"><span data-stu-id="49c3c-136">The credentials are listed against the **Customer ID** (user name) and **Primary Account Key** (password) labels.</span></span>  
  
        4.  <span data-ttu-id="49c3c-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="49c3c-137">Click **OK**.</span></span>  
  
    5.  <span data-ttu-id="49c3c-138">上**消息**选项卡上，为**禁止显示谓词的正文**，指定你想要去除从请求消息的消息负载的谓词。</span><span class="sxs-lookup"><span data-stu-id="49c3c-138">On the **Messages** tab, for **Suppress Body for Verbs**, specify the verb for which you want to strip the message payload from the request message.</span></span> <span data-ttu-id="49c3c-139">对于本教程中，指定为`GET`。</span><span class="sxs-lookup"><span data-stu-id="49c3c-139">For this tutorial, specify this as `GET`.</span></span> <span data-ttu-id="49c3c-140">原因是： 美国无线运营商航班延迟 REST 终结点上的 GET 方法调用不需要一个消息有效负载中;REST 资源 URL 是不足以检索信息。</span><span class="sxs-lookup"><span data-stu-id="49c3c-140">Here’s why: A GET method call on the US Air Carrier flight delays REST endpoint does not require a message payload; the REST resource URL is sufficient to retrieve the information.</span></span> <span data-ttu-id="49c3c-141">但是，到触发器**WCF WebHttp**使 REST 调用的发送端口，则将删除具有某些消息正文的 dummy 消息。</span><span class="sxs-lookup"><span data-stu-id="49c3c-141">However, to trigger the **WCF-WebHttp** send port that makes the REST call, you drop a dummy message that has some message body.</span></span> <span data-ttu-id="49c3c-142">该发送端口不得将此虚拟消息发送到 REST 终结点，因为如前所述，该终结点不需要消息负载。</span><span class="sxs-lookup"><span data-stu-id="49c3c-142">The send port must not send that dummy message to the REST endpoint because, as explained earlier, the endpoint does not expect a message payload.</span></span> <span data-ttu-id="49c3c-143">因此，在调用 REST 终结点之前, 适配器剥离消息负载中指定的谓词仅的 dummy 消息从**禁止显示谓词的正文**文本框。</span><span class="sxs-lookup"><span data-stu-id="49c3c-143">So, before invoking the REST endpoint, the adapter strips the message payload from the dummy message only for the verbs that you specify in the **Suppress Body for Verbs** text box.</span></span>  
  
    6.  <span data-ttu-id="49c3c-144">单击**确定**直到您会在发送端口属性对话框中。</span><span class="sxs-lookup"><span data-stu-id="49c3c-144">Click **OK** until you are back on the Send Port Properties dialog box.</span></span> <span data-ttu-id="49c3c-145">从左窗格中，单击**筛选器**，并指定要使用通过接收接收的所有消息的筛选器端口中创建[步骤 1： 配置文件接收位置](../core/step-1-configure-a-file-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="49c3c-145">From the left pane, click **Filters**, and specify the filter to consume all messages that are received through the receive port you created in [Step 1: Configure a FILE Receive Location](../core/step-1-configure-a-file-receive-location.md).</span></span>  
  
        |||  
        |-|-|  
        |<span data-ttu-id="49c3c-146">**属性**</span><span class="sxs-lookup"><span data-stu-id="49c3c-146">**Property**</span></span>|<span data-ttu-id="49c3c-147">设置为**BTS。ReceivePortName**</span><span class="sxs-lookup"><span data-stu-id="49c3c-147">Set to **BTS.ReceivePortName**</span></span>|  
        |<span data-ttu-id="49c3c-148">**运算符**</span><span class="sxs-lookup"><span data-stu-id="49c3c-148">**Operator**</span></span>|<span data-ttu-id="49c3c-149">设置为**==**</span><span class="sxs-lookup"><span data-stu-id="49c3c-149">Set to **==**</span></span>|  
        |<span data-ttu-id="49c3c-150">**值**</span><span class="sxs-lookup"><span data-stu-id="49c3c-150">**Value**</span></span>|<span data-ttu-id="49c3c-151">设置为`ReceivePortRestAzureMarketPlace`</span><span class="sxs-lookup"><span data-stu-id="49c3c-151">Set to `ReceivePortRestAzureMarketPlace`</span></span>|  
  
    7.  <span data-ttu-id="49c3c-152">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="49c3c-152">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c3c-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49c3c-153">See Also</span></span>  
 [<span data-ttu-id="49c3c-154">教程 5： 调用 REST 接口使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="49c3c-154">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)