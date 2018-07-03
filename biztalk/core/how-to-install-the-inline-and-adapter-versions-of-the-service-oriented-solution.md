---
title: 安装内联和适配器版本的服务面向解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6050cfe9-4e94-4a55-8b24-fbcc74d9e8f4
caps.latest.revision: 97
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdbdb61d37f6828f6e738d438fe9087acbc4d26c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019538"
---
# <a name="how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution"></a>如何安装面向服务的解决方案的内联版本和适配器版本
以下步骤将说明如何准备计算机以安装面向服务的解决方案的内联版本和适配器版本，以及如何在此计算机上安装该解决方案：  

> [!NOTE]
>  - 面向的解决方案位于文件夹中的服务\< *BizTalk Server 安装文件夹*\>\SDK\Scenarios\SO。  
>  - 如果没有大型机可用于该解决方案，则可以修改端口绑定以使用存根 Web Services 来模拟挂起事务。 该 Web Services 将在本地生成事务以模拟大型机事务。  

##  <a name="step1"></a> 准备计算机以安装面向服务的解决方案的适配器和内联版本  

1. 如果您安装了 Windows SharePoint Services，排除 （根） 的默认网站从 Windows SharePoint Services 管理路径，如下所示： 单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。  

   1.  下**虚拟服务器配置**，选择**配置虚拟服务器设置**。  

   2.  上**虚拟服务器列表**页上，单击**Default Web Site**。  

   3.  上**虚拟服务器设置**页上，单击**定义管理路径**。  

   4.  在中**包含的路径**一部分**定义管理路径**页上，选择**根**，然后单击**删除所选的路径**。  

   5.  在命令提示符下，执行 IISReset。  

2. 单击**启动**，依次指向**所有程序**，指向**管理工具**，单击**计算机管理**控制台，以及如何将到本地管理员组的 BizTalk 服务帐户。  

3. 从计算机注销，然后使用 BizTalk 服务帐户登录到该计算机。  

4. 在命令提示符下，键入以下命令，然后按 Enter 以设置 %BTSSolutionsPath% 环境变量。 然后，退出命令提示符。  

   - setx BTSSolutionsPath [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"  

     > [!NOTE]
     >  如果使用的是 64 位计算机，则使用 %ProgramFiles(x86)% 而不是 %ProgramFiles%。  

     > [!NOTE]
     >  有关 SETX 命令的详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=67831 ](http://go.microsoft.com/fwlink/?LinkId=67831)。  

##  <a name="step3"></a> 删除面向服务的解决方案的存根版本  

1. 打开**BizTalk Server 管理控制台**，如下所示： 单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在中**BizTalk Server 管理控制台**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**的应用程序**，右键单击**BTSScn.SO.CustomerService**，然后单击**停止**。 在中**停止应用程序**对话框中，选择**完全停止-终止实例**，然后单击**停止**。  

   > [!NOTE]
   >  若要安装内联版本和适配器版本，则无需删除存根版本。 如果要将所有版本放在一起，则应跳过此步骤。  

3. 打开命令提示符，键入以下命令，然后按 Enter。 此命令会将默认脚本主机更改为 CScript.exe：  

   -   `cscript /H:CScript`  

4. 在命令提示符下，将当前目录更改为 %BTSSolutonsPath%\SO\BTSSoln\Scripts 文件夹，键入以下命令，然后按 Enter：  

   -   `UnEnlistStub.vbs`  

5. 在命令提示符处，键入以下命令，然后按 ENTER:  

   -   `UndeployStub.vbs`  

6. 在命令提示符下运行以下命令  

    SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"  

    此命令将设置用于查找 BAM 实用工具的路径。  

   > [!NOTE]
   >  如果使用 64 位计算机，键入`%ProgramFiles(x86)%`而不是`%ProgramFiles%`。  

7. 在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\BAM，然后运行以下命令：  

   -   `bm remove-all -DefinitionFile:ServiceLevelTracking.xml`  

8. 在命令提示符下，将目录更改为\<*企业单一登录安装目录*\>，然后运行以下命令：  

   -   `ssomanage -tickets no no`  

9. 在命令提示符下，运行以下命令以删除 WoodgroveBank.CustomerService SSO 关联应用程序：  

    -   `ssomanage -deleteapp WoodgroveBank.CustomerService`  

10. 在命令提示符下，运行以下命令以删除存根版本所使用的网站： 有关 iisvdir.vbs 的详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=67830 ](http://go.microsoft.com/fwlink/?LinkId=67830)。  

    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub`  

    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP`  

    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions`  

    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker`  

11. 按如下所示启动 Internet 信息服务 (IIS) 管理器： 单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) 管理器**。  

    -   展开**应用程序池**，右键单击你在创建的以前的 Web 应用程序的应用程序池，单击**删除**，然后单击**确定**确认消息中对话框。  

12. 单击**启动**，依次指向**控制面板**，单击**添加或删除程序**，然后卸载 IBM WebSphere MQ 客户端的 Windows。  

13. 启动**Visual Studio 命令提示符**，然后运行以下命令以删除存根版本安装的 amqmdnet.dll:。  

    -   `gacutil /u amqmdnet`  

##  <a name="step5"></a> 准备面向服务的解决方案访问后端系统  

1. 适用于 Windows Server 在本地计算机上安装 IBM WebSphere MQ。  

   1.  保留所有默认设置。 设置**默认配置**末尾处**准备 WebSphere MQ 向导**。 队列管理器命名为 QM_\<*您的计算机名称*\>。  

   2.  安装 Fix Pack 10 (CSD10)。 保留所有默认设置。  

