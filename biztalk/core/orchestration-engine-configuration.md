---
title: 业务流程引擎配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration engine, examples
- orchestration engine, code sample
- orchestration engine, dehydration
- orchestration engine, configuring
ms.assetid: d4f253c3-317d-4b52-bf54-81d50f03eeb3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f45fbc1d4114fc6c20011a7b03670b0e874345f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262742"
---
# <a name="orchestration-engine-configuration"></a><span data-ttu-id="9f1fe-102">业务流程引擎配置</span><span class="sxs-lookup"><span data-stu-id="9f1fe-102">Orchestration Engine Configuration</span></span>
<span data-ttu-id="9f1fe-103">业务流程引擎使用名为 BTSNTSvc.exe.config 的 XML 文件来确定特定行为。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-103">The orchestration engine uses an XML file called BTSNTSvc.exe.config to determine certain behaviors.</span></span> <span data-ttu-id="9f1fe-104">例如，冻结属性及其默认值配置为在 BTSNTSvc.exe.config 文件中的 XML 并读取所有主机实例包含业务流程开始时。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-104">For example, dehydration properties and their default values are configured as XML in the BTSNTSvc.exe.config file and are read when all host instances containing an orchestration start.</span></span> <span data-ttu-id="9f1fe-105">有关详细信息，请参阅[业务流程冻结和解除冻结](../core/orchestration-dehydration-and-rehydration.md)。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-105">For more information, see [Orchestration Dehydration and Rehydration](../core/orchestration-dehydration-and-rehydration.md).</span></span>  
  
 <span data-ttu-id="9f1fe-106">服务在启动时读取一次，此配置信息。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-106">A service reads this configuration information once, when it is started.</span></span> <span data-ttu-id="9f1fe-107">对它的任何更改将不会选取除非停止并重新启动此服务。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-107">Any changes to it will not be picked up unless the service is stopped and restarted.</span></span>  
  
 <span data-ttu-id="9f1fe-108">请参阅下面的示例不同的节点和可能的值。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-108">See the examples below for different nodes and possible values.</span></span>  
  
## <a name="example-all-validations-on"></a><span data-ttu-id="9f1fe-109">示例： 打开所有验证</span><span class="sxs-lookup"><span data-stu-id="9f1fe-109">Example: all validations on</span></span>  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <configSections>  
              <section   
                     name="xlangs"  
                     type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess" />  
       </configSections>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
  
       <xlangs>  
              <Configuration>  
                     <Debugging   
                            ValidateAssemblies="true"  
                            ValidateSchemas="true"  
                            ValidateCorrelations="true"  
                            ExtendedLogging="true"  
                     />  
              </Configuration>  
       </xlangs>  
</configuration>  
```  
  
## <a name="example-assembly-validation-only"></a><span data-ttu-id="9f1fe-110">只验证示例： 程序集</span><span class="sxs-lookup"><span data-stu-id="9f1fe-110">Example: assembly validation only</span></span>  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <configSections>  
              <section   
                     name="xlangs"  
                     type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess"  
              />  
       </configSections>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
  
       <xlangs>  
              <Configuration>  
                     <Debugging   
                            ValidateAssemblies="true"  
                            ExtendedLogging="false"  
                     />  
              </Configuration>  
       </xlangs>  
</configuration>  
```  
  
## <a name="example-remote-debugging-enabled"></a><span data-ttu-id="9f1fe-111">示例： 启用进行远程调试</span><span class="sxs-lookup"><span data-stu-id="9f1fe-111">Example: remote debugging enabled</span></span>  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
  
       <system.runtime.remoting>  
              <customErrors mode="on"/>  
              <channelSinkProviders>  
                     <serverProviders>  
                            <provider id="sspi"  
                                    type="Microsoft.BizTalk.XLANGs.BTXEngine.SecurityServerChannelSinkProvider,Microsoft.XLANGs.BizTalk.Engine" securityPackage="negotiate" authenticationLevel="packetPrivacy" />  
                     </serverProviders>  
              </channelSinkProviders>  
  
              <application>  
                     <channels>  
                            <channel ref="tcp" port="0" name="">  
                                   <serverProviders>  
                                          <provider ref="sspi" />  
                                          <formatter ref="binary" typeFilterLevel="Full"/>  
                                   </serverProviders>  
                            </channel>  
                     </channels>  
              </application>  
       </system.runtime.remoting>  
