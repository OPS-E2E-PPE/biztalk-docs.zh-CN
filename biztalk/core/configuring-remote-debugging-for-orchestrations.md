---
title: 为业务流程配置远程调试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Microsoft.XLANGs.BizTalk.Client.dll.config, code sample
- BTSNTSvc.exe.config, code sample
- orchestrations, debugging
- building, debugging
- building, code sample
ms.assetid: 722efaec-d160-48dc-b94b-0733c9904d98
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96fa7775bc6e67e0c56e2b93e9ca334ac361794c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390911"
---
# <a name="configuring-remote-debugging-for-orchestrations"></a>为业务流程配置远程调试
您可以完全配置客户端和服务器之间的远程调试。 在 Microsoft.XLANGs.BizTalk.Client.dll.config 中指定客户端配置。在 BTSNTSvc.exe.config 中指定服务器配置。以下是为每个默认配置的列表。  
  
## <a name="client-microsoftxlangsbiztalkclientdllconfig"></a>Client (Microsoft.XLANGs.BizTalk.Client.dll.config)  
  
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
  
## <a name="serverbtsntsvcexeconfig"></a>Server(BTSNTSvc.exe.config)  
  
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
  
## <a name="configurable-parameters"></a>可配置参数  
 默认值可确保最高的安全性配置。 但是留给用户可以更改这些默认值，并且这些文件处于 acl 的控制下，因为它们位于 program files 文件夹。  
  
 元素\<提供程序 / > 是可选的如果未提供会导致将互相进行身份验证使用自定义接收器对通道。 但是，这是一个危险选项，以便关闭，因为它将开放通道。 这可以更好的性能和何时各种安全攻击，不是问题。  
  
 通道元素可具有属性 rejectRemoteRequests = true，这将只启用本地调用并且拒绝远程请求。  
  
 中的 securityPackage 属性\<serverProviders / > 元素可以具有任何以下值：  
  
- 协商  
  
- ntlm  
  
- Kerberos  
  
  中的 authenticationLevel 属性\<serverProviders / > 元素可以具有任何以下值：  
  
- packetPrivacy-消息将被加密/解密  
  
- packetIntegrity – 消息将被签名/验证  
  
- call-消息将按原样发送  
  
  中的 ref 属性\<通道 / > 元素可以更改为 tcp 或 http。 Port 和 name 属性中\<通道 / > 元素也可以更改为显式值。  
  
  有关详细信息，请参阅.NET Framework 开发人员指南 （通道和格式化程序配置属性）。  
  
## <a name="see-also"></a>请参阅  
 [调试业务流程](../core/debugging-orchestrations.md)