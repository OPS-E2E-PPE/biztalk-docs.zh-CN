---
title: "安装后步骤 BizTalk 适配器包 2016 |Microsoft 文档"
description: "步骤完成后安装 BAP 2016，包括将适配器添加到 BizTalk 管理、 更新 Oracle，和注册适配器绑定。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8946bfe-92bb-470d-bec4-9bc3a07ce0d2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17bd0a76cacb35563448f31f79c2275c79b92ab8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="post-installation-steps-for-biztalk-adapter-pack-2016"></a>BizTalk 适配器包 2016年的安装后步骤
安装之后[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，有一些安装后步骤。 本主题列出了这些步骤。   

## <a name="add-the-adapter-to-biztalk-administration"></a>将适配器添加到 BizTalk 管理
  
1.  打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  展开**BizTalk 组**，展开**平台设置**，然后选择**适配器**。  
  
3.  右键单击**适配器**，选择**新建**，然后选择**适配器**。  
  
     ![将适配器添加](../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4.  在**适配器属性**，如从下拉列表中，选择一个适配器**WCF SAP**，然后输入一个名称，例如**WCF SAP**。  
  
     ![将 SAP 适配器添加到 BizTalk](../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")  
  
5.  选择“确定”。  

## <a name="use-a-newer-oracledataaccessdll-version"></a>使用较新的 Oracle.DataAccess.dll 版本  

当配置要使用 WCF OracleDB 适配器，或者使用 Visual Studio 使用的生成的适配器的端口时，显示一条消息，该适配器需要 Oracle.DataAccess.dll 版本 2.111.7.0。 若要解决此消息，请安装支持的 Oracle.DataAccess.dll 版本 (请参阅[支持版本列表](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))，然后更新`bindingRedirect`OracleDB 配置文件使用以下步骤中的元素：  
  
1.  在 BizTalk Server 中，转到以下文件夹：  
  
     *驱动器*: files\microsoft BizTalk 适配器包 (x64) \bin  
  
     *驱动器*: \Program 文件 (x86) \Microsoft BizTalk Adapter Pack\bin  
  
2.  打开 Microsoft.Adapters.OracleDB.config 文件。  
  
3.  找到以下部分:，然后复制/粘贴以下：  
  
    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  
  
    ```  
  
    > [!NOTE]
    >  在此示例中，我们将设置*newVersion*到 2.112.1.00。 将此值设置为已安装的版本。  
  
> [!IMPORTANT]
> - 如果此组中有多个 BizTalk 服务器，请在组中的所有 BizTalk 服务器上进行此更改。  
> - *NewVersion*值需要更新的计算机上安装的 Oracle.DataAccess.dll 文件的版本。  Oracle.DataAccess.dll 都附带从 Oracle 安装 Oracle 客户端。  你只需安装的 Oracle 客户端版本[的 BizTalk 适配器包支持](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)。  
  
## <a name="create-sql-server-database-objects-sap-adapter-only"></a>创建 SQL Server 数据库对象 （仅适用于 SAP 适配器）  
 若要调用 tRFCs SAP 系统中，运行*SapAdapter DbScript Install.sql* SQL 脚本。 此脚本安装使用[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，并在 SQL Server 中创建数据库对象。 该脚本通常安装在*\<安装驱动器\>: files\microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]* 。 只要在使用该适配器调用 tRFCs 时输入该数据库名称，你可以针对任何 SQL Server 数据库，运行此脚本。
  
## <a name="register-the-adapter-bindings"></a>注册的适配器绑定
期间[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，安装向导可能无法注册的适配器绑定或.NET Framework 数据提供程序 mySAP Business Suite。 和安装程序将继续执行适配器安装。 这可能由 Windows Communication Foundation (WCF) 安装中，[!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。  

> [!IMPORTANT]
> 完成以下步骤*仅*如果安装向导无法在 machine.config 文件中注册的适配器的绑定或.NET Framework 数据提供程序。  
  
1.  转到计算机上的 machine.config 文件。 例如，在 32 位平台上，machine.config 位于下*\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG*。  
  
2.  打开使用文本编辑器的文件。  
  
3.  注册的适配器绑定：  
  
    1.  搜索`system.serviceModel`元素，并添加其下的以下：  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  搜索`bindingElementExtensions`system.serviceModel\extensions 下的元素。  
  
    3.  查找缺失的适配器绑定。 添加以下各节下的`bindingElementExtensions`节点，具体取决于缺少的适配器绑定。 如果安装向导无法注册任何，则必须注册的所有绑定。  
  
         有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，添加：  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，添加：  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，添加：  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，添加：  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，添加：  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  搜索`bindingExtensions`system.serviceModel\extensions 下的元素。  
  
    5.  查找缺失的适配器绑定。 添加以下各节下的`bindingExtensions`节点，具体取决于缺少的适配器绑定。 如果安装向导无法注册任何，则必须注册的所有绑定。  
  
         有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，添加：  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，添加：  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，添加：  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，添加：  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，添加：  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  若要获取的公钥值，请参阅**确定的公钥和版本**（本主题中）。  
  
4.  注册.NET Framework 数据提供程序：  
  
    1.  搜索`DbProviderFactories`system.data 节点下的元素。  
  
    2.  查找缺少的.NET Framework 数据提供程序。 添加以下各节下的`DbProviderFactories`节点，具体取决于缺少提供程序。 如果安装向导无法注册任何，则必须注册的所有提供程序。  
  
         有关[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，添加：  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，添加：  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  保存并关闭 machine.config 文件。  
  
## <a name="determine-the-public-key-and-version"></a>确定的公钥和版本  
 完成以下步骤以确定公钥和适配器或.NET Framework 数据提供程序的版本。  
  
1.  请转到 Windows 目录中，通常*C:\WINDOWS\assembly*。  
  
2.  右键单击该 DLL 为其您希望将公钥，，然后选择**属性**。 下表列出的每个适配器和提供程序 Dll 的名称：  
  
    |适配器/.NET Framework 数据提供程序|DLL 的名称|  
    |---|---|  
    |[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|Microsoft.Adapters.SAP|  
    |[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|Microsoft.Adapters.Siebel|  
    |[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|Microsoft.Adapters.OracleDB|  
    |[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|Microsoft.Adapters.OracleEBS|  
    |[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|Microsoft.Adapters.Sql.dll|  
    |[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|Microsoft.Data.SAPClient|  
    |[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|Microsoft.Data.SiebelClient|  
  
3.  上**常规**选项卡上， **Public Key Token**值是 DLL 的公共密钥。 **版本**值是 DLL 的版本号。  
  
4.  复制公钥，，然后选择**取消**。  
  
## <a name="install-the-custom-rfcs"></a>安装自定义的 Rfc  
仅为必填项*如果*你想要使用[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。 请参阅[安装自定义 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)中[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]文档。 
  
> [!IMPORTANT]
>  如果您将早期版本的自定义的 Rfc 随附[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，然后必须将它们升级到此版本中提供了 Rfc。 通过删除早期的 Rfc 中，执行此操作，然后安装了 Rfc 附带此版本。  

## <a name="install-the-enterprise-applications"></a>安装企业应用程序  
对于这些步骤和指南来安装不同企业 LOB 系统，我们建议你使用由企业系统提供的安装指南。 如果任何还引用特定的配置更改，及其适配器文档。   

## <a name="installation-and-post-installation-checklist"></a>安装和安装后的清单  
  
-   请确保安装所有[软件必备项](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)使用正确的安装选项。
  
-   请确保企业的 LOB 应用程序安装在计算机上安装受支持的版本[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 请参阅[支持的业务线 (LOB) 系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)。  
  
-   若要安装仅适用于企业你想要连接的 LOB 系统的适配器，请确保你安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]使用**自定义**安装选项。 请确保你未使用**完成**安装选项。 请参阅[安装 BizTalk 适配器包](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)。  
  
-   如果你想要对 SAP 系统使用 tRFC 调用[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，请确保 SQL Server 数据库中创建所需的表。 请参阅**创建 SQL Server 数据库对象**（本主题中）。
  
-   在运行时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装向导中，你可能会收到一个表明安装程序无法注册绑定的错误消息。 如果是这样，则手动注册它们。 请参阅**注册的适配器绑定**（本主题中）。  
  
-   如果你选择安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，请确保在 SAP 系统上安装了自定义的 Rfc。 请参阅[安装自定义的 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。

## <a name="more-good-info"></a>良好的详细信息
[更改或删除 BizTalk 适配器包](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)  
[BizTalk 适配器包常见问题解答](../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)