---
title: 如何安装该服务的存根版本面向解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IIS, installing virtual directories [service solutions]
- service solution tutorial, IIS virtual directories
- service solution tutorial, stub version
- deploying, BAM solutions [service solutions]
- service solution tutorial, solutions [BAM]
- service solution tutorial, service solutions
- SSO, configuring
- IBM WebSphere MQ Client
- service solution tutorial, IBM WebSphere MQ Client
- installing, tutorials
- service solutions, deploying
- service solution tutorial, SSO
- BAM, deploying solutions
- service solution tutorial, building solutions
- service solution tutorial, installing
ms.assetid: 45de7681-4df0-47a4-a02c-509140423a1e
caps.latest.revision: 53
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d42b559afb89c931aec44080beaa4c00dea89ba2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023659"
---
# <a name="how-to-install-the-stub-version-of-the-service-oriented-solution"></a>如何安装面向服务的解决方案的存根版本
以下步骤介绍了如何准备计算机以安装面向服务的解决方案的存根版本，以及如何在计算机上安装该解决方案：  
  
-   [准备计算机以安装面向服务的解决方案的存根版本](#step1)  
  
-   [安装 Windows 的 IBM WebSphere MQ 客户端](#step3)  
  
-   [为面向服务的解决方案在 IIS 中创建的虚拟目录](#step5)  
  
-   [构建面向服务的解决方案](#step7)  
  
-   [在 SSO 数据库中创建的企业单一登录 (SSO) 条目和值](#step9)  
  
-   [部署面向服务的解决方案的 BAM 定义](#step11)  
  
-   [部署面向服务的解决方案](#step13)  
  
##  <a name="step1"></a> 准备计算机以安装面向服务的解决方案的存根版本  
  
#### <a name="to-prepare-the-computer-for-installing-the-stub-version-of-the-service-oriented-solution"></a>准备计算机以安装面向服务的解决方案的存根版本  
  
1. 请确保**Default Web Site**配置为使用 ASP.NET 2.X。  
  
   1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
   2.  在中**Internet 信息服务 (IIS) 管理器**，计算机名称，展开**站点**，展开**Default Web Site**，展开**aspnet_client**，展开**system_web**。  
  
   3.  确保子文件夹为 2.X。  
  
2. 单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**服务**。 使用**Services**控制台中，请确保以下服务正在运行：  
  
   -   **World Wide Web 发布**  
  
3. 单击**启动**，依次指向**所有程序**，指向**管理工具**，单击**计算机管理**控制台，以及如何将到本地管理员组的 BizTalk 服务帐户。  
  
4. 如果您安装了 Windows SharePoint Services，排除了 （根） 的**Default Web Site** ，如下所示 Windows SharePoint Services 管理路径中： 单击**启动**，指向**所有程序**，依次指向**管理工具**，然后单击**SharePoint 管理中心**。  
  
   1.  下**虚拟服务器配置**，选择**配置虚拟服务器设置**。  
  
   2.  上**虚拟服务器列表**页上，单击**Default Web Site**。  
  
   3.  上**虚拟服务器设置**页上，单击**定义管理路径**。  
  
   4.  在中**包含的路径**一部分**定义管理路径**页上，选择**根**，然后单击**删除所选的路径**。  
  
   5.  在命令提示符下，执行 IISReset。  
  
5. 从计算机注销，然后使用 BizTalk 服务帐户登录到该计算机。  
  
6. 打开命令提示符，键入以下命令，然后按 Enter 以设置 %BTSSolutionsPath% 环境。 然后，退出命令提示符。  
  
   - setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"  
  
     > [!NOTE]
     >  如果使用的是 64 位计算机，则使用 %ProgramFiles(x86)% 而不是 %ProgramFiles%。  
  
     > [!NOTE]
     >  有关 SETX 命令的详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=67831 ](http://go.microsoft.com/fwlink/?LinkId=67831)。  
  
##  <a name="step3"></a> 安装 Windows 的 IBM WebSphere MQ 客户端  
  
#### <a name="to-install-the-ibm-websphere-mq-client-for-windows"></a>安装 IBM WebSphere MQ Client for Windows  
  
1. 下载最新版本的 IBM WebSphere MQ Client for Windows。  
  
   > [!NOTE]
   >  即使解决方案的存根版本不需要 IBM WebSphere Server，客户端应用程序仍然会引用由 IBM WebSphere MQ Client for Windows 提供的 amqmdnet.dll 文件，因此必须安装它。 存根版本的客户端实际上不会调用该 DLL 中的 API。 只有在编译和运行客户端应用程序时才需要该 DLL。 你可以从 IBM 网站下载 IBM WebSphere MQ Client for Windows。  
  
2. 安装 IBM WebSphere MQ Client for Windows。  
  
   > [!NOTE]
   >  不需要配置 IBM WebSphere MQ Client for Windows。 请保留所有默认设置。  
  
3. 将用于 .NET 程序集的 WebSphere MQ 类添加到全局程序集缓存 (GAC) 中。  
  
   1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，导航到目录\<IBM MQSeries 安装目录\>\bin。  
  
   2. 运行以下命令（请确保 gacutil.exe 位于该路径环境下）：  
  
       `gacutil.exe /i amqmdnet.dll`  
  
##  <a name="step5"></a> 为面向服务的解决方案在 IIS 中创建的虚拟目录  
  
#### <a name="to-create-the-virtual-directories-in-iis-for-the-service-oriented-solution"></a>在 IIS 中为面向服务的解决方案创建虚拟目录  
  
1.  在中**Internet 信息服务 (IIS) 管理器**，右键单击**应用程序池**，选择**添加应用程序池**。  
  
     上**添加应用程序池**对话框中，键入`SSOStubAppPool`中**名称**文本框中，，然后单击**确定**。  
  
     面向服务的解决方案使用的虚拟目录包括：业务流程的存根版本的已发布 Web Services、存根 SAP Web Services、存根付款跟踪程序 Web Services 和存根挂起事务 Web Services。  
  
2.  在中**Internet 信息服务 (IIS) 管理器**，右键单击您刚的应用程序池创建，并单击**高级设置**。  
  
3.  右侧的列中单击**标识**属性，然后单击省略号 (**...**) 按钮。  
  
4.  在中**应用程序池标识**对话框中，选择**自定义帐户**选项，并单击**设置**。  
  
5.  在中**设置凭据**对话框中，指定用户名和密码，确认该密码，然后单击**确定**。  
  
    > [!NOTE]
    >  此用户必须有权执行业务流程代理 Web Services，并且必须添加到 BizTalk Server Administrators、SSO Administrators 或 SSO Affiliated Administrators 组中。  
  
6.  单击**确定**以关闭**应用程序池标识**对话框。  
  
7.  单击“确定”  关闭“高级设置”  对话框。  
  
8.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  
  
    1.  使用**虚拟目录创建向导**，代理 Web 服务适配器版本创建以下虚拟目录：  
  
         别名 = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub  
  
         路径 = \<BizTalk 安装目录\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub  
  
         访问权限 = 读取，运行脚本  
  
    2.  使用**虚拟目录创建向导**，代理 Web 服务适配器版本创建以下虚拟目录：  
  
         别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP  
  
         路径 = \<BizTalk 安装目录\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP  
  
         访问权限 = 读取，运行脚本  
  
    3.  使用**虚拟目录创建向导**，代理 Web 服务适配器版本创建以下虚拟目录：  
  
         别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  
  
         路径 = \<BizTalk 安装目录\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  
  
         访问权限 = 读取，运行脚本  
  
    4.  使用**虚拟目录创建向导**，代理 Web 服务适配器版本创建以下虚拟目录：  
  
         别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker  
  
         路径 = \<BizTalk 安装目录\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack  
  
         访问权限 = 读取，运行脚本  
  
9. 在中**Internet 信息服务 (IIS) 管理器**，展开**Web 站点**展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub，单击**属性**，，然后修改设置，如下所示：  
  
    1.  上**虚拟目录**选项卡上，设置**应用程序池**到**SSOStubAppPool**你刚刚创建。  
  
    2.  单击**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，选择**仅集成 Windows 身份验证已启用**，然后清除其他**身份验证访问**复选框。 单击**确定**退出。  
  
10. 在中**Internet 信息服务 (IIS) 管理器**，展开**Web 站点**展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP，单击**属性**，，然后修改设置，如下所示：  
  
    1.  上**虚拟目录**选项卡上，设置**应用程序池**到**SSOStubAppPool**你刚刚创建。  
  
    2.  单击**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**分组框中，并选择**启用匿名访问**. 单击**确定**退出。  
  
11. 在中**Internet 信息服务 (IIS) 管理器**，展开**Web 站点**展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions，单击**属性**，，然后修改设置，如下所示：  
  
    1.  上**虚拟目录**选项卡上，设置**应用程序池**到**SSOStubAppPool**你刚刚创建。  
  
    2.  单击**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**分组框中，并选择**启用匿名访问**. 单击**确定**退出。  
  
12. 在中**Internet 信息服务 (IIS) 管理器**，展开**Web 站点**展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker，单击**属性**，，然后修改设置，如下所示：  
  
    1.  上**虚拟目录**选项卡上，设置**应用程序池**到**SSOStubAppPool**你刚刚创建。  
  
    2.  单击**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**分组框中，并选择**启用匿名访问**. 单击**确定**退出。  
  
##  <a name="step7"></a> 构建面向服务的解决方案  
  
#### <a name="to-build-the-service-oriented-solution"></a>若要构建面向服务的解决方案  
  
1. 启动**Visual Studio 命令提示符**。  
  
   > [!NOTE]
   >  在文件中 **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs**和 **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\customerserviceport.asmx.cs**，17f20caea2afcc8c 的所有实例都替换为 a1054514fc67bded。  
  
2. 在“Visual Studio 命令提示”下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln 文件夹，然后运行以下命令以生成面向服务的解决方案的存根版本。  
  
   -   `SetupBTSSoln.bat`  
  
   > [!NOTE]
   >  在下面列出的文件中，将 17f20caea2afcc8c 所有的实例替换为当前公钥标记。  
   > 
   > - %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs  
  
##  <a name="step9"></a> 在 SSO 数据库中创建的企业单一登录 (SSO) 条目和值  
  
#### <a name="to-create-the-enterprise-single-sign-on-sso-entries-and-values-in-the-sso-database"></a>在 SSO 数据库中创建企业单一登录 (SSO) 条目和值  
  
1.  打开命令提示符，将当前目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts，然后运行以下命令以设置 Enterprise Single Sign-On 文件夹的 PATH 环境：  
  
    -   `Set PATH=%PATH%;%ProgramFiles%\"Common Files\Enterprise Single Sign-On"`  
  
2.  在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，使用记事本打开 ConfigStoreApp.xml，然后查看该文件的内容。  
  
    > [!NOTE]
    >  此文件定义了该方案在 SSO 中用于存储配置参数的配置存储应用程序。 一些配置参数包括**超时**值，该值用于与 SAP 进行通信 （适用于所有三个版本）。 不需要更改此文件。  
  
3.  在命令提示符下，运行以下命令以创建 SSO 配置存储应用程序：  
  
    -   `ssomanage -createapps ConfigStoreApp.xml`  
  
4.  在命令提示符下，使用记事本打开 SetConfigValuesInSSO.cmd，然后查看该文件的内容。  
  
    > [!NOTE]
    >  此命令文件在 SSO 数据库中设置的配置参数的值。 该命令文件的开头包含几个设置局部变量值的 set 语句。 **SAPAdapterTimeout**， **PendingTransactionsAdapterTimeout**，并**PaymentTrackingAdapterTimeout**存根和适配器版本中使用的值。 其余的值用于内联版本。 对于存根版本不需要更改此文件。  
  
5.  在命令提示符处，键入`SetConfigValuesInSSO.cmd`，然后按 enter 键以将值存储在 SSO 配置存储应用程序。  
  
6.  在命令提示符下，运行以下命令以在 SSO 中启用票证：  
  
    -   `ssomanage -tickets yes yes`  
  
##  <a name="step11"></a> 部署面向服务的解决方案的 BAM 定义  
  
#### <a name="to-deploy-the-bam-definition-for-the-service-oriented-solution"></a>若要部署面向服务的解决方案的 BAM 定义  
  
1.  在命令提示符下，键入以下命令，然后按 Enter。 此命令将设置用于查找 BAM 实用工具的路径：  
  
    -   集 PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking  
  
2.  在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\BAM 文件夹，键入以下命令，然后按 Enter：  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
        > [!NOTE]
        >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
##  <a name="step13"></a> 部署面向服务的解决方案  
  
#### <a name="to-deploy-the-service-oriented-solution"></a>若要部署面向服务的解决方案  
  
1.  打开命令提示符，并将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。  
  
2.  修改**DeployStubBinding.cmd**文件的"debug"和"开发"的所有实例都替换为"发布"。  
  
3.  打开命令提示符，并将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。 键入以下命令，然后按 Enter：  
  
    -   `DeployStubBinding.cmd`  
  
4.  在命令提示符下，运行以下命令以启动用于存根版本的业务流程：  
  
    -   `Startstub.vbs`  
  
## <a name="next-steps"></a>后续步骤  
 测试面向服务的解决方案的存根版本中的工作方式[如何运行面向服务的解决方案](../core/how-to-run-the-service-oriented-solution.md)。  
  
## <a name="see-also"></a>请参阅  
 [然后再安装面向服务的解决方案](../core/before-installing-the-service-oriented-solution.md)   
 [如何安装的内联版本和适配器版本的服务面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [面向服务的解决方案的开发人员计算机设置](../core/developer-machine-setup-for-the-service-oriented-solution.md)