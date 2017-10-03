---
title: "使用单元测试功能包含架构和映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29bcb159-ffdb-44b9-a3ff-565973d41797
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbc14621a1830f15da02336b7b82e9df475cfe9b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-unit-testing-feature-with-schemas-and-maps"></a><span data-ttu-id="37ee4-102">对架构和映射使用单元测试功能</span><span class="sxs-lookup"><span data-stu-id="37ee4-102">Using the Unit Testing Feature with Schemas and Maps</span></span>
<span data-ttu-id="37ee4-103">本主题介绍如何在 HelloWord 工作流程示例中使用单元测试功能添加架构和映射。</span><span class="sxs-lookup"><span data-stu-id="37ee4-103">This topic demonstrates how to use the unit testing feature to add a unit test for the schemas and map in the HelloWorld orchestration example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37ee4-104">用于映射的单元测试功能当前不支持多输入映射。</span><span class="sxs-lookup"><span data-stu-id="37ee4-104">The unit testing feature for maps currently does not support multiple input maps.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="37ee4-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="37ee4-105">Prerequisites</span></span>  
 <span data-ttu-id="37ee4-106">您必须首先按照以下步骤构建 HelloWorld 示例。</span><span class="sxs-lookup"><span data-stu-id="37ee4-106">You must first follow the steps for building the HelloWorld sample.</span></span> <span data-ttu-id="37ee4-107">这些步骤可在此处找到： [HelloWorld （BizTalk Server 示例）](../core/helloworld-biztalk-server-sample.md)</span><span class="sxs-lookup"><span data-stu-id="37ee4-107">Those steps can be found here: [HelloWorld (BizTalk Server Sample)](../core/helloworld-biztalk-server-sample.md)</span></span>  
  
### <a name="adding-a-unit-test-project-to-the-helloworld-sample"></a><span data-ttu-id="37ee4-108">将单元测试项目添加到 HelloWorld 示例</span><span class="sxs-lookup"><span data-stu-id="37ee4-108">Adding a Unit Test Project to the HelloWorld Sample</span></span>  
  
1.  <span data-ttu-id="37ee4-109">在 Visual Studio 中，打开 HelloWorld.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="37ee4-109">In Visual Studio, open the HelloWorld.sln solution file.</span></span>  
  
2.  <span data-ttu-id="37ee4-110">在解决方案资源管理器，右键单击**HelloWorld**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="37ee4-110">In Solution Explorer, right-click the **HelloWorld** project, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="37ee4-111">在项目设计器中，单击**部署**属性页选项卡和组**启用单元测试**到`True`。</span><span class="sxs-lookup"><span data-stu-id="37ee4-111">In Project Designer, click the **Deployment** property page tab and set **Enable Unit Testing** to `True`.</span></span>  
  
4.  <span data-ttu-id="37ee4-112">关闭项目属性页，保存更改。</span><span class="sxs-lookup"><span data-stu-id="37ee4-112">Close the project properties page saving the changes.</span></span>  
  
5.  <span data-ttu-id="37ee4-113">在主菜单上，单击**生成**，然后单击**重新生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="37ee4-113">In main menu, click **Build**, and then click **Rebuild Solution**.</span></span>  
  
6.  <span data-ttu-id="37ee4-114">在主菜单中，单击**测试**，然后单击**新测试**。</span><span class="sxs-lookup"><span data-stu-id="37ee4-114">On the main menu, click **Test**, and then click **New Test**.</span></span>  
  
7.  <span data-ttu-id="37ee4-115">在**添加新测试**对话框中，选择**创建新的 Visual C# 测试项目**为**将添加到测试项目**字段。</span><span class="sxs-lookup"><span data-stu-id="37ee4-115">In the **Add New Test** dialog box, select **Create a new Visual C# test project** for **Add to Test Project** field.</span></span> <span data-ttu-id="37ee4-116">选择**单元测试向导**中**模板**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="37ee4-116">Select **Unit Test Wizard** in the **Templates** list, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="37ee4-117">在**新的测试项目**对话框框中，保留项目同名**TestProject1**单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="37ee4-117">In the **New Test Project** dialog box, leave the project name as **TestProject1** and click **Create**.</span></span>  
  
