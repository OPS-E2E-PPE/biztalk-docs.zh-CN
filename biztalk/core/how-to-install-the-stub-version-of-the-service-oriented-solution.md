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
ms.openlocfilehash: 8ecb7da2662649fe9744c5a4744b50834b2b87bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336988"
---
# <a name="how-to-install-the-stub-version-of-the-service-oriented-solution"></a>如何安装该服务的存根版本面向解决方案
以下步骤介绍如何准备计算机以安装面向服务的解决方案的存根版本以及如何在计算机上安装该解决方案。  
  
-   [准备计算机以安装面向服务的解决方案的存根版本](#step1)  
  
-   [安装 Windows 的 IBM WebSphere MQ 客户端](#step3)  
  
-   [为面向服务的解决方案在 IIS 中创建的虚拟目录](#step5)  
  
-   [构建面向服务的解决方案](#step7)  
  
-   [在 SSO 数据库中创建的企业单一登录 (SSO) 条目和值](#step9)  
  
-   [部署面向服务的解决方案的 BAM 定义](#step11)  
  
-   [部署面向服务的解决方案](#step13)  
  
##  <a name="step1"></a> 准备计算机以安装面向服务的解决方案的存根版本  
  
#### <a name="to-prepare-the-computer-for-installing-the-stub-version-of-the-service-oriented-solution"></a>若要准备计算机以安装面向服务的解决方案的存根版本  
  
1. 请确保**Default Web Site**配置为使用 ASP.NET 2.X。  
  
   1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
   2.  在中**Internet 信息服务 (IIS) 管理器**，计算机名称，展开**站点**，展开**Default Web Site**，展开**aspnet_client**，展开**system_web**。  
  
   3.  请确保子文件夹为 2.X。  
  
2. 单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**服务**。 使用**Services**控制台中，请确保以下服务正在运行：  
  
   -   **World Wide Web 发布**  
  
3. 单击**启动**，依次指向**所有程序**，指向**管理工具**，单击**计算机管理**控制台，以及如何将到本地管理员组的 BizTalk 服务帐户。  
  
4. 如果您安装了 Windows SharePoint Services，排除了 （根） 的**Default Web Site** ，如下所示 Windows SharePoint Services 管理路径中：单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。  
  
   1.  下**虚拟服务器配置**，选择**配置虚拟服务器设置**。  
  
   2.  上**虚拟服务器列表**页上，单击**Default Web Site**。  
  
   3.  上**虚拟服务器设置**页上，单击**定义管理路径**。  
  
   4.  在中**包含的路径**一部分**定义管理路径**页上，选择**根**，然后单击**删除所选的路径**。  
  
   5.  在命令提示符处，执行 IISReset。  
  
5. 注销计算机，然后登录到 BizTalk 服务帐户的计算机。  
  
6. 打开命令提示符下键入以下命令，然后按 ENTER 以设置 %btssolutionspath%环境。 然后，退出命令提示符。  
  
   - setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"  
  
     > [!NOTE]
     >  如果使用 64 位计算机，使用 %programfiles （x86） %而不是 %programfiles%。  
  
     > [!NOTE]
     >  有关 SETX 命令的详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=67831 ](http://go.microsoft.com/fwlink/?LinkId=67831)。  
  
##  <a name="step3"></a> 安装 Windows 的 IBM WebSphere MQ 客户端  
  
#### <a name="to-install-the-ibm-websphere-mq-client-for-windows"></a>若要安装 IBM WebSphere MQ 客户端的 Windows  
  
1. 下载最新版本的 IBM WebSphere MQ 客户端的 Windows。  
  
   > [!NOTE]
   >  即使解决方案的存根版本不需要 IBM WebSphere Server，客户端应用程序引用由 IBM WebSphere MQ 客户端的 Windows，因此您必须安装的 amqmdnet.dll 文件。 存根版本的客户端不会在 DLL 中实际调用 API。 仅用于编译和运行客户端应用程序需要它。 可以从 IBM 网站下载 IBM WebSphere MQ 客户端的 Windows。  
  
2. 安装适用于 Windows 的 IBM WebSphere MQ 客户端。  
  
   > [!NOTE]
   >  不需要配置 IBM WebSphere MQ 客户端的 Windows。 将所有默认设置。  
  
3. 将 WebSphere MQ 类添加到全局程序集缓存 (GAC) 的.NET 程序集。  
  
   1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，导航到目录\<IBM MQSeries 安装目录\>\bin。  
  
   2. 运行以下命令 （请确保 gacutil.exe 位于 path 环境）：  
  
       `gacutil.exe /i amqmdnet.dll`  
  
##  <a name="step5"></a> 为面向服务的解决方案在 IIS 中创建的虚拟目录  
  
#### <a name="to-create-the-virtual-directories-in-iis-for-the-service-oriented-solution"></a>若要为面向服务的解决方案在 IIS 中创建的虚拟目录  
  
1.  在中**Internet 信息服务 (IIS) 管理器**，右键单击**应用程序池**，选择**添加应用程序池**。  
  
     上**添加应用程序池**对话框中，键入`SSOStubAppPool`中**名称**文本框中，，然后单击**确定**。  
  
     面向服务的解决方案使用，包括已发布的 Web 虚拟目录为存根版本的业务流程、 存根 SAP Web 服务、 存根付款跟踪程序 Web 服务和存根挂起事务 Web 服务的服务。  
  
2.  在中**Internet 信息服务 (IIS) 管理器**，右键单击您刚的应用程序池创建，并单击**高级设置**。  
  
3.  右侧的列中单击**标识**属性，然后单击省略号 (**...**) 按钮。  
  
4.  在中**应用程序池标识**对话框中，选择**自定义帐户**选项，并单击**设置**。  
  
5.  在中**设置凭据**对话框中，指定用户名和密码，确认该密码，然后单击**确定**。  
  
    > [!NOTE]
    >  此用户必须有权执行业务流程代理 Web 服务，并且必须添加到一个 BizTalk Server Administrators、 SSO Administrators 或 SSO Affiliated Administrators 组  
  
6.  单击**确定**以关闭**应用程序池标识**对话框。  
  
7.  单击“确定”  关闭“高级设置”  对话框。  
  
8.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  
  
    1.  使用**虚拟目录创建向导**，代理 Web 服务适配器版本创建以下虚拟目录：  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub  
  
         PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub  
  
         访问权限 = 读取，运行脚本  
  
    2.  使用**虚拟目录创建向导**，代理 Web 服务适配器版本创建以下虚拟目录：  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP  
  
         PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP  
  
         访问权限 = 读取，运行脚本  
  
    3.  使用**虚拟目录创建向导**，代理 Web 服务适配器版本创建以下虚拟目录：  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  
  
         PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  
  
         访问权限 = 读取，运行脚本  
  
    4.  使用**虚拟目录创建向导**，代理 Web 服务适配器版本创建以下虚拟目录：  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker  
  
         PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack  
  
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
  
2. 在 Visual Studio 命令提示符，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln 文件夹，然后运行以下命令以生成面向服务的解决方案的存根版本。  
  
   -   `SetupBTSSoln.bat`  
  
   > [!NOTE]
   >  在下面列出的文件，将 17f20caea2afcc8c 的所有实例都替换当前公钥标记。  
   > 
   > - %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs  
   >   -   %BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs  
  
##  <a name="step9"></a> 在 SSO 数据库中创建的企业单一登录 (SSO) 条目和值  
  
#### <a name="to-create-the-enterprise-single-sign-on-sso-entries-and-values-in-the-sso-database"></a>若要在 SSO 数据库中创建的企业单一登录 (SSO) 条目和值  
  
1.  打开命令提示符，将当前目录更改为 %btssolutionspath%\so\btssoln\scripts，然后运行以下命令以设置 Enterprise Single Sign-on 文件夹的 PATH 环境。  
  
    -   `Set PATH=%PATH%;%ProgramFiles%\"Common Files\Enterprise Single Sign-On"`  
  
2.  在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，使用记事本，打开 ConfigStoreApp.xml，然后查看该文件的内容。  
  
    > [!NOTE]
    >  此文件定义在此方案用于存储配置参数的 SSO 配置存储应用程序。 一些配置参数包括**超时**值，该值用于与 SAP 进行通信 （适用于所有三个版本）。 没有更改此文件是必需的。  
  
3.  在命令提示符处，运行以下命令以创建 SSO 配置存储应用程序。  
  
    -   `ssomanage -createapps ConfigStoreApp.xml`  
  
4.  在命令提示符下，使用记事本，打开 SetConfigValuesInSSO.cmd，然后查看该文件的内容  
  
    > [!NOTE]
    >  此命令文件在 SSO 数据库中设置的配置参数的值。 它包含在命令文件的开头中本地变量中设置的值的多个 set 语句。 **SAPAdapterTimeout**， **PendingTransactionsAdapterTimeout**，并**PaymentTrackingAdapterTimeout**存根和适配器版本中使用的值。 其余的值用于内联版本中。 存根版本所需不不到此文件的任何更改。  
  
5.  在命令提示符处，键入`SetConfigValuesInSSO.cmd`，然后按 enter 键以将值存储在 SSO 配置存储应用程序。  
  
6.  在命令提示符下运行以下命令以启用 sso 票证：  
  
    -   `ssomanage -tickets yes yes`  
  
##  <a name="step11"></a> 部署面向服务的解决方案的 BAM 定义  
  
#### <a name="to-deploy-the-bam-definition-for-the-service-oriented-solution"></a>若要部署面向服务的解决方案的 BAM 定义  
  
1.  在命令提示符下键入以下命令，然后按 ENTER。 这将设置用于查找 BAM 实用工具的路径：  
  
    -   SET PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking  
  
2.  在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\BAM 文件夹，并键入以下命令，然后按 ENTER:  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
        > [!NOTE]
        >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
##  <a name="step13"></a> 部署面向服务的解决方案  
  
#### <a name="to-deploy-the-service-oriented-solution"></a>若要部署面向服务的解决方案  
  
1.  打开命令提示符处，并将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。  
  
2.  修改**DeployStubBinding.cmd**文件的"debug"和"开发"的所有实例都替换为"发布"。  
  
3.  打开命令提示符处，并将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。 键入以下命令，然后按 Enter：  
  
    -   `DeployStubBinding.cmd`  
  
4.  在命令提示符处，运行以下命令以启动业务流程的存根版本  
  
    -   `Startstub.vbs`  
  
## <a name="next-steps"></a>后续步骤  
 测试面向服务的解决方案的存根版本中的工作方式[如何运行面向服务的解决方案](../core/how-to-run-the-service-oriented-solution.md)。  
  
## <a name="see-also"></a>请参阅  
 [然后再安装面向服务的解决方案](../core/before-installing-the-service-oriented-solution.md)   
 [如何安装的内联版本和适配器版本的服务面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [面向服务的解决方案的开发人员计算机设置](../core/developer-machine-setup-for-the-service-oriented-solution.md)