---
title: 如何更改已使用的 Web 服务的 URI |Microsoft Docs
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
ms.openlocfilehash: c5fd101ba0553397b6c7144545a9ac557ceada03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342392"
---
# <a name="how-to-change-the-uri-of-a-consumed-web-service"></a><span data-ttu-id="d71f8-102">如何更改已使用的 Web Service 的 URI</span><span class="sxs-lookup"><span data-stu-id="d71f8-102">How to Change the URI of a Consumed Web Service</span></span>
<span data-ttu-id="d71f8-103">在部署您的业务流程后，BizTalk Server 将配置该业务流程引用每个 Web 服务的发送端口。</span><span class="sxs-lookup"><span data-stu-id="d71f8-103">After you deploy your orchestration, BizTalk Server configures a send port for each Web service that the orchestration references.</span></span> <span data-ttu-id="d71f8-104">默认情况下，BizTalk Web 服务的 URL 在运行时使用的导入的 Web 服务的相同 URL。</span><span class="sxs-lookup"><span data-stu-id="d71f8-104">By default, BizTalk uses the URL of the Web service at run time for the same URL for the imported Web service.</span></span> <span data-ttu-id="d71f8-105">你可以更改此 URL 使用 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="d71f8-105">You can change this URL using BizTalk Server Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d71f8-106">更改使用的 Web 服务的 URI 之前，必须部署您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="d71f8-106">You must deploy your orchestration before you change the URI of a consumed Web service.</span></span> <span data-ttu-id="d71f8-107">部署您的业务流程的详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d71f8-107">For more information on deploying your orchestration, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-uri-of-a-consumed-web-service-using-biztalk-server-administration-console"></a><span data-ttu-id="d71f8-108">若要更改使用 BizTalk Server 管理控制台使用的 Web 服务的 URI</span><span class="sxs-lookup"><span data-stu-id="d71f8-108">To change the URI of a consumed Web service using BizTalk Server Administration Console</span></span>  
  
1.  <span data-ttu-id="d71f8-109">在 BizTalk Server 管理控制台中，展开 BizTalk 应用程序，然后展开**发送端口**节点。</span><span class="sxs-lookup"><span data-stu-id="d71f8-109">In BizTalk Server Administration console, expand a BizTalk application, and then expand the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="d71f8-110">右键单击与 SOAP 适配器配置的发送端口，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d71f8-110">Right-click a send port configured with SOAP adapter, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d71f8-111">如果没有物理端口，可以创建发送端口和接收位置使用 BizTalk 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="d71f8-111">If you do not have physical ports, you can create send ports and receive locations by using BizTalk Administration console.</span></span> <span data-ttu-id="d71f8-112">有关信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="d71f8-112">For information, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
4.  <span data-ttu-id="d71f8-113">上**发送属性**对话框中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d71f8-113">On the **Send Properties** dialog box, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="d71f8-114">在中**SOAP 传输属性**对话框中**Web 服务 URL**框中，键入 Web 服务的位置的完整 URL，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d71f8-114">In the **SOAP Transport Properties** dialog box, in the **Web Service URL** box, type the full URL for the location of the Web service, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d71f8-115">您应该确保你指定的 url 存在 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="d71f8-115">You should ensure that a Web service exists for the URL that you specify.</span></span> <span data-ttu-id="d71f8-116">BizTalk Server 不会验证的 URL 位置。</span><span class="sxs-lookup"><span data-stu-id="d71f8-116">BizTalk Server does not validate the URL location.</span></span>  
  
6.  <span data-ttu-id="d71f8-117">单击确定以退出**发送属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="d71f8-117">Click OK to exit the **Send Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d71f8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d71f8-118">See Also</span></span>  
 <span data-ttu-id="d71f8-119">[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md) </span><span class="sxs-lookup"><span data-stu-id="d71f8-119">[Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md) </span></span>  
 <span data-ttu-id="d71f8-120">[如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="d71f8-120">[How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md) </span></span>  
 <span data-ttu-id="d71f8-121">[SOAP 标头与已使用的 Web 服务](../core/soap-headers-with-consumed-web-services.md) </span><span class="sxs-lookup"><span data-stu-id="d71f8-121">[SOAP Headers with Consumed Web Services](../core/soap-headers-with-consumed-web-services.md) </span></span>  
 [<span data-ttu-id="d71f8-122">创建 Web 端口</span><span class="sxs-lookup"><span data-stu-id="d71f8-122">Creating Web Ports</span></span>](../core/creating-web-ports.md)