---
title: 如何使用 Web Services 在消息传递的仅限方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66873959-5b1b-4d9b-ad19-f083670420b8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ac3e87d54ab7babed8be6b4d81267d22d8ac319
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249421"
---
# <a name="how-to-consume-web-services-in-a-messaging-only-scenario"></a><span data-ttu-id="b3509-102">如何在仅进行消息传送的方案中使用 Web Services</span><span class="sxs-lookup"><span data-stu-id="b3509-102">How to Consume Web Services in a Messaging Only Scenario</span></span>
<span data-ttu-id="b3509-103">SOAP 适配器的新增强之一便是其在仅进行消息传送的方案中使用基于内容的路由发送端口调用 Web Services 的能力。</span><span class="sxs-lookup"><span data-stu-id="b3509-103">One of the new enhancements for the SOAP adapter is ability to call Web services in a messaging only scenario by using content-based routing send ports.</span></span> <span data-ttu-id="b3509-104">此功能使得在无需创建业务流程的情况下使用 Web Services 成为可能。</span><span class="sxs-lookup"><span data-stu-id="b3509-104">This feature makes it possible to consume Web services without creating orchestrations.</span></span> <span data-ttu-id="b3509-105">此外，由于消息不再通过业务流程，在使用 Web Services 时它还具有更为出色的性能表现。</span><span class="sxs-lookup"><span data-stu-id="b3509-105">It also provides better performance to consume Web services because messages do not pass through orchestrations.</span></span>  
  
 <span data-ttu-id="b3509-106">要在仅进行消息传送的方案中使用 Web Services，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b3509-106">To consume Web services in a messaging only scenario, do the following:</span></span>  
  
-   <span data-ttu-id="b3509-107">创建代理库和用于调用 Web 服务的 XML 架构</span><span class="sxs-lookup"><span data-stu-id="b3509-107">Create a proxy library and XML schemas for invoking Web services</span></span>  
  
-   <span data-ttu-id="b3509-108">配置发送端口和接收使用 Web 服务的位置</span><span class="sxs-lookup"><span data-stu-id="b3509-108">Configure a send port and receive location for consuming a Web service</span></span>  
  
### <a name="to-create-a-proxy-library-and-xml-schemas-for-invoking-web-services"></a><span data-ttu-id="b3509-109">为调用 Web Services 创建代理库和 XML 架构</span><span class="sxs-lookup"><span data-stu-id="b3509-109">To create a proxy library and XML schemas for invoking Web services</span></span>  
  
1.  <span data-ttu-id="b3509-110">确定 Web Services 的 URL。</span><span class="sxs-lookup"><span data-stu-id="b3509-110">Determine the URL for the Web service.</span></span>  
  
2.  <span data-ttu-id="b3509-111">打开**空 BizTalk 服务器项目**中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="b3509-111">Open an **Empty BizTalk Server Project** in a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solution.</span></span> <span data-ttu-id="b3509-112">有关如何创建 BizTalk 服务器项目的详细信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="b3509-112">For more information about how to create a BizTalk Server project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3509-113">此演练使用 BizTalk Server 项目来生成 Web Services 使用的代理库和 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="b3509-113">This walkthrough uses a BizTalk Server project to generate proxy libraries and XML schemas that the Web service uses.</span></span> <span data-ttu-id="b3509-114">此外可以实现此目的，在.NET Framework 4.0 SDK 中使用的 Wsdl.exe 和 Xsd.exe。</span><span class="sxs-lookup"><span data-stu-id="b3509-114">You can also use the Wsdl.exe and Xsd.exe in the .NET Framework 4.0 SDK for the same purpose.</span></span>  
  
3.  <span data-ttu-id="b3509-115">在解决方案资源管理器，右键单击 BizTalk 服务器项目名称，，然后单击**添加服务引用**。</span><span class="sxs-lookup"><span data-stu-id="b3509-115">In Solution Explorer, right-click the BizTalk Server project name, and then click **Add Service Reference**.</span></span>  
  
4.  <span data-ttu-id="b3509-116">在**添加服务引用**对话框中，单击**高级**。</span><span class="sxs-lookup"><span data-stu-id="b3509-116">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
5.  <span data-ttu-id="b3509-117">在**服务引用设置**对话框中，单击**添加 Web 引用**中**兼容性**部分。</span><span class="sxs-lookup"><span data-stu-id="b3509-117">In the **Service Reference Settings** dialog box, Click **Add Web Reference** in the **Compatibility** section.</span></span>  
  
6.  <span data-ttu-id="b3509-118">在**添加 Web 引用**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b3509-118">In the **Add Web Reference** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="b3509-119">在**URL**字段中键入 Web 服务 URL，然后依次**转**。</span><span class="sxs-lookup"><span data-stu-id="b3509-119">In the **URL** field, type a Web service URL, and then click **Go**.</span></span>  
  
    2.  <span data-ttu-id="b3509-120">在**Web 引用名称**字段，为命名空间中，键入一个名称，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="b3509-120">In the **Web reference name** field, type a name for the namespace, and then click **Add Reference**.</span></span>  
  
7.  <span data-ttu-id="b3509-121">Web 引用将出现在**Web 引用**在解决方案资源管理器中的节点。</span><span class="sxs-lookup"><span data-stu-id="b3509-121">The Web reference will appear under **Web References** node in Solution Explorer.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b3509-122">Web 引用添加到 BizTalk 项目，一旦**添加 Web 引用**右键单击项目名称时，命令时直接可用或**引用**或**Web 引用**.</span><span class="sxs-lookup"><span data-stu-id="b3509-122">Once you have a web reference added to a BizTalk project, the **Add Web Reference** command is directly available when you right-click the project name or **References** or **Web References**.</span></span>  
  
