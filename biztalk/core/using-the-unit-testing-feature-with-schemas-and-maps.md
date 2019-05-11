---
title: 使用单元测试功能架构和映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29bcb159-ffdb-44b9-a3ff-565973d41797
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 576974b71b5f5312fdcea792458b86ea1590d42d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302829"
---
# <a name="using-the-unit-testing-feature-with-schemas-and-maps"></a><span data-ttu-id="8b275-102">使用单元测试功能架构和映射</span><span class="sxs-lookup"><span data-stu-id="8b275-102">Using the Unit Testing Feature with Schemas and Maps</span></span>
<span data-ttu-id="8b275-103">本主题演示如何使用单元测试功能在 HelloWorld 业务流程的示例中添加架构和映射的单元测试。</span><span class="sxs-lookup"><span data-stu-id="8b275-103">This topic demonstrates how to use the unit testing feature to add a unit test for the schemas and map in the HelloWorld orchestration example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b275-104">单元测试适用于映射的功能当前不支持多个输入的映射。</span><span class="sxs-lookup"><span data-stu-id="8b275-104">The unit testing feature for maps currently does not support multiple input maps.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8b275-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="8b275-105">Prerequisites</span></span>  
 <span data-ttu-id="8b275-106">您必须首先按照用于生成 HelloWorld 示例的步骤。</span><span class="sxs-lookup"><span data-stu-id="8b275-106">You must first follow the steps for building the HelloWorld sample.</span></span> <span data-ttu-id="8b275-107">这些步骤可在此处找到：[HelloWorld（BizTalk Server 示例）](../core/helloworld-biztalk-server-sample.md)</span><span class="sxs-lookup"><span data-stu-id="8b275-107">Those steps can be found here: [HelloWorld (BizTalk Server Sample)](../core/helloworld-biztalk-server-sample.md)</span></span>  
  
### <a name="adding-a-unit-test-project-to-the-helloworld-sample"></a><span data-ttu-id="8b275-108">将单元测试项目添加到 HelloWorld 示例</span><span class="sxs-lookup"><span data-stu-id="8b275-108">Adding a Unit Test Project to the HelloWorld Sample</span></span>  
  
1.  <span data-ttu-id="8b275-109">在 Visual Studio 中，打开 HelloWorld.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="8b275-109">In Visual Studio, open the HelloWorld.sln solution file.</span></span>  
  
2.  <span data-ttu-id="8b275-110">在解决方案资源管理器中右键单击**HelloWorld**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="8b275-110">In Solution Explorer, right-click the **HelloWorld** project, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="8b275-111">在项目设计器中，单击**部署**属性页选项卡和组**启用单元测试**到`True`。</span><span class="sxs-lookup"><span data-stu-id="8b275-111">In Project Designer, click the **Deployment** property page tab and set **Enable Unit Testing** to `True`.</span></span>  
  
4.  <span data-ttu-id="8b275-112">关闭项目属性页，保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8b275-112">Close the project properties page saving the changes.</span></span>  
  
5.  <span data-ttu-id="8b275-113">在主菜单中，单击**构建**，然后单击**重新生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="8b275-113">In main menu, click **Build**, and then click **Rebuild Solution**.</span></span>  
  
6.  <span data-ttu-id="8b275-114">在主菜单上，单击**测试**，然后单击**新测试**。</span><span class="sxs-lookup"><span data-stu-id="8b275-114">On the main menu, click **Test**, and then click **New Test**.</span></span>  
  
7.  <span data-ttu-id="8b275-115">在中**添加新测试**对话框中，选择**创建新的视觉对象C#测试项目**有关**将添加到测试项目**字段。</span><span class="sxs-lookup"><span data-stu-id="8b275-115">In the **Add New Test** dialog box, select **Create a new Visual C# test project** for **Add to Test Project** field.</span></span> <span data-ttu-id="8b275-116">选择**单元测试向导**中**模板**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b275-116">Select **Unit Test Wizard** in the **Templates** list, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8b275-117">在中**新的测试项目**对话框框中，将项目名称设置为**TestProject1**然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="8b275-117">In the **New Test Project** dialog box, leave the project name as **TestProject1** and click **Create**.</span></span>  
  
