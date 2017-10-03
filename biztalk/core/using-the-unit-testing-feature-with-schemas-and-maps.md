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
# <a name="using-the-unit-testing-feature-with-schemas-and-maps"></a>对架构和映射使用单元测试功能
本主题介绍如何在 HelloWord 工作流程示例中使用单元测试功能添加架构和映射。  
  
> [!NOTE]
>  用于映射的单元测试功能当前不支持多输入映射。  
  
## <a name="prerequisites"></a>先决条件  
 您必须首先按照以下步骤构建 HelloWorld 示例。 这些步骤可在此处找到： [HelloWorld （BizTalk Server 示例）](../core/helloworld-biztalk-server-sample.md)  
  
### <a name="adding-a-unit-test-project-to-the-helloworld-sample"></a>将单元测试项目添加到 HelloWorld 示例  
  
1.  在 Visual Studio 中，打开 HelloWorld.sln 解决方案文件。  
  
2.  在解决方案资源管理器，右键单击**HelloWorld**项目，，然后单击**属性**。  
  
3.  在项目设计器中，单击**部署**属性页选项卡和组**启用单元测试**到`True`。  
  
4.  关闭项目属性页，保存更改。  
  
5.  在主菜单上，单击**生成**，然后单击**重新生成解决方案**。  
  
6.  在主菜单中，单击**测试**，然后单击**新测试**。  
  
7.  在**添加新测试**对话框中，选择**创建新的 Visual C# 测试项目**为**将添加到测试项目**字段。 选择**单元测试向导**中**模板**列表，，然后单击**确定**。  
  
8.  在**新的测试项目**对话框框中，保留项目同名**TestProject1**单击**创建**。  
  
9. 在**创建单元测试**对话框中，展开类型并选择**POSchema()**构造函数下的**Microsoft.Samples.BizTalk.HelloWorld.POSchema**节点。 此外选择**POToInvoice()**构造函数下的**Microsoft.Samples.BizTalk.HelloWorld.POToInvoice**节点。 下图显示了应进行的选择。 完成后会显示下面的选项，请按**确定**。  
  
     ![](../core/media/schemaandmapsunittestwizardselection.gif "SchemaAndMapsUnitTestWizardSelection")  
  
### <a name="adding-test-code-to-test-the-schemas-and-map"></a>添加测试代码以测试架构和映射  
  
1.  添加以下引用到**TestProject1**项目从**.NET**添加引用对话框中的选项卡：  
  
    -   Microsoft.BizTalk.TestTools  
  
    -   Microsoft XLANG/s 基本类型  
  
2.  在解决方案资源管理器中，打开 POSchemaTest.cs  
  
3.  滚动到文件的底部并替换**POSchemaConstructorTest**方法替换为以下代码验证示例 PO 输入消息：  
  
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
  
4.  在解决方案资源管理器中，打开 POToInvoiceTest.cs 并在该文件顶部添加以下指令：  
  
    ```  
  
    using System.IO;   
    ```  
  
5.  滚动到文件的底部并替换**POToInvoiceConstructorTest**方法替换为以下代码的测试使用示例 PO 映射输入消息：  
  
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
  
### <a name="building-and-running-the-unit-test"></a>生成并运行单元测试  
  
1.  在解决方案资源管理器，右键单击**TestProject1**，然后单击**生成**。  
  
2.  在主菜单中，单击**测试**，然后在**Windows**列表中，单击**测试视图**。  
  
3.  在测试视图窗口中，右键单击**POSchemaInstanceValidationTest**，然后单击**运行选定内容**。 确认你看到**通过**测试结果窗口中。  
  
4.  在测试视图窗口中，右键单击**POToInvoiceMapTest**，然后单击**运行选定内容**。 确认你看到**通过**测试结果窗口中。  
  
5.  如果任何测试失败，你可以双击“测试结果”窗口中的测试以查看导致该测试失败的添加或异常。  
  
## <a name="test-code-summary"></a>测试代码摘要  
 为单元测试已启用时**HelloWorld**项目，与关联的 C# 类**POSchema.xsd**派生自**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**类。 **POSchemaInstanceValidationTest**中的方法**TestProject1**使用**ValidateInstance**方法**POSchema**类验证 SamplePOInput.xml 针对采购订单架构。  
  
 同样，当单元测试为启用了**HelloWorld**项目，与关联的 C# 类**POToInvoice.btm**映射派生自**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**类。 **POToInvoiceMaptest**方法使用**测试映射**方法**POToInvoice**类，以测试使用同一 SamplePOInput.xml 消息映射。 这会在 HelloWorld 目录中创建 SampleInvoiceOutput.xml。  
  
## <a name="see-also"></a>另请参阅  
 [使用单元测试使用管道功能](../core/using-the-unit-testing-feature-with-pipelines.md)   
 [使用单元测试 (Visual Studio)](http://go.microsoft.com/fwlink/?LinkId=128890)