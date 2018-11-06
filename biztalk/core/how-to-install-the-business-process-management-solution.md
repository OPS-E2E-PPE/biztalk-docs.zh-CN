---
title: 如何安装业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, examples
- process management solution tutorial, installing
- process management solution tutorial, deployment prerequisites
ms.assetid: 930f3bb1-05e6-4b02-852d-6139aaf341f0
caps.latest.revision: 61
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffb067c206018996bc48641bcd8211921b0294dd
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752518"
---
# <a name="how-to-install-the-business-process-management-solution"></a>如何安装业务流程管理解决方案
以下步骤介绍如何为安装业务流程管理 (BPM) 解决方案准备计算机，以及如何在此计算机上安装该解决方案：  
  
-   [准备用于安装业务流程管理解决方案的计算机](#step1)  
  
     在准备步骤中，需要创建将由接收和发送端口使用的文件夹、队列和 SQL 数据库。 还要为客户端应用程序、CSRWebApp 和 OrderBroker 代理 Web Services 创建两个虚拟目录。  
  
-   [配置用于安装业务流程管理解决方案的计算机](#step3)  
  
-   [安装业务流程管理解决方案](#step5)  
  
> [!NOTE]
>  您将运行一些批处理文件以部署该解决方案。 建议将批处理文件的输出重定向到文本文件，以检验脚本是否成功完成。  
  
##  <a name="step1"></a> 准备用于安装业务流程管理解决方案的计算机  
  
#### <a name="to-prepare-the-computer-for-installing-the-business-process-management-solution"></a>若要准备用于安装业务流程管理解决方案的计算机  
  
1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**服务**。 使用**Services**控制台中，请确保以下服务正在运行：  
  
    -   **FTP 发布**  
  
    -   **消息队列**  
  
    -   **World Wide Web 发布**  
  
2.  单击**启动**，依次指向**所有程序**，指向**管理工具**，单击**计算机管理**控制台，以及如何将到本地管理员组的 BizTalk 服务帐户。  
  
3.  如果您安装了 Windows SharePoint Services，排除了 （根） 的**Default Web Site** ，如下所示 Windows SharePoint Services 管理路径中： 单击**启动**，指向**所有程序**，依次指向**管理工具**，然后单击**SharePoint 管理中心**。  
  
    1.  下**虚拟服务器配置**，选择**配置虚拟服务器设置**。  
  
    2.  上**虚拟服务器列表**页上，单击**Default Web Site**。  
  
    3.  上**虚拟服务器设置**页上，单击**定义管理路径**。  
  
    4.  在中**包含的路径**一部分**定义管理路径**页上，选择**根**，然后单击**删除所选的路径**。  
  
    5.  在命令提示符下，执行 IISReset。  
  
##  <a name="step3"></a> 配置用于安装业务流程管理解决方案的计算机  
  
#### <a name="to-configure-the-computer-for-installing-the-business-process-management-solution"></a>若要配置用于安装业务流程管理解决方案的计算机  
  
1.  从计算机注销，然后使用 BizTalk 服务帐户登录到该计算机。  
  
2.  打开命令提示符，键入以下命令，然后按 Enter 设置 %BTSSolutionsPath% 环境变量，以指示 E2E 解决方案的基本文件夹。 然后，退出命令提示符。  
  
    -   `setx BTSSolutionsPath "%ProgramFiles%\Microsoft BizTalk Server 2009\SDK\Scenarios"`  
  
        > [!NOTE]
        >  如果使用的是 64 位计算机，则使用 %ProgramFiles(x86)% 而不是 %ProgramFiles%。  
  
        > [!NOTE]
        >  有关 SETX 命令的详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=67831 ](http://go.microsoft.com/fwlink/?LinkId=67831)。  
  
3.  打开命令提示符下，将当前目录更改为 %BTSSolutionsPath%\BPM\HistoryDB 文件夹，键入`CreateDatabase.cmd`，然后按 ENTER 以创建历史记录数据库。  
  
    > [!NOTE]
    >  运行指定作为 SQL 发送适配器处理程序的主机的用户必须具有对 SouthridgeVideoHistory 数据库执行存储过程的权限。  
  
4.  在命令提示符下，运行以下命令以将默认脚本主机更改为 CScript.exe  
  
    -   `CScript /H:CScript`  
  
5.  在命令提示符下，运行以下命令以创建 CSRWebApp Web 应用程序  
  
    -   `iisvdir /create "Default Web Site" CSRWebApp "%BTSSolutionsPath%\BPM\CSRWebApp"`  
  
        > [!NOTE]
        >  有关 iisvdir.vbs 的详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=67830 ](http://go.microsoft.com/fwlink/?LinkId=67830)。  
  
6.  在命令提示符下，运行以下命令以为 OrderBroker_Proxy 创建新的 IIS 虚拟目录。  
  
    -   `iisvdir /create "Default Web Site" BTSScn.BPM.OrderBroker_Proxy "%BTSSolutionsPath%\BPM\OrderBroker_Proxy"`  
  
    > [!NOTE]
    >  Internet 信息服务 (IIS) 管理器可用于创建 Web 应用程序。 有关如何在 IIS 7.0 中创建应用程序的详细信息，请参阅上的 IIS 7.0 文档[ http://go.microsoft.com/fwlink/?LinkId=59263 ](http://go.microsoft.com/fwlink/?LinkId=59263)。  
  
7.  创建新的 IIS 应用程序池，并将其标识设置为 BizTalk Isolated Host Users 组和 IIS_WPG 组的成员用户，如下所示：  
  
    1.  在 Internet 信息服务 (IIS) 管理器中，右键单击**应用程序池**，选择**新建**，然后选择**应用程序池**。  
  
    2.  类型**应用程序池 ID** （任何值），然后单击**确定**。  
  
    3.  右键单击应用程序池创建，并选择**高级设置**。  
  
    4.  展开**过程模型**，在右侧列中单击**标识**设置，然后依次 **...**  
  
    5.  选择用户帐户 (任一**内置帐户**或**自定义帐户**) 有权创建和执行在 Windows\Temp 目录中的文件。 在配置 BizTalk 时，配置过程已为添加到 BizTalk Isolated Host Users 组中的用户设置了这些权限。 最好指定同一用户。  
  
8.  在 Internet 信息服务 (IIS) 管理器中，展开**网站**，展开**Default Web Site**，右键单击**BTSScn.BPM.OrderBroker_Proxy**，指向**管理应用程序**，然后单击**高级设置**。  
  
9. 设置**应用程序池**到上一步中创建的应用程序池。  
  
10. 重复前面的两个步骤对于**CSRWebApp**应用程序。  
  
11. 重置 IIS 以确保所有这些更改立即生效。 若要执行此操作，请运行**iisreset**在命令提示符。  
  
12. 在命令提示符下，将当前文件夹更改为 %btssolutionspath%\bpm\scripts，类型`CreateQueues.vbs`，然后按 ENTER 以创建以下专用队列。  
  
    |“属性”|事务性|事务协议|  
    |----------|-------------------|--------------------------|  
    |ToFacilitiesQ|用户帐户控制|本机|  
    |FromFacilitiesQ|用户帐户控制|本机|  
    |FromFixedOrdersQ|用户帐户控制|本机|  
    |ToServicingSystemQ|用户帐户控制|本机|  
    |ToCSRSystemQ|否|HTTP|  
    |ToVendorSystemQ|否|HTTP|  
  
    > [!NOTE]
    >  可以使用**计算机管理**管理单元来创建队列。 有关如何创建专用队列的详细信息，请参阅消息队列文档，网址[ http://go.microsoft.com/fwlink/?LinkId=59264 ](http://go.microsoft.com/fwlink/?LinkId=59264)。 有关如何安装 MSMQ 3.0 的详细信息，请参阅消息队列文档，网址[ http://go.microsoft.com/fwlink/?LinkId=59265 ](http://go.microsoft.com/fwlink/?LinkId=59265)。  
  
13. 在命令提示符下，将当前文件夹更改为 %btssolutionspath%\bpm\scripts，类型`CreateTestDirectories.cmd`，然后按 ENTER。  
  
    -   将在 %SystemDrive%\BPMTest 文件夹中创建以下文件夹  
  
         CSRResponse-DSP  
  
         VendorResponse-DSP  
  
         OrderErrors-SP  
  
         ErrorResponse-RP-TestRL  
  
         Facilities-SP  
  
         Facilities-RP-TestRL  
  
         HistoryInsert-SP  
  
         HistoryUpdate-SP  
  
         Order-RP-TestRL  
  
         ServicingSystem-SP  
  
         Vendor-RP-TestRL  
  
         BizTalkErrors-SP  
  
    -   在 %SystemDrive%\Inetpub\ftproot 文件夹中创建 FromVendor 文件夹。  
  
        > [!NOTE]
        >  如果 Windows 系统未安装在 C 驱动器上，则应将 %SystemDrive% 替换为 C:。 文件夹名称必须与 BPM 解决方案所提供的绑定文件中的地址相匹配。  
  
        > [!NOTE]
        >  BizTalk 服务帐户必须对 FromVendor 文件夹具有读/写权限。  
  
##  <a name="step5"></a> 安装业务流程管理解决方案  
  
#### <a name="to-install-the-business-process-management-solution"></a>安装业务流程管理解决方案  
  
1. 在命令提示符下，将当前文件夹更改为 %btssolutionspath%\bpm，类型`SetupBPM.bat`，然后按 ENTER。  
  
   > [!NOTE]
   >  在运行 setupbpm.bat 之前，在文件中 **%BTSInstallPath%/SDK/Scenarios/BPM/CSDWebApp/App_WebReferences/SouthridgeVideo_OrderBroker/OrderBrokerOrch_OrderPort.wsdl**和 **%BTSInstallPath%/SDK/Scenarios/BPM/OrderBroker_Proxy/App_Code/OrderBrokerOrch_OrderPort.asmx.cs**，8f8bbebbb3fb375a 的所有实例都替换为 XXXXXXXXXXXXXXXX。  
  
    SetupBPM.bat 将执行以下任务：  
  
   1.  创建唯一强名称密钥 (SNK)，用于对 BPM 解决方案的程序集进行签名。  
  
   2.  从 SNK 中提取公钥标记。  
  
   3.  使用该公钥标记更新绑定文件。  
  
   4.  生成 BPM 解决方案，并安装 OpsAdapter。  
  
   5.  在 %BTSSolutionsPath%\Common 文件夹中生成 SSOApplicationConfig。  
  
2. 使用业务规则引擎部署向导部署 Southridge Video 业务规则：  
  
   1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则引擎部署向导**。  
  
      > [!NOTE]
      >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
   2. 上**欢迎**页上，单击**下一步**。  
  
   3. 上**部署任务**页上，选择**导入策略/词汇并发布到数据库文件从**，然后单击**下一步**。  
  
   4. 上**策略存储区**页上，保留所有其他默认设置，然后单击**下一步**。  
  
   5. 上**导入规则引擎策略/词汇文件**页上，单击**浏览**，选择 %BTSSolutionsPath%\BPM\Rules 文件夹中的 DecodeAndValidateOrderRules.xml 文件，然后单击**下一步**。  
  
   6. 上**准备好**页上，单击**下一步**，然后在**导入策略/词汇**页上，单击**下一步**  
  
   7. 在完成页上选择**再次运行向导**以再次打开该向导，然后单击**完成**。  
  
   8. 上**欢迎**页上，单击**下一步**。  
  
   9. 上**部署任务**页上，选择**DeployPolicy**，然后单击**下一步**。  
  
   10. 上**策略存储区**页上，保留所有其他默认设置，然后单击**下一步**。  
  
   11. 上**部署策略**页上，选择**DecodeAndValidateOrder 1.0**中**规则引擎策略**下拉列表，再单击**下一步**.  
  
   12. 上**准备好**页上，单击**下一步**，然后在**部署策略**页上，单击**下一步**。  
  
   13. 在完成页上单击**完成**。  
  
3. 如果您安装 BPM 解决方案的 64 位计算机上，然后  
  
   1.  打开 32 位命令提示符，以下操作： 单击**启动**，单击**运行**，类型`%SYSTEMROOT%\SYSWOW64\CMD.EXE`，然后按 ENTER。  
  
   2.  在 32 位命令提示符下，将目录更改为 %BTSSolutionsPath%\BPM\Scripts 文件夹。  
  
   3.  使用记事本，打开 CreateSouthridgeVideoApplication.cmd，然后将“%CommonProgramFiles%\Enterprise Single Sign-On\ssomanage.exe”替换为“%SystemDrive%\Program Files\Common Files\Enterprise Single Sign-On\ssomanage.exe”。  
  
       > [!NOTE]
       >  在 32 位命令提示符下，%CommonProgramFiles% 变量将更改为“%ProgramFiles(x86)%\Common Files”。 由于 SSO 管理实用工具即使在 64 位计算机上也安装在 %ProgramFiles% 中，因此必须修复该路径。 DeployBPM.cmd 将调用 CreateSouthridgeVideoApplication.cmd。  
  
   4.  在 32 位命令提示符下键入`DeployBPM.cmd`，然后按 ENTER。  
  
       > [!NOTE]
       >  DeployBPM.cmd 必须在 32 位命令提示符下运行，因为它所包括的 VB 脚本需要访问 x86 对象，而这样的对象需要 x86 版本的 cscript.exe。  
  
4. 在命令提示符下，将当前文件夹更改为 %btssolutionspath%\bpm\scripts，类型`DeployBPM.cmd`，然后按 ENTER。 DeployBPM.cmd 将执行以下任务：  
  
   1.  为 BPM 解决方案创建 BizTalk 应用程序。  
  
   2.  添加应用程序之间的引用。  
  
   3.  导入绑定文件。  
  
   4.  部署 BAM 定义文件。  
  
   5.  注册 SouthridgeVideo 事件源。  
  
   6.  创建单一登录 (SSO) 关联应用程序，并将配置值保存到 SSO 应用程序。  
  
5. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
   1.  在中**BizTalk Server 管理控制台**，展开**BizTalk 组**，展开**应用程序**，展开**BTSScn.BPM.OrderBrokerApp**，展开**接收位置**，右键单击**供应商 RP RL**，再单击属性。  
  
   2.  上**属性**对话框中，单击**配置**，，然后下表作为输入值**传输属性**对话框：  
  
       |属性名称|ReplTest1|  
       |-------------------|-----------|  
       |**Server**|`localhost`|  
       |**用户名**|\<*BizTalk 服务帐户名称*\>|  
       |**密码**|\<*BizTalk 服务帐户密码*\>|  
  
6. 运行 BPM 解决方案。 有关运行该解决方案的详细信息，请参阅[如何运行业务流程管理解决方案](../core/how-to-run-the-business-process-management-solution.md)。  
  
## <a name="next-steps"></a>后续步骤  
 测试的业务管理解决方案工作原理[如何运行业务流程管理解决方案](../core/how-to-run-the-business-process-management-solution.md)。  
  
## <a name="see-also"></a>请参阅  
 [安装业务流程管理解决方案之前](../core/before-installing-the-business-process-management-solution.md)   
 [业务流程管理解决方案的开发人员计算机设置](../core/developer-machine-setup-for-the-business-process-management-solution.md)
