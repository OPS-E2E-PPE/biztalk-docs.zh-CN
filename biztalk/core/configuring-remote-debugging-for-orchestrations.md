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
# <a name="configuring-remote-debugging-for-orchestrations"></a><span data-ttu-id="e375f-102">为业务流程配置远程调试</span><span class="sxs-lookup"><span data-stu-id="e375f-102">Configuring Remote Debugging for Orchestrations</span></span>
<span data-ttu-id="e375f-103">您可以完全配置客户端和服务器之间的远程调试。</span><span class="sxs-lookup"><span data-stu-id="e375f-103">You can completely configure remote debugging between client and server.</span></span> <span data-ttu-id="e375f-104">在 Microsoft.XLANGs.BizTalk.Client.dll.config 中指定客户端配置。在 BTSNTSvc.exe.config 中指定服务器配置。以下是为每个默认配置的列表。</span><span class="sxs-lookup"><span data-stu-id="e375f-104">The client configuration is specified in Microsoft.XLANGs.BizTalk.Client.dll.config. The server configuration is specified in BTSNTSvc.exe.config. The following is a listing of the default configuration for each.</span></span>  
  
## <a name="client-microsoftxlangsbiztalkclientdllconfig"></a><span data-ttu-id="e375f-105">Client (Microsoft.XLANGs.BizTalk.Client.dll.config)</span><span class="sxs-lookup"><span data-stu-id="e375f-105">Client (Microsoft.XLANGs.BizTalk.Client.dll.config)</span></span>  
  
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
  
## <a name="serverbtsntsvcexeconfig"></a><span data-ttu-id="e375f-106">Server(BTSNTSvc.exe.config)</span><span class="sxs-lookup"><span data-stu-id="e375f-106">Server(BTSNTSvc.exe.config)</span></span>  
  
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
  
## <a name="configurable-parameters"></a><span data-ttu-id="e375f-107">可配置参数</span><span class="sxs-lookup"><span data-stu-id="e375f-107">Configurable Parameters</span></span>  
 <span data-ttu-id="e375f-108">默认值可确保最高的安全性配置。</span><span class="sxs-lookup"><span data-stu-id="e375f-108">The default ensures maximum security configuration.</span></span> <span data-ttu-id="e375f-109">但是留给用户可以更改这些默认值，并且这些文件处于 acl 的控制下，因为它们位于 program files 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e375f-109">However it is left to the user to change these defaults and these files are ACL'ed since they are in the program files folder.</span></span>  
  
 <span data-ttu-id="e375f-110">元素\<提供程序 / > 是可选的如果未提供会导致将互相进行身份验证使用自定义接收器对通道。</span><span class="sxs-lookup"><span data-stu-id="e375f-110">The element \<provider/> is optional and if not provided will cause the channels not to be mutually authenticated using the custom sinks.</span></span> <span data-ttu-id="e375f-111">但是，这是一个危险选项，以便关闭，因为它将开放通道。</span><span class="sxs-lookup"><span data-stu-id="e375f-111">However this is a dangerous option to turn off as it will open up the channels.</span></span> <span data-ttu-id="e375f-112">这可以更好的性能和何时各种安全攻击，不是问题。</span><span class="sxs-lookup"><span data-stu-id="e375f-112">This can be done for better performance and when security attacks are not a concern.</span></span>  
  
 <span data-ttu-id="e375f-113">通道元素可具有属性 rejectRemoteRequests = true，这将只启用本地调用并且拒绝远程请求。</span><span class="sxs-lookup"><span data-stu-id="e375f-113">The channel element can have property rejectRemoteRequests = true which will enable only local calls and reject remote requests.</span></span>  
  
 <span data-ttu-id="e375f-114">中的 securityPackage 属性\<serverProviders / > 元素可以具有任何以下值：</span><span class="sxs-lookup"><span data-stu-id="e375f-114">The securityPackage attribute in the \<serverProviders/> element can have any of the following values:</span></span>  
  
- <span data-ttu-id="e375f-115">协商</span><span class="sxs-lookup"><span data-stu-id="e375f-115">negotiate</span></span>  
  
- <span data-ttu-id="e375f-116">ntlm</span><span class="sxs-lookup"><span data-stu-id="e375f-116">ntlm</span></span>  
  
- <span data-ttu-id="e375f-117">Kerberos</span><span class="sxs-lookup"><span data-stu-id="e375f-117">Kerberos</span></span>  
  
  <span data-ttu-id="e375f-118">中的 authenticationLevel 属性\<serverProviders / > 元素可以具有任何以下值：</span><span class="sxs-lookup"><span data-stu-id="e375f-118">The authenticationLevel attribute in the \<serverProviders/> element can have any of the following values:</span></span>  
  
- <span data-ttu-id="e375f-119">packetPrivacy-消息将被加密/解密</span><span class="sxs-lookup"><span data-stu-id="e375f-119">packetPrivacy  - the messages will be encrypted/decrypted</span></span>  
  
- <span data-ttu-id="e375f-120">packetIntegrity – 消息将被签名/验证</span><span class="sxs-lookup"><span data-stu-id="e375f-120">packetIntegrity – the messages will be signed/verified</span></span>  
  
- <span data-ttu-id="e375f-121">call-消息将按原样发送</span><span class="sxs-lookup"><span data-stu-id="e375f-121">call  - the messages will be sent as is</span></span>  
  
  <span data-ttu-id="e375f-122">中的 ref 属性\<通道 / > 元素可以更改为 tcp 或 http。</span><span class="sxs-lookup"><span data-stu-id="e375f-122">The ref attribute in the \<channel/> element can be changed to tcp or http.</span></span> <span data-ttu-id="e375f-123">Port 和 name 属性中\<通道 / > 元素也可以更改为显式值。</span><span class="sxs-lookup"><span data-stu-id="e375f-123">The port and name attribute in the \<channel/> element can be changed as well to explicit values.</span></span>  
  
  <span data-ttu-id="e375f-124">有关详细信息，请参阅.NET Framework 开发人员指南 （通道和格式化程序配置属性）。</span><span class="sxs-lookup"><span data-stu-id="e375f-124">For more information, see .NET Framework Developer's Guide (Channel and formatter configuration properties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e375f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e375f-125">See Also</span></span>  
 [<span data-ttu-id="e375f-126">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="e375f-126">Debugging Orchestrations</span></span>](../core/debugging-orchestrations.md)