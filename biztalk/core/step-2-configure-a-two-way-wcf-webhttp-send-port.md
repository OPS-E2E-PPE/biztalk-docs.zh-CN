---
title: 第 2 步：配置双向 Wcf-webhttp 发送端口 |Microsoft Docs
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
ms.openlocfilehash: aa2018b9212ddb1f8a4df8d94d0f48f5bdaf26ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392803"
---
# <a name="step-2-configure-a-two-way-wcf-webhttp-send-port"></a><span data-ttu-id="d8992-102">第 2 步：配置双向 Wcf-webhttp 发送端口</span><span class="sxs-lookup"><span data-stu-id="d8992-102">Step 2: Configure a Two-way WCF-WebHttp Send Port</span></span>
<span data-ttu-id="d8992-103">在此步骤中配置一个双向**Wcf-webhttp**发送端口来调用 REST 资源 URL 来检索美国航空公司的计划中的延迟。</span><span class="sxs-lookup"><span data-stu-id="d8992-103">In this step you configure a two-way **WCF-WebHttp** send port to invoke the REST resource URL to retrieve delays in the US air carriers’ schedules.</span></span>  
  
### <a name="to-configure-wcf-webhttp-send-port"></a><span data-ttu-id="d8992-104">配置 Wcf-webhttp 发送端口</span><span class="sxs-lookup"><span data-stu-id="d8992-104">To configure WCF-WebHttp send port</span></span>  
  
1.  <span data-ttu-id="d8992-105">从 BizTalk Server 管理控制台中下, **BizTalk Application 1**节点，右键单击**发送端口**，指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d8992-105">From BizTalk Server Administration Console, under the **BizTalk Application 1** node, right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
2.  <span data-ttu-id="d8992-106">在 **“常规”** 选项卡上，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d8992-106">On the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="d8992-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d8992-107">Use this</span></span>|<span data-ttu-id="d8992-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d8992-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d8992-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="d8992-109">**Name**</span></span>|<span data-ttu-id="d8992-110">类型**SendPortRESTAzureMarketPlace**。</span><span class="sxs-lookup"><span data-stu-id="d8992-110">Type **SendPortRESTAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="d8992-111">**类型**</span><span class="sxs-lookup"><span data-stu-id="d8992-111">**Type**</span></span>|<span data-ttu-id="d8992-112">选择**Wcf-webhttp**。</span><span class="sxs-lookup"><span data-stu-id="d8992-112">Select **WCF-WebHttp**.</span></span>|  
    |<span data-ttu-id="d8992-113">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="d8992-113">**Send handler**</span></span>|<span data-ttu-id="d8992-114">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="d8992-114">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="d8992-115">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="d8992-115">**Send pipeline**</span></span>|<span data-ttu-id="d8992-116">选择**PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="d8992-116">Select **PassThruTransmit**.</span></span>|  
    |<span data-ttu-id="d8992-117">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="d8992-117">**Receive pipeline**</span></span>|<span data-ttu-id="d8992-118">选择**PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="d8992-118">Select **PassThruReceive**.</span></span>|  
  
     <span data-ttu-id="d8992-119">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d8992-119">Click **Configure**.</span></span>  
  
