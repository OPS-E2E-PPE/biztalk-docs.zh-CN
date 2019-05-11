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
ms.openlocfilehash: b135dc4b322a2fe09289e971021ddbb387cf2915
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530641"
---
# <a name="background-information-for-sample-scenarios"></a>示例方案的背景信息
本主题包含在本部分方案的背景信息。  
  
## <a name="background-for-all-scenarios"></a>所有方案的背景信息  
 在主要威胁模型会议之前, 我们收集了以下背景信息。 此信息适用于我们在示例体系结构发现的所有使用方案：  
  
-   边界和体系结构的作用域  
  
-   受信任和不受信任的组件之间的边界  
  
-   每个组件的配置和管理模型  
  
-   有关其他组件和应用程序的假设  
  
### <a name="boundaries-and-scope-of-the-architecture"></a>边界和体系结构的作用域  
  
-   防火墙 2 有助于保护服务器和电子商务域中的应用程序从外围网络和你的环境 （例如，公司的域或其他应用程序的域） 的任何其他域。  
  
-   防火墙 2 路由所有传入和传出的电子商务域的流量。  
  
-   所有用户组和访问 BizTalk Server 环境的帐户必须都是电子商务域中的全局组。  
  
-   访问仅限于该主机实例; 的服务帐户删除消息的接收服务器中的文件、 SQL 或消息队列; 任何应用程序管理员和 BizTalk Server、 企业单一登录 (SSO) 和 Windows。  
  
### <a name="boundaries-between-trusted-and-untrusted-companies"></a>受信任和不受信任的公司之间的边界  
  
-   防火墙 2 路由所有传入和传出的电子商务域的流量。  
  
-   使用不同的 BizTalk 主机作为 BizTalk Server 中的应用程序之间的安全边界。  
  
-   仅当你信任的应用程序 （例如，不要在受信任的主机中运行第三方组件） 中的代码，请使用受信任的主机。  
  
### <a name="configuration-and-administration-model-for-each-component"></a>每个组件的配置和管理模型  
 **配置模型：**  
  
- 仅在 BizTalk 服务器上安装 BizTalk Server 运行时组件。  
  
- 主密钥服务器不包含任何其他组件。  
  
- SQL Server 包含所有 BizTalk Server 数据库。  
  
- 服务器在外围网络中的没有任何 BizTalk Server 组件。  
  
- 管理客户端用于管理电子商务域中的所有服务器。  
  
  **管理模型：**  
  
- 从桌面 （或便携式计算机） 中，管理员身份连接到具有管理工具 （使用终端服务或远程桌面连接） 的计算机。 管理员在连接到的计算机的管理工具后，管理员可以使用 BizTalk 管理工具来管理所有服务器和域中的应用程序。  
  
### <a name="assumptions-about-other-components-and-applications"></a>有关其他组件和应用程序的假设  
 所有其他应用程序和与 BizTalk Server 环境交互的组件位于之外 （例如，在外围网络中） 的电子商务域的域。 这些应用程序和组件到和从 BizTalk Server 环境的流量都通过防火墙 2。  
  
 BizTalk Server 的任何第三方应用程序来自受信任的供应商。  
  
### <a name="data-flow-diagrams"></a>数据流关系图  
 每个使用方案的背景信息的最后一个元素是数据数据流关系图 (DFD)。 DFD 阐释了数据如何流经体系结构。 每个方案都包含不同的 DFD。 在本文档中，数据流关系图包含下图中显示的元素。  
  
 **图 1 DFD 的元素**  
  
 ![DFD 的元素](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")  
  
## <a name="background-for-adapter-scenarios"></a>适配器方案的背景信息  
 在示例体系结构中，我们发现基于以下使用方案上某些适配器可以使用开箱：  
  
- HTTP 和 SOAP (Web services) 适配器方案  
  
- BizTalk 消息队列适配器方案  
  
- 文件适配器方案  
  
- FTP 适配器方案  
  
  对于每个方案中，我们将遵循以下步骤来完成威胁模型分析：  
  
- 收集背景信息  
  
- 创建和分析威胁模型  
  
- 查看威胁  
  
- 确定缓解措施  
  
  对于每个方案中，我们已尝试进行评定通用等级的各种攻击可能表示的威胁级别。 但是，您的环境或体验可能会建议对特定威胁需要不同级别，比我们给出它。 与所有安全方案，你自己的数据是最可靠确定威胁级别，以及我们建议您进行您自己的分析，使用我们的分析和结果作为指导。  
  
  背景信息 — 除数据流关系图 (DFD)-对于所有使用方案是相同的。 在接下来的部分中，我们将介绍每个方案的 dfd:。  
  
## <a name="see-also"></a>请参阅  
 [威胁模型分析](../core/threat-model-analysis.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)   
 [规划安全性](../core/planning-for-security.md)   
 [中小型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)