2. 安装 MQSeries 代理。  

   1.  重新运行 BizTalk Server 安装程序。  

   2.  上**程序维护**页上，选择**修改**，然后单击**下一步**。  

   3.  上**组件安装**页上，展开**其他软件**节点，并选择**MQSeries 代理**。  

   4.  上**完成**页上，请确保**启动 BizTalk MQSeries 代理配置向导**未选中。  

   > [!NOTE]
   >  **MQSeries 代理**复选框内容 IBM WebSphere MQ 后才会激活 Windows 安装。  

3. 打开**Visual Studio 命令提示符**，将目录更改为\< *IBM MQSeries 安装目录*\>\bin 文件夹，并运行以下命令：  

   -   `gacutil /i amqmdnet.dll`  

4. 安装 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]如果你想要安装 Microsoft Host Integration Server 2004 以访问大型机。 安装程序中对**选项**页上，选择**Visual C#.NET**，然后清除其他组件复选框。 无需安装其他组件相比**Visual C#.NET**。  

   > [!NOTE]
   >  Host Integration Server 2004 中的 TI 设计器需要[!INCLUDE[btsVStudioNet2003](../includes/btsvstudionet2003-md.md)]。  

5. 如果具有要访问的大型机 ， 则安装并配置 Microsoft Host Integration Server 2004 。 保留所有默认设置。  

#### <a name="create-the-mqseries-queues"></a>创建 MQSeries 队列  

1.  打开 WebSphere MQ Explorer 中，展开**队列管理器**，然后展开你要在其中创建队列的队列管理器。 通常情况下，队列管理器命名为 QM_\<*您的计算机名称*\>。  

2.  在 WebSphere MQ Explorer 中，右键单击**队列**，依次指向**新建**，单击**本地队列**，然后创建以下本地队列的适配器版本解决方案：  

    -   AdapterSOAInputQueue  

    -   AdapterSOAOutputQueue  

    > [!NOTE]
    >  这些队列可以共享 MQSeries 群集，但不要求其执行此操作。  

    > [!NOTE]
    >  MQSeries 队列管理器名称和队列名称均区分大小写。  

3.  重复上一步骤可为内联版本创建以下本地队列：  

    -   InlineSOAOutputQueue  

    -   InlineSOAInputQueue  

4.  重复上一步骤可为付款跟踪模拟程序创建以下本地队列。 （适配器版本和内联版本中都使用付款跟踪模拟程序）：  

    -   LastPaymentsInputQueue  

    -   LastPaymentsOutputQueue  

#### <a name="complete-configuration-of-the-mqseries-adapter"></a>完成的 MQSeries 适配器配置  

1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk MQSeries 代理配置向导**。  

2. 上**欢迎**页上，单击**下一步**。  

3. 上**应用程序标识**页上，选择**此用户**，然后输入用户名和密码。 MQSeries 代理的 COM+ 应用程序将使用此用户帐户运行。 对于此演练，请使用 BizTalk 服务所使用的同一用户帐户。 如果它不是，用户帐户必须将 MQSeries 适配器宿主的 BizTalk 服务添加到**CreatorOwner** COM + 应用程序角色。  

4. 单击**是**上**MQSConfigWiz**对话框中，如果系统提示你在上一步中输入的用户帐户具有管理权限。  

5. 上**名称的角色**页上，单击**下一步**。  

6. 上**创建 MQSAgent COM + 应用程序**页上，单击**下一步**，然后单击**完成**上**完成**页。  

#### <a name="configure-the-mainframe-cics-application"></a>配置大型机 CICS 应用程序  

1.  使用记事本，打开位于 %BTSSolutionsPath%\SO\MFAccess\HISTIComponent 文件夹中的 bizcbl.txt 及其“副件”(MainFrameProgramVTCS2Description.txt)，然后检查这两个文件的内容。  

    -   Bizcbl.txt 包括 COBOL 过程，该过程可根据帐户编号输入返回随机的帐户语句。  

    -   MainFrameProgramVTCS2Descriptoin.txt 包含用于说明输入和输出数据信息的 COMMAREA。 COMMAREA 是用于在被调用的程序和调用方程序之间来回传递数据的连续内存块。  

    > [!NOTE]
    >  副件还可用于生成事务集成器 (TI) 元数据文件使用 TI 设计器插件中使用 Visual Studio。  

    > [!NOTE]
    >  尽管以下步骤对于成功部署是至关紧要的，但 BizTalk Server 开发人员通常不执行这些步骤。 必须依赖大型机人员才可正确配置大型机环境。 大多数的大型机环境中通常都安装了此演练所需的软件。 最小的大型机操作系统环境有关的详细信息，请参阅 Host Integration Server 文档。  

2.  采用如 FTP 之类的方法将 COBOL 代码复制到主机。  

3.  编译 COBOL 代码和副件。 以下代码显示了 COBOL 编译器的作业控制语言 (JCL) 的示例：  

    ```  
    //COB      EXEC PGM=IGYCRCTL,  
    //            PARM=&COBPARM,  
    //            REGION=&REG  
    //STEPLIB  DD DSN=&COMPINDX..SIGYCOMP,DISP=SHR  
    //SYSLIB   DD DSN=&INDEX..SDFHCOB,DISP=SHR  
    //         DD DSN=&INDEX..SDFHMAC,DISP=SHR  
    //         DD DSN=&HLQ..&COMP..COBCOPY,DISP=SHR  
    //SYSPRINT DD SYSOUT=&OUTC  
    //*SYSPRINT DD DSN=&&INPUT,DISP=(,PASS),UNIT=SYSDA,  
    //*         SPACE=(TRK,(100,50)),  
    //*         DCB=(DSORG=PS,LRECL=121,BLKSIZE=2420,RECFM=FBA)  
    //SYSIN    DD DSN=&&SYSCIN,DISP=(OLD,DELETE)  
    //SYSLIN   DD DSN=&&LOADSET,  
    //            DISP=(MOD,PASS),  
    //            UNIT=&WORK,  
    //            SPACE=(80,(250,100))  
    //SYSUT1   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT2   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT3   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT4   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT5   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT6   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT7   DD UNIT=&WORK,SPACE=(460,(350,150))  
    ```  

