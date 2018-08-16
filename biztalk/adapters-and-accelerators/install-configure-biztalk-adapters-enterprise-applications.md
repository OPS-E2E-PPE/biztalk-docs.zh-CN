---
title: 安装企业应用程序的 BizTalk 适配器 |Microsoft Docs
description: 要求和 JD Edwards OneWorld，JD Edwards EnterpriseOne PeopleSoft Enterprise、 TIBCO Rendezvous 和 TIBCO Enterprise Message Service 的 BizTalk Server 上的安装步骤
ms.custom: ''
ms.date: 10/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7777b7027e51460e79a6dff6a591d8faa4fe57e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987518"
---
# <a name="install-and-configure-the-microsoft-biztalk-adapters-for-enterprise-applications"></a>安装和配置 Microsoft BizTalk 适配器的企业应用程序 
  
 用于企业应用程序的 Microsoft BizTalk 适配器包括以下适配器：  
  
-   用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器  
  
-   用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器  
  
-   用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器  
  
-   用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器  
  
-   用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器  


> [!IMPORTANT]
> - 进行任何配置更改之前备份所有数据
> - 您必须非常熟悉特定企业应用程序进行任何配置更改之前
  
## <a name="supported-versions--requirements"></a>支持的版本和要求

||要求|  
|---|---|
|操作系统|适配器支持 BizTalk Server 相同的操作系统：<ul><li>[BizTalk Server 2016 要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)</li><li>[BizTalk Server 2013 R2 / 2013年要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)</li></ul>|
|支持的企业系统|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)列出了受支持的版本 |
|JD Edwards OneWorld XE | <ul><li>在 Windows 上的 JD Edwards 企业服务器</li><li>在 Windows 上的 JD Edwards 部署服务器</li></ul>|
|JD Edwards EnterpriseOne | 适配器调用 JD Edwards EnterpriseOne API 使用 JDBC 驱动程序需要数据库。 如果安装 JD Edwards EnterpriseOne 的同时安装了 SQL 数据库，则需要 MS-SQL 驱动程序。 同样如果您安装 JD Edwards EnterpriseOne 的 Oracle 数据库，则需要 Oracle 驱动程序;或者，如果安装了 DB2 数据库，则需要 DB2 驱动程序。 |
|PeopleSoft Enterprise | <ul><li>Sun Systems Java 开发工具包 (JDK)</li><li>PeopleSoft 工具发行版本</li><li>PeopleSoft 应用程序发行版本</li><li>此适配器要求对 PeopleSoft 应用程序的修改。 若要使用组件接口，自定义组件接口 GET_CI_INFO 上载到 PeopleSoft 中。 GET_CI_INFO.pc 位于 Program Files\Common Files\Microsoft BizTalk Adapters 为 Enterprise Applications\PeopleSoft Enterprise(r) \Config\。</li></ul>|
|TIBCO Rendezvous | <ul><li>必须在运行用于 TIBCO Rendezvous 的 BizTalk 适配器的计算机上安装 TIBCO Rendezvous 运行时组件</li><li>必须运行用于 TIBCO Rendezvous 的 BizTalk 适配器的计算机上配置的 TIBCO Rendezvous 许可证。</li><li>TIBCO Rendezvous 二进制文件目录必须对该适配器可见：在环境变量 PATH 值中，或在 BizTalk 服务器中的每个 Rendezvous 端口上指定。 这对于 Rendezvous 程序集查找它的库和可执行文件是必需的。</li></ul>|
|TIBCO Enterprise Message Service | Enterprise Message Service (EMS) 版本 5.x 和更高版本包括一个客户端 SDK （使用 TIBCO EMS C# API）。 用于 TIBCO EMS 的 BizTalk 适配器使用此与服务器进行通信。 |


## <a name="jd-edwards-oneworld-xe"></a>JD Edwards OneWorld XE

本部分包含有关使用用于 JD Edwards OneWorld XE 与 BizTalk Server 的 Microsoft BizTalk 适配器的密钥信息。
  
### <a name="create-the-jar-files"></a>创建 JAR 文件
 本节介绍 JD Edwards OneWorld 与用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器一起工作的要求。  
  
#### <a name="jar-files-and-the-classpath"></a>JAR 文件和 CLASSPATH  
 JD Edwards OneWorld JAR 文件必须是可用于适配器。 例如，若要连接到 B7.3.3.3 版本，以下 jar 文件所需。 具体取决于所连接的服务器，可能会更改 jar 文件列表：
  
- Connector.jar    
- Kernel.jar  
  
  这些文件位于运行 JD Edwards OneWorld 的计算机上的以下位置：  
  
- JD Edwards OneWorld XE_install_Directory\System\classes\Connector.jar    
- JD Edwards OneWorld XE_install_Directory\System\classes\Kernel.jar  
  
  你可将这些文件复制到任何位置；但是，必须指定 CLASSPATH 中的 JAR 文件位置。 CLASSPATH 必须包括文件的完整路径和 JAR 文件的名称（用分号隔开）。  
  
  用于 JD Edwards OneWorld 的 BizTalk 适配器提供 JDEJAccess JAR 文件以用于 JD Edwards OneWorld。 默认情况下，JDEJAccess.jar 文件引用从*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise applications\j.d.Edwards OneWorld(r)\classes\JDEJAccess.jar*. 
  
> [!NOTE]
>  你必须在可以使用用于 JD Edwards OneWorld 的 BizTalk 适配器之前验证 jdeinterop.ini 文件的注册。 请确保您包括在此文件的路径**JDE 传输属性**页面时 BizTalk Server 中创建发送端口。 有关完整说明，请参阅"自定义 jdeinterop.ini 文件。"  
  
#### <a name="create-the-btslibinteropjar-file"></a>创建 BTSLIBinterop.jar 文件  
创建文件，并确认适配器都可以访问它。 使用下面的示例作为指南：  
  
1.  创建包括以下代码的 BTSLIB.cmd 文件：  
  
    ```  
    define library BTSLIB  
    login  
    library BTSLIB  
    interface JDEAdapter  
    import B5500900  
    build  
    logout  
    ```  
  
2.  运行以下命令：  
  
    ```  
    GenJava  /cmd  .\BTSLIB.cmd  
    ```  
  
### <a name="verify-your-setup"></a>验证您的安装程序  
  
1.  使用受支持的版本，包括服务包编号 ([受支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))。 服务包（ESU 和 ASU）更新系统二进制文件。 必备的服务包提供用于导入的 ASU/ESU 菜单选项。  
  
2.  配置 jdeinterop.ini 文件以使用正确的驱动器进行日志记录，如果它不同于驱动器 c。例如，如果 TEMP 目录空间不足在 JD Edwards OneWorld 更新可能会失败。  
  
3.  确定是否必须添加用于左/右填充 JD Edwards OneWorld 字段的配置文件。  
  
4.  请验证你的 JAVA_HOME 的环境变量指向 Java 开发工具包 (JDK) 安装以便从计算机上的任何程序启用 javac 和 java 命令。  
  
5.  验证设置 CLASSPATH 环境变量。 这样，若要找到 Kernel.jar 和 Connect.jar 文件的 JD Edwards OneWorld 的 BizTalk 适配器。  
  
    JAR 文件的路径是区分大小写的。  
  
6.  通过键入区分大小写的以下命令来测试环境。  
  
    ```  
    javap -s -p com.microsoft.jde.JDEJAccess  
    ```  
  
7.  你给出的命令 (javap) 是 Java 类文件拆装器：  
  
    ```  
    http://java.sun.com/j2se/1.3/docs/tooldocs/solaris/javap.html  
    ```  
  
8.  `javap`命令拆分类文件。 其输出取决于所使用的选项。 如果未不使用任何选项，javap 输出包、 受保护，和公共字段和类传递给它的方法。 javap 打印其输出到 stdout。  
  
     如果没有错误，所有 Java 文件及其依赖项都在 CLASSPATH 中。  
  
