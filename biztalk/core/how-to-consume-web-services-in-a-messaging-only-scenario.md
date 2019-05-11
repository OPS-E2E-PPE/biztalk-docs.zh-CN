---
title: 在仅消息传递方案中如何使用 Web Services |Microsoft Docs
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
ms.openlocfilehash: 34a58ae2d7ece7de0814359779de0fef95294ed5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340146"
---
# <a name="how-to-consume-web-services-in-a-messaging-only-scenario"></a><span data-ttu-id="e4296-102">如何仅消息传递方案中使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="e4296-102">How to Consume Web Services in a Messaging Only Scenario</span></span>
<span data-ttu-id="e4296-103">SOAP 适配器的新增强功能之一是能够使用基于内容的路由发送端口在仅消息传递方案中调用 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="e4296-103">One of the new enhancements for the SOAP adapter is ability to call Web services in a messaging only scenario by using content-based routing send ports.</span></span> <span data-ttu-id="e4296-104">此功能使可能使用 Web 服务，而无需创建业务流程。</span><span class="sxs-lookup"><span data-stu-id="e4296-104">This feature makes it possible to consume Web services without creating orchestrations.</span></span> <span data-ttu-id="e4296-105">它还提供更好的性能，可以使用 Web 服务，因为消息未通过业务流程。</span><span class="sxs-lookup"><span data-stu-id="e4296-105">It also provides better performance to consume Web services because messages do not pass through orchestrations.</span></span>  
  
 <span data-ttu-id="e4296-106">若要使用 Web 服务在仅消息传递方案中的，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e4296-106">To consume Web services in a messaging only scenario, do the following:</span></span>  
  
-   <span data-ttu-id="e4296-107">创建代理库和 XML 架构，用于调用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="e4296-107">Create a proxy library and XML schemas for invoking Web services</span></span>  
  
-   <span data-ttu-id="e4296-108">配置发送端口和接收位置以使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="e4296-108">Configure a send port and receive location for consuming a Web service</span></span>  
  
### <a name="to-create-a-proxy-library-and-xml-schemas-for-invoking-web-services"></a><span data-ttu-id="e4296-109">若要创建代理库和 XML 架构，用于调用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="e4296-109">To create a proxy library and XML schemas for invoking Web services</span></span>  
  
1. <span data-ttu-id="e4296-110">确定 Web 服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="e4296-110">Determine the URL for the Web service.</span></span>  
  
2. <span data-ttu-id="e4296-111">打开**空的 BizTalk Server 项目**中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="e4296-111">Open an **Empty BizTalk Server Project** in a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solution.</span></span> <span data-ttu-id="e4296-112">有关如何创建 BizTalk Server 项目的详细信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="e4296-112">For more information about how to create a BizTalk Server project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e4296-113">本演练使用 BizTalk Server 项目生成的代理库和 Web 服务使用的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="e4296-113">This walkthrough uses a BizTalk Server project to generate proxy libraries and XML schemas that the Web service uses.</span></span> <span data-ttu-id="e4296-114">此外可以实现相同目的，在.NET Framework 4.0 SDK 中使用 Wsdl.exe 和 Xsd.exe。</span><span class="sxs-lookup"><span data-stu-id="e4296-114">You can also use the Wsdl.exe and Xsd.exe in the .NET Framework 4.0 SDK for the same purpose.</span></span>  
  
3. <span data-ttu-id="e4296-115">在解决方案资源管理器，右键单击 BizTalk Server 项目名称，然后依次**添加服务引用**。</span><span class="sxs-lookup"><span data-stu-id="e4296-115">In Solution Explorer, right-click the BizTalk Server project name, and then click **Add Service Reference**.</span></span>  
  
4. <span data-ttu-id="e4296-116">在中**添加服务引用**对话框中，单击**高级**。</span><span class="sxs-lookup"><span data-stu-id="e4296-116">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
5. <span data-ttu-id="e4296-117">在中**服务引用设置**对话框中，单击**添加 Web 引用**中**兼容性**部分。</span><span class="sxs-lookup"><span data-stu-id="e4296-117">In the **Service Reference Settings** dialog box, Click **Add Web Reference** in the **Compatibility** section.</span></span>  
  
6. <span data-ttu-id="e4296-118">在中**添加 Web 引用**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e4296-118">In the **Add Web Reference** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="e4296-119">在中**URL**字段中，键入 Web 服务 URL，然后单击**转**。</span><span class="sxs-lookup"><span data-stu-id="e4296-119">In the **URL** field, type a Web service URL, and then click **Go**.</span></span>  
  
   2.  <span data-ttu-id="e4296-120">在中**Web 引用名**字段，为命名空间中，键入一个名称，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="e4296-120">In the **Web reference name** field, type a name for the namespace, and then click **Add Reference**.</span></span>  
  
7. <span data-ttu-id="e4296-121">Web 引用将显示下**Web 引用**在解决方案资源管理器中的节点。</span><span class="sxs-lookup"><span data-stu-id="e4296-121">The Web reference will appear under **Web References** node in Solution Explorer.</span></span>  
  
   > [!TIP]
   >  <span data-ttu-id="e4296-122">Web 引用添加到 BizTalk 项目后**添加 Web 引用**当您右键单击项目名称时，才直接可用命令或**引用**或**的Web引用**.</span><span class="sxs-lookup"><span data-stu-id="e4296-122">Once you have a web reference added to a BizTalk project, the **Add Web Reference** command is directly available when you right-click the project name or **References** or **Web References**.</span></span>  
  