8.  <span data-ttu-id="b3509-123">在解决方案资源管理器，右键单击项目名称，然后单击**属性**以启动项目设计器。</span><span class="sxs-lookup"><span data-stu-id="b3509-123">In Solution Explorer, right-click the project name, and then click **Properties** to launch the Project Designer.</span></span>  
  
9. <span data-ttu-id="b3509-124">在项目设计器中，单击**签名**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b3509-124">In the Project Designer, click the **Signing** tab.</span></span>  
  
10. <span data-ttu-id="b3509-125">选择**对程序集签名**选项上，单击下拉列表**选择强名称密钥文件**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="b3509-125">Select **Sign the assembly** option, click the drop-down list for the **Choose a strong name key file**, and then click **Browse**.</span></span>  
  
11. <span data-ttu-id="b3509-126">浏览并选择的程序集密钥文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="b3509-126">Browse and select the assembly key file, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="b3509-127">在解决方案资源管理器，右键单击项目名称，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="b3509-127">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
13. <span data-ttu-id="b3509-128">在解决方案资源管理器，右键单击项目名称，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="b3509-128">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>  
  
### <a name="to-configure-a-send-port-and-receive-location-for-consuming-a-web-service"></a><span data-ttu-id="b3509-129">为使用 Web Services 配置发送端口和接收位置</span><span class="sxs-lookup"><span data-stu-id="b3509-129">To configure a send port and receive location for consuming a Web service</span></span>  
  
1.  <span data-ttu-id="b3509-130">在 BizTalk Server 管理控制台中，创建一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="b3509-130">In the BizTalk Server Administration console, create a send port.</span></span> <span data-ttu-id="b3509-131">有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="b3509-131">For more information, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="b3509-132">在创建发送端口时，选择 SOAP 作为传输类型或传输协议。</span><span class="sxs-lookup"><span data-stu-id="b3509-132">When creating the send port, select SOAP as the transport type or transport protocol.</span></span>  
  
2.  <span data-ttu-id="b3509-133">使用以下设置配置 SOAP 发送端口。</span><span class="sxs-lookup"><span data-stu-id="b3509-133">Configure the SOAP send port with the following settings.</span></span> <span data-ttu-id="b3509-134">有关详细信息，请参阅[如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="b3509-134">For more information, see [How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md).</span></span>  
  
    |<span data-ttu-id="b3509-135">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b3509-135">Use this</span></span>|<span data-ttu-id="b3509-136">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b3509-136">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b3509-137">**以下设置**</span><span class="sxs-lookup"><span data-stu-id="b3509-137">**The following settings**</span></span>|<span data-ttu-id="b3509-138">选择此选项可指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="b3509-138">Select this option to specify the following properties.</span></span>|  
    |<span data-ttu-id="b3509-139">**程序集名称**</span><span class="sxs-lookup"><span data-stu-id="b3509-139">**Assembly name**</span></span>|<span data-ttu-id="b3509-140">选择在前面的过程中创建的程序集。</span><span class="sxs-lookup"><span data-stu-id="b3509-140">Select the assembly created in the previous procedure.</span></span> <span data-ttu-id="b3509-141">程序集的完全限定的名写入到 SOAP 适配器**AssemblyName**属性。</span><span class="sxs-lookup"><span data-stu-id="b3509-141">The fully qualified name of the assembly is written to the SOAP adapter **AssemblyName** property.</span></span>|  
    |<span data-ttu-id="b3509-142">**类型名称**</span><span class="sxs-lookup"><span data-stu-id="b3509-142">**Type name**</span></span>|<span data-ttu-id="b3509-143">指定包含要调用的 Web 方法的类的名称。</span><span class="sxs-lookup"><span data-stu-id="b3509-143">Specify the name of the class that contains the Web method to be invoked.</span></span> <span data-ttu-id="b3509-144">类型名称写入 SOAP 适配器**TypeName**属性。</span><span class="sxs-lookup"><span data-stu-id="b3509-144">The type name is written to the SOAP adapter **TypeName** property.</span></span>|  
    |<span data-ttu-id="b3509-145">**方法名称**</span><span class="sxs-lookup"><span data-stu-id="b3509-145">**Method name**</span></span>|<span data-ttu-id="b3509-146">指定列表框中的方法之一。</span><span class="sxs-lookup"><span data-stu-id="b3509-146">Specify one of the methods in the list box.</span></span> <span data-ttu-id="b3509-147">Web 方法写入 Soap 适配器**MethodName**属性。</span><span class="sxs-lookup"><span data-stu-id="b3509-147">The Web method is written to the Soap Adapter **MethodName** property.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="b3509-148">如果要使用基于内容的路由 (CBR)，请配置发送端口的筛选器。</span><span class="sxs-lookup"><span data-stu-id="b3509-148">If you want to use Content-Based Routing (CBR), configure the filter of the send port.</span></span> <span data-ttu-id="b3509-149">有关详细信息，请参阅[如何将筛选器配置为发送端口](../core/how-to-configure-filters-for-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="b3509-149">For more information, see [How to Configure Filters for a Send Port](../core/how-to-configure-filters-for-a-send-port.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3509-150">如果没有订阅者订阅来自所调用 Web Services 的响应消息，将发生路由失败错误。</span><span class="sxs-lookup"><span data-stu-id="b3509-150">If there is no subscriber to the response messages from the invoked Web services, a routing failure error will occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3509-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3509-151">See Also</span></span>  
 [<span data-ttu-id="b3509-152">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="b3509-152">Consuming Web Services</span></span>](../core/consuming-web-services.md)