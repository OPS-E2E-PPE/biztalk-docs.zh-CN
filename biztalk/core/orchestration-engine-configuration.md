---
title: 业务流程引擎配置 |Microsoft 文档
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
ms.openlocfilehash: 3c5d2fae252d1b99f1a6393dc2f2ebbd45ed70a2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972675"
---
# <a name="orchestration-engine-configuration"></a>业务流程引擎配置
业务流程引擎使用名为 BTSNTSvc.exe.config 的 XML 文件来确定特定行为。 例如，冻结属性及其默认值在 BTSNTSvc.exe.config 文件中配置为 XML，并会在所有包含业务流程的主机实例启动时进行读取。 有关详细信息，请参阅[Orchestration 冻结和 Rehydration](../core/orchestration-dehydration-and-rehydration.md)。  
  
 服务会在启动时读取一次此配置信息。 除非停止并重新启动该服务，否则不会读取对配置的任何更改。  
  
 有关不同的节点和可能的值，请参阅以下示例。  
  
## <a name="example-all-validations-on"></a>示例：打开所有验证  
  
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
  
## <a name="example-assembly-validation-only"></a>示例：只验证程序集  
  
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
  
## <a name="example-remote-debugging-enabled"></a>示例：启用远程调试  
  
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
  
## <a name="example-appdomain-configuration"></a>示例：AppDomain 配置  
 程序集是使用赋值规则分配给命名域的（详见下面的内容）。 如果没有为某个程序集指定规则，则会将该程序集分配给一个特别域。 为每个特别域分配的这种程序集的数目由 AssembliesPerDomain 的值来确定。  
  
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
  
## <a name="modifying-other-sections-of-the-btsntsvcexeconfig-file"></a>修改 BTSNTSvc.exe.config 文件的其他部分  
 有关修改 BTSNTSvc.exe.config 中的冻结值的信息，请参阅[冻结默认属性](../core/dehydration-default-properties.md)。  
  
 BTSNTSvc.exe 配置文件包含若干个其他部分，.NET Framework 常规参考中记载了这些部分。 有关修改这些部分的详细信息请参阅**配置文件架构**的在.NET Framework 常规参考[http://go.microsoft.com/FWLink/?LinkID=52964](http://go.microsoft.com/FWLink/?LinkID=52964)。  
  
 除了特定于 BizTalk 的配置信息，该 BTSNTSvc.exe.config 文件也是在业务流程、 适配器或管道的上下文中运行.NET 应用程序组件从何处获取它们在运行的时使用的配置信息标准.NET **\<appSettings\>** 标记下**\<配置\>** 标记。 因为 BizTalk 已经提供了用于自定义适配器和管道组件来获取配置信息的机制**\<appSettings\>** BTSNTSvc.exe.config 文件中的标记通常将适用于从内部业务流程调用的自定义.NET 组件。 例如：  
  
```  
<appSettings>  
     <add key="configParamName" value="configParamValue" />  
</appSettings>  
```  
  
## <a name="throttling-messages-per-orchestration"></a>基于业务流程阻止消息  
 此属性在 btsntsvc.exe.config 文件中指定，它通过限制业务流程可具有的未处理消息的数目，防止业务流程占用过多的内存。 所有消息将都继续传送到 MessageBox;但是，排队的消息将传递到业务流程直到它处理某些其未完成的消息。  
  
 若要在 btsntsvc.exe.config 文件（位于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 根目录中）中指定此属性，请在“应用程序”节点下添加以下参数：  
  
```  
<configuration>  
            <application>  
                        <Throttling PauseAt="100" ResumeAt="50" />  
            </application>  
</configuration>  
```  
  
 在此示例中，一旦业务流程具有 100 个未处理消息后，MessageBox 就将停止发送更多的消息。 下 50 业务流程的邮件数时，它将指定 MessageBox 可以恢复发送消息。 您可以指定其他值。  
  
 你还必须启用此功能，每个主机，在数据库中。 若要为主机启用消息阻止，您必须在 BizTalkMsgBoxDb 数据库中编辑 dbo.Applications 表。 对于每个主机，你想要启用消息限制每个业务流程，设置 fAttributes 标志位为 1。 仅与设置为 1 fAttribute 这些主机将允许每个业务流程限制的消息。  
  
## <a name="see-also"></a>另请参阅  
 [调试业务流程](../core/debugging-orchestrations.md)   
 [XLANG-s 语言](../core/xlang-s-language.md)