9. 通过配置本地主机文件中设置 DNS 解析 (*C:\WINNT\system32\drivers\etc\hosts*)，JD Edwards OneWorld 系统的服务器名称。  
  
### <a name="create-and-install-the-custom-package"></a>创建并安装自定义包  
安装 BTSREL 自定义包以使用用于 JD Edwards OneWorld 的 BizTalk 适配器。 本节介绍：  
  
-   JD Edwards OneWorld 自定义包创建过程  
-   如何创建并安装 BTSREL  
-   在 JD Edwards OneWorld 中创建的 BTSREL 对象
  
> [!NOTE]
>  BTSREL.exe 是一个自定义包（在 JD Edwards OneWorld 术语中为自动化的软件更新或 ASU）。 它包含业务功能以提取元数据。 应为特定的 JD Edwards OneWorld 配置和版本创建自定义包。  
  
#### <a name="define-a-custom-package"></a>定义自定义包  
 自定义包是一个后发布的可交付结果，为特定目的（例如法规更改或增强功能）提供软件更改。 这些自定义包是为特定功能创建的。 例如，创建 BTSREL 来提取元数据。 当安装 BTSREL 自定义包时，它会更新在 JD Edwards OneWorld 环境中的选定的模块。 若要更新，必须将 BTSREL 对象合并到适当的 JD Edwards OneWorld 环境中。 有关通过 BTSREL 进行更新的模块的详细列表，请参阅模块列表。  
  
