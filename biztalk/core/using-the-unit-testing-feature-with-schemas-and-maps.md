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
# <a name="using-the-unit-testing-feature-with-schemas-and-maps"></a>使用单元测试功能架构和映射
本主题演示如何使用单元测试功能在 HelloWorld 业务流程的示例中添加架构和映射的单元测试。  
  
> [!NOTE]
>  单元测试适用于映射的功能当前不支持多个输入的映射。  
  
## <a name="prerequisites"></a>先决条件  
 您必须首先按照用于生成 HelloWorld 示例的步骤。 这些步骤可在此处找到：[HelloWorld（BizTalk Server 示例）](../core/helloworld-biztalk-server-sample.md)  
  
### <a name="adding-a-unit-test-project-to-the-helloworld-sample"></a>将单元测试项目添加到 HelloWorld 示例  
  
1.  在 Visual Studio 中，打开 HelloWorld.sln 解决方案文件。  
  
2.  在解决方案资源管理器中右键单击**HelloWorld**项目，并单击**属性**。  
  
3.  在项目设计器中，单击**部署**属性页选项卡和组**启用单元测试**到`True`。  
  
4.  关闭项目属性页，保存所做的更改。  
  
5.  在主菜单中，单击**构建**，然后单击**重新生成解决方案**。  
  
6.  在主菜单上，单击**测试**，然后单击**新测试**。  
  
7.  在中**添加新测试**对话框中，选择**创建新的视觉对象C#测试项目**有关**将添加到测试项目**字段。 选择**单元测试向导**中**模板**列表，，然后单击**确定**。  
  
8.  在中**新的测试项目**对话框框中，将项目名称设置为**TestProject1**然后单击**创建**。  
  
9. 在中**创建单元测试**对话框中，展开类型并选择**POSchema()** 下的构造函数**Microsoft.Samples.BizTalk.HelloWorld.POSchema**节点。 此外选择**POToInvoice()** 构造函数下的**Microsoft.Samples.BizTalk.HelloWorld.POToInvoice**节点。 下图显示了应做的选择。 做出如下所示选择后，按**确定**。  
  
     ![](../core/media/schemaandmapsunittestwizardselection.gif "SchemaAndMapsUnitTestWizardSelection")  
  
### <a name="adding-test-code-to-test-the-schemas-and-map"></a>添加测试代码以测试架构和映射  
  
1.  添加到以下引用**TestProject1**从项目 **.NET**添加引用对话框中的选项卡：  
  
    -   Microsoft.BizTalk.TestTools  
  
    -   Microsoft XLANG/s 基本类型  
  
2.  在解决方案资源管理器，打开 POSchemaTest.cs  
  
3.  滚动到文件的底部，并替换**POSchemaConstructorTest**方法，使用以下代码用于验证示例 PO 输入消息：  
  
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
  
4.  在解决方案资源管理器中打开 POToInvoiceTest.cs 并向该文件的顶部添加以下指令：  
  
    ```  
  
    using System.IO;   
    ```  
  
5.  滚动到文件的底部，并替换**POToInvoiceConstructorTest**方法，用下面的代码测试映射使用示例 PO 输入消息：  
  
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
  
### <a name="building-and-running-the-unit-test"></a>生成和运行单元测试  
  
1.  在解决方案资源管理器中右键单击**TestProject1**，然后单击**生成**。  
  
2.  在主菜单上，单击**测试**，然后在**Windows**列表中，单击**测试视图**。  
  
3.  在测试视图窗口中，右键单击**POSchemaInstanceValidationTest**，然后单击**运行选定内容**。 验证是否看到**已通过**测试结果窗口中。  
  
4.  在测试视图窗口中，右键单击**POToInvoiceMapTest**，然后单击**运行选定内容**。 验证是否看到**已通过**测试结果窗口中。  
  
5.  如果任何测试失败，您可以双击测试结果窗口以查看添加或导致该测试失败的异常中的测试。  
  
## <a name="test-code-summary"></a>测试代码摘要  
 有关启用单元测试时**HelloWorld**项目，C#类与关联**POSchema.xsd**派生自**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**类。 **POSchemaInstanceValidationTest**中的方法**TestProject1**使用**ValidateInstance**方法**POSchema**类针对 PO 架构验证 SamplePOInput.xml。  
  
 同样，当启用单元测试时用于**HelloWorld**项目，C#类与关联**POToInvoice.btm**派生与**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**类。 **POToInvoiceMaptest**方法使用**测试映射**方法**POToInvoice**类，以测试使用相同 SamplePOInput.xml 消息映射。 这会导致在 HelloWorld 目录中创建 SampleInvoiceOutput.xml。  
  
## <a name="see-also"></a>请参阅  
 [使用单元测试功能管道](../core/using-the-unit-testing-feature-with-pipelines.md)   
 [使用单元测试 (Visual Studio)](http://go.microsoft.com/fwlink/?LinkId=128890)