9. <span data-ttu-id="8b275-118">在中**创建单元测试**对话框中，展开类型并选择**POSchema()** 下的构造函数**Microsoft.Samples.BizTalk.HelloWorld.POSchema**节点。</span><span class="sxs-lookup"><span data-stu-id="8b275-118">In the **Create Unit Tests** dialog box, expand the types and select the **POSchema()** constructor under the **Microsoft.Samples.BizTalk.HelloWorld.POSchema** node.</span></span> <span data-ttu-id="8b275-119">此外选择**POToInvoice()** 构造函数下的**Microsoft.Samples.BizTalk.HelloWorld.POToInvoice**节点。</span><span class="sxs-lookup"><span data-stu-id="8b275-119">Also select **POToInvoice()** constructor under the **Microsoft.Samples.BizTalk.HelloWorld.POToInvoice** node.</span></span> <span data-ttu-id="8b275-120">下图显示了应做的选择。</span><span class="sxs-lookup"><span data-stu-id="8b275-120">The figure below shows the selections that should be made.</span></span> <span data-ttu-id="8b275-121">做出如下所示选择后，按**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b275-121">After making the selections shown below, press **OK**.</span></span>  
  
     <span data-ttu-id="8b275-122">![](../core/media/schemaandmapsunittestwizardselection.gif "SchemaAndMapsUnitTestWizardSelection")</span><span class="sxs-lookup"><span data-stu-id="8b275-122">![](../core/media/schemaandmapsunittestwizardselection.gif "SchemaAndMapsUnitTestWizardSelection")</span></span>  
  
### <a name="adding-test-code-to-test-the-schemas-and-map"></a><span data-ttu-id="8b275-123">添加测试代码以测试架构和映射</span><span class="sxs-lookup"><span data-stu-id="8b275-123">Adding Test Code to Test the Schemas and Map</span></span>  
  
1.  <span data-ttu-id="8b275-124">添加到以下引用**TestProject1**从项目 **.NET**添加引用对话框中的选项卡：</span><span class="sxs-lookup"><span data-stu-id="8b275-124">Add the following references to the **TestProject1** project from the **.NET** tab in the Add Reference dialog:</span></span>  
  
    -   <span data-ttu-id="8b275-125">Microsoft.BizTalk.TestTools</span><span class="sxs-lookup"><span data-stu-id="8b275-125">Microsoft.BizTalk.TestTools</span></span>  
  
    -   <span data-ttu-id="8b275-126">Microsoft XLANG/s 基本类型</span><span class="sxs-lookup"><span data-stu-id="8b275-126">Microsoft XLANG/s Base Types</span></span>  
  
2.  <span data-ttu-id="8b275-127">在解决方案资源管理器，打开 POSchemaTest.cs</span><span class="sxs-lookup"><span data-stu-id="8b275-127">In Solution Explorer, open POSchemaTest.cs</span></span>  
  
3.  <span data-ttu-id="8b275-128">滚动到文件的底部，并替换**POSchemaConstructorTest**方法，使用以下代码用于验证示例 PO 输入消息：</span><span class="sxs-lookup"><span data-stu-id="8b275-128">Scroll to the bottom of the file and replace the **POSchemaConstructorTest** method with the following code which validates the sample PO input message:</span></span>  
  
    ```  
    [TestMethod()]  
    public void POSchemaInstanceValidationTest()  
    {  
        POSchema target = new POSchema();  
  
        //=== The SamplePOInput.xml file from <Samples Path>\Orchestrations\HelloWorld ===//  
        string strSourcePO_XML = testContextInstance.TestDir + "..\\..\\..\\SamplePOInput.xml";  
  
        //=== Validate the SamplePOInput message against the schema ===//  
        Assert.IsTrue(target.ValidateInstance(strSourcePO_XML, Microsoft.BizTalk.TestTools.Schema.OutputInstanceType.XML));  
    }  
    ```  
  
4.  <span data-ttu-id="8b275-129">在解决方案资源管理器中打开 POToInvoiceTest.cs 并向该文件的顶部添加以下指令：</span><span class="sxs-lookup"><span data-stu-id="8b275-129">In Solution Explorer open POToInvoiceTest.cs and add the following directive to the top of that file:</span></span>  
  
    ```  
  
    using System.IO;   
    ```  
  
5.  <span data-ttu-id="8b275-130">滚动到文件的底部，并替换**POToInvoiceConstructorTest**方法，用下面的代码测试映射使用示例 PO 输入消息：</span><span class="sxs-lookup"><span data-stu-id="8b275-130">Scroll to the bottom of the file and replace the **POToInvoiceConstructorTest** method with the following code which tests the map using the sample PO input message:</span></span>  
  
    ```  
  
    [TestMethod()]  
    public void POToInvoiceMapTest()  
    {  
        POToInvoice target = new POToInvoice();  
  
        //=== Use the HelloWorld sample directory path for the message files ===//  
  
        string strSourcePO_XML = testContextInstance.TestDir + "..\\..\\..\\SamplePOInput.xml";  
        string strDestInvoice_XML = testContextInstance.TestDir + "..\\..\\..\\SampleInvoiceOutput.xml";  
  
        //=== Test the map by using the TestMap method of the TestableMapBase class ===//  
  
        target.ValidateOutput = true;  
        target.TestMap(strSourcePO_XML,  
                       Microsoft.BizTalk.TestTools.Schema.InputInstanceType.Xml,  
                       strDestInvoice_XML,  
                       Microsoft.BizTalk.TestTools.Schema.OutputInstanceType.XML);  
  
        //=== Output file should be created as a result of testing the map ===//  
  
        Assert.IsTrue(File.Exists(strDestInvoice_XML));   
    }  
    ```  
  
