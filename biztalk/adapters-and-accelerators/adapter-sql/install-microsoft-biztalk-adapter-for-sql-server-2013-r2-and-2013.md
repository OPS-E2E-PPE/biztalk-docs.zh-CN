---
title: "安装 Microsoft BizTalk Adapter for SQL Server-2013 R2 和 2013年 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56c31d0d-783b-41ee-8265-56c9547e9dca
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af91ae787d5800738865980609bb86f96a73bfb8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2013-r2-and-2013"></a>安装 Microsoft BizTalk Adapter for SQL Server-2013 R2 和 2013
安装[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]附带[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]，或包含[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]2013年。

 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以与使用：  
  
-   .NET 应用程序  
  
-   Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  
  
 所需的软件基于如何使用适配器，而异。  
 
<a name="BKMK_Prereqs_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a>.NET 应用程序中使用该适配器时的先决条件  
要在其中编写.NET 应用程序使用的计算机上安装以下软件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 列出的顺序安装软件。  

|2013 R2|2013|  
|---|---|  
|[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]|Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]|  
|Visual Studio 2013|Visual Studio 2012|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|  
|SQL Server 客户端库。 实例时都提供 SQL Server 登录名。|SQL Server 客户端库...|  

<a name="BKMK_Prereqs_BTS"></a>    
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a>与 BizTalk Server 使用适配器时的先决条件  
将使用你在计算机上安装以下软件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 我们建议以下列出的相同顺序安装软件。  
 
 |2013 R2|2013|  
