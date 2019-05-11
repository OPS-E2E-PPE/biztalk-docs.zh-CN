---
title: 第 2 步：测试 Echo 适配器的入站处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86dede9b-6b7e-4901-9c79-b75bfee9155f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f238a6ddafb70aa30d8b736042e48b0466b77a42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363261"
---
# <a name="step-2-test-inbound-handler-of-the-echo-adapter"></a><span data-ttu-id="6fd9f-102">第 2 步：测试 Echo 适配器的入站处理程序</span><span class="sxs-lookup"><span data-stu-id="6fd9f-102">Step 2: Test Inbound Handler of the Echo Adapter</span></span>
<span data-ttu-id="6fd9f-103">![步骤 2 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span><span class="sxs-lookup"><span data-stu-id="6fd9f-103">![Step 2 of 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span></span>  
  
 <span data-ttu-id="6fd9f-104">**若要完成的时间：** 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="6fd9f-105">在此步骤中，测试 Echo 适配器提供的入站的服务。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-105">In this step, you test the inbound service provided by the Echo Adapter.</span></span> <span data-ttu-id="6fd9f-106">为此，使用 Visual Studio 中，添加适配器服务参考 Visual Studio 插件和自定义代码。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-106">You do this using Visual Studio, the Add Adapter Service Reference Visual Studio Plug-In and custom code.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6fd9f-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="6fd9f-107">Prerequisites</span></span>  
 <span data-ttu-id="6fd9f-108">若要完成此步骤中，你必须完成[教程 1:开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-108">To complete this step, you must have completed [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span> <span data-ttu-id="6fd9f-109">完成此步骤可以独立于[步骤 1:测试 Echo 适配器的出站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-109">This step can be completed independent of [Step 1: Test Outbound Handler of the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md).</span></span>  
  
## <a name="create-a-visual-studio-project"></a><span data-ttu-id="6fd9f-110">创建 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="6fd9f-110">Create a Visual Studio project</span></span>  
  
1.  <span data-ttu-id="6fd9f-111">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-111">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="6fd9f-112">在 Visual Studio 中，在**文件**菜单，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-112">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="6fd9f-113">在中**新的项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6fd9f-113">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="6fd9f-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6fd9f-114">Use this</span></span>|<span data-ttu-id="6fd9f-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6fd9f-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6fd9f-116">**项目类型**</span><span class="sxs-lookup"><span data-stu-id="6fd9f-116">**Project types**</span></span>|<span data-ttu-id="6fd9f-117">单击**Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-117">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="6fd9f-118">**模板**</span><span class="sxs-lookup"><span data-stu-id="6fd9f-118">**Templates**</span></span>|<span data-ttu-id="6fd9f-119">单击**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-119">Click **Console Application**.</span></span>|  
    |<span data-ttu-id="6fd9f-120">**名称**</span><span class="sxs-lookup"><span data-stu-id="6fd9f-120">**Name**</span></span>|<span data-ttu-id="6fd9f-121">类型**ConsumeEchoAdapter_Inbound**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-121">Type **ConsumeEchoAdapter_Inbound**.</span></span>|  
    |<span data-ttu-id="6fd9f-122">**位置**</span><span class="sxs-lookup"><span data-stu-id="6fd9f-122">**Location**</span></span>|<span data-ttu-id="6fd9f-123">类型**C:\Tutorials**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-123">Type **C:\Tutorials**.</span></span>|  
    |<span data-ttu-id="6fd9f-124">**解决方案名称**</span><span class="sxs-lookup"><span data-stu-id="6fd9f-124">**Solution Name**</span></span>|<span data-ttu-id="6fd9f-125">类型**ConsumeEchoAdapter_Inbound**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-125">Type **ConsumeEchoAdapter_Inbound**.</span></span>|  
  
4.  <span data-ttu-id="6fd9f-126">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-126">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="6fd9f-127">在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-127">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="browse-search-and-generate-the-wcf-service"></a><span data-ttu-id="6fd9f-128">浏览、 搜索和生成的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="6fd9f-128">Browse, search, and generate the WCF service</span></span>  
  
1.  <span data-ttu-id="6fd9f-129">在 Visual Studio 解决方案窗格中，右键单击**ConsumeEchoAdapter_Inbound**项目，然后选择**添加适配器服务引用**以启动添加适配器服务引用插件。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-129">In the Visual Studio Solution pane, right-click **ConsumeEchoAdapter_Inbound** project then choose **Add Adapter Service Reference** to launch the Add Adapter Service Reference plug-in.</span></span>  
  
2.  <span data-ttu-id="6fd9f-130">在中**添加适配器服务引用**屏幕上，选择一个绑定。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-130">In the **Add Adapter Service Reference** screen, choose a binding.</span></span> <span data-ttu-id="6fd9f-131">这可通过选择**echoAdapterBindingV2**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-131">This is done by choosing **echoAdapterBindingV2**.</span></span>  
  
3.  <span data-ttu-id="6fd9f-132">接下来，通过单击配置的适配器和 connection 属性**配置**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-132">Next, configure the adapter and connection properties by clicking **Configure**.</span></span>  <span data-ttu-id="6fd9f-133">这将打开**配置适配器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-133">This opens the **Configure Adapter** screen.</span></span>  
  
4.  <span data-ttu-id="6fd9f-134">在中**配置适配器**屏幕上，选择**绑定属性**选项卡以配置适配器属性。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-134">In the **Configure Adapter** screen, select the **Binding Properties** tab to configure the adapter properties.</span></span> <span data-ttu-id="6fd9f-135">请注意，自定义 Echo 适配器类别**入站**并**杂项**显示。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-135">Notice that the custom Echo Adapter categories **Inbound** and **Misc** are shown.</span></span> <span data-ttu-id="6fd9f-136">下**杂项**类别中，单击**InboundFileSystemWatcherFolder** ，然后输入你想要监视的目录。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-136">Under the **Misc** category, click **InboundFileSystemWatcherFolder** and then enter the directory you want to monitor.</span></span>  
  
5.  <span data-ttu-id="6fd9f-137">单击**确定**以关闭**配置适配器**屏幕上，并返回到**添加适配器服务引用**屏幕。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-137">Click **OK** to close the **Configure Adapter** screen and return to the **Add Adapter Service Reference** screen.</span></span>  
  
6.  <span data-ttu-id="6fd9f-138">接下来，单击**Connect**连接到 Echo 适配器 （和假设它支持的业务线系统）。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-138">Next, click **Connect** to connect to the Echo Adapter (and hypothetical line-of-business system it supports).</span></span> <span data-ttu-id="6fd9f-139">几分钟后，连接状态应更改为**已连接**和类别树 (下**选择一个类别**) 应填充。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-139">After a few moments, the connection status should change to **Connected** and the Category Tree (under **Select a category**) should be populated.</span></span>  
  
7.  <span data-ttu-id="6fd9f-140">若要查看可用的入站的操作，请更改**服务协定类型**到**服务 （入站操作）**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-140">To view available inbound operations, change the **Service contract type** to **Service (Inbound operations)**.</span></span>  
  
8.  <span data-ttu-id="6fd9f-141">在类别树中，单击**主类别**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-141">In the Category Tree, click **Main Category**.</span></span> <span data-ttu-id="6fd9f-142">这将填充可用类别和与单个的入站操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-142">This populates the list of available categories and operations with a single inbound operation.</span></span> <span data-ttu-id="6fd9f-143">没有类别。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-143">There are no categories.</span></span>  
  
9. <span data-ttu-id="6fd9f-144">在中**可用类别和操作**，选择**OnReceiveEcho**操作。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-144">In the **Available Categories and Operations**, select the **OnReceiveEcho** operation.</span></span> <span data-ttu-id="6fd9f-145">单击**添加**以使生成的 WCF 接口的所选的操作部分。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-145">Click **Add** to make the selected operations part of the generated WCF interface.</span></span>  
  
10. <span data-ttu-id="6fd9f-146">单击**确定**生成 WCF 接口。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-146">Click **OK** to generate the WCF interface.</span></span> <span data-ttu-id="6fd9f-147">这将应用程序配置文件 (app.config)、 WCF 接口 (EchoAdapterBindingInterface.cs) 和 WCF 服务 (EchoAdapterBindingService.cs) 添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-147">This adds an application configuration file (app.config), a WCF interface (EchoAdapterBindingInterface.cs) and a WCF service (EchoAdapterBindingService.cs) to the project.</span></span>  
  
11. <span data-ttu-id="6fd9f-148">单击**文件**上**Visual Studio**菜单，然后选择**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-148">Click **File** on the **Visual Studio** menu and choose **Save All**.</span></span>  
  
## <a name="test-the-echo-adapter"></a><span data-ttu-id="6fd9f-149">测试 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="6fd9f-149">Test the Echo Adapter</span></span>  
  
1.  <span data-ttu-id="6fd9f-150">在解决方案资源管理器中双击**EchoAdapterBindingService.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-150">In Solution Explorer, double-click the **EchoAdapterBindingService.cs** file.</span></span>  
  
2.  <span data-ttu-id="6fd9f-151">在 Visual Studio 编辑器中，内部**OnReceiveEcho**方法，用以下代码替换现有的实现：</span><span class="sxs-lookup"><span data-stu-id="6fd9f-151">In the Visual Studio editor, inside the **OnReceiveEcho** method, replace the existing implementation with the following:</span></span>  
  
    ```csharp  
    System.Console.WriteLine("path = " + path + ", len = " + length);  
    ```  
  
3.  <span data-ttu-id="6fd9f-152">在解决方案资源管理器中双击**Program.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-152">In Solution Explorer, double-click the **Program.cs** file.</span></span>  
  
4.  <span data-ttu-id="6fd9f-153">在 Visual Studio 编辑器中，在 Main 方法中，添加以下代码以承载 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-153">In the Visual Studio editor, inside the Main method, add the following code to host the WCF service.</span></span>  
  
    ```csharp  
    try  
    {  
        // Create a ServiceHost for the EchoServiceImpl type  
        // and use the base address from app.config  
        System.ServiceModel.ServiceHost host = new System.ServiceModel.ServiceHost(typeof(EchoAdapterBindingNamespace.EchoAdapterBindingService));  
  
        // Open the ServiceHost to start listening for messages  
        host.Open();  
  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost  
        host.Close();  
    }  
    catch (TimeoutException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    catch (System.ServiceModel.CommunicationException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    ```  
  
5.  <span data-ttu-id="6fd9f-154">在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-154">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="6fd9f-155">按 F5 以启动示例。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-155">Press F5 to start the sample.</span></span>  
  
7.  <span data-ttu-id="6fd9f-156">放入在本教程前面指定的目录的"txt"扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-156">Drop a file with the "txt" extension into the directory specified earlier in this tutorial.</span></span> <span data-ttu-id="6fd9f-157">应看到类似于程序输出窗口中的以下信息：</span><span class="sxs-lookup"><span data-stu-id="6fd9f-157">You should see information similar to the following in the program output window:</span></span>  
  
     <span data-ttu-id="6fd9f-158">**服务已准备就绪。**</span><span class="sxs-lookup"><span data-stu-id="6fd9f-158">**The service is ready.**</span></span>  
  
     <span data-ttu-id="6fd9f-159">**按\<ENTER\>以终止服务。**</span><span class="sxs-lookup"><span data-stu-id="6fd9f-159">**Press \<ENTER\> to terminate service.**</span></span>  
  
     <span data-ttu-id="6fd9f-160">**路径 = file:///C:/Tutorial/InboundTest/InboundTest.txt，len = 229179**</span><span class="sxs-lookup"><span data-stu-id="6fd9f-160">**path = file:///C:/Tutorial/InboundTest/InboundTest.txt, len = 229179**</span></span>  
  
8.  <span data-ttu-id="6fd9f-161">按 Enter 键以停止服务。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-161">Press the Enter key to stop the service.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="6fd9f-162">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="6fd9f-162">What Did I Just Do?</span></span>  
 <span data-ttu-id="6fd9f-163">在此步骤中，您创建的测试应用程序对于开发中的公开 Echo 适配器的入站的操作[教程 1:开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-163">In this step, you created a test application for the inbound operation exposed by the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span> <span data-ttu-id="6fd9f-164">若要执行此操作，创建了一个 Visual Studio 项目，生成 WCF 服务，，并提供代码以承载 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-164">To do this, you created a Visual Studio project, generated a WCF Service, and provided code to host the WCF Service.</span></span> <span data-ttu-id="6fd9f-165">最后，您运行了测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-165">Finally, you ran the test application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6fd9f-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6fd9f-166">Next Steps</span></span>  
 <span data-ttu-id="6fd9f-167">这是本教程的最后一步。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-167">This is the last step of the tutorial.</span></span> <span data-ttu-id="6fd9f-168">入站操作的详细信息，请参阅`Microsoft.ServiceModel.Channels.Common.IInboundHandler`。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-168">For more information about Inbound operations, see `Microsoft.ServiceModel.Channels.Common.IInboundHandler`.</span></span> <span data-ttu-id="6fd9f-169">若要查看示例演示如何承载需要进行身份验证的 WCF 服务的 SDK，下载在 echo 适配器和测试代码[ http://go.microsoft.com/fwlink/?LinkID=96184 ](http://go.microsoft.com/fwlink/?LinkID=96184)。</span><span class="sxs-lookup"><span data-stu-id="6fd9f-169">To see an example SDK that demonstrates how to host a WCF Service that requires authentication, download the echo adapter and test code at [http://go.microsoft.com/fwlink/?LinkID=96184](http://go.microsoft.com/fwlink/?LinkID=96184).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd9f-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fd9f-170">See Also</span></span>  
 <span data-ttu-id="6fd9f-171">[教程 2：使用通过.NET Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span><span class="sxs-lookup"><span data-stu-id="6fd9f-171">[Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span></span>  
 [<span data-ttu-id="6fd9f-172">教程 1:开发 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="6fd9f-172">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)