4.  链接将编辑经过编译的源代码以创建可执行文件。 以下代码显示了 COBOL 链接编辑的 JCL 示例：  

    ```  
    //LKED     EXEC PGM=IEWL,REGION=&REG,  
    //            PARM=&LNKPARM,COND=(5,LT,COB)  
    //SYSLIB   DD DSN=&INDEX..SDFHLOAD,DISP=SHR  
    //         DD DSN=CEE.SCEELKED,DISP=SHR  
    //         DD DSN=&TCPINDX..SEZATCP,DISP=SHR  
    //SYSLMOD  DD DSN=&LMINDX..&COMP..LOADLIB,DISP=SHR  
    //SYSUT1   DD UNIT=&WORK,  
    //            DCB=BLKSIZE=1024,  
    //            SPACE=(1024,(200,20))  
    //SYSPRINT DD SYSOUT=&OUTC  
    //SYSLIN   DD DSN=&&LOADSET,DISP=(OLD,DELETE)  
    //         DD DSN=&&COPYLINK,DISP=(OLD,DELETE)  
    ```  

5.  配置 CICS 大型机应用程序。  

    -   在此步骤中，大型机系统程序员或 CICS 开发人员必须安装 TCPIPSERVICE、会话、连接、事务和程序的资源定义。  

    -   你应与大型机管理员联系，以获取可访问的 IP 地址、端口号和程序名的链接。  

        > [!NOTE]
        >  此演练假定该大型机使用 CICS 应用程序服务器，并且事务的编程模型为 TCP/IP（增强型侦听器模式（ELM）链接）。  

##  <a name="step7"></a> 配置安全套接字层 (SSL) 的 Web 服务器  

#### <a name="install-certificate-services"></a>安装证书服务  

1.  单击**启动**，依次指向**控制面板**，然后单击**添加或删除程序**。  

2.  在中**添加或删除程序**对话框中，单击**添加/删除 Windows 组件**。  

3.  在中**Windows 组件向导**，选择**证书服务**，单击**下一步**，然后按照屏幕说明完成安装。  

#### <a name="create-a-certificate-request"></a>创建证书请求  

1.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，右键单击**Default Web Site**，单击**属性**单击**目录安全性**选项卡，然后依次**服务器证书**。  

2.  上**欢迎**页**Web 服务器证书向导**，单击**下一步**。  

3.  上**服务证书**页上，选择**创建新证书**，然后单击**下一步**。  

4.  上**延迟或立即请求**页上，单击**现在，准备请求，但稍后发送**，然后单击**下一步**。  

5.  上**名称和安全设置**页上，保留所有默认设置，然后单击**下一步**。  

6.  上**组织信息**页上，键入您公司的组织和组织单位名称，然后单击**下一步**。  

7.  上**站点的公用名称**页上，键入您的计算机名称中**公用名**框中，然后依次**下一步**。  

8.  上**地理信息**页上，填写您的地理信息，然后单击**下一步**。  

9. 上**证书请求文件名**页上，键入`c:\certreq.txt`中**文件名**框中，然后依次**下一步**。  

10. 上**请求文件摘要**页上，单击**下一步**，然后单击**完成**上**完成**页。  

#### <a name="submit-the-certificate-request-to-the-certification-authority"></a>将证书请求提交给证书颁发机构  

1.  在 Internet Explorer 中，在地址框中，键入`http://localhost/certsrvt`，然后按 ENTER。  

2.  上**欢迎**页上，单击**申请一个证书**，然后单击**高级的证书申请**上**申请一个证书**页。  

3.  上**高级证书申请**页上，单击**提交证书申请使用 base64 编码 PKCS #10 文件或使用 base64 编码 PKCS #7 文件续订请求**。  

4.  从"若要创建证书请求"，将其粘贴到在过程中创建的 c:\certreq.txt 复制所有文本**保存的申请**框**提交证书申请或续订申请**页上，然后依次**提交**。  

#### <a name="issue-a-certificate-using-certification-authority-management-tool"></a>使用证书颁发机构管理工具颁发证书  

1.  单击**启动**，依次指向**管理工具**，然后单击**证书颁发机构**。  

2.  在中**证书颁发机构**控制台中，展开证书颁发机构的名称，展开**挂起的请求**，右键单击在上一步骤中，点提交证书申请向**的所有任务**，然后单击**问题**。  

3.  关闭**证书颁发机构**控制台。  

#### <a name="download-the-certificate-to-the-web-server"></a>下载与 Web 服务器的证书  

1.  在 Internet Explorer 中，在地址框中，键入`http://localhost/certsrvt`，然后按 ENTER。  

2.  上**欢迎**页上，单击**查看挂起的证书申请的状态**。  

3.  上**查看挂起的证书申请的状态**页上，单击证书**请求**"创建证书请求"过程中创建。  

4.  上**证书颁发**页上，选择任一编码方案，然后单击**下载证书**。  

5.  上**安全警告**对话框中，单击**保存**，然后将证书保存另存为 c:\certnew.cer。  

#### <a name="install-the-certificate-to-the-web-server"></a>将证书安装到 Web 服务器  

1.  在**Internet 信息服务 (IIS) 管理器**，展开**网站**，右键单击**Default Web Site**为其创建证书申请，然后单击**属性**。  

2.  上**属性**对话框中，单击**目录安全性**选项卡，然后依次**服务器证书**。  

