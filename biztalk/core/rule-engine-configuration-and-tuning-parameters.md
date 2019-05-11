---
title: 规则引擎的配置和优化参数 |Microsoft Docs
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
ms.openlocfilehash: 357d891eb783192e4b5c9c82bd2f5a8dc9f9061d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254656"
---
# <a name="rule-engine-configuration-and-tuning-parameters"></a>规则引擎的配置和优化参数
下表列出了可能可用于配置验证和故障排除的注册表项。 这些注册表项存储在下**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BusinessRules\3.0**。  
  
 除了列出的前三个密钥，这些注册表项都用于允许产品，而不是用户 — 若要自定义规则引擎。 所有这些创建安装;但是，不提供任何界面来设置这些值。  
  
 表中的列的定义如下所示：  
  
-   **名称**。 注册表项的名称。  
  
-   **说明**。 有关使用密钥的位置的简短说明。  
  
-   **配置默认值**。 如果键不存在时返回值。  
  
-   **安装默认**。 安装规则引擎时由 BizTalk Server 设置的值。  
  
|“属性”|Description|配置默认值|安装默认值|  
|----------|-----------------|--------------------|---------------------|  
|InstallPath|在配置时使用的 BRE 文件的位置。|(null)|C:\Program Files\Common Files\Microsoft BizTalk （或 64 位操作系统上的 C:\Program Files (x86) \Common Files\Microsoft BizTalk）|  
|DatabaseServer|使用数据库服务器。|(空字符串)|在配置 BRE 过程中指定的数据库服务器的名称。|  
|DatabaseName|若要使用的数据库的名称。|(空字符串)|在配置 BRE 过程中指定的数据库的名称。 通常情况下，为 BizTalkRuleEngineDb|  
|PubSubAdapterAssembly|发布/订阅适配器的程序集名称。|Microsoft.RuleEngine|Microsoft.RuleEngine|  
|PubSubAdapterClass|发布/订阅适配器的类名。|Microsoft.RuleEngine.PubSubAdapter|Microsoft.RuleEngine.PubSubAdapter|  
|DeploymentDriverAssembly|部署驱动程序的程序集名称。|Microsoft.RuleEngine|Microsoft.BizTalk.RuleEngineExtensions|  
|DeploymentDriverClass|部署驱动程序的类名称。|Microsoft.RuleEngine.RuleSetDeploymentDriver|Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver|  
|TrackingInterceptorAssembly|跟踪侦听器的程序集名称。|(空字符串)|Microsoft.BizTalk.RuleEngineExtensions|  
|TrackingInterceptorClass|跟踪侦听器的类名。|(空字符串)|Microsoft.BizTalk.RuleEngineExtensions.RuleSetTrackingInterceptor|  
|TranslationTimeout|最大时间 （毫秒） 可用于翻译规则集。 **注意：** 这可以通过在每个规则集的基础上使用 RuleSetConfiguration）。|60000 （1 分钟）|60000|  
|UpdateServiceName|更新服务，.NET 远程处理用于查找服务的名称。|RemoteUpdateService|RemoteUpdateService|  
|UpdateServiceHost|承载更新服务，.NET 远程处理用于查找服务的计算机。 **注意：** 当前，服务将传入的消息限制为仅同一台计算机。|localhost|localhost|  
|UpdateServicePort|更新服务，.NET 远程处理用于查找该服务所使用的 TCP 端口号。|3132|3132|  
|CacheEntries|缓存的更新服务的规则集的最大数目。|32|32|  
|CacheTimeout|以秒为单位从更新服务缓存条目的时间。|3600 （1 小时）|3600|  
|PollingInterval|时间 （秒） 更新服务检查 SqlRuleStore 以查找更新。|60 （1 分钟）|60|  
|SqlTimeout|访问 SQL 规则存储的 SQL 命令的超时值。 此键的值解释，如下所示：<br /><br /> < 0-使用.NET 默认值 （30 秒）<br /><br /> = 0-无超时<br /><br /> 查询超时之前的 > 0 的最长时间|-1|-1|  
  
 此外可以添加注册表项中所述，名为 StaticSupport[类的调用静态成员](../core/invoking-static-members-of-a-class.md)。  
  
 注册表设置是全局的承载规则引擎实例的所有应用程序。 可以使用应用程序配置文件来覆盖这些注册表设置在应用程序级别。 有关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，主机应用程序是 BTSNTSvc.exe 和配置文件为 BTSNTSvc.exe.config，可以在中找到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装目录。  需要指定您想要覆盖应用程序配置文件如下所示的配置参数的值：  
  
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