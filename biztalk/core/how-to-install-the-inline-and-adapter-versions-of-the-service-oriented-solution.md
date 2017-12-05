---
title: "安装内联和服务的适配器版本面向解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6050cfe9-4e94-4a55-8b24-fbcc74d9e8f4
caps.latest.revision: "97"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d648db0f3a7c6ad4dccdbcc7555fc3c0727568c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution"></a>如何安装面向服务的解决方案的内联版本和适配器版本
以下步骤将说明如何准备计算机以安装面向服务的解决方案的内联版本和适配器版本，以及如何在此计算机上安装该解决方案：  
  
> [!NOTE]
>  - 面向的解决方案位于文件夹中的服务\< *BizTalk Server 安装文件夹*\>\SDK\Scenarios\SO。  
>  - 如果没有大型机可用于该解决方案，则可以修改端口绑定以使用存根 Web Services 来模拟挂起事务。 该 Web Services 将在本地生成事务以模拟大型机事务。  
  
##  <a name="step1"></a>准备计算机以安装服务面向解决方案的适配器和内联版本  
  
1.  如果你安装 Windows SharePoint Services，(root) 的默认网站从排除 Windows SharePoint Services 管理路径，如下所示： 单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。  
  
    1.  下**虚拟服务器配置**，选择**配置虚拟服务器设置**。  
  
    2.  上**虚拟服务器列表**页上，单击**Default Web Site**。  
  
    3.  上**虚拟服务器设置**页上，单击**定义管理路径**。  
  
    4.  在**包含的路径**部分**定义托管路径**页上，选择**根**，然后单击**删除所选的路径**。  
  
    5.  在命令提示符下，执行 IISReset。  
  
2.  单击**启动**，指向**所有程序**，指向**管理工具**，单击**计算机管理**控制台，并将到本地管理员组的 BizTalk 服务帐户。  
  
3.  从计算机注销，然后使用 BizTalk 服务帐户登录到该计算机。  
  