3.  上**欢迎**页**Web 服务器证书向导**，单击**下一步**。  

4.  上**挂起的证书申请**页上，选择**处理挂起的请求和安装证书**，然后单击**下一步**。  

5.  上**处理挂起的申请**页上，键入`c:\certnew.cer`中**路径和文件名**文本框中，，然后单击**下一步**。  

6.  单击**下一步**上**SSL 端口**页上，单击**下一步**上**证书 Summery**页上，然后依次**完成**上**确认**页。  

    > [!NOTE]
    >  在此演练中，不需要将服务器证书安装到本地计算机上的“受信任的根证书颁发机构”存储区，因为证书服务和 Web 服务器均安装在同一台计算机上。  

##  <a name="step9"></a> 创建后端系统的 Web 服务  

1.  在中**Internet 信息服务 (IIS) 管理器**，右键单击**应用程序池**，选择**新建**，然后选择**应用程序池**.  

    > [!NOTE]
    >  面向服务的解决方案将通过此 Web Services 访问大型机。  

2.  上**添加新应用程序池**对话框框中，输入**应用程序池 ID** （任何值），然后单击**确定**。  

3.  在中**Internet 信息服务 (IIS) 管理器**，右键单击您刚的应用程序池创建，并选择**属性**。  

4.  上**属性**页上，单击**标识**选项卡上，选择**可配置**，输入**用户名**和**密码**，然后单击**确定**。 对于此演练，请使用 BizTalk 服务所使用的同一用户帐户。  

#### <a name="create-the-pendingtransactions-web-service-for-runtime"></a>创建 PendingTransactions Web 服务的运行时  

1.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  

     使用**虚拟目录创建向导**，创建以下虚拟目录为存根 SAP Web 服务：  

     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions  

     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\MFAccess\PendingTransactions  

     访问权限 = 读取，运行脚本  

2.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions，并单击**属性**。  

    1.  在中**目录安全性**选项卡上，单击**编辑**修改**身份验证和访问控制**。 选择**基本身份验证 （密码以明文形式发送）**，并清除其他**身份验证访问**复选框。 单击**确定**以关闭**身份验证方法**对话框。  

    2.  在中**目录安全性**选项卡上，单击**编辑**下**安全通信**分组框，然后再检查**要求安全通道 (SSL)** 中**安全通信**对话框。  

    3.  在中**虚拟目录**选项卡上，设置**应用程序池**到在"创建新的 IIS 应用程序池为挂起事务 Web services"的过程中创建的应用程序池。  

#### <a name="create-the-pendingtransactions-web-service-for-development-environment"></a>创建开发环境的 PendingTransactions Web 服务  

1. 在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  

    使用**虚拟目录创建向导**，创建以下虚拟目录为存根 SAP Web 服务：  

    别名 = PendingTransactions  

    路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\MFAccess\PendingTransactions  

    访问权限 = 读取，运行脚本  

2. 在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，展开**Default Web Site**，右键单击 PendingTransactions，，然后单击**属性**。  

   1. 在中**目录安全性**选项卡上，单击**编辑**修改**身份验证和访问控制**。 选择**启用匿名访问**。 单击**确定**退出。  

      > [!NOTE]
      >  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 将使用用于开发环境的 PendingTransactions Web 应用程序。 对于生产环境，则不需要此 Web 应用程序。  

   2. 在中**虚拟目录**选项卡上，设置**应用程序池**到在"创建新的 IIS 应用程序池为挂起事务 Web services"的过程中创建的应用程序池。  

#### <a name="create-the-stub-sap-web-service"></a>创建存根 SAP Web 服务  

1.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  

     使用**虚拟目录创建向导**，创建以下虚拟目录为存根 SAP Web 服务：  

     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP  

     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP  

     访问权限 = 读取，运行脚本  

2.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP，单击**属性**，，然后修改设置，如下所示：  

    1.  在中**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \> "创建新的 IIS 的过程中创建应用程序池为挂起事务 Web services 的"。  

    2.  在中**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**分组框中，并选择**启用匿名访问**. 单击**确定**退出。  

##  <a name="step11"></a> 为面向服务的解决方案创建 TI 组件  

#### <a name="create-a-com-application-for-the-ti-component"></a>创建的 COM + 应用程序 TI 组件  

1.  在命令提示符下，运行 %systemroot%\system32\com\comexp.msc。  

2.  在中**组件服务**控制台中，展开**组件服务**，展开**计算机**，展开**我的电脑**，右键单击**COM + 应用程序**，依次指向**新建**，然后单击**应用程序**。  

    1.  上**欢迎**页上，单击**下一步**，然后单击**创建空应用程序**上**安装或创建新的应用程序**页。  

    2.  类型`BTSScn SO TI Component`中**输入新的应用程序的名称**框中，选择**服务器应用程序**作为**激活类型**，然后单击**下一步**.  

    3.  在中**帐户**分组框**设置应用程序标识**页上，选择**此用户**，然后键入用户名和密码在**用户**并**密码**框。 新的 COM+ 应用程序将使用此用户帐户运行。 此用户帐户必须为本地 HIS Runtime Users 组的成员。 对于此演练，请使用 BizTalk 服务所使用的同一用户帐户。  

    4.  上**添加应用程序角色**页上，单击**下一步**。  

    5.  上**向角色添加用户**页上，展开**CreatorOwner**，单击**用户**，然后单击**添加**。  

    6.  上**选择用户或组**对话框框中，选择将用于访问大型机的用户帐户。 对于此演练，请添加 UserID 本地帐户。  

        > [!NOTE]
        >  若要通过 TI 组件访问 CICS 事务，则可以使用该 COM+ 应用程序或作为 .NET 远程处理组件宿主的 Web 应用程序。 此演练使用 COM+ 应用程序和 TI 组件的 COM Interop 来访问大型机，以提高性能。  

    7.  上**完成**页上，单击**完成**。  