### <a name="building-and-running-the-unit-test"></a><span data-ttu-id="8b275-131">生成和运行单元测试</span><span class="sxs-lookup"><span data-stu-id="8b275-131">Building and Running the Unit Test</span></span>  
  
1.  <span data-ttu-id="8b275-132">在解决方案资源管理器中右键单击**TestProject1**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="8b275-132">In Solution Explorer, right-click **TestProject1**, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="8b275-133">在主菜单上，单击**测试**，然后在**Windows**列表中，单击**测试视图**。</span><span class="sxs-lookup"><span data-stu-id="8b275-133">On the main menu, click **Test**, and then in the **Windows** list, click **Test View**.</span></span>  
  
3.  <span data-ttu-id="8b275-134">在测试视图窗口中，右键单击**POSchemaInstanceValidationTest**，然后单击**运行选定内容**。</span><span class="sxs-lookup"><span data-stu-id="8b275-134">In the Test View window, right-click **POSchemaInstanceValidationTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="8b275-135">验证是否看到**已通过**测试结果窗口中。</span><span class="sxs-lookup"><span data-stu-id="8b275-135">Verify that you see **Passed** in the Test Results window.</span></span>  
  
4.  <span data-ttu-id="8b275-136">在测试视图窗口中，右键单击**POToInvoiceMapTest**，然后单击**运行选定内容**。</span><span class="sxs-lookup"><span data-stu-id="8b275-136">In the Test View window, right-click **POToInvoiceMapTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="8b275-137">验证是否看到**已通过**测试结果窗口中。</span><span class="sxs-lookup"><span data-stu-id="8b275-137">Verify that you see **Passed** in the Test Results window.</span></span>  
  
5.  <span data-ttu-id="8b275-138">如果任何测试失败，您可以双击测试结果窗口以查看添加或导致该测试失败的异常中的测试。</span><span class="sxs-lookup"><span data-stu-id="8b275-138">If any test fails you can double-click the test in the Test Results window to see the assert or exception that caused that test failure.</span></span>  
  
## <a name="test-code-summary"></a><span data-ttu-id="8b275-139">测试代码摘要</span><span class="sxs-lookup"><span data-stu-id="8b275-139">Test Code Summary</span></span>  
 <span data-ttu-id="8b275-140">有关启用单元测试时**HelloWorld**项目，C#类与关联**POSchema.xsd**派生自**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**类。</span><span class="sxs-lookup"><span data-stu-id="8b275-140">When unit testing was enabled for the **HelloWorld** project, the C# class associated with **POSchema.xsd** was derived from the **Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase** class.</span></span> <span data-ttu-id="8b275-141">**POSchemaInstanceValidationTest**中的方法**TestProject1**使用**ValidateInstance**方法**POSchema**类针对 PO 架构验证 SamplePOInput.xml。</span><span class="sxs-lookup"><span data-stu-id="8b275-141">The **POSchemaInstanceValidationTest** method in **TestProject1** used the **ValidateInstance** method of the **POSchema** class to validate SamplePOInput.xml against the PO schema.</span></span>  
  
 <span data-ttu-id="8b275-142">同样，当启用单元测试时用于**HelloWorld**项目，C#类与关联**POToInvoice.btm**派生与**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**类。</span><span class="sxs-lookup"><span data-stu-id="8b275-142">Similarly, when unit testing was enabled for the **HelloWorld** project, the C# class associated with the **POToInvoice.btm** map was derived from the **Microsoft.BizTalk.TestTools.Mapper.TestableMapBase** class.</span></span> <span data-ttu-id="8b275-143">**POToInvoiceMaptest**方法使用**测试映射**方法**POToInvoice**类，以测试使用相同 SamplePOInput.xml 消息映射。</span><span class="sxs-lookup"><span data-stu-id="8b275-143">The **POToInvoiceMaptest** method used the **TestMap** method of the **POToInvoice** class to test the map using the same SamplePOInput.xml message.</span></span> <span data-ttu-id="8b275-144">这会导致在 HelloWorld 目录中创建 SampleInvoiceOutput.xml。</span><span class="sxs-lookup"><span data-stu-id="8b275-144">This resulted in SampleInvoiceOutput.xml being created in the HelloWorld directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b275-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b275-145">See Also</span></span>  
 <span data-ttu-id="8b275-146">[使用单元测试功能管道](../core/using-the-unit-testing-feature-with-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="8b275-146">[Using the Unit Testing Feature with Pipelines](../core/using-the-unit-testing-feature-with-pipelines.md) </span></span>  
 [<span data-ttu-id="8b275-147">使用单元测试 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="8b275-147">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)