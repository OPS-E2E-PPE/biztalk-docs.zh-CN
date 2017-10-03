---
title: "解决安装问题与 Oracle E-business Suite 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09b3af20-ab87-44e8-8ded-c19432552be7
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 387ca48954fc075e696a8d3b093fbc9f1b5d7259
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter"></a>与 Oracle E-business Suite 适配器解决安装问题
安装 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]复制产品二进制文件的计算机上并注册每个适配器的绑定。 本部分讨论如何使用故障排除方法来解决安装错误。  
  
## <a name="logging-messages-for-setup-actions"></a>安装程序操作的日志记录消息  
 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序执行安装的标准任务[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 此外，安装程序还执行某些自定义操作，例如注册的适配器绑定。 可以记录这两个标准以及自定义操作的安装程序将执行的消息。  
  
-   [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序将安装使用 MSI 的适配器特定的文件。 因此，安装程序的日志记录是标准的 MSI 日志记录。 [Windows 安装程序日志记录](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx)提供更多详细信息。 
  
-   安装程序执行的自定义操作的所有日志都位于 %temp%\adaptersetup.log。 如果跟踪日志文件失败，跟踪也会出现在事件日志。  
  
## <a name="known-issues"></a>已知问题  
 以下是在安装时可能遇到的最常见错误[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，以及其可能的原因和解决方法。  
  
  
  
###  <a name="BKMK_OraAppBinding"></a>安装程序无法注册适配器绑定  
 **问题**  
  
 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导无法注册的适配器绑定，但将继续执行适配器安装。  
  
 **可能的原因**  
  
 这可能会由于存在问题导致[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]安装，[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。 适配器绑定写入到 machine.config 文件中。  
  
 **解决方法**  
  
 你应该手动注册[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定。  
  
##### <a name="to-register-the-adapter-binding"></a>若要注册的适配器绑定  
  
1.  导航到计算机上的 machine.config 文件。 例如，在 32 位平台上，machine.config 位于下\<系统驱动器 >: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  
  
     在此路径中， \<*版本*> 是.NET Framework 的版本。  
  
2.  通过使用文本编辑器中打开该文件。  
  
3.  若要注册[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定：  
  
    1.  搜索的元素"的 system.serviceModel"和其下添加以下：  
  
        ```  
        <client>  
          <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleebs" />  
        </client>  
        ```  
  
    2.  搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。  
  
    3.  查找缺失[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定。 添加以下节"bindingElementExtensions"节点下。  
  
         有关[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，添加：  
  
        ```  
        <add name="oracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  搜索"bindingExtensions"system.serviceModel\extensions 下的元素。  
  
    5.  查找缺失[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定。 添加以下节"bindingExtensions"节点下。  
  
         有关[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，添加：  
  
        ```  
        <add name="oracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  有关如何确定公用密钥和版本的信息，请参阅[确定的公钥和版本](#BKMK_PubKey)。  
  
4.  保存并关闭 machine.config 文件。  
  
####  <a name="BKMK_PubKey"></a>确定的公钥和版本  
 执行以下步骤来确定的公钥[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
###### <a name="to-determine-the-public-key"></a>若要确定的公钥  
  
1.  导航到 Windows 目录中，通常 C:\WINDOWS\assembly。  
  
2.  右键单击对其需的公钥和版本，且然后选择该 DLL**属性**。 下表列出的 DLL 的名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
    |适配器|DLL 的名称|  
    |-------------|---------------------|  
    |[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]|Microsoft.Adapters.OracleEBS|  
  
3.  上**常规**选项卡上，针对值**Public Key Token**标签指定 DLL 的公共密钥。 同样，针对值**版本**标签指定的 dll 的版本号。  
  
4.  复制公钥，，然后单击**取消**。  
  
###  <a name="BKMK_ConsumeOraApp"></a>在 64 位安装上使用使用适配器服务外接程序或添加适配器服务引用插件时出错  
 **问题**  
  
 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]运行的 64 位版本的 64 位计算机上[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]会导致以下错误：  
  
```  
No valid adapters are installed on this machine  
```  
  
 **可能的原因**  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是 WCF 自定义绑定，它在 machine.config 文件中的 System.ServiceModel 下注册。 64 位平台都有两个 machine.config 文件，其中一个 32 位应用程序使用，另一个 64 位应用程序使用。 因此，在安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 64 位版本的 machine.config 文件中注册绑定。 但是，[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]作为 32 位进程运行，因此启动[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，插件检查 machine.config 文件的 32 位版本中的绑定和失败为错误。  
  
 **解决方法**  
  
-   安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]在 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。  
  
    > [!IMPORTANT]
    >  你必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。 通过并行安装 32 位和 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。  
  
-   安装修补程序集 11.1.0.7 的 Oracle 客户端 11.1.0.6 Oracle 数据访问组件的 32 位和 64 位版本。  
  
    > [!NOTE]
    >  若要确保你的应用程序与 ODP.NET 的最新版本，你必须具有"策略 Dll"在计算机上安装并在 GAC 中注册。 有关详细信息，请参阅"Oracle 数据提供程序的.NET 常见问题"在[http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834)。  
  
###  <a name="BKMK_OraAppInvalidBinding"></a>在 BizTalk Server 管理控制台中配置 Oracle E-business Suite 适配器的端口，在 64 位安装上时的无效的绑定错误  
 **问题**  
  
 当你尝试配置中的适配器的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你将收到以下错误：  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "oracleEBSBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 **可能的原因**  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是 WCF 自定义绑定，它在 machine.config 文件中的 System.ServiceModel 下注册。 64 位平台都有两个 machine.config 文件，其中一个 32 位应用程序使用，另一个 64 位应用程序使用。 因此，在安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 64 位版本的 machine.config 文件中注册绑定。 但是，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为 32 位进程运行的管理控制台，因此当你配置为适配器的端口时，它检查 machine.config 文件的 32 位版本中的绑定无法提供错误。  
  
 **解决方法**  
  
-   安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]在 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。  
  
    > [!IMPORTANT]
    >  你必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。 通过并行安装 32 位和 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。  
  
-   安装修补程序集 11.1.0.7 的 Oracle 客户端 11.1.0.6 Oracle 数据访问组件的 32 位和 64 位版本。  
  
    > [!NOTE]
    >  若要确保你的应用程序与 ODP.NET 的最新版本，你必须具有"策略 Dll"在计算机上安装并在 GAC 中注册。 有关详细信息，请参阅"Oracle 数据提供程序的.NET 常见问题"在[http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834)。  
  
## <a name="see-also"></a>另请参阅  
[故障排除 Oracle EBS 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)