9. <span data-ttu-id="37ee4-118">在**创建单元测试**对话框中，展开类型并选择**POSchema()**构造函数下的**Microsoft.Samples.BizTalk.HelloWorld.POSchema**节点。</span><span class="sxs-lookup"><span data-stu-id="37ee4-118">In the **Create Unit Tests** dialog box, expand the types and select the **POSchema()** constructor under the **Microsoft.Samples.BizTalk.HelloWorld.POSchema** node.</span></span> <span data-ttu-id="37ee4-119">此外选择**POToInvoice()**构造函数下的**Microsoft.Samples.BizTalk.HelloWorld.POToInvoice**节点。</span><span class="sxs-lookup"><span data-stu-id="37ee4-119">Also select **POToInvoice()** constructor under the **Microsoft.Samples.BizTalk.HelloWorld.POToInvoice** node.</span></span> <span data-ttu-id="37ee4-120">下图显示了应进行的选择。</span><span class="sxs-lookup"><span data-stu-id="37ee4-120">The figure below shows the selections that should be made.</span></span> <span data-ttu-id="37ee4-121">完成后会显示下面的选项，请按**确定**。</span><span class="sxs-lookup"><span data-stu-id="37ee4-121">After making the selections shown below, press **OK**.</span></span>  
  
     ![](../core/media/schemaandmapsunittestwizardselection.gif "SchemaAndMapsUnitTestWizardSelection")  
  
### <a name="adding-test-code-to-test-the-schemas-and-map"></a><span data-ttu-id="37ee4-122">添加测试代码以测试架构和映射</span><span class="sxs-lookup"><span data-stu-id="37ee4-122">Adding Test Code to Test the Schemas and Map</span></span>  
  
1.  <span data-ttu-id="37ee4-123">添加以下引用到**TestProject1**项目从**.NET**添加引用对话框中的选项卡：</span><span class="sxs-lookup"><span data-stu-id="37ee4-123">Add the following references to the **TestProject1** project from the **.NET** tab in the Add Reference dialog:</span></span>  
  
    -   <span data-ttu-id="37ee4-124">Microsoft.BizTalk.TestTools</span><span class="sxs-lookup"><span data-stu-id="37ee4-124">Microsoft.BizTalk.TestTools</span></span>  
  
    -   <span data-ttu-id="37ee4-125">Microsoft XLANG/s 基本类型</span><span class="sxs-lookup"><span data-stu-id="37ee4-125">Microsoft XLANG/s Base Types</span></span>  
  
2.  <span data-ttu-id="37ee4-126">在解决方案资源管理器中，打开 POSchemaTest.cs</span><span class="sxs-lookup"><span data-stu-id="37ee4-126">In Solution Explorer, open POSchemaTest.cs</span></span>  
  
3.  <span data-ttu-id="37ee4-127">滚动到文件的底部并替换**POSchemaConstructorTest**方法替换为以下代码验证示例 PO 输入消息：</span><span class="sxs-lookup"><span data-stu-id="37ee4-127">Scroll to the bottom of the file and replace the **POSchemaConstructorTest** method with the following code which validates the sample PO input message:</span></span>  
  
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
  
4.  <span data-ttu-id="37ee4-128">在解决方案资源管理器中，打开 POToInvoiceTest.cs 并在该文件顶部添加以下指令：</span><span class="sxs-lookup"><span data-stu-id="37ee4-128">In Solution Explorer open POToInvoiceTest.cs and add the following directive to the top of that file:</span></span>  
  
    ```  
  
    using System.IO;   
    ```  
  
5.  <span data-ttu-id="37ee4-129">滚动到文件的底部并替换**POToInvoiceConstructorTest**方法替换为以下代码的测试使用示例 PO 映射输入消息：</span><span class="sxs-lookup"><span data-stu-id="37ee4-129">Scroll to the bottom of the file and replace the **POToInvoiceConstructorTest** method with the following code which tests the map using the sample PO input message:</span></span>  
  
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
  
### <a name="building-and-running-the-unit-test"></a><span data-ttu-id="37ee4-130">生成并运行单元测试</span><span class="sxs-lookup"><span data-stu-id="37ee4-130">Building and Running the Unit Test</span></span>  
  
