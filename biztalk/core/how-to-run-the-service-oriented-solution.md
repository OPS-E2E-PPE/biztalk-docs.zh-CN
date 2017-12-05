---
title: "如何运行服务面向解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service solution tutorial, client applications
- service solution tutorial, starting solution
- service solution tutorial, sending requests
- service solution tutorial, SOAP transports
ms.assetid: 764a5ddc-e571-41d8-9e2f-6d0fb3361b2f
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35c33b914ecbb9f385e5546d100b7572b4b48b6a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-run-the-service-oriented-solution"></a><span data-ttu-id="15dc8-102">如何运行面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="15dc8-102">How to Run the Service Oriented Solution</span></span>
<span data-ttu-id="15dc8-103">以下步骤介绍了如何在单台计算机上运行和验证面向服务的解决方案。</span><span class="sxs-lookup"><span data-stu-id="15dc8-103">The following steps describe how to run and validate the service oriented solution on a single computer.</span></span> <span data-ttu-id="15dc8-104">启动付款跟踪模拟程序之后，可以使用 SOAP 或 MQSeries 传输发送请求（对于面向服务的解决方案的适配器和内联版本，需要使用不同的过程）。</span><span class="sxs-lookup"><span data-stu-id="15dc8-104">After starting the Payment Tracker simulator, you can send requests using either the SOAP or MQSeries transport (with separate procedures for the adapter and inline versions of the service oriented solution).</span></span>  
  