</configuration>  
```  
  
## <a name="example-appdomain-configuration"></a><span data-ttu-id="9f1fe-112">例如：AppDomain 配置</span><span class="sxs-lookup"><span data-stu-id="9f1fe-112">Example: AppDomain configuration</span></span>  
 <span data-ttu-id="9f1fe-113">程序集分配给命名域使用赋值规则 （详见下文中）。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-113">Assemblies are assigned to named domains using assignment rules (see more below).</span></span> <span data-ttu-id="9f1fe-114">如果为某个程序集不指定任何规则，则该程序集将分配给一个特别域。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-114">If no rule is specified for some assembly, the assembly will be assigned to an ad hoc domain.</span></span> <span data-ttu-id="9f1fe-115">这样每个特别域分配的程序集的数目由 AssembliesPerDomain 的值确定。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-115">The number of such assigned assemblies per ad hoc domain is determined by the value of AssembliesPerDomain.</span></span>  
  
```  
<?xml version="1.0" ?>  
<configuration>  
    <configSections>  
        <section name="xlangs" type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess" />  
    </configSections>  
    <runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
            <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
        </assemblyBinding>  
    </runtime>  
    <xlangs>  
        <Configuration>  
            <!--   
                <!--   
AppDomain configuration.  
                Assemblies are assigned to named domains using assignment rules (see more below). If no rule is specified for some assembly, the assembly will be assigned to an ad hoc domain. The number of such assigned assemblies per ad hoc domain is determined by the value of AssembliesPerDomain.  
            -->-->   
            <AppDomains AssembliesPerDomain="10">  
                <!--   
                    <!--   
In this section the user may specify defualt configuration for any app domain created that does not have a named configuration associated with it (see AppDomainSpecs below)  
                    SecondsEmptyBeforeShutdown is the number of seconds that an app domain is empty (that is, it does not contain any orchestrations) before being unloaded. Specify -1 to signal that an app domain should never unload, even when empty.  
                    Similarly, SecondsIdleBeforeShutdown is the number of seconds that an app domain is idle (that is, it contains only dehydratable orchestrations) before being unloaded. Specify -1 to signal that an app domain should never unload when idle but not empty. When an idle but non-empty domain is shut down, all of the contained instances are dehydrated first.  
                -->  
                -->   
<DefaultSpec SecondsIdleBeforeShutdown="1200" SecondsEmptyBeforeShutdown="1800">  
                    <!--   
                        <!--   
BaseSetup is a serialized System.AppDomainSetup object. This is passed as-is to  
                        AppDomain.CreateAppDomain() and can be used to influence assembly search path etc.  
                    -->  
                    -->   
<BaseSetup>  
                        <ApplicationBase>c:\myAppBase</ApplicationBase>_0</ApplicationBase>   
                        <ConfigurationFile>c:\myAppBase\myConfig.config</ConfigurationFile>_0</ConfigurationFile>   
                    <DynamicBase>DynamicBase_0</DynamicBase>   
<DisallowPublisherPolicy>true</DisallowPublisherPolicy>   
<ApplicationName>ApplicationName_0</ApplicationName>   
<PrivateBinPath>PrivateBinPath_0</PrivateBinPath>   
<PrivateBinPathProbe>PrivateBinPathProbe_0</PrivateBinPathProbe>   
<ShadowCopyDirectories>ShadowCopyDirectories_0</ShadowCopyDirectories>   
<ShadowCopyFiles>ShadowCopyFiles_0</ShadowCopyFiles>   
<CachePath>CachePath_0</CachePath>   
<LicenseFile>LicenseFile_0</LicenseFile>   
<LoaderOptimization>NotSpecified</LoaderOptimization>   
</BaseSetup>  
                </DefaultSpec>  
                <!--   
                    - <!--   
In this section the user may specify named configurations for specific app domains, identified by their "friendly name". The format of any app-domain spec is identical to that of the default app-domain spec.  
                -->-->   
                <AppDomainSpecs>  
                    <AppDomainSpec Name="MyDomain1" SecondsIdleBeforeShutdown="-1" SecondsEmptyBeforeShutdown="12000">  
                        <BaseSetup>  
                            <PrivateBinPath>c:\PathForAppDomain1</PrivateBinPath>  
                        <PrivateBinPath>PrivateBinPath_0</PrivateBinPath>   
<PrivateBinPathProbe>PrivateBinPathProbe_0</PrivateBinPathProbe>   
</BaseSetup>  
                    </AppDomainSpec>  
                    <AppDomainSpec Name="MyFrequentlyUnloadingDomainMyTrashyDomain" SecondsIdleBeforeShutdown="60" SecondsEmptyBeforeShutdown="60" />   
                </AppDomainSpecs>  
                <!--   
                    <!--   