3.  <span data-ttu-id="d8992-120">从**Wcf-webhttp 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d8992-120">From the **WCF-WebHttp Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="d8992-121">上**常规**选项卡上，对于**地址 (URI)**，输入`https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`。</span><span class="sxs-lookup"><span data-stu-id="d8992-121">On the **General** tab, for **Address (URI)**, enter `https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`.</span></span>  
  
    2.  <span data-ttu-id="d8992-122">在常规选项卡上的**HTTP 方法和 URL 映射**，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="d8992-122">On the General tab, for **HTTP Method and URL Mapping**, enter the following:</span></span>  
  
        ```  
        <BtsHttpUrlMapping>  
        <Operation Method="GET" Url="/On_Time_Performance" />  
        </BtsHttpUrlMapping>  
  
        ```  
  
         <span data-ttu-id="d8992-123">在这里，**获取**是 HTTP 动词和**On_Time_Performance**追加到基 URI 来构造的唯一资源 URL 来检索航班延误情况。</span><span class="sxs-lookup"><span data-stu-id="d8992-123">Here, **GET** is the HTTP verb and **On_Time_Performance** is appended to the base URI to construct a unique resource URL to retrieve flight delays.</span></span>  
         
         > [!TIP] 
         > <span data-ttu-id="d8992-124">在 URL 字段中，任何特殊 XML 字符必须被"转义"。</span><span class="sxs-lookup"><span data-stu-id="d8992-124">Within the URL field, any special XML characters must be "escaped".</span></span> <span data-ttu-id="d8992-125">这可确保这些特殊 XML 字符是处理，并通过端口保留。</span><span class="sxs-lookup"><span data-stu-id="d8992-125">This ensures that the special XML characters are processed, and preserved by the port.</span></span> <span data-ttu-id="d8992-126">例如，`&`特殊字符必须转义为`&amp;`。</span><span class="sxs-lookup"><span data-stu-id="d8992-126">For example, the `&` special character must be escaped as `&amp;`.</span></span> 
           >
           ><span data-ttu-id="d8992-127">从： `Url=”/Customer?{ID}& group=Location”`</span><span class="sxs-lookup"><span data-stu-id="d8992-127">From: `Url=”/Customer?{ID}& group=Location”`</span></span>
           >
           >
           ><span data-ttu-id="d8992-128">自： `Url=”/Customer?{ID}&amp;group=Location”`</span><span class="sxs-lookup"><span data-stu-id="d8992-128">To: `Url=”/Customer?{ID}&amp;group=Location”`</span></span>
  
    3.  <span data-ttu-id="d8992-129">上**绑定**选项卡上，对于**最大接收消息大小**字段中，选择一个足够大的值。</span><span class="sxs-lookup"><span data-stu-id="d8992-129">On the **Bindings** tab, for the **Maximum Received Message Size** field, select a sufficiently large value.</span></span> <span data-ttu-id="d8992-130">这是因为包含航班状态的响应消息通常相当大，且可能会超过指定的默认消息大小。</span><span class="sxs-lookup"><span data-stu-id="d8992-130">That’s because typically the response message containing the flight status is considerably large and might exceed the default message size specified.</span></span>  
  
    4.  <span data-ttu-id="d8992-131">上**安全**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d8992-131">On the **Security** tab, do the following:</span></span>  
  
        1.  <span data-ttu-id="d8992-132">有关**安全模式**，选择**传输**。</span><span class="sxs-lookup"><span data-stu-id="d8992-132">For the **Security mode**, select **Transport**.</span></span>  
  
        2.  <span data-ttu-id="d8992-133">有关**传输客户端凭据类型**，选择**基本**。</span><span class="sxs-lookup"><span data-stu-id="d8992-133">For **Transport client credential type**, select **Basic**.</span></span>  
  
        3.  <span data-ttu-id="d8992-134">下**用户名凭据**框中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d8992-134">Under the **User name credentials** box, click **Edit**.</span></span> <span data-ttu-id="d8992-135">中**客户端凭据**对话框中，选择**不使用单一登录**，然后输入用户名和密码从检索**我的帐户**选项卡后必须登录到[Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913)。</span><span class="sxs-lookup"><span data-stu-id="d8992-135">In the **Client Credentials** dialog box, select **Do no use Single-Sign On**, and enter the username and password that you retrieved from the **My Account** tab after you have logged into [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913).</span></span> <span data-ttu-id="d8992-136">对列出这些凭据**Customer ID** （用户名） 和**主帐户密钥**（密码） 标签。</span><span class="sxs-lookup"><span data-stu-id="d8992-136">The credentials are listed against the **Customer ID** (user name) and **Primary Account Key** (password) labels.</span></span>  
  
        4.  <span data-ttu-id="d8992-137">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d8992-137">Click **OK**.</span></span>  
  
    5.  <span data-ttu-id="d8992-138">上**消息**选项卡上，对于**为谓词取消正文**，指定你想要去除消息负载将请求消息中的谓词。</span><span class="sxs-lookup"><span data-stu-id="d8992-138">On the **Messages** tab, for **Suppress Body for Verbs**, specify the verb for which you want to strip the message payload from the request message.</span></span> <span data-ttu-id="d8992-139">对于本教程中，指定此方法作为`GET`。</span><span class="sxs-lookup"><span data-stu-id="d8992-139">For this tutorial, specify this as `GET`.</span></span> <span data-ttu-id="d8992-140">原因是：美国航空公司航班延迟 REST 终结点调用 GET 方法不需要消息负载;REST 资源 URL 足以检索的信息。</span><span class="sxs-lookup"><span data-stu-id="d8992-140">Here’s why: A GET method call on the US Air Carrier flight delays REST endpoint does not require a message payload; the REST resource URL is sufficient to retrieve the information.</span></span> <span data-ttu-id="d8992-141">但是，以触发**Wcf-webhttp**进行 REST 调用的发送端口，则删除包含某些消息正文的虚拟消息。</span><span class="sxs-lookup"><span data-stu-id="d8992-141">However, to trigger the **WCF-WebHttp** send port that makes the REST call, you drop a dummy message that has some message body.</span></span> <span data-ttu-id="d8992-142">发送端口不必须将此虚拟消息发送到 REST 终结点，因为如前面所述，该终结点不需要消息负载。</span><span class="sxs-lookup"><span data-stu-id="d8992-142">The send port must not send that dummy message to the REST endpoint because, as explained earlier, the endpoint does not expect a message payload.</span></span> <span data-ttu-id="d8992-143">因此，在调用之前的 REST 终结点，该适配器中去除虚拟消息仅为你在中指定的谓词中的消息有效负载**为谓词取消正文**文本框。</span><span class="sxs-lookup"><span data-stu-id="d8992-143">So, before invoking the REST endpoint, the adapter strips the message payload from the dummy message only for the verbs that you specify in the **Suppress Body for Verbs** text box.</span></span>  
  
    6.  <span data-ttu-id="d8992-144">单击**确定**只有在返回在发送端口属性对话框上。</span><span class="sxs-lookup"><span data-stu-id="d8992-144">Click **OK** until you are back on the Send Port Properties dialog box.</span></span> <span data-ttu-id="d8992-145">在左窗格中，单击**筛选器**，并指定筛选器来处理通过接收收到的所有消息端口中创建[步骤 1:配置一个 FILE 接收位置](../core/step-1-configure-a-file-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="d8992-145">From the left pane, click **Filters**, and specify the filter to consume all messages that are received through the receive port you created in [Step 1: Configure a FILE Receive Location](../core/step-1-configure-a-file-receive-location.md).</span></span>  
  
        |||  
        |-|-|  
        |<span data-ttu-id="d8992-146">**属性**</span><span class="sxs-lookup"><span data-stu-id="d8992-146">**Property**</span></span>|<span data-ttu-id="d8992-147">设置为**BTS。ReceivePortName**</span><span class="sxs-lookup"><span data-stu-id="d8992-147">Set to **BTS.ReceivePortName**</span></span>|  
        |<span data-ttu-id="d8992-148">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="d8992-148">**Operator**</span></span>|<span data-ttu-id="d8992-149">设置为 **==**</span><span class="sxs-lookup"><span data-stu-id="d8992-149">Set to **==**</span></span>|  
        |<span data-ttu-id="d8992-150">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="d8992-150">**Value**</span></span>|<span data-ttu-id="d8992-151">设置为 `ReceivePortRestAzureMarketPlace`</span><span class="sxs-lookup"><span data-stu-id="d8992-151">Set to `ReceivePortRestAzureMarketPlace`</span></span>|  
  
    7.  <span data-ttu-id="d8992-152">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d8992-152">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8992-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8992-153">See Also</span></span>  
 [<span data-ttu-id="d8992-154">教程 5:调用 REST 接口使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d8992-154">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)