8. <span data-ttu-id="e4296-123">在解决方案资源管理器，右键单击项目名称，然后单击**属性**启动项目设计器。</span><span class="sxs-lookup"><span data-stu-id="e4296-123">In Solution Explorer, right-click the project name, and then click **Properties** to launch the Project Designer.</span></span>  
  
9. <span data-ttu-id="e4296-124">在项目设计器中，单击**签名**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e4296-124">In the Project Designer, click the **Signing** tab.</span></span>  
  
10. <span data-ttu-id="e4296-125">选择**为程序集签名**选项，请单击下拉列表**选择一个强名称密钥文件**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="e4296-125">Select **Sign the assembly** option, click the drop-down list for the **Choose a strong name key file**, and then click **Browse**.</span></span>  
  
11. <span data-ttu-id="e4296-126">浏览并选择程序集密钥文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="e4296-126">Browse and select the assembly key file, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="e4296-127">在解决方案资源管理器，右键单击项目名称，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="e4296-127">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
13. <span data-ttu-id="e4296-128">在解决方案资源管理器，右键单击项目名称，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="e4296-128">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>  
  
### <a name="to-configure-a-send-port-and-receive-location-for-consuming-a-web-service"></a><span data-ttu-id="e4296-129">若要配置的发送端口和接收位置，用于使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="e4296-129">To configure a send port and receive location for consuming a Web service</span></span>  
  
1.  <span data-ttu-id="e4296-130">在 BizTalk Server 管理控制台中，创建一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="e4296-130">In the BizTalk Server Administration console, create a send port.</span></span> <span data-ttu-id="e4296-131">有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="e4296-131">For more information, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="e4296-132">创建发送端口时，选择 SOAP 作为传输类型或传输协议。</span><span class="sxs-lookup"><span data-stu-id="e4296-132">When creating the send port, select SOAP as the transport type or transport protocol.</span></span>  
  
2.  <span data-ttu-id="e4296-133">使用以下设置配置 SOAP 发送端口。</span><span class="sxs-lookup"><span data-stu-id="e4296-133">Configure the SOAP send port with the following settings.</span></span> <span data-ttu-id="e4296-134">有关详细信息，请参阅[如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="e4296-134">For more information, see [How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md).</span></span>  
  
    |<span data-ttu-id="e4296-135">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e4296-135">Use this</span></span>|<span data-ttu-id="e4296-136">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e4296-136">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e4296-137">**以下设置**</span><span class="sxs-lookup"><span data-stu-id="e4296-137">**The following settings**</span></span>|<span data-ttu-id="e4296-138">选择此选项可指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="e4296-138">Select this option to specify the following properties.</span></span>|  
    |<span data-ttu-id="e4296-139">**程序集名称**</span><span class="sxs-lookup"><span data-stu-id="e4296-139">**Assembly name**</span></span>|<span data-ttu-id="e4296-140">选择在上一过程中创建的程序集。</span><span class="sxs-lookup"><span data-stu-id="e4296-140">Select the assembly created in the previous procedure.</span></span> <span data-ttu-id="e4296-141">程序集的完全限定的名写入到 SOAP 适配器**AssemblyName**属性。</span><span class="sxs-lookup"><span data-stu-id="e4296-141">The fully qualified name of the assembly is written to the SOAP adapter **AssemblyName** property.</span></span>|  
    |<span data-ttu-id="e4296-142">**类型名称**</span><span class="sxs-lookup"><span data-stu-id="e4296-142">**Type name**</span></span>|<span data-ttu-id="e4296-143">指定包含要调用的 Web 方法的类的名称。</span><span class="sxs-lookup"><span data-stu-id="e4296-143">Specify the name of the class that contains the Web method to be invoked.</span></span> <span data-ttu-id="e4296-144">类型名称写入到 SOAP 适配器**TypeName**属性。</span><span class="sxs-lookup"><span data-stu-id="e4296-144">The type name is written to the SOAP adapter **TypeName** property.</span></span>|  
    |<span data-ttu-id="e4296-145">**方法名称**</span><span class="sxs-lookup"><span data-stu-id="e4296-145">**Method name**</span></span>|<span data-ttu-id="e4296-146">在列表框中指定的方法之一。</span><span class="sxs-lookup"><span data-stu-id="e4296-146">Specify one of the methods in the list box.</span></span> <span data-ttu-id="e4296-147">Web 方法写入到 Soap 适配器**MethodName**属性。</span><span class="sxs-lookup"><span data-stu-id="e4296-147">The Web method is written to the Soap Adapter **MethodName** property.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="e4296-148">如果你想要使用基于内容的路由 (CBR)，配置发送端口的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e4296-148">If you want to use Content-Based Routing (CBR), configure the filter of the send port.</span></span> <span data-ttu-id="e4296-149">有关详细信息，请参阅[如何为发送端口配置筛选器](../core/how-to-configure-filters-for-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="e4296-149">For more information, see [How to Configure Filters for a Send Port](../core/how-to-configure-filters-for-a-send-port.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4296-150">如果调用 Web 服务的响应消息没有订户，将发生路由失败错误。</span><span class="sxs-lookup"><span data-stu-id="e4296-150">If there is no subscriber to the response messages from the invoked Web services, a routing failure error will occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4296-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4296-151">See Also</span></span>  
 [<span data-ttu-id="e4296-152">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="e4296-152">Consuming Web Services</span></span>](../core/consuming-web-services.md)