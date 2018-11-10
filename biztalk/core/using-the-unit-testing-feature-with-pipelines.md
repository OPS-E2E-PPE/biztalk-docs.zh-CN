---
title: 使用单元测试功能管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d58bfa4-322b-455f-a062-5bd44d368f57
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e437df707ace58eef6de9dc9f7eb65d888309a9
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752632"
---
# <a name="using-the-unit-testing-feature-with-pipelines"></a><span data-ttu-id="f7d40-102">对管道使用单元测试功能</span><span class="sxs-lookup"><span data-stu-id="f7d40-102">Using the Unit Testing Feature with Pipelines</span></span>
<span data-ttu-id="f7d40-103">本主题演示如何使用单元测试功能为 FlatFileReceive 管道示例中的管道添加单元测试。</span><span class="sxs-lookup"><span data-stu-id="f7d40-103">This topic demonstrates how to use the unit testing feature to add a unit test for the pipeline in the FlatFileReceive pipeline example.</span></span> <span data-ttu-id="f7d40-104">管道单元测试是类似于此处记录的 Pipeline.exe 工具：[管道工具](../core/pipeline-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d40-104">Pipeline unit testing is similar to the Pipeline.exe tool that is documented here: [Pipeline Tools](../core/pipeline-tools.md).</span></span> <span data-ttu-id="f7d40-105">如果启用单元测试上**部署**选项卡上的项目属性中，你的项目中的管道类派生自**Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**。</span><span class="sxs-lookup"><span data-stu-id="f7d40-105">When you enable unit testing on the **Deployment** tab of the project properties, the pipeline class in your project is derived from **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**.</span></span>  <span data-ttu-id="f7d40-106">此类会对 Pipeline.exe 工具公开的某些相同功能进行建模。</span><span class="sxs-lookup"><span data-stu-id="f7d40-106">This class models some of the same functionality exposed by the Pipeline.exe tool.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f7d40-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="f7d40-107">Prerequisites</span></span>  
 <span data-ttu-id="f7d40-108">必须首先按照步骤生成 FlatFileReceive 示例，并熟悉该示例。</span><span class="sxs-lookup"><span data-stu-id="f7d40-108">You must first follow the steps for building the FlatFileReceive sample and become familiar with that sample.</span></span> <span data-ttu-id="f7d40-109">包括的步骤生成 FlatFileReceive 示例可以在此找到的文档： [FlatFileReceive （BizTalk Server 示例）](../core/flatfilereceive-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d40-109">The documentation that includes the steps for building the FlatFileReceive sample can be found here: [FlatFileReceive (BizTalk Server Sample)](../core/flatfilereceive-biztalk-server-sample.md).</span></span>  
  
## <a name="adding-a-unit-test-project-to-the-flatfilereceive-sample"></a><span data-ttu-id="f7d40-110">将单元测试项目添加到 FlatFileReceive 示例</span><span class="sxs-lookup"><span data-stu-id="f7d40-110">Adding a Unit Test Project to the FlatFileReceive Sample</span></span>  
  
#### <a name="to-add-a-unit-test-project-to-the-flatfilereceive-sample"></a><span data-ttu-id="f7d40-111">若要将单元测试项目添加到 FlatFileReceive 示例</span><span class="sxs-lookup"><span data-stu-id="f7d40-111">To add a unit test project to the FlatFileReceive sample</span></span>  
  
1.  <span data-ttu-id="f7d40-112">在 Visual Studio 中，打开 FlatFileReceive.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="f7d40-112">In Visual Studio, open the FlatFileReceive.sln solution file.</span></span>  
  
2.  <span data-ttu-id="f7d40-113">在解决方案资源管理器中右键单击**FlatFileReceive**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f7d40-113">In Solution Explorer, right-click the **FlatFileReceive** project, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f7d40-114">在项目设计器中，单击**部署**属性页选项卡和组**启用单元测试**到`True`。</span><span class="sxs-lookup"><span data-stu-id="f7d40-114">In Project Designer, click the **Deployment** property page tab and set **Enable Unit Testing** to `True`.</span></span>  
  
4.  <span data-ttu-id="f7d40-115">关闭项目属性页，保存更改。</span><span class="sxs-lookup"><span data-stu-id="f7d40-115">Close the project properties page saving the changes.</span></span>  
  
5.  <span data-ttu-id="f7d40-116">在主菜单上，单击**构建**，然后单击**重新生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="f7d40-116">On the main menu, click **Build**, and then click **Rebuild Solution**.</span></span>  
  
6.  <span data-ttu-id="f7d40-117">在主菜单上，单击**测试**，然后单击**新测试**。</span><span class="sxs-lookup"><span data-stu-id="f7d40-117">On the main menu, click **Test**, and then click **New Test**.</span></span>  
  
7.  <span data-ttu-id="f7d40-118">在中**添加新测试**对话框中，选择**创建新的视觉对象C#测试项目**有关**将添加到测试项目**字段。</span><span class="sxs-lookup"><span data-stu-id="f7d40-118">In the **Add New Test** dialog box, select **Create a new Visual C# test project** for the **Add to Test Project** field.</span></span> <span data-ttu-id="f7d40-119">选择**单元测试向导**中**模板**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f7d40-119">Select **Unit Test Wizard** in the **Templates** list, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="f7d40-120">在中**新的测试项目**对话框框中，将项目名称设置为**TestProject1**然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="f7d40-120">In the **New Test Project** dialog box, leave the project name as **TestProject1** and click **Create**.</span></span>  
  
9. <span data-ttu-id="f7d40-121">在中**创建单元测试**对话框中，展开类型并选择**FFReceivePipeline()** 构造函数下的**Microsoft.Samples.BizTalk.FlatFileReceive.FFReceivePipeline**节点。</span><span class="sxs-lookup"><span data-stu-id="f7d40-121">In the **Create Unit Tests** dialog box, expand the types and select the **FFReceivePipeline()** constructor under the **Microsoft.Samples.BizTalk.FlatFileReceive.FFReceivePipeline** node.</span></span> <span data-ttu-id="f7d40-122">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="f7d40-122">Click **OK**.</span></span>  
  
## <a name="adding-test-code-to-test-the-pipeline"></a><span data-ttu-id="f7d40-123">添加测试代码以测试管道</span><span class="sxs-lookup"><span data-stu-id="f7d40-123">Adding Test Code to Test the Pipeline</span></span>  
  
#### <a name="to-add-test-code-to-test-the-pipeline"></a><span data-ttu-id="f7d40-124">若要添加测试代码以测试管道</span><span class="sxs-lookup"><span data-stu-id="f7d40-124">To add test code to test the pipeline</span></span>  
  
1.  <span data-ttu-id="f7d40-125">添加到以下引用**TestProject1**项目：</span><span class="sxs-lookup"><span data-stu-id="f7d40-125">Add the following references to the **TestProject1** project:</span></span>  
  
    -   <span data-ttu-id="f7d40-126">BizTalk 管道 Interop</span><span class="sxs-lookup"><span data-stu-id="f7d40-126">BizTalk Pipeline Interop</span></span>  
  
    -   <span data-ttu-id="f7d40-127">Microsoft.BizTalk.TestTools</span><span class="sxs-lookup"><span data-stu-id="f7d40-127">Microsoft.BizTalk.TestTools</span></span>  
  
    -   <span data-ttu-id="f7d40-128">Microsoft XLANG/s 基本类型</span><span class="sxs-lookup"><span data-stu-id="f7d40-128">Microsoft XLANG/s Base Types</span></span>  
  
2.  <span data-ttu-id="f7d40-129">在解决方案资源管理器中，打开 FFReceivePipelineTest.cs，然后将以下指令添加到该文件的顶部：</span><span class="sxs-lookup"><span data-stu-id="f7d40-129">In Solution Explorer, open FFReceivePipelineTest.cs and add the following directives to the top of that file:</span></span>  
  
    ```  
    using System.IO;  
    using System.Collections.Specialized;  
    using System.Collections.Generic;  
    ```  
  
3.  <span data-ttu-id="f7d40-130">滚动到文件的底部，并替换**FFReceivePipelineConstructorTest**方法验证是否测试管道之前存在的管道输入以下代码。</span><span class="sxs-lookup"><span data-stu-id="f7d40-130">Scroll to the bottom of the file and replace the **FFReceivePipelineConstructorTest** method with the following code, which verifies that the pipeline inputs exist before testing the pipeline.</span></span> <span data-ttu-id="f7d40-131">此代码还验证是否生成符合平面文件架构的消息。</span><span class="sxs-lookup"><span data-stu-id="f7d40-131">This code also verifies that a message conforming to the flat file schema is generated.</span></span>  
  
    ```  
    [TestMethod()]  
    public void FFReceivePipelineUnitTest()  
    {  
        //=== Pipeline class derived from TestableReceivePipeline ===//  
        FFReceivePipeline target = new FFReceivePipeline();  
  
        //=== Collection of messages to test the flat file pipeline ===//  
        StringCollection documents = new StringCollection();  
        string strSourcePO_XML = @".\..\..\..\FlatFileReceive_in.txt";  
        Assert.IsTrue(File.Exists(strSourcePO_XML));  
        documents.Add(strSourcePO_XML);  
  
        //=== Only a body part for this test message so an empty ===//  
        //=== collection will be passed.                         ===//  
        StringCollection parts = new StringCollection();  
  
        //=== Dictionary mapping the schema to the namespace and type ===//  
        //=== as displayed in the properties window for the *.xsd     ===//  
        Dictionary<string, string> schemas = new Dictionary<string, string>();  
        string SchemaFile = @".\..\..\..\PO.xsd";  
        Assert.IsTrue(File.Exists(SchemaFile));  
        schemas.Add("Microsoft.Samples.BizTalk.FlatFileReceive.PO", SchemaFile);  
  
        //=== Test the execution of the pipeline using the inputs ===//  
        target.TestPipeline(documents, parts, schemas);  
  
        //=== Validate that the pipeline test produced the message ===//  
        //=== which conforms to the schema.                        ===//  
        string[] strMessages = Directory.GetFiles(testContextInstance.TestDir + "\\out","Message*.out");              
        Assert.IsTrue(strMessages.Length > 0);                          
        PO PO_target = new PO();  
        foreach(string outFile in strMessages)  
        {  
          Assert.IsTrue(PO_target.ValidateInstance(outFile,Microsoft.BizTalk.TestTools.Schema.OutputInstanceType.XML));  
        }                       
    }  
    ```  
  
## <a name="building-and-running-the-unit-test"></a><span data-ttu-id="f7d40-132">生成和运行单元测试</span><span class="sxs-lookup"><span data-stu-id="f7d40-132">Building and Running the Unit Test</span></span>  
  
#### <a name="to-build-and-run-the-unit-test"></a><span data-ttu-id="f7d40-133">生成并运行单元测试</span><span class="sxs-lookup"><span data-stu-id="f7d40-133">To build and run the unit test</span></span>  
  
1.  <span data-ttu-id="f7d40-134">在解决方案资源管理器中右键单击**TestProject1**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="f7d40-134">In Solution Explorer, right-click **TestProject1**, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="f7d40-135">在主菜单上，单击**测试**，然后在**Windows**列表中，单击**测试视图**。</span><span class="sxs-lookup"><span data-stu-id="f7d40-135">On the main menu, click **Test**, and then in the **Windows** list, click **Test View**.</span></span>  
  
3.  <span data-ttu-id="f7d40-136">在测试视图窗口中，右键单击**FFReceivePipelineUnitTest**，然后单击**运行选定内容**。</span><span class="sxs-lookup"><span data-stu-id="f7d40-136">In the Test View window, right-click **FFReceivePipelineUnitTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="f7d40-137">验证是否看到**已通过**测试结果窗口中。</span><span class="sxs-lookup"><span data-stu-id="f7d40-137">Verify that you see **Passed** in the Test Results window.</span></span>  
  
4.  <span data-ttu-id="f7d40-138">TestResults 目录中检查\*.out 文件。</span><span class="sxs-lookup"><span data-stu-id="f7d40-138">In the TestResults directory examine the \*.out file.</span></span> <span data-ttu-id="f7d40-139">此文件应包含管道处理的新消息。</span><span class="sxs-lookup"><span data-stu-id="f7d40-139">This file should contain the new message processed by the pipeline.</span></span>  <span data-ttu-id="f7d40-140">它应位于类似于以下示例的目录中：</span><span class="sxs-lookup"><span data-stu-id="f7d40-140">It should be located in a directory similar to the following:</span></span>  
  
     <span data-ttu-id="f7d40-141">C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\Pipelines\AssemblerDisassembler\FlatFileReceive\TestResults\Wes_BTS2009Svr 2009-02-04 09_01_04\Out</span><span class="sxs-lookup"><span data-stu-id="f7d40-141">C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\Pipelines\AssemblerDisassembler\FlatFileReceive\TestResults\Wes_BTS2009Svr 2009-02-04 09_01_04\Out</span></span>  
  
     <span data-ttu-id="f7d40-142">已处理的消息应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="f7d40-142">The processed message should look similar to the following:</span></span>  
  
    ```  
    <purchaseOrder orderDate="1999-10-20" xmlns="http://FlatFileRecieve.PO">  
  
      <shipTo country="US" xmlns="">  
        <name>Alice Smith</name>  
        <street>123 Maple Street</street>  
        <city>Mill Valley</city>  
        <state>CA</state>  
        <zip>90952</zip>  
      </shipTo>  
  
      <billTo country="US" xmlns="">  
        <name>Robert Smith</name>  
        <street>8 Oak Avenue</street>  
        <city>Old Town</city>  
        <state>PA</state>  
        <zip>95819</zip>  
      </billTo>  
  
      <comment>Hurry, my lawn is going wild!</comment>  
  
      <items xmlns="">  
  
        <item partNum="872-AA">  
          <productName>Lawnmower</productName>  
          <quantity>1</quantity>  
          <USPrice>148.95</USPrice>  
          <comment xmlns="http://FlatFileRecieve.PO">Confirm this is electric</comment>  
        </item>  
  
        <item partNum="926-AA">  
          <productName>Baby Monitor</productName>  
          <quantity>1</quantity>  
          <USPrice>39.98</USPrice>  
          <comment xmlns="http://FlatFileRecieve.PO">Confirm this is electric</comment>  
          <shipDate>1999-05-21</shipDate>  
        </item>  
  
      </items>  
  
    </purchaseOrder>  
    ```  
  
5.  <span data-ttu-id="f7d40-143">如果任何测试失败，你可以双击“测试结果”窗口中的测试以查看导致该测试失败的添加或异常。</span><span class="sxs-lookup"><span data-stu-id="f7d40-143">If any test fails you can double-click the test in the Test Results window to see the assert or exception that caused that test failure.</span></span>  
  
## <a name="test-code-summary"></a><span data-ttu-id="f7d40-144">测试代码摘要</span><span class="sxs-lookup"><span data-stu-id="f7d40-144">Test Code Summary</span></span>  
 <span data-ttu-id="f7d40-145">有关启用单元测试时**FlatFileReceive**项目， **FFReceivePipeline** C#类与关联**FFReceivePipeline.btp**派生自**Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**类。</span><span class="sxs-lookup"><span data-stu-id="f7d40-145">When unit testing was enabled for the **FlatFileReceive** project, the **FFReceivePipeline** C# class associated with **FFReceivePipeline.btp** was derived from the **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline** class.</span></span> <span data-ttu-id="f7d40-146">**FFReceivePipelineUnitTest**中的方法**TestProject1**使用**TestPipeline**方法的**FFReceivePipeline**继承若要测试的平面文件接收管道。</span><span class="sxs-lookup"><span data-stu-id="f7d40-146">The **FFReceivePipelineUnitTest** method in **TestProject1** used the **TestPipeline** method that **FFReceivePipeline** inherited to test the flat file receive pipeline.</span></span> <span data-ttu-id="f7d40-147">在管道处理完消息后，将根据平面文件架构对输出消息进行验证。</span><span class="sxs-lookup"><span data-stu-id="f7d40-147">After the pipeline processed the message, the output message was validated against the flat file schema.</span></span> <span data-ttu-id="f7d40-148">参数**TestPipeline**方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7d40-148">The parameters for the **TestPipeline** method are as follows:</span></span>  
  
|<span data-ttu-id="f7d40-149">参数名称</span><span class="sxs-lookup"><span data-stu-id="f7d40-149">Parameter Name</span></span>|<span data-ttu-id="f7d40-150">Description</span><span class="sxs-lookup"><span data-stu-id="f7d40-150">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f7d40-151">文档</span><span class="sxs-lookup"><span data-stu-id="f7d40-151">Documents</span></span>|<span data-ttu-id="f7d40-152">包含管道处理的消息的 StringCollection。</span><span class="sxs-lookup"><span data-stu-id="f7d40-152">StringCollection containing messages to be processed by the pipeline.</span></span>|  
|<span data-ttu-id="f7d40-153">组成部分</span><span class="sxs-lookup"><span data-stu-id="f7d40-153">Parts</span></span>|<span data-ttu-id="f7d40-154">包含消息部分的 StringCollection。</span><span class="sxs-lookup"><span data-stu-id="f7d40-154">StringCollection containing the parts for the messages.</span></span>|  
|<span data-ttu-id="f7d40-155">架构</span><span class="sxs-lookup"><span data-stu-id="f7d40-155">Schemas</span></span>|<span data-ttu-id="f7d40-156">用于将每种消息类型映射到其对应的目录映射\*.xsd 架构文件。</span><span class="sxs-lookup"><span data-stu-id="f7d40-156">Dictionary mapping used to map each message type to its corresponding \*.xsd schema file.</span></span> <span data-ttu-id="f7d40-157">密钥必须采用格式**Namespace.Type**。</span><span class="sxs-lookup"><span data-stu-id="f7d40-157">The key must be in the format **Namespace.Type**.</span></span> <span data-ttu-id="f7d40-158">命名空间和使用类型应注意的是从属性窗口\*Visual Studio 中的.xsd 文件。</span><span class="sxs-lookup"><span data-stu-id="f7d40-158">The namespace and type used should be noted from the properties window for the \*.xsd file in Visual Studio.</span></span> <span data-ttu-id="f7d40-159">请参见以下屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="f7d40-159">See the screenshot below.</span></span><br /><br /> <span data-ttu-id="f7d40-160">![](../core/media/namespaceandtypeforxsd.gif "NamespaceAndTypeForXSD")</span><span class="sxs-lookup"><span data-stu-id="f7d40-160">![](../core/media/namespaceandtypeforxsd.gif "NamespaceAndTypeForXSD")</span></span><br /><br /> <span data-ttu-id="f7d40-161">**Namespace 和从 XSD 文件的属性窗口公开的类型。**</span><span class="sxs-lookup"><span data-stu-id="f7d40-161">**Namespace and type exposed from the properties window of an XSD file.**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7d40-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7d40-162">See Also</span></span>  
 <span data-ttu-id="f7d40-163">[使用单元测试功能架构和映射](../core/using-the-unit-testing-feature-with-schemas-and-maps.md) </span><span class="sxs-lookup"><span data-stu-id="f7d40-163">[Using the Unit Testing Feature with Schemas and Maps](../core/using-the-unit-testing-feature-with-schemas-and-maps.md) </span></span>  
 [<span data-ttu-id="f7d40-164">使用单元测试 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="f7d40-164">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)