---
title: 后台示例方案的信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security examples [TMA], background information
- DFD
- TMA, examples
ms.assetid: f9518fe7-9892-44f5-8e05-fe48bdb5161a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9424de9c530fb855b21df787f87e674e8a561f5e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978446"
---
# <a name="background-information-for-sample-scenarios"></a>示例方案的背景信息
本主题介绍本部分中各个方案的背景信息。  
  
## <a name="background-for-all-scenarios"></a>所有方案的背景信息  
 在主要威胁模型会议前，我们收集了以下背景信息。 此信息适用于为示例结构确定的所有使用方案：  
  
-   结构的边界和作用域  
  
-   可信组件与不可信组件之间的边界  
  
-   每个组件的配置和管理模式  
  
-   有关其他组件和应用程序的假设  
  
### <a name="boundaries-and-scope-of-the-architecture"></a>结构的边界和作用域  
  
-   防火墙 2 有助于保护电子商务域中的服务器和应用程序免受外围网络和您的环境中其他任何域（例如，公司域或其他应用程序的域）的影响。  
  
-   防火墙 2 将所有传入和传出的通信路由到电子商务域。  
  
-   访问 BizTalk Server 环境的所有用户组和帐户都必须是电子商务域中的全局组。  
  
-   仅将访问权限授予主机实例的服务帐户；在文件、SQL 或消息队列的接收服务器中存放消息的任何应用程序；以及 BizTalk Server、企业单一登录 (SSO) 和 Windows 的管理员。  
  
### <a name="boundaries-between-trusted-and-untrusted-companies"></a>受信任的公司与不受信任的公司之间的边界  
  
-   防火墙 2 将所有传入和传出的通信路由到电子商务域。  
  
-   使用其他 BizTalk 主机作为 BizTalk Server 内应用程序之间的安全边界。  
  
-   仅在您信任应用程序内的代码时才使用受信任的主机（例如，不要在受信任的主机中运行第三方组件）。  
  
### <a name="configuration-and-administration-model-for-each-component"></a>每个组件的配置和管理模式  
 **配置模型：**  
  
- BizTalk Server 运行时组件仅安装在 BizTalk Server 上。  
  
- 主密钥服务器不包含任何其他组件。  
  
- SQL Server 包含所有 BizTalk Server 数据库。  
  
- 外围网络中的服务器不包含任何 BizTalk Server 组件。  
  
- 使用管理客户端来管理电子商务域中的所有服务器。  
  
  **管理模型：**  
  
- 管理员（使用终端服务或远程桌面连接）从台式计算机（或便携式计算机）连接到具有管理工具的计算机。 管理员在连接到具有管理工具的计算机后，可以使用 BizTalk 管理工具来管理域中的所有服务器和应用程序。  
  
### <a name="assumptions-about-other-components-and-applications"></a>有关其他组件和应用程序的假设  
 与 BizTalk Server 环境交互的所有其他应用程序和组件都位于电子商务域之外的域中（例如，在外围网络中）。 这些应用程序和组件与 BizTalk Server 环境之间通过防火墙 2 进行通信。  
  
 BizTalk Server 的所有第三方应用程序均来自受信任的供应商。  
  
### <a name="data-flow-diagrams"></a>数据流关系图  
 每个使用方案的背景信息的最终元素是一个数据流关系图 (DFD)。 DFD 阐释了数据如何在结构中传输。 每个方案都具有不同的 DFD。 在本文档中，数据流关系图包含下图中所示的元素：  
  
 **图 1 DFD 的元素**  
  
 ![DFD 的元素](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")  
  
## <a name="background-for-adapter-scenarios"></a>适配器方案的背景信息  
 在此示例结构中，我们根据可开箱即用的某些适配器确定了以下使用方案：  
  
- HTTP 和 SOAP (Web Services) 适配器方案  
  
- BizTalk 消息队列适配器方案  
  
- 文件适配器方案  
  
- FTP 适配器方案  
  
  对于每个方案，我们均遵循以下步骤来完成威胁模型分析：  
  
- 收集背景信息  
  
- 创建和分析威胁模型  
  
- 查看威胁  
  
- 确定缓解措施  
  
  对于每个方案，我们已尝试为各种攻击可能表示的威胁级别评定通用等级。 不过，根据您的环境或经验，对特定威胁建议评定的等级可能不同于我们给出的等级。 与所有安全方案一样，您自己的数据对于确定威胁级别是最可靠的，建议您使用我们的分析和结果作为指导来进行自己的分析。  
  
  背景信息 — 除数据流关系图 (DFD)-对于所有使用方案是相同的。 在接下来的部分中，我们将显示每个方案的 DFD。  
  
## <a name="see-also"></a>请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [规划安全性](../core/planning-for-security.md)   
 [中小型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)