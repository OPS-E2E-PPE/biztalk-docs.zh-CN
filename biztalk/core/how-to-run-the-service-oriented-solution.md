---
title: 如何运行该服务面向解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, client applications
- service solution tutorial, starting solution
- service solution tutorial, sending requests
- service solution tutorial, SOAP transports
ms.assetid: 764a5ddc-e571-41d8-9e2f-6d0fb3361b2f
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa1fed4a695eef0e21a3199854416436bf2af13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384074"
---
# <a name="how-to-run-the-service-oriented-solution"></a><span data-ttu-id="82027-102">如何运行该服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="82027-102">How to Run the Service Oriented Solution</span></span>
<span data-ttu-id="82027-103">以下步骤介绍如何运行和验证面向服务的解决方案在单台计算机上。</span><span class="sxs-lookup"><span data-stu-id="82027-103">The following steps describe how to run and validate the service oriented solution on a single computer.</span></span> <span data-ttu-id="82027-104">启动付款跟踪模拟程序之后, 可以发送请求使用 SOAP 或 MQSeries 传输 （具有单独的适配器版本和内联版本的面向服务的解决方案的过程）。</span><span class="sxs-lookup"><span data-stu-id="82027-104">After starting the Payment Tracker simulator, you can send requests using either the SOAP or MQSeries transport (with separate procedures for the adapter and inline versions of the service oriented solution).</span></span>  
  