#### <a name="install-the-btsrel-custom-package"></a>安装 BTSREL 自定义包   
下载[BTSREL](https://www.microsoft.com/download/details.aspx?id=56113)。 在部署服务器上安装它，然后将其部署到企业服务器。  
  
 现有的 BTSREL.exe 程序包可直接用于 B7333 版本。 若要与 B7334 版本，然后运行包：  
  
1. 下载并将 BTSREL.exe 的内容提取到你的工作文件夹。  
  
2. 同时修改**ReleaseLevelRequired**并**发行**B7334 Deployment.Inf 文件中的值。  
  
3. 运行安装程序。  
  
   若要安装 BTSREL，需要以下项：  
  
-   部署服务器安装    
-   安装工作台  
  
#### <a name="install-btsrel-on-the-deployment-server"></a>在部署服务器上安装 BTSREL  
 自定义包仅适用于 Windows 操作系统，并与部署服务器一起使用。 必须在部署服务器上，构建并随后部署到企业服务器。 企业服务器通常是生产服务器，并且可在 Windows 或 UNIX 的操作系统上使用。  
  
> [!NOTE]
>  将 ASU 应用于 JD Edwards OneWorld 部署服务器上，确认你已加入**更新**模式。 **证明**模式中验证 ASU 中没有任何 bug 而**更新**模式应用 ASU 时已指定。  
  
1.  登录到部署服务器以用户身份**JDE**。  
  
2.  在部署服务器 (root)/B7 文件夹上创建一个名为 BTSREL 的新文件夹。  
  
3.  将 BTSREL.exe 复制到新创建的 BTSREL 文件夹。  
  
4.  从.../B7/BTSREL 文件夹运行 BTSREL.exe。 安装管理器会自动启动。  
  
5.  在安装程序窗口中，选择**下一步**，然后选择**完成**。 如果安装成功，将显示一条消息。  
  
6.  登录到 JDEPLAN 环境**JDE** JD Edwards OneWorld 部署服务器上的用户。  
  
    1.  如果系统上未安装包括 SAR #4533357 的电子软件更新 (ESU)，选择**软件更新**从**系统安装工具**菜单 (GH9612)。  
  
    2.  中的选项 1 输入 02**处理选项**面板。  
  
    3.  如果安装包括 SAR #4533357 ESU 后系统上，选择**应用程序软件更新**从**系统安装工具**菜单 (GH9612)。  
  
#### <a name="install-btsrel-on-the-jd-edwards-oneworld-workbench"></a>在 JD Edwards OneWorld 工作台上安装 BTSREL  
   
1.  上**使用应用程序更新**屏幕上，双击 BTSREL 更新，然后选择**下一步**。  
  
2.  双击要安装，更新的环境，然后选择**下一步**。  
  
    1.  检查**无人参与的工作台**如果你想要在无人参与模式下运行的软件更新。  
  
    2.  选择**备份**如果你希望规范的备份 （以便可以还原原始的规范）。  
  
3.  上**使用安装计划**屏幕上，选择要安装的更新的计划，然后**选择**。  
  
4.  安装完成后，请查看自动生成的 PDF 是否存在错误。  
  
    > [!NOTE]
    >  如果出现错误，在 JD Edwards OneWorld 软件更新指南中查找故障排除技巧，或直接与 JD Edwards OneWorld 联系。  
  
5.  手动注册业务函数库使用"手动注册业务函数库"在本部分中所描述的步骤。  
  
#### <a name="uninstall-the-custom-package"></a>卸载自定义包  
 无需卸载自定义包。 但是，如果想要清理系统，可以不同方式卸载。 卸载后，重新生成包使用以下方法之一：  
  
- 使用 JD Edwards OneWorld 部署服务器 Gh8612 — P96470，在**行**菜单中，选择**更新**，然后选择**卸载**。    
- 将所有自定义对象 (BTSREL) 签出到客户端计算机并将其删除。    
- 应用之前的数据库快照。  
  
  在清理过程中，验证对 JD Edwards OneWorld 的其他对象做出的任何其他修改。  
  
#### <a name="manually-register-the-business-function-library"></a>手动注册业务函数库  
 由于 JD Edwards OneWorld 产品打包过程的限制，用于 JD Edwards OneWorld 的 BizTalk 适配器的自定义业务函数库 DLL 必须使用 JD Edwards OneWorld 进行手动注册。 此过程包括以下步骤。
  
##### <a name="step-1-create-the-custom-business-function-library"></a>步骤 1： 创建自定义业务函数库  
 使用 JD Edwards OneWorld 对象管理工作台 (OMW) 创建自定义业务函数库。 下面的过程必须在初始安装中，执行，并适用于所有平台。  
  
1.  启动对象管理工作台 (快速路径:"OMW"或菜单选项： GH902 对象： P98220)。  
  
2.  选择**外**，然后选择的选项**业务函数库**。  
  
3.  对新业务函数库对象输入以下信息：  
  
    -   **名称：** ACBLIB    
    -   **说明：** Microsoft DLL    
    -   **产品代码：** 55    
    -   **产品系统代码：** 55  
  
4.  选择“确定”。  
  
##### <a name="step-2-rebuild-libraries-from-the-deployment-server"></a>步骤 2： 重新生成库从部署服务器  
完成初始安装程序为每个平台上的以下步骤。  
  
1.  若要在独立模式下启动 BusBuild 程序，请选择**启动**，选择**运行**，然后选择**busbuild.exe**。
  
2.  在 pathcode （PY7333，PD7333 或 DV7333） 中登录到 JD Edwards OneWorld。  
  
3.  在中**重新生成库**列表中，选择**生成**。  
  
##### <a name="step-3-copy-the-custom-dll"></a>步骤 3： 复制自定义 DLL  
 将自定义 DLL 从 pathcode 目录复制到 JD Edwards OneWorld 部署服务器和 JD Edwards OneWorld 企业服务器上的父包目录。
  
**JD Edwards OneWorld XE 部署服务器上**  
  
1.  将 ACBLIB.dll 从 DV7333\bin32 复制到 DV7333\Packages\DV7333FA\bin32。  
  
2.  将 ACBLIB.def、ACBLIB.dmp 和 ACBLIB.mak 从 DV7333\obj 文件夹复制到 DV7333\Packages\DV7333FA\obj 文件夹。  
  
3.  ACBLIB.exp、 ACBLIB.lib 和 sACBLIB.lib DV7333\lib32 文件夹复制到 DV7333\Packages\DV7333FA\lib32 文件夹。  
  
**JD Edwards OneWorld 企业服务器上**  
  
在创建每个目录和文件后，验证授权。  
  
1.  创建一个目录 ACBLIB 下 DV7333FA\obj\\。  
  
2.  创建一个目录 ACBLIB DV7333FA\source 下。  
  
3.  从部署服务器 DV7333\source 目录到 DV7333FA\source\ACBLIB 目录的 FTP b5500900.c。  
  
4.  FTP b5500900.h 从部署服务器 DV7333\include 目录复制到 DV7333FA\include 目录。  
  
##### <a name="step-4-build-a-full-package"></a>步骤 4： 生成完整的包  
 由于 JD Edwards 包生成过程的限制，生成的环境中向其应用了 BTSREL 更新，或更新包内部版本无法正常工作的完整包。 请参阅有关如何生成完整包内部版本的 JD Edwards 文档。  
  
> [!NOTE]
>  当应用 JD Edwards OneWorld ASU/ESU 时，ASU/ESU 通常不创建新的库和业务函数。 因此，该过程很简单： 但是，用于 JD Edwards OneWorld 自定义软件包的 BizTalk 适配器创建新的库。 因此，必须执行额外的步骤，例如，手动创建一个目录并运行完整包内部版本。  
  
#### <a name="modules-list"></a>模块列表  
 自定义包 BTSREL 在 JD Edwards OneWorld 中创建以下对象。 BTSREL 包含用来提取元数据的业务功能和测试数据类型的自定义函数。  
  
> [!NOTE]
>  JD Edwards OneWorld 的更新中有一个 bug。 如果没有所有业务和自定义函数，请验证已完成的是完整包内部版本，而不是更新包内部版本。  
>  
>  如果列表缺失文件，例如，在 ACBTEST 之下有所有内容而其上没有任何内容，则你可能缺失数据字典 (DD) 项目。 你可以转到**使用数据项**，查找缺少的文件。  
>   
>  如果缺失其他项，例如 ACBCHAR01、 ACBDATE01、 ADBINT01、 ACBMATH01 和 ACBSTR01，这些是*主数据元素*。 如果你从及计划者到开发人员合并对象，许多报表将在后台运行。 你可以打开合并报告并检查错误。 报告应列出的所有项目并指示它们已完成，且无错误或警告。 有了此验证，你可以继续，因为所有项都已检查过。  
  
-   ACBCHAR01 - 测试字符类型 01  
  
-   ACBCUST - ACB 客户 ID  
  
-   ACBDATE01 - 测试数据类型 01  
  
-   ACBDEF - ACB 函数类型定义  
  
-   ACBFCNT - ACB 函数名称列表计数  
  
-   ACBFUNC - ACB 函数名称列表  
  
-   ACBFUNCN - ACB 函数名称  
  
-   ACBINT01 - 测试整数类型 01  
  
-   ACBLIB - 控制 BROKER 库  
  
-   ACBMATH01 - 测试数学类型 01  
  
-   ACBNEWS - ACB 新状态  
  
-   ACBORDER - ACB 订单号  
  
-   ACBPRC - ACB 商品价格  
  
-   ACBPROD - ACB 产品 ID  
  
-   ACBQTY - ACB 商品数量  
  
-   ACBRES - ACB 结果指示器  
  
-   ACBSTAT - ACB 状态  
  
-   ACBSTR01 - 测试字符串类型 01  
  
-   ACBTEST - ACB 测试屏幕  
  
-   ACBTEST2 - ACB 测试屏幕 2  
  
-   ACBTEST3 - ACB 测试屏幕 3  
  
-   B5500900 - 控制 BROKER 支持模块  
  
-   D5500900 - 控制 BROKER 数据结构  
  
-   D5500900A - 控制 BROKER 数据结构  
  
-   D5500900B - FETCH 价格数据结构  
  
-   D5500900C - 获得客户状态数据结构  
  
-   D5500900D - 设置客户状态数据结构  
  
-   D5500900E - 更新销售订单状态数据结构  
  
-   D5500900F - 测试整数  
  
-   D5500900G - 测试字符串  
  
-   D5500900H - 测试日期  
  
-   D5500900I - 测试字符  
  
-   D5500900J - 测试数学数值  
  
-   D5500900K - 测试日期 2  
  
#### <a name="customize-the-jdeinteropini-file"></a>自定义 jdeinterop.ini 文件  
 Connector.jar 和 Kernel.jar 中的 JD Edwards OneWorld XE 连接器类需要使用 jdeinterop.ini 的配置文件。 此文件由 JD Edwards OneWorld 软件定义，并使用其术语。 JD Edwards 互操作性指南发行 OneWorld 可能提供有关用途和术语的此文件的详细信息。 还有一个示例 jdeinterop.ini 文件中的 *< 自 > \config\jde*。  
  
更新 jdeinterop.ini 以匹配你在中定义的参数值**传输属性**屏幕。 如果它们的参数兼容，则多个 JD Edwards OneWorld 逻辑系统可以共享同一个 jdeinterop.ini 文件。 通常情况下，如果两个逻辑系统指向两个不同的 JD Edwards OneWorld 计算机，他们需要两个不同的 jdeinterop.ini 副本。  
  
> [!NOTE]
>  Jdeinterop.ini 中的日志记录应关闭，并且可以安全地忽略各种日志文件的参数。  
  
 下表列举 jdeinterop.ini 文件中的设置。 信息是按节组织的。 例如 [JDENET] 与本节按其在 JD Edwards OneWorld 软件中出现的顺序列出。  
  
#### <a name="jdeinteropini-file-settings"></a>jdeinterop.ini 文件设置
  
|部分|参数和说明|  
|-------------|-------------------------------|  
|[JDENET]|**EnterpriseServerTimeout.** 对企业服务器的请求的超时值（以毫秒为单位）。 默认大小为 120000。<br /><br /> **maxPoolSize.** JDENET 套接字连接池大小。 默认大小为 30。|  
|[SERVER]|**glossaryTextServer.** 提供词汇表文本信息的企业服务器和端口。 这是返回错误的文本说明的服务器。 这通常是与 JD Edwards OneWorld 应用程序服务器相同的主机和端口。 不同的受支持的语言编码可能有不止一个词汇表服务器。 例如，JDED:6010 或 actsrv1:6009。 值必须与系统定义中设置的相匹配。<br /><br /> **codePage.** 编码方案。 默认为 1252。<br /><br /> 1252 英语和西欧语言<br /><br /> -932 日语<br /><br /> -950 繁体中文<br /><br /> -936 中文 （简体的)<br /><br /> -949 朝鲜语|  
|[LOGS]|**日志 = c:\jas.log。** 日志文件的位置。 可以安全地忽略此参数。<br /><br /> **debuglog = c:\jasdebug.log。** 调试日志文件的位置。 可以安全地忽略此参数。<br /><br /> **调试。** 确定是否已启用 JDENET 调试。 默认值为 FALSE。|  
|[DEBUG]|**JobFile = c:\Interop.log。** 错误文件的位置。 可以安全地忽略此参数。<br /><br /> **DebugFile = c:\InteropDebug.log。** 调试文件的位置。 可以安全地忽略此参数。<br /><br /> **日志 = c:\net.log。** 日志文件的位置。 可以安全地忽略此参数。<br /><br /> **debugLevel = 0-12。** 调试级别。 可以安全地忽略此参数。 此项定义了由仅在 COM 服务器中的指定日志文件中的 COM 连接器和 Callobject 组件提供的跟踪级别。<br /><br /> -0 none。 关闭日志记录并仅将错误写入 JobFile。<br /><br /> -2 个错误 （错误消息）<br /><br /> -4 系统错误 （异常消息）<br /><br /> -6 警告信息<br /><br /> -8 分钟跟踪 （键操作。 例如，登录、注销、业务函数调用。）<br /><br /> -10 个故障排除信息 （帮助）。<br /><br /> -12 完整的调试信息 （记录所有内容）<br /><br /> -默认情况下，不需要启用跟踪，但调试代码时，跟踪是非常有用。<br /><br /> -NetTraceLevel = 0。 跟踪级别。 可以安全地忽略此参数。 定义由 ThinNet 组件在指定的日志文件中，仅在 COM 服务器中提供的跟踪级别。 对于未来要添加的级别保留奇数值。<br /><br /> -以下列表介绍了更多的调试级别：<br /><br /> -0 没有跟踪<br /><br /> -1 表示记录进程 ID、 线程 ID 和可用套接字状态时添加新的连接和搜索套接字池。<br /><br /> -2 包括跟踪级别 1 中的信息，还跟踪在连接管理器类中所做的每个调用。<br /><br /> -3 包括跟踪级别 2，还跟踪 getport （） 调用和 gethost （） 调用中的所有信息。|  
|[INTEROP]|**enterpriseServer.** 此值是主机服务器的名称。 请确保此值是相同的值中输入**主机名**字段中**JDE 凭据**主题中**系统定义**中**传输属性**对话框。 默认值为 JDED。<br /><br /> **端口。** 此值是用于交换数据的端口号。 请确保此值是相同的值中输入**端口号**字段中 JD Edwards**凭据**主题中**传输属性系统定义**. 例如，6010 或 6009。 值必须匹配中设置的相**系统定义**。<br /><br /> **inactive_timeout**。 自动提交模式下的事务的超时值（以毫秒为单位）。 如果用户在这段时间（以毫秒为单位）处于非活动状态，互操作的服务器将注销用户。 可以将此值更改为较短的时间段。 默认值为 1200000。<br /><br /> **manual_timeout。** 以毫秒为单位在手动提交模式下事务超时值。 默认值为 120000。<br /><br /> **存储库。** 指向包含 Connector.jar 和 Kernel.jar 的目录的位置。 在 UNIX 上，这是完整路径。|  
|[CORBA]|可以安全地忽略此参数。<br /><br /> **多线程。** 可以忽略该设置。 将 CORBA 的多线程支持设置为 1。<br /><br /> Objects= CORBA::Connector；CORBA::OneWorldVersion<br /><br /> 定义要在启动时创建的 CORBA 服务器的对象。 此外会替换-DIORFILENAME = 命令行选项，例如： CORBA::Connector=connector.ior。|  
  
