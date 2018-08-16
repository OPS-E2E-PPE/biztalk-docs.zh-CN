---
title: 教程 5： 调用 REST 接口使用 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73871ca3-abd0-45ae-b379-6df76a967a80
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d45daa5f567863fd3531edb1f951ac673628fd6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967566"
---
# <a name="tutorial-5-invoking-a-rest-interface-using-biztalk-server"></a><span data-ttu-id="a7730-102">教程 5： 调用 REST 接口使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a7730-102">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>
<span data-ttu-id="a7730-103">本部分提供了有关如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 调用 REST 终结点的分步概览。</span><span class="sxs-lookup"><span data-stu-id="a7730-103">This section provides a step-by-step walkthrough on how to invoke a REST endpoint using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a7730-104">在本教程中，你将调用 [!INCLUDE[winazure](../includes/winazure-md.md)] 市场中的 REST 终结点，该终结点将返回美国航空公司航班的延误情况。</span><span class="sxs-lookup"><span data-stu-id="a7730-104">In this tutorial you invoke a REST endpoint available from the [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace that returns the delays in flights of US air carriers.</span></span> <span data-ttu-id="a7730-105">本教程使用的新**Wcf-webhttp**适配器中引入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来调用 REST 终结点。</span><span class="sxs-lookup"><span data-stu-id="a7730-105">The tutorial uses the new **WCF-WebHttp** adapter introduced in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to invoke the REST endpoint.</span></span>  
  
