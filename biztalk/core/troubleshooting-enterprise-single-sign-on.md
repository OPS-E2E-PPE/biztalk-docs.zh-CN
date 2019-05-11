---
title: 企业单一登录故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb54af9f-a6ef-46c1-b987-2019cff3f837
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 905e3b188409dd4ab8a10042acbeb3ae23d936db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295880"
---
# <a name="troubleshooting-enterprise-single-sign-on"></a>企业单一登录故障排除
本主题提供有关使用企业单一登录 (SSO) 时所遇到的常见问题的信息。  

 开始对 SSO 环境进行故障排除时，逐一排查下表中的各项可能会很有用，以确保所有组件按预期正常工作：  


|                                                                      问题                                                                      |                                                                                                                                                                                                                      注释                                                                                                                                                                                                                       |
|----------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                        应用程序事件日志中是否有来自 SSO 系统的任何内容？                                         | 事件日志中的 SSO 消息可帮助您缩小 SSO 系统中问题的范围。 SSO 系统中消息的源为 ENTSSO。 **重要提示：** 许多 SSO 错误和事件显示为警告事件日志中不是作为错误。 当问题影响 SSO 服务的单个客户端时，SSO 系统生成警告，而问题影响整个 SSO 系统（所有客户端）时，则生成错误。 |
| 是否正确安装了SSO 服务？<br /><br /> SSO 服务是否按预期启动？<br /><br /> SSO 服务在哪个服务帐户下运行？ |                                                                                                                                                               确保 SSO 服务正确安装，并且服务帐户是 SSO 管理员组的成员。                                                                                                                                                                |
|                                                             SSO 数据库位于何处？                                                             |                                                                                                                           使用命令行 **ssoconfig -showdb**。 有关此命令的详细信息，请参阅[如何显示 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)。                                                                                                                           |
|                                                          正在使用哪个 SSO 服务器？                                                           |                                                                                                                                           使用命令行 **ssomanage -showserver**。 有关此命令的详细信息，请参阅[如何设置 SSO 服务器](../core/how-to-set-the-sso-server.md)。                                                                                                                                           |
|                                                       SSO 管理员帐户是什么？                                                       |                                                                                                                         使用命令行 **ssomanage –displaydb**。 有关此命令的详细信息，请参阅[如何显示 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)。                                                                                                                          |
|                                                          是否所有项都正确启用？                                                          |                                                                                                                         使用命令行 **ssomanage –displaydb**。 有关此命令的详细信息，请参阅[如何显示 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)。                                                                                                                          |
|                                                        关联应用程序是否存在？                                                        |                                                                                                                                 使用命令行 **ssomanage –listapps all**。 有关此命令的详细信息，请参阅[如何列出关联应用程序](../core/how-to-list-affiliate-applications.md)。                                                                                                                                 |
|               从外观上看，特定关联应用程序是否正确？<br /><br /> 哪些帐户在使用此关联应用程序？                |                                                                                               使用命令行**ssomanage-displayapp**<em>\<应用程序名称\></em>。 有关此命令的详细信息，请参阅[如何列出关联应用程序的属性](../core/how-to-list-the-properties-of-an-affiliate-application.md)。                                                                                                |
|                                               此关联应用程序是否有任何映射？                                               |                                                                                                                           使用命令行**ssomanage-listmappings**<em>\<应用程序名称\></em>。 有关此命令的详细信息，请参阅[如何列出用户映射](../core/how-to-list-user-mappings.md)。                                                                                                                            |
|                                                    哪些帐户是 SSO 组的成员？                                                    |                                                                                                                                                                                            验证所有 SSO 组和帐户的组成员关系。                                                                                                                                                                                             |
|                                          SSO 服务器的 COM+ 应用程序是否按预期运行？                                           |                                                                                                                                                  验证 SSO 服务器的 COM+ 应用程序。 **注意：** 此外可以检查事件日志的详细信息，如事件和警告消息。                                                                                                                                                  |

## <a name="known-issues"></a>已知问题  

#### <a name="entsso-service-fails-to-start"></a>ENTSSO 服务启动失败  