## <a name="jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne  
本部分包含有关用于 JD Edwards EnterpriseOne 的 BizTalk Server 使用的 Microsoft BizTalk 适配器的密钥信息。
  
### <a name="execute-a-jd-edwards-enterpriseone-master-business-function"></a>执行 JD Edwards EnterpriseOne 主业务函数  
 用于 JD Edwards EnterpriseOne 的 BizTalk 适配器可用于调用 JD Edwards EnterpriseOne 主业务函数，例如通讯簿、采购订单或销售订单。 也可使用适配器作为集成工作的一部分来将 JD Edwards EnterpriseOne 和 BizTalk 服务器相连接。  
  
##### <a name="access-data-stored-in-jd-edwards-enterpriseone"></a>访问 JD Edwards EnterpriseOne 中存储的数据  
 适配器接受 XML 消息，使 BizTalk 服务器应用程序能够使用以下端口之一与 JD Edwards EnterpriseOne 进行通信和事务交换：  
  
-   **传输适配器**，其中使用静态要求响应发送端口将消息发送到 JD Edwards EnterpriseOne 并等待响应。    
-   **接收适配器**，它使用静态单向接收端口以接收来自 JD Edwards EnterpriseOne 的消息。  
  
### <a name="interoperability-framework"></a>互操作性框架  
 JD Edwards EnterpriseOne 为通过其互操作性框架与系统集成做准备。 适配器使用 JD Edwards EnterpriseOne 框架，并利用各种集成访问方法，以提供最大程度的灵活性和功能。  
  
 用于 JD Edwards EnterpriseOne 的 BizTalk 适配器支持以下集成访问方法：  
  
- JD Edwards EnterpriseOne ThinNet API    
- JD Edwards EnterpriseOne XML    
- JD Edwards EnterpriseOne 未编辑的事务表（Z 表）  
  
  适配器使用 JD Edwards EnterpriseOne ThinNet API 与 JD Edwards EnterpriseOne 应用程序进行通信。 通过使用 ThinNet API，该适配器可以调用单个工作单元 (UOW) 中的一个主业务函数 (MBF)。 当 MBF 失败时，整个 UOW 无法正常工作。 这样可以防止部分更新。 数据验证、业务规则和与基础数据库的通信都由 JD Edwards EnterpriseOne 应用程序处理。  
  
#### <a name="jd-edwards-outbound-processing-framework"></a>JD Edwards 出站处理框架  
 在出站过程中，当在 JD Edwards EnterpriseOne 环境中执行一个特定的 MBF 时，事件启动。 MBF 将该事件所需的信息写入到适当的接口表并随后通知发生事件的子系统批处理函数 (BF)。 随后子系统 BF 包括一个关于子系统数据队列上的事件的条目。  
  
 出站子系统检索数据队列条目，并在数据输出控制表中查找外部进程以进行通知。 随后出站子系统调用用于 JD Edwards EnterpriseOne 侦听器的 BizTalk 适配器并发出通知。 侦听器将通知传递给生成器。 随后生成器使用 JD Edwards EnterpriseOne ThinNet API 检索来自接口表的相应信息。  
  
### <a name="set-string-justification-in-jdearglist"></a>在 Jdearglist 中设置字符串对齐  
 若要将某些字符串参数配置为右对齐和左填充中 j.d. Edwards EnterpriseOne jdearglist.txt 文件中右对齐和左填充，你必须知道你希望访问哪些业务函数，特别是，你必须知道你希望调用业务函数中的哪些字段。  
  
 您必须先更新该 jdearglist.txt，然后在业务流程中生成绑定（架构）。 用于更新 jdearglist.txt 文件中的"处理字符串值"部分所述的说明。  
  
 如果在日志中收到 jdearglist.txt 警告消息，其目的是通知您缺少指定 jdearglist.txt。 但是，如果运行 SalesOrder 或 PurchaseOrder 业务函数，必须在你的路径具有该文件或它不起作用。  
  
### <a name="understand-jdeinteropini"></a>了解 jdeinterop.ini  
 Connector.jar 和 Kernel.jar 中的 JD Edwards EnterpriseOne 连接器类需要你使用名为 jdeinterop.ini 的配置文件。 此文件由 JD Edwards EnterpriseOne 软件定义，并使用其术语。 有关用途和术语的此文件的详细信息，请参阅 JD Edwards 互操作性指南。 还有一个示例 jdeinterop.ini 文件中： Program Files\ Microsoft BizTalk Adapters for Enterprise Applications\ J.D. Edwards EnterpriseOne(r) \config。  
  
 建议不要因为它与交互手动编辑此文件**传输属性**发送端口-例如这些字段标记为对话框 **< 由 BizTalk 配置\>**.  
  
## <a name="peoplesoft-enterprise"></a>PeopleSoft Enterprise  
此部分包含有关适用于 PeopleSoft Enterprise 的 BizTalk Server 使用的 Microsoft BizTalk 适配器的关键信息。
  