The PatternAssignmentRules and ExactAssignmentRules control assignment of assemblies to app domains.  
                    When a message arrives, the name of its corresponding orchestration's assembly is determined. Then, the assembly is assigned an app domain name. The rules guide this assignment. Exact rules are consulted first, in their order of definition, and then the pattern rules. The first match is used.  
                    If no match is found, the assembly will be assigned to an ad-hoc domain. The configuration and number of assemblies per ad-hoc domain is controlled by the AssembliesPerDomain attribute and the DefaultSpec section.  
                -->  
               -->   
- <ExactAssignmentRules>  
                    <!--   
                        <!--   
An exact assembly rule specifies a strong assembly name and an app domain name. If the strong assembly name equals the rule's assembly name, it is assigned to the corresponding app domain.  
                    -->-->   
                    <ExactAssignmentRule AssemblyName="BTSAssembly1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=9c7731c5584592ad"  
                       AssemblyName_0" AppDomainName="MyDomain1" />AppDomainName_1" />   
                    <ExactAssignmentRule AssemblyName="BTSAssembly2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=9c7731c5584592ad"AssemblyName_0" AppDomainName="AppDomainName_1" />   
                        AppDomainName="MyFrequentlyUnloadingDomain " />  
                <ExactAssignmentRule AssemblyName="AssemblyName_0" AppDomainName="AppDomainName_1" />   
</ExactAssignmentRules>  
                <PatternAssignmentRules>  
                    <!--   
                        <!--   
A pattern assignment rule specifies a regular expression and an app domain name. If the strong assembly name matches the expression, it is assigned to the corresponding app domain. This allows version independent assignment, assignment by public key token, or assignment by the custom assembly key.  
                    -->-->   
                    <!--  
                        assign all assemblies with name BTSAssembly3, regardless of version and public key,  
                        to the MyDomain1 app domain   
                    -->  
                    <PatternAssignmentRule AssemblyNamePattern=" BTSAssembly3, Version=\d.\d.\d.\d, Culture=neutral, PublicKeyToken=.{16}"AssemblyNamePattern_0" AppDomainName=" MyDomain1" />  
                <PatternAssignmentRule AssemblyNamePattern="AssemblyNamePattern_0" AppDomainName="AppDomainName_1" />   
<PatternAssignmentRule AssemblyNamePattern="AssemblyNamePattern_0" AppDomainName="AppDomainName_1" />   
</PatternAssignmentRules>  
            </AppDomains>  
        </Configuration>  
    </xlangs>  
</configuration>  
```  
  
## <a name="modifying-other-sections-of-the-btsntsvcexeconfig-file"></a><span data-ttu-id="9f1fe-116">修改 BTSNTSvc.exe.config 文件的其他部分</span><span class="sxs-lookup"><span data-stu-id="9f1fe-116">Modifying other sections of the BTSNTSvc.exe.config file</span></span>  
 <span data-ttu-id="9f1fe-117">有关修改 BTSNTSvc.exe.config 中的冻结值的信息，请参阅[冻结默认属性](../core/dehydration-default-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-117">For information about modifying the dehydration values in BTSNTSvc.exe.config, see [Dehydration Default Properties](../core/dehydration-default-properties.md).</span></span>  
  
 <span data-ttu-id="9f1fe-118">BTSNTSvc.exe 配置文件包含.NET Framework 常规参考中所述的多个其他部分。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-118">The BTSNTSvc.exe configuration file contains several other sections documented in the .NET Framework General Reference.</span></span> <span data-ttu-id="9f1fe-119">有关修改这些部分的详细信息请参阅**配置文件架构**的.NET Framework 常规参考[ http://go.microsoft.com/FWLink/?LinkID=52964 ](http://go.microsoft.com/FWLink/?LinkID=52964)。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-119">For more information about the modification of these sections see the **Configuration File Schema** of the .NET Framework General Reference at [http://go.microsoft.com/FWLink/?LinkID=52964](http://go.microsoft.com/FWLink/?LinkID=52964).</span></span>  
  
 <span data-ttu-id="9f1fe-120">除了特定于 BizTalk 的配置信息中，BTSNTSvc.exe.config 文件也是在业务流程、 适配器或管道的上下文中运行.NET 应用程序组件在何处获取它们在运行的时使用的配置信息标准.NET **\<appSettings\>** 标记下**\<configuration\>** 标记。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-120">In addition to BizTalk-specific configuration information, the BTSNTSvc.exe.config file is also where .NET application components which run in the context of an orchestration, adapter or pipeline obtain their configuration information at run time using the standard .NET **\<appSettings\>** tag under the **\<configuration\>** tag.</span></span> <span data-ttu-id="9f1fe-121">由于 BizTalk 已经提供了用于自定义适配器和管道组件来获取配置信息的机制**\<appSettings\>** 通常需要在 BTSNTSvc.exe.config 文件中的标记使用从业务流程中调用的自定义.NET 组件。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-121">Because BizTalk already provides a mechanism for custom adapters and pipeline components to obtain configuration information, the **\<appSettings\>** tag in the BTSNTSvc.exe.config file would typically be used by custom .NET components called from within an orchestration.</span></span> <span data-ttu-id="9f1fe-122">例如：</span><span class="sxs-lookup"><span data-stu-id="9f1fe-122">For example:</span></span>  
  
```  
<appSettings>  
     <add key="configParamName" value="configParamValue" />  
