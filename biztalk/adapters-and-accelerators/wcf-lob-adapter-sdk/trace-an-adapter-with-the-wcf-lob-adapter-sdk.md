---
title: 跟踪适配器使用 WCF LOB 适配器 SDK |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a4f4758-3e3e-48c4-b4cf-414c2b05d539
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b03e56127071215a33b81f1d16ad653a9764d1d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363172"
---
# <a name="trace-an-adapter-with-the-wcf-lob-adapter-sdk"></a>跟踪使用 WCF LOB 适配器 SDK 的适配器
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 跟踪是基于 Systems.Diagnostics。 使用 Microsoft.ServiceModel.Channels 跟踪源[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时。  使用 Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse 跟踪源[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 WCF 跟踪将写入到名为 System.ServiceModel 的源。  
  
 适配器开发人员可以提供使用 Microsoft.ServiceModel.Channels.Common.AdapterTrace 类的适配器的跟踪源名称。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]生成适配器开发人员可用于提供适配器代码中的检测的跟踪包装器类。  
  
 有关 WCF 跟踪的信息，请参阅[跟踪](https://msdn.microsoft.com/library/ms730342.aspx)。
  
 有关分析 WCF 中的跟踪信息，请参阅[Service Trace Viewer Tool (SvcTraceViewer.exe)](https://msdn.microsoft.com/library/ms732023.aspx)。 
  
## <a name="sample-trace-wrapper-utility-class"></a>示例跟踪包装器实用程序类  
  
```  
public class EchoAdapterUtilities  
{  
    static AdapterTrace trace = new AdapterTrace("Microsoft.Adapters.Samples.Echo.EchoAdapter");  
  
    /// <summary>  
    /// Gets the AdapterTrace  
    /// </summary>  
    public static AdapterTrace Trace  
    {  
        get  
        {  
            return trace;  
        }  
    }  
}  
```  
  
 以前的实用工具类然后可由适配器开发人员在适配器代码供适配器使用者提供检测数据。  
  
 EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully opened!");  
  
## <a name="enable-tracing-for-the-adapter-and-wcf-lob-adapter-sdk-runtime"></a>对适配器和 WCF LOB 适配器 SDK 运行时启用跟踪  
 可以启用跟踪中提供[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过使用适配器的应用程序的 app.config 文件中添加以下部分。  
  
```  
<system.diagnostics>  
  <sources>  
    <source name="Microsoft.Adapters.Samples.Echo.EchoAdapter" switchValue="Verbose">  
      <listeners>  
        <add name="xmlTrace" />  
      </listeners>  
    </source>  
    <source name="Microsoft.ServiceModel.Channels" switchValue="Verbose">  
      <listeners>  
        <add name="xmlTrace" />  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add initializeData="C:\logs\TestEchoAdapter_Browse.svclog" type="System.Diagnostics.XmlWriterTraceListener" name="xmlTrace">  
      <filter type="" />  
    </add>  
  </sharedListeners>  
  <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 添加元素可用于指定的名称和你想要使用的跟踪侦听器的类型。 在示例配置中，我们将侦听器命名为"xmlTrace"，并添加了标准.NET Framework 跟踪侦听器 (System.Diagnostics.XmlWriterTraceListener) 为我们想要使用的类型。 可以添加任意数量的每个源的跟踪侦听器。 例如，在以下示例中，我们还添加了名为"textTrace"使用.NET Framework 跟踪侦听器 System.Diagnostics.TextWriterTraceListener 的另一个侦听器。 如果跟踪侦听器发出的跟踪文件，您必须在配置文件中指定的输出文件的位置和名称。 这可通过该侦听器将 initializeData 设置为的文件的名称。  
  
## <a name="enabling-tracing-for-the-add-adapter-service-reference-plug-in"></a>为启用跟踪添加适配器服务引用插件  
 可以启用跟踪，此插件通过 devenv.exe.config 文件中添加以下部分位于`\Program Files (x86)\Microsoft Visual Studio\Common7\IDE`。
  
```  
<system.diagnostics>  
   <sources>  
    <source name="Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse" switchValue="Verbose, ActivityTracing">  
      <listeners>  
        <add name="textTrace"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add initializeData="C:\logs\aasr.svclog" type="System.Diagnostics.XmlWriterTraceListener" name="xmlTrace">  
      <filter type="" />  
    </add>  
    <add initializeData="C:\logs\aasr.log" type="System.Diagnostics.TextWriterTraceListener" name="textTrace">  
      <filter type="" />  
    </add>  
  </sharedListeners>  
  <trace autoflush="true" indentsize="4" />  
</system.diagnostics>  
```  
  
## <a name="enable-tracing-for-the-consume-adapter-service-add-in"></a>启用对跟踪使用适配器服务外接程序  
 您可以通过添加以下部分中的 BTSNTSVC.exe.config 文件中启用对该外接程序的跟踪`\Program Files (x86)\Microsoft BizTalk Server`。  
  
```  
<system.diagnostics>  
   <sources>  
    <source name="Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse" switchValue="Verbose, ActivityTracing">  
      <listeners>  
        <add name="textTrace"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add initializeData="C:\logs\aasr.svclog" type="System.Diagnostics.XmlWriterTraceListener" name="xmlTrace">  
      <filter type="" />  
    </add>  
    <add initializeData="C:\logs\aasr.log" type="System.Diagnostics.TextWriterTraceListener" name="textTrace">  
      <filter type="" />  
    </add>  
  </sharedListeners>  
  <trace autoflush="true" indentsize="4" />  
</system.diagnostics>  
```  
  
## <a name="see-also"></a>请参阅  
 [使用 WCF LOB 适配器 SDK 创建的适配器疑难解答](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)