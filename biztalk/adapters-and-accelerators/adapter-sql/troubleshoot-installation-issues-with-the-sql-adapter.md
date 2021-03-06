---
title: '使用 SQl 适配器进行故障排除安装问题: |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48778158-6064-4731-be72-1af855ebe373
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d21e3d8e2f6496560a749942f64636776ab5862
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367521"
---
# <a name="troubleshoot-installation-issues-with-the-sql-adapter"></a>使用 SQl 适配器进行故障排除安装问题：
> [!IMPORTANT]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]现作为的一部分[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]以及一个单独的适配器。 如果您正在访问此主题可了解有关安装问题[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]独立于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，对所有引用[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序必须解释为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。  

 安装 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]复制产品二进制文件的计算机上并注册每个适配器的绑定。 本部分讨论如何使用故障排除技术来解决安装错误。  

## <a name="logging-messages-for-setup-actions"></a>安装程序操作的日志记录消息  
 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]的安装程序进行安装的标准任务[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 此外，安装程序还执行某些自定义操作，例如注册适配器绑定。 你可以记录这两个的标准，以及自定义操作安装程序将执行的消息。  

- [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序将安装使用 MSI 的特定于适配器的文件。 因此，安装程序的日志记录是标准的 MSI 日志记录。  

- 安装程序执行的自定义操作的所有日志都位于 %temp%\adaptersetup.log。 如果跟踪日志文件失败，跟踪还提供了在事件日志。  

## <a name="known-issues"></a>已知问题  
 以下是在安装时可能会遇到的最常见错误[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，以及其可能的原因和解决方法。  



###  <a name="BKMK_SQLSetupBinding"></a> 安装程序无法注册适配器绑定  
 **问题**  

 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导无法注册适配器绑定，但将继续进行安装适配器。  

 **原因**  

 这可能会由于存在问题导致[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]安装，[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。 适配器绑定写入到 machine.config 文件中。  

 **解决方法**  

 您应手动注册[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定。  

##### <a name="to-register-the-adapter-binding"></a>若要注册适配器绑定  

1. 导航到计算机上的 machine.config 文件。 例如，在 32 位平台上，在 machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  

    在此路径中，\<版本\>是.NET Framework 的版本。  

2. 使用文本编辑器打开该文件。  

3. 若要注册[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定：  

   1. 搜索元素"的 system.serviceModel"并将其下的以下代码添加：  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. 搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。  

   3. 查找缺失[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定。 添加"bindingElementExtensions"节点下的以下部分。  

       有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. 搜索"bindingExtensions"system.serviceModel\extensions 下的元素。  

   5. 查找缺失[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定。 添加"bindingExtensions"节点下的以下部分。  

       有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  有关如何确定公用密钥和版本信息，请参阅[确定公用密钥和版本](#BKMK_PubKey)。  

4. 保存并关闭 machine.config 文件。  

####  <a name="BKMK_PubKey"></a> 确定公用密钥和版本  
 执行以下步骤来确定的公钥[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

###### <a name="to-determine-the-public-key"></a>若要确定的公钥  

1. 导航到 Windows 目录，通常 C:\WINDOWS\assembly。  

2. 右键单击的 DLL 为其也想公用密钥和版本，并选择**属性**。 下表列出了为 DLL 的名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  


   |                              适配器                              |    DLL 的名称     |
   |-------------------------------------------------------------------|------------------------|
   | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] | Microsoft.Adapters.Sql |


3. 上**常规**选项卡上，针对值**公钥标记**标签指定 DLL 的公共密钥。 同样，针对值**版本**标签指定 dll 的版本号。  

4. 复制公钥，，然后单击**取消**。  

###  <a name="BKMK_SQLConsumeBinding"></a> 在 64 位安装上使用使用适配器服务外接程序或添加适配器服务引用插件时出错  
 **问题**  

 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]运行的 64 位版本的 64 位计算机上[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]会导致以下错误：  

```  
No valid adapters are installed on this machine  
```  

 **原因**  

 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是 WCF 自定义绑定，后者在 machine.config 文件中的 System.ServiceModel 下注册。 64 位平台都有两个 machine.config 文件、 一个 32 位应用程序使用，另一个 64 位应用程序使用。 因此，当你安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 machine.config 文件的 64 位版本中注册绑定。 但是，[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]作为 32 位进程运行，因此启动[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，该插件检查 machine.config 文件的 32 位版本中的绑定并失败错误。  

 **解决方法**  

 安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]64 位上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。  

> [!IMPORTANT]
>  必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。 通过并行安装 32 位和 64 位的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。  

###  <a name="BKMK_SQLInvalidBinding"></a> 无效的绑定上的 64 位安装 BizTalk Server 管理控制台中配置 SQL 适配器端口时的错误  
 **问题**  

 当您尝试为中的适配器配置端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，则会收到以下错误：  

```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sqlBinding".  
Verify the binding extension is registered in machine.config."  
```  

 **原因**  

 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是 WCF 自定义绑定，后者在 machine.config 文件中的 System.ServiceModel 下注册。 64 位平台都有两个 machine.config 文件、 一个 32 位应用程序使用，另一个 64 位应用程序使用。 因此，当你安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 machine.config 文件的 64 位版本中注册绑定。 但是，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为 32 位进程运行管理控制台，因此在配置适配器的端口时，它会检查 32 位版本的 machine.config 文件中的绑定和失败错误。  

 **解决方法**  

 安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]64 位上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。  

> [!IMPORTANT]
>  必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。 通过并行安装 32 位和 64 位的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。  

## <a name="see-also"></a>请参阅  
 [SQL 适配器疑难解答](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)