#### <a name="create-a-remote-environment-to-access-the-mainframe"></a>创建远程环境，以访问大型机  

1.  单击**启动**，依次指向**所有程序**，指向**Microsoft Host Integration Server 2004**，然后单击**TI 管理器**。  

2.  在中**TI 管理器**控制台中，单击**事务集成器 （配置）**，展开**Windows 启动的处理**，右键单击**远程环境**，依次指向**新建**，然后单击**远程环境**。  

    1.  上**欢迎**页上，单击**下一步**。  

    2.  上**配置一个新的远程环境**页上，键入**远程应用程序名称**，然后单击**下一步**。 对于此演练，请使用 Mainframe_TCP 作为名称。  

    3.  上**配置主机环境和编程模型**页上，选择**CICS**有关**目标主机**并**ELM 链接**为**编程模型**，然后单击**下一步**。  

    4.  上**配置终结点 TCP/IP**页上，键入为大型机中的 IP 地址**IP/DNS 地址**框中，然后依次**编辑**若要添加的端口号。 HIS COM 将通过该终结点地址来访问事务。  

    5.  上**完成**页上，单击**完成**。  

#### <a name="create-the-ti-component-for-the-service-oriented-solution"></a>为面向服务的解决方案创建 TI 组件  

1.  单击**启动**，依次指向**所有程序**，指向**Microsoft Host Integration Server 2004**，然后单击**TI 管理器**。  

2.  在中**TI 管理器**控制台中，单击**事务集成器 （配置）**，单击**Windows 启动的处理**，然后单击**对象**. 右键单击**对象**，单击**新建**，然后单击**对象**。  

    1.  上**欢迎**页上，单击**下一步**。  

    2.  上**指定或查找对象**页上，单击**浏览**，在 %BTSSolutionsPath%\SO\MFAccess\HISTIComponent 文件夹中，选择 SOHISTIUsingCOM.TLB，然后单击**下一步**.  

    3.  上**COM 对象的定义环境特征**页上，选择**BTSScn SO TI Component**有关**COM + 应用程序**，然后单击**下一步**.  

    4.  上**定义远程环境**页上，选择在前面的过程中创建的远程环境**远程环境中，然后单击下一步。**  

    5.  上**创建 WIP 对象**页上，单击**下一步**，然后单击**完成**上**完成**页。  

#### <a name="test-the-connectivity-to-the-mainframe"></a>测试与大型机的连接  

1.  在 Windows 资源管理器中，浏览至 %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester 文件夹，然后双击 Interop.SOHISTIUsingCOM.dll.reg 文件。 这将添加 HISTISimpleTester 应用程序的注册表值，以便通过运行库可调用包装 (RCW) 来调用 TI 组件。  

2.  在 Windows 资源管理器中，浏览至 %BTSSolutionsPath%\SO\MFAccess\ 文件夹，然后运行 SetupMFAccess.bat。  

3.  在 Windows 资源管理器中，导航到 %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester\bin\Debug 文件夹，然后运行 BTSScnSOHISTIComponentSimpleTester.exe。  

    -   在 HISTISimpleTester 应用程序中，单击**调用大型机程序-使用 COM**。 这样将从运行在大型机上的 COBOL 应用程序返回五条记录。  

##  <a name="step13"></a> 创建 Web 服务的业务流程的虚拟目录  

1.  在中**Internet 信息服务 (IIS) 管理器**，右键单击**应用程序池**，选择**新建**，然后选择**应用程序池**.  

    1.  上**添加新应用程序池**对话框框中，输入**应用程序池 ID** （任何值），然后单击**确定**。  

    2.  右键单击您刚的应用程序池创建，然后依次**属性**。  

    3.  上**属性**页上，单击**标识**选项卡上，选择**可配置**，输入**用户名**和**密码**，然后单击**确定**。 对于本演练使用 BizTalk 服务正在使用的相同用户帐户。  

    > [!NOTE]
    >  此用户必须有权执行业务流程代理 Web Services，并且必须添加到 BizTalk Server Administrators、SSO Administrators 或 SSO Affiliated Administrators 组中。  

2.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  

     使用**虚拟目录创建向导**，代理 Web 服务适配器版本创建以下虚拟目录：  

     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter  

     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Adapter  

     访问权限 = 读取，运行脚本  

3.  在中**Internet 信息服务 (IIS) 管理器**，展开**Web 站点**展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter，单击**属性**，，然后修改设置，如下所示：  

    1.  在中**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>你在上一步中创建。  

    2.  在中**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，选择**仅集成 Windows 身份验证已启用**，然后清除其他**身份验证访问**复选框。 单击**确定**退出。  

4.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  

     使用**虚拟目录创建向导**，内联版本的 Web 服务的代理创建以下虚拟目录：  

     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline  

     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Inline  

     访问权限 = 读取，运行脚本  

5.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline，单击**属性**，，然后修改设置，如下所示：  

    1.  上**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>你刚刚创建。  

    2.  单击**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，选择**仅集成 Windows 身份验证已启用**，然后清除其他**身份验证访问**复选框。 单击**确定**退出。  

##  <a name="step15"></a> 构建面向服务的解决方案  

-   在命令提示符下，将目录更改为 %btssolutionspath%\so\btssoln，类型`SetupBTSSoln.bat`，然后按 ENTER。 SetupBTSSoln.bat 将执行以下任务：  

    -   创建唯一强名称密钥 (SNK)，用于进行签名的 SO 解决方案的程序集。  

    -   从 SNK 中提取公钥标记，并使用该公钥标记更新绑定文件。  

    -   生成 SO 解决方案。  

    -   在 %BTSSolutionsPath%\Common 文件夹中生成 SSOApplicationConfig。  

