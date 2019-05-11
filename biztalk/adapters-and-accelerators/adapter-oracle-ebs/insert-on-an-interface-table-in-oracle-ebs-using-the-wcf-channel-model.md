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
# <a name="run-an-insert-operation-on-an-interface-table-in-oracle-e-business-suite-using-the-wcf-channel-model"></a><span data-ttu-id="936fa-102">Oracle E-business Suite 使用 WCF 通道模型中运行插入操作在界面表</span><span class="sxs-lookup"><span data-stu-id="936fa-102">Run an insert operation on an interface table in Oracle E-Business Suite using the WCF channel model</span></span>
<span data-ttu-id="936fa-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]找到对 Oracle E-business Suite 的接口表的 Insert、 Select、 Update 和 Delete 操作的一组。</span><span class="sxs-lookup"><span data-stu-id="936fa-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers a set of Insert, Select, Update, and Delete operations on Oracle E-Business Suite interface tables.</span></span> <span data-ttu-id="936fa-104">通过使用这些操作，你可以执行简单的 Insert、 Select、 Update 和 Delete 语句限定由 Where 子句对目标接口表。</span><span class="sxs-lookup"><span data-stu-id="936fa-104">By using these operations, you can perform simple Insert, Select, Update, and Delete statements qualified by a Where clause on a target interface table.</span></span> <span data-ttu-id="936fa-105">本主题提供有关如何执行插入操作在界面表使用 WCF 通道模型的说明。</span><span class="sxs-lookup"><span data-stu-id="936fa-105">This topic provides instructions on how to perform an Insert operation on an interface table using the WCF channel model.</span></span>  
  
 <span data-ttu-id="936fa-106">适配器如何支持这些操作的详细信息，请参阅[对界面表和界面视图操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)。</span><span class="sxs-lookup"><span data-stu-id="936fa-106">For more information on how the adapter supports these operations, see [Operations on Interface Tables and Interface Views](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).</span></span> <span data-ttu-id="936fa-107">有关如何执行对 Oracle E-business Suite 使用 WCF 通道模型的操作的详细信息，请参阅[与 Oracle E-business Suite 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="936fa-107">For more information about how to perform operations on Oracle E-Business Suite using the WCF Channel model, see [Overview of the WCF channel model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="936fa-108">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="936fa-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="936fa-109">本主题中的示例执行 MS_SAMPLE_EMPLOYEE 接口表的操作。</span><span class="sxs-lookup"><span data-stu-id="936fa-109">The example in this topic performs operations on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="936fa-110">通过运行这些示例提供的脚本创建表。</span><span class="sxs-lookup"><span data-stu-id="936fa-110">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="936fa-111">有关示例的详细信息，请参阅[适用于 Oracle EBS 适配器示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="936fa-111">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="936fa-112">示例中， **InsertOperation**，后者基于本主题中，还提供与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="936fa-112">A sample, **InsertOperation**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-insert-message"></a><span data-ttu-id="936fa-113">插入消息</span><span class="sxs-lookup"><span data-stu-id="936fa-113">The Insert Message</span></span>  
 <span data-ttu-id="936fa-114">若要对 Oracle E-business Suite 使用 WCF 通道模型执行操作，必须具有特定于操作的请求消息。</span><span class="sxs-lookup"><span data-stu-id="936fa-114">To perform operations on the Oracle E-Business Suite using the WCF channel model, you must have the request message specific to the operation.</span></span> <span data-ttu-id="936fa-115">要执行插入操作 MS_SAMPLE_EMPLOYEE 接口表上的请求消息类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="936fa-115">The request message to perform an Insert operation on the MS_SAMPLE_EMPLOYEE interface table resembles the following:</span></span>  
  
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
  
 <span data-ttu-id="936fa-116">此请求消息将插入以下详细信息的记录：</span><span class="sxs-lookup"><span data-stu-id="936fa-116">This request message inserts a record with following details:</span></span>  
  
```  
Employee Number = 10050  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 <span data-ttu-id="936fa-117">必须将该消息复制到一个文件，例如 InsertRequest.xml。</span><span class="sxs-lookup"><span data-stu-id="936fa-117">You must copy the message to a file, e.g. InsertRequest.xml.</span></span> <span data-ttu-id="936fa-118">此文件使用在此示例中，若要将请求消息发送到 Oracle E-business Suite 使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="936fa-118">This file is used in this example to send the request message to Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="936fa-119">有关对表的操作的消息架构的详细信息，请参阅[Insert、 Update、 Delete 和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="936fa-119">For more information about the message schema for operations on table, see [Message Schemas for Insert, Update, Delete, and Select Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).</span></span>  
  
## <a name="creating-a-wcf-channel-application"></a><span data-ttu-id="936fa-120">创建 WCF 通道应用程序</span><span class="sxs-lookup"><span data-stu-id="936fa-120">Creating a WCF Channel Application</span></span>  
 <span data-ttu-id="936fa-121">本部分将说明了如何创建 WCF 通道应用程序，以执行插入操作上 MS_SAMPLE_EMPLOYEE 接口表。</span><span class="sxs-lookup"><span data-stu-id="936fa-121">This section provides instructions on how to create a WCF channel application to perform an Insert operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-table"></a><span data-ttu-id="936fa-122">若要创建的 WCF 通道应用程序将记录插入到表</span><span class="sxs-lookup"><span data-stu-id="936fa-122">To create a WCF channel application for inserting records into the table</span></span>  
  
1.  <span data-ttu-id="936fa-123">在 Visual Studio 中创建一个 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="936fa-123">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="936fa-124">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="936fa-124">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="936fa-125">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。</span><span class="sxs-lookup"><span data-stu-id="936fa-125">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="936fa-126">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="936fa-126">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="936fa-127">创建绑定和终结点。</span><span class="sxs-lookup"><span data-stu-id="936fa-127">Create the binding and endpoint.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
  
    ```  
  
5.  <span data-ttu-id="936fa-128">由于您正在执行的操作在界面表，必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="936fa-128">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="936fa-129">在此示例中，若要设置应用程序上下文中，您指定**OracleUserName**， **OraclePassword**，并**OracleEBSResponsibilityName**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="936fa-129">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="936fa-130">有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="936fa-130">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
6.  <span data-ttu-id="936fa-131">创建并打开通道工厂。</span><span class="sxs-lookup"><span data-stu-id="936fa-131">Create and open the channel factory.</span></span> <span data-ttu-id="936fa-132">此应用程序将请求消息发送到 Oracle E-business Suite，并接收响应，因此您必须实现 IRequestChannel 接口。</span><span class="sxs-lookup"><span data-stu-id="936fa-132">This application sends request message to Oracle E-Business Suite and receives a response, hence you must implement the IRequestChannel interface.</span></span>  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
7.  <span data-ttu-id="936fa-133">创建并打开通道。</span><span class="sxs-lookup"><span data-stu-id="936fa-133">Create and open the channel.</span></span>  
  
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
  
8.  <span data-ttu-id="936fa-134">创建并发送请求消息。</span><span class="sxs-lookup"><span data-stu-id="936fa-134">Create and send the request message.</span></span>  
  
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
  
     <span data-ttu-id="936fa-135">在创建请求消息时，必须指定指示适配器对界面表执行的操作的消息操作。</span><span class="sxs-lookup"><span data-stu-id="936fa-135">While creating the request message, you must specify the message action that indicates the action that the adapter performs on the interface table.</span></span> <span data-ttu-id="936fa-136">若要执行插入操作 MS_SAMPLE_EMPLOYEE 表上的，消息操作是`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`。</span><span class="sxs-lookup"><span data-stu-id="936fa-136">To perform an Insert operation on the MS_SAMPLE_EMPLOYEE table, the message action is `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`.</span></span> <span data-ttu-id="936fa-137">有关如何确定对表进行各种操作的消息操作的信息，请参阅[Insert、 Update、 Delete 和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="936fa-137">For information about how you can determine the message action for various operations on tables, see [Message Schemas for Insert, Update, Delete, and Select Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).</span></span>  
  
9. <span data-ttu-id="936fa-138">获取响应消息。</span><span class="sxs-lookup"><span data-stu-id="936fa-138">Get the response message.</span></span>  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
10. <span data-ttu-id="936fa-139">关闭消息、 通道和通道工厂。</span><span class="sxs-lookup"><span data-stu-id="936fa-139">Close the message, channel, and channel factory.</span></span>  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
11. <span data-ttu-id="936fa-140">生成项目。</span><span class="sxs-lookup"><span data-stu-id="936fa-140">Build the project.</span></span> <span data-ttu-id="936fa-141">后生成项目时，必须将复制的请求消息，InsertRequest.xml，与可执行项目所在的位置。</span><span class="sxs-lookup"><span data-stu-id="936fa-141">After building the project, you must copy the request message, InsertRequest.xml, at the same location as your project executable.</span></span> <span data-ttu-id="936fa-142">通常情况下，此位置为 \bin\Debug\ 项目目录下。</span><span class="sxs-lookup"><span data-stu-id="936fa-142">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
12. <span data-ttu-id="936fa-143">运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="936fa-143">Run the application.</span></span> <span data-ttu-id="936fa-144">响应消息，Response.xml，保存在应用程序中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="936fa-144">The response message, Response.xml, is saved at the location you specified in the application.</span></span> <span data-ttu-id="936fa-145">响应消息包含的数量或插入的记录，如下所示：</span><span class="sxs-lookup"><span data-stu-id="936fa-145">The response message contains the number or records inserted and resembles the following:</span></span>  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
      <InsertResult>1</InsertResult>  
    </InsertResponse>  
    ```  
  
     <span data-ttu-id="936fa-146">值"1"表示一条记录插入 MS_SAMPLE_EMPLOYEE 表。</span><span class="sxs-lookup"><span data-stu-id="936fa-146">The value “1” denotes that a single record is inserted into the MS_SAMPLE_EMPLOYEE table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936fa-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="936fa-147">See Also</span></span>  
 [<span data-ttu-id="936fa-148">开发 Oracle E-business Suite 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="936fa-148">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)