4.  在命令提示符下，键入以下命令，然后按 Enter 以设置 %BTSSolutionsPath% 环境变量。 然后，退出命令提示符。  
  
    -   setx BTSSolutionsPath [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"  
  
        > [!NOTE]
        >  如果使用的是 64 位计算机，则使用 %ProgramFiles(x86)% 而不是 %ProgramFiles%。  
  
        > [!NOTE]
        >  有关 SETX 命令的详细信息，请参阅 Microsoft TechNet 网站，网址[http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)。  
  
##  <a name="step3"></a>删除服务面向解决方案的存根 （stub） 版本  
  
1.  打开**BizTalk Server 管理控制台**，如下所示： 单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在**BizTalk Server 管理控制台**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**的应用程序**，右键单击**BTSScn.SO.CustomerService**，然后单击**停止**。 在**停止应用程序**对话框中，选择**句号-终止实例**，然后单击**停止**。  
  
    > [!NOTE]
    >  若要安装内联版本和适配器版本，则无需删除存根版本。 如果要将所有版本放在一起，则应跳过此步骤。  
  
3.  打开命令提示符，键入以下命令，然后按 Enter。 此命令会将默认脚本主机更改为 CScript.exe：  
  
    -   `cscript /H:CScript`  
  
4.  在命令提示符下，将当前目录更改为 %BTSSolutonsPath%\SO\BTSSoln\Scripts 文件夹，键入以下命令，然后按 Enter：  
  
    -   `UnEnlistStub.vbs`  
  
5.  在命令提示符下键入以下命令，，然后按 ENTER:  
  
    -   `UndeployStub.vbs`  
  
6.  在命令提示符下运行以下命令  
  
     SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"  
  
     此命令将设置用于查找 BAM 实用工具的路径。  
  
    > [!NOTE]
    >  如果你使用的 64 位计算机，键入`%ProgramFiles(x86)%`而不是`%ProgramFiles%`。  
  
7.  在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\BAM，然后运行以下命令：  
  
    -   `bm remove-all -DefinitionFile:ServiceLevelTracking.xml`  
  
8.  在命令提示符下，将目录更改为\<*企业单一登录安装目录*\>，然后运行以下命令：  
  
    -   `ssomanage -tickets no no`  
  
9. 在命令提示符下，运行以下命令以删除 WoodgroveBank.CustomerService SSO 关联应用程序：  
  
    -   `ssomanage -deleteapp WoodgroveBank.CustomerService`  
  
10. 在命令提示符下，运行以下命令以删除存根版本所使用的网站： 有关 iisvdir.vbs 的详细信息，请参阅 Microsoft TechNet 网站，网址[http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830)。  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker`  
  
11. 启动 Internet 信息服务 (IIS) 管理器，如下所示： 单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) 管理器**。  
  
    -   展开**应用程序池**，右键单击创建为以前的 Web 应用程序的应用程序池，单击**删除**，然后单击**确定**入确认对话框。  
  
12. 单击**启动**，指向**控制面板**，单击**添加或删除程序**，然后卸载 IBM WebSphere MQ 客户端适用于 Windows 的。  
  
13. 启动**Visual Studio 命令提示符**，然后运行以下命令以删除为存根 （stub） 版本安装 amqmdnet.dll。  
  
    -   `gacutil /u amqmdnet`  
  
##  <a name="step5"></a>准备服务面向解决方案访问的后端系统  
  
1.  在本地计算机上安装 Windows Server IBM WebSphere MQ。  
  
    1.  保留所有默认设置。 设置**默认配置**末尾**准备 WebSphere MQ 向导**。 队列管理器命名为 QM_\<*您的计算机名称*\>。  
  
    2.  安装 Fix Pack 10 (CSD10)。 保留所有默认设置。  
  
2.  安装 MQSeries 代理。  
  
    1.  重新运行 BizTalk Server 安装程序。  
  
    2.  上**程序维护**页上，选择**修改**，然后单击**下一步**。  
  
    3.  上**组件安装**页上，展开**其他软件**节点，，然后选择**MQSeries 代理**。  
  
    4.  上**完成**页上，请确保**启动 BizTalk MQSeries 代理配置向导**未选中。  
  
    > [!NOTE]
    >  **MQSeries 代理**安装适用于 Windows 的复选框仅在 IBM WebSphere MQ 后激活。  
  
3.  打开**Visual Studio 命令提示符**，将目录更改为\< *IBM MQSeries 安装目录*\>\bin 文件夹，然后运行以下命令：  
  
    -   `gacutil /i amqmdnet.dll`  
  
4.  安装 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]如果你想要安装 Microsoft 主机集成 Server 2004 访问大型机。 在安装程序中，在**选项**页上，选择**Visual C#.NET**，然后清除其他组件复选框。 你不需要安装比其他组件**Visual C#.NET**。  
  
    > [!NOTE]
    >  主机集成 Server 2004 中的 TI 设计器需要[!INCLUDE[btsVStudioNet2003](../includes/btsvstudionet2003-md.md)]。  
  
5.  如果具有要访问的大型机 ， 则安装并配置 Microsoft Host Integration Server 2004 。 保留所有默认设置。  
  
#### <a name="create-the-mqseries-queues"></a>创建 MQSeries 队列  
  
1.  打开 WebSphere MQ 资源管理器中，展开**队列管理器**，然后展开你要在其中创建队列的队列管理器。 通常情况下，队列管理器命名为 QM_\<*您的计算机名称*\>。  
  
2.  在 WebSphere MQ 资源管理器中，右键单击**队列**，指向**新建**，单击**本地队列**，然后创建的适配器版本的以下本地队列解决方案：  
  
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
  
#### <a name="complete-configuration-of-the-mqseries-adapter"></a>要完成的 MQSeries 适配器配置  
  
1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk MQSeries 代理配置向导**。  
  
2.  上**欢迎**页上，单击**下一步**。  
  
3.  上**应用程序标识**页上，选择**此用户**，然后输入用户名和密码。 MQSeries 代理的 COM+ 应用程序将使用此用户帐户运行。 对于此演练，请使用 BizTalk 服务所使用的同一用户帐户。 如果不是，用户帐户用于承载 MQSeries 适配器的 BizTalk 服务必须可向添加**CreatorOwner** COM + 应用程序的角色。  
  
4.  单击**是**上**MQSConfigWiz**对话框中，如果系统提示你在上一步中输入的用户帐户具有管理权限。  
  
5.  上**名称的角色**页上，单击**下一步**。  
  
6.  上**创建 MQSAgent COM + 应用程序**页上，单击**下一步**，然后单击**完成**上**完成**页。  
  
#### <a name="configure-the-mainframe-cics-application"></a>配置大型机 CICS 应用程序  
  
1.  使用记事本，打开位于 %BTSSolutionsPath%\SO\MFAccess\HISTIComponent 文件夹中的 bizcbl.txt 及其“副件”(MainFrameProgramVTCS2Description.txt)，然后检查这两个文件的内容。  
  
    -   Bizcbl.txt 包括 COBOL 过程，该过程可根据帐户编号输入返回随机的帐户语句。  
  
    -   MainFrameProgramVTCS2Descriptoin.txt 包含用于说明输入和输出数据信息的 COMMAREA。 COMMAREA 是用于在被调用的程序和调用方程序之间来回传递数据的连续内存块。  
  
    > [!NOTE]
    >  印书籍还可用于生成与插件 TI 设计器中使用 Visual Studio 的事务系统集成商 (TI) 元数据文件。  
  
    > [!NOTE]
    >  尽管以下步骤对于成功部署是至关紧要的，但 BizTalk Server 开发人员通常不执行这些步骤。 必须依赖大型机人员才可正确配置大型机环境。 大多数的大型机环境中通常都安装了此演练所需的软件。 有关最小大型机操作系统环境的详细信息，请参阅 Host Integration Server 文档。  
  
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
  
##  <a name="step7"></a>配置安全套接字层 (SSL) 的 Web 服务器  
  
#### <a name="install-certificate-services"></a>安装证书服务  
  
1.  单击**启动**，指向**控制面板**，然后单击**添加或删除程序**。  
  
2.  在**添加或删除程序**对话框中，单击**添加/删除 Windows 组件**。  
  
3.  在**Windows 组件向导**，选择**证书服务**，单击**下一步**，然后按照屏幕说明完成安装。  
  
#### <a name="create-a-certificate-request"></a>创建一个证书请求  
  
1.  在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，单击**属性**单击**目录安全性**选项卡上，并依次**服务器证书**。  
  
2.  上**欢迎**页**Web 服务器证书向导**，单击**下一步**。  
  
3.  上**服务证书**页上，选择**创建新证书**，然后单击**下一步**。  
  
4.  上**延迟或立即请求**页上，单击**现在，准备请求，但稍后发送**，然后单击**下一步**。  
  
5.  上**名称和安全设置**页上，保留所有默认设置，然后单击**下一步**。  
  
6.  上**组织信息**页上，键入你的公司组织和组织单位名称，然后单击**下一步**。  
  
7.  上**站点的公用名称**页上，键入你的计算机名称**公用名**框中，并依次**下一步**。  
  
8.  上**的地理位置信息**页上，填写你的地理位置信息，然后单击**下一步**。  
  
9. 上**证书请求文件名称**页上，键入`c:\certreq.txt`中**文件名**框中，并依次**下一步**。  
  
10. 上**请求文件摘要**页上，单击**下一步**，然后单击**完成**上**完成**页。  
  
#### <a name="submit-the-certificate-request-to-the-certification-authority"></a>提交到证书颁发机构证书请求  
  
1.  在 Internet Explorer，在地址框中，键入`http://localhost/certsrvt`，然后按 ENTER。  
  
2.  上**欢迎**页上，单击**请求证书**，然后单击**高级的证书申请**上**请求证书**页。  
  
3.  上**高级证书申请**页上，单击**提交证书申请，使用 base64 编码的 PKCS #10 文件或使用 base64 编码的 PKCS #7 文件的续订请求**。  
  
4.  从"若要创建证书请求"，将其粘贴到过程中创建 c:\certreq.txt 复制的所有文本**保存请求**框**提交证书申请或续订申请**页，，然后单击**提交**。  
  
#### <a name="issue-a-certificate-using-certification-authority-management-tool"></a>颁发证书使用证书颁发机构管理工具  
  
1.  单击**启动**，指向**管理工具**，然后单击**证书颁发机构**。  
  
2.  在**证书颁发机构**控制台，展开证书颁发机构的名称，展开**挂起请求**，右键单击在上一步骤中，点提交证书请求到**所有任务**，然后单击**问题**。  
  
3.  关闭**证书颁发机构**控制台。  
  
#### <a name="download-the-certificate-to-the-web-server"></a>下载与 Web 服务器的证书  
  
1.  在 Internet Explorer，在地址框中，键入`http://localhost/certsrvt`，然后按 ENTER。  
  
2.  上**欢迎**页上，单击**查看挂起的证书申请的状态**。  
  
3.  上**查看挂起的证书申请的状态**页上，单击证书**请求**你在"创建证书请求"的过程中创建。  
  
4.  上**颁发证书**页上，选择编码方案，任一，然后单击**下载证书**。  
  
5.  上**安全警告**对话框中，单击**保存**，然后将证书保存为 c:\certnew.cer。  
  
#### <a name="install-the-certificate-to-the-web-server"></a>将证书安装到 Web 服务器  
  
1.  在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**为其创建证书请求，然后单击**属性**。  
  
2.  上**属性**对话框中，单击**目录安全性**选项卡上，并依次**服务器证书**。  
  
3.  上**欢迎**页**Web 服务器证书向导**，单击**下一步**。  
  
4.  上**挂起的证书申请**页上，选择**处理挂起的请求和安装证书**，然后单击**下一步**。  
  
5.  上**处理挂起的请求**页上，键入`c:\certnew.cer`中**路径和文件名**文本中，然后单击**下一步**。  
  
6.  单击**下一步**上**SSL 端口**页上，单击**下一步**上**证书 Summery**页，，然后单击**完成**上**确认**页。  
  
    > [!NOTE]
    >  在此演练中，不需要将服务器证书安装到本地计算机上的“受信任的根证书颁发机构”存储区，因为证书服务和 Web 服务器均安装在同一台计算机上。  
  
##  <a name="step9"></a>创建后端系统的 Web 服务  
  
1.  在**Internet Information Services (IIS) Manager**，右键单击**应用程序池**，选择**新建**，然后选择**应用程序池**.  
  
    > [!NOTE]
    >  面向服务的解决方案将通过此 Web Services 访问大型机。  
  
2.  上**添加新的应用程序池**对话框框中，输入**应用程序池 ID** （任意值），然后单击**确定**。  
  
3.  在**Internet Information Services (IIS) Manager**，右键单击你刚的应用程序池创建，，然后选择**属性**。  
  
4.  上**属性**页上，单击**标识**选项卡上，选择**可配置**，输入**用户名**和**密码**，然后单击**确定**。 对于此演练，请使用 BizTalk 服务所使用的同一用户帐户。  
  
#### <a name="create-the-pendingtransactions-web-service-for-runtime"></a>创建运行时的 PendingTransactions Web 服务  
  
1.  在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  
  
     使用**虚拟目录创建向导**，创建以下虚拟目录存根 （stub） SAP Web 服务：  
  
     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions  
  
     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\MFAccess\PendingTransactions  
  
     访问权限 = 读取，运行脚本  
  
2.  在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions，，然后单击**属性**。  
  
    1.  在**目录安全性**选项卡上，单击**编辑**修改**身份验证和访问控制**。 选择**基本身份验证 （以明文形式发送密码）**，并清除其他**身份验证访问**复选框。 单击**确定**关闭**身份验证方法**对话框。  
  
    2.  在**目录安全性**选项卡上，单击**编辑**下**安全通信**组框中，，然后检查**要求安全通道 (SSL)**中**安全通信**对话框。  
  
    3.  在**虚拟目录**选项卡上，设置**应用程序池**到你在"创建新的 IIS 应用程序池的挂起的事务 Web 服务"的过程中创建的应用程序池。  
  
#### <a name="create-the-pendingtransactions-web-service-for-development-environment"></a>创建开发环境 PendingTransactions Web 服务  
  
1.  在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  
  
     使用**虚拟目录创建向导**，创建以下虚拟目录存根 （stub） SAP Web 服务：  
  
     别名 = PendingTransactions  
  
     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\MFAccess\PendingTransactions  
  
     访问权限 = 读取，运行脚本  
  
2.  在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击 PendingTransactions，，然后单击**属性**。  
  
    1.  在**目录安全性**选项卡上，单击**编辑**修改**身份验证和访问控制**。 选择**启用匿名访问**。 单击**确定**退出。  
  
        > [!NOTE]
        >  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 将使用用于开发环境的 PendingTransactions Web 应用程序。 对于生产环境，则不需要此 Web 应用程序。  
  
    2.  在**虚拟目录**选项卡上，设置**应用程序池**到你在"创建新的 IIS 应用程序池的挂起的事务 Web 服务"的过程中创建的应用程序池。  
  
#### <a name="create-the-stub-sap-web-service"></a>创建存根 （stub) SAP Web 服务  
  
1.  在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  
  
     使用**虚拟目录创建向导**，创建以下虚拟目录存根 （stub） SAP Web 服务：  
  
     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP  
  
     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP  
  
     访问权限 = 读取，运行脚本  
  
2.  在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP，单击**属性**，，然后修改设置，如下所示：  
  
    1.  在**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>你在"创建新的 IIS 的过程中创建应用程序池的挂起的事务 Web 服务"。  
  
    2.  在**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，，然后选择**启用匿名访问**. 单击**确定**退出。  
  
##  <a name="step11"></a>为服务面向解决方案创建 TI 组件  
  
#### <a name="create-a-com-application-for-the-ti-component"></a>创建用于 TI 组件的 COM + 应用程序  
  
1.  在命令提示符下，运行 %systemroot%\system32\com\comexp.msc。  
  
2.  在**组件服务**控制台中，展开**组件服务**，展开**计算机**，展开**我的电脑**，右键单击**COM + 应用程序**，指向**新建**，然后单击**应用程序**。  
  
    1.  上**欢迎**页上，单击**下一步**，然后单击**创建空的应用程序**上**安装或创建新的应用程序**页。  
  
    2.  类型`BTSScn SO TI Component`中**输入新的应用程序的名称**框中，选择**服务器应用程序**作为**激活类型**，然后单击**下一步**.  
  
    3.  在**帐户**组框**设置应用程序标识**页上，选择**此用户**，然后键入用户名和密码在**用户**和**密码**框。 新的 COM+ 应用程序将使用此用户帐户运行。 此用户帐户必须为本地 HIS Runtime Users 组的成员。 对于此演练，请使用 BizTalk 服务所使用的同一用户帐户。  
  
    4.  上**添加应用程序角色**页上，单击**下一步**。  
  
    5.  上**向角色添加用户**页上，展开**CreatorOwner**，单击**用户**，然后单击**添加**。  
  
    6.  上**选择用户或组**对话框框中，选择将用于访问大型机的用户帐户。 对于此演练，请添加 UserID 本地帐户。  
  
        > [!NOTE]
        >  若要通过 TI 组件访问 CICS 事务，则可以使用该 COM+ 应用程序或作为 .NET 远程处理组件宿主的 Web 应用程序。 此演练使用 COM+ 应用程序和 TI 组件的 COM Interop 来访问大型机，以提高性能。  
  
    7.  上**完成**页上，单击**完成**。  
  
#### <a name="create-a-remote-environment-to-access-the-mainframe"></a>创建一个远程的环境，以访问主机  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft 主机集成 Server 2004**，然后单击**TI Manager**。  
  
2.  在**TI Manager**控制台中，单击**事务系统集成商 （配置）**，展开**Windows 启动处理**，右键单击**远程环境**，指向**新建**，然后单击**远程环境**。  
  
    1.  上**欢迎**页上，单击**下一步**。  
  
    2.  上**配置一个新的远程环境**页上，键入**远程应用程序名称**，然后单击**下一步**。 对于此演练，请使用 Mainframe_TCP 作为名称。  
  
    3.  上**配置宿主环境和编程模型**页上，选择**CICS**为**目标主机**和**榆树链接**为**编程模型**，然后单击**下一步**。  
  
    4.  上**配置终结点 TCP/IP**页上，键入你大型机中的 IP 地址**IP/DNS 地址**框中，并依次**编辑**若要添加的端口号。 HIS COM 将通过该终结点地址来访问事务。  
  
    5.  上**完成**页上，单击**完成**。  
  
#### <a name="create-the-ti-component-for-the-service-oriented-solution"></a>为面向服务的解决方案创建 TI 组件  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft 主机集成 Server 2004**，然后单击**TI Manager**。  
  
2.  在**TI Manager**控制台中，单击**事务系统集成商 （配置）**，单击**Windows 启动处理**，然后单击**对象**. 右键单击**对象**，单击**新建**，然后单击**对象**。  
  
    1.  上**欢迎**页上，单击**下一步**。  
  
    2.  上**指定或查找对象**页上，单击**浏览**，在 %BTSSolutionsPath%\SO\MFAccess\HISTIComponent 文件夹中，选择 SOHISTIUsingCOM.TLB，然后单击**下一步**.  
  
    3.  上**定义 COM 对象的环境特征**页上，选择**BTSScn 因此 TI 组件**为**COM + 应用程序**，然后单击**下一步**.  
  
    4.  上**定义远程环境**页上，选择你在前面的过程中创建的远程环境**远程环境中，然后单击下一步。**  
  
    5.  上**WIP 对象创建**页上，单击**下一步**，然后单击**完成**上**完成**页。  
  
#### <a name="test-the-connectivity-to-the-mainframe"></a>测试到大型机连接  
  
1.  在 Windows 资源管理器中，浏览至 %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester 文件夹，然后双击 Interop.SOHISTIUsingCOM.dll.reg 文件。 这将添加 HISTISimpleTester 应用程序的注册表值，以便通过运行库可调用包装 (RCW) 来调用 TI 组件。  
  
2.  在 Windows 资源管理器中，浏览至 %BTSSolutionsPath%\SO\MFAccess\ 文件夹，然后运行 SetupMFAccess.bat。  
  
3.  在 Windows 资源管理器中，导航到 %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester\bin\Debug 文件夹，然后运行 BTSScnSOHISTIComponentSimpleTester.exe。  
  
    -   在 HISTISimpleTester 应用程序中，单击**调用大型机程序-使用 COM**。 这样将从运行在大型机上的 COBOL 应用程序返回五条记录。  
  
##  <a name="step13"></a>创建 Web 服务的业务流程的虚拟目录  
  
1.  在**Internet Information Services (IIS) Manager**，右键单击**应用程序池**，选择**新建**，然后选择**应用程序池**.  
  
    1.  上**添加新的应用程序池**对话框框中，输入**应用程序池 ID** （任意值），然后单击**确定**。  
  
    2.  右键单击你刚的应用程序池创建，，然后选择**属性**。  
  
    3.  上**属性**页上，单击**标识**选项卡上，选择**可配置**，输入**用户名**和**密码**，然后单击**确定**。 对于本演练使用 BizTalk 服务正在使用的相同用户帐户。  
  
    > [!NOTE]
    >  此用户必须有权执行业务流程代理 Web Services，并且必须添加到 BizTalk Server Administrators、SSO Administrators 或 SSO Affiliated Administrators 组中。  
  
2.  在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  
  
     使用**虚拟目录创建向导**，为代理的适配器版本的 Web 服务创建以下虚拟目录：  
  
     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter  
  
     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Adapter  
  
     访问权限 = 读取，运行脚本  
  
3.  在**Internet Information Services (IIS) Manager**，展开**网站，**展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter，单击**属性**，，然后修改设置，如下所示：  
  
    1.  在**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>你在上一步中创建。  
  
    2.  在**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，选择**仅集成 Windows 身份验证启用**，然后清除其他**身份验证访问**复选框。 单击**确定**退出。  
  
4.  在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  
  
     使用**虚拟目录创建向导**，为代理的内联版本的 Web 服务创建以下虚拟目录：  
  
     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline  
  
     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Inline  
  
     访问权限 = 读取，运行脚本  
  
5.  在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline，单击**属性**，，然后修改设置，如下所示：  
  
    1.  上**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>你刚创建。  
  
    2.  单击**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，选择**仅集成 Windows 身份验证启用**，然后清除其他**身份验证访问**复选框。 单击**确定**退出。  
  
##  <a name="step15"></a>生成面向服务的解决方案  
  
-   在命令提示符下，将目录更改为 %btssolutionspath%\so\btssoln，类型`SetupBTSSoln.bat`，然后按 ENTER。 SetupBTSSoln.bat 将执行以下任务：  
  
    -   创建唯一的强名称密钥 (SNK) 进行签名等解决方案的程序集。  
  
    -   从 SNK 中提取公钥标记，并使用该公钥标记更新绑定文件。  
  
    -   生成 SO 解决方案。  
  
    -   在 %BTSSolutionsPath%\Common 文件夹中生成 SSOApplicationConfig。  
  
##  <a name="step17"></a>创建 SSO 关联应用程序  
  
1.  打开命令提示符，然后将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。  
  
2.  在命令提示符下，使用记事本打开 PendTransAffApp.xml，并对其进行检查。 不需要更改此文件。  
  
    > [!NOTE]
    >  PendTransAffApp.xml 文件定义了用于挂起事务后端系统的 SSO 关联应用程序 WoodgroveBank.PendingTransactions。 该文件还定义了 SSO 关联应用程序的用户组和管理组。 对于本演练中，使用**BizTalk 应用程序用户**和**BizTalk Server Administrators**。  
    >   
    >  如果你想要为 SSO 关联应用程序使用不同的组，则需要 Active Directory 中创建 Windows 组 （使用任何名称），然后更改**appAdminAccount**和**appUserAccount**PendTransAffApp.xml 中的节点。 如果执行此操作时，应将值设置**groupApp**属性**标志**节点为"yes"。  
    >   
    >  SSO 关联应用程序有关的详细信息，请参阅[SSO Affiliate 应用程序](../core/sso-affiliate-applications.md)。  
  
3.  在命令提示符下，使用记事本打开 PendTransUserMap.xml 文件，然后进行以下编辑：  
  
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
    >  有关**externalUserId**节点，待执行事务后端系统使用的外部用户 ID。 对于此演练，请使用 UserID 作为外部 ID。  
  
    > [!NOTE]
    >  有关**windowsUserId**节点，输入用户将其命名**externalUserId**将映射到。 可以使用域组和域用户帐户。 此用户必须是将允许其使用挂起事务后端系统的组的成员。 对于此演练，请使用 BizTalk 服务的用户名。  
  
    > [!NOTE]
    >  有关**windowsDomain**节点，输入的域名称**windowsUserId**。  
  
4.  在命令提示符下，使用记事本打开 PmntTrckAffApp.xml 文件，并检查该文件的内容。 不需要更改此文件。  
  
    > [!NOTE]
    >  PmntTrckAffApp.xml 文件定义了用于付款跟踪程序后端系统的 SSO 关联应用程序 WoodgroveBank.PaymentTracker。  
  
5.  在命令提示符下，使用记事本打开 PmntTrckUserMap.xml 文件，然后进行以下编辑：  
  
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
    >  有关 SSO 的详细信息相关联 MQSeries 适配器的应用程序，请参阅[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)。  
  
    > [!NOTE]
    >  PmntTrckUserMap.xml 文件包含用于付款跟踪程序后端系统的 SSO 用户映射。 付款跟踪模拟程序可模拟用户身份验证的成功条件和失败条件。  
    >   
    >  程序成功进行身份验证以字母开头的所有用户 Id **PT** (例如， **PTUserID**)，并且无法进行身份验证不始于的 Id 的任何用户**PT**. 这样，你就能根据要测试的条件来选择适当的用户 ID。 您也可以重复整个**映射**针对每个用户 ID 的节点并在同一个文件中定义的多个映射。  
  
    > [!NOTE]
    >  有关**externalUserId**节点，外部用户 ID 输入付款跟踪器后端系统。 对于此演练，请使用 PTUserID 作为外部 ID。  
  
    > [!NOTE]
    >  有关**windowsUserId**节点，输入用户将其命名**externalUserId**将映射到。 此用户必须是将允许其使用付款跟踪程序后端系统的组的成员。 对于此演练，请使用 BizTalk 服务的用户名。  
  
    > [!NOTE]
    >  有关**windowsDomain**节点，输入的域名称**windowsUserId**。  
  
6.  在命令提示符下，使用记事本打开 ConfigStoreApp.xml 文件，然后检查该文件的内容。  
  
     此文件定义了 SSO 中该方案用于存储配置参数的配置存储应用程序。 其中的某些配置参数包括与 SAP 进行通信时的超时值（适用于适配器版本和内联版本），以及队列管理器的名称和使用内联版本时要使用的队列。 不需要更改此文件。  
  
7.  在命令提示符下，使用记事本打开 SetConfigValuesInSSO.cmd 文件，并按下表检查和更改文件的内容。  
  
    > [!NOTE]
    >  此命令文件设置 SSO 数据库中各配置参数的值。 该命令文件的开头包含几个为局部变量赋值的 set 语句。  
    >   
    >  SAPAdapterTimeout、PendingTransactionsAdapterTimeout 和 PaymentTrackingAdapterTimeout 值用于适配器版本中。 其余的值用于内联版本。  
  
    > [!NOTE]
    >  你可以输入""（两个双引号） 有关标记的默认值\<用户指定\>下表中。  
  
    |参数|默认值|Description|  
    |---------------|-------------------|-----------------|  
    |SAPAdapterTimeout|20000|对 SAP 后端的请求的最大超时值（毫秒）|  
    |SAPInlineTimeout|20000|对 SAP 后端的请求的最大超时值（毫秒）|  
    |SAPInlineHostName|\<指定用户\>|SAP 后端标识符|  
    |SAPInlineClientNumber|\<指定用户\>|SAP 客户端编号|  
    |SAPInlineSystemNumber|\<指定用户\>|SAP 系统编号|  
    |SAPInlineUserName|\<指定用户\>|用于连接到 SAP 后端的用户名|  
    |SAPInlinePassword|\<指定用户\>|用于连接到 SAP 后端的密码|  
    |PendingTransactionsAdapterTimeout|20000|对挂起事务服务器的请求的最大超时值（毫秒）|  
    |PendingTransactionsInlineTimeout|20000|对挂起事务服务器的请求的最大超时值（毫秒）|  
    |PendingTransactionsInlineURL|https://\<*您的计算机名称*\>/Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions/PendTransWS.asmx|挂起事务服务的 URL。 \<*你的计算机名*\>必须匹配**公用名**中"创建证书请求"的过程。 您必须对不使用"localhost" \<*您的计算机名称*\>。|  
    |PendingTransactionsInlineSSOAffiliateApp|WoodgroveBank.PendingTransactions|挂起事务 SSO 应用程序名|  
    |PaymentTrackingAdapterTimeout|20000|对付款跟踪系统的请求的最大超时值（毫秒）|  
    |PaymentTrackingInlineTimeout|20000|对付款跟踪系统的请求的最大超时值（毫秒）|  
    |PaymentTrackingInlineQManager|\<用户指定\>(通常 QM_\<*您的计算机名称*\>)。|MQSeries 队列管理器名称|  
    |PaymentTrackingInlineMQChannelDefinition|" "（需要输入两个双引号）。|如果为本地，则此项为空字符串，也可以为远程 MQ 服务器的格式化通道名称。 如果在配置 IBM WebSphere MQ 保留所有默认设置，通道定义将 S__\<*您的计算机名称*\>/TCP/\<*您的计算机名称*\>(1414)。|  
    |PaymentTrackingInlineRequestQueue|LastPaymentsInputQueue|付款跟踪请求的 MQ 队列名称|  
    |PaymentTrackingInlineResponseQueue|LastPaymentsOutputQueue|付款跟踪响应的 MQ 队列名称|  
    |PaymentTrackingInlineSSOAffiliateApp|WoodgroveBank.PaymentTracker|付款跟踪 SSO 应用程序名|  
    |StubSAPWebServiceURL|http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP/StubSAPWS.asmx|信用限额 SAP 系统的存根 Web Services URL|  
  
8.  在命令提示符下，运行以下命令以设置 PATH 环境：  
  
    -   `SET PATH=%PATH%;"%CommonProgramFiles%\Enterprise Single Sign-On"`  
  
9. 在命令提示符下运行 CreateInitialConfigInSSO.cmd。 它将创建 SSO Affiliate 应用程序、 SSO 配置存储应用程序和关联应用程序的用户映射。 然后，它将执行 SetConfigValuesInSSO.cmd，以便将配置值存储在 SSO 配置存储应用程序中。  
  
10. 在命令提示符下，运行以下命令以设置挂起事务关联应用程序的用户凭据。 使用\< **DomainName** \>和\< **UserID** \>中为 PendTransUserMap.xml 定义\<WindowsDomain\> \\< WindowsUserId\>。 此命令要求你输入此演练中所使用的外部用户的密码和 UserID。  
  
    -   `ssomanage -setcredentials <WindowsDomain>\<WindowsUserId> WoodgroveBank.PendingTransactions`  
  
11. 在命令提示符下，运行以下命令以设置付款跟踪关联应用程序的用户凭据。 使用\< **DomainName** \>和\< **UserID** \>中为 PmntTrckUserMap.xml 定义\<WindowsDomain\> \\< WindowsUserId\>。 此命令要求你输入此演练中所使用的外部用户的密码和 PTUserID。  
  
    > [!NOTE]
    >  付款跟踪模拟程序不验证外部用户凭据。 可以为 PTUserID 输入任何密码。  
  
    -   `ssomanage -setcredentials < WindowsDomain >\< WindowsUserId > WoodgroveBank.PaymentTracker`  
  
##  <a name="step19"></a>为服务面向解决方案部署的 BAM 定义文件  
  
1.  打开命令提示符，键入以下命令，然后按 Enter 以设置用于查找 BAM 实用工具的路径：  
  
    -   SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"  
  
2.  在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\BAM，键入以下命令，然后按 Enter：  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
##  <a name="step21"></a>部署面向服务的解决方案  
  
#### <a name="update-the-binding-files-for-the-service-oriented-solution"></a>更新服务面向解决方案绑定文件  
  
1.  在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，使用记事本打开 Deployallbinding.xml，然后进行以下编辑：  
  
    -   将 SET MGMT_DB_SERVER 和 MBMT_DB 中的服务器名称更改为 BizTalk Server 正在使用的服务器和数据库的名称。  
  
    -   将 SOLNDIR 变量的值更改为“%BTSSolutionsPath%\SO\BTSSoln”。  
  
2.  在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Bindings 文件夹。  
  
3.  对于适配器版本，使用记事本打开 AdapterSOAOrchBindings.xml，然后按如下所述进行编辑：  
  
    -   替换所有出现的 __MQ_SERVER_NAME\_ \_ MQSeries 的服务器名称。  
  
    -   替换所有出现的 __MQ_QMANAGER_NAME\_ \_具有 MQSeries 队列管理器名称。  
  
    -   替换所有出现的 __PT_WS_SERVER_NAME\_ \_字符串中"\<地址\>https://\__PT_WS_SERVER_NAME\_\_"的服务器名称其中 Pending部署事务 Web 服务。 服务器名称必须匹配**公用名**在步骤中，"若要配置 Web 服务器用于 SSL"。 不应使用“localhost”。  
  
    > [!NOTE]
    >  绑定文件 AdapterSOAOrchBindings.xml 为以下项使用存根 Web Services：  
    >   
    >  1.  信用限额后端 SAP 系统。  
    > 2.  用于与付款跟踪后端系统相集成的 MQSeries 适配器。  
    > 3.  用于调用 HIS TI .NET 组件以与大型机后端系统相集成的挂起事务 Web Services。  
    >   
    >  如果不是使用大型机，则必须使用存根 Web Services 为挂起事务系统生成数据。  
  
4.  对于内联版本，使用记事本打开 InlineSOAOrchBindings.xml，然后按如下所述进行编辑：  
  
    -   替换所有出现的 __MQ_SERVER_NAME\_ \_ MQSeries 的服务器名称。  
  
    -   替换所有出现的 __MQ_QMANAGER_NAME\_ \_具有 MQSeries 队列管理器名称。  
  
#### <a name="deploy-the-service-oriented-solution"></a>部署面向服务的解决方案  
  
-   在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，键入以下命令，然后按 Enter：  
  
    -   `Deployallbinding.cmd`  
  
    > [!NOTE]
    >  Deployallbinding.cmd 将创建名为 BTSScn.SO.CustomerService 的 BizTalk 应用程序，并为适配器版本和内联版本导入绑定文件。  
  
##  <a name="step23"></a>配置存根 （stub） 挂起的事务 Web 服务主机不可用时  
  
#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-adapter-version-without-a-mainframe"></a>配置存根 （stub） 挂起的事务 Web 服务 （适用于使用而无需大型机的适配器版本）  
  
1.  在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  
  
     使用**虚拟目录创建向导**，创建以下虚拟目录存根 （stub） 适配器版本的挂起的事务 Web 服务：  
  
     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  
  
     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  
  
     访问权限 = 读取，运行脚本  
  
2.  在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions，单击**属性**，然后修改的设置，如下所示使用**属性**对话框。  
  
    1.  在**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>创建在步骤中，创建虚拟目录在 IIS 中的解决方案"。  
  
    2.  在**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，，然后选择**启用匿名访问**. 单击**确定**退出。  
  
3.  在**BizTalk Server 管理控制台**，展开**BizTalk 组**，展开**应用程序**，展开 BTSScn.SO.CustomerService，展开**发送端口**，右键单击**PendingTransactionSolicitResponsePort**，然后单击**属性**。  
  
    1.  在**常规**页上，单击**配置**以显示**传输属性**对话框框中，，然后修改**Web 服务 URL**到存根 （stub） 挂起的事务 Web 服务，例如：  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  
  
    2.  关闭所有对话框。  
  
#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-inline-version-without-a-mainframe"></a>配置存根 （stub） 挂起的事务 Web 服务 （适用于使用而无需大型机的内联版本）  
  
1.  在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。  
  
     使用**虚拟目录创建向导**，创建以下虚拟目录存根 （stub） 适配器版本的挂起的事务 Web 服务：  
  
     别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  
  
     路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  
  
     访问权限 = 读取，运行脚本  
  
2.  在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions，单击**属性**，，然后修改设置，如下所示：  
  
    1.  在**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>创建在步骤中，创建虚拟目录在 IIS 中的解决方案"。  
  
    2.  在**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，，然后选择**启用匿名访问**. 单击**确定**退出。  
  
3.  打开命令提示符，然后将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。  
  
4.  在命令提示符下，SetConfigValuesInSSO.cmd 使用记事本打开文件，并将的值**PendingTransactionsInlineURL**存根 （stub) 挂起的事务 Web 服务的 url。  
  
    -   `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  
  
5.  在命令提示符下，键入 `SetConfigValuesInSSO.cmd`，然后按 Enter。  
  
##  <a name="step25"></a>启动服务面向解决方案  
  
1.  打开命令提示符，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，键入以下命令，然后按 Enter 以启动内联版本和适配器版本的所有业务流程：  
  
    -   `startAll.vbs`  
  
2.  运行面向服务的解决方案。 有关运行解决方案的详细信息，请参阅[如何运行服务面向解决方案](../core/how-to-run-the-service-oriented-solution.md)。  
  
## <a name="next-steps"></a>后续步骤  
 测试中的面向服务的解决方案的内联和适配器版本[如何运行服务面向解决方案](../core/how-to-run-the-service-oriented-solution.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在安装之前面向服务解决方案](../core/before-installing-the-service-oriented-solution.md)   
 [如何安装服务的存根 （stub） 版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [面向服务的解决方案的开发人员计算机设置](../core/developer-machine-setup-for-the-service-oriented-solution.md)