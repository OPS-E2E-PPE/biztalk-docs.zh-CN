---
title: "如何添加 Web 端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web ports, creating
- creating, Web ports
ms.assetid: da94d98e-10ca-437a-ba34-7aa6efc68f3d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e9853755788aa29d3ca7506829dcd6bdfed53d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-web-port"></a><span data-ttu-id="1e1fe-102">如何添加 Web 端口</span><span class="sxs-lookup"><span data-stu-id="1e1fe-102">How to Add a Web Port</span></span>
<span data-ttu-id="1e1fe-103">你可以在业务流程设计器的端口图面上添加 Web 端口。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-103">You add a Web port on the port surface in Orchestration Designer.</span></span> <span data-ttu-id="1e1fe-104">与其他已配置端口不同，Web 端口支持混合使用请求（单向）和请求/响应（双向）操作。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-104">Unlike other configured ports, Web ports support a mixture of request (one-way) and request/response (two-way) operations.</span></span> <span data-ttu-id="1e1fe-105">Web 端口中的每个操作都表示一个 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-105">Each operation in the Web port represents a Web method.</span></span> <span data-ttu-id="1e1fe-106">如果 Web 方法包含*输入*和*输出*参数，BizTalk 创建请求/响应操作。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-106">If the Web method contains *input* and *output* parameters, BizTalk creates a request/response operation.</span></span> <span data-ttu-id="1e1fe-107">如果 Web 服务仅包含*输入*参数时，BizTalk 仅创建单向操作。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-107">If the Web service contains only an *input* parameter, BizTalk only creates a one-way operation.</span></span>  
  
### <a name="to-add-a-web-port"></a><span data-ttu-id="1e1fe-108">添加 Web 端口</span><span class="sxs-lookup"><span data-stu-id="1e1fe-108">To add a Web port</span></span>  
  
1.  <span data-ttu-id="1e1fe-109">业务流程设计器中，与打开的业务流程中右键单击端口图面，，然后选择**新配置端口**。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-109">In Orchestration Designer, with an orchestration open, right-click the port surface, and then select **New Configured Port**.</span></span>  
  
2.  <span data-ttu-id="1e1fe-110">在“欢迎使用端口配置向导”  页上，单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-110">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="1e1fe-111">上**端口属性**页上，在**名称**文本框中，键入端口的名称，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-111">On the **Port Properties** page, in the **Name** text box, type a name for the port, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="1e1fe-112">在**选择端口类型**页上，选择**使用现有的端口类型**。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-112">In the **Select a Port Type** page, select **Use an existing Port Type**.</span></span>  
  
5.  <span data-ttu-id="1e1fe-113">在**可用端口类型**框中，展开**Web 端口类型**节点，然后选择 Web 端口对应于添加 Web 服务的类型，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-113">In the **Available Port Types** box, expand the **Web Port Types** node and select the Web port type that corresponds to the added Web service, and then click **Next**.</span></span>  
  
     <span data-ttu-id="1e1fe-114">下图显示**选择端口类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-114">The following figure shows the **Select a Port Type** dialog box.</span></span>  
  
     ![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")  
  
6.  <span data-ttu-id="1e1fe-115">在**端口绑定**页上，在**端口绑定**下拉列表框中，选择**现在指定**。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-115">In the **Port Binding** page, in the **Port binding** drop down box, select **Specify now**.</span></span> <span data-ttu-id="1e1fe-116">BizTalk 将引用的 Web Services 的值自动放置到 URI、传输以及接收和发送管道中。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-116">BizTalk automatically places the values from the referenced Web service in the URI, transport, and receive and send pipelines.</span></span> <span data-ttu-id="1e1fe-117">当部署 BizTalk 项目时，BizTalk 使用这些值创建发送端口。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-117">BizTalk uses these values to create the send port when you deploy your BizTalk project.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1e1fe-118">发送端口的默认身份验证方法是匿名访问。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-118">The default authentication method for the send port is anonymous access.</span></span> <span data-ttu-id="1e1fe-119">如果 Web Services 需要不同身份验证或加密方法，则必须更改配置，才能提供正确的用户凭据或安全套接字层 (SSL) 以运行 Web Services。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-119">If the Web service requires a different authentication or encryption method, you must change the configuration to supply the appropriate user credentials or Secure Sockets Layer (SSL) to run Web services.</span></span> <span data-ttu-id="1e1fe-120">有关详细信息，请参阅[SOAP 发送适配器](../core/soap-send-adapter.md)和[示例 TMA: HTTP 和 SOAP 适配器](../core/sample-tma-http-and-soap-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-120">For more information, see [SOAP Send Adapter](../core/soap-send-adapter.md) and [Sample TMA: HTTP and SOAP Adapters](../core/sample-tma-http-and-soap-adapters.md).</span></span>  
  
7.  <span data-ttu-id="1e1fe-121">单击**下一步**，，然后**完成**以完成向导。</span><span class="sxs-lookup"><span data-stu-id="1e1fe-121">Click **Next**, and then **Finish** to complete the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e1fe-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e1fe-122">See Also</span></span>  
 <span data-ttu-id="1e1fe-123">[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="1e1fe-123">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="1e1fe-124">创建 Web 端口</span><span class="sxs-lookup"><span data-stu-id="1e1fe-124">Creating Web Ports</span></span>](../core/creating-web-ports.md)