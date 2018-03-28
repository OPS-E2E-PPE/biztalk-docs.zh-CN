---
title: 使用单元测试使用管道功能 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d58bfa4-322b-455f-a062-5bd44d368f57
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca19a58410014b9ea7c0c49df7420b439a544581
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="using-the-unit-testing-feature-with-pipelines"></a>对管道使用单元测试功能
本主题演示如何使用单元测试功能为 FlatFileReceive 管道示例中的管道添加单元测试。 管道单元测试功能类似于此处记录 Pipeline.exe 工具：[管道工具](../core/pipeline-tools.md)。 如果启用单元测试上 **部署** 选项卡上的项目属性中，你的项目中的管道类派生自 **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**。  此类会对 Pipeline.exe 工具公开的某些相同功能进行建模。  
  
## <a name="prerequisites"></a>先决条件  
 必须首先按照步骤生成 FlatFileReceive 示例，并熟悉该示例。 可以此处找到生成 FlatFileReceive 示例包括步骤的文档： [FlatFileReceive （BizTalk Server 示例）](../core/flatfilereceive-biztalk-server-sample.md)。  
  
## <a name="adding-a-unit-test-project-to-the-flatfilereceive-sample"></a>将单元测试项目添加到 FlatFileReceive 示例  
  
#### <a name="to-add-a-unit-test-project-to-the-flatfilereceive-sample"></a>将单元测试项目添加到 FlatFileReceive 示例  
  
1.  在 Visual Studio 中，打开 FlatFileReceive.sln 解决方案文件。  
  
2.  在解决方案资源管理器，右键单击 **FlatFileReceive** 项目，，然后单击 **属性**。  
  
3.  在项目设计器中，单击 **部署** 属性页选项卡和组 **启用单元测试** 到 `True`。  
  
4.  关闭项目属性页，保存更改。  
  
5.  在主菜单中，单击 **生成**, ，然后单击 **重新生成解决方案**。  
  
6.  在主菜单中，单击 **测试**, ，然后单击 **新测试**。  
  
7.  在 **添加新测试** 对话框中，选择 **创建新的 Visual C# 测试项目** 为 **将添加到测试项目** 字段。 选择 **单元测试向导** 中 **模板** 列表，，然后单击 **确定**。  
  
8.  在 **新的测试项目** 对话框框中，保留项目同名 **TestProject1** 单击 **创建**。  
  
9. 在 **创建单元测试** 对话框中，展开类型并选择 **FFReceivePipeline()** 构造函数下的 **Microsoft.Samples.BizTalk.FlatFileReceive.FFReceivePipeline** 节点。 单击 **“确定”**。  
  
## <a name="adding-test-code-to-test-the-pipeline"></a>添加测试代码以测试管道  
  
#### <a name="to-add-test-code-to-test-the-pipeline"></a>若要添加的测试代码以测试管道  
  
1.  添加以下引用到 **TestProject1** 项目︰  
  
    -   BizTalk 管道 Interop  
  
    -   Microsoft.BizTalk.TestTools  
  
    -   Microsoft XLANG/s 基本类型  
  
2.  在解决方案资源管理器中，打开 FFReceivePipelineTest.cs，然后将以下指令添加到该文件的顶部：  
  
    ```  
    using System.IO;  
    using System.Collections.Specialized;  
    using System.Collections.Generic;  
    ```  
  
3.  滚动到文件的底部并替换 **FFReceivePipelineConstructorTest** 方法替换为以下代码，它验证测试管道之前存在的管道输入。 此代码还验证是否生成符合平面文件架构的消息。  
  
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
  
## <a name="building-and-running-the-unit-test"></a>生成并运行单元测试  
  
#### <a name="to-build-and-run-the-unit-test"></a>生成并运行单元测试  
  
1.  在解决方案资源管理器，右键单击 **TestProject1**, ，然后单击 **生成**。  
  
2.  在主菜单中，单击 **测试**, ，然后在 **Windows** 列表中，单击 **测试视图**。  
  
3.  在测试视图窗口中，右键单击 **FFReceivePipelineUnitTest**, ，然后单击 **运行选定内容**。 确认你看到 **通过** 测试结果窗口中。  
  
4.  在 TestResults 目录中检查 *.out 文件。 此文件应包含管道处理的新消息。  它应位于类似于以下示例的目录中：  
  
     C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\Pipelines\AssemblerDisassembler\FlatFileReceive\TestResults\Wes_BTS2009Svr 2009-02-04 09_01_04\Out  
  
     已处理的消息应类似于以下内容：  
  
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
  
5.  如果任何测试失败，你可以双击“测试结果”窗口中的测试以查看导致该测试失败的添加或异常。  
  
## <a name="test-code-summary"></a>测试代码摘要  
 为单元测试已启用时 **FlatFileReceive** 项目， **FFReceivePipeline** 与相关联的 C# 类 **FFReceivePipeline.btp** 派生自 **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline** 类。 **FFReceivePipelineUnitTest** 中的方法 **TestProject1** 使用 **TestPipeline** 方法， **FFReceivePipeline** 继承，以测试平面文件接收管道。 在管道处理完消息后，将根据平面文件架构对输出消息进行验证。 参数 **TestPipeline** 方法如下所示︰  
  
|参数名称|Description|  
|--------------------|-----------------|  
|文档|包含管道处理的消息的 StringCollection。|  
|组成部分|包含消息部分的 StringCollection。|  
|架构|用于将每种消息类型映射到其对应的字典映射 \*.xsd 架构文件。 密钥必须是格式 **Namespace.Type**。 命名空间和使用类型应注意的是从属性窗口\*Visual Studio 中的.xsd 文件。 请参见以下屏幕截图。<br /><br /> ![](../core/media/namespaceandtypeforxsd.gif "NamespaceAndTypeForXSD")<br /><br /> **Namespace 和公开从 XSD 文件的属性窗口的类型。**|  
  
## <a name="see-also"></a>另请参阅  
 [使用单元测试与架构和映射的功能](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)   
 [使用单元测试 (Visual Studio)](http://go.microsoft.com/fwlink/?LinkId=128890)