##  <a name="step17"></a> 创建 SSO 关联应用程序  

1. 打开命令提示符，然后将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。  

2. 在命令提示符下，使用记事本打开 PendTransAffApp.xml，并对其进行检查。 不需要更改此文件。  

   > [!NOTE]
   >  PendTransAffApp.xml 文件定义了用于挂起事务后端系统的 SSO 关联应用程序 WoodgroveBank.PendingTransactions。 该文件还定义了 SSO 关联应用程序的用户组和管理组。 对于本演练中，使用**BizTalk Application Users**并**BizTalk Server Administrators**。  
   >   
   >  如果你想要为 SSO 关联应用程序使用不同的组，则需要在 Active Directory 中创建 Windows 组 （使用任何名称），然后更改**appAdminAccount**并**appUserAccount**PendTransAffApp.xml 中的节点。 如果执行此操作时，应设置为值**groupApp**的属性**标志**节点为"yes"。  
   >   
   >  有关 SSO 关联应用程序的详细信息，请参阅[SSO 关联应用程序](../core/sso-affiliate-applications.md)。  

3. 在命令提示符下，使用记事本打开 PendTransUserMap.xml 文件，然后进行以下编辑：  

   ```  
   <mapping>  
     <windowsDomain><DomainName></windowsDomain>  
     <windowsUserId><UserID></windowsUserId>  
     <externalUserId><ExternalUserID></externalUserId>  
   </mapping>  
   ```  

   > [!NOTE]
   >  PendTransUserMap.xml 文件包含用于挂起事务后端系统的用户映射。  

   > [!NOTE]
   >  有关**externalUserId**节点，用于挂起事务后端系统的外部用户 ID。 对于此演练，请使用 UserID 作为外部 ID。  

   > [!NOTE]
   >  有关**windowsUserId**节点中，输入用户名称的**externalUserId**将映射到。 可以使用域组和域用户帐户。 此用户必须是将允许其使用挂起事务后端系统的组的成员。 对于此演练，请使用 BizTalk 服务的用户名。  

   > [!NOTE]
   >  有关**windowsDomain**节点中，输入的域名**windowsUserId**。  

4. 在命令提示符下，使用记事本打开 PmntTrckAffApp.xml 文件，并检查该文件的内容。 不需要更改此文件。  

   > [!NOTE]
   >  PmntTrckAffApp.xml 文件定义了用于付款跟踪程序后端系统的 SSO 关联应用程序 WoodgroveBank.PaymentTracker。  

5. 在命令提示符下，使用记事本打开 PmntTrckUserMap.xml 文件，然后进行以下编辑：  

   ```  
   <mapping>  
     <windowsDomain><DomainName></windowsDomain>  
     <windowsUserId><UserID></windowsUserId>  
     <externalUserId><ExternalUserID></externalUserId>  
   </mapping>  
   ```  

   > [!NOTE]
   >  付款跟踪程序 SSO 关联应用程序将用于 MQSeries 适配器，并且所映射的外部用户 ID/密码将通过 MQSeries 标头属性进行发送。 MQSeries 服务器只验证运行 MQSeries 适配器时所使用的 BizTalk 服务帐户。 它不验证任何外部用户凭据。  
   >   
   >  详细了解 SSO 关联应用程序的 MQSeries 适配器，请参阅[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)。  

   > [!NOTE]
   >  PmntTrckUserMap.xml 文件包含用于付款跟踪程序后端系统的 SSO 用户映射。 付款跟踪模拟程序可模拟用户身份验证的成功条件和失败条件。  
   >   
   >  程序成功通过身份验证以字母开头的所有用户 Id **PT** (例如， **PTUserID**)，并且无法进行身份验证不开头的 Id 的任何用户**PT**. 这样，你就能根据要测试的条件来选择适当的用户 ID。 您也可以重复整个**映射**针对每个用户 ID 的节点，并在同一文件中定义多个映射。  

   > [!NOTE]
   >  有关**externalUserId**节点中，输入付款跟踪程序后端系统的外部用户 ID。 对于此演练，请使用 PTUserID 作为外部 ID。  

   > [!NOTE]
   >  有关**windowsUserId**节点中，输入用户名称的**externalUserId**将映射到。 此用户必须是将允许其使用付款跟踪程序后端系统的组的成员。 对于此演练，请使用 BizTalk 服务的用户名。  

   > [!NOTE]
   >  有关**windowsDomain**节点中，输入的域名**windowsUserId**。  

6. 在命令提示符下，使用记事本打开 ConfigStoreApp.xml 文件，然后检查该文件的内容。  

    此文件定义了 SSO 中该方案用于存储配置参数的配置存储应用程序。 其中的某些配置参数包括与 SAP 进行通信时的超时值（适用于适配器版本和内联版本），以及队列管理器的名称和使用内联版本时要使用的队列。 不需要更改此文件。  

