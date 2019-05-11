---
title: 第 1 步：测试 Echo 适配器的出站处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4a8164-a584-436f-b20b-4c884f6e2b37
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 597c4059cb2fc673a557a6e68c5d544db1700522
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363358"
---
# <a name="step-1-test-outbound-handler-of-the-echo-adapter"></a><span data-ttu-id="a545a-102">第 1 步：测试 Echo 适配器的出站处理程序</span><span class="sxs-lookup"><span data-stu-id="a545a-102">Step 1: Test Outbound Handler of the Echo Adapter</span></span>
<span data-ttu-id="a545a-103">![2 的第 1 步](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span><span class="sxs-lookup"><span data-stu-id="a545a-103">![Step 1 of 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span></span>  
  
 <span data-ttu-id="a545a-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="a545a-104">**Time to Complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="a545a-105">在此步骤中，您将测试 Echo 适配器提供的三个出站操作。</span><span class="sxs-lookup"><span data-stu-id="a545a-105">In this step, you will test the three outbound operations provided by the Echo Adapter.</span></span> <span data-ttu-id="a545a-106">您将执行此操作使用 Visual Studio 中，添加适配器服务参考 Visual Studio 插件和自定义代码。</span><span class="sxs-lookup"><span data-stu-id="a545a-106">You will do this using Visual Studio, the Add Adapter Service Reference Visual Studio Plug-In and custom code.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a545a-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="a545a-107">Prerequisites</span></span>  
 <span data-ttu-id="a545a-108">若要完成此步骤中，你必须完成[教程 1:开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a545a-108">To complete this step, you must have completed [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
## <a name="create-a-visual-studio-project"></a><span data-ttu-id="a545a-109">创建 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="a545a-109">Create a Visual Studio project</span></span>  
  
1.  <span data-ttu-id="a545a-110">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="a545a-110">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a545a-111">在 Visual Studio 中，在**文件**菜单，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="a545a-111">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="a545a-112">在中**新的项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a545a-112">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a545a-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a545a-113">Use this</span></span>|<span data-ttu-id="a545a-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a545a-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a545a-115">**项目类型**</span><span class="sxs-lookup"><span data-stu-id="a545a-115">**Project types**</span></span>|<span data-ttu-id="a545a-116">单击**Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="a545a-116">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="a545a-117">**模板**</span><span class="sxs-lookup"><span data-stu-id="a545a-117">**Templates**</span></span>|<span data-ttu-id="a545a-118">单击**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a545a-118">Click **Console Application**.</span></span>|  
    |<span data-ttu-id="a545a-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="a545a-119">**Name**</span></span>|<span data-ttu-id="a545a-120">类型**ConsumeEchoAdapter_Outbound**。</span><span class="sxs-lookup"><span data-stu-id="a545a-120">Type **ConsumeEchoAdapter_Outbound**.</span></span>|  
    |<span data-ttu-id="a545a-121">**位置**</span><span class="sxs-lookup"><span data-stu-id="a545a-121">**Location**</span></span>|<span data-ttu-id="a545a-122">类型**C:\Tutorials**。</span><span class="sxs-lookup"><span data-stu-id="a545a-122">Type **C:\Tutorials**.</span></span>|  
    |<span data-ttu-id="a545a-123">**解决方案名称**</span><span class="sxs-lookup"><span data-stu-id="a545a-123">**Solution Name**</span></span>|<span data-ttu-id="a545a-124">类型**ConsumeEchoAdapter_Outbound**。</span><span class="sxs-lookup"><span data-stu-id="a545a-124">Type **ConsumeEchoAdapter_Outbound**.</span></span>|  
  
4.  <span data-ttu-id="a545a-125">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="a545a-125">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a545a-126">在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="a545a-126">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="browse-search-and-generate-the-wcf-client"></a><span data-ttu-id="a545a-127">浏览、 搜索和生成 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="a545a-127">Browse, search, and generate the WCF client</span></span>  
  
1.  <span data-ttu-id="a545a-128">在 Visual Studio 解决方案窗格中，右键单击**ConsumeEchoAdapter_Outbound**项目，然后选择**添加适配器服务引用**以启动添加适配器服务引用插件。</span><span class="sxs-lookup"><span data-stu-id="a545a-128">In the Visual Studio Solution pane, right-click **ConsumeEchoAdapter_Outbound** project, then choose **Add Adapter Service Reference** to launch the Add Adapter Service Reference plug-in.</span></span>  
  
2.  <span data-ttu-id="a545a-129">在中**添加适配器服务引用**屏幕上，选择一个绑定。</span><span class="sxs-lookup"><span data-stu-id="a545a-129">In the **Add Adapter Service Reference** screen, choose a binding.</span></span> <span data-ttu-id="a545a-130">这可通过选择**echoAdapterBindingV2**。</span><span class="sxs-lookup"><span data-stu-id="a545a-130">This is done by choosing **echoAdapterBindingV2**.</span></span>  
  
3.  <span data-ttu-id="a545a-131">接下来，通过单击配置的适配器和 connection 属性**配置...**.</span><span class="sxs-lookup"><span data-stu-id="a545a-131">Next, configure the adapter and connection properties by clicking **Configure…**.</span></span>  <span data-ttu-id="a545a-132">此时会弹出**配置适配器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="a545a-132">This will bring up the **Configure Adapter** screen.</span></span>  
  
4.  <span data-ttu-id="a545a-133">在中**配置适配器**屏幕上，选择**URI 属性**选项卡可配置连接属性。</span><span class="sxs-lookup"><span data-stu-id="a545a-133">In the **Configure Adapter** screen, select the **URI Properties** tab to configure connection properties.</span></span> <span data-ttu-id="a545a-134">请注意，自定义 Echo 适配器类别显示 —**连接**并**格式**。</span><span class="sxs-lookup"><span data-stu-id="a545a-134">Notice that the custom Echo Adapter categories are shown — **Connection** and **Format**.</span></span> <span data-ttu-id="a545a-135">下**格式**类别中，更改**EchoInUpperCase**到**True**。</span><span class="sxs-lookup"><span data-stu-id="a545a-135">Under the **Format** category, change **EchoInUpperCase** to **True**.</span></span>  
  
5.  <span data-ttu-id="a545a-136">在中**配置适配器**屏幕上，选择**绑定属性**选项卡以配置适配器属性。</span><span class="sxs-lookup"><span data-stu-id="a545a-136">In the **Configure Adapter** screen, select the **Binding Properties** tab to configure the adapter properties.</span></span> <span data-ttu-id="a545a-137">请注意，自定义 Echo 适配器类别**入站**并**杂项**显示。</span><span class="sxs-lookup"><span data-stu-id="a545a-137">Notice that the custom Echo Adapter categories **Inbound** and **Misc** are shown.</span></span> <span data-ttu-id="a545a-138">下**杂项**类别中，更改**计数**到**3**。</span><span class="sxs-lookup"><span data-stu-id="a545a-138">Under the **Misc** category, change **Count** to **3**.</span></span>  
  
6.  <span data-ttu-id="a545a-139">单击**确定**以关闭**配置适配器**屏幕上，并返回到**添加适配器服务引用**屏幕。</span><span class="sxs-lookup"><span data-stu-id="a545a-139">Click **OK** to close the **Configure Adapter** screen and return to the **Add Adapter Service Reference** screen.</span></span>  
  
7.  <span data-ttu-id="a545a-140">接下来，单击**Connect**连接到 Echo 适配器 （和假设它支持的业务线系统）。</span><span class="sxs-lookup"><span data-stu-id="a545a-140">Next, click **Connect** to connect to the Echo Adapter (and hypothetical line-of-business system it supports).</span></span> <span data-ttu-id="a545a-141">几分钟后，连接状态应更改为**已连接**和类别树 (下**选择一个类别**) 应填充。</span><span class="sxs-lookup"><span data-stu-id="a545a-141">After a few moments, the connection status should change to **Connected** and the Category Tree (under **Select a category**) should be populated.</span></span>  
  
8.  <span data-ttu-id="a545a-142">在类别树中，单击**主类别**。</span><span class="sxs-lookup"><span data-stu-id="a545a-142">In the Category Tree, click **Main Category**.</span></span> <span data-ttu-id="a545a-143">这将填充可用类别和包含三个出站操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="a545a-143">This will populate the list of available categories and operations with three outbound operations.</span></span> <span data-ttu-id="a545a-144">将没有类别。</span><span class="sxs-lookup"><span data-stu-id="a545a-144">There will be no categories.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a545a-145">默认协定类型为出站。</span><span class="sxs-lookup"><span data-stu-id="a545a-145">The default contract type is Outbound.</span></span> <span data-ttu-id="a545a-146">类别结果将与此协定类型匹配。</span><span class="sxs-lookup"><span data-stu-id="a545a-146">Category results will match this contract type.</span></span>  
  
9. <span data-ttu-id="a545a-147">在中**可用类别和操作**，选择所有三个操作。</span><span class="sxs-lookup"><span data-stu-id="a545a-147">In the **Available Categories and Operations**, select all three operations.</span></span> <span data-ttu-id="a545a-148">当存在大量的操作时，你可能会使用搜索来缩小选择范围;在这种情况下，有只有三个。</span><span class="sxs-lookup"><span data-stu-id="a545a-148">When there are a large number of operations, you might use search to narrow down the selection; in this case, there are only three.</span></span> <span data-ttu-id="a545a-149">单击**添加**以使生成的 WCF 接口的所选的操作部分。</span><span class="sxs-lookup"><span data-stu-id="a545a-149">Click **Add** to make the selected operations part of the generated WCF interface.</span></span>  
  
10. <span data-ttu-id="a545a-150">单击**确定**生成 WCF 接口。</span><span class="sxs-lookup"><span data-stu-id="a545a-150">Click **OK** to generate the WCF interface.</span></span> <span data-ttu-id="a545a-151">这将添加到项目的应用程序配置文件 (app.config) 和 WCF 客户端代理 (EchoAdapterBindingClient.cs)。</span><span class="sxs-lookup"><span data-stu-id="a545a-151">This will add an application configuration file (app.config) and a WCF client proxy (EchoAdapterBindingClient.cs) to the project.</span></span>  
  
11. <span data-ttu-id="a545a-152">单击**文件**Visual Studio 菜单上，然后选择**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="a545a-152">Click **File** on the Visual Studio menu and choose **Save All**.</span></span>  
  
## <a name="configure-adapter-authentication"></a><span data-ttu-id="a545a-153">配置适配器身份验证</span><span class="sxs-lookup"><span data-stu-id="a545a-153">Configure adapter authentication</span></span>  
  
1.  <span data-ttu-id="a545a-154">在 Visual Studio 解决方案窗格中，双击**app.config**。</span><span class="sxs-lookup"><span data-stu-id="a545a-154">In Visual Studio Solution pane, double-click **app.config**.</span></span>  
  
2.  <span data-ttu-id="a545a-155">查找`address`属性中`endpoint`元素。</span><span class="sxs-lookup"><span data-stu-id="a545a-155">Find the `address` attribute in the `endpoint` element.</span></span> <span data-ttu-id="a545a-156">该属性应与下面类似：</span><span class="sxs-lookup"><span data-stu-id="a545a-156">It should look similar to the following:</span></span>  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=False&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
     <span data-ttu-id="a545a-157">更改**enableAuthentication**从**False**到**True** ，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a545a-157">Change **enableAuthentication** from **False** to **True** as shown below.</span></span> <span data-ttu-id="a545a-158">这将需要调用应用程序中，若要将凭据传递给适配器。</span><span class="sxs-lookup"><span data-stu-id="a545a-158">This will require the calling application to pass credentials to the adapter.</span></span>  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=True&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
3.  <span data-ttu-id="a545a-159">通过单击保存解决方案**文件**Visual studio 菜单，然后选择**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="a545a-159">Save the solution by clicking **File** on the Visual Studio menu and choosing **Save All**.</span></span>  
  
## <a name="create-a-sample-xml-file"></a><span data-ttu-id="a545a-160">创建示例 XML 文件</span><span class="sxs-lookup"><span data-stu-id="a545a-160">Create a sample XML file</span></span>  
  
1.  <span data-ttu-id="a545a-161">启动记事本的实例。</span><span class="sxs-lookup"><span data-stu-id="a545a-161">Start an instance of Notepad.</span></span> <span data-ttu-id="a545a-162">使用开始菜单中，单击**所有程序** &#124; **附件**，然后选择**记事本**。</span><span class="sxs-lookup"><span data-stu-id="a545a-162">Using the Start menu, click **All Programs** &#124; **Accessories** and then choose **Notepad**.</span></span>  
  
2.  <span data-ttu-id="a545a-163">将下面的示例数据复制到记事本编辑器。</span><span class="sxs-lookup"><span data-stu-id="a545a-163">Copy the following sample data into the Notepad editor.</span></span>  
  
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
  
3.  <span data-ttu-id="a545a-164">在记事本菜单上，单击**文件**，然后选择**另存为...**.</span><span class="sxs-lookup"><span data-stu-id="a545a-164">On the Notepad menu, click **File** and then choose **Save As…**.</span></span> <span data-ttu-id="a545a-165">"CustomGreetingInstance.xml"中键入文件名称并选择 Unicode 的编码和将其保存到项目目录中或另一个合适的位置。</span><span class="sxs-lookup"><span data-stu-id="a545a-165">Type in "CustomGreetingInstance.xml" for the file name and choose Unicode for the encoding and then save it to the project directory or another suitable location.</span></span> <span data-ttu-id="a545a-166">请注意的完整路径和文件名以供日后参考。</span><span class="sxs-lookup"><span data-stu-id="a545a-166">Note the full path and filename for later reference.</span></span>  
  
4.  <span data-ttu-id="a545a-167">已成功保存文件时，请关闭文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="a545a-167">Close the text editor when the file is successfully saved.</span></span>  
  
## <a name="test-the-echo-adapter"></a><span data-ttu-id="a545a-168">测试 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="a545a-168">Test the Echo Adapter</span></span>  
  
1.  <span data-ttu-id="a545a-169">在解决方案资源管理器中双击**Program.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="a545a-169">In Solution Explorer, double-click the **Program.cs** file.</span></span>  
  
2.  <span data-ttu-id="a545a-170">在 Visual Studio 编辑器中，内部**Main**方法中，添加以下行的代码以创建生成的 WCF 客户端的实例。</span><span class="sxs-lookup"><span data-stu-id="a545a-170">In the Visual Studio editor, inside the **Main** method, add the following line of code to create an instance of the generated WCF client.</span></span>  
  
    ```csharp  
    EchoOutboundContractClient client = new EchoOutboundContractClient();  
    ```  
  
3.  <span data-ttu-id="a545a-171">现在添加建立的适配器的凭据的代码。</span><span class="sxs-lookup"><span data-stu-id="a545a-171">Now add code that establishes credentials for the adapter.</span></span> <span data-ttu-id="a545a-172">Echo 适配器中启用身份验证，它将检查存在的用户名称，但不是会检查值。</span><span class="sxs-lookup"><span data-stu-id="a545a-172">When authentication is enabled in the Echo Adapter, it will check for the existence of a user name but will not check the value.</span></span>  
  
    ```csharp  
    // pass client credentials  
    client.ClientCredentials.UserName.UserName = "username";  
    ```  
  
4.  <span data-ttu-id="a545a-173">继续通过添加代码以调用 EchoStrings 操作。</span><span class="sxs-lookup"><span data-stu-id="a545a-173">Continue by adding code to invoke the EchoStrings operation.</span></span>  
  
    ```csharp  
    // Invoke EchoStrings()  
    Console.WriteLine("Invoking EchoStrings() method against the adapter...");  
    string[] response = client.EchoStrings("Bonjour!");  
    foreach (string data in response)  
    {  
        Console.WriteLine(data);  
    }  
    ```  
  
5.  <span data-ttu-id="a545a-174">继续通过添加代码以调用 EchoGreetings 操作。</span><span class="sxs-lookup"><span data-stu-id="a545a-174">Continue by adding code to invoke the EchoGreetings operation.</span></span>  
  
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
  
6.  <span data-ttu-id="a545a-175">继续通过添加代码以调用 EchoCustomGreetingsFromFile 操作。</span><span class="sxs-lookup"><span data-stu-id="a545a-175">Continue by adding code to invoke the EchoCustomGreetingsFromFile operation.</span></span>  
  
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
  
7.  <span data-ttu-id="a545a-176">EchoCustomGreetingsFromFile 中测试代码中，请确保自定义问候语使用上一个过程中创建的文件。</span><span class="sxs-lookup"><span data-stu-id="a545a-176">In the EchoCustomGreetingsFromFile test code, make sure the custom greeting uses the file you created in a previous procedure.</span></span> <span data-ttu-id="a545a-177">更改代码以反映你的文件的位置。</span><span class="sxs-lookup"><span data-stu-id="a545a-177">Change the code to reflect the location of your file.</span></span>  
  
8.  <span data-ttu-id="a545a-178">在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="a545a-178">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
9. <span data-ttu-id="a545a-179">运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a545a-179">Run the application.</span></span> <span data-ttu-id="a545a-180">应看到类似于以下输出：</span><span class="sxs-lookup"><span data-stu-id="a545a-180">You should see output similar to the following:</span></span>  
  
     <span data-ttu-id="a545a-181">**调用根据适配器 EchoStrings() 方法...**</span><span class="sxs-lookup"><span data-stu-id="a545a-181">**Invoking EchoStrings() method against the adapter...**</span></span>  
  
     <span data-ttu-id="a545a-182">**Bonjour ！**</span><span class="sxs-lookup"><span data-stu-id="a545a-182">**Bonjour!**</span></span>  
  
     <span data-ttu-id="a545a-183">**Bonjour ！**</span><span class="sxs-lookup"><span data-stu-id="a545a-183">**Bonjour!**</span></span>  
  
     <span data-ttu-id="a545a-184">**Bonjour ！**</span><span class="sxs-lookup"><span data-stu-id="a545a-184">**Bonjour!**</span></span>  
  
     <span data-ttu-id="a545a-185">**Bonjour ！**</span><span class="sxs-lookup"><span data-stu-id="a545a-185">**Bonjour!**</span></span>  
  
     <span data-ttu-id="a545a-186">**Bonjour ！**</span><span class="sxs-lookup"><span data-stu-id="a545a-186">**Bonjour!**</span></span>  
  
     <span data-ttu-id="a545a-187">**调用根据适配器 EchoGreetings() 方法...**</span><span class="sxs-lookup"><span data-stu-id="a545a-187">**Invoking EchoGreetings() method against the adapter...**</span></span>  
  
     <span data-ttu-id="a545a-188">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**</span><span class="sxs-lookup"><span data-stu-id="a545a-188">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="a545a-189">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**</span><span class="sxs-lookup"><span data-stu-id="a545a-189">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="a545a-190">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**</span><span class="sxs-lookup"><span data-stu-id="a545a-190">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="a545a-191">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**</span><span class="sxs-lookup"><span data-stu-id="a545a-191">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="a545a-192">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**</span><span class="sxs-lookup"><span data-stu-id="a545a-192">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="a545a-193">**调用根据适配器 EchoCustomGreetingFromFile() 方法...**</span><span class="sxs-lookup"><span data-stu-id="a545a-193">**Invoking EchoCustomGreetingFromFile() method against the adapter ...**</span></span>  
  
     <span data-ttu-id="a545a-194">**欢迎使用雷德蒙德 ！雷德蒙德**</span><span class="sxs-lookup"><span data-stu-id="a545a-194">**Welcome to Redmond! Redmond**</span></span>  
  
10. <span data-ttu-id="a545a-195">按 Enter 键以停止程序。</span><span class="sxs-lookup"><span data-stu-id="a545a-195">Press the Enter key to stop the program.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="a545a-196">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="a545a-196">What Did I Just Do?</span></span>  
 <span data-ttu-id="a545a-197">在此步骤中，您可以创建公开在教程 1 中开发 Echo 适配器的三个出站操作的测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="a545a-197">In this step, you created a test application for the three outbound operations exposed by the Echo Adapter developed in Tutorial 1.</span></span> <span data-ttu-id="a545a-198">若要执行此操作，创建了一个 Visual Studio 项目，生成 WCF 服务，，并提供代码以承载 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="a545a-198">To do this, you created a Visual Studio project, generated a WCF Service, and provided code to host the WCF Service.</span></span> <span data-ttu-id="a545a-199">最后，您运行了测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="a545a-199">Finally, you ran the test application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a545a-200">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a545a-200">Next Steps</span></span>  
 <span data-ttu-id="a545a-201">要测试入站的操作，请转到[步骤 2:测试 Echo 适配器的入站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a545a-201">To test the Inbound operation, proceed to [Step 2: Test Inbound Handler of the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a545a-202">请参阅</span><span class="sxs-lookup"><span data-stu-id="a545a-202">See Also</span></span>  
  <span data-ttu-id="a545a-203">[教程 2：使用通过.NET Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span><span class="sxs-lookup"><span data-stu-id="a545a-203">[Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span></span>  
 [<span data-ttu-id="a545a-204">步骤 2：测试 Echo 适配器的入站处理程序</span><span class="sxs-lookup"><span data-stu-id="a545a-204">Step 2: Test Inbound Handler of the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)