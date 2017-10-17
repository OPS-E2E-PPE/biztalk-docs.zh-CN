---
title: "演练： 发布 WCF 服务与 WCF NetMsmq 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e623b6dc-32e5-467c-bb7d-68b7a75723c1
caps.latest.revision: "46"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38530cfdbde78e96fb41093c79b6a5d1bb8fd132
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2017
---
# <a name="walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter"></a>演练： 使用 WCF NetMsmq 适配器的 WCF 服务发布
  
> [!NOTE]
>  有关适配器的详细信息，请参阅[BizTalk Server 中的适配器](../core/adapters-in-biztalk-server.md)。  
  
## <a name="introduction"></a>简介
  
 在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 中，业务流程可以作为 [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 服务发布。 通过 BizTalk 接收位置，业务流程可以公开 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 终结点，以允许由 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 客户端进行调用。 **BizTalk WCF 服务发布向导**提供一种简单的方法来公开作为接收位置业务流程。  
  
 WCF NetMsmq 适配器使用**NetMsmqBinding**绑定以支持使用 Microsoft 消息队列 (也称为 MSMQ) 作为其基础传输。 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的客户端使用配置为使用 WCF-NetMSMQ 适配器的接收位置，将 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 消息发送到 MSMQ 队列。 该适配器从 MSMQ 队列提取 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 消息，将其转换成 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 格式，然后再写入到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox 数据库。  
  
 本演练将说明 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 客户端控制台应用程序如何通过 MSMQ 消息队列，使用 WCF-NetMsmq 适配器与 .NET 控制台应用程序中承载的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务进行通信。 演示了如何使用 BizTalk WCF 服务发布向导为接收位置发布元数据。 它还演示如何配置 Web 应用程序以支持发布元数据。  
  
 在完成本演练后，你将了解如何执行以下任务：  
  
-   在 Visual Studio 中使用**部署**命令将 BizTalk 程序集部署到的本地实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这将创建一个用这些程序集填充的 BizTalk 应用程序。 BizTalk 程序集将包含各种资源信息，例如要在 BizTalk 解决方案中使用的业务流程、管道、架构和映射。  
  
-   在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，配置 WCF-NetMsmq 接收位置以承载已发布的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务。  
  
-   从**BizTalk WCF 服务发布向导**，创建 Web 应用程序，以将发布元数据的现有接收位置。 该元数据由向接收位置提交消息的客户端使用。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本示例中的步骤，请确保你的环境中安装了以下必备软件：  
  
-   这两个的程序集将生成并运行部署过程中，并运行此示例中的计算机的计算机需要 Microsoft Windows Server、.NET Framework 和 BizTalk Server。  
  
-   用于构建程序集和运行部署过程的计算机需要安装 Microsoft Visual Studio。  
  
-   运行示例的计算机需要 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 适配器和 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理工具。 这些是 Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 安装过程中安装的选件。  
  
-   在用于执行管理任务的计算机上，你必须使用作为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的用户帐户运行，才能在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台内配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序设置。 此用户帐户还必须是本地管理员组的成员，才能部署应用程序，管理主机实例以及其他可能需要的任务。  
  
-   需要的任何计算机上[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]功能，完成的一次性安装过程[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]示例在[http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510)。  
  
-   在运行示例并将绑定或 .msi 文件导入 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上，确保主机不是受信任主机，否则导入将失败。  
  
-   你必须下载演练代码并将其解压缩到你的计算机。 本演练是整个的一部分[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]适配器演练包。 你可以下载该文件**WCFAdapterWalkthroughs.exe**从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员中心， [http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140)。  
  
## <a name="build-and-deploy-the-biztalk-solution-biztalkapp"></a>生成和部署 BizTalk 解决方案，BizTalkApp  
  
1.  提取到 WCFNetMsmqAdapterPublishing.exe **C:\WCFNetMsmqAdapterPublishing**。  
  
2.  在 Visual Studio 中，打开**WCFNetMsmqAdapterPublishing.sln**文件。  
  
3.  在解决方案资源管理器，展开**BizTalkApp**，然后打开**OrderProcess.odx**查看。 示例业务流程接收订单请求消息，但只返回订单响应消息。  
  
4.  因为**BizTalkApp**程序集必须安装到 GAC 中，它将需要一个强名称密钥文件，以完成部署过程。 右键单击**BizTalkApp**项目，，然后单击**属性**。 上**属性**页上，单击**签名**，然后选择**对程序集签名**。 单击中的向下箭头**选择强名称密钥文件**下拉列表中，单击**\<新建 >**并输入`keyfile.snk`中**密钥文件名称**文本框。 取消选中**保护我使用密码的密钥文件**，然后单击**确定**。  
  
5.  单击**部署**选项卡上，然后更改**服务器**属性如果除了 BizTalk 管理数据库使用不同的数据库服务器**LOCALHOST**。  确保**BizTalk 应用程序**值设置为**WCFNetMsmqAdapterPublishing**。 确保**安装到全局程序集缓存**设置为**True**。  
  
6.  在解决方案资源管理器，右键单击**BizTalkApp**项目，然后单击**重新生成**。  
  
7.  在解决方案资源管理器，右键单击**BizTalkApp**，然后单击**部署**。  
  
## <a name="configure-the-application"></a>配置应用程序  
  
1.  确保按如下方式将 Microsoft 消息队列 (MSMQ) 组件安装在您的计算机上：  
  
    1.  单击**启动**，右键单击**计算机**，然后单击**管理**以打开**服务器管理器**。  
  
    2.  展开**功能**节点。  如果**消息队列**是未安装，请右键单击**功能**，然后选择**添加功能**。 检查**消息队列**，单击**下一步**，然后单击**安装**该系统上安装 MSMQ。  
  
2.  按照以下方法确保在您的计算机上启动 MSMQ 消息队列，以供 WCF-NetMsmq 适配器使用：  
  
    1.  单击**启动**，指向**管理工具**，然后单击**服务**。  
  
    2.  在**服务**，请确保**状态**的**消息队列**服务是**已启动**。 如果服务未启动，请右键单击**消息队列**，然后单击**启动**。  
  
3.  创建接收位置使用的目标队列，WCF-NetMsmq 适配器从中提取来自客户端的传入 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 消息。  
  
    1.  单击**启动**，指向**管理工具**，然后单击**计算机管理**。  
  
    2.  在**计算机管理**，展开**服务和应用程序**，展开**消息队列**，右键单击**专用队列**，指向**新建**，然后单击**专用队列**。  
  
    3.  在**新的专用队列**对话框中，键入`WCFNetMsmqAdapterPublishing`中**队列名称**文本框中，选择**事务**复选框，并依次**确定**.  
  
4.  创建 WCF NetMsmq 接收示例应用程序的位置，如下所示：  
  
    1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
    2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开**应用程序**，展开**WCFNetMsmqAdapterPublishing**，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**  
  
    3.  在**接收端口属性**对话框中，在**名称**文本框中，键入`WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder`，然后单击**确定**。  
  
    4.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder**，指向**新建**，然后单击**接收位置**.  
  
    5.  在**接收位置属性**对话框中，在**名称**文本框中，键入`WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder.NetMsmq`。  
  
    6.  在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**WCF NetMsmq**从下拉列表，然后单击**配置**。  
  
    7.  在**WCF NetMsmq 传输属性**对话框中，在**常规**选项卡上，在**地址 (URI)**文本框中，键入`net.msmq://localhost/private/WCFNetMsmqAdapterPublishing`。  
  
    8.  在**WCF NetMsmq 传输属性**对话框中，在**绑定**选项卡上，请确保**事务**复选框处于选中状态。  
  
        > [!NOTE]
        >  由于在创建目标队列为事务性队列，你必须选中此复选框。 如果未选中此框，接收位置将不启用由于接收位置的事务要求和的基础的 MSMQ 队列之间将有差异。  
  
    9. 在**WCF NetMsmq 传输属性**对话框中，在**安全**选项卡上，选择**无**从**安全模式**下拉列表.  
  
        > [!NOTE]
        >  本演练假定 MSMQ 已安装，且计算机禁用 [!INCLUDE[btsAD](../includes/btsad-md.md)] 集成。 默认值， **WindowsDomain**，为**MSMQ 身份验证模式**时，属性均可用[!INCLUDE[btsAD](../includes/btsad-md.md)]启用集成。  
  
    10. 在**接收位置属性**对话框中，单击**确定**。  
  
5.  为示例应用程序创建 FILE 发送端口。 此端口用于路由来自服务的基础业务流程采购定单的响应。  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFNetMsmqAdapterPublishing**，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
    2.  在**发送端口属性**对话框中，在**名称**文本框中，键入`WCFNetMsmqAdapterPublishing.SendPurchaseOrder.File`。  
  
    3.  在**发送端口属性**对话框中，在**传输**旁边部分**类型**，选择**文件**从下拉列表中，然后单击**配置**。  
  
    4.  在**文件传输属性**对话框中，在**常规**选项卡上，在**目标文件夹**文本框中，键入`C:\WCFNetMsmqAdapterPublishing\Out`，然后单击**确定**.  
  
    5.  在**发送端口属性**对话框中，单击**确定**。  
  
6.  指定的主机名和示例应用程序的绑定，如下所示：  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**WCFNetMsmqAdapterPublishing**，展开**业务流程**，右键单击示例业务流程，单击**属性**，单击**绑定**，并设置**主机**到**BizTalkServerApplication**或另一个适当的主机。  
  
    2.  在**业务流程属性**对话框中，选择**WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder**从**接收端口**的下拉列表**PurchaseOrderRequestPort**。  
  
    3.  在**业务流程属性**对话框中，选择**WCFNetMsmqAdapterPublishing.SendPurchaseOrder.File**从**发送端口/发送端口组**下拉列表有关**PurchaseOrderResponsePort**。  
  
    4.  在**业务流程属性**对话框中，单击**确定**保存配置。  
  
## <a name="publish-the-metadata-for-the-wcf-netmsmq-receive-location"></a>发布元数据，为 WCF NetMsmq 接收位置  
  
1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk WCF 服务发布向导**。  
  
2.  上**BizTalk WCF 服务发布向导欢迎**页上，单击**下一步**。  
  
3.  上**WCF 服务类型**页上，选择**元数据仅终结点 (MEX)**复选框以将发布元数据以供 WCFNetMsmq 接收位置。 选择**WCFNetMsmqAdapterPublishing.ReceivePurchaseOrder.NetMsmq**从**发布元数据接收位置**下拉列表，然后单击**下一步**。  
  
4.  上**创建 WCF 服务**页上，选择**作为 WCF 服务发布 BizTalk 业务流程**，然后单击**下一步**。  
  
5.  上**BizTalk 程序集**页上，在**BizTalk 程序集文件 (\*.dll)**文本框中，单击**浏览**以浏览到**C:\WCFNetMsmqAdapterPublishing\BizTalkApp\bin\Development**文件夹中，双击包含示例业务流程的程序集以发布，然后单击**下一步**。  
  
6.  上**业务流程和端口**页上，请确保**端口： PurchaseOrderRequestPort**节点在页上，选择，再单击**下一步**。  
  
     客户端将发布接收端口的 MEX，并用它来向接收位置提交消息。  
  
7.  上**WCF 服务属性**页上，在**的 WCF 服务的目标命名空间**文本框中，键入你希望此已发布的 URI[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务要使用，并依次**下一步**. 对于本演练中，保留默认 URI， `http://tempuri.org/`。  
  
8.  上**WCF 服务位置**页上，执行以下操作来指定的位置[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务来创建，然后单击**下一步**:  
  
    1.  在**位置**文本框中，键入 Web 目录名称[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务运行，或单击**浏览**并选择 Web 目录。 对于本演练中，保留默认位置 (http://localhost/*\<BizTalk 程序集名称 >*) 中**位置**文本框。  
  
    2.  选择**允许匿名访问 WCF 服务**选项。 此选项会为已创建的虚拟目录添加匿名访问权限。 此选项需要选择以允许为此向导将创建 Web 应用程序的匿名身份验证。  
  
9. 上**WCF 服务摘要**页上，单击**创建**创建[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。  
  
10. 上**完成 BizTalk WCF 服务发布向导**页上，单击**完成**。  
  
## <a name="configure-the-web-application-hosting-the-published-metadata-service"></a>配置托管已发布的元数据服务的 Web 应用程序  
  
1.  打开命令提示符处，转到**C:\inetpub\wwwroot\Microsoft.Samples.BizTalk.WCF.NetMsmqPublishing.BizTalkApp**文件夹其中**BizTalk WCF 服务发布向导**创建[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务。 打开**Web.config**文件中使用记事本。  
  
2.  在记事本中，添加以下代码行内的 **\<.w e b >**元素：  
  
    ```  
    <trust level="Full" originUrl="" />  
    ```  
  
    > [!NOTE]
    >  此设置是可选的。 此设置向已发布了 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的宿主 ASP.NET 应用程序授予对受操作系统安全机制保护的任何资源的访问权限。  
  
3.  测试已发布[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务通过 Internet Explorer，如下所示：  
  
    1.  单击**启动**，指向**管理员工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
    2.  在 IIS 管理器中，创建一个拥有正确 BizTalk 数据库权限的应用程序池，此服务将在其中运行。 右键单击**应用程序池**，单击**添加应用程序池**，输入应用程序池的名称，然后单击**确定**。  
  
    3.  展开**应用程序池**，右键单击你刚的应用程序池创建，，然后选择**高级设置**。 下**进程模型**部分中，输入可以访问的帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库下**标识**字段。  
  
    4.  展开**网站**，展开**Default Web Site**，然后展开 BizTalk WCF 服务发布向导创建的 Web 应用程序。  
  
    5.  在 IIS 管理器中，在中心窗格中，单击**内容视图**以显示应用程序的文件。  
  
    6.  右键单击**Microsoft_Samples_BizTalk_WCF_NetMsmqPublishing_BizTalkApp_OrderProcess_PurchaseOrderRequestPort.svc**服务文件**BizTalk WCF 服务发布向导**创建，并依次**浏览**。 这将打开 Internet Explorer 显示**BizTalkServerInstance 服务**指示的页的实例[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务正在运行。 页会显示完整的 WSDL 地址，你可以复制和使用的服务元数据工具 (svcutil.exe)，或从 Visual Studio 中，检索代理代码和配置文件可以用于创建服务的客户端应用程序。  
  
    7.  在命令行从完整的 WSDL 地址复制到剪贴板**BizTalkServerInstance 服务**Internet 资源管理器显示上一步中的页。  
  
         **svcutil.exe http://localhost/Microsoft.Samples.BizTalk.WCF.NetMsmqPublishing.BizTalkApp/Microsoft_Samples_BizTalk_WCF_NetMsmqPublishing_BizTalkApp_OrderProcess_PurchaseOrderRequestPort.svc?wsdl**  
  
## <a name="build-the-client-application"></a>生成客户端应用程序  
  
1.  打开 Visual Studio 命令提示符以管理员身份并转到**C:\WCFNetMsmqAdapterPublishing\WCFClient**文件夹。 这是放置代理类和应用程序配置文件的位置。  
  
2.  粘贴包含您在上一过程中复制的整个 WSDL 地址的完整 svcutil.exe 命令行，然后按 Enter。 这将创建代理类中， **BizTalkServiceInstance.cs**，和应用程序配置文件， **output.config**。保持命令提示符窗口打开以供最后一部分使用。  
  
3.  在 Visual Studio 中，在解决方案资源管理器，右键单击**WCFClient**，指向**添加**，然后单击**现有项**。  
  
4.  在**添加现有项**对话框中，浏览到**WCFClient**文件夹，选择**所有文件 (\*。\*)**中**类型的文件**下拉列表中，选择**BizTalkServiceInstance.cs**和**output.config**文件，并依次**添加**。  
  
5.  展开**WCFClient**，右键单击**output.config**，单击**重命名**，然后键入`App.config`作为新的名称。  
  
6.  双击**Program.cs**若要查看如何调用已发布[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务中使用 svcutil.exe 生成的代理类。  
  
7.  展开**引用**，那么请确保和**WCFClient**项目具有**System.ServiceModel.dll**引用。  
  
8.  右键单击**WCFClient**项目，然后选择**生成**。 保持 Visual Studio 的打开状态并转到下一节。  
  
## <a name="test-the-sample-solution-with-the-wcf-netmsmq-adapter"></a>测试与 WCF NetMsmq 适配器的示例解决方案  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**WCFNetMsmqAdapterPublishing**应用程序，，然后单击**启动**。 在**启动**对话框中，单击**启动**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，展开**主机实例**，右键单击**BizTalkServerApplication**或另一个适当的主机实例，然后单击**重新启动**。 尽管本步骤中并未要求，但确保本示例到此处仍能正常运行不失为一个好的方法。  
  
3.  在 Visual Studio 中，在**调试**菜单上，单击**启动但不调试**运行 WCFClient 应用程序。 这会向 WCF-NetMsmq 接收位置发送示例消息。 您将看到以下输出消息，说明消息已发送。  
  
     **调用 WCF NetMsmq 提交操作接收位置**  
  
     **按任意键关闭 WCF 客户端应用程序**  
  
4.  按任意键以关闭 WCFClient 应用程序。  
  
5.  在 Visual Studio 命令提示符下，请转到**C:\WCFNetMsmqAdapterPublishing\Out**文件夹，然后确保响应消息发回 WCFClient 应用程序存在。  
  
6.  双击要打开 Internet Explorer 和视图中的 {GUID}.xml 文件**OrderID**服务处理的值。  
  
## <a name="see-also"></a>另请参阅  
 [配置 WCF NetMsmq 接收位置](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)   
 [WCF 适配器演练](../core/wcf-adapter-walkthroughs.md)   
 [为 WCF 发布服务元数据接收适配器](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)