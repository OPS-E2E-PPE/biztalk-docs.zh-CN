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
# <a name="trace-an-adapter-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="4bd82-102">跟踪使用 WCF LOB 适配器 SDK 的适配器</span><span class="sxs-lookup"><span data-stu-id="4bd82-102">Trace an adapter with the WCF LOB Adapter SDK</span></span>
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] <span data-ttu-id="4bd82-103">跟踪是基于 Systems.Diagnostics。</span><span class="sxs-lookup"><span data-stu-id="4bd82-103">tracing is built on top of Systems.Diagnostics.</span></span> <span data-ttu-id="4bd82-104">使用 Microsoft.ServiceModel.Channels 跟踪源[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时。</span><span class="sxs-lookup"><span data-stu-id="4bd82-104">You use Microsoft.ServiceModel.Channels trace source for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] runtime.</span></span>  <span data-ttu-id="4bd82-105">使用 Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse 跟踪源[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4bd82-105">You use Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse trace source for [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="4bd82-106">WCF 跟踪将写入到名为 System.ServiceModel 的源。</span><span class="sxs-lookup"><span data-stu-id="4bd82-106">WCF traces are written to the source named System.ServiceModel.</span></span>  
  
 <span data-ttu-id="4bd82-107">适配器开发人员可以提供使用 Microsoft.ServiceModel.Channels.Common.AdapterTrace 类的适配器的跟踪源名称。</span><span class="sxs-lookup"><span data-stu-id="4bd82-107">The adapter developer can provide a trace source name for the adapter using Microsoft.ServiceModel.Channels.Common.AdapterTrace class.</span></span> <span data-ttu-id="4bd82-108">[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]生成适配器开发人员可用于提供适配器代码中的检测的跟踪包装器类。</span><span class="sxs-lookup"><span data-stu-id="4bd82-108">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] generates a trace wrapper class that can be used by the adapter developer to provide instrumentation in the adapter code.</span></span>  
  
 <span data-ttu-id="4bd82-109">有关 WCF 跟踪的信息，请参阅[跟踪](https://msdn.microsoft.com/library/ms730342.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4bd82-109">For information about WCF tracing, see [Tracing](https://msdn.microsoft.com/library/ms730342.aspx).</span></span>
  
 <span data-ttu-id="4bd82-110">有关分析 WCF 中的跟踪信息，请参阅[Service Trace Viewer Tool (SvcTraceViewer.exe)](https://msdn.microsoft.com/library/ms732023.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4bd82-110">For information about analyzing traces in WCF, see [Service Trace Viewer Tool (SvcTraceViewer.exe)](https://msdn.microsoft.com/library/ms732023.aspx).</span></span> 
  
## <a name="sample-trace-wrapper-utility-class"></a><span data-ttu-id="4bd82-111">示例跟踪包装器实用程序类</span><span class="sxs-lookup"><span data-stu-id="4bd82-111">Sample Trace Wrapper Utility Class</span></span>  
  
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
  
 <span data-ttu-id="4bd82-112">以前的实用工具类然后可由适配器开发人员在适配器代码供适配器使用者提供检测数据。</span><span class="sxs-lookup"><span data-stu-id="4bd82-112">The previous utility class can then be used by the adapter developer throughout the adapter code to provide instrumentation data for the adapter consumers.</span></span>  
  
 <span data-ttu-id="4bd82-113">EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully opened!");</span><span class="sxs-lookup"><span data-stu-id="4bd82-113">EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully opened!");</span></span>  
  
## <a name="enable-tracing-for-the-adapter-and-wcf-lob-adapter-sdk-runtime"></a><span data-ttu-id="4bd82-114">对适配器和 WCF LOB 适配器 SDK 运行时启用跟踪</span><span class="sxs-lookup"><span data-stu-id="4bd82-114">Enable Tracing for the Adapter and WCF LOB Adapter SDK Runtime</span></span>  
 <span data-ttu-id="4bd82-115">可以启用跟踪中提供[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过使用适配器的应用程序的 app.config 文件中添加以下部分。</span><span class="sxs-lookup"><span data-stu-id="4bd82-115">You can enable tracing provided in the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] by adding the following section in the app.config file of the application using the adapter.</span></span>  
  
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
  
 <span data-ttu-id="4bd82-116">添加元素可用于指定的名称和你想要使用的跟踪侦听器的类型。</span><span class="sxs-lookup"><span data-stu-id="4bd82-116">You can use the add element to specify the name and type of the trace listener you want to use.</span></span> <span data-ttu-id="4bd82-117">在示例配置中，我们将侦听器命名为"xmlTrace"，并添加了标准.NET Framework 跟踪侦听器 (System.Diagnostics.XmlWriterTraceListener) 为我们想要使用的类型。</span><span class="sxs-lookup"><span data-stu-id="4bd82-117">In our example configuration, we named the Listener "xmlTrace" and added the standard .NET Framework trace listener (System.Diagnostics.XmlWriterTraceListener) as the type we want to use.</span></span> <span data-ttu-id="4bd82-118">可以添加任意数量的每个源的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="4bd82-118">You can add any number of trace listeners for each source.</span></span> <span data-ttu-id="4bd82-119">例如，在以下示例中，我们还添加了名为"textTrace"使用.NET Framework 跟踪侦听器 System.Diagnostics.TextWriterTraceListener 的另一个侦听器。</span><span class="sxs-lookup"><span data-stu-id="4bd82-119">For example, in the following examples, we also added another listener named "textTrace" that uses the .NET Framework trace listener System.Diagnostics.TextWriterTraceListener.</span></span> <span data-ttu-id="4bd82-120">如果跟踪侦听器发出的跟踪文件，您必须在配置文件中指定的输出文件的位置和名称。</span><span class="sxs-lookup"><span data-stu-id="4bd82-120">If the trace listener emits the trace to a file, you must specify the output file location and name in the configuration file.</span></span> <span data-ttu-id="4bd82-121">这可通过该侦听器将 initializeData 设置为的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4bd82-121">This is done by setting initializeData to the name of the file for that listener.</span></span>  
  
## <a name="enabling-tracing-for-the-add-adapter-service-reference-plug-in"></a><span data-ttu-id="4bd82-122">为启用跟踪添加适配器服务引用插件</span><span class="sxs-lookup"><span data-stu-id="4bd82-122">Enabling Tracing for the Add Adapter Service Reference Plug-in</span></span>  
 <span data-ttu-id="4bd82-123">可以启用跟踪，此插件通过 devenv.exe.config 文件中添加以下部分位于`\Program Files (x86)\Microsoft Visual Studio\Common7\IDE`。</span><span class="sxs-lookup"><span data-stu-id="4bd82-123">You can enable tracing for this plug-in by adding the following section in the devenv.exe.config file located in `\Program Files (x86)\Microsoft Visual Studio\Common7\IDE`.</span></span>
  
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
  
## <a name="enable-tracing-for-the-consume-adapter-service-add-in"></a><span data-ttu-id="4bd82-124">启用对跟踪使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="4bd82-124">Enable Tracing for the Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="4bd82-125">您可以通过添加以下部分中的 BTSNTSVC.exe.config 文件中启用对该外接程序的跟踪`\Program Files (x86)\Microsoft BizTalk Server`。</span><span class="sxs-lookup"><span data-stu-id="4bd82-125">You can enable tracing for this add-in by adding the following section in the BTSNTSVC.exe.config file located in `\Program Files (x86)\Microsoft BizTalk Server`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4bd82-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="4bd82-126">See Also</span></span>  
 [<span data-ttu-id="4bd82-127">使用 WCF LOB 适配器 SDK 创建的适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="4bd82-127">Troubleshoot adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)