### <a name="receive-handler-peoplesoft-requirements"></a>接收处理程序 PeopleSoft 要求  
 PeopleSoft Integration Broker 必须能够与 BizTalk 服务器进行通信。 以下情况可能已经在现有 PeopleSoft 环境中发生，你可以重新使用现有节点；因此，除了从 PeopleSoft 系统管理员那里获取 HTTP 规范之外，你不需要进行任何操作。 有关详细信息，请参阅 PeopleSoft 文档。  

以下步骤提供的概述，可在 PeopleSoft 中完成：  
  
1.  设置该消息，并使它通过应用程序设计器处于活动状态。  
  
2.  对 PeopleSoft integration.gateway.properties 文件进行一次性更改。  
  
3.  创建和配置网关以及节点以激活 HTTP:
  
    -   节点必须使用一些触发方法，例如 LOCATION_SYNC 机制。   
    -   节点必须使用 HTTP。    
    -   节点必须指向发送该事件的主机和端口。  
  
### <a name="send-handler-peoplesoft-requirements"></a>发送处理程序 PeopleSoft 要求  
 用于 PeopleSoft Enterprise 的 BizTalk 适配器包含自定义组件接口 (CI) 用于通过 Java API 的访问。 自定义 CI 对象**GET_CI_INFO**，使用 PeopleSoft 工具提供用于 PeopleSoft Enterprise 的 BizTalk 适配器所需的元数据信息在 PeopleSoft 系统中部署。 有关详细信息，请参阅 PeopleSoft 文档。  
  
 上载自定义组件接口是一次性的。 文件 GET_CI_INFO.pc 是随产品提供的，且在使用适配器来浏览 CI 之前必须安装在 PeopleSoft 系统中。 必须有权访问 PeopleSoft 应用程序设计器;但是，应用程序设计器不必位于 BizTalk Server 计算机附近的任何位置。 应用程序设计器用于将自定义 CI 上载到您浏览的 PeopleSoft 计算机。  
  
 必须有权访问的 PeopleSoft 计算机，因为您必须设置环境变量 CLASSPATH (或中设置该信息**传输属性**窗口) 以指向 PeopleSoft PSJOA/psjoa.jar 文件。  
  
### <a name="set-environment-variable-and-use-component-interface"></a>设置环境变量和使用组件接口  
有关 PeopleSoft 的详细信息，请参阅 PeopleSoft 文档。  
  
#### <a name="set-classpath-environment-variable"></a>设置 ClassPath 环境变量  

**更新 JAVA_HOME**    
  
 设置 JAVA_HOME 变量，使其指向您的 JDK 安装，例如：  
  
```  
set JAVA_HOME=C:\j2sdk1.4.2_06  
```  
  
 **更新 CLASSPATH**  
  
若要使用组件接口 (仅适用于 PeopleSoft 8)，则必须更新 CLASSPATH 以包含 PeopleSoft 组件接口 jar 文件：
  
1. 在中**Control Panel**，打开**系统**。  
  
2. 上**高级**选项卡上，选择**环境变量**，然后选择**CLASSPATH**。  
  
3. 添加的路径。 例如，输入：  
  
   ```  
   <PeopleSoft_Home>\web\PSJOA\psjoa.jar  
   ```  
  
   用于 PeopleSoft Enterprise 的 BizTalk 适配器需要 psjoa.jar 文件。 创建发送端口时执行此操作。 有关详细信息，请参阅适配器文档中的"在 PeopleSoft 系统中设置传输属性"。  
  
> [!NOTE]
>  只要你的 PATH 中有一个目录，就可确保用于 PeopleSoft Enterprise 的 BizTalk 适配器拾取正确的 DLL。 未能对你想要的 PeopleSoft 版本正确设置环境可能导致难以追踪的错误。  
  
#### <a name="use-component-interfaces"></a>使用组件接口  
  
<a name="BKMK_CustomCI"></a>   
##### <a name="upload-a-custom-ci-into-peoplesoft"></a>将自定义 CI 上载到 PeopleSoft  
 用于 PeopleSoft Enterprise 的 BizTalk 适配器要求对 PeopleSoft 应用程序进行修改。 要使用组件接口，必须将自定义组件接口 GET_CI_INFO 上载到 PeopleSoft。 只需在初始安装过程中导入 GET_CI_INFO 以使用适配器。 适配器使用 GET_CI_INFO 获取有关 PeopleSoft 中的其他现有组件接口的信息。  
  
 本部分介绍如何手动导入一个可浏览 PeopleSoft 中的组件接口的自定义组件接口。 请注意自定义的方法不使用或修改它所安装的位置中的任何组件接口属性。 若要导入自定义组件接口，可以使用以下方法之一：  
  
- 创建新的组件导入自定义方法。  
  
- 使用未包含键的现有的组件，例如，INSTALLATION_RS。  
  
  简单的组件接口不得包含键。 如果你不确定特定组件接口是否包含键，则可以使用 SQL 查询工具运行此简单 SQL 语句。 这样，可以在应用程序中所有不包含键的组件接口的列表。  
  
```  
select distinct BCNAME  
from PSBCITEM bc1  
where not exists  
(select 1  
from PSBCITEM bc2  
where bc1.BCNAME = bc2.BCNAME  
and bc2.BCTYPE in (1, 2))  
```  
  
 你可以按照 PeopleSoft 文档创建用于存储 PeopleSoft Enterprise 自定义方法的 BizTalk 适配器的唯一简单组件。 你还可以克隆一个预先存在的组件接口并使用它来存储自定义方法。  
  
 要验证 GET_CI_INFO 不包含键，请运行 PeopleTools 应用程序设计器组件接口测试工具。  
  
<a name="BKMK_NewCom"></a>   
##### <a name="create-a-new-component-interface"></a>创建新的组件接口  
 请按照以下步骤创建新的组件接口使用 PeopleSoft 应用程序设计器操作：
  
1. 打开**PeopleSoft 应用程序设计器**。  
  
2. 输入一个三层连接类型，并单击**确定**。 例如，从列表中选择应用程序服务器。  
  
3. 在应用程序设计器上**文件**菜单中，选择**新建**。  
  
4. 在中**新建**对话框中，选择**组件接口**，然后单击**确定**。  
  
5. 然后单击“选择”。  
  
6. 从所有组件的列表，选择任何简单组件。 例如，选择 INSTALLATION_RS 或你创建一个新的 PeopleSoft 组件。  
  
   自定义方法不要使用或修改的组件接口安装在任何属性。  
  
   此简单的组件接口不得包含键。 如果你不确定特定组件接口是否包含键，则可以使用 SQL 查询工具运行此简单 SQL 语句。 这样，可以在应用程序中所有不包含键的组件接口的列表：  
  
```  
select distinct BCNAME from PSBCITEM bc1 where not exists (select 1 from PSBCITEM bc2 where bc1.BCNAME = bc2.BCNAME and bc2.BCTYPE in (1, 2))  
```  
  
> [!NOTE]
>  您也可以按照 PeopleSoft 文档创建用于存储 PeopleSoft Enterprise 的 BizTalk 适配器自定义方法的唯一简单组件。  
  
 要验证 GET_CI_INFO 不包含键，请运行 PeopleTools 应用程序设计器组件接口测试工具。  
  
##### <a name="check-component-interface"></a>检查组件接口  
 你已完成将 PeopleSoft GET_CI_INFO 的 Microsoft BizTalk 适配器的上载到 PeopleSoft 系统的工作。 GET_CI_INFO 是一个用户定义的自定义组件接口。 它包含用户定义的方法。 GET_CI_INFO 组件接口允许你在 PeopleSoft 系统中使用 Microsoft 适配器向导浏览组件接口。 你可以找到并展开 GET_CI_INFO 以查看其用户定义的方法。  
  
> [!NOTE]
>  有关用户定义的方法的详细信息，请参阅适配器文档中的"PeopleSoft:: 组件接口用户定义方法"。  
  
