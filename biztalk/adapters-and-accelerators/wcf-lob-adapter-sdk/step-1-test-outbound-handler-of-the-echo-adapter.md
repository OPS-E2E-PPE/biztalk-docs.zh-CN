---
title: 步骤 1： 测试的 Echo 适配器的出站处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4a8164-a584-436f-b20b-4c884f6e2b37
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba2b1d6586588d17c58c0ca9a74cb11a7a9bd9f2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="step-1-test-outbound-handler-of-the-echo-adapter"></a><span data-ttu-id="fca60-102">步骤 1： 测试 Echo 适配器的出站处理的程序</span><span class="sxs-lookup"><span data-stu-id="fca60-102">Step 1: Test Outbound Handler of the Echo Adapter</span></span>
<span data-ttu-id="fca60-103">![2 的第 1 步](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span><span class="sxs-lookup"><span data-stu-id="fca60-103">![Step 1 of 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span></span>  
  
 <span data-ttu-id="fca60-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="fca60-104">**Time to Complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="fca60-105">在此步骤中，你将测试由 Echo 适配器提供的三个出站操作。</span><span class="sxs-lookup"><span data-stu-id="fca60-105">In this step, you will test the three outbound operations provided by the Echo Adapter.</span></span> <span data-ttu-id="fca60-106">你将执行此操作使用 Visual Studio 中，添加适配器服务引用 Visual Studio 插件和自定义代码。</span><span class="sxs-lookup"><span data-stu-id="fca60-106">You will do this using Visual Studio, the Add Adapter Service Reference Visual Studio Plug-In and custom code.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fca60-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="fca60-107">Prerequisites</span></span>  
 <span data-ttu-id="fca60-108">若要完成此步骤，你必须已完成[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fca60-108">To complete this step, you must have completed [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
## <a name="create-a-visual-studio-project"></a><span data-ttu-id="fca60-109">创建 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="fca60-109">Create a Visual Studio project</span></span>  
  
1.  <span data-ttu-id="fca60-110">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="fca60-110">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="fca60-111">在 Visual Studio 中，在**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="fca60-111">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="fca60-112">在 **新项目** 对话框框中，执行以下操作︰</span><span class="sxs-lookup"><span data-stu-id="fca60-112">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="fca60-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="fca60-113">Use this</span></span>|<span data-ttu-id="fca60-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="fca60-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fca60-115">**项目类型**</span><span class="sxs-lookup"><span data-stu-id="fca60-115">**Project types**</span></span>|<span data-ttu-id="fca60-116">单击 **Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="fca60-116">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="fca60-117">**模板**</span><span class="sxs-lookup"><span data-stu-id="fca60-117">**Templates**</span></span>|<span data-ttu-id="fca60-118">单击 **控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="fca60-118">Click **Console Application**.</span></span>|  
    |<span data-ttu-id="fca60-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="fca60-119">**Name**</span></span>|<span data-ttu-id="fca60-120">类型**ConsumeEchoAdapter_Outbound**。</span><span class="sxs-lookup"><span data-stu-id="fca60-120">Type **ConsumeEchoAdapter_Outbound**.</span></span>|  
    |<span data-ttu-id="fca60-121">**位置**</span><span class="sxs-lookup"><span data-stu-id="fca60-121">**Location**</span></span>|<span data-ttu-id="fca60-122">类型**C:\Tutorials**。</span><span class="sxs-lookup"><span data-stu-id="fca60-122">Type **C:\Tutorials**.</span></span>|  
    |<span data-ttu-id="fca60-123">**解决方案名称**</span><span class="sxs-lookup"><span data-stu-id="fca60-123">**Solution Name**</span></span>|<span data-ttu-id="fca60-124">类型**ConsumeEchoAdapter_Outbound**。</span><span class="sxs-lookup"><span data-stu-id="fca60-124">Type **ConsumeEchoAdapter_Outbound**.</span></span>|  
  
4.  <span data-ttu-id="fca60-125">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="fca60-125">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="fca60-126">在 Visual Studio 中，在**文件**菜单上，单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="fca60-126">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="browse-search-and-generate-the-wcf-client"></a><span data-ttu-id="fca60-127">浏览、 搜索和生成 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="fca60-127">Browse, search, and generate the WCF client</span></span>  
  
1.  <span data-ttu-id="fca60-128">在 Visual Studio 解决方案窗格中，右键单击**ConsumeEchoAdapter_Outbound**项目，然后选择**添加适配器服务引用**以启动添加适配器服务引用插件。</span><span class="sxs-lookup"><span data-stu-id="fca60-128">In the Visual Studio Solution pane, right-click **ConsumeEchoAdapter_Outbound** project, then choose **Add Adapter Service Reference** to launch the Add Adapter Service Reference plug-in.</span></span>  
  
2.  <span data-ttu-id="fca60-129">在**添加适配器服务引用**屏幕上，选择一个绑定。</span><span class="sxs-lookup"><span data-stu-id="fca60-129">In the **Add Adapter Service Reference** screen, choose a binding.</span></span> <span data-ttu-id="fca60-130">这可通过选择**echoAdapterBindingV2**。</span><span class="sxs-lookup"><span data-stu-id="fca60-130">This is done by choosing **echoAdapterBindingV2**.</span></span>  
  
3.  <span data-ttu-id="fca60-131">接下来，通过单击配置的适配器和连接属性**配置...**.</span><span class="sxs-lookup"><span data-stu-id="fca60-131">Next, configure the adapter and connection properties by clicking **Configure…**.</span></span>  <span data-ttu-id="fca60-132">此时会弹出**配置适配器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="fca60-132">This will bring up the **Configure Adapter** screen.</span></span>  
  
4.  <span data-ttu-id="fca60-133">在**配置适配器**屏幕上，选择**URI 属性**选项卡来配置连接属性。</span><span class="sxs-lookup"><span data-stu-id="fca60-133">In the **Configure Adapter** screen, select the **URI Properties** tab to configure connection properties.</span></span> <span data-ttu-id="fca60-134">请注意，显示了自定义的 Echo 适配器类别-**连接**和**格式**。</span><span class="sxs-lookup"><span data-stu-id="fca60-134">Notice that the custom Echo Adapter categories are shown — **Connection** and **Format**.</span></span> <span data-ttu-id="fca60-135">下**格式**类别中，更改**EchoInUpperCase**到**True**。</span><span class="sxs-lookup"><span data-stu-id="fca60-135">Under the **Format** category, change **EchoInUpperCase** to **True**.</span></span>  
  
5.  <span data-ttu-id="fca60-136">在**配置适配器**屏幕上，选择**绑定属性**选项卡来配置适配器属性。</span><span class="sxs-lookup"><span data-stu-id="fca60-136">In the **Configure Adapter** screen, select the **Binding Properties** tab to configure the adapter properties.</span></span> <span data-ttu-id="fca60-137">请注意，自定义的 Echo 适配器类别**入站**和**杂项**显示。</span><span class="sxs-lookup"><span data-stu-id="fca60-137">Notice that the custom Echo Adapter categories **Inbound** and **Misc** are shown.</span></span> <span data-ttu-id="fca60-138">下**杂项**类别中，更改**计数**到**3**。</span><span class="sxs-lookup"><span data-stu-id="fca60-138">Under the **Misc** category, change **Count** to **3**.</span></span>  
  
6.  <span data-ttu-id="fca60-139">单击**确定**关闭**配置适配器**屏幕并返回到**添加适配器服务引用**屏幕。</span><span class="sxs-lookup"><span data-stu-id="fca60-139">Click **OK** to close the **Configure Adapter** screen and return to the **Add Adapter Service Reference** screen.</span></span>  
  
7.  <span data-ttu-id="fca60-140">接下来，单击**连接**连接到 Echo 适配器 （及假设它支持的业务线系统）。</span><span class="sxs-lookup"><span data-stu-id="fca60-140">Next, click **Connect** to connect to the Echo Adapter (and hypothetical line-of-business system it supports).</span></span> <span data-ttu-id="fca60-141">几分钟后的连接状态应更改为**已连接**和类别树 (下**选择类别**) 应进行填充。</span><span class="sxs-lookup"><span data-stu-id="fca60-141">After a few moments, the connection status should change to **Connected** and the Category Tree (under **Select a category**) should be populated.</span></span>  
  
8.  <span data-ttu-id="fca60-142">在类别树中，单击**Main 类别**。</span><span class="sxs-lookup"><span data-stu-id="fca60-142">In the Category Tree, click **Main Category**.</span></span> <span data-ttu-id="fca60-143">这将填充可用类别和与三个出站操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="fca60-143">This will populate the list of available categories and operations with three outbound operations.</span></span> <span data-ttu-id="fca60-144">不将任何类别。</span><span class="sxs-lookup"><span data-stu-id="fca60-144">There will be no categories.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fca60-145">默认协定类型为出站。</span><span class="sxs-lookup"><span data-stu-id="fca60-145">The default contract type is Outbound.</span></span> <span data-ttu-id="fca60-146">类别结果将与此协定类型匹配。</span><span class="sxs-lookup"><span data-stu-id="fca60-146">Category results will match this contract type.</span></span>  
  
9. <span data-ttu-id="fca60-147">在**可用类别和操作**，选择所有三个操作。</span><span class="sxs-lookup"><span data-stu-id="fca60-147">In the **Available Categories and Operations**, select all three operations.</span></span> <span data-ttu-id="fca60-148">当存在大量的操作时，你可能使用搜索来缩小选择;在这种情况下，有仅三个。</span><span class="sxs-lookup"><span data-stu-id="fca60-148">When there are a large number of operations, you might use search to narrow down the selection; in this case, there are only three.</span></span> <span data-ttu-id="fca60-149">单击**添加**以使生成的 WCF 接口的所选的操作部分。</span><span class="sxs-lookup"><span data-stu-id="fca60-149">Click **Add** to make the selected operations part of the generated WCF interface.</span></span>  
  
10. <span data-ttu-id="fca60-150">单击**确定**生成 WCF 接口。</span><span class="sxs-lookup"><span data-stu-id="fca60-150">Click **OK** to generate the WCF interface.</span></span> <span data-ttu-id="fca60-151">这将添加到项目的应用程序配置文件 (app.config) 和 WCF 客户端代理 (EchoAdapterBindingClient.cs)。</span><span class="sxs-lookup"><span data-stu-id="fca60-151">This will add an application configuration file (app.config) and a WCF client proxy (EchoAdapterBindingClient.cs) to the project.</span></span>  
  
11. <span data-ttu-id="fca60-152">单击**文件**Visual Studio 菜单上，选择**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="fca60-152">Click **File** on the Visual Studio menu and choose **Save All**.</span></span>  
  
## <a name="configure-adapter-authentication"></a><span data-ttu-id="fca60-153">配置适配器身份验证</span><span class="sxs-lookup"><span data-stu-id="fca60-153">Configure adapter authentication</span></span>  
  
1.  <span data-ttu-id="fca60-154">在 Visual Studio 解决方案窗格中，双击**app.config**。</span><span class="sxs-lookup"><span data-stu-id="fca60-154">In Visual Studio Solution pane, double-click **app.config**.</span></span>  
  
2.  <span data-ttu-id="fca60-155">查找`address`属性中`endpoint`元素。</span><span class="sxs-lookup"><span data-stu-id="fca60-155">Find the `address` attribute in the `endpoint` element.</span></span> <span data-ttu-id="fca60-156">该属性应与下面类似：</span><span class="sxs-lookup"><span data-stu-id="fca60-156">It should look similar to the following:</span></span>  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=False&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
     <span data-ttu-id="fca60-157">更改**enableAuthentication**从**False**到**True**如下所示。</span><span class="sxs-lookup"><span data-stu-id="fca60-157">Change **enableAuthentication** from **False** to **True** as shown below.</span></span> <span data-ttu-id="fca60-158">这将需要调用应用程序中，可以将凭据传递给适配器。</span><span class="sxs-lookup"><span data-stu-id="fca60-158">This will require the calling application to pass credentials to the adapter.</span></span>  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=True&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
3.  <span data-ttu-id="fca60-159">通过单击保存解决方案**文件**在 Visual Studio 菜单，选择**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="fca60-159">Save the solution by clicking **File** on the Visual Studio menu and choosing **Save All**.</span></span>  
  
## <a name="create-a-sample-xml-file"></a><span data-ttu-id="fca60-160">创建示例 XML 文件</span><span class="sxs-lookup"><span data-stu-id="fca60-160">Create a sample XML file</span></span>  
  
1.  <span data-ttu-id="fca60-161">启动记事本实例。</span><span class="sxs-lookup"><span data-stu-id="fca60-161">Start an instance of Notepad.</span></span> <span data-ttu-id="fca60-162">使用开始菜单中，单击**所有程序** &#124; **附件**，然后选择**记事本**。</span><span class="sxs-lookup"><span data-stu-id="fca60-162">Using the Start menu, click **All Programs** &#124; **Accessories** and then choose **Notepad**.</span></span>  
  
2.  <span data-ttu-id="fca60-163">将下面的示例数据复制到记事本编辑器。</span><span class="sxs-lookup"><span data-stu-id="fca60-163">Copy the following sample data into the Notepad editor.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <ns0:greeting xmlns:ns0="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes">  
      <ns0:address>  
        <ns0:street1>123 Microsoft Way</ns0:street1>  
        <ns0:street2>Building # 4599</ns0:street2>  
        <ns0:city>Redmond</ns0:city>  
        <ns0:state>WA</ns0:state>  
        <ns0:zip>98052</ns0:zip>  
      </ns0:address>  
      <ns0:greetingText>Welcome to Redmond!</ns0:greetingText>  
    </ns0:greeting>              
    ```  
  
3.  <span data-ttu-id="fca60-164">在记事本菜单上，单击**文件**，然后选择**另存为...**.</span><span class="sxs-lookup"><span data-stu-id="fca60-164">On the Notepad menu, click **File** and then choose **Save As…**.</span></span> <span data-ttu-id="fca60-165">在"CustomGreetingInstance.xml"中键入的文件名称和选择的编码的 Unicode 和将其保存到项目目录中或另一个合适的位置。</span><span class="sxs-lookup"><span data-stu-id="fca60-165">Type in "CustomGreetingInstance.xml" for the file name and choose Unicode for the encoding and then save it to the project directory or another suitable location.</span></span> <span data-ttu-id="fca60-166">请注意的完整路径和文件名以供稍后参考。</span><span class="sxs-lookup"><span data-stu-id="fca60-166">Note the full path and filename for later reference.</span></span>  
  
4.  <span data-ttu-id="fca60-167">已成功保存该文件，请关闭文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="fca60-167">Close the text editor when the file is successfully saved.</span></span>  
  
## <a name="test-the-echo-adapter"></a><span data-ttu-id="fca60-168">测试 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="fca60-168">Test the Echo Adapter</span></span>  
  
1.  <span data-ttu-id="fca60-169">在解决方案资源管理器中，双击**Program.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="fca60-169">In Solution Explorer, double-click the **Program.cs** file.</span></span>  
  
2.  <span data-ttu-id="fca60-170">在 Visual Studio 编辑器中，内部**Main**方法，添加以下代码行以创建生成的 WCF 客户端的实例。</span><span class="sxs-lookup"><span data-stu-id="fca60-170">In the Visual Studio editor, inside the **Main** method, add the following line of code to create an instance of the generated WCF client.</span></span>  
  
    ```csharp  
    EchoOutboundContractClient client = new EchoOutboundContractClient();  
    ```  
  
3.  <span data-ttu-id="fca60-171">现在添加建立为适配器的凭据的代码。</span><span class="sxs-lookup"><span data-stu-id="fca60-171">Now add code that establishes credentials for the adapter.</span></span> <span data-ttu-id="fca60-172">Echo 适配器中启用身份验证时，它将检查用户名存在的连接，但不是会检查值。</span><span class="sxs-lookup"><span data-stu-id="fca60-172">When authentication is enabled in the Echo Adapter, it will check for the existence of a user name but will not check the value.</span></span>  
  
    ```csharp  
    // pass client credentials  
    client.ClientCredentials.UserName.UserName = "username";  
    ```  
  
4.  <span data-ttu-id="fca60-173">通过添加代码以调用 EchoStrings 操作继续进行。</span><span class="sxs-lookup"><span data-stu-id="fca60-173">Continue by adding code to invoke the EchoStrings operation.</span></span>  
  
    ```csharp  
    // Invoke EchoStrings()  
    Console.WriteLine("Invoking EchoStrings() method against the adapter...");  
    string[] response = client.EchoStrings("Bonjour!");  
    foreach (string data in response)  
    {  
        Console.WriteLine(data);  
    }  
    ```  
  
5.  <span data-ttu-id="fca60-174">通过添加代码以调用 EchoGreetings 操作继续进行。</span><span class="sxs-lookup"><span data-stu-id="fca60-174">Continue by adding code to invoke the EchoGreetings operation.</span></span>  
  
    ```csharp  
    // Invoke EchoGreetings()  
    Console.WriteLine("\nInvoking EchoGreetings() method against the adapter...");  
    microsoft.adapters.samples.echov2.Types.Greeting greeting = new microsoft.adapters.samples.echov2.Types.Greeting();  
    greeting.id = Guid.NewGuid();  
    greeting.sentDateTime = DateTime.Now;  
    greeting.greetingText = "Hello World!";  
    greeting.name = new microsoft.adapters.samples.echov2.Types.Name();  
    greeting.name.salutation = microsoft.adapters.samples.echov2.Types.Salutation.Miss;  
    greeting.name.firstName = "Jane";  
    greeting.name.middleName = "Z.";  
    greeting.name.lastName = "Smith";  
    microsoft.adapters.samples.echov2.Types.Greeting[] greetingArray = client.EchoGreetings(greeting);  
    foreach (microsoft.adapters.samples.echov2.Types.Greeting data in greetingArray)  
    {  
        Console.WriteLine(data.id + " " + data.sentDateTime + " " + data.greetingText + " " + data.name.firstName );  
    }  
    ```  
  
6.  <span data-ttu-id="fca60-175">通过添加代码以调用 EchoCustomGreetingsFromFile 操作继续进行。</span><span class="sxs-lookup"><span data-stu-id="fca60-175">Continue by adding code to invoke the EchoCustomGreetingsFromFile operation.</span></span>  
  
    ```csharp  
    // Invoke EchoCustomGreetingFromFile()  
    Console.WriteLine("\nInvoking EchoCustomGreetingFromFile() method against the adapter ...");  
    // Copy the sample data from CustomGreeting-instance.xml file and place in appropriate folder  
    // as specified in the operation parameter  
    microsoft.adapters.samples.echov2.PreDefinedTypes.CustomGreeting   
    // change the Uri to point to the greeting instance xml file you created  
    customGreeting = client.EchoCustomGreetingFromFile(new Uri(@"c:\CustomGreetingInstance.xml"));  
    Console.WriteLine(customGreeting.greetingText + " " + customGreeting.address.city);  
    client.Close();  
    Console.ReadLine();  
    ```  
  
7.  <span data-ttu-id="fca60-176">在 EchoCustomGreetingsFromFile 测试代码中，请确保自定义问候语使用你在前一过程中创建的文件。</span><span class="sxs-lookup"><span data-stu-id="fca60-176">In the EchoCustomGreetingsFromFile test code, make sure the custom greeting uses the file you created in a previous procedure.</span></span> <span data-ttu-id="fca60-177">更改代码以反映你的文件的位置。</span><span class="sxs-lookup"><span data-stu-id="fca60-177">Change the code to reflect the location of your file.</span></span>  
  
8.  <span data-ttu-id="fca60-178">在 Visual Studio 中，在**文件**菜单上，单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="fca60-178">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
9. <span data-ttu-id="fca60-179">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="fca60-179">Run the application.</span></span> <span data-ttu-id="fca60-180">你应看到类似于下面的输出：</span><span class="sxs-lookup"><span data-stu-id="fca60-180">You should see output similar to the following:</span></span>  
  
     <span data-ttu-id="fca60-181">**对适配器调用 EchoStrings() 方法...**</span><span class="sxs-lookup"><span data-stu-id="fca60-181">**Invoking EchoStrings() method against the adapter...**</span></span>  
  
     <span data-ttu-id="fca60-182">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="fca60-182">**Bonjour!**</span></span>  
  
     <span data-ttu-id="fca60-183">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="fca60-183">**Bonjour!**</span></span>  
  
     <span data-ttu-id="fca60-184">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="fca60-184">**Bonjour!**</span></span>  
  
     <span data-ttu-id="fca60-185">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="fca60-185">**Bonjour!**</span></span>  
  
     <span data-ttu-id="fca60-186">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="fca60-186">**Bonjour!**</span></span>  
  
     <span data-ttu-id="fca60-187">**对适配器调用 EchoGreetings() 方法...**</span><span class="sxs-lookup"><span data-stu-id="fca60-187">**Invoking EchoGreetings() method against the adapter...**</span></span>  
  
     <span data-ttu-id="fca60-188">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**</span><span class="sxs-lookup"><span data-stu-id="fca60-188">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="fca60-189">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**</span><span class="sxs-lookup"><span data-stu-id="fca60-189">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="fca60-190">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**</span><span class="sxs-lookup"><span data-stu-id="fca60-190">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="fca60-191">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**</span><span class="sxs-lookup"><span data-stu-id="fca60-191">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="fca60-192">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**</span><span class="sxs-lookup"><span data-stu-id="fca60-192">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="fca60-193">**对适配器调用 EchoCustomGreetingFromFile() 方法...**</span><span class="sxs-lookup"><span data-stu-id="fca60-193">**Invoking EchoCustomGreetingFromFile() method against the adapter ...**</span></span>  
  
     <span data-ttu-id="fca60-194">**欢迎使用 Redmond ！Redmond**</span><span class="sxs-lookup"><span data-stu-id="fca60-194">**Welcome to Redmond! Redmond**</span></span>  
  
10. <span data-ttu-id="fca60-195">按 Enter 键停止节目。</span><span class="sxs-lookup"><span data-stu-id="fca60-195">Press the Enter key to stop the program.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="fca60-196">未我只需做什么？</span><span class="sxs-lookup"><span data-stu-id="fca60-196">What Did I Just Do?</span></span>  
 <span data-ttu-id="fca60-197">在此步骤中，你创建的测试应用程序开发在教程 1 中的 Echo 适配器公开的三个出站操作。</span><span class="sxs-lookup"><span data-stu-id="fca60-197">In this step, you created a test application for the three outbound operations exposed by the Echo Adapter developed in Tutorial 1.</span></span> <span data-ttu-id="fca60-198">为此，你创建了 Visual Studio 项目，生成 WCF 服务，并提供代码以承载 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="fca60-198">To do this, you created a Visual Studio project, generated a WCF Service, and provided code to host the WCF Service.</span></span> <span data-ttu-id="fca60-199">最后，您运行测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="fca60-199">Finally, you ran the test application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fca60-200">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fca60-200">Next Steps</span></span>  
 <span data-ttu-id="fca60-201">若要测试的入站的操作，请继续执行到[步骤 2： 测试入站处理程序回显适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fca60-201">To test the Inbound operation, proceed to [Step 2: Test Inbound Handler of the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fca60-202">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fca60-202">See Also</span></span>  
  <span data-ttu-id="fca60-203">[教程 2： 使用.NET Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span><span class="sxs-lookup"><span data-stu-id="fca60-203">[Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span></span>  
 [<span data-ttu-id="fca60-204">步骤 2：测试 Echo 适配器的入站处理程序</span><span class="sxs-lookup"><span data-stu-id="fca60-204">Step 2: Test Inbound Handler of the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)