##### <a name="problem"></a>问题  
 ENTSSO 服务启动失败。  

##### <a name="cause"></a>原因  
 如果 ENTSSO 服务没有在有效的 SSO 管理员帐户下运行，将无法启动。  

##### <a name="resolution"></a>解决方法  
 请为 ENTSSO 服务指定有效的 SSO 管理员帐户，然后从服务控制管理器 (SCM) 管理单元重新启动该服务。  

#### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a>依赖于企业单一登录服务 (ENTSSO) 的 BizTalk 服务在重新启动之后无法启动  

##### <a name="problem"></a>问题  
 BTSSvc$BizTalkServerApplication 依赖于企业单一登录服务 (ENTSSO)，且在重新启动之后的启动过程中可能超时。  

##### <a name="cause"></a>原因  
 企业单一登录服务可能需要约 3 分钟时间才能启动。  

##### <a name="resolution"></a>解决方法  
 配置"BizTalk 服务 BizTalk 组：具有自动 （延迟启动） 启动类型选项 BizTalkServerApplication"服务。 这将在所有自动服务完成其启动例程后开始启动服务。  

#### <a name="cannot-access-an-affiliate-application"></a>无法访问关联应用程序  

##### <a name="problem"></a>问题  
 如果与关联应用程序关联的应用程序管理员帐户无效，则企业单一登录禁用关联应用程序。  

##### <a name="cause"></a>原因  
 SSO 应用程序管理员帐户无效。  

##### <a name="resolution"></a>解决方法  
 在创建关联应用程序之前，请确保 SSO 应用程序管理员帐户有效。 然后，您必须使关联应用程序能够使用该应用程序。  

#### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a>连接到客户端计算机时发生 RPC 错误  

##### <a name="problem"></a>问题  
 当用户运行命令如**ssomanage-displayapp**<em>\<applicationname\></em>，其中计算机尝试连接到远程 SSO 服务器以检索信息，他们会收到以下错误：错误：0x800706BA:RPC 服务器不可用。  

##### <a name="cause"></a>原因  
 当用户指定了错误的服务器信息时，或者当 SSO 服务在远程服务器上不可用时，会发生此错误。  

##### <a name="resolution"></a>解决方法  

-   按照中的步骤[如何设置 SSO 服务器](../core/how-to-set-the-sso-server.md)以确保您连接到正确的 SSO 服务器。  

-   确保 SSO 服务已启用并且运行在您要连接到的 SSO 服务器中。  

#### <a name="master-secret-is-missing-or-corrupt"></a>缺少主密钥，或者主密钥已损坏  

##### <a name="problem"></a>问题  
 缺少主密钥，或者主密钥已损坏。 主密钥通常在配置期间生成。 如果缺少该密钥，当企业单一登录服务启动时事件日志中便会显示下列消息之一。  

 MessageId=10520  

 Severity=Warning  

 SSO_WARN_NO_SECRETS  

 MessageId=10565  

 Severity=Error  

 SSO_ERROR_SECRET_VALIDATE_FAILED  

 MessageId=10521  

 Severity=Error  

 SSO_ERROR_SECRETS_NOT_LOADED  

##### <a name="cause"></a>原因  
 如果企业单一登录服务 (SSO) 在某个服务帐户下运行时生成密钥，又更改了该服务帐户，则可能出现此问题。 但是，该密钥以加密的形式存储在注册表中，并且使用基于此服务帐户标识（ENTSSO 在该帐户下运行）的密钥进行加密。  

##### <a name="resolution"></a>解决方法  
 将 ENTSSO 在其下运行的服务帐户更改为创建主密钥时的原始服务帐户。  

 更改 ENTSSO 服务帐户：  

1.  备份主密钥。 有关详细信息，请参阅[如何返回主密钥](../core/how-to-back-up-the-master-secret.md)。  

2.  停止企业单一登录服务。  

3.  更改服务帐户。  

4.  重新启动 SSO，并忽略有关受损密钥的任何事件日志错误。  

5.  还原主密钥。 有关详细信息，请参阅[如何还原主密钥](../core/how-to-restore-the-master-secret.md)。  

## <a name="see-also"></a>请参阅  
 [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)