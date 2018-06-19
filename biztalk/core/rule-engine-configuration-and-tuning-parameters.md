---
title: 规则引擎配置和优化参数 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, registry keys
- registry keys
- Business Rules Engine, registry keys
- troubleshooting, business rules
- validating, business rules
- business rules, validating
ms.assetid: cb0bcffe-bbc6-4495-84d2-2a822c3413b3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6d2acc5b70f7a2be120db5159f893922135a429
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270333"
---
# <a name="rule-engine-configuration-and-tuning-parameters"></a>规则引擎的配置和优化参数
下表包含的注册表项列表对于配置验证和疑难解答可能非常有用。 这些注册表项存储在下**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BusinessRules\3.0**。  
  
 除了前三项之外，这些注册表项都用于允许产品（而不是用户）自定义规则引擎。 所有这些注册表项都是在安装时创建的。但是，没有提供任何界面来设置这些值。  
  
 表列的定义如下：  
  
-   **名称**。 注册表项的名称。  
  
-   **说明**。 关于注册项的位置或用法的简短说明。  
  
-   **配置默认**。 该注册项不存在时返回的值。  
  
-   **安装默认**。 在安装规则引擎时由 BizTalk Server 设置的值。  
  
|Name|Description|配置默认值|安装默认值|  
|----------|-----------------|--------------------|---------------------|  
|InstallPath|配置时使用的 BRE 文件的位置。|(null)|C:\Program Files\Common Files\Microsoft BizTalk（或 64 位操作系统上的 C:\Program Files (x86)\Common Files\Microsoft BizTalk）|  
|DatabaseServer|所使用的数据库服务器。|(空字符串)|配置 BRE 过程中指定的数据库服务器的名称。|  
|DatabaseName|要使用的数据库的名称。|(空字符串)|配置 BRE 过程中指定的数据库的名称。 通常为 BizTalkRuleEngineDb|  
|PubSubAdapterAssembly|发布/订阅适配器的程序集名称。|Microsoft.RuleEngine|Microsoft.RuleEngine|  
|PubSubAdapterClass|发布/订阅适配器的类名。|Microsoft.RuleEngine.PubSubAdapter|Microsoft.RuleEngine.PubSubAdapter|  
|DeploymentDriverAssembly|部署驱动程序的程序集名称。|Microsoft.RuleEngine|Microsoft.BizTalk.RuleEngineExtensions|  
|DeploymentDriverClass|部署驱动程序的类名。|Microsoft.RuleEngine.RuleSetDeploymentDriver|Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver|  
|TrackingInterceptorAssembly|跟踪侦听器的程序集名称。|(空字符串)|Microsoft.BizTalk.RuleEngineExtensions|  
|TrackingInterceptorClass|跟踪侦听器的类名。|(空字符串)|Microsoft.BizTalk.RuleEngineExtensions.RuleSetTrackingInterceptor|  
|TranslationTimeout|可用于翻译规则集的最长时间（以毫秒计）。 **注意：** 这可以每个 ruleset 的基础上覆盖，通过使用 RuleSetConfiguration)。|60000（1 分钟）|60000|  
|UpdateServiceName|更新服务的名称，.NET 远程处理将使用该名称来查找服务。|RemoteUpdateService|RemoteUpdateService|  
|UpdateServiceHost|承载更新服务的计算机，.NET 远程处理将使用该计算机来查找服务。 **注意：** 服务当前限制到同一台计算机的传入消息。|localhost|localhost|  
|UpdateServicePort|更新服务所使用的 TCP 端口号，.NET 远程处理将使用该端口号来查找服务。|3132|3132|  
|CacheEntries|更新服务缓存的规则集的最大数目。|32|32|  
|CacheTimeout|条目在更新服务缓存中保存的时间（以秒计）。|3600（1 小时）|3600|  
|PollingInterval|更新服务检查 SqlRuleStore 以查找更新的时间（以秒计）。|60 （1 分钟）|60|  
|SqlTimeout|访问 SQL 规则存储的 SQL 命令的超时值。 此键的值解释如下：<br /><br /> < 0-使用.NET 默认值 （30 秒）<br /><br /> = 0 - 无超时限制<br /><br /> 查询超时之前的 > 0 的最长时间|-1|-1|  
  
 你还可以添加注册表项中所述，名为 StaticSupport[调用的类的静态成员](../core/invoking-static-members-of-a-class.md)。  
  
 注册表设置对承载规则引擎实例的所有应用程序是全局的。 通过使用应用程序配置文件，可以在应用程序级别重写这些注册表设置。 有关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，主机应用程序是 BTSNTSvc.exe，配置文件是 BTSNTSvc.exe.config，你可以在找到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装目录。  您需要为希望在应用程序配置文件中重写的配置参数指定值，如下所示：  
  
```  
<configuration>  
    <configSections>  
        <section name="Microsoft.RuleEngine" type="System.Configuration.SingleTagSectionHandler" />  
    </configSections>  
    <Microsoft.RuleEngine  
        UpdateServiceHost="localhost"  
        UpdateServicePort="3132"  
        UpdateServiceName="RemoteUpdateService"  
        CacheEntries="32"  
        CacheTimeout="3600"  
        PollingInterval="60"  
        TranslationTimeout="3600"  
        CachePruneInterval="60"  
        DatabaseServer="(localhost)"  
        DatabaseName="BizTalkRuleEngineDb"  
        SqlTimeout="-1"  
        StaticSupport="1"  
    />  
</configuration>  
```