</appSettings>  
```  
  
## <a name="throttling-messages-per-orchestration"></a><span data-ttu-id="9f1fe-123">限制每个业务流程的消息</span><span class="sxs-lookup"><span data-stu-id="9f1fe-123">Throttling Messages Per Orchestration</span></span>  
 <span data-ttu-id="9f1fe-124">此属性中，btsntsvc.exe.config 文件中指定将阻止业务流程占用太多内存的限制可以具有的未处理消息的数量。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-124">This property, specified in the btsntsvc.exe.config file, will prevent an orchestration from consuming too much memory by limiting the number of outstanding messages it can have.</span></span> <span data-ttu-id="9f1fe-125">所有消息将都继续传送到 MessageBox;但是，排队的消息将传递到业务流程直到它处理某些其未处理的消息。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-125">All messages will continue to be delivered to the MessageBox; however, queued messages will not be delivered to the orchestration until it processes some of its outstanding messages.</span></span>  
  
 <span data-ttu-id="9f1fe-126">若要在 btsntsvc.exe.config 文件中指定此属性 (位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]根目录)，添加应用程序节点下的以下参数：</span><span class="sxs-lookup"><span data-stu-id="9f1fe-126">To specify this property in the btsntsvc.exe.config file (located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] root directory), add the following parameter under Application node:</span></span>  
  
```  
<configuration>  
            <application>  
                        <Throttling PauseAt="100" ResumeAt="50" />  
            </application>  
</configuration>  
```  
  
 <span data-ttu-id="9f1fe-127">在此示例中，一旦业务流程具有 100 个未完成的消息，MessageBox 将停止的发送其他消息。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-127">In this example, once an orchestration has 100 outstanding messages, the MessageBox will stop sending additional messages.</span></span> <span data-ttu-id="9f1fe-128">未处理消息的业务流程的数量下降到 50 时，它将指定 MessageBox 可以继续发送消息。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-128">When the orchestration's number of outstanding messages is down to 50, it will specify the MessageBox can resume sending messages.</span></span> <span data-ttu-id="9f1fe-129">可以指定其他值。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-129">You can specify other values.</span></span>  
  
 <span data-ttu-id="9f1fe-130">您还必须启用此功能，每个主机，在数据库中。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-130">You must also enable this feature, per-host, in the database.</span></span> <span data-ttu-id="9f1fe-131">若要启用消息阻止的主机，必须编辑 dbo。应用程序在 BizTalkMsgBoxDb 数据库中的表。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-131">To enable message throttling for a host, you must edit the dbo.Applications table in the BizTalkMsgBoxDb database.</span></span> <span data-ttu-id="9f1fe-132">对于每个你想要启用消息阻止每个业务流程的主机，设置 fAttributes 标志位为 1。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-132">For each host you want to enable message throttling per orchestration, set the fAttributes flag bit to 1.</span></span> <span data-ttu-id="9f1fe-133">只有 fattribute 设置为 1 的那些主机将允许限制每个业务流程的消息。</span><span class="sxs-lookup"><span data-stu-id="9f1fe-133">Only those hosts with the fAttribute set to 1 will allow message throttling per orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f1fe-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f1fe-134">See Also</span></span>  
 <span data-ttu-id="9f1fe-135">[调试业务流程](../core/debugging-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="9f1fe-135">[Debugging Orchestrations](../core/debugging-orchestrations.md) </span></span>  
 [<span data-ttu-id="9f1fe-136">XLANG-s 语言</span><span class="sxs-lookup"><span data-stu-id="9f1fe-136">XLANG-s Language</span></span>](../core/xlang-s-language.md)