---
title: 在 Oracle E-business Suite 使用 WCF 通道模型运行接口表上的 insert 操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a2e5ee3-552b-40a2-aaa6-5391347f1146
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703b00adeb373fe66c4a96c324f13f9c3c5ec655
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216733"
---
# <a name="run-an-insert-operation-on-an-interface-table-in-oracle-e-business-suite-using-the-wcf-channel-model"></a>在 Oracle E-business Suite 使用 WCF 通道模型运行接口表上的 insert 操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]发现一套对 Oracle E-business Suite 接口表的 Insert、 Select、 Update 和 Delete 操作。 通过使用这些操作，你可以执行简单的 Insert、 Select、 Update 和 Delete 语句由 Where 限定目标接口表上的子句。 本主题提供有关如何执行对使用 WCF 通道模型接口表的插入操作的说明。  
  
 有关如何的适配器支持这些操作的详细信息，请参阅[接口表和接口视图上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)。 有关如何对 Oracle E-business Suite 使用 WCF 通道模型执行操作的详细信息，请参阅[与 Oracle E-business Suite 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例对执行 MS_SAMPLE_EMPLOYEE 接口表操作。 通过运行这些示例使用提供的脚本创建表。 有关示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。 示例中， **InsertOperation**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。  
  
## <a name="the-insert-message"></a>插入消息  
 若要对 Oracle E-business Suite 使用 WCF 通道模型执行操作，你必须使用特定于操作的请求消息。 要执行对 MS_SAMPLE_EMPLOYEE 接口表的插入操作的请求消息如下所示：  
  
```  
<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
  <RECORDSET>  
    <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">  
      <EMP_NO>10050</EMP_NO>  
      <NAME>John Smith</NAME>  
      <DESIGNATION>Manager</DESIGNATION>  
      <SALARY>500000</SALARY>  
      <JOIN_DATE>1999-05-31</JOIN_DATE>  
    </InsertRecord>  
  </RECORDSET>  
</Insert>  
```  
  
 此请求消息将插入以下详细信息的记录：  
  
```  
Employee Number = 10050  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 必须将消息复制到一个文件，例如 InsertRequest.xml。 此文件使用在此示例中，将请求消息发送到 Oracle E-business Suite 使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关对表操作的消息架构的详细信息，请参阅[插入、 更新、 删除和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)。  
  
## <a name="creating-a-wcf-channel-application"></a>创建 WCF 通道应用程序  
 本部分提供有关如何创建一个 WCF 通道应用程序来执行插入操作 MS_SAMPLE_EMPLOYEE 接口表上的说明。  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-table"></a>若要创建的 WCF 通道应用程序将记录插入到表  
  
1.  在 Visual Studio 中创建 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。  
  
3.  打开 Program.cs 文件并添加以下命名空间：  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  创建绑定和终结点。  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
  
    ```  
  
5.  由于您正在执行对接口表的操作，必须设置应用程序上下文。 在此示例中，若要设置应用程序上下文中，你指定**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。 有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
6.  创建并打开通道工厂。 此应用程序将请求消息发送到 Oracle E-business Suite 并收到响应，因此必须实现 IRequestChannel 接口。  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
7.  创建并打开通道。  
  
    ```  
    IRequestChannel channel;  
    try  
    {  
       channel = factory.CreateChannel();  
       channel.Open();  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception :" + ex.Message);  
       throw;  
    }  
    ```  
  
8.  创建和发送的请求消息。  
  
    ```  
    XmlReader readerIn;  
    try  
    {  
       readerIn = XmlReader.Create("InsertRequest.xml");  
       Console.WriteLine("Reader created");  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    Message messageIn;  
    Message messageOut;  
    try  
    {  
       messageIn = Message.CreateMessage(MessageVersion.Default, "InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE", readerIn);  
       messageOut = channel.Request(messageIn);  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    ```  
  
     在创建请求消息时，必须指定，该值指示适配器接口表执行的操作的消息操作。 若要执行插入操作上 MS_SAMPLE_EMPLOYEE 表，消息操作是`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`。 有关如何确定对表的各种操作的消息操作的信息，请参阅[插入、 更新、 删除和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)。  
  
9. 获取响应消息。  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
10. 关闭消息、 通道和通道工厂。  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
11. 生成此项目。 生成项目时，你必须将复制请求消息，InsertRequest.xml，与你的项目可执行文件所在的位置。 通常，此位置是项目目录下的 \bin\Debug\。  
  
12. 运行该应用程序。 响应消息，Response.xml，保存应用程序中指定的位置。 响应消息包含的数或插入的记录，如下所示：  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
      <InsertResult>1</InsertResult>  
    </InsertResponse>  
    ```  
  
     此值"1"代表一条记录插入 MS_SAMPLE_EMPLOYEE 表。  
  
## <a name="see-also"></a>另请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)