##### <a name="set-the-component-interface-security"></a>设置组件接口安全性  
 在 PeopleSoft 上安装自定义 GET_CI_INFO PeopleSoft 组件接口后，设置的安全设置**GetCINamespace**， **GetDetails**，和**GetCollections**用于 PeopleSoft Enterprise 的 BizTalk 适配器的方法。 这是创建自定义组件或用户定义方法的标准做法。  
  
> [!NOTE]
>  以下过程介绍如何在所有支持的模式下为 PeopleSoft 的所有支持发行版配置安全性。  
>   
>  要配置组件接口的安全性  
  
1.  指向**PeopleTools**，依次指向**安全**，指向**权限与角色**，然后选择**权限列表**。  
  
2.  在中**维护安全**窗口中，单击**搜索**，选择相关**权限列表**，然后单击相应的列表超链接。  
  
3.  在中**权限列表**窗格在右侧，单击右箭头旁边**登录时间**选项卡以显示**组件接口**选项卡。  
  
4.  单击**组件接口**选项卡。  
  
5.  单击加号 （+） 以将新行添加到**组件接口**列表。  
  
6.  选择**GET_CI_INFO**组件接口，然后单击**编辑**。  
  
7.  将方法设置为**的完全访问权限**，单击 **（全部） 的完全访问权限**，然后单击**确定**。  
  
8.  滚动到底部**组件接口**窗口，，然后单击**保存**。  
  
##### <a name="test-the-component-interface"></a>测试组件接口  
 你已经为以 PeopleSoft Enterprise 的 BizTalk 适配器传递的 GET_CI_INFO 组件接口完成了配置安全性的工作。 你的 PeopleSoft 组件接口已准备就绪，可浏览 PeopleSoft 组件接口。  
  
 请按照以下步骤在应用程序设计器中测试组件接口。  
  
 若要测试组件接口  
  
1.  启动**PeopleSoft 应用程序设计器**。  
  
2.  上**文件**菜单，依次指向**打开**，然后选择**定义 = 组件接口**。  
  
3.  从组件接口的列表中选择**GET_CI_INFO CI**。  
  
4.  打开 GET_CI_INFO 后，在组件接口定义中，右窗格中右键单击任意位置，然后选择**测试组件接口**。  
  
**Component Interface Tester**窗口随即打开。 不应列出任何键。 如果 GET_CI_INFO 包含键，或如果没有为所选内容的另一种方法，返回到应用程序设计器中，并消除 GET_CI_INFO 中的所有键。  
  
## <a name="install-steps"></a>安装步骤
 在安装之前，请确保 BizTalk Server 并安装所有必备软件的适配器。 建议你运行安装程序之前关闭所有应用程序。  
  
1.  运行 BizTalk Server **Setup.exe**，选择**安装 Microsoft BizTalk 适配器**，然后选择**用于企业应用程序中安装 Microsoft BizTalk 适配器**。  
  
    > [!NOTE]
    >  - 您还可以运行使用以下命令无提示安装： msiexec /i < msi\> /qn /l* < 日志文件\>-其中 < 日志文件\>是可选的但如果安装失败非常有用。  
    >  - 安装更新了 PATH 环境变量。 要确保正在使用正确的变量，请关闭安装命令窗口来更新你的变量。  
  
2.  接受**许可协议**，然后选择**下一步**。
  
3.  输入你**客户信息**，然后选择**下一步**。  
  
4.  选择**完成**或**自定义**安装： 
  
    -   **完整**： 企业应用程序，所有程序功能，可安装所有 Microsoft BizTalk 适配器，用于开发和运行时。  
  
    -   **自定义**： 您选择的适配器和功能，你想要安装，并安装位置。  
  
    若要设置目标，请选择**浏览**，并设置安装路径。  
  
    选择**下一步**以继续。  
  
5. **安装**，然后选择**完成**时完成。  
  
> [!IMPORTANT]
>  在安装过程中，可能会遇到以下错误：  
>   
>  `Error 1609. An error occurred while applying security settings. CREATOR OWNER is not a valid user or group`  
>   
>  若要解决此错误，执行以下操作，并再次运行安装程序：  
>   
>  1. 打开命令提示符
>  2. 类型： `net user "CREATOR OWNER" /add`。 这将创建一个名为 CREATOR OWNER 的新用户。
>  3. 类型： `net localgroup Users /add`。 这将创建名为用户的新组。
  
若要将适配器添加到 BizTalk Server，请参阅"添加适配器向 BizTalk 管理员"本主题中。

## <a name="add-adapters-to-biztalk-admin"></a>将适配器添加到 BizTalk 管理员
  
> [!NOTE]
>  如果在多计算机环境 （仅限运行时的一台计算机上的安装和管理仅工具安装在另一台计算机上的） 中安装 BizTalk，你应在两台计算机上用于企业应用程序安装 BizTalk 适配器。  
  
1.  打开 BizTalk Server 管理控制台中，依次展开**Microsoft BizTalk Server**，然后展开**平台设置**。  
  
2.  右键单击**适配器**，选择**新建**，然后选择**适配器**。  
  
3.  输入一个名称，例如**PeopleSoft**。  
  
4.  选择从输入的名称**适配器**列表，然后选择**确定**。  
   
## <a name="post-install---jd-edwards-oneworld"></a>安装后的 JD Edwards OneWorld  
 用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器包含接口支持的数据库和服务器系统与 Microsoft BizTalk Server 传输适配器。 通过传输适配器，你可以从 BizTalk 服务器调用服务器系统。 传输适配器（BizTalk 服务器管理发送处理程序）配置指定 SQL 数据库的位置。  
  
 有关如何使用用于 JD Edwards OneWorld 的 BizTalk 适配器以及在它的模型和 BizTalk 服务器模型之间进行映射的详细信息，请参阅适配器文档。  
  
### <a name="single-sign-on"></a>单一登录  
 用于 JD Edwards OneWorld 的 BizTalk 适配器提供支持的企业单一登录 (SSO)。 如果你选择要使用的 SSO**传输属性**页上，凭据用于 SSO 凭据数据库中的关联应用程序。 关联应用程序表示一个应用程序 - 一个需要凭据的后端。  
  
### <a name="installed-components"></a>已安装的组件  

* 适配器安装安装，并在全局程序集缓存 (GAC) 中注册以下组件。 你可以通过在资源管理器中打开的程序集文件夹以验证注册 (< %WINDIR%> \assembly)，或使用`gacutil /l`从 Visual Studio 命令提示符：

    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll  

  
* btsTask.exe 安装并部署`Microsoft.BizTalk.Adapters.JDEProperties.dll`到 gac 中的文件。 BizTalk Server 部署日志结果位于*\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\jdeDeploy.html*并**jdeDeploy.xml**。
  
* 特定于适配器的文件安装在*Program Files*并*Program Files\Common Files*。  
  
