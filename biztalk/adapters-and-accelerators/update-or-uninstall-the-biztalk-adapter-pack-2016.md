---
title: 更新或卸载 BizTalk 适配器包 2016年 |Microsoft 文档
description: 使用安装向导或 msiexec 来更改或卸载 BAP 2016 附带 BizTalk Server;包括删除绑定，删除了自定义的 Rfc
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3d6c001-1005-4d7b-a143-eaa37b48f898
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb0dd0b9d778f878df9a06efdfc0f41754403690
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967995"
---
# <a name="update-or-uninstall-the-biztalk-adapter-pack-2016"></a>更新或卸载 BizTalk 适配器包 2016
如何更改或卸载[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。

<a name="BKMK_Modify_Adap"></a>
## <a name="change-or-update-the-installation"></a>更改或更新安装  
在运行安装向导以修改之前[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，请确保[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]安装。 
  
 你可以修改安装在交互模式下 （安装程序向导），或在静默模式下 （命令行）。
  
### <a name="use-the-setup-wizard"></a>使用安装向导  
  
1.  使用 BizTalk Server Administrators 组的成员的帐户登录。  
  
2.  在**程序和功能**，选择**卸载程序**。  
  
3.  右键单击**Microsoft BizTalk 适配器包**，然后选择**更改**。  
  
4.  在欢迎屏幕上，选择**下一步**。  
  
5.  在**更改、 修复或删除安装**:  
  
    -   若要选择你想要安装的组件，选择**更改**并转到步骤 6。  
  
    -   若要修复最新安装中的错误，选择**修复**并转到步骤 7。  
  
    -   若要删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]从计算机上，选择**删除**，然后转到步骤 10。  
  
6.  如果你选择要修改安装：  
  
    -   展开**Microsoft BizTalk 适配器包**节点，以选择要安装的基的适配器和 / 或.NET Framework 数据提供程序。  
  
    -   展开**基适配器**节点，以选择安装所有适配器或特定的适配器。  
  
    -   展开**ADO 提供程序**节点，以选择安装所有提供程序或特定的提供程序安装。  
  
    -   选择“下一步” 。  
  
    -   选择**更改**，然后选择**完成**。  
  
7.  如果你选择在修复安装，**准备好修复 Microsoft BizTalk 适配器包**对话框中，选择**修复**。 启动向导，修复安装。  
  
8.  如果需要，更改你的首选项有关选择加入的 CEIP，，然后选择**确定**。 
  
9. 选择“完成”。  
  
10. 如果您选择中删除适配器，**准备好删除 Microsoft BizTalk 适配器包**对话框中，选择**删除**，然后选择**完成**。  
  
### <a name="use-msiexec-in-silent-mode"></a>在静默模式下使用 msiexec  
  
1.  打开命令提示符，并转到根目录下的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序。  
  
2.  运行如下命令：  
  
    > [!NOTE]
    >  若要修改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在基于 x64 的平台上，在以下命令，以无提示模式安装替换`AdaptersSetup.msi`与`AdaptersSetup64.msi`。  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
    ```  
  
     此命令删除[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，并安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]。  
  
     通过使用不同的值`REMOVE`和`ADDLOCAL`属性，可以添加或删除特定的组件。 中的表是指**在无提示模式下安装**在[安装 BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)有关你可以使用这些属性的值。  
  
     你还可以通过为 msiexec 命令的一部分使用 /f 选项来执行无提示的修复。 例如：  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn /f  
    ```  
  
     带 /f 选项，可以使用各种不同的组合。 有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。 或转到[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)。  
  
    > [!IMPORTANT]
    >  修改时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下的安装，不能更改用于选择加入或退出 CEIP 首选项。 在过程中选择该安装将保持，即使你显式设置为 true 或 false 的 CEIP_OPTIN 首选项。  

## <a name="uninstall-or-remove-the-biztalk-adapter-pack"></a>卸载或删除 BizTalk 适配器包  
  
> [!IMPORTANT]
>  如果你在要使用的 tRFC 功能的 SQL Server 数据库中创建表[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，你必须手动卸载之前删除它们[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装副本`SapAdapter-DbScript-Uninstall.sql`文件通常在*\<安装驱动器\>: files\microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]* 。 运行此文件，以删除你创建的表。  
  
完成以下步骤以删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]从您的计算机。 请确保你具有[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]安装之前您运行安装向导。  
  
 你可以删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在交互模式 （安装程序向导） 中或在静默模式下 （命令行）。
  
### <a name="uninstall-using-the-setup-wizard"></a>卸载使用安装向导  
  
1.  在**程序和功能**，选择**卸载程序**。  
  
2.  右键单击**Microsoft BizTalk 适配器包**，然后选择**卸载**。  
  
### <a name="uninstall-in-silent-mode"></a>在静默模式下卸载  
  
1.  打开命令提示符，并转到根目录下的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序。  
  
2.  运行以下命令：  
  
    > [!NOTE]
    >  若要删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下，在基于 x64 的平台上，在以下命令，将`AdaptersSetup.msi`与`AdaptersSetup64.msi`。  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
    ```  
  
     此命令删除[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]从[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。  
  
     通过提供不同的值`REMOVE`属性，您可以删除从特定组件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。 中的表是指**在无提示模式下安装**在[安装 BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)有关你可以使用此属性的值。  
  
     若要完全删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，执行以下命令：  
  
    ```  
    msiexec /x AdaptersSetup.msi /qn  
    ```  
  
     有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。 或转到[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)。
  
## <a name="remove-the-bindings"></a>删除绑定  
 完成这些步骤*仅*如果安装向导无法从 machine.config 文件中删除适配器绑定或.NET Framework 数据提供程序注册。  
  
1.  转到计算机上的 machine.config 文件。 例如，在 32 位平台上，machine.config 位于下*\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG*。  
  
2.  打开使用文本编辑器的文件。  
  
3.  删除适配器绑定注册：  
  
    1.  搜索`system.serviceModel`元素，并删除以下从元素：  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  搜索`bindingElementExtensions`system.serviceModel\extensions 下的元素。  
  
    3.  删除以下各节下的`bindingElementExtensions`节点，具体取决于可用的适配器绑定。 如果安装向导删除任何失败，则必须删除所有绑定。  
  
         有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，删除：  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，删除：  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，删除：  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，删除：  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，删除：  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  搜索`bindingExtensions`system.serviceModel\extensions 下的元素。  
  
    5.  删除以下各节下的`bindingExtensions`节点，具体取决于可用的适配器绑定。 如果安装向导删除任何失败，则必须删除所有绑定。  
  
         有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，删除：  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，删除：  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，删除：  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，删除：  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，删除：  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  删除.NET Framework 数据提供程序注册：  
  
    -   搜索`DbProviderFactories`system.data 节点下的元素。  
  
    -   查找仍有注册.NET Framework 数据提供程序。 删除以下各节下的`DbProviderFactories`节点，具体取决于现有的.NET Framework 数据提供程序。 如果它们存在，则必须删除所有提供程序。  
  
         有关[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，删除：  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，删除：  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  保存并关闭 machine.config 文件。  
  
## <a name="remove-the-custom-rfcs"></a>删除自定义的 Rfc  
完成此步骤以删除 SAP 系统中安装了自定义 Rfc。 请参阅[安装或删除自定义的 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。  
  
