---
title: '使用 SAP 适配器进行故障排除安装问题: |Microsoft Docs'
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
ms.assetid: fdfdaf44-c32d-43a5-998d-02032c0b9211
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5b331d391229938093953dd6a6bcd65f8178265
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372485"
---
# <a name="troubleshoot-installation-issues-with-the-sap-adapter"></a>使用 SAP 适配器进行故障排除安装问题：
安装 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]复制产品二进制文件的计算机上并注册每个适配器的绑定。 本部分讨论故障排除技术来解决安装错误。  

## <a name="logging-messages-for-setup-actions"></a>安装程序操作的日志记录消息  
 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]的安装程序进行安装的标准任务[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 此外，安装程序还执行某些自定义操作，例如注册适配器绑定。 你可以记录这两个的标准，以及自定义操作安装程序将执行的消息。  

- [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序将安装使用 MSI 的适配器特定文件。 因此，安装程序的日志记录是标准的 MSI 日志记录。  

- 安装程序执行的自定义操作的日志位于 %temp%\adaptersetup.log。 如果跟踪日志文件失败，跟踪还提供了在事件日志。  

##  <a name="BKMK_SAPSetupBinding"></a> 安装程序无法注册适配器绑定或数据访问接口  
 **问题**  

 在 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导无法注册适配器绑定或[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]，但将继续进行安装适配器。  

 **原因**  

 这可能会由于存在问题导致[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]安装，[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。 适配器绑定写入到 machine.config 文件中。  

 **解决方法**  

 您应手动注册[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定或[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  

### <a name="register-the-adapter-bindings-or-the-data-provider"></a>注册适配器绑定或数据提供程序  

1. 导航到计算机上的 machine.config 文件。 例如，在 32 位平台上，在 machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  

    在此路径中，\<版本\>是.NET Framework 的版本。  

2. 打开文件使用文本编辑器。  

3. 若要注册[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定：  

   1. 搜索元素"的 system.serviceModel"并将其下的以下代码添加：  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
      </client>  
      ```  

   2. 搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。  

   3. 查找缺失[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定。 添加"bindingElementExtensions"节点下的以下部分。  

       有关[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，添加：  

      ```  
      <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. 搜索"bindingExtensions"system.serviceModel\extensions 下的元素。  

   5. 查找缺失[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定。 添加"bindingExtensions"节点下的以下部分。  

       有关[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，添加：  

      ```  
      <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

      > [!NOTE]
      >  有关如何确定的公钥的信息，请参阅[确定公用密钥和版本](#BKMK_PubKey)。  

4. 若要注册[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:  

   1. 搜索"system.data"节点下的元素"DbProviderFactories"。  

   2. 查找缺失[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。 添加"DbProviderFactories"节点下的以下部分。  

       有关[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，添加：  

      ```  
      <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient" description=".NET Framework Data Provider for mySAP Business Suite" type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

5. 保存并关闭 machine.config 文件。  

###  <a name="BKMK_PubKey"></a> 确定公用密钥和版本  
 执行以下步骤来确定的公钥[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]或[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  

1. 导航到 Windows 目录，通常 C:\WINDOWS\assembly。  

2. 右键单击的 DLL 为其也希望将公钥，并选择**属性**。 下表列出了为 Dll 的名称[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  


   |                           适配器/数据访问接口                           |     DLL 的名称      |
   |---------------------------------------------------------------------------|--------------------------|
   |    [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]    |  Microsoft.Adapters.SAP  |
   | [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] | Microsoft.Data.SAPClient |


3. 上**常规**选项卡上，针对值**公钥标记**标签指定 DLL 的公共密钥。 同样，针对值**版本**标签指定 dll 的版本号。  

4. 复制公钥，，然后单击**取消**。  

##  <a name="BKMK_SAPConsumeBinding"></a> 任何有效的适配器不，已安装的错误

 **问题**  

 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]运行的 64 位版本的 64 位计算机上[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]会导致以下错误：  

```  
No valid adapters are installed on this machine  
```  

 **原因**  

 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是 WCF 自定义绑定，后者在 machine.config 文件中的 System.ServiceModel 下注册。 64 位平台都有两个 machine.config 文件、 一个 32 位应用程序使用，另一个 64 位应用程序使用。 因此，当你安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 machine.config 文件的 64 位版本中注册绑定。 但是，[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]作为 32 位进程运行，因此启动[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，该插件检查 machine.config 文件的 32 位版本中的绑定并失败错误。  

 **解决方法**  

- 安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]64 位上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。  

  > [!IMPORTANT]
  >  必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。 通过并行安装 32 位和 64 位的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。  

- 添加的客户端 Dll 的 32 位和 64 位版本[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]（如 librfc32u.dll) 到 PATH 变量。 32 位版本的 Dll 必须添加到 C:\Windows\SysWow64 文件夹。 Dll 的 64 位版本必须添加到 C:\Windows\System32 文件夹中。  

  > [!IMPORTANT]
  >  如果在具有 64 位操作系统的计算机上运行的适配器 （32 位或 64 位），并且使用适配器来编写应用程序，应将标记作为适配器的相同类型 （32 位或 64 位） 到应用程序。 此外，RFC SDK （32 位或 64 位） 的版本必须与适配器 （32 位或 64 位） 的版本相同。  
  >   
  >  例如，如果使用 64 位操作系统的计算机上运行 32 位适配器，适配器客户端应用程序必须标记为 32 位。  

   有关 SAP 客户端 Dll 的详细信息，请参阅[适用于 SAP 数据提供程序安装自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。  

##  <a name="BKMK_SAPInvalidBinding"></a> 配置 SAP 适配器的端口时无效的绑定错误  
 **问题**  

 当您尝试为中的适配器配置端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，则会收到以下错误：  

```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sapBinding".  
Verify the binding extension is registered in machine.config."  
```  

 **原因**  

 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是 WCF 自定义绑定，后者在 machine.config 文件中的 System.ServiceModel 下注册。 64 位平台都有两个 machine.config 文件、 一个 32 位应用程序使用，另一个 64 位应用程序使用。 因此，当你安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 machine.config 文件的 64 位版本中注册绑定。 但是，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为 32 位进程运行管理控制台，因此在配置适配器的端口时，它会检查 32 位版本的 machine.config 文件中的绑定和失败错误。  

 **解决方法**  

- 安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]64 位上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。  

  > [!IMPORTANT]
  >  必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。 通过并行安装 32 位和 64 位的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。  

- 添加的客户端 Dll 的 32 位和 64 位版本[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]（如 librfc32u.dll) 到 PATH 变量。 32 位版本的 Dll 必须添加到 C:\Windows\SysWow64 文件夹。 Dll 的 64 位版本必须添加到 C:\Windows\System32 文件夹中。  

  > [!IMPORTANT]
  >  如果在具有 64 位操作系统的计算机上运行的适配器 （32 位或 64 位），并且使用适配器来编写应用程序，应将标记作为适配器的相同类型 （32 位或 64 位） 到应用程序。 此外，RFC SDK （32 位或 64 位） 的版本必须与适配器 （32 位或 64 位） 的版本相同。  
  >   
  >  例如，如果使用 64 位操作系统的计算机上运行 32 位适配器，适配器客户端应用程序必须标记为 32 位。  

   有关 SAP 客户端 Dll 的详细信息，请参阅[适用于 SAP 数据提供程序安装自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。

## <a name="see-also"></a>请参阅  
[SAP 适配器疑难解答](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)