##  <a name="BKMK_Scenario"></a> <span data-ttu-id="a7730-106">本教程中使用的方案</span><span class="sxs-lookup"><span data-stu-id="a7730-106">Scenario Used in This Tutorial</span></span>  
 <span data-ttu-id="a7730-107">
  [!INCLUDE[winazure](../includes/winazure-md.md)] 市场提供了以下 REST 资源 URL 来检索美国航空公司航班的延误情况：</span><span class="sxs-lookup"><span data-stu-id="a7730-107">[!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace provides the following the REST resource URL to retrieve flight delays of US air carriers:</span></span>  
  
```  
https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/On_Time_Performance  
```  
  
 <span data-ttu-id="a7730-108">如果在 Web 浏览器的地址栏中输入此 URL，系统会提示你输入访问资源的凭据。</span><span class="sxs-lookup"><span data-stu-id="a7730-108">If you enter this URL in the address bar of a Web browser, you are prompted for credentials to access the resource.</span></span> <span data-ttu-id="a7730-109">登录到之后[Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913)，你可以获取从凭据**我的帐户**web 页的选项卡。</span><span class="sxs-lookup"><span data-stu-id="a7730-109">After you have logged into the [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913), you can get the credentials from the **My Account** tab of the web page.</span></span> <span data-ttu-id="a7730-110">对列出这些凭据**Customer ID** （用户名） 和**主帐户密钥**（密码） 标签。</span><span class="sxs-lookup"><span data-stu-id="a7730-110">The credentials are listed against the **Customer ID** (user name) and **Primary Account Key** (password) labels.</span></span>  
  
 <span data-ttu-id="a7730-111">在本教程中，将使用的资源 URL 和凭据来配置一个双向**Wcf-webhttp**发送端口。</span><span class="sxs-lookup"><span data-stu-id="a7730-111">In this tutorial, you use the resource URL and the credentials to configure a two-way **WCF-WebHttp** send port.</span></span> <span data-ttu-id="a7730-112">该双向发送端口的接收管道将接收包含航班详细信息的响应消息，然后将其发布到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="a7730-112">The receive pipeline of the two-way send port receives the response message with the flight details and publishes the message to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message box database.</span></span> <span data-ttu-id="a7730-113">你将配置一个 FILE 发送端口，以便订阅由 WCF-WebHttp 发送端口发布的所有消息。</span><span class="sxs-lookup"><span data-stu-id="a7730-113">You configure a FILE send port that subscribes to all the messages published by the WCF-WebHttp send port.</span></span> <span data-ttu-id="a7730-114">该 FILE 发送端口将处理来自 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的消息，然后将其复制到某个文件位置。</span><span class="sxs-lookup"><span data-stu-id="a7730-114">The FILE send port consumes the message from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and copies it to a file location.</span></span>  
  
 <span data-ttu-id="a7730-115">在现实世界的业务场合中，可以通过将 WCF-WebHttp 发送端口与某个大型业务流程（如从业务应用程序获取消息的接收位置）关联来触发该发送端口。</span><span class="sxs-lookup"><span data-stu-id="a7730-115">In a real-world business scenario, the WCF-WebHttp send port can be triggered by associating it with a larger business process such as a receive location that gets a message from a business application.</span></span> <span data-ttu-id="a7730-116">但是，在本教程中，由于重点是演示如何调用 REST 接口，因此你可以使用一个接收虚拟消息的简单 FILE 位置来触发该发送端口。</span><span class="sxs-lookup"><span data-stu-id="a7730-116">However, in this tutorial, because the focus is on demonstrating how to invoke a REST interface, you can use a simple FILE location that receives a dummy message to trigger the send port.</span></span>  
  
 <span data-ttu-id="a7730-117">因此，总体而言，你必须执行以下步骤来配置此解决方案：</span><span class="sxs-lookup"><span data-stu-id="a7730-117">So, to summarize, you must perform the following steps to configure this solution:</span></span>  
  
1.  <span data-ttu-id="a7730-118">配置一个 FILE 接收位置来提取虚拟请求消息。</span><span class="sxs-lookup"><span data-stu-id="a7730-118">Configure a FILE receive location to pick a dummy request message.</span></span>  
  
2.  <span data-ttu-id="a7730-119">配置一个双向 WCF-WebHttp 发送端口来调用 REST 资源 URL 并接收响应。</span><span class="sxs-lookup"><span data-stu-id="a7730-119">Configure a two-way WCF-WebHttp send port to invoke the REST resource URL and receive a response.</span></span>  
  
3.  <span data-ttu-id="a7730-120">配置一个单向 FILE 发送端口来处理包含航班详细信息的响应消息，然后将其复制到某个文件位置。</span><span class="sxs-lookup"><span data-stu-id="a7730-120">Configure a one-way FILE send port to consume the response message with the flight details and copy it to a file location.</span></span>  
  
## <a name="set-up-your-includewinazureincludeswinazure-mdmd-marketplace-account"></a><span data-ttu-id="a7730-121">设置 [!INCLUDE[winazure](../includes/winazure-md.md)] 市场帐户</span><span class="sxs-lookup"><span data-stu-id="a7730-121">Set up Your [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace Account</span></span>  
 <span data-ttu-id="a7730-122">若要访问通过 REST 终结点公开的航班延误数据，必须首先订阅美国航空公司航班延误示例数据源。</span><span class="sxs-lookup"><span data-stu-id="a7730-122">To access the flight delay data exposed through the REST endpoint, you must first subscribe to the US Air Carrier Flight Delays sample data feed.</span></span> <span data-ttu-id="a7730-123">执行以下步骤来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="a7730-123">Perform the following steps to do so:</span></span>  
  
#### <a name="to-subscribe-to-the-data-feed"></a><span data-ttu-id="a7730-124">订阅数据源</span><span class="sxs-lookup"><span data-stu-id="a7730-124">To subscribe to the data feed</span></span>  
  
1. <span data-ttu-id="a7730-125">使用你的 Microsoft 帐户登录到 [!INCLUDE[winazure](../includes/winazure-md.md)] 市场。</span><span class="sxs-lookup"><span data-stu-id="a7730-125">Log in to the [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace using your Microsoft account.</span></span>  
  
2. <span data-ttu-id="a7730-126">在中**数据**选项卡上，找到并单击**美国美国航空公司航班延误**服务。</span><span class="sxs-lookup"><span data-stu-id="a7730-126">In the **Data** tab, locate and click the **US Air Carrier Flight Delays** service.</span></span>  
  
3. <span data-ttu-id="a7730-127">在数据服务页面上单击**注册**。</span><span class="sxs-lookup"><span data-stu-id="a7730-127">On the data service page, click **Sign Up**.</span></span> <span data-ttu-id="a7730-128">在注册页上，接受协议的条款，然后单击**注册**试。</span><span class="sxs-lookup"><span data-stu-id="a7730-128">On the Sign Up page, accept the terms of agreement and then click **Sign up** again.</span></span>  
  
4. <span data-ttu-id="a7730-129">在中**我的帐户**选项卡上，检索用于访问数据服务的凭据。</span><span class="sxs-lookup"><span data-stu-id="a7730-129">In the **My Account** tab, retrieve the credentials to access the data service.</span></span> <span data-ttu-id="a7730-130">对列出这些凭据**Customer ID** （用户名） 和**主帐户密钥**（密码） 标签。</span><span class="sxs-lookup"><span data-stu-id="a7730-130">The credentials are listed against the **Customer ID** (user name) and **Primary Account Key** (password) labels.</span></span> <span data-ttu-id="a7730-131">配置时，将需要这些凭据**Wcf-webhttp**发送端口。</span><span class="sxs-lookup"><span data-stu-id="a7730-131">You will need these credentials while configuring the **WCF-WebHttp** send port.</span></span>  
  
## <a name="set-up-your-computer"></a><span data-ttu-id="a7730-132">设置计算机</span><span class="sxs-lookup"><span data-stu-id="a7730-132">Set up Your Computer</span></span>  
 <span data-ttu-id="a7730-133">若要配置本教程中使用的方案，你必须在自己的计算机上安装和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a7730-133">To configure the scenario used in this tutorial you must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installed and configured on your computer.</span></span> <span data-ttu-id="a7730-134">如果想要预配[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机上 Windows Azure VM，请遵循的说明[Azure VM 上配置 BizTalk Server](http://msdn.microsoft.com/library/azure/jj248689.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a7730-134">If you want to provision a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer on a Windows Azure VM, follow the instructions at [Configuring BizTalk Server on an Azure VM](http://msdn.microsoft.com/library/azure/jj248689.aspx).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7730-135">本节内容</span><span class="sxs-lookup"><span data-stu-id="a7730-135">In This Section</span></span>  
  
-   [<span data-ttu-id="a7730-136">步骤 1：配置 FILE 接收位置</span><span class="sxs-lookup"><span data-stu-id="a7730-136">Step 1: Configure a FILE Receive Location</span></span>](../core/step-1-configure-a-file-receive-location.md)  
  
-   [<span data-ttu-id="a7730-137">步骤 2：配置双向 WCF-WebHttp 发送端口</span><span class="sxs-lookup"><span data-stu-id="a7730-137">Step 2: Configure a Two-way WCF-WebHttp Send Port</span></span>](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md)  
  
-   [<span data-ttu-id="a7730-138">步骤 3：配置单向 FILE 发送端口</span><span class="sxs-lookup"><span data-stu-id="a7730-138">Step 3: Configure a One-way FILE Send Port</span></span>](../core/step-3-configure-a-one-way-file-send-port.md)  
  
-   [<span data-ttu-id="a7730-139">步骤 4：测试解决方案</span><span class="sxs-lookup"><span data-stu-id="a7730-139">Step 4: Test the Solution</span></span>](../core/step-4-test-the-solution.md)