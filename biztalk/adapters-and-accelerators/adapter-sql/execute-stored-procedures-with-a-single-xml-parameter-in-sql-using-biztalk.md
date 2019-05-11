---
title: 在 SQL Server 使用 BizTalk Server 中执行使用单个 XML 参数的存储的过程 |Microsoft Docs
description: 在 BizTalk 中使用 WCF 自定义端口和 SQL 适配器存储过程中传递单个参数
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deb9333a-5e28-4e8d-8e0b-07b5a97a111b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8e1e078be859750e84b729edf93ea7894b5078f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369628"
---
# <a name="execute-stored-procedures-with-a-single-xml-parameter-in-sql-server-using-biztalk-server"></a><span data-ttu-id="33079-103">在 SQL Server 使用 BizTalk Server 中执行使用单个 XML 参数的存储的过程</span><span class="sxs-lookup"><span data-stu-id="33079-103">Execute stored procedures with a single XML parameter in SQL Server using BizTalk Server</span></span>
<span data-ttu-id="33079-104">执行存储的过程采用单个参数是类似于执行任何其他存储的过程中所述[SQL Server 使用 BizTalk Server 中执行存储过程](execute-stored-procedures-in-sql-server-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="33079-104">Executing a stored procedure that takes a single parameter is similar to executing any other stored procedure as described in [Execute Stored Procedures in SQL Server using BizTalk Server](execute-stored-procedures-in-sql-server-using-biztalk-server.md).</span></span> <span data-ttu-id="33079-105">但是，上述链接中所述的方法，你必须在设计时生成存储过程的元数据并创建一个业务流程在运行时调用该过程。</span><span class="sxs-lookup"><span data-stu-id="33079-105">However, for the approach described in the preceding link, you need to generate metadata for the stored procedure at design time and create an orchestration to invoke the procedure at run time.</span></span>  
  
 <span data-ttu-id="33079-106">假设只是想要将一个单一值传递给存储过程，而无需执行任何处理此值。</span><span class="sxs-lookup"><span data-stu-id="33079-106">Consider a scenario where you just want to pass one single value to a stored procedure without doing any processing on that value.</span></span> <span data-ttu-id="33079-107">在这种情况下，您不希望生成元数据、 创建业务流程、 部署业务流程，并执行该操作的开销。</span><span class="sxs-lookup"><span data-stu-id="33079-107">In such cases, you don't want the overhead of generating metadata, creating an orchestration, deploying the orchestration, and executing the operation.</span></span> <span data-ttu-id="33079-108">相反，你可以配置 WCF 自定义或 WCF-SQL 发送端口来直接调用存储的过程。</span><span class="sxs-lookup"><span data-stu-id="33079-108">Rather, you can configure a WCF-Custom or WCF-SQL send port to directly invoke the stored procedure.</span></span> <span data-ttu-id="33079-109">本主题演示如何使用执行这些任务[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="33079-109">This topic demonstrates how to perform these tasks using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33079-110">本主题提供有关如何配置 WCF 自定义发送端口执行采用单个参数的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="33079-110">This topic provides instructions on how to configure a WCF-Custom send port for executing stored procedure that takes a single parameter.</span></span> <span data-ttu-id="33079-111">可以通过配置 WCF SQL 端口执行相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="33079-111">You can perform the same steps by configuring a WCF-SQL port.</span></span> <span data-ttu-id="33079-112">有关如何配置 WCF SQL 端口的说明，请参阅[使用 WCF-SQL 适配器配置端口](configure-a-port-using-the-wcf-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="33079-112">For instructions on configuring WCF-SQL port, see [Configure a Port using the WCF-SQL Adapter](configure-a-port-using-the-wcf-sql-adapter.md).</span></span>  
  
## <a name="invoke-stored-procedures-without-orchestration"></a><span data-ttu-id="33079-113">调用存储的过程，而无需业务流程</span><span class="sxs-lookup"><span data-stu-id="33079-113">Invoke stored procedures without orchestration</span></span>  
 <span data-ttu-id="33079-114">若要演示如何执行存储的过程使用单个参数而无需业务流程，本主题使用 ADD_LAST_EMP_XML_INFO 存储过程。</span><span class="sxs-lookup"><span data-stu-id="33079-114">To demonstrate how to execute stored procedures with single parameters without an orchestration, this topic uses the ADD_LAST_EMP_XML_INFO stored procedure.</span></span> <span data-ttu-id="33079-115">此过程采用 XML 值作为参数，并将其插入到**地址**的列**员工**表。</span><span class="sxs-lookup"><span data-stu-id="33079-115">This procedure takes an XML value as a parameter and inserts it into the **Address** column of the **Employee** table.</span></span> <span data-ttu-id="33079-116">必须具有 XML 值将传递给存储过程。</span><span class="sxs-lookup"><span data-stu-id="33079-116">You must have the XML value that you will pass to the stored procedure.</span></span> <span data-ttu-id="33079-117">但是，若要执行存储的过程使用的适配器，必须将发送请求消息的过程的架构符合和包含的 XML 值**地址**字段中，为 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="33079-117">However, to execute the stored procedure using the adapter, you must send a request message conforming to the schema of the procedure, and containing the XML value for the **Address** field, to the SQL Server.</span></span> <span data-ttu-id="33079-118">因此，必须创建由该请求消息：</span><span class="sxs-lookup"><span data-stu-id="33079-118">So, you must create that request message by:</span></span>  
  
- <span data-ttu-id="33079-119">使用**模板**中使用可创建使用消息模板的请求消息的发送端口配置选项。</span><span class="sxs-lookup"><span data-stu-id="33079-119">Using the **Template** option in the send port configuration using which you can create a request message using a message template.</span></span>  
  
- <span data-ttu-id="33079-120">将 XML 值**地址**字段到消息。</span><span class="sxs-lookup"><span data-stu-id="33079-120">Putting the XML value for the **Address** field into the message.</span></span>  
  
  <span data-ttu-id="33079-121">本主题中详细介绍所有这些步骤。</span><span class="sxs-lookup"><span data-stu-id="33079-121">All these steps are described in detail in this topic.</span></span> <span data-ttu-id="33079-122">您必须执行以下一组任务：</span><span class="sxs-lookup"><span data-stu-id="33079-122">You must perform the following set of tasks:</span></span>  
  
1. <span data-ttu-id="33079-123">创建文件接收的端口将插入到 XML 文件将存放**地址**的 XML 字段**员工**表。</span><span class="sxs-lookup"><span data-stu-id="33079-123">Create a FILE receive port where you will drop the XML file that will be inserted into the **Address** XML field of the **Employee** table.</span></span> <span data-ttu-id="33079-124">假设此端口被称为**MessageIn**端口。</span><span class="sxs-lookup"><span data-stu-id="33079-124">Suppose this port is called **MessageIn** port.</span></span>  
  
2. <span data-ttu-id="33079-125">创建一个 WCF 自定义单向发送端口提取 XML 文件从文件接收端口、 构造消息使用消息模板，并将其发送到 SQL Server 以执行该存储的过程。</span><span class="sxs-lookup"><span data-stu-id="33079-125">Create a WCF-Custom one-way send port that picks the XML file from the FILE receive port, constructs the message using the message template, and sends it to SQL Server to execute the stored procedure.</span></span>  
  
   <span data-ttu-id="33079-126">主题的此部分介绍如何配置 WCF 自定义发送端口与消息模板。</span><span class="sxs-lookup"><span data-stu-id="33079-126">This part of the topic provides instructions on configuring a WCF-Custom send port with the message template.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33079-127">尽管本主题中的信息演示如何执行存储的过程与单个 XML 参数，可以执行的任务执行任何操作，采用单个参数的任何数据类型。</span><span class="sxs-lookup"><span data-stu-id="33079-127">Even though the information in this topic demonstrates how to execute a stored procedure with a single XML parameter, you can perform the tasks to perform any operation that takes a single parameter of any data type.</span></span> <span data-ttu-id="33079-128">唯一的区别是在创建针对特定操作的消息模板的方式。</span><span class="sxs-lookup"><span data-stu-id="33079-128">The only difference will be in the way you create a message template for a specific operation.</span></span> <span data-ttu-id="33079-129">可以通过将使用以执行此操作的请求消息创建的消息模板使用业务流程和参数的值替换为 BizTalk 消息正文。</span><span class="sxs-lookup"><span data-stu-id="33079-129">You can create a message template by taking the request message you would use to execute the operation using an orchestration and replacing the value of the parameter with the BizTalk message body.</span></span>  
  
##  <a name="BKMK_OneWay"></a> <span data-ttu-id="33079-130">配置 Wcf-custom 发送端口</span><span class="sxs-lookup"><span data-stu-id="33079-130">Configure a WCF-Custom send port</span></span>  
 <span data-ttu-id="33079-131">创建 WCF 自定义之前发送端口，请确保已创建文件接收端口中， **MessageIn**。</span><span class="sxs-lookup"><span data-stu-id="33079-131">Before creating the WCF-Custom send port, make sure you created the FILE receive port, **MessageIn**.</span></span>  
  
1. <span data-ttu-id="33079-132">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="33079-132">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="33079-133">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="33079-133">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="33079-134">展开你想要部署的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="33079-134">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
4. <span data-ttu-id="33079-135">右键单击**发送端口**，依次指向**新建**，然后指向**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="33079-135">Right-click **Send Ports**, point to **New**, and then point to **Static One-way Send Port**.</span></span>  
  
5. <span data-ttu-id="33079-136">在中**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="33079-136">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6. <span data-ttu-id="33079-137">配置端口以接收所有消息在该文件删除接收端口中， **MessageIn**。</span><span class="sxs-lookup"><span data-stu-id="33079-137">Configure the port to receive all messages dropped at the FILE receive port, **MessageIn**.</span></span>  
  
   1.  <span data-ttu-id="33079-138">在中**发送端口属性**对话框中，从左窗格中，单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="33079-138">In the **Send Port Properties** dialog box, from the left pane, click **Filters**.</span></span>  
  
   2.  <span data-ttu-id="33079-139">在右窗格中下,**属性**列中，单击网格中，并选择**BTS。ReceivePortName**属性。</span><span class="sxs-lookup"><span data-stu-id="33079-139">In the right pane, under the **Property** column, click the grid, and then select **BTS.ReceivePortName** property.</span></span>  
  
   3.  <span data-ttu-id="33079-140">有关**运算符**列中，选择"**==**"。</span><span class="sxs-lookup"><span data-stu-id="33079-140">For the **Operator** column, select “**==**”.</span></span>  
  
   4.  <span data-ttu-id="33079-141">有关**值**列中，指定的文件的名称的接收端口， `MessageIn`。</span><span class="sxs-lookup"><span data-stu-id="33079-141">For the **Value** column, specify the name of the FILE receive port, `MessageIn`.</span></span>  
  
7. <span data-ttu-id="33079-142">在中**发送端口属性**对话框中，在**常规**选项卡上，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="33079-142">In the **Send Port Properties** dialog box, on the **General** tab, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="33079-143">在中**Wcf-custom 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="33079-143">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="33079-144">单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定 SQL Server 的连接 URI。</span><span class="sxs-lookup"><span data-stu-id="33079-144">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for SQL Server.</span></span> <span data-ttu-id="33079-145">有关连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="33079-145">For more information about the connection URI, see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="33079-146">上**常规**选项卡上，在**操作**文字框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="33079-146">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="33079-147">请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)有关每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="33079-147">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) for a list of actions for each operation.</span></span> <span data-ttu-id="33079-148">例如，要调用 ADD_LAST_EMP_XML_INFO 的操作是：</span><span class="sxs-lookup"><span data-stu-id="33079-148">For example, the action to invoke the ADD_LAST_EMP_XML_INFO is:</span></span>  
  
      ```  
      Procedure/dbo/ADD_LAST_EMP_XML_INFO  
      ```  
  
   3. <span data-ttu-id="33079-149">单击**绑定**选项卡上，并从**绑定类型**列表中，选择**sqlBinding**。</span><span class="sxs-lookup"><span data-stu-id="33079-149">Click the **Binding** tab, and from the **Binding Type** list, select **sqlBinding**.</span></span> <span data-ttu-id="33079-150">您可以指定不同的绑定属性公开的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="33079-150">You can specify the different binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="33079-151">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="33079-151">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
   4. <span data-ttu-id="33079-152">单击**凭据**选项卡，然后再执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="33079-152">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
      -   <span data-ttu-id="33079-153">选择**不使用单一登录**选项，以及指定的用户名和密码以连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="33079-153">Select the **Do not use Single Sign-On** option, and the specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="33079-154">请注意，用户名和密码是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="33079-154">Note that the user name and password are case-sensitive.</span></span>  
  
          > [!NOTE]
          >  <span data-ttu-id="33079-155">如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="33079-155">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span>  
  
      -   <span data-ttu-id="33079-156">选择**使用单一登录**选项，，然后指定附属机构企业单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="33079-156">Select the **Use Single Sign-On** option, and then specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
           <span data-ttu-id="33079-157">有关与 BizTalk Server 相关的安全性的详细信息，请参阅[SQL 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="33079-157">For more information about security with respect to BizTalk Server, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>
  
   5. <span data-ttu-id="33079-158">单击**消息**选项卡上，然后在**出站 WCF 消息正文**部分中，选择**模板**选项。</span><span class="sxs-lookup"><span data-stu-id="33079-158">Click the **Messages** tab, and in the **Outbound WCF message body** section, choose the **Template** option.</span></span>  
  
   6. <span data-ttu-id="33079-159">在中**XML**文字框中，指定将用于构造 WCF 消息的模板。</span><span class="sxs-lookup"><span data-stu-id="33079-159">In the **XML** text box, specify the template that will be used to construct the WCF message.</span></span> <span data-ttu-id="33079-160">通过此操作，创建一条消息，符合基于 WCF 的 ADD_LAST_EMP_XML_INFO 操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="33079-160">By doing so, you create a message that conforms to the ADD_LAST_EMP_XML_INFO operation for the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
       <span data-ttu-id="33079-161">![指定出站 WCF 消息的模板](../../adapters-and-accelerators/adapter-sql/media/012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55.gif "012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55")</span><span class="sxs-lookup"><span data-stu-id="33079-161">![Specify template for outbound WCF message](../../adapters-and-accelerators/adapter-sql/media/012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55.gif "012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55")</span></span>  
  
       <span data-ttu-id="33079-162">有关 ADD_LAST_EMP_XML_INFO 存储过程中，您必须指定以下模板：</span><span class="sxs-lookup"><span data-stu-id="33079-162">For the ADD_LAST_EMP_XML_INFO stored procedure, you must specify the following template:</span></span>  
  
      ```  
      <ADD_LAST_EMP_XML_INFO xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
      <xml_info>  
      <bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/>  
      </xml_info>  
      </ADD_LAST_EMP_XML_INFO>  
      ```  
  
      > [!IMPORTANT]
      >  <span data-ttu-id="33079-163">消息模板中的编码必须始终为"string"而不考虑将使用发送端口调用的操作参数的类型。</span><span class="sxs-lookup"><span data-stu-id="33079-163">The encoding in the message template must always be “string” irrespective of the type of the parameter for the operation that will be invoked using the send port.</span></span> <span data-ttu-id="33079-164">例如，ADD_LAST_EMP_XML_INFO 采用一个参数的类型为 XML，但在消息模板中编码为字符串。</span><span class="sxs-lookup"><span data-stu-id="33079-164">For example, the ADD_LAST_EMP_XML_INFO takes a parameter of type XML, but the encoding in the message template is string.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="33079-165">可以通过复制存储过程的请求消息并使用 BizTalk 消息正文替换 < xml_info > 标记内的值来创建此消息模板。</span><span class="sxs-lookup"><span data-stu-id="33079-165">You can create this message template by copying the request message for the stored procedure and replacing the value within the <xml_info> tags with the BizTalk message body.</span></span> <span data-ttu-id="33079-166">可以通过生成过程使用的架构的存储过程获取请求消息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，然后生成要获取请求 XML 的架构的实例。</span><span class="sxs-lookup"><span data-stu-id="33079-166">You can get the request message for the stored procedure by generating the schema for the procedure using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], and then generating an instance of the schema to get the request XML.</span></span>  
  
   7. <span data-ttu-id="33079-167">若要返回到**发送端口属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="33079-167">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="33079-168">从**发送处理程序**列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="33079-168">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="33079-169">从**发送管道**列表中，选择对应于管道**PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="33079-169">From the **Send pipeline** list, select the pipeline that corresponds to **PassThruTransmit**.</span></span>  
  