-   [<span data-ttu-id="82027-105">通过使用客户端应用程序 （存根版本） 的 SOAP 传输发送请求</span><span class="sxs-lookup"><span data-stu-id="82027-105">Send requests by SOAP transport using the client application (stub version)</span></span>](#step1)  
  
-   [<span data-ttu-id="82027-106">使用客户端应用程序 （适配器版本） 发送请求</span><span class="sxs-lookup"><span data-stu-id="82027-106">Send requests using the client application (adapter version)</span></span>](#step3)  
  
-   [<span data-ttu-id="82027-107">使用客户端应用程序 （内联版本） 发送请求</span><span class="sxs-lookup"><span data-stu-id="82027-107">Send requests using the client application (inline version)</span></span>](#step5)  
  
##  <a name="step1"></a> <span data-ttu-id="82027-108">通过使用客户端应用程序 （存根版本） 的 SOAP 传输发送请求</span><span class="sxs-lookup"><span data-stu-id="82027-108">Send requests by SOAP transport using the client application (stub version)</span></span>  
  
#### <a name="to-send-requests-by-soap-transport-using-the-client-application-stub-version"></a><span data-ttu-id="82027-109">若要通过使用客户端应用程序 （存根版本） 的 SOAP 传输发送请求</span><span class="sxs-lookup"><span data-stu-id="82027-109">To send requests by SOAP transport using the client application (stub version)</span></span>  
  
1.  <span data-ttu-id="82027-110">打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，，然后运行 BTSScnSOSimpleClient.exe。</span><span class="sxs-lookup"><span data-stu-id="82027-110">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
2.  <span data-ttu-id="82027-111">中键入任意字符**RequestType**， **RequestSource**，并**RequestID**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-111">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
3.  <span data-ttu-id="82027-112">键入在任何 16 位数字**帐号**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-112">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
4.  <span data-ttu-id="82027-113">选择**SOAP （WS 调用）** 并**存根**中**选择传输和参数**分组框。</span><span class="sxs-lookup"><span data-stu-id="82027-113">Select **SOAP (WS Call)** and **Stub** in the **Select Transport and Parameters** group box.</span></span>  
  
5.  <span data-ttu-id="82027-114">键入以下 URL 中的**URL**文本框中，例如：</span><span class="sxs-lookup"><span data-stu-id="82027-114">Type the following URL in the **URL** text box, for example:</span></span>  
  
6.  `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub/CustomerServicePort.asmx`  
  
7.  <span data-ttu-id="82027-115">类型`ZipCode`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-115">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
8.  <span data-ttu-id="82027-116">类型`CustomerName`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-116">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
9. <span data-ttu-id="82027-117">单击**获取余额**。</span><span class="sxs-lookup"><span data-stu-id="82027-117">Click **Get my balance**.</span></span>  
  
10. <span data-ttu-id="82027-118">响应显示在**响应**文本框中：**成功**显示如果请求已成功处理; 如果请求失败，将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="82027-118">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
     <span data-ttu-id="82027-119">![运行用于存根版本的客户端应用程序](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")</span><span class="sxs-lookup"><span data-stu-id="82027-119">![Run the client application for the stub version](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")</span></span>  
  
##  <a name="step3"></a> <span data-ttu-id="82027-120">使用客户端应用程序 （适配器版本） 发送请求</span><span class="sxs-lookup"><span data-stu-id="82027-120">Send requests using the client application (adapter version)</span></span>  
  
#### <a name="to-send-requests-using-the-client-application-adapter-version"></a><span data-ttu-id="82027-121">若要使用客户端应用程序 （适配器版本） 发送请求</span><span class="sxs-lookup"><span data-stu-id="82027-121">To send requests using the client application (adapter version)</span></span>  
  
1.  <span data-ttu-id="82027-122">打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug，然后运行以下命令以启动付款跟踪模拟程序：</span><span class="sxs-lookup"><span data-stu-id="82027-122">Open a command prompt, change the directory to \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug and, then run the following command to start the PaymentTracker simulator:</span></span>  
  
     <span data-ttu-id="82027-123">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *队列管理器名称* `> 5 [<` *通道定义* `>]`</span><span class="sxs-lookup"><span data-stu-id="82027-123">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *Queue Manager Name* `> 5 [<` *Channel Definition* `>]`</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82027-124">通道定义是可选的如果它不是远程 MQSeries 服务器。</span><span class="sxs-lookup"><span data-stu-id="82027-124">The channel definition is optional if it is not remote MQSeries Server.</span></span>  
  
    -   <span data-ttu-id="82027-125">将付款跟踪模拟程序运行。</span><span class="sxs-lookup"><span data-stu-id="82027-125">Leave the Payment Tracker simulator running.</span></span>  
  
2.  <span data-ttu-id="82027-126">打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，，然后运行 BTSScnSOSimpleClient.exe。</span><span class="sxs-lookup"><span data-stu-id="82027-126">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
3.  <span data-ttu-id="82027-127">在 BTSScnSOSimpleClient.exe 中发送 soap 请求传输如下所示：</span><span class="sxs-lookup"><span data-stu-id="82027-127">In the BTSScnSOSimpleClient.exe, send a request by SOAP transport using the as follows:</span></span>  
  
    1.  <span data-ttu-id="82027-128">中键入任意字符**RequestType**， **RequestSource**，并**RequestID**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-128">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="82027-129">键入在任何 16 位数字**帐号**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-129">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="82027-130">选择**SOAP （WS 调用）** 并**适配器**中**选择传输和参数**分组框。</span><span class="sxs-lookup"><span data-stu-id="82027-130">Select **SOAP (WS Call)** and **Adapter** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="82027-131">键入以下 URL 中的**URL**文本框中，例如：</span><span class="sxs-lookup"><span data-stu-id="82027-131">Type the following URL in the **URL** text box, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter/CustomerServicePort.asmx`  
  
    5.  <span data-ttu-id="82027-132">类型`ZipCode`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-132">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    6.  <span data-ttu-id="82027-133">类型`CustomerName`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-133">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    7.  <span data-ttu-id="82027-134">单击**获取余额**。</span><span class="sxs-lookup"><span data-stu-id="82027-134">Click **Get my balance**.</span></span>  
  
    8.  <span data-ttu-id="82027-135">响应显示在**响应**文本框中：**成功**显示如果请求已成功处理; 如果请求失败，将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="82027-135">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="82027-136">![运行用于适配器版本的客户端应用程序](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")</span><span class="sxs-lookup"><span data-stu-id="82027-136">![Run the client application for the adapter version](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")</span></span>  
  
4.  <span data-ttu-id="82027-137">在 BTSScnSOSimpleClient.exe 中通过传输发送请求 MQSeries，如下所示：</span><span class="sxs-lookup"><span data-stu-id="82027-137">In the BTSScnSOSimpleClient.exe, send requests by MQSeries transport as follows:</span></span>  
  
    1.  <span data-ttu-id="82027-138">中键入任意字符**RequestType**， **RequestSource**，并**RequestID**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-138">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="82027-139">键入在 16 位数字**帐号**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-139">Type a 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="82027-140">选择**MQSeries**中**选择传输和参数**分组框。</span><span class="sxs-lookup"><span data-stu-id="82027-140">Select **MQSeries** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="82027-141">类型\<*队列管理器名称*\>中**队列管理器**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-141">Type \<*Queue Manager Name*\> in the **Queue Manager** text box.</span></span> <span data-ttu-id="82027-142">QM_\<*您的计算机名称*\>是默认值\<*队列管理器名称*\>。</span><span class="sxs-lookup"><span data-stu-id="82027-142">QM_\<*Your Computer Name*\> is the default value for \<*Queue Manager Name*\>.</span></span>  
  
    5.  <span data-ttu-id="82027-143">类型`AdapterSOAInputQueue`中**输入队列**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-143">Type `AdapterSOAInputQueue` in the **Input Queue** text box.</span></span>  
  
    6.  <span data-ttu-id="82027-144">类型`AdapterSOAOutputQueue`中**输出队列**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-144">Type `AdapterSOAOutputQueue` in the **Output Queue** text box.</span></span>  
  
    7.  <span data-ttu-id="82027-145">类型\<*通道定义*\>中**通道定义**框。</span><span class="sxs-lookup"><span data-stu-id="82027-145">Type \<*Channel Definition*\> in the **Channel Definition** box.</span></span> <span data-ttu-id="82027-146">S_\<*您的计算机名称*\>/tcp/&lt\<*您的计算机名称*\>(1414) 是默认值为\< *通道定义*\>。</span><span class="sxs-lookup"><span data-stu-id="82027-146">S_\<*Your Computer Name*\>/TCP/\<*Your Computer Name*\>(1414) is the default value for \<*Channel Definition*\>.</span></span>  
  
    8.  <span data-ttu-id="82027-147">类型`ZipCode`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-147">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    9. <span data-ttu-id="82027-148">类型`CustomerName`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-148">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    10. <span data-ttu-id="82027-149">单击**获取余额**。</span><span class="sxs-lookup"><span data-stu-id="82027-149">Click **Get my balance**.</span></span>  
  
    11. <span data-ttu-id="82027-150">响应显示在**响应**文本框中：**成功**显示如果请求已成功处理; 如果请求失败，将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="82027-150">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="82027-151">![运行用于适配器版本的客户端应用程序](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")</span><span class="sxs-lookup"><span data-stu-id="82027-151">![Run the client application for the adapter version](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")</span></span>  
  
##  <a name="step5"></a> <span data-ttu-id="82027-152">使用客户端应用程序 （内联版本） 发送请求</span><span class="sxs-lookup"><span data-stu-id="82027-152">Send requests using the client application (inline version)</span></span>  
  
#### <a name="to-send-requests-using-the-client-application-inline-version"></a><span data-ttu-id="82027-153">若要使用客户端应用程序 （内联版本） 发送请求</span><span class="sxs-lookup"><span data-stu-id="82027-153">To send requests using the client application (inline version)</span></span>  
  
1.  <span data-ttu-id="82027-154">打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug，并运行以下命令以启动付款跟踪模拟程序：</span><span class="sxs-lookup"><span data-stu-id="82027-154">Open a command prompt, change the directory to \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug, and then run the following command to start the PaymentTracker simulator:</span></span>  
  
     <span data-ttu-id="82027-155">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *队列管理器名称* `> 5 [<` *通道定义* `>]`</span><span class="sxs-lookup"><span data-stu-id="82027-155">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *Queue Manager Name* `> 5 [<` *Channel Definition* `>]`</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82027-156">通道定义是可选的如果它不是远程 MQSeries 服务器。</span><span class="sxs-lookup"><span data-stu-id="82027-156">The channel definition is optional if it is not remote MQSeries Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82027-157">如果付款跟踪模拟程序已在运行，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="82027-157">Skip this step if the PaymentTracker simulator is already running.</span></span>  
  
    -   <span data-ttu-id="82027-158">将付款跟踪模拟程序运行。</span><span class="sxs-lookup"><span data-stu-id="82027-158">Leave the Payment Tracker simulator running.</span></span>  
  
2.  <span data-ttu-id="82027-159">在中**BizTalk Server 管理控制台**，展开**BTSScn.SO.CustomerService**，单击**接收位置**，右键单击**PaymentTrackingSystemOutputQueue**在右窗格中，然后单击**禁用**。</span><span class="sxs-lookup"><span data-stu-id="82027-159">In the **BizTalk Server Administration Console**, expand **BTSScn.SO.CustomerService**, click **Receive Locations**, right-click **PaymentTrackingSystemOutputQueue** in the right pane, and then click **Disable**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82027-160">适配器版本和内联版本使用同一个 MQSeries 队列，即 LastPaymentsOutputQueue。</span><span class="sxs-lookup"><span data-stu-id="82027-160">The adapter version and inline version uses the same MQSeries queue, LastPaymentsOutputQueue.</span></span> <span data-ttu-id="82027-161">若要避免两个版本之间的争用条件，请禁用适配器版本的接收位置 MQSeries 队列上侦听。</span><span class="sxs-lookup"><span data-stu-id="82027-161">To avoid the race condition between two versions, disable the adapter version's receive location listening on the MQSeries queue.</span></span>  
  
3.  <span data-ttu-id="82027-162">打开命令提示符下，将目录更改为\< *BizTalk Server 安装目录*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release，，然后运行 BTSScnSOSimpleClient.exe。</span><span class="sxs-lookup"><span data-stu-id="82027-162">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
4.  <span data-ttu-id="82027-163">在 BTSScnSOSimpleClient.exe 中发送 soap 请求传输如下所示：</span><span class="sxs-lookup"><span data-stu-id="82027-163">In the BTSScnSOSimpleClient.exe, send a request by SOAP transport using the as follows:</span></span>  
  
    1.  <span data-ttu-id="82027-164">中键入任意字符**RequestType**， **RequestSource**，并**RequestID**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-164">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="82027-165">键入在任何 16 位数字**帐号**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-165">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="82027-166">选择**SOAP （WS 调用）** 并**内联**中**选择传输和参数**分组框。</span><span class="sxs-lookup"><span data-stu-id="82027-166">Select **SOAP (WS Call)** and **Inline** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="82027-167">键入以下 URL 中的**URL**文本框中，例如：</span><span class="sxs-lookup"><span data-stu-id="82027-167">Type the following URL in the **URL** text box, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline/CustomerServicePort.asmx`  
  
    5.  <span data-ttu-id="82027-168">类型`ZipCode`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-168">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    6.  <span data-ttu-id="82027-169">类型`CustomerName`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-169">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    7.  <span data-ttu-id="82027-170">单击**获取余额**。</span><span class="sxs-lookup"><span data-stu-id="82027-170">Click **Get my balance**.</span></span>  
  
    8.  <span data-ttu-id="82027-171">响应显示在**响应**文本框中：**成功**显示如果请求已成功处理; 如果请求失败，将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="82027-171">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="82027-172">![运行用于内联版本的客户端应用程序](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")</span><span class="sxs-lookup"><span data-stu-id="82027-172">![Run the client application for the inline version](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")</span></span>  
  
5.  <span data-ttu-id="82027-173">在 BTSScnSOSimpleClient.exe 中通过传输发送请求 MQSeries，如下所示：</span><span class="sxs-lookup"><span data-stu-id="82027-173">In the BTSScnSOSimpleClient.exe, send requests by MQSeries transport as follows:</span></span>  
  
    1.  <span data-ttu-id="82027-174">中键入任意字符**RequestType**， **RequestSource**，并**RequestID**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-174">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="82027-175">键入在 16 位数字**帐号**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-175">Type a 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="82027-176">选择**MQSeries**中**选择传输和参数**分组框。</span><span class="sxs-lookup"><span data-stu-id="82027-176">Select **MQSeries** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="82027-177">类型\<*队列管理器名称*\>中**队列管理器**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-177">Type \<*Queue Manager Name*\> in the **Queue Manager** text box.</span></span> <span data-ttu-id="82027-178">QM_\<*您的计算机名称*\>是默认值\<*队列管理器名称*\>。</span><span class="sxs-lookup"><span data-stu-id="82027-178">QM_\<*Your Computer Name*\> is the default value for \<*Queue Manager Name*\>.</span></span>  
  
    5.  <span data-ttu-id="82027-179">类型`InlineSOAInputQueue`中**输入队列**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-179">Type `InlineSOAInputQueue` in the **Input Queue** text box.</span></span>  
  
    6.  <span data-ttu-id="82027-180">类型`InlineSOAOutputQueue`中**输出队列**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-180">Type `InlineSOAOutputQueue` in the **Output Queue** text box.</span></span>  
  
    7.  <span data-ttu-id="82027-181">类型\<*通道定义*\>中**通道定义**框。</span><span class="sxs-lookup"><span data-stu-id="82027-181">Type \<*Channel Definition*\> in the **Channel Definition** box.</span></span> <span data-ttu-id="82027-182">S_\<*您的计算机名称*\>/tcp/&lt\<*您的计算机名称*\>(1414) 是默认值为\< *通道定义*\>。</span><span class="sxs-lookup"><span data-stu-id="82027-182">S_\<*Your Computer Name*\>/TCP/\<*Your Computer Name*\>(1414) is the default value for \<*Channel Definition*\>.</span></span>  
  
    8.  <span data-ttu-id="82027-183">类型`ZipCode`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-183">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    9. <span data-ttu-id="82027-184">类型`CustomerName`中**名称**下的文本框**身份验证元素**，然后键入中的任何字符**值**文本框。</span><span class="sxs-lookup"><span data-stu-id="82027-184">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    10. <span data-ttu-id="82027-185">单击**获取余额**。</span><span class="sxs-lookup"><span data-stu-id="82027-185">Click **Get my balance**.</span></span>  
  
    11. <span data-ttu-id="82027-186">响应显示在**响应**文本框中：**成功**显示如果请求已成功处理; 如果请求失败，将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="82027-186">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="82027-187">![运行用于内联版本的客户端应用程序](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")</span><span class="sxs-lookup"><span data-stu-id="82027-187">![Run the client application for the inline version](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82027-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="82027-188">See Also</span></span>  
 <span data-ttu-id="82027-189">[然后再安装面向服务的解决方案](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="82027-189">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="82027-190">[如何安装该服务的存根版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="82027-190">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="82027-191">[如何安装的内联版本和适配器版本的服务面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="82027-191">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="82027-192">面向服务的解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="82027-192">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)