7. 在命令提示符下，使用记事本打开 SetConfigValuesInSSO.cmd 文件，并按下表检查和更改文件的内容。  

   > [!NOTE]
   >  此命令文件设置 SSO 数据库中各配置参数的值。 该命令文件的开头包含几个为局部变量赋值的 set 语句。  
   >   
   >  SAPAdapterTimeout、PendingTransactionsAdapterTimeout 和 PaymentTrackingAdapterTimeout 值用于适配器版本中。 其余的值用于内联版本。  

   > [!NOTE]
   >  可以输入""（两个双引号） 标记的默认值\<用户指定\>下表中。  

   |                参数                 |                                                 默认值                                                 |                                                                                                                Description                                                                                                                 |
   |------------------------------------------|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |            SAPAdapterTimeout             |                                                     20000                                                     |                                                                                        对 SAP 后端的请求的最大超时值（毫秒）                                                                                         |
   |             SAPInlineTimeout             |                                                     20000                                                     |                                                                                        对 SAP 后端的请求的最大超时值（毫秒）                                                                                         |
   |            SAPInlineHostName             |                                              \<指定用户\>                                               |                                                                                                          SAP 后端标识符                                                                                                           |
   |          SAPInlineClientNumber           |                                              \<指定用户\>                                               |                                                                                                             SAP 客户端编号                                                                                                              |
   |          SAPInlineSystemNumber           |                                              \<指定用户\>                                               |                                                                                                             SAP 系统编号                                                                                                              |
   |            SAPInlineUserName             |                                              \<指定用户\>                                               |                                                                                             用于连接到 SAP 后端的用户名                                                                                              |
   |            SAPInlinePassword             |                                              \<指定用户\>                                               |                                                                                              用于连接到 SAP 后端的密码                                                                                              |
   |    PendingTransactionsAdapterTimeout     |                                                     20000                                                     |                                                                                 对挂起事务服务器的请求的最大超时值（毫秒）                                                                                 |
   |     PendingTransactionsInlineTimeout     |                                                     20000                                                     |                                                                                 对挂起事务服务器的请求的最大超时值（毫秒）                                                                                 |
   |       PendingTransactionsInlineURL       | https://\<*您的计算机名称*\>/Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions/PendTransWS.asmx |              挂起事务服务的 URL。 \<*你的计算机名*\>必须匹配**公用名**中"创建证书请求"过程。 必须为使用"localhost" \<*您的计算机名称*\>。               |
   | PendingTransactionsInlineSSOAffiliateApp |                                       WoodgroveBank.PendingTransactions                                       |                                                                                                 挂起事务 SSO 应用程序名                                                                                                  |
   |      PaymentTrackingAdapterTimeout       |                                                     20000                                                     |                                                                                   对付款跟踪系统的请求的最大超时值（毫秒）                                                                                   |
   |       PaymentTrackingInlineTimeout       |                                                     20000                                                     |                                                                                   对付款跟踪系统的请求的最大超时值（毫秒）                                                                                   |
   |      PaymentTrackingInlineQManager       |                          \<用户指定\>(通常 QM_\<*您的计算机名称*\>)。                          |                                                                                                        MQSeries 队列管理器名称                                                                                                         |
   | PaymentTrackingInlineMQChannelDefinition |                                  " "（需要输入两个双引号）。                                   | 如果为本地，则此项为空字符串，也可以为远程 MQ 服务器的格式化通道名称。 如果在配置 IBM WebSphere MQ 中保留所有默认设置，则通道定义将 S__\<*您的计算机名称*\>/tcp/&lt\<*您的计算机名称*\>(1414)。 |
   |    PaymentTrackingInlineRequestQueue     |                                            LastPaymentsInputQueue                                             |                                                                                              付款跟踪请求的 MQ 队列名称                                                                                               |
   |    PaymentTrackingInlineResponseQueue    |                                            LastPaymentsOutputQueue                                            |                                                                                              付款跟踪响应的 MQ 队列名称                                                                                              |
   |   PaymentTrackingInlineSSOAffiliateApp   |                                         WoodgroveBank.PaymentTracker                                          |                                                                                                   付款跟踪 SSO 应用程序名                                                                                                    |
   |           StubSAPWebServiceURL           |                http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP/StubSAPWS.asmx                |                                                                                          信用限额 SAP 系统的存根 Web Services URL                                                                                           |


8. 在命令提示符下，运行以下命令以设置 PATH 环境：  

   -   `SET PATH=%PATH%;"%CommonProgramFiles%\Enterprise Single Sign-On"`  

9. 在命令提示符处，运行 CreateInitialConfigInSSO.cmd。 它创建 SSO 关联应用程序、 SSO 配置存储应用程序和关联应用程序的用户映射。 然后，它将执行 SetConfigValuesInSSO.cmd，以便将配置值存储在 SSO 配置存储应用程序中。  

10. 在命令提示符下，运行以下命令以设置挂起事务关联应用程序的用户凭据。 使用\< **DomainName** \>并\< **UserID** \> PendTransUserMap.xml 中定义\<WindowsDomain\> \\< 域名\>。 此命令要求你输入此演练中所使用的外部用户的密码和 UserID。  

    -   `ssomanage -setcredentials <WindowsDomain>\<WindowsUserId> WoodgroveBank.PendingTransactions`  

11. 在命令提示符下，运行以下命令以设置付款跟踪关联应用程序的用户凭据。 使用\< **DomainName** \>并\< **UserID** \>为 PmntTrckUserMap.xml 中定义\<WindowsDomain\> \\< 域名\>。 此命令要求你输入此演练中所使用的外部用户的密码和 PTUserID。  

    > [!NOTE]
    >  付款跟踪模拟程序不验证外部用户凭据。 可以为 PTUserID 输入任何密码。  

    -   `ssomanage -setcredentials < WindowsDomain >\< WindowsUserId > WoodgroveBank.PaymentTracker`  

##  <a name="step19"></a> 为面向服务的解决方案部署 BAM 定义文件  

1. 打开命令提示符，键入以下命令，然后按 Enter 以设置用于查找 BAM 实用工具的路径：  

   - SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"  

2. 在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\BAM，键入以下命令，然后按 Enter：  

   -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  

##  <a name="step21"></a> 部署面向服务的解决方案  