1.  <span data-ttu-id="37ee4-131">在解决方案资源管理器，右键单击**TestProject1**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="37ee4-131">In Solution Explorer, right-click **TestProject1**, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="37ee4-132">在主菜单中，单击**测试**，然后在**Windows**列表中，单击**测试视图**。</span><span class="sxs-lookup"><span data-stu-id="37ee4-132">On the main menu, click **Test**, and then in the **Windows** list, click **Test View**.</span></span>  
  
3.  <span data-ttu-id="37ee4-133">在测试视图窗口中，右键单击**POSchemaInstanceValidationTest**，然后单击**运行选定内容**。</span><span class="sxs-lookup"><span data-stu-id="37ee4-133">In the Test View window, right-click **POSchemaInstanceValidationTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="37ee4-134">确认你看到**通过**测试结果窗口中。</span><span class="sxs-lookup"><span data-stu-id="37ee4-134">Verify that you see **Passed** in the Test Results window.</span></span>  
  
4.  <span data-ttu-id="37ee4-135">在测试视图窗口中，右键单击**POToInvoiceMapTest**，然后单击**运行选定内容**。</span><span class="sxs-lookup"><span data-stu-id="37ee4-135">In the Test View window, right-click **POToInvoiceMapTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="37ee4-136">确认你看到**通过**测试结果窗口中。</span><span class="sxs-lookup"><span data-stu-id="37ee4-136">Verify that you see **Passed** in the Test Results window.</span></span>  
  
5.  <span data-ttu-id="37ee4-137">如果任何测试失败，你可以双击“测试结果”窗口中的测试以查看导致该测试失败的添加或异常。</span><span class="sxs-lookup"><span data-stu-id="37ee4-137">If any test fails you can double-click the test in the Test Results window to see the assert or exception that caused that test failure.</span></span>  
  
## <a name="test-code-summary"></a><span data-ttu-id="37ee4-138">测试代码摘要</span><span class="sxs-lookup"><span data-stu-id="37ee4-138">Test Code Summary</span></span>  
 <span data-ttu-id="37ee4-139">为单元测试已启用时**HelloWorld**项目，与关联的 C# 类**POSchema.xsd**派生自**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**类。</span><span class="sxs-lookup"><span data-stu-id="37ee4-139">When unit testing was enabled for the **HelloWorld** project, the C# class associated with **POSchema.xsd** was derived from the **Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase** class.</span></span> <span data-ttu-id="37ee4-140">**POSchemaInstanceValidationTest**中的方法**TestProject1**使用**ValidateInstance**方法**POSchema**类验证 SamplePOInput.xml 针对采购订单架构。</span><span class="sxs-lookup"><span data-stu-id="37ee4-140">The **POSchemaInstanceValidationTest** method in **TestProject1** used the **ValidateInstance** method of the **POSchema** class to validate SamplePOInput.xml against the PO schema.</span></span>  
  
 <span data-ttu-id="37ee4-141">同样，当单元测试为启用了**HelloWorld**项目，与关联的 C# 类**POToInvoice.btm**映射派生自**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**类。</span><span class="sxs-lookup"><span data-stu-id="37ee4-141">Similarly, when unit testing was enabled for the **HelloWorld** project, the C# class associated with the **POToInvoice.btm** map was derived from the **Microsoft.BizTalk.TestTools.Mapper.TestableMapBase** class.</span></span> <span data-ttu-id="37ee4-142">**POToInvoiceMaptest**方法使用**测试映射**方法**POToInvoice**类，以测试使用同一 SamplePOInput.xml 消息映射。</span><span class="sxs-lookup"><span data-stu-id="37ee4-142">The **POToInvoiceMaptest** method used the **TestMap** method of the **POToInvoice** class to test the map using the same SamplePOInput.xml message.</span></span> <span data-ttu-id="37ee4-143">这会在 HelloWorld 目录中创建 SampleInvoiceOutput.xml。</span><span class="sxs-lookup"><span data-stu-id="37ee4-143">This resulted in SampleInvoiceOutput.xml being created in the HelloWorld directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ee4-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37ee4-144">See Also</span></span>  
 <span data-ttu-id="37ee4-145">[使用单元测试使用管道功能](../core/using-the-unit-testing-feature-with-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="37ee4-145">[Using the Unit Testing Feature with Pipelines](../core/using-the-unit-testing-feature-with-pipelines.md) </span></span>  
 [<span data-ttu-id="37ee4-146">使用单元测试 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="37ee4-146">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)