11. <span data-ttu-id="33079-170">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="33079-170">Click **OK**.</span></span>  
  
## <a name="start-the-application"></a><span data-ttu-id="33079-171">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="33079-171">Start the Application</span></span>  
 <span data-ttu-id="33079-172">若要启动的 BizTalk 应用程序，可以启动这两个文件接收位置和 WCF 自定义单独发送端口。</span><span class="sxs-lookup"><span data-stu-id="33079-172">To start the BizTalk application, you can start both the FILE receive location and the WCF-Custom send port individually.</span></span> <span data-ttu-id="33079-173">你必须现在复制该文件夹映射到该文件的 XML 文件接收位置。</span><span class="sxs-lookup"><span data-stu-id="33079-173">You must now copy an XML file to the folder mapped to the FILE receive location.</span></span> <span data-ttu-id="33079-174">BizTalk 应用程序使用该文件，并在 Employee 表的地址列中插入的 XML 值。</span><span class="sxs-lookup"><span data-stu-id="33079-174">The BizTalk application consumes the file, and the XML value is inserted in the Address column of the Employee table.</span></span> <span data-ttu-id="33079-175">可以通过使用 SQL Server 客户端并从 Employee 表中选择记录对此进行验证。</span><span class="sxs-lookup"><span data-stu-id="33079-175">You can verify this by using a SQL Server client and selecting records from the Employee table.</span></span>  
  