#### <a name="update-the-binding-files-for-the-service-oriented-solution"></a>绑定文件更新为面向服务的解决方案  

1. 在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，使用记事本打开 Deployallbinding.xml，然后进行以下编辑：  

   -   将 SET MGMT_DB_SERVER 和 MBMT_DB 中的服务器名称更改为 BizTalk Server 正在使用的服务器和数据库的名称。  

   -   将 SOLNDIR 变量的值更改为“%BTSSolutionsPath%\SO\BTSSoln”。  

2. 在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Bindings 文件夹。  

3. 对于适配器版本，使用记事本打开 AdapterSOAOrchBindings.xml，然后按如下所述进行编辑：  

   - 替换出现的所有 *_MQ_SERVER_NAME\\*  \_与的 MQSeries 服务器名称。  

   - 替换出现的所有 *_MQ_QMANAGER_NAME\\*  \_与的 MQSeries 队列管理器名称。  

   - 替换出现的所有 *_PT_WS_SERVER_NAME\\*  \_字符串中"\<地址\>https://\_*PT_WS_SERVER_NAME\\* \_"使用部署挂起事务 Web 服务的服务器名称。 服务器名称必须与匹配**公用名**在步骤中，"若要配置 Web 服务器的 SSL"。 不应使用“localhost”。  

   > [!NOTE]
   >  绑定文件 AdapterSOAOrchBindings.xml 为以下项使用存根 Web Services：  
   > 
   > 1. 信用限额后端 SAP 系统。  
   >    2.  用于与付款跟踪后端系统相集成的 MQSeries 适配器。  
   >    3.  用于调用 HIS TI .NET 组件以与大型机后端系统相集成的挂起事务 Web Services。  
   > 
   >    如果不是使用大型机，则必须使用存根 Web Services 为挂起事务系统生成数据。  

4. 对于内联版本，使用记事本打开 InlineSOAOrchBindings.xml，然后按如下所述进行编辑：  

   - 替换出现的所有 *_MQ_SERVER_NAME\\*  \_与的 MQSeries 服务器名称。  

   - 替换出现的所有 *_MQ_QMANAGER_NAME\\*  \_与的 MQSeries 队列管理器名称。  

#### <a name="deploy-the-service-oriented-solution"></a>部署面向服务的解决方案  

-   在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，键入以下命令，然后按 Enter：  

    -   `Deployallbinding.cmd`  

    > [!NOTE]
    >  Deployallbinding.cmd 将创建名为 BTSScn.SO.CustomerService 的 BizTalk 应用程序，并为适配器版本和内联版本导入绑定文件。  

##  <a name="step23"></a> 当大型机不可用时配置存根挂起事务 Web Services  

#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-adapter-version-without-a-mainframe"></a>配置存根挂起事务 Web 服务 （适用于使用而无需在大型机的适配器版本）  

1.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  

     使用**虚拟目录创建向导**，创建以下虚拟目录为存根挂起事务 Web 服务适配器版本：  

     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  

     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  

     访问权限 = 读取，运行脚本  

2.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions，单击**属性**，然后修改设置，请按如下所示使用**属性**对话框。  

    1.  在中**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>在步骤中，"若要创建的虚拟创建目录在 IIS 中的解决方案"。  

    2.  在中**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**分组框中，并选择**启用匿名访问**. 单击**确定**退出。  

3.  在中**BizTalk Server 管理控制台**，展开**BizTalk 组**，展开**应用程序**、 BTSScn.SO.CustomerService 及**发送端口**，右键单击**PendingTransactionSolicitResponsePort**，然后单击**属性**。  

    1.  在中**常规**页上，单击**配置**以显示**传输属性**对话框框中，并修改**Web 服务 URL**到存根挂起事务 Web 服务，例如：  

         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  

    2.  关闭所有对话框。  

#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-inline-version-without-a-mainframe"></a>配置存根挂起事务 Web 服务 （适用于使用而无需在大型机的内联版本）  

1.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  

     使用**虚拟目录创建向导**，创建以下虚拟目录为存根挂起事务 Web 服务适配器版本：  

     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  

     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  

     访问权限 = 读取，运行脚本  

2.  在中**Internet 信息服务 (IIS) 管理器**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions，单击**属性**，，然后修改设置，如下所示：  

    1.  在中**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>在步骤中，"若要创建的虚拟创建目录在 IIS 中的解决方案"。  

    2.  在中**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**分组框中，并选择**启用匿名访问**. 单击**确定**退出。  

3.  打开命令提示符，然后将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。  

4.  在命令提示符下，打开 SetConfigValuesInSSO.cmd 文件使用记事本，然后将值设置**PendingTransactionsInlineURL**为存根挂起事务 Web 服务的 URL。  

    -   `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  

5.  在命令提示符下，键入 `SetConfigValuesInSSO.cmd`，然后按 Enter。  

##  <a name="step25"></a> 启动服务面向解决方案  

1.  打开命令提示符，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，键入以下命令，然后按 Enter 以启动内联版本和适配器版本的所有业务流程：  

    -   `startAll.vbs`  

2.  运行面向服务的解决方案。 有关运行该解决方案的详细信息，请参阅[如何运行面向服务的解决方案](../core/how-to-run-the-service-oriented-solution.md)。  

## <a name="next-steps"></a>后续步骤  
 测试中的面向服务的解决方案的内联和适配器版本[如何运行面向服务的解决方案](../core/how-to-run-the-service-oriented-solution.md)。  

## <a name="see-also"></a>请参阅  
 [然后再安装面向服务的解决方案](../core/before-installing-the-service-oriented-solution.md)   
 [如何安装该服务的存根版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [面向服务的解决方案的开发人员计算机设置](../core/developer-machine-setup-for-the-service-oriented-solution.md)