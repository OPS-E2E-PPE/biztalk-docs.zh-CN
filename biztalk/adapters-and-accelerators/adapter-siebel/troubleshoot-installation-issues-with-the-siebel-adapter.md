---
title: 解决安装问题与 Siebel 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, installation
- installation, troubleshooting
ms.assetid: f9f066d9-37b6-4a18-9f60-d0931ea91a18
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff49285df7e43103f2ad7441cbc82b96bb59eaa4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964867"
---
# <a name="troubleshoot-installation-issues-with-the-siebel-adapter"></a>与 Siebel 适配器解决安装问题
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装将复制产品二进制文件的计算机上并注册每个适配器的绑定。 本部分讨论故障排除方法来解决安装错误。  
  
## <a name="setup-logging"></a>安装程序日志记录  
 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序执行安装的标准任务[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 此外，安装程序还执行某些自定义操作，例如注册的适配器绑定。 可以记录有关安装程序执行的这两个标准以及自定义操作的消息。  
  
-   [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序将安装使用 MSI 的适配器特定文件。 因此，安装程序的日志记录将是标准的 MSI 日志记录。  
  
-   执行安装程序的自定义操作的日志位于 %temp%\adaptersetup.log。 如果跟踪日志文件失败，跟踪也会出现在事件日志。  
  
## <a name="known-issues"></a>已知问题  
  
### <a name="setup-fails-to-register-adapter-bindings"></a>安装程序无法注册适配器绑定  
 **问题**  
  
 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导无法注册[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定或[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，但与适配器安装继续进行。  
  
 **可能的原因**  
  
 这可能会由于使用 WCF 安装时，问题而导致[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]安装或被损坏 machine.config。 适配器绑定写入到 machine.config 文件中。  
  
 **解决方法**  
  
手动注册[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定和[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用以下步骤： 
  
1.  导航到计算机上的 machine.config 文件。 例如，在 32 位平台上，machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  
  
     在此路径中，\<版本\>是.NET Framework 的版本。  
  
2.  打开使用文本编辑器的文件。  
  
3.  若要注册[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定：  
  
    1.  搜索的元素"的 system.serviceModel"和其下添加以下：  
  
        ```  
        <client>  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        </client>  
        ```  
  
    2.  搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。  
  
    3.  查找缺失[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定。 添加以下节"bindingElementExtensions"节点下。  
  
         有关[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，添加：  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  搜索"bindingExtensions"system.serviceModel\extensions 下的元素。  
  
    5.  查找缺失[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定。 添加"bindingExtensions"节点下的以下部分。  
  
         有关[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，添加：  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
        > [!NOTE]
        >  有关如何确定的公钥的信息，请参阅[确定的公钥和版本](#BKMK_PubKey)。  
  
4.  若要注册[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]:  
  
    1.  元素 DbProviderFactories system.data 节点下搜索。  
  
    2.  查找缺失[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。 添加以下节 DbProviderFactories 节点下。  
  
         有关[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，添加：  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  保存并关闭 machine.config 文件。  
  
####  <a name="BKMK_PubKey"></a>确定的公钥和版本  
 执行以下步骤来确定的公钥[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]或[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。  
  
###### <a name="to-determine-the-public-key"></a>若要确定的公钥  
  
1.  导航到 Windows 目录中，通常 C:\WINDOWS\assembly。  
  
2.  右键单击的 DLL 键并选择希望公共**属性**。 下表列出的每个适配器和提供程序 Dll 的名称。  
  
    |适配器/ADO 提供程序|DLL 的名称|  
    |---------------------------|---------------------|  
    |[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]|Microsoft.Adapters.Siebel|  
    |[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]|Microsoft.Data.SiebelClient|  
  
3.  上**常规**选项卡上，针对值**Public Key Token**标签指定 DLL 的公共密钥。 同样，针对值**版本**标签指定的 dll 的版本号。  
  
4.  复制公钥，，然后单击**取消**。  
  
## <a name="see-also"></a>另请参阅  
[解决在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)