## <a name="using-a-two-way-wcf-custom-send-port"></a><span data-ttu-id="33079-176">使用双向 WCF 自定义发送端口</span><span class="sxs-lookup"><span data-stu-id="33079-176">Using a Two-way WCF-Custom Send Port</span></span>  
 <span data-ttu-id="33079-177">本主题中下一节, 中的说明[如何配置 Wcf-custom 发送端口](../../core/how-to-configure-a-wcf-custom-send-port.md)，演示了如何配置用于执行带一个参数的存储的过程，而不使用 BizTalk 的单向 WCF 自定义发送端口业务流程。</span><span class="sxs-lookup"><span data-stu-id="33079-177">The instructions in this topic, under the section [How to Configure a WCF-Custom Send Port](../../core/how-to-configure-a-wcf-custom-send-port.md), demonstrate how to configure a one-way WCF-Custom send port to execute a stored procedure with a single parameter without using a BizTalk orchestration.</span></span> <span data-ttu-id="33079-178">但是，在这种情况下，若要验证是否执行该存储的过程已成功将必须验证 SQL Server 数据库中是否更新员工表中的地址列。</span><span class="sxs-lookup"><span data-stu-id="33079-178">However, in such a case, to verify whether the stored procedure is executed successfully you will have to verify in the SQL Server database whether the Address column in the Employee table is updated.</span></span>  
  
 <span data-ttu-id="33079-179">相反，您可以创建双向 Wcf-custom 发送端口还从 SQL Server 获取响应，如果成功执行存储的过程。</span><span class="sxs-lookup"><span data-stu-id="33079-179">Instead, you can create a two-way WCF-Custom send port that also gets the response from SQL Server if the stored procedure is executed successfully.</span></span> <span data-ttu-id="33079-180">如果创建一个双向的 WCF 自定义端口，则必须执行一些附加步骤。</span><span class="sxs-lookup"><span data-stu-id="33079-180">You must perform a few additional steps if you create a two-way WCF-Custom port.</span></span> <span data-ttu-id="33079-181">请注意，您仍需要一个文件接收位置，如前面的说明中所述。</span><span class="sxs-lookup"><span data-stu-id="33079-181">Note that you will still need a FILE receive location, as mentioned in the preceding instructions.</span></span>  
  
