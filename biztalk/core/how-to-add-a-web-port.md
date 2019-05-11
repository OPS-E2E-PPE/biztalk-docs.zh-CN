---
title: 如何添加 Web 端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web ports, creating
- creating, Web ports
ms.assetid: da94d98e-10ca-437a-ba34-7aa6efc68f3d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a67cfd33aeace3b6cfde9f1e0a7e87831d7972ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387342"
---
# <a name="how-to-add-a-web-port"></a><span data-ttu-id="4f037-102">如何添加 Web 端口</span><span class="sxs-lookup"><span data-stu-id="4f037-102">How to Add a Web Port</span></span>
<span data-ttu-id="4f037-103">在业务流程设计器中的端口图面上添加 Web 端口。</span><span class="sxs-lookup"><span data-stu-id="4f037-103">You add a Web port on the port surface in Orchestration Designer.</span></span> <span data-ttu-id="4f037-104">与其他已配置的端口不同的 Web 端口支持混合使用请求 （单向） 和请求/响应 （双向） 操作。</span><span class="sxs-lookup"><span data-stu-id="4f037-104">Unlike other configured ports, Web ports support a mixture of request (one-way) and request/response (two-way) operations.</span></span> <span data-ttu-id="4f037-105">Web 端口中的每个操作表示 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="4f037-105">Each operation in the Web port represents a Web method.</span></span> <span data-ttu-id="4f037-106">如果 Web 方法包含*输入*并*输出*参数，BizTalk 将创建请求/响应操作。</span><span class="sxs-lookup"><span data-stu-id="4f037-106">If the Web method contains *input* and *output* parameters, BizTalk creates a request/response operation.</span></span> <span data-ttu-id="4f037-107">如果 Web 服务仅包含*输入*参数时，BizTalk 仅创建单向操作。</span><span class="sxs-lookup"><span data-stu-id="4f037-107">If the Web service contains only an *input* parameter, BizTalk only creates a one-way operation.</span></span>  
  
### <a name="to-add-a-web-port"></a><span data-ttu-id="4f037-108">若要添加 Web 端口</span><span class="sxs-lookup"><span data-stu-id="4f037-108">To add a Web port</span></span>  
  
1.  <span data-ttu-id="4f037-109">使用打开的业务流程的业务流程设计器中右键单击端口图面，然后选择**新建配置的端口**。</span><span class="sxs-lookup"><span data-stu-id="4f037-109">In Orchestration Designer, with an orchestration open, right-click the port surface, and then select **New Configured Port**.</span></span>  
  
2.  <span data-ttu-id="4f037-110">在“欢迎使用端口配置向导”  页上，单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="4f037-110">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="4f037-111">上**端口属性**页上，在**名称**文本框中，键入端口的名称，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4f037-111">On the **Port Properties** page, in the **Name** text box, type a name for the port, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="4f037-112">在中**选择端口类型**页上，选择**使用现有端口类型**。</span><span class="sxs-lookup"><span data-stu-id="4f037-112">In the **Select a Port Type** page, select **Use an existing Port Type**.</span></span>  
  
5.  <span data-ttu-id="4f037-113">在中**可用端口类型**框中，展开**Web 端口类型**节点，然后选择 Web 端口类型对应于已添加的 Web 服务，然后依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4f037-113">In the **Available Port Types** box, expand the **Web Port Types** node and select the Web port type that corresponds to the added Web service, and then click **Next**.</span></span>  
  
     <span data-ttu-id="4f037-114">下图显示**选择端口类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="4f037-114">The following figure shows the **Select a Port Type** dialog box.</span></span>  
  
     <span data-ttu-id="4f037-115">![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")</span><span class="sxs-lookup"><span data-stu-id="4f037-115">![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")</span></span>  
  
6.  <span data-ttu-id="4f037-116">在中**端口绑定**页上，在**端口绑定**下拉列表框中，选择**立即指定**。</span><span class="sxs-lookup"><span data-stu-id="4f037-116">In the **Port Binding** page, in the **Port binding** drop down box, select **Specify now**.</span></span> <span data-ttu-id="4f037-117">BizTalk 会自动将引用的 Web 服务中的值放在 URI、 传输和接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="4f037-117">BizTalk automatically places the values from the referenced Web service in the URI, transport, and receive and send pipelines.</span></span> <span data-ttu-id="4f037-118">BizTalk 使用这些值来部署您的 BizTalk 项目时创建发送端口。</span><span class="sxs-lookup"><span data-stu-id="4f037-118">BizTalk uses these values to create the send port when you deploy your BizTalk project.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4f037-119">发送端口的默认身份验证方法是匿名访问。</span><span class="sxs-lookup"><span data-stu-id="4f037-119">The default authentication method for the send port is anonymous access.</span></span> <span data-ttu-id="4f037-120">如果 Web 服务需要不同的身份验证或加密方法，您必须更改配置以提供相应的用户凭据或安全套接字层 (SSL) 来运行 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="4f037-120">If the Web service requires a different authentication or encryption method, you must change the configuration to supply the appropriate user credentials or Secure Sockets Layer (SSL) to run Web services.</span></span> <span data-ttu-id="4f037-121">有关详细信息，请参阅[SOAP Send Adapter](../core/soap-send-adapter.md)和[示例 TMA:HTTP 和 SOAP 适配器](../core/sample-tma-http-and-soap-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="4f037-121">For more information, see [SOAP Send Adapter](../core/soap-send-adapter.md) and [Sample TMA: HTTP and SOAP Adapters](../core/sample-tma-http-and-soap-adapters.md).</span></span>  
  
7.  <span data-ttu-id="4f037-122">单击**下一步**，然后**完成**以完成向导。</span><span class="sxs-lookup"><span data-stu-id="4f037-122">Click **Next**, and then **Finish** to complete the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f037-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f037-123">See Also</span></span>  
 <span data-ttu-id="4f037-124">[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="4f037-124">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="4f037-125">创建 Web 端口</span><span class="sxs-lookup"><span data-stu-id="4f037-125">Creating Web Ports</span></span>](../core/creating-web-ports.md)