* `sdk\`安装在*Program Files\Microsoft BizTalk Adapters for Enterprise Applications\ J.D.Edwards OneWorld(r)*。
  
* * 程序 Files\Microsoft BizTalk Adapters for Enterprise Applications\JD Edwards OneWorld(r)\*包含以下文件：  
  
    -   classes\JDEJAccess.jar    
    -   Config\ J.D. Edwards OneWorld(r) \BTSREL.exe    
    -   Config\ J.D. Edwards OneWorld(r) \jdearglist.txt    
    -   Config\ J.D. Edwards OneWorld(r) \jdeinterop.ini  
  
* * 编程 Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\Bin\*包含以下文件：  
  
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   jdecba.dll  
  
## <a name="post-install---jd-edwards-enterpriseone"></a>安装后的 JD Edwards EnterpriseOne  
 用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器包含支持的数据库和服务器系统与 BizTalk Server 与连接的传输适配器。 传输适配器允许你从 BizTalk 服务器调用服务系统。  
  
 用于 JD Edwards EnterpriseOne 的 BizTalk 适配器提供支持的企业单一登录 (SSO)。 如果你选择要使用的 SSO**传输属性**页上，凭据用于 SSO 凭据数据库中的关联应用程序。 关联应用程序表示一个应用程序 - 一个需要凭据的后端。  
  
### <a name="installed-components"></a>已安装的组件  
* 适配器安装安装，并在全局程序集缓存 (GAC) 中注册以下组件。 你可以通过在资源管理器中打开的程序集文件夹以验证注册 (< %WINDIR%> \assembly)，或使用`gacutil /l`从 Visual Studio 命令提示符：
  
    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll    

* 特定于适配器的文件安装在*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\Bin*文件夹。 此文件夹包含以下文件：  
  
    -   Jdecba.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll  
  
* 以下文件安装在*Program Files\Microsoft BizTalk Adapters for Enterprise applications\j.d.。Edwards EnterpriseOne(r)*:  
  
    -   Bin\BTAJDEEnterpriseOneTrace.cmd    
    -   Classes\JDEDynAccess.jar    
    -   Config\btaJDEEnterpriseOneTrace.mof    
    -   Config\jdearglist.txt    
    -   Config\jdeinterop.ini    
    -   Config\jdelog.properties    
    -   Sdk  
  
 
## <a name="post-install---peoplesoft-enterprise"></a>安装后的 PeopleSoft Enterprise  
 用于 PeopleSoft Enterprise 的 Microsof BizTalk 适配器包括一个传输适配器，该适配器将支持的数据库和服务器系统与 BizTalk 服务器相连接。 传输适配器允许你从 BizTalk 服务器调用服务系统。 传输适配器（BizTalk 服务器管理发送处理程序）配置指定 SQL 数据库的位置。  
  
 用于 PeopleSoft Enterprise 的 BizTalk 适配器提供支持的企业单一登录 (SSO)。 如果你选择要使用的 SSO**传输属性**页上，凭据用于 SSO 凭据数据库中的关联应用程序。 关联应用程序表示一个应用程序 - 一个需要凭据的后端。  
  
 适配器安装包括 \sdk 目录中的示例。  
  
### <a name="installed-components"></a>已安装的组件  
* 适配器安装安装，并在全局程序集缓存 (GAC) 中注册以下组件。 你可以通过在资源管理器中打开的程序集文件夹以验证注册 (< %WINDIR%> \assembly)，或使用`gacutil /l`从 Visual Studio 命令提示符：
  
    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll    

* 特定于适配器的文件安装在*Program Files*并*Program Files\Common Files*。 以下文件安装在*Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise (r)*:
  
    -   bin\BTAPeopleSoftTrace.cmd    
    -   config\btaPeopleSoftTrace.mof    
    -   config\GET_CI_INFO.pc    
    -   config\GET_CI_INFO.pc    
    -   sdk\  
  
* *用于企业应用程序进行编程 Files\Common Files\Microsoft BizTalk Adapters*包含以下文件：  
  
    -   bin\psosa.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
## <a name="post-install-overview---tibco-rendezvous"></a>安装后概述-TIBCO Rendezvous  
 用于 TIBCO Rendezvous 的 BizTalk 适配器包括接收和传输功能，该功能将支持的数据库和服务器系统与 BizTalk 服务器相连接。  
  
- 接收端侦听来从服务器系统出站的调用。  
  
- 传输端使你能够从 BizTalk 服务器调用服务器系统。  
  
  请参阅适配器文档，以了解有关如何使用用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器以及有关其模型和 BizTalk 服务器模型之间的映射。  
  
### <a name="installed-components"></a>已安装的组件  
* 适配器安装安装，并在全局程序集缓存 (GAC) 中注册以下组件。 你可以通过在资源管理器中打开的程序集文件夹以验证注册 (< %WINDIR%> \assembly)，或使用`gacutil /l`从 Visual Studio 命令提示符： 
  
    -   Microsoft.BizTalk.Adapters.TibcoRV    
    -   Microsoft.BizTalk.Adapters.TibcoRV.Common    
    -   Microsoft.BizTalk.Adapters.TibcoRV.Service    
    -   Microsoft.BizTalk.Adapters.TibRV.Properties    
    -   Microsoft.BizTalk.Adapters.TibcoEMS    
    -   Microsoft.BizTalk.Adapters.TibcoEMS.Properties    
    -   Microsoft.BizTalk.Adapters.TibcoRVManagement    
    -   Microsoft.BizTalk.Adapters.TibcoRVReceiver  
    -   Microsoft.BizTalk.Adapters.TibcoRVTransmitter  
  
* 特定于适配器的文件安装在*Program Files 和 Program Files\Common Files*。 以下文件安装在*Program Files\Microsoft BizTalk Adapters for Enterprise Applications\ tibco （) Rendezvous(r)*:  
  
    -   bin\BTATibcoRVTrace.cmd    
    -   bin\mbaRV.exe    
    -   bin\Microsoft.BizTalk.Adapters.TibcoRV.Common.dll    
    -   bin\Microsoft.BizTalk.Adapters.TibcoRV.dll    
    -   bin\Microsoft.BizTalk.Adapters.TibcoRV.Service.dll    
    -   bin\Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll    
    -   bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll    
    -   Config\btaTibcoRVTrace.mof    
    -   sdk\  
  
* *用于企业应用程序进行编程 Files\Common Files\Microsoft BizTalk Adapters*包含以下文件：  
  
    -   bin\tibcorvcba.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
### <a name="add-tibcorendezvousdll-to-the-gac"></a>添加 TIBCO。Rendezvous.dll 到 GAC  
 用于 TIBCO Rendezvous 的 BizTalk 适配器要求**TIBCO。Rendezvous.dll**文件。 所需的最低版本是 1.0.3036.23330 附带的产品版本 8.1 的文件版本。 如果未安装此程序集，则适配器会触发异常并记录相应的消息。  
  
 必须使用后期绑定加载程序集，以便当特定版本的 TIBCO TIBCO Rendezvous 程序集不会发生故障。Rendezvous.dll 和 TIBCO。Rendezvous.net 模块不是目标计算机上。
  
 **运行时组件**  
  
 验证你的计算机上安装了 TIBCO Rendezvous 运行时组件。 运行时组件是安装 TIBCO Rendezvous 时必须安装的唯一组件。  

1. 在 Visual Studio 命令提示符中，将目录更改为 TIBCO 的位置。Rendezvous.dll 文件。 在 TIBCO rendezvous 默认安装此 DLL 的路径是**C:\TIBCO\TIBRV\BIN\TIBCO。Rendezvous.dll**。  
  
2. 在命令提示符下键入以下内容：  
  
```
C:\TIBCO\TIBRV\BIN > gacutil /i TIBCO.Rendezvous.dll
```
  
 TIBCO.Rendezvous.dl 现在显示 GAC 列表。 若要查看列表中，在控制面板中，打开**管理工具**，打开**Microsoft.NET Framework 配置**，然后打开**程序集缓存**。  
  
## <a name="post-install---tibco-enterprise-message-service"></a>安装后的 TIBCO Enterprise Message Service  
 Microsoft BizTalk 适配器包含 TIBCO Enterprise Message Service (EMS) 接收和传输与支持的数据库和服务器系统与 BizTalk Server 进行交互的功能。  
  
- 接收端侦听来从服务器系统出站的调用。  

- 传输端使你能够从 BizTalk 服务器调用服务器系统。  
  
  请参阅有关如何使用用于 TIBCO EMS 的 BizTalk 适配器以及其模型和 BizTalk 服务器模型之间的映射信息的适配器文档。  
  
### <a name="installed-components"></a>已安装的组件  
* 适配器安装安装并注册`Microsoft.BizTalk.Adapters.TibcoEMS.dll`全局程序集缓存 (GAC) 中的文件。 你可以通过在资源管理器中打开的程序集文件夹以验证注册 (< %WINDIR%> \assembly)，或使用`gacutil /l`从 Visual Studio 命令提示符。
  
* 特定于适配器的文件安装在*Program Files*并*Program Files\Common Files*。 以下文件安装在*Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) 企业消息 Service(TM)*:  
  
    -   bin\BTATibcoEMSTrace.cmd    
    -   Microsoft.BizTalk.Adapters.TibcoEMS.dll    
    -   Config\btaTibcoEMSTrace.mof    
    -   sdk\  
  
* *程序 Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin*文件夹包含以下文件：  
  
  - Microsoft.BizTalk.Adapters.CoreManagement.dll    
  - Microsoft.BizTalk.Adapters.CoreReceiver.dll    
  - Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
    > [!NOTE]
    >  必须使用后期绑定加载程序集，以便当特定版本的 TIBCO TIBCO EMS 程序集不会失败。EMS.dll 不存在于目标计算机上。  
  
### <a name="add-tibcoemsdll-api-to-the-gac"></a>添加 TIBCO。EMS.dll API 到 GAC  
 用于 TIBCO EMS 的 BizTalk 适配器要求将 TIBCO.EMS.dll 添加到 GAC。 如果未安装该程序集，则用于 TIBCO EMS 的 BizTalk 适配器触发异常并记录相应的消息。  
  
1. 将 TIBCO EMS C #API 复制到 BizTalk 计算机。  
  
2. 在 Visual Studio 命令提示符中，将目录更改为 C# API 文件的位置。  
  
3. 在 Visual Studio 命令提示符中，键入以下命令：  
  
   ```
   C:\\<TIBCO EMS Folder\>bin> gacutil /i TIBCO.EMS.dll
   ```
  
   TIBCO.EMS.dll 现在显示在 C:\Windows\assembly 列表中。 或者，在控制面板中打开**管理工具**，打开**Microsoft.NET Framework**，并打开**程序集缓存**若要查看 GAC 列表。  
  
   **限制**  
  
   用于 TIBCO EMS 的 BizTalk 适配器使用 TIBCO。若要与服务器通信的 EMS.dll。 使用 TIBCO.EMS.dll 的限制如下：  
  
4. 消息压缩不可用，它允许 TIBCO EMS 客户端以压缩格式向 EMS 发送消息。  
  
5. 适配器与服务器之间的消息加密不可用。 TIBCO.EMS.dll 不允许 SSL 加密使用 OpenSSL 库，但适配器使用 ProductVersion 5.0 及以上的 Tibco.EMS.dll 支持 SLL。  
  
6. 不支持用于 EMS 的管理 API。  
  
## <a name="adapter-tracing"></a>适配器跟踪

### <a name="enable-tracing"></a>启用跟踪
 Windows 跟踪所用的文件名由管理员决定。 应用程序写入到操作系统，除非你想要关于特定后端系统的日志，否则此操作将忽略所有日志。 通过运行一个单独的用于企业应用程序的 BizTalk 适配器的命令文件来执行此操作。 该命令的参数之一是文件的用于捕获的跟踪信息的名称。 有关详细信息，请参阅"使用 Windows 跟踪事件"（在本主题中）。
  
 跟踪文件安装到 * \Program Files\Microsoft BizTalk Adapters for Enterprise Applications\*。  
  
-   bin\BTATrace.cmd    
-   config\btaTrace.mof  
  
### <a name="use-windows-trace-event"></a>使用 Windows 跟踪事件  
 适配器将错误、警告和信息性消息记录到 Windows 事件查看器。 可以使用 Windows 事件跟踪 (ETW) 工具来查看更多的跟踪消息。 如果启用 ETW，将创建一个 *.etl 文件以接收消息。 该文件为二进制格式，必须将其转换为可读格式。 若要执行此操作，必须提供要解释的使用者应用程序\*.etl 文件，例如，Windows tracerpt.exe 或 tracedmp.exe。  
  
### <a name="etw-components"></a>ETW 组件
  
 Windows 事件跟踪包括以下三个组件：  
  
* **控制器应用程序：** 激活和停用提供程序。 例如，tracelog.exe 或 logman.exe。  
  
    设置 PATH 环境变量以指向 tracelog.exe 的位置。 这可确保该 BTA < 适配器名称\>跟踪调用可以在系统中找到 tracelog.exe。 默认情况下，BTA < 适配器名称\>跟踪搜索当前路径。  
  
    > [!NOTE]
    >  tracelog.exe 可以从 Microsoft SDK，并与提供的 Microsoft BizTalk 适配器用于企业应用程序的命令兼容。 若要使用 logman.exe，请参阅 logman 文档。  
  
* **使用者应用程序：** 读取记录的事件。  
  
    为了让使用者应用程序能够读取 .etl 文件中的事件，Windows 事件跟踪必须将其转储到该文件中。 通常，当控制器停用跟踪时执行此操作。  
  
    若要使用使用者应用程序不停用跟踪的情况下，控制器必须激活使用实时选项时，跟踪 **< 实时\>=-rt**。  
  
* **提供程序：** 用于提供事件。  
  
    每个适配器包括五个不同的提供程序。 它们在 Windows Management Instrumentation (WMI) 中进行注册。 若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。  
  
    五个提供程序允许你记录不同种类的消息：  
  
        -   **Receiver Logging Provider**: The <Trace element\> switch is - **receiver**.    
        -   **Receiver CastDetails Provider**: The <Trace element\> switch is - **castDetailsReceive**.    
        -   **Transmitter Logging Provider**: The <Trace element\> switch is - **transmitter**.    
        -   **Transmitter CastDetails Provider**: The <Trace element\> switch is - **castDetailsTransmit**.    
        -   **Management Logging Provider**: The <Trace element\> switch is - **management**.  
  
若要使用 ETW，运行该命令为特定的适配器： `BTA<Adapter Name\>Trace.cmd`。 如下所示使用此命令：  
  
```  
BTA<Adapter Name>Trace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA<Adapter Name>Trace <Trace element> -stop  
  
