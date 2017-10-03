---
title: "配置业务流程的远程调试 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Microsoft.XLANGs.BizTalk.Client.dll.config, code sample
- BTSNTSvc.exe.config, code sample
- orchestrations, debugging
- building, debugging
- building, code sample
ms.assetid: 722efaec-d160-48dc-b94b-0733c9904d98
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4184b82efccd0ab2dcc2b871b6389b28148754c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-remote-debugging-for-orchestrations"></a>为业务流程配置远程调试
您可以完全配置客户端和服务器之间的远程调试。 Microsoft.XLANGs.BizTalk.Client.dll.config 中指定客户端配置。BTSNTSvc.exe.config 中指定的服务器配置。以下是每个的默认配置的列表。  
  
## <a name="client-microsoftxlangsbiztalkclientdllconfig"></a>客户端 (Microsoft.XLANGs.BizTalk.Client.dll.config)  
  
```  
<configuration>  
     <system.runtime.remoting>  
  
 <channelSinkProviders>  
       <clientProviders>  
         <provider id="sspi" type="Microsoft.BizTalk.XLANGs.Client.SecurityClientChannelSinkProvider,Microsoft.XLANGs.BizTalk.Client" securityPackage="negotiate" authenticationLevel="packetPrivacy"/>  
       </clientProviders>  
</channelSinkProviders>  
  
<application>  
<channels>  
    <channel ref="tcp" port="0" name="">  
       <clientProviders>  
             <formatter ref="binary"/>  
             <provider ref="sspi" />  
        </clientProviders>  
       <serverProviders>  
             <formatter ref="binary" typeFilterLevel="Full"/>  
       </serverProviders>  
    </channel>  
</channels>  
</application>  
  </system.runtime.remoting>  
</configuration>  
```  
  
## <a name="serverbtsntsvcexeconfig"></a>服务器 (BTSNTSvc.exe.config)  
  
```  
<?xml version="1.0" ?>  
<configuration>  
    <runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
            <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking;Tracking\interop" />  
        </assemblyBinding>  
    </runtime>  
  
    <system.runtime.remoting>  
  
        <channelSinkProviders>  
            <serverProviders>  
                <provider id="sspi" type="Microsoft.BizTalk.XLANGs.BTXEngine.SecurityServerChannelSinkProvider,Microsoft.XLANGs.BizTalk.Engine" securityPackage="ntlm" authenticationLevel="packetPrivacy" />  
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
  
## <a name="configurable-parameters"></a>可配置的参数  
 默认值将确保最高安全性的配置。 但是，用户可以更改这些默认值，并且这些文件处于 ACL 的控制下，因为它们处于程序文件文件夹中。  
  
 元素\<提供程序 / > 是可选的如果未提供将导致的通道不会相互进行身份验证使用自定义的接收器。 但是，这也是一个应该禁用的危险选项，因为它将开放通道。 如果看重性能并且安全攻击无关紧要，则可以设置此元素。  
  
 该通道元素可具有属性 rejectRemoteRequests = true，这将只启用本地调用并且拒绝远程请求。  
  
 中的 securityPackage 属性\<serverProviders / > 元素可以具有任何以下值：  
  
-   negotiate  
  
-   ntlm  
  
-   Kerberos  
  
 中的 authenticationLevel 属性\<serverProviders / > 元素可以具有任何以下值：  
  
-   packetPrivacy - 消息将被加密/解密  
  
-   packetIntegrity – 消息将被签名/验证  
  
-   call - 消息将按原样发送  
  
 中的 ref 属性\<通道 / > 元素可以将更改为 tcp 或 http。 端口和名称属性中\<通道 / > 元素也可以更改为显式值。  
  
 有关详细信息，请参阅 .NET Framework 开发人员指南（通道和格式化程序配置属性）。  
  
## <a name="see-also"></a>另请参阅  
 [调试业务流程](../core/debugging-orchestrations.md)