1. <span data-ttu-id="33079-182">例如，创建一个双向的 Wcf-custom 发送端口， **ExecProcedure**。</span><span class="sxs-lookup"><span data-stu-id="33079-182">Create a two-way WCF-Custom send port, for example, **ExecProcedure**.</span></span> <span data-ttu-id="33079-183">若要配置的发送端口的步骤是类似于单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="33079-183">The steps to configure the send port are similar to those for the one-way send port.</span></span> <span data-ttu-id="33079-184">唯一的区别是双向的端口，还必须指定接收管道。</span><span class="sxs-lookup"><span data-stu-id="33079-184">The only difference is that for the two-way port you must also specify a receive pipeline.</span></span> <span data-ttu-id="33079-185">请确保选择**PassThruReceive**接收管道。</span><span class="sxs-lookup"><span data-stu-id="33079-185">Make sure you select **PassThruReceive** for the receive pipeline.</span></span>  
  
2. <span data-ttu-id="33079-186">创建 FILE 发送端口。</span><span class="sxs-lookup"><span data-stu-id="33079-186">Create a FILE send port.</span></span> <span data-ttu-id="33079-187">此端口将响应消息从数据库中删除 SQL Server 到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="33079-187">This port will drop the response message from the SQL Server database to a folder.</span></span> <span data-ttu-id="33079-188">使用**筛选器**选项卡的端口属性对话框中，配置 FILE 发送端口以接收来自 WCF 自定义发送端口的所有响应消息。</span><span class="sxs-lookup"><span data-stu-id="33079-188">Using the **Filters** tab of the port properties dialog box, configure the FILE send port to receive all response messages from the WCF-Custom send port.</span></span>  
  
   1.  <span data-ttu-id="33079-189">在中**发送端口属性**对话框中，从左窗格中，单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="33079-189">In the **Send Port Properties** dialog box, from the left pane, click **Filters**.</span></span>  
  
   2.  <span data-ttu-id="33079-190">在右窗格中下,**属性**列中，单击网格中，并选择**BTS。SPName**属性。</span><span class="sxs-lookup"><span data-stu-id="33079-190">In the right pane, under the **Property** column, click the grid, and then select **BTS.SPName** property.</span></span>  
  
   3.  <span data-ttu-id="33079-191">有关**运算符**列中，选择"**==**"。</span><span class="sxs-lookup"><span data-stu-id="33079-191">For the **Operator** column, select “**==**”.</span></span>  
  
   4.  <span data-ttu-id="33079-192">有关**值**列中，指定发送端口的 WCF 自定义名称`ExecProcedure`。</span><span class="sxs-lookup"><span data-stu-id="33079-192">For the **Value** column, specify the name of the WCF-Custom send port, `ExecProcedure`.</span></span>  
  
   <span data-ttu-id="33079-193">启动所有三个端口。</span><span class="sxs-lookup"><span data-stu-id="33079-193">Start all the three ports.</span></span> <span data-ttu-id="33079-194">复制文件夹映射到该文件的 XML 文件接收位置。</span><span class="sxs-lookup"><span data-stu-id="33079-194">Copy an XML file to the folder mapped to the FILE receive location.</span></span> <span data-ttu-id="33079-195">查找映射到 FILE 发送端口的文件夹中的响应。</span><span class="sxs-lookup"><span data-stu-id="33079-195">Look for the response in the folder mapped to the FILE send port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33079-196">请参阅</span><span class="sxs-lookup"><span data-stu-id="33079-196">See Also</span></span>  
[<span data-ttu-id="33079-197">使用 SQL 适配器开发 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="33079-197">Develop BizTalk applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)