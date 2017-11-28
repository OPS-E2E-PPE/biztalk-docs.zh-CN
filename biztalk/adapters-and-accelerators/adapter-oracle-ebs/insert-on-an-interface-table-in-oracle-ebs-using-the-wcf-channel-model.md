---
title: "在 Oracle E-business Suite 使用 WCF 通道模型运行接口表上的 insert 操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a2e5ee3-552b-40a2-aaa6-5391347f1146
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703b00adeb373fe66c4a96c324f13f9c3c5ec655
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-an-insert-operation-on-an-interface-table-in-oracle-e-business-suite-using-the-wcf-channel-model"></a><span data-ttu-id="45996-102">在 Oracle E-business Suite 使用 WCF 通道模型运行接口表上的 insert 操作</span><span class="sxs-lookup"><span data-stu-id="45996-102">Run an insert operation on an interface table in Oracle E-Business Suite using the WCF channel model</span></span>
<span data-ttu-id="45996-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]发现一套对 Oracle E-business Suite 接口表的 Insert、 Select、 Update 和 Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="45996-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers a set of Insert, Select, Update, and Delete operations on Oracle E-Business Suite interface tables.</span></span> <span data-ttu-id="45996-104">通过使用这些操作，你可以执行简单的 Insert、 Select、 Update 和 Delete 语句由 Where 限定目标接口表上的子句。</span><span class="sxs-lookup"><span data-stu-id="45996-104">By using these operations, you can perform simple Insert, Select, Update, and Delete statements qualified by a Where clause on a target interface table.</span></span> <span data-ttu-id="45996-105">本主题提供有关如何执行对使用 WCF 通道模型接口表的插入操作的说明。</span><span class="sxs-lookup"><span data-stu-id="45996-105">This topic provides instructions on how to perform an Insert operation on an interface table using the WCF channel model.</span></span>  
  
 <span data-ttu-id="45996-106">有关如何的适配器支持这些操作的详细信息，请参阅[接口表和接口视图上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)。</span><span class="sxs-lookup"><span data-stu-id="45996-106">For more information on how the adapter supports these operations, see [Operations on Interface Tables and Interface Views](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).</span></span> <span data-ttu-id="45996-107">有关如何对 Oracle E-business Suite 使用 WCF 通道模型执行操作的详细信息，请参阅[与 Oracle E-business Suite 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="45996-107">For more information about how to perform operations on Oracle E-Business Suite using the WCF Channel model, see [Overview of the WCF channel model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="45996-108">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="45996-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="45996-109">本主题中的示例对执行 MS_SAMPLE_EMPLOYEE 接口表操作。</span><span class="sxs-lookup"><span data-stu-id="45996-109">The example in this topic performs operations on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="45996-110">通过运行这些示例使用提供的脚本创建表。</span><span class="sxs-lookup"><span data-stu-id="45996-110">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="45996-111">有关示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="45996-111">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="45996-112">示例中， **InsertOperation**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="45996-112">A sample, **InsertOperation**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-insert-message"></a><span data-ttu-id="45996-113">插入消息</span><span class="sxs-lookup"><span data-stu-id="45996-113">The Insert Message</span></span>  
 <span data-ttu-id="45996-114">若要对 Oracle E-business Suite 使用 WCF 通道模型执行操作，你必须使用特定于操作的请求消息。</span><span class="sxs-lookup"><span data-stu-id="45996-114">To perform operations on the Oracle E-Business Suite using the WCF channel model, you must have the request message specific to the operation.</span></span> <span data-ttu-id="45996-115">要执行对 MS_SAMPLE_EMPLOYEE 接口表的插入操作的请求消息如下所示：</span><span class="sxs-lookup"><span data-stu-id="45996-115">The request message to perform an Insert operation on the MS_SAMPLE_EMPLOYEE interface table resembles the following:</span></span>  
  
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
  
 <span data-ttu-id="45996-116">此请求消息将插入以下详细信息的记录：</span><span class="sxs-lookup"><span data-stu-id="45996-116">This request message inserts a record with following details:</span></span>  
  
```  
Employee Number = 10050  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 <span data-ttu-id="45996-117">必须将消息复制到一个文件，例如 InsertRequest.xml。</span><span class="sxs-lookup"><span data-stu-id="45996-117">You must copy the message to a file, e.g. InsertRequest.xml.</span></span> <span data-ttu-id="45996-118">此文件使用在此示例中，将请求消息发送到 Oracle E-business Suite 使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="45996-118">This file is used in this example to send the request message to Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="45996-119">有关对表操作的消息架构的详细信息，请参阅[插入、 更新、 删除和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="45996-119">For more information about the message schema for operations on table, see [Message Schemas for Insert, Update, Delete, and Select Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).</span></span>  
  
## <a name="creating-a-wcf-channel-application"></a><span data-ttu-id="45996-120">创建 WCF 通道应用程序</span><span class="sxs-lookup"><span data-stu-id="45996-120">Creating a WCF Channel Application</span></span>  
 <span data-ttu-id="45996-121">本部分提供有关如何创建一个 WCF 通道应用程序来执行插入操作 MS_SAMPLE_EMPLOYEE 接口表上的说明。</span><span class="sxs-lookup"><span data-stu-id="45996-121">This section provides instructions on how to create a WCF channel application to perform an Insert operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-table"></a><span data-ttu-id="45996-122">若要创建的 WCF 通道应用程序将记录插入到表</span><span class="sxs-lookup"><span data-stu-id="45996-122">To create a WCF channel application for inserting records into the table</span></span>  
  
1.  <span data-ttu-id="45996-123">在 Visual Studio 中创建 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="45996-123">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="45996-124">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="45996-124">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="45996-125">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。</span><span class="sxs-lookup"><span data-stu-id="45996-125">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="45996-126">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="45996-126">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="45996-127">创建绑定和终结点。</span><span class="sxs-lookup"><span data-stu-id="45996-127">Create the binding and endpoint.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
  
    ```  
  
5.  <span data-ttu-id="45996-128">由于您正在执行对接口表的操作，必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="45996-128">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="45996-129">在此示例中，若要设置应用程序上下文中，你指定**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="45996-129">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="45996-130">有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="45996-130">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
6.  <span data-ttu-id="45996-131">创建并打开通道工厂。</span><span class="sxs-lookup"><span data-stu-id="45996-131">Create and open the channel factory.</span></span> <span data-ttu-id="45996-132">此应用程序将请求消息发送到 Oracle E-business Suite 并收到响应，因此必须实现 IRequestChannel 接口。</span><span class="sxs-lookup"><span data-stu-id="45996-132">This application sends request message to Oracle E-Business Suite and receives a response, hence you must implement the IRequestChannel interface.</span></span>  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
7.  <span data-ttu-id="45996-133">创建并打开通道。</span><span class="sxs-lookup"><span data-stu-id="45996-133">Create and open the channel.</span></span>  
  
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
  
8.  <span data-ttu-id="45996-134">创建和发送的请求消息。</span><span class="sxs-lookup"><span data-stu-id="45996-134">Create and send the request message.</span></span>  
  
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
  
     <span data-ttu-id="45996-135">在创建请求消息时，必须指定，该值指示适配器接口表执行的操作的消息操作。</span><span class="sxs-lookup"><span data-stu-id="45996-135">While creating the request message, you must specify the message action that indicates the action that the adapter performs on the interface table.</span></span> <span data-ttu-id="45996-136">若要执行插入操作上 MS_SAMPLE_EMPLOYEE 表，消息操作是`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`。</span><span class="sxs-lookup"><span data-stu-id="45996-136">To perform an Insert operation on the MS_SAMPLE_EMPLOYEE table, the message action is `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`.</span></span> <span data-ttu-id="45996-137">有关如何确定对表的各种操作的消息操作的信息，请参阅[插入、 更新、 删除和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="45996-137">For information about how you can determine the message action for various operations on tables, see [Message Schemas for Insert, Update, Delete, and Select Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).</span></span>  
  
9. <span data-ttu-id="45996-138">获取响应消息。</span><span class="sxs-lookup"><span data-stu-id="45996-138">Get the response message.</span></span>  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
10. <span data-ttu-id="45996-139">关闭消息、 通道和通道工厂。</span><span class="sxs-lookup"><span data-stu-id="45996-139">Close the message, channel, and channel factory.</span></span>  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
11. <span data-ttu-id="45996-140">生成此项目。</span><span class="sxs-lookup"><span data-stu-id="45996-140">Build the project.</span></span> <span data-ttu-id="45996-141">生成项目时，你必须将复制请求消息，InsertRequest.xml，与你的项目可执行文件所在的位置。</span><span class="sxs-lookup"><span data-stu-id="45996-141">After building the project, you must copy the request message, InsertRequest.xml, at the same location as your project executable.</span></span> <span data-ttu-id="45996-142">通常，此位置是项目目录下的 \bin\Debug\。</span><span class="sxs-lookup"><span data-stu-id="45996-142">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
12. <span data-ttu-id="45996-143">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="45996-143">Run the application.</span></span> <span data-ttu-id="45996-144">响应消息，Response.xml，保存应用程序中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="45996-144">The response message, Response.xml, is saved at the location you specified in the application.</span></span> <span data-ttu-id="45996-145">响应消息包含的数或插入的记录，如下所示：</span><span class="sxs-lookup"><span data-stu-id="45996-145">The response message contains the number or records inserted and resembles the following:</span></span>  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
      <InsertResult>1</InsertResult>  
    </InsertResponse>  
    ```  
  
     <span data-ttu-id="45996-146">此值"1"代表一条记录插入 MS_SAMPLE_EMPLOYEE 表。</span><span class="sxs-lookup"><span data-stu-id="45996-146">The value “1” denotes that a single record is inserted into the MS_SAMPLE_EMPLOYEE table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45996-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45996-147">See Also</span></span>  
 [<span data-ttu-id="45996-148">开发 Oracle E-business Suite 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="45996-148">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)