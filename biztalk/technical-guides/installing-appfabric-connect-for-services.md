---
title: "安装 AppFabric Connect 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1de3bf49-e3cc-4d3f-9883-9a2c472f3647
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3d10862a6a60d173cc68c25d0dcc463d2f16e38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-appfabric-connect-for-services"></a>安装 AppFabric 连接服务
本指南将说明了如何安装 BizTalk Server 2010 功能包 （2010 年 10 月）。 功能包提供的增强功能的服务功能的安装 BizTalk Server 2010 AppFabric 连接**BizTalk WCF 服务发布向导**和**WCF 适配器服务开发向导**. 已安装的功能包后，你将能够将扩展你的本地 BizTalk Server 项目或者是 LOB 应用程序云的添加 Windows Azure AppFabric Service Bus 终结点。  
  
## <a name="prerequisites"></a>先决条件  
 BizTalk Server 2010 功能包到 BizTalk WCF 服务发布向导和 WCF 适配器服务开发向导提供增强功能。 BizTalk Server 2010 开发人员工具中提供了 BizTalk WCF 服务发布向导时，WCF 适配器服务开发向导时使用 BizTalk 适配器包 2010年。 因此，在安装的功能包之前，你必须具有 BizTalk Server 2010 开发人员工具或 BizTalk 适配器包 2010年或两者都安装。 如果你只有一个的这些已安装，则仅与父产品安装向导将更新作为功能包安装的一部分。  
  
 除此之外，有一些使用这些向导的先决条件。 每个向导的先决条件的完整列表被列入描述如何使用向导的主题。 主题的链接提供下[使用服务连接 AppFabric](../technical-guides/installing-appfabric-connect-for-services.md#BKMK_Using)。  
  
## <a name="installing-biztalk-server-2010-feature-pack"></a>安装 BizTalk Server 2010 功能包  
 执行以下步骤以安装 AppFabric 连接的服务：  
  
#### <a name="to-install-the-feature-pack"></a>若要安装的功能包  
  
1.  下载服务可从安装 AppFabric 连接[http://go.microsoft.com/fwlink/?LinkId=204701](http://go.microsoft.com/fwlink/?LinkId=204701)。 运行自解压的 BizTalkServer2010_FeaturePack.exe 文件，以启动功能包安装程序。  
  
2.  上**欢迎**页上，单击**下一步**。  
  
3.  接受许可条款，然后单击**下一步**然后在以下屏幕中，单击**下一步**试。  
  
4.  在向导完成功能包安装后，单击**完成**。  
  
##  <a name="BKMK_Using"></a>用 AppFabric 连接服务  
 安装后 AppFabric 连接的服务，可以执行以下操作：  
  
-   使用**BizTalk WCF 服务发布向导**作为与 Azure AppFabric Service bus 中继终结点的 WCF 服务公开 BizTalk 项目 （业务流程、 架构、 等）。 有关详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=204700](http://go.microsoft.com/fwlink/?LinkId=204700)。  
  
-   使用**WCF 适配器服务开发向导**作为与 Azure AppFabric Service bus 中继终结点的 WCF 服务公开对 LOB 应用程序的操作。 有关详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=204699](http://go.microsoft.com/fwlink/?LinkId=204699)。  
  
## <a name="uninstalling-biztalk-server-2010-feature-pack"></a>卸载 BizTalk Server 2010 功能包  
 此部分提供有关卸载 AppFabric 连接的服务说明。  
  
#### <a name="to-uninstall-the-feature-pack"></a>若要卸载的功能包  
  
1.  打开 Windows 更新，请单击**查看更新历史记录**，然后单击**已安装的更新**。  
  
2.  从已安装的更新，列表下**BizTalk Server 2010**类别中，右键单击**BizTalk Server 2010 功能包 （2010 年 10 月） LDR**，然后选择**卸载**. 在确认你是否想要卸载的功能包对话框中，单击**是**。  
  
3.  刷新列表以验证功能包是否已卸载。  
  
## <a name="copyright"></a>版权信息  
 本文档支持在最终商业版本发布之前可能进行重大更改的软件产品的预备版本。  本文档提供的信息仅供参考，Microsoft 对本文档不做任何明示或暗示的担保。  本文档中的信息（包括引用的 URL 和其他 Internet 网站）如有变更，恕不另行通知。  所有使用风险或因使用本文档而导致的结果都由用户自行承担。  除非特别声明，本文档示例中提及的公司、组织、产品、域名、电子邮件地址、徽标、人物、地点和事件纯属虚构，  我们无意将它们与任何真实的公司、组织、产品、域名、电子邮件地址、徽标、人员、地点或事件挂钩，请勿“对号入座”。  用户有责任遵守所有适用的版权法/著作权法。  在不限制版权所辖权利的前提下，未经 Microsoft Corporation 的明确书面许可，本文档的任何部分不得被复制、存储或引进检索系统，或者以任何形式、任何方式（电子、机械、影印、录音等）或为任何目的进行传播。  
  
 Microsoft 可能拥有本文档所涵盖主题的专利、专利申请、商标、版权或其他知识产权。  除非 Microsoft 提供了明确的书面许可协议，否则提供本文档并不意味着赋予您这些专利、商标、版权或其他知识产权的任何许可。  
  
 © 2010 Microsoft Corporation。  保留所有权利。  
  
 Microsoft、Active Directory、ActiveX、BizTalk、Excel、InfoPath、JScript、IntelliSense、Internet Explorer、MSDN、Outlook、PivotChart、PivotTable、PowerPoint、SharePoint、Tahoma、Visio、Visual Basic、Visual C++、Visual C#、Visual SourceSafe、Visual Studio、Win32、Windows、Windows NT、Windows PowerShell、Windows Server、Windows Server System 和 Windows Vista 是 Microsoft 集团公司的商标。  
  
 SAP、R/3、mySAP、mySAP.com、xApps、xApp、SAP NetWeaver、本文档中提及的其他 SAP 产品和服务以及其各自的徽标是 SAP AG 在德国和全球多个国家/地区的商标或注册商标。 本文档中提及的所有其他产品和服务的名称分别为它们各自公司的商标。 本文档中包含的数据只用于提供信息。 各个国家/地区的产品规范可能有所不同。  
  
 所有其他商标均为其各自所有者的财产。