---
title: 安装 Microsoft BizTalk Adapter for SQL Server-2016年 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcc6b94e-1cac-4b90-8567-05b33caa9bf3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15681ec21d399e03d86ec9457d814cf4531ed30b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369360"
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2016"></a>安装 Microsoft BizTalk Adapter for SQL Server-2016
安装[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]附带[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。

 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可用于：  

- .NET 应用程序  

- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  

  根据如何使用适配器，所需的软件各不相同。  


<a name="BKMK_prereq_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a>使用.NET 应用程序中使用适配器时的先决条件  
要在其中编写的.NET 应用程序使用的计算机上安装以下软件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 列出的顺序安装软件。  

||
|---|
|- Windows Server 2016 <br />- Windows Server 2012 R2 <br />- Windows 10 <br />- Windows 8.1    |
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|
|SQL Server 客户端库。 请参阅[受支持的版本](#BKMK_SuppLOB)（在本主题中）。|

<a name="BKMK_prereq_BTS"></a>     
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a>使用适配器与 BizTalk Server 时的先决条件  
： 您正在使用的计算机上安装以下软件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 按所列顺序安装软件。  

||
|---|
|- Windows Server 2016 <br />- Windows Server 2012 R2 <br />- Windows 10 <br />- Windows 8.1    |
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> 安装[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]有关[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。|
|[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|
|SQL Server 客户端库。 请参阅[受支持的版本](#BKMK_SuppLOB)（在本主题中）。|

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a>支持的 SQL Server 版本和客户端库  
 以下部分提供支持的 SQL Server 版本和客户端所需的库[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

- **支持的服务器版本**:SQL Server 2016, SQL Server 2014

- **支持的客户端版本**:Microsoft[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]捆绑包连接到 SQL Server 所需的客户端 Dll。 不需要在您的计算机上显式安装任何客户端 Dll。  

- **所需的驱动程序**:  

  - 如果使用 Udt 附带的 SQL Server 版本，例如，地理位置，请确保以下 Dll 计算机上存在其中使用该适配器在 SQL Server 上执行操作。 例如，如果在 BizTalk 项目，在 SQL Server 上执行操作，这些 Dll 必须在运行 BizTalk Server 的计算机上存在。  

    - 请确保 Microsoft.SqlServer.Types.dll 添加到 GAC。  

    - 确保 SqlServerSpatial.dll System32 文件夹中可用。  

      可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-Basic**并**管理工具-完整**中**功能选择**向导页。  

  - 如果使用适配器来执行对 FILESTREAM 数据类型的列的操作，请确保已安装的 SQL 客户端连接 SDK。 可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。 适配器使用 sqlncli10.dll，随 SQL 客户端连接 SDK，用于执行 FILESTREAM 操作。  

  - 如果在 SQL Server 中创建你自己的 Udt，请确保对 Udt 的相应程序集添加到 GAC。  

<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a>64 位支持 

[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以运行的 32 位或 64 位主机实例中。

 有关为 32 位和 64 位支持的安装方案的信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[32 位和 64 位安装方案](#BKMK_Install_Scenarios)（在本主题中）。

<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a>安装 SQL 适配器  
 请确保已安装之前安装必备组件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 请参阅[.NET 系统必备组件](#BKMK_prereq_NET)（在本主题中），或[BizTalk Server 必备组件](#BKMK_prereq_BTS)（在本主题中）。

 你可以安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以下两种方式：  

- **在交互模式下**使用安装向导

- **在静默模式下**使用 msiexec 命令行中  

  > [!IMPORTANT]
  >  必须在其中安装的计算机上具有管理特权[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，不考虑要使用向导或命令行安装。    

### <a name="BKMK_Install_Scenarios"></a> 32 位和 64 位安装方案
 与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可用于：  

- [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 设计时 （时生成的操作的元数据）。  

- BizTalk Server 管理控制台 （用于创建物理端口） 的设计时。  

  > [!NOTE]
  >  BizTalk Server 管理控制台作为 32 位 Microsoft 管理控制台 (MMC) 应用程序运行。  

- BizTalk 运行时 （发送和接收消息时的 LOB 应用程序）。  

  您可以安装在同一台计算机或不同的计算机上执行所有这些任务的位置。 因为这两[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]以及 BizTalk MMC 是 32 位进程，你必须安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]你想要执行的设计时任务的计算机上。 安装支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 32 位和 64 位平台上。  

#### <a name="32-bit-install-scenarios"></a>32 位安装方案  
 安装时，支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]32 位平台上。  


|                                                                                                               Visual Studio 设计时                                                                                                                |                                                                                                                BizTalk MMC 设计时                                                                                                                 |                                                                                                                    BizTalk 运行时                                                                                                                    |                                                                                      Visual Studio 设计时和/或 BizTalk MMC 设计时间 + BizTalk 运行时                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他所需的 Dll。 | 安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他所需的 Dll。 | 安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他所需的 Dll。 | 安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他所需的 Dll。 |

#### <a name="64-bit-install-scenarios"></a>64 位安装方案  
 安装时，支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]64 位平台上。  

> [!NOTE]
>  你想要执行设计时任务使用的任何计算机上[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]BizTalk MMC 中，你必须安装 32 位或[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

|                                                                                                               Visual Studio 设计时                                                                                                                |                                                                                                                BizTalk MMC 设计时                                                                                                                 |                                                                                                                                                                                                                                                                                                   BizTalk 运行时                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                    Visual Studio 设计时和/或 BizTalk MMC 设计时间 + BizTalk 运行时                                                                                                                                                                                                                                                                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他所需的 Dll。 | 安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他所需的 Dll。 | **对于 32 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他所需的 Dll。<br /><br /> **对于 64 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> 安装 64 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 64 位客户端和其他所需的 Dll。 | **对于 32 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他所需的 Dll。<br /><br /> **对于 64 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。<br /><br /> 安装 64 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 64 位客户端和其他所需的 Dll。<br /><br /> 安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。<br /><br /> -安装 32 位客户端和其他所需的 Dll。 |

<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-adapter-in-interactive-mode"></a>在交互模式下安装适配器  
完成以下步骤来安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用安装向导。  

1. 运行安装程序。  

   > [!NOTE]
   >  如果您正在安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]虚拟机上安装向导可能无法继续超出了对话框，通知安装程序正在检查的可用磁盘空间。 在这种情况下，我们建议你使用的无提示安装选项。 有关详细信息，请参阅[在无提示模式下安装 SQL 适配器](#BKMK_SilentInst)（在本主题中）。

2. 阅读欢迎屏幕上的信息，然后单击**下一步**。  

3. 阅读并接受最终用户许可协议 (EULA)，然后单击**下一步**。  

4. 在中**目标文件夹**对话框框中，指定你想要安装的位置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，单击**下一步**，然后单击**安装**。  

5. 在中**客户体验改善计划**对话框框中，指定是否想要注册的客户体验改善计划 (CEIP)。 有关 CEIP 的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您将与 Microsoft 共享的以下数据：  

   - 与正在其安装的计算机硬件相关的数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

   - 与用来连接使用的 SQL Server 版本相关的数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

     指定所选，然后单击**确定**。  

   > [!NOTE]
   >  你可以随时更改您的首选项有关注册 CEIP 通过从控制面板在修复模式下运行安装程序。  

6. 单击 **“完成”**。  

<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a>在无提示模式下安装 SQL 适配器 
完成以下步骤，若要执行的无提示安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用`msiexec`命令。  

1. 打开命令提示符，并导航到你有安装程序文件夹。  

2. 运行以下命令以安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  

   > [!NOTE]
   >  若要执行无提示安装在基于 x64 的平台上，在以下命令中，替换为 SqlAdapterSetup.msi SqlAdapterSetup64.msi。  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn  
   ```  

    您还可以选择无提示安装的一部分注册 CEIP。 有关 CEIP 的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您将与 Microsoft 共享的以下数据：  

   - 正在其安装的计算机硬件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

   - 用来连接使用的 SQL Server 版本[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

     若要注册 CEIP，运行以下命令：  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
   ```  

    默认情况下，选项为 false。  

    有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或参阅[ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781)。  

<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a>安装后任务  

<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a>注册绑定  
完成这些步骤*仅*如果安装向导无法注册适配器绑定在 machine.config 文件中。  

1. 导航到计算机上的 machine.config 文件。 例如，在 32 位平台上，在 machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  

2. 打开文件使用文本编辑器。  

3. 若要注册适配器绑定：  

   1. 搜索元素"的 system.serviceModel"并将其下的以下代码添加：  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. 搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。  

   3. 添加"bindingElementExtensions"节点下的以下部分。  

       有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. 搜索"bindingExtensions"system.serviceModel\extensions 下的元素。  

   5. 添加"bindingExtensions"节点下的以下部分。  

       有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  有关如何确定的公钥的信息，请参阅[确定公用密钥和版本](#BKMK_PubKey)。  

4. 保存并关闭 machine.config 文件。  

<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a>确定公用密钥和版本  
完成以下步骤来确定公用密钥和版本[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

1. 导航到 Windows 目录，通常 C:\WINDOWS\assembly。  

2. 右键单击的 DLL 为其也希望将公钥，并选择**属性**。 下表列出了的 Dll 名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  


   |                              适配器                              |      DLL 的名称       |
   |-------------------------------------------------------------------|----------------------------|
   | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] | Microsoft.Adapters.Sql.dll |


3. 上**常规**选项卡上，针对值**公钥标记**标签指定 DLL 的公共密钥。 同样，针对值**版本**标签指定 dll 的版本号。  

4. 复制公钥，，然后单击**取消**。  

<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a>更新或更改 SQL 适配器安装  
 执行以下步骤来修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。 请确保你拥有[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装，然后运行安装向导以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。  

 您可以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装以下两种方式：  

-   **在交互模式下**通过运行安装向导。  

-   **在静默模式下**使用命令行。  

#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a>更新在交互模式下安装 SQL 适配器  

1.  单击**启动**，然后单击**控制面板**。  

2.  在控制面板中，双击**程序和功能**。  

3.  在中**程序和功能**窗口中，选择**适用于 SQL Server 的 Microsoft BizTalk 适配器**，然后单击**更改**。  

4.  阅读欢迎屏幕上的信息，然后单击**下一步**。  

5.  在中**更改、 修复或删除安装**对话框中，单击**修复**。  

6.  在中**准备好修复 for SQL Server 的 Microsoft BizTalk 适配器**对话框中，单击**修复**。  

7.  如果需要，更改您的首选项有关选择加入 ceip，然后依次**确定**。  

8.  单击 **“完成”**。  

#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a>更新在静默模式下安装 SQL 适配器  

1. 打开命令提示符，并导航到的根目录下[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。  

2. 运行下面的命令：  

   > [!NOTE]
   >  若要修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在基于 x64 的平台，在以下命令中上, 无提示模式下安装替换 SqlAdapterSetup64.msi SqlAdapterSetup.msi。  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn /f  
   ```  

   > [!IMPORTANT]
   >  修改时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在静默模式下安装，不能更改首选项的选择加入或退出 CEIP。 首选项将保持不变作为安装过程中，指定即使 CEIP_OPTIN 显式设置为 true 或 false。  

    有关详细信息`msiexec`命令类型`msiexec`上的命令行和按`ENTER`，或参阅[ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781)。  

<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a>卸载或删除 SQL 适配器  
 执行以下步骤以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从您的计算机。 请确保你拥有[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装，然后运行安装向导以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

 您可以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以下两种方式：  

-   **在交互模式下**通过运行安装向导。  

-   **在静默模式下**使用命令行。  

#### <a name="uninstall-the-sql-adapter-in-interactive-mode"></a>卸载在交互模式下的 SQL 适配器  

1.  单击**启动**，然后单击**控制面板**。  

2.  在控制面板中，双击**程序和功能**。  

3.  在中**添加或删除程序**窗口中，选择**适用于 SQL Server 的 Microsoft BizTalk 适配器**，然后单击**删除**。  

4.  在对话框中，单击**是**。  

#### <a name="uninstall-the-sql-adapter-in-silent-mode"></a>卸载在静默模式下的 SQL 适配器  

1. 打开命令提示符，并导航到的根目录下[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。  

2. 运行下面的命令：  

   > [!NOTE]
   >  若要删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在无提示模式在基于 x64 的平台，在以下命令中，替换为 SqlAdapterSetup.msi SqlAdapterSetup64.msi。  

   ```  
   msiexec /x SqlAdapterSetup.msi /qn  
   ```  

    此命令将删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从计算机。  

    有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或参阅[ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781)。  

<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a>卸载后任务  
 如果[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序无法删除适配器绑定，同时删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您必须手动将其删除。 以下部分介绍如何手动删除的绑定[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

完成这些步骤*仅*如果安装向导无法从 machine.config 文件中删除适配器绑定。  

1. 导航到计算机上的 machine.config 文件。 例如，在 32 位平台上，在 machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  

   - 用于 Microsoft.NET Framework 3.5 SP1 中， \<*版本*\>是.NET Framework 版本 v2.0.50727。  

   - Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]， \<*版本*\>是.NET Framework 版本 v4.0.30319。  

2. 打开文件使用文本编辑器。  

3. 若要删除适配器绑定注册：  

   1. 搜索的元素"的 system.serviceModel"并删除以下从元素下：  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  

      ```  

   2. 搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。  

   3. 删除"bindingElementExtensions"节点下的以下部分。  

       有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，删除：  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. 搜索"bindingExtensions"system.serviceModel\extensions 下的元素。  

   5. 删除"bindingExtensions"节点下的以下部分。  

       有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，删除：  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

4. 保存并关闭 machine.config 文件。  

## <a name="see-also"></a>另请参阅
[安装 SQL 适配器](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[了解用于 SQL Server 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)