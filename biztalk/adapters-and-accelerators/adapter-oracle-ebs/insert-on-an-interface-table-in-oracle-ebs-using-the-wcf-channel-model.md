---
title: Oracle E-business Suite 使用 WCF 通道模型中运行插入操作在界面表 |Microsoft Docs
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
ms.openlocfilehash: c2f52284e3d4fb08c7dafae9f1a761346fd56351
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375482"
---
# <a name="run-an-insert-operation-on-an-interface-table-in-oracle-e-business-suite-using-the-wcf-channel-model"></a>Oracle E-business Suite 使用 WCF 通道模型中运行插入操作在界面表
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]找到对 Oracle E-business Suite 的接口表的 Insert、 Select、 Update 和 Delete 操作的一组。 通过使用这些操作，你可以执行简单的 Insert、 Select、 Update 和 Delete 语句限定由 Where 子句对目标接口表。 本主题提供有关如何执行插入操作在界面表使用 WCF 通道模型的说明。  
  
 适配器如何支持这些操作的详细信息，请参阅[对界面表和界面视图操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)。 有关如何执行对 Oracle E-business Suite 使用 WCF 通道模型的操作的详细信息，请参阅[与 Oracle E-business Suite 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例执行 MS_SAMPLE_EMPLOYEE 接口表的操作。 通过运行这些示例提供的脚本创建表。 有关示例的详细信息，请参阅[适用于 Oracle EBS 适配器示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。 示例中， **InsertOperation**，后者基于本主题中，还提供与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。  
  
## <a name="the-insert-message"></a>插入消息  
 若要对 Oracle E-business Suite 使用 WCF 通道模型执行操作，必须具有特定于操作的请求消息。 要执行插入操作 MS_SAMPLE_EMPLOYEE 接口表上的请求消息类似于以下内容：  
  
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
  
 必须将该消息复制到一个文件，例如 InsertRequest.xml。 此文件使用在此示例中，若要将请求消息发送到 Oracle E-business Suite 使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关对表的操作的消息架构的详细信息，请参阅[Insert、 Update、 Delete 和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)。  
  
## <a name="creating-a-wcf-channel-application"></a>创建 WCF 通道应用程序  
 本部分将说明了如何创建 WCF 通道应用程序，以执行插入操作上 MS_SAMPLE_EMPLOYEE 接口表。  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-table"></a>若要创建的 WCF 通道应用程序将记录插入到表  
  
1.  在 Visual Studio 中创建一个 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
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
  
5.  由于您正在执行的操作在界面表，必须设置应用程序上下文。 在此示例中，若要设置应用程序上下文中，您指定**OracleUserName**， **OraclePassword**，并**OracleEBSResponsibilityName**绑定属性。 有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
6.  创建并打开通道工厂。 此应用程序将请求消息发送到 Oracle E-business Suite，并接收响应，因此您必须实现 IRequestChannel 接口。  
  
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
  
8.  创建并发送请求消息。  
  
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
  
     在创建请求消息时，必须指定指示适配器对界面表执行的操作的消息操作。 若要执行插入操作 MS_SAMPLE_EMPLOYEE 表上的，消息操作是`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`。 有关如何确定对表进行各种操作的消息操作的信息，请参阅[Insert、 Update、 Delete 和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)。  
  
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
  
11. 生成项目。 后生成项目时，必须将复制的请求消息，InsertRequest.xml，与可执行项目所在的位置。 通常情况下，此位置为 \bin\Debug\ 项目目录下。  
  
12. 运行应用程序。 响应消息，Response.xml，保存在应用程序中指定的位置。 响应消息包含的数量或插入的记录，如下所示：  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
      <InsertResult>1</InsertResult>  
    </InsertResponse>  
    ```  
  
     值"1"表示一条记录插入 MS_SAMPLE_EMPLOYEE 表。  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)