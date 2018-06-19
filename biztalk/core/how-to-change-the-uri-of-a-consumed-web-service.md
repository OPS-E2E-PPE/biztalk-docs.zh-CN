---
title: 如何更改使用的 Web 服务的 URI |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, modifying
- Web services, consuming
- consuming [Web services]
- modifying, Web services
ms.assetid: 907de565-8c99-4d34-939f-fd3dba37dd11
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b9ae7d7178fc24c5f16b28325fb627045e5273a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247397"
---
# <a name="how-to-change-the-uri-of-a-consumed-web-service"></a><span data-ttu-id="9619e-102">如何更改已使用的 Web Service 的 URI</span><span class="sxs-lookup"><span data-stu-id="9619e-102">How to Change the URI of a Consumed Web Service</span></span>
<span data-ttu-id="9619e-103">部署业务流程之后，BizTalk Server 将为该业务流程引用的每个 Web Services 都配置一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="9619e-103">After you deploy your orchestration, BizTalk Server configures a send port for each Web service that the orchestration references.</span></span> <span data-ttu-id="9619e-104">默认情况下，BizTalk 在运行时使用的 Web Services 的 URL 与已导入 Web Services 的 URL 相同。</span><span class="sxs-lookup"><span data-stu-id="9619e-104">By default, BizTalk uses the URL of the Web service at run time for the same URL for the imported Web service.</span></span> <span data-ttu-id="9619e-105">你可以使用 BizTalk Server 管理控制台更改此 URL。</span><span class="sxs-lookup"><span data-stu-id="9619e-105">You can change this URL using BizTalk Server Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9619e-106">你必须部署您的业务流程才能更改已使用的 Web Services 的 URI。</span><span class="sxs-lookup"><span data-stu-id="9619e-106">You must deploy your orchestration before you change the URI of a consumed Web service.</span></span> <span data-ttu-id="9619e-107">有关部署您的业务流程的详细信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9619e-107">For more information on deploying your orchestration, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-uri-of-a-consumed-web-service-using-biztalk-server-administration-console"></a><span data-ttu-id="9619e-108">使用 BizTalk Server 管理控制台更改已使用的 Web Services 的 URI</span><span class="sxs-lookup"><span data-stu-id="9619e-108">To change the URI of a consumed Web service using BizTalk Server Administration Console</span></span>  
  
1.  <span data-ttu-id="9619e-109">在 BizTalk Server 管理控制台中，BizTalk 应用程序，再展开**发送端口**节点。</span><span class="sxs-lookup"><span data-stu-id="9619e-109">In BizTalk Server Administration console, expand a BizTalk application, and then expand the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="9619e-110">右键单击使用 SOAP 适配器配置发送端口，请单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="9619e-110">Right-click a send port configured with SOAP adapter, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9619e-111">如果你没有物理端口，可以创建发送端口和接收位置使用 BizTalk 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="9619e-111">If you do not have physical ports, you can create send ports and receive locations by using BizTalk Administration console.</span></span> <span data-ttu-id="9619e-112">有关信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="9619e-112">For information, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
4.  <span data-ttu-id="9619e-113">上**发送属性**对话框中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9619e-113">On the **Send Properties** dialog box, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="9619e-114">在**SOAP 传输属性**对话框中，在**Web 服务 URL**框中，键入 Web 服务的位置的完整 URL，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9619e-114">In the **SOAP Transport Properties** dialog box, in the **Web Service URL** box, type the full URL for the location of the Web service, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9619e-115">应确保对于你指定的 URL 存在 Web Services。</span><span class="sxs-lookup"><span data-stu-id="9619e-115">You should ensure that a Web service exists for the URL that you specify.</span></span> <span data-ttu-id="9619e-116">BizTalk Server 对该 URL 位置不进行验证。</span><span class="sxs-lookup"><span data-stu-id="9619e-116">BizTalk Server does not validate the URL location.</span></span>  
  
6.  <span data-ttu-id="9619e-117">单击确定以退出**发送属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="9619e-117">Click OK to exit the **Send Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9619e-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9619e-118">See Also</span></span>  
 <span data-ttu-id="9619e-119">[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md) </span><span class="sxs-lookup"><span data-stu-id="9619e-119">[Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md) </span></span>  
 <span data-ttu-id="9619e-120">[如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="9619e-120">[How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md) </span></span>  
 <span data-ttu-id="9619e-121">[与使用的 Web 服务的 SOAP 标头](../core/soap-headers-with-consumed-web-services.md) </span><span class="sxs-lookup"><span data-stu-id="9619e-121">[SOAP Headers with Consumed Web Services](../core/soap-headers-with-consumed-web-services.md) </span></span>  
 [<span data-ttu-id="9619e-122">创建 Web 端口</span><span class="sxs-lookup"><span data-stu-id="9619e-122">Creating Web Ports</span></span>](../core/creating-web-ports.md)