|---|---|  
|[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]|Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]|  
|Visual Studio 2013|Visual Studio 2012|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> 安装[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]为[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> 安装[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]为[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。|  
|BizTalk Server 2013 R2|BizTalk Server 2013|  
|SQL Server 客户端库。 |SQL Server 客户端库。 |  

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a>支持的 SQL Server 版本和客户端库  
 下面的部分介绍支持的 SQL Server 版本和客户端所需的库[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
-   **支持的服务器版本**: SQL Server 2005、 SQL Server 2008 SP1、 SQL Server 2008 R2、 SQL Server 2012  
  
-   **支持的客户端版本**: Microsoft[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]捆绑包连接到 SQL Server 所需的客户端 Dll。 不需要显式安装在计算机上的任何客户端 Dll。  
  
-   **所需驱动程序**:  
  
    -   如果你使用随 SQL Server 版本，例如，Geography，Udt 请确保以下 Dll 计算机上存在其中你使用该适配器在 SQL Server 上执行操作。 例如，如果你创建 BizTalk 项目，在 SQL Server 上执行操作，这些 Dll 必须存在于运行 BizTalk Server 的计算机上。  
  
        -   请确保 Microsoft.SqlServer.Types.dll 已添加到 GAC。  
  
        -   确保 SqlServerSpatial.dll System32 文件夹中可用。  
  
         可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-基本**和**管理工具 – 完整**中**功能选择**向导页。  
  
    -   如果你使用该适配器上的 FILESTREAM 数据类型的列执行操作，请确保已安装的 SQL 客户端连接 SDK。 你可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。 适配器使用 sqlncli10.dll，安装 SQL 客户端连接 SDK，与执行 FILESTREAM 操作。  
  
    -   如果在 SQL Server 中创建你自己的 Udt，请确保 Udt 的相应程序集添加到 GAC。  
  
<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a>64 位支持 

[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以在一个 32 位或 64 位主机实例中运行。

 有关的 32 位和 64 位的受支持的安装方案的详细信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 
  
<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a>安装 SQL 适配器  
 请确保已在安装之前安装的先决条件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 你可以安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以下两种方式：  
  
-   **在交互模式中**使用安装向导  
  
-   **在静默模式下**命令中使用 msiexec 链接  
  
    > [!IMPORTANT]
    >  必须将在其中安装的计算机上具有管理特权[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，不管是否使用向导或命令行安装。  
  
<a name="BKMK_Install_Scenarios"></a>   
### <a name="32-bit-and-64-bit-install-scenarios"></a>32 位和 64 位安装方案
 与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可用于：  
  
-   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]设计时 （在生成操作的元数据）。  
  
-   BizTalk Server 管理控制台 （用于创建的物理端口） 的设计时。  
  
    > [!NOTE]
    >  BizTalk Server 管理控制台将作为 32 位 Microsoft 管理控制台 (MMC) 应用程序运行。  
  
-   BizTalk 运行时 （发送和接收消息时从 LOB 应用程序）。  
  
 你可以安装在同一台计算机或不同计算机上执行所有这些任务的位置。 因为同时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和 BizTalk MMC 是 32 位进程，则必须安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]你想要执行的设计时任务的计算机上。 安装支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 32 位和 64 位平台上。  
  
#### <a name="install-scenarios-on-a-32-bit-platform"></a>在 32 位平台上安装方案  
 在安装时支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 32 位平台上。  
  
|Visual Studio 设计时|BizTalk MMC 设计时|BizTalk 运行时|Visual Studio 设计时和/或 BizTalk MMC 设计时 + BizTalk 运行时|  
|---|---|---|---|  
|-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他必要的 Dll。|-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他必要的 Dll。|-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他必要的 Dll。|-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他必要的 Dll。|  
  
#### <a name="install-scenarios-on-a-64-bit-platform"></a>在 64 位平台上安装方案  
 在安装时支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 64 位平台上。  
  
> [!NOTE]
>  你想要使用的设计时任务执行的任何计算机上[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或者 BizTalk MMC 中，则必须安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
|Visual Studio 设计时|BizTalk MMC 设计时|BizTalk 运行时|Visual Studio 设计时和/或 BizTalk MMC 设计时 + BizTalk 运行时|  
|---|---|---|---|  
|-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他必要的 Dll。|-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他必要的 Dll。|**对于 32 位 BizTalk 进程**:<br /><br /> -安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他必要的 Dll。<br /><br /> **对于 64 位 BizTalk 进程**:<br /><br /> -安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> -安装 64 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 64 位客户端和其他必要的 Dll。|**对于 32 位 BizTalk 进程**:<br /><br /> -安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他必要的 Dll。<br /><br /> **对于 64 位 BizTalk 进程**:<br /><br /> -安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> -安装 64 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 64 位客户端和其他必要的 Dll。<br /><br /> -安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他必要的 Dll。|  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-sql-adapter-in-interactive-mode"></a>在交互模式中安装 SQL 适配器  
 
1.  运行安装程序。  
  
    > [!NOTE]
    >  如果你正在安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上虚拟机，安装向导可能不会继续超出了通知，安装程序正在检查可用磁盘空间的对话框。 在这种情况下，我们建议你使用的无提示安装选项。   
  
2.  阅读欢迎屏幕上的信息，然后单击**下一步**。  
  
3.  阅读并接受最终用户许可协议 (EULA)，然后单击**下一步**。  
  
4.  在**目标文件夹**对话框框中，指定你想要安装的位置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，单击**下一步**，然后单击**安装**。  
  
5.  在**客户体验改善计划**对话框框中，指定是否想要注册的客户体验改善计划 (CEIP)。 有关 CEIP 的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您将与 Microsoft 共享的下列数据：  
  
    -   与你正在其安装的计算机硬件相关的数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
    -   与你用来连接使用的 SQL Server 版本相关的数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
     指定你选择和单击**确定**。  
  
    > [!NOTE]
    >  你始终可以更改您的首选项有关在修复模式下运行安装程序，从控制面板注册 CEIP。  
  
6.  单击 **“完成”**。  
  
<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a>在无提示模式下安装 SQL 适配器  
 下面的过程演示如何执行无提示安装的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用`msiexec`命令。  
  
1.  打开命令提示符，并导航到你有安装文件夹。  
  
2.  运行以下命令以安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
    > [!NOTE]
    >  若要执行无提示安装在基于 x64 的平台上，在以下命令，将替换为 SqlAdapterSetup64.msi SqlAdapterSetup.msi。  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn  
    ```  
  
     你还可以选择注册 CEIP 的无提示安装的一部分。 有关 CEIP 的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您将与 Microsoft 共享的下列数据：  
  
    -   你正在其安装的计算机硬件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
    -   你要用于连接使用的 SQL Server 版本[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
     若要注册 CEIP，运行以下命令：  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
    ```  
  
     默认情况下，选项为 false。  
  
     有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或请参阅[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)。  
  
<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a>安装后任务  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a>注册绑定  
完成这些步骤*仅*如果安装向导无法在 machine.config 文件中注册的适配器绑定。  
  
1.  导航到计算机上的 machine.config 文件。 例如，在 32 位平台上，machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  
  
    -   对 Microsoft.NET Framework 3.5 SP1， \<*版本*\>是.NET Framework 版本 v2.0.50727。  
  
    -   Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]， \<*版本*\>是.NET Framework 版本 v4.0.30319。  
  
2.  打开使用文本编辑器的文件。  
  
3.  若要注册的适配器绑定：  
  
    1.  搜索的元素"的 system.serviceModel"和其下添加以下：  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。  
  
    3.  添加以下节"bindingElementExtensions"节点下。  
  
         有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  搜索"bindingExtensions"system.serviceModel\extensions 下的元素。  
  
    5.  添加以下节"bindingExtensions"节点下。  
  
         有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
      
  
4.  保存并关闭 machine.config 文件。  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a>确定的公钥和版本  
完成以下步骤来确定的公钥和版本[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
1.  导航到 Windows 目录中，通常 C:\WINDOWS\assembly。  
  
2.  右键单击该 DLL 为其您希望将公钥，，然后选择**属性**。 下表列出的 Dll 的名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
    |适配器|DLL 的名称|  
    |---|---|  
    |[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]|Microsoft.Adapters.Sql.dll|  
  
3.  上**常规**选项卡上，针对值**Public Key Token**标签指定 DLL 的公共密钥。 同样，针对值**版本**标签指定的 dll 的版本号。  
  
4.  复制公钥，，然后单击**取消**。  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a>更新或更改 SQL 适配器安装  
 执行以下步骤以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。 请确保你具有[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装之前您运行安装向导以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。  
  
 你可以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装以下两种方式：  
  
-   **在交互模式中**通过运行安装向导。  
  
-   **在静默模式下**通过使用命令行。  
  
#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a>更新 SQL 适配器安装在交互模式中  
  
1.  单击**启动**，然后单击**控制面板**。  
  
2.  在 Control Panel 中，双击**程序和功能**。  
  
3.  在**程序和功能**窗口中，选择**用于 SQL Server 的 Microsoft BizTalk Adapter**，然后单击**更改**。  
  
4.  阅读欢迎屏幕上的信息，然后单击**下一步**。  
  
5.  在**更改、 修复或删除安装**对话框中，单击**修复**。  
  
6.  在**准备好修复 Microsoft BizTalk Adapter for SQL Server**对话框中，单击**修复**。  
  
7.  如果需要，更改你的首选项有关选择加入的 CEIP，，然后单击**确定**。  
  
8.  单击 **“完成”**。  
  
#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a>更新 SQL 适配器安装在静默模式下  
  
1.  打开命令提示符，并导航到的根目录下[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。  
  
2.  运行以下命令：  
  
    > [!NOTE]
    >  若要修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装在静默模式下，在基于 x64 的平台上，在以下命令，将替换为 SqlAdapterSetup64.msi SqlAdapterSetup.msi。  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn /f  
    ```  
  
    > [!IMPORTANT]
    >  修改时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在静默模式下的安装，不能更改用于选择加入或退出 CEIP 首选项。 首选项将保持不变按照您指定在安装期间，即使您显式将 CEIP_OPTIN 设置为 true 或 false。  
  
     有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或请参阅[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)。   
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a>卸载或删除 SQL 适配器  
 执行以下步骤以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从您的计算机。 请确保你具有[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装在运行安装向导以删除之前[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 你可以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以下两种方式：  
  
-   **在交互模式中**通过运行安装向导。  
  
-   **在静默模式下**通过使用命令行。  
  
#### <a name="uninstall-in-interactive-mode"></a>在交互模式中卸载  
  
1.  单击**启动**，然后单击**控制面板**。  
  
2.  在 Control Panel 中，双击**程序和功能**。  
  
3.  在**添加或删除程序**窗口中，选择**用于 SQL Server 的 Microsoft BizTalk Adapter**，然后单击**删除**。  
  
4.  在对话框中，单击**是**。  
  
#### <a name="uninstall-in-silent-mode"></a>在静默模式下卸载  
  
1.  打开命令提示符，并导航到的根目录下[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。  
  
2.  运行以下命令：  
  
    > [!NOTE]
    >  若要删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在静默模式下，在基于 x64 的平台上，在以下命令，将替换为 SqlAdapterSetup64.msi SqlAdapterSetup.msi。  
  
    ```  
    msiexec /x SqlAdapterSetup.msi /qn  
    ```  
  
     此命令删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从计算机。  
  
     有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或请参阅[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)。  
  
<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a>卸载后任务  
 如果[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序无法删除适配器绑定，同时删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，则必须手动删除它们。 以下部分介绍如何手动删除的绑定[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
<a name="BKMK_Remove_Binding"></a>   
#### <a name="manually-remove-the-bindings"></a>手动删除绑定  
 执行这些步骤*仅*如果安装向导无法从 machine.config 文件中删除适配器绑定。  
  
1.  导航到计算机上的 machine.config 文件。 例如，在 32 位平台上，machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  
  
    -   对 Microsoft.NET Framework 3.5 SP1， \<*版本*\>是.NET Framework 版本 v2.0.50727。  
  
    -   Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]， \<*版本*\>是.NET Framework 版本 v4.0.30319。  
  
2.  打开使用文本编辑器的文件。  
  
3.  删除适配器绑定注册：  
  
    1.  搜索的元素"的 system.serviceModel"，然后删除该元素从以下：  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。  
  
    3.  删除"bindingElementExtensions"节点下的以下部分。  
  
         有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，删除：  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  搜索"bindingExtensions"system.serviceModel\extensions 下的元素。  
  
    5.  删除"bindingExtensions"节点下的以下部分。  
  
         有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，删除：  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  保存并关闭 machine.config 文件。  
  
## <a name="see-also"></a>另请参阅
[安装 SQL 适配器](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[了解用于 SQL Server 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)