-   [<span data-ttu-id="15dc8-105">将请求发送的 SOAP 传输使用客户端应用程序 （存根 （stub） 版本）</span><span class="sxs-lookup"><span data-stu-id="15dc8-105">Send requests by SOAP transport using the client application (stub version)</span></span>](#step1)  
  
-   [<span data-ttu-id="15dc8-106">发送请求使用客户端应用程序 （适配器版本）</span><span class="sxs-lookup"><span data-stu-id="15dc8-106">Send requests using the client application (adapter version)</span></span>](#step3)  
  
-   [<span data-ttu-id="15dc8-107">发送请求使用客户端应用程序 （内联版本）</span><span class="sxs-lookup"><span data-stu-id="15dc8-107">Send requests using the client application (inline version)</span></span>](#step5)  
  
##  <a name="step1"></a><span data-ttu-id="15dc8-108">将请求发送的 SOAP 传输使用客户端应用程序 （存根 （stub） 版本）</span><span class="sxs-lookup"><span data-stu-id="15dc8-108">Send requests by SOAP transport using the client application (stub version)</span></span>  
  
#### <a name="to-send-requests-by-soap-transport-using-the-client-application-stub-version"></a><span data-ttu-id="15dc8-109">可以使用客户端应用程序 （存根 （stub） 版本） 的 SOAP 传输的发送请求</span><span class="sxs-lookup"><span data-stu-id="15dc8-109">To send requests by SOAP transport using the client application (stub version)</span></span>  
  
1.  <span data-ttu-id="15dc8-110">打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，并再次运行 BTSScnSOSimpleClient.exe。</span><span class="sxs-lookup"><span data-stu-id="15dc8-110">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
2.  <span data-ttu-id="15dc8-111">键入中的任何字符**RequestType**， **RequestSource**，和**RequestID**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-111">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
3.  <span data-ttu-id="15dc8-112">键入在任何 16 位数字**帐号**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-112">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
4.  <span data-ttu-id="15dc8-113">选择**SOAP （WS 调用）**和**存根 （stub)**中**选择传输协议和参数**分组框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-113">Select **SOAP (WS Call)** and **Stub** in the **Select Transport and Parameters** group box.</span></span>  
  
5.  <span data-ttu-id="15dc8-114">键入以下 URL **URL**文本框中，例如：</span><span class="sxs-lookup"><span data-stu-id="15dc8-114">Type the following URL in the **URL** text box, for example:</span></span>  
  
6.  `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub/CustomerServicePort.asmx`  
  
7.  <span data-ttu-id="15dc8-115">类型`ZipCode`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-115">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
8.  <span data-ttu-id="15dc8-116">类型`CustomerName`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-116">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
9. <span data-ttu-id="15dc8-117">单击**获取我余额**。</span><span class="sxs-lookup"><span data-stu-id="15dc8-117">Click **Get my balance**.</span></span>  
  
10. <span data-ttu-id="15dc8-118">响应将显示在**响应**文本框：**成功**显示如果请求成功处理; 如果请求失败不会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="15dc8-118">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
     <span data-ttu-id="15dc8-119">![运行的客户端应用程序的存根 （stub） 版本](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")</span><span class="sxs-lookup"><span data-stu-id="15dc8-119">![Run the client application for the stub version](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")</span></span>  
  
##  <a name="step3"></a><span data-ttu-id="15dc8-120">发送请求使用客户端应用程序 （适配器版本）</span><span class="sxs-lookup"><span data-stu-id="15dc8-120">Send requests using the client application (adapter version)</span></span>  
  
#### <a name="to-send-requests-using-the-client-application-adapter-version"></a><span data-ttu-id="15dc8-121">使用客户端应用程序发送请求（适配器版本）</span><span class="sxs-lookup"><span data-stu-id="15dc8-121">To send requests using the client application (adapter version)</span></span>  
  
1.  <span data-ttu-id="15dc8-122">打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug 和，然后运行以下命令以启动PaymentTracker 模拟器：</span><span class="sxs-lookup"><span data-stu-id="15dc8-122">Open a command prompt, change the directory to \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug and, then run the following command to start the PaymentTracker simulator:</span></span>  
  
     <span data-ttu-id="15dc8-123">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*队列管理器名称* `> 5 [<` *通道定义*`>]`</span><span class="sxs-lookup"><span data-stu-id="15dc8-123">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *Queue Manager Name* `> 5 [<` *Channel Definition* `>]`</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15dc8-124">如果不是远程 MQSeries 服务器，则通道定义为可选项。</span><span class="sxs-lookup"><span data-stu-id="15dc8-124">The channel definition is optional if it is not remote MQSeries Server.</span></span>  
  
    -   <span data-ttu-id="15dc8-125">使付款跟踪模拟程序处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="15dc8-125">Leave the Payment Tracker simulator running.</span></span>  
  
2.  <span data-ttu-id="15dc8-126">打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，并再次运行 BTSScnSOSimpleClient.exe。</span><span class="sxs-lookup"><span data-stu-id="15dc8-126">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
3.  <span data-ttu-id="15dc8-127">在 BTSScnSOSimpleClient.exe 中，按以下步骤通过 SOAP 传输发送请求：</span><span class="sxs-lookup"><span data-stu-id="15dc8-127">In the BTSScnSOSimpleClient.exe, send a request by SOAP transport using the as follows:</span></span>  
  
    1.  <span data-ttu-id="15dc8-128">键入中的任何字符**RequestType**， **RequestSource**，和**RequestID**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-128">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="15dc8-129">键入在任何 16 位数字**帐号**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-129">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="15dc8-130">选择**SOAP （WS 调用）**和**适配器**中**选择传输协议和参数**分组框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-130">Select **SOAP (WS Call)** and **Adapter** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="15dc8-131">键入以下 URL **URL**文本框中，例如：</span><span class="sxs-lookup"><span data-stu-id="15dc8-131">Type the following URL in the **URL** text box, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter/CustomerServicePort.asmx`  
  
    5.  <span data-ttu-id="15dc8-132">类型`ZipCode`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-132">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    6.  <span data-ttu-id="15dc8-133">类型`CustomerName`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-133">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    7.  <span data-ttu-id="15dc8-134">单击**获取我余额**。</span><span class="sxs-lookup"><span data-stu-id="15dc8-134">Click **Get my balance**.</span></span>  
  
    8.  <span data-ttu-id="15dc8-135">响应将显示在**响应**文本框：**成功**显示如果请求成功处理; 如果请求失败不会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="15dc8-135">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="15dc8-136">![运行的客户端应用程序的适配器版本](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")</span><span class="sxs-lookup"><span data-stu-id="15dc8-136">![Run the client application for the adapter version](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")</span></span>  
  
4.  <span data-ttu-id="15dc8-137">在 BTSScnSOSimpleClient.exe 中，按以下步骤通过 MQSeries 传输发送请求：</span><span class="sxs-lookup"><span data-stu-id="15dc8-137">In the BTSScnSOSimpleClient.exe, send requests by MQSeries transport as follows:</span></span>  
  
    1.  <span data-ttu-id="15dc8-138">键入中的任何字符**RequestType**， **RequestSource**，和**RequestID**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-138">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="15dc8-139">键入中的 16 位数字**帐号**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-139">Type a 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="15dc8-140">选择**MQSeries**中**选择传输协议和参数**分组框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-140">Select **MQSeries** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="15dc8-141">类型\<*队列管理器名称*\>中**队列管理器**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-141">Type \<*Queue Manager Name*\> in the **Queue Manager** text box.</span></span> <span data-ttu-id="15dc8-142">QM_\<*您的计算机名称*\>默认值为\<*队列管理器名称*\>。</span><span class="sxs-lookup"><span data-stu-id="15dc8-142">QM_\<*Your Computer Name*\> is the default value for \<*Queue Manager Name*\>.</span></span>  
  
    5.  <span data-ttu-id="15dc8-143">类型`AdapterSOAInputQueue`中**输入队列**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-143">Type `AdapterSOAInputQueue` in the **Input Queue** text box.</span></span>  
  
    6.  <span data-ttu-id="15dc8-144">类型`AdapterSOAOutputQueue`中**输出队列**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-144">Type `AdapterSOAOutputQueue` in the **Output Queue** text box.</span></span>  
  
    7.  <span data-ttu-id="15dc8-145">类型\<*通道定义*\>中**通道定义**框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-145">Type \<*Channel Definition*\> in the **Channel Definition** box.</span></span> <span data-ttu-id="15dc8-146">S_\<*您的计算机名称*\>/TCP/\<*您的计算机名称*\>(1414) 是默认值为\< *通道定义*\>。</span><span class="sxs-lookup"><span data-stu-id="15dc8-146">S_\<*Your Computer Name*\>/TCP/\<*Your Computer Name*\>(1414) is the default value for \<*Channel Definition*\>.</span></span>  
  
    8.  <span data-ttu-id="15dc8-147">类型`ZipCode`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-147">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    9. <span data-ttu-id="15dc8-148">类型`CustomerName`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-148">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    10. <span data-ttu-id="15dc8-149">单击**获取我余额**。</span><span class="sxs-lookup"><span data-stu-id="15dc8-149">Click **Get my balance**.</span></span>  
  
    11. <span data-ttu-id="15dc8-150">响应将显示在**响应**文本框：**成功**显示如果请求成功处理; 如果请求失败不会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="15dc8-150">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="15dc8-151">![运行的客户端应用程序的适配器版本](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")</span><span class="sxs-lookup"><span data-stu-id="15dc8-151">![Run the client application for the adapter version](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")</span></span>  
  
##  <a name="step5"></a><span data-ttu-id="15dc8-152">发送请求使用客户端应用程序 （内联版本）</span><span class="sxs-lookup"><span data-stu-id="15dc8-152">Send requests using the client application (inline version)</span></span>  
  
#### <a name="to-send-requests-using-the-client-application-inline-version"></a><span data-ttu-id="15dc8-153">发送请求，使用客户端应用程序 （内联版本）</span><span class="sxs-lookup"><span data-stu-id="15dc8-153">To send requests using the client application (inline version)</span></span>  
  
1.  <span data-ttu-id="15dc8-154">打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug，并运行以下命令，以启动PaymentTracker 模拟器：</span><span class="sxs-lookup"><span data-stu-id="15dc8-154">Open a command prompt, change the directory to \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug, and then run the following command to start the PaymentTracker simulator:</span></span>  
  
     <span data-ttu-id="15dc8-155">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*队列管理器名称* `> 5 [<` *通道定义*`>]`</span><span class="sxs-lookup"><span data-stu-id="15dc8-155">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *Queue Manager Name* `> 5 [<` *Channel Definition* `>]`</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15dc8-156">如果不是远程 MQSeries 服务器，则通道定义为可选项。</span><span class="sxs-lookup"><span data-stu-id="15dc8-156">The channel definition is optional if it is not remote MQSeries Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15dc8-157">如果付款跟踪模拟程序已运行，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="15dc8-157">Skip this step if the PaymentTracker simulator is already running.</span></span>  
  
    -   <span data-ttu-id="15dc8-158">使付款跟踪模拟程序处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="15dc8-158">Leave the Payment Tracker simulator running.</span></span>  
  
2.  <span data-ttu-id="15dc8-159">在**BizTalk Server 管理控制台**，展开**BTSScn.SO.CustomerService**，单击**接收位置**，右键单击**PaymentTrackingSystemOutputQueue**在右窗格中，然后单击**禁用**。</span><span class="sxs-lookup"><span data-stu-id="15dc8-159">In the **BizTalk Server Administration Console**, expand **BTSScn.SO.CustomerService**, click **Receive Locations**, right-click **PaymentTrackingSystemOutputQueue** in the right pane, and then click **Disable**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15dc8-160">适配器版本和内联版本使用同一个 MQSeries 队列，即 LastPaymentsOutputQueue。</span><span class="sxs-lookup"><span data-stu-id="15dc8-160">The adapter version and inline version uses the same MQSeries queue, LastPaymentsOutputQueue.</span></span> <span data-ttu-id="15dc8-161">为避免这两个版本之间发生争用情况，请禁用适配器版本对 MQSeries 队列的接收位置侦听。</span><span class="sxs-lookup"><span data-stu-id="15dc8-161">To avoid the race condition between two versions, disable the adapter version's receive location listening on the MQSeries queue.</span></span>  
  
3.  <span data-ttu-id="15dc8-162">打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，并再次运行 BTSScnSOSimpleClient.exe。</span><span class="sxs-lookup"><span data-stu-id="15dc8-162">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
4.  <span data-ttu-id="15dc8-163">在 BTSScnSOSimpleClient.exe 中，按以下步骤通过 SOAP 传输发送请求：</span><span class="sxs-lookup"><span data-stu-id="15dc8-163">In the BTSScnSOSimpleClient.exe, send a request by SOAP transport using the as follows:</span></span>  
  
    1.  <span data-ttu-id="15dc8-164">键入中的任何字符**RequestType**， **RequestSource**，和**RequestID**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-164">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="15dc8-165">键入在任何 16 位数字**帐号**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-165">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="15dc8-166">选择**SOAP （WS 调用）**和**内联**中**选择传输协议和参数**分组框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-166">Select **SOAP (WS Call)** and **Inline** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="15dc8-167">键入以下 URL **URL**文本框中，例如：</span><span class="sxs-lookup"><span data-stu-id="15dc8-167">Type the following URL in the **URL** text box, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline/CustomerServicePort.asmx`  
  
    5.  <span data-ttu-id="15dc8-168">类型`ZipCode`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-168">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    6.  <span data-ttu-id="15dc8-169">类型`CustomerName`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-169">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    7.  <span data-ttu-id="15dc8-170">单击**获取我余额**。</span><span class="sxs-lookup"><span data-stu-id="15dc8-170">Click **Get my balance**.</span></span>  
  
    8.  <span data-ttu-id="15dc8-171">响应将显示在**响应**文本框：**成功**显示如果请求成功处理; 如果请求失败不会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="15dc8-171">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="15dc8-172">![运行的客户端应用程序的内联版本](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")</span><span class="sxs-lookup"><span data-stu-id="15dc8-172">![Run the client application for the inline version](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")</span></span>  
  
5.  <span data-ttu-id="15dc8-173">在 BTSScnSOSimpleClient.exe 中，按以下步骤通过 MQSeries 传输发送请求：</span><span class="sxs-lookup"><span data-stu-id="15dc8-173">In the BTSScnSOSimpleClient.exe, send requests by MQSeries transport as follows:</span></span>  
  
    1.  <span data-ttu-id="15dc8-174">键入中的任何字符**RequestType**， **RequestSource**，和**RequestID**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-174">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="15dc8-175">键入中的 16 位数字**帐号**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-175">Type a 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="15dc8-176">选择**MQSeries**中**选择传输协议和参数**分组框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-176">Select **MQSeries** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="15dc8-177">类型\<*队列管理器名称*\>中**队列管理器**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-177">Type \<*Queue Manager Name*\> in the **Queue Manager** text box.</span></span> <span data-ttu-id="15dc8-178">QM_\<*您的计算机名称*\>默认值为\<*队列管理器名称*\>。</span><span class="sxs-lookup"><span data-stu-id="15dc8-178">QM_\<*Your Computer Name*\> is the default value for \<*Queue Manager Name*\>.</span></span>  
  
    5.  <span data-ttu-id="15dc8-179">类型`InlineSOAInputQueue`中**输入队列**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-179">Type `InlineSOAInputQueue` in the **Input Queue** text box.</span></span>  
  
    6.  <span data-ttu-id="15dc8-180">类型`InlineSOAOutputQueue`中**输出队列**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-180">Type `InlineSOAOutputQueue` in the **Output Queue** text box.</span></span>  
  
    7.  <span data-ttu-id="15dc8-181">类型\<*通道定义*\>中**通道定义**框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-181">Type \<*Channel Definition*\> in the **Channel Definition** box.</span></span> <span data-ttu-id="15dc8-182">S_\<*您的计算机名称*\>/TCP/\<*您的计算机名称*\>(1414) 是默认值为\< *通道定义*\>。</span><span class="sxs-lookup"><span data-stu-id="15dc8-182">S_\<*Your Computer Name*\>/TCP/\<*Your Computer Name*\>(1414) is the default value for \<*Channel Definition*\>.</span></span>  
  
    8.  <span data-ttu-id="15dc8-183">类型`ZipCode`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-183">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    9. <span data-ttu-id="15dc8-184">类型`CustomerName`中**名称**下的文本框中**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="15dc8-184">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    10. <span data-ttu-id="15dc8-185">单击**获取我余额**。</span><span class="sxs-lookup"><span data-stu-id="15dc8-185">Click **Get my balance**.</span></span>  
  
    11. <span data-ttu-id="15dc8-186">响应将显示在**响应**文本框：**成功**显示如果请求成功处理; 如果请求失败不会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="15dc8-186">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="15dc8-187">![运行的客户端应用程序的内联版本](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")</span><span class="sxs-lookup"><span data-stu-id="15dc8-187">![Run the client application for the inline version](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15dc8-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15dc8-188">See Also</span></span>  
 <span data-ttu-id="15dc8-189">[在安装之前面向服务解决方案](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="15dc8-189">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="15dc8-190">[如何安装服务的存根 （stub） 版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="15dc8-190">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="15dc8-191">[如何安装内联和服务的适配器版本面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="15dc8-191">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="15dc8-192">面向服务的解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="15dc8-192">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)