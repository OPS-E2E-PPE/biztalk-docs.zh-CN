---
title: 跟踪使用 WCF LOB 适配器 SDK 的适配器 |Microsoft 文档
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
ms.openlocfilehash: 8ca4b68f23f791de3ecd68bc69b85c2908b6d7a0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965355"
---
# <a name="trace-an-adapter-with-the-wcf-lob-adapter-sdk"></a>跟踪使用 WCF LOB 适配器 SDK 的适配器
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]跟踪是 Systems.Diagnostics 基础生成的。 使用 Microsoft.ServiceModel.Channels 跟踪源[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时。  使用 Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse 跟踪源[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 WCF 跟踪将写入到名为 System.ServiceModel 的源。  
  
 适配器开发人员可以提供使用 Microsoft.ServiceModel.Channels.Common.AdapterTrace 类的适配器的跟踪源名称。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]生成适配器开发人员可以用于提供适配器代码中的检测的跟踪包装类。  
  
 有关 WCF 跟踪的信息，请参阅[跟踪](https://msdn.microsoft.com/library/ms730342.aspx)。
  
 有关分析在 WCF 中的跟踪的信息，请参阅[服务跟踪查看器工具 (SvcTraceViewer.exe)](https://msdn.microsoft.com/library/ms732023.aspx)。 
  
## <a name="sample-trace-wrapper-utility-class"></a>示例跟踪包装实用程序类  
  
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
  
 以前的实用工具类随后可由适配器开发人员在整个适配器代码适配器使用者提供检测数据。  
  
 EchoAdapterUtilities.Trace.Trace (System.Diagnostics.TraceEventType.Information，"EchoAdapterConnection::Open"，"已成功打开连接 ！");  
  
## <a name="enable-tracing-for-the-adapter-and-wcf-lob-adapter-sdk-runtime"></a>适配器和 WCF LOB 适配器 SDK 运行时启用跟踪  
 你可以启用中提供的跟踪[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过在使用该适配器的应用程序的 app.config 文件中添加以下部分。  
  
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
  
 可以使用 add 元素来指定名称和你想要使用的跟踪侦听器的类型。 在示例配置中，我们将侦听器命名为"xmlTrace"，并为我们想要使用的类型添加标准的.NET Framework 跟踪侦听器 (System.Diagnostics.XmlWriterTraceListener)。 你可以添加任意数量的每个源的跟踪侦听器。 例如，在以下示例中，我们还添加名为"textTrace"使用.NET Framework 跟踪侦听器 System.Diagnostics.TextWriterTraceListener 的另一个侦听器。 如果跟踪侦听器发出的跟踪文件，你必须在配置文件中指定的输出文件的位置和名称。 这可通过该侦听器将 initializeData 设置为文件的名称。  
  
## <a name="enabling-tracing-for-the-add-adapter-service-reference-plug-in"></a>启用的跟踪添加插件的适配器服务引用  
 你可以启用跟踪，对于此插件通过在 devenv.exe.config 文件中添加以下部分位于`\Program Files (x86)\Microsoft Visual Studio\Common7\IDE`。
  
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
 可以启用跟踪时为此外接程序通过在位于 BTSNTSVC.exe.config 文件中添加以下部分`\Program Files (x86)\Microsoft BizTalk Server`。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [解决使用 WCF LOB 适配器 SDK 创建的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)