```  
  
 其中：  
  
**< 跟踪元素\>** （必需） 是一种的提供程序。 相应的选项包括：  
  
 **-castDetailsTransmit**  
  
 **-发送器**  
  
 **-castDetailsReceive**  
  
 **-接收方**  
  
 **-管理**  
  
 **-启动、-停止：** 激活或停用该提供程序。  
  
 **-cir < MB\>:** 文件的大小和类型。 **-cir**是循环文件。 **< MB\>:** 大小以兆字节为单位。  
  
 **-seq < MB\>:** 文件的大小和类型。 **-seq**是顺序文件。 **< MB\>:** 大小以兆字节为单位。  
  
 **-rt:** 上设置实时模式。  
  
 **日志文件：** 日志文件的名称 （c:\rtlog.etl 是默认值）。  
  
 例如：  
  
```  
BTAXXXTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAXXXTrace -transmitter -stop  
  
```  
  
> [!NOTE]
>  使用 tracerpt.exe 命令设置 .etl 文件的格式。  

## <a name="next-steps"></a>后续步骤
* [JD Edwards EnterpriseOne 适配器](../core/jd-edwards-enterpriseone-adapter.md)
* [JD Edwards OneWorld 适配器](../core/jd-edwards-oneworld-adapter.md)
* [PeopleSoft Enterprise 适配器](../core/peoplesoft-enterprise-adapter.md)
* [TIBCO Enterprise Message Service 适配器](../core/tibco-enterprise-message-service-adapter.md)
* [TIBCO Rendezvous 适配